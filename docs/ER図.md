```mermaid
erDiagram
    users ||..o{ orders : ""
    users ||..o{ payment_failures : ""
    users ||..o{ subscriptions : ""
    users ||..o{ reviews : ""
    users ||..o{ cart_items : ""
    users ||..|| sellers : ""
    users ||..o{ payment_methods : ""
    users ||..o{ shipping_addresses : ""
    users ||..o{ invoices : ""
    
    invoices ||..o{ orders : ""
    invoices ||..o{ subscriptions : ""
    invoices ||..o{ payment_failures : ""

    subscriptions ||--o| shipping_addresses : "配送先"
    subscriptions ||..|{ subscription_plans : "定期購入プラン"
    subscription_plans ||..|{ products : "商品"

    products ||..o{ orders : "注文"
    products ||..o{ reviews : "レビュー"
    products ||--o| categories : "カテゴリー"
    products ||..o{ brands : "ブランド"
    products ||--o{ product_images : "商品画像"

    reviews ||--o{ review_images : "レビュー画像"

    cart_items ||--o| products : "商品"

    orders ||..o{ order_items : "注文商品"
    orders ||--o| shipping_addresses : "配送先"

    order_items ||--o| products : "商品"

    sellers ||..o{ products : "商品"
```
