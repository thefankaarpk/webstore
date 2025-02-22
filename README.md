import Image from "next/image"
import Link from "next/link"
import { Button } from "@/components/ui/button"
import { ShoppingBag } from "lucide-react"

const products = [
  {
    id: 1,
    name: "Fankaar Green Hoodie",
    price: 49.99,
    image:
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/fankaar-hoodies-trendy-unisex-fleece-sweatshirt-stylish-adidas-graphic-design-fashionable-hooded-jumper-comfortable-pullover-cool.jpg-70d33rbU9IzubNNo1zIFIBjbCA1lmq.jpeg",
    category: "Hoodies",
  },
  {
    id: 2,
    name: "Fankaar Blue Hoodie",
    price: 49.99,
    image:
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/fankaar-hoodies-trendy-unisex-fleece-sweatshirt-stylish-adidas-graphic-design-fashionable-hooded-jumper-comfortable-pullover-cool%20(2).jpg-Zwy4WpFvZOZLcsQs4i6UUNSbeZ6Q5z.jpeg",
    category: "Hoodies",
  },
  {
    id: 3,
    name: "Tokyo Japan T-Shirt",
    price: 29.99,
    image:
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/1951501f648.jpg-xcjBRXUYWUGLbzJjQihnjOF2FsUfdN.jpeg",
    category: "T-Shirts",
  },
]

export default function Home() {
  return (
    <div className="min-h-screen bg-gray-50">
      {/* Hero Section */}
      <div className="relative h-[60vh] bg-black">
        <Image
          src="https://hebbkx1anhila5yf.public.blob.vercel-storage.com/1951501f648.jpg-xcjBRXUYWUGLbzJjQihnjOF2FsUfdN.jpeg"
          alt="Hero"
          fill
          className="object-cover opacity-80"
        />
        <div className="absolute inset-0 flex items-center justify-center">
          <div className="text-center text-white">
            <h1 className="text-4xl md:text-6xl font-bold mb-4">TheFankaarPK</h1>
            <p className="text-xl md:text-2xl mb-8">Custom Apparel for the Creative Soul</p>
            <Button size="lg" asChild>
              <Link href="#products">Shop Now</Link>
            </Button>
          </div>
        </div>
      </div>

      {/* Products Section */}
      <section id="products" className="container mx-auto py-16 px-4">
        <h2 className="text-3xl font-bold mb-8">Featured Products</h2>
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          {products.map((product) => (
            <Link key={product.id} href={`/products/${product.id}`} className="group">
              <div className="bg-white rounded-lg shadow-lg overflow-hidden transition-transform duration-300 group-hover:-translate-y-1">
                <div className="relative aspect-square">
                  <Image src={product.image || "/placeholder.svg"} alt={product.name} fill className="object-cover" />
                </div>
                <div className="p-4">
                  <h3 className="text-lg font-semibold mb-2">{product.name}</h3>
                  <div className="flex items-center justify-between">
                    <p className="text-lg font-bold">${product.price}</p>
                    <Button size="sm" variant="secondary">
                      <ShoppingBag className="h-4 w-4 mr-2" />
                      View Details
                    </Button>
                  </div>
                </div>
              </div>
            </Link>
          ))}
        </div>
      </section>
    </div>
  )
}

import Image from "next/image"
import { Button } from "@/components/ui/button"
import { ShoppingCart } from "lucide-react"

const products = [
  {
    id: 1,
    name: "Fankaar Green Hoodie",
    price: 49.99,
    images: [
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/fankaar-hoodies-trendy-unisex-fleece-sweatshirt-stylish-adidas-graphic-design-fashionable-hooded-jumper-comfortable-pullover-cool.jpg-70d33rbU9IzubNNo1zIFIBjbCA1lmq.jpeg",
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/fankaar-hoodies-trendy-unisex-fleece-sweatshirt-stylish-adidas-graphic-design-fashionable-hooded-jumper-comfortable-pullover-cool%20(1).jpg-JUCg63ilecEM0BSd3D3hUERkpSS3aw.jpeg",
    ],
    description: "Premium quality hoodie with Fankaar branding. Features a motivational quote on the back.",
    sizes: ["S", "M", "L", "XL"],
  },
  {
    id: 2,
    name: "Fankaar Blue Hoodie",
    price: 49.99,
    images: [
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/fankaar-hoodies-trendy-unisex-fleece-sweatshirt-stylish-adidas-graphic-design-fashionable-hooded-jumper-comfortable-pullover-cool%20(2).jpg-Zwy4WpFvZOZLcsQs4i6UUNSbeZ6Q5z.jpeg",
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/fankaar-hoodies-trendy-unisex-fleece-sweatshirt-stylish-adidas-graphic-design-fashionable-hooded-jumper-comfortable-pullover-cool%20(3).jpg-eStnqLgxUAQlwLYYftMnlsDFXtk9Av.jpeg",
    ],
    description: "Comfortable blue hoodie with Fankaar branding. Features a unique design on the back.",
    sizes: ["S", "M", "L", "XL"],
  },
  {
    id: 3,
    name: "Tokyo Japan T-Shirt",
    price: 29.99,
    images: [
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/1951501f648.jpg-xcjBRXUYWUGLbzJjQihnjOF2FsUfdN.jpeg",
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/1951501f648%20(1).jpg-FBR3GksvCd4oRnVeRZ8JEcc8NtUUKJ.jpeg",
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/1951501f648%20(2).jpg-UMGkvVzWWNwm05xcDcVLWH1U8sIUn6.jpeg",
      "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/1951501f648%20(3).jpg-tbx6hFDHtnK5Iczdf2mjfLbBDAzEXy.jpeg",
    ],
    description: "Stylish black t-shirt featuring a Japanese-inspired design with Mount Fuji and cherry blossoms.",
    sizes: ["S", "M", "L", "XL"],
  },
]

export default function ProductPage({ params }: { params: { id: string } }) {
  const product = products.find((p) => p.id === Number.parseInt(params.id))

  if (!product) {
    return <div>Product not found</div>
  }

  return (
    <div className="container mx-auto py-8 px-4">
      <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
        {/* Product Images */}
        <div className="grid grid-cols-2 gap-4">
          {product.images.map((image, index) => (
            <div key={index} className="relative aspect-square">
              <Image
                src={image || "/placeholder.svg"}
                alt={`${product.name} view ${index + 1}`}
                fill
                className="object-cover rounded-lg"
              />
            </div>
          ))}
        </div>

        {/* Product Details */}
        <div className="space-y-6">
          <h1 className="text-3xl font-bold">{product.name}</h1>
          <p className="text-2xl font-bold">${product.price}</p>
          <p className="text-gray-600">{product.description}</p>

          {/* Size Selection */}
          <div>
            <h3 className="text-lg font-semibold mb-2">Select Size</h3>
            <div className="flex gap-2">
              {product.sizes.map((size) => (
                <Button key={size} variant="outline" className="w-12 h-12">
                  {size}
                </Button>
              ))}
            </div>
          </div>

          {/* Add to Cart Button */}
          <Button size="lg" className="w-full">
            <ShoppingCart className="mr-2 h-5 w-5" />
            Add to Cart
          </Button>
        </div>
      </div>
    </div>
  )
}

import type React from "react"
import "./globals.css"
import { Inter } from "next/font/google"
import Header from "@/components/header"
import Footer from "@/components/footer"

const inter = Inter({ subsets: ["latin"] })

export const metadata = {
  title: "TheFankaarPK - Custom Apparel Store",
  description: "Shop custom hoodies, t-shirts and more at TheFankaarPK",
}

export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <body className={inter.className}>
        <Header />
        <main>{children}</main>
        <Footer />
      </body>
    </html>
  )
}

import Link from "next/link"
import { ShoppingCart } from "lucide-react"
import { Button } from "@/components/ui/button"

export default function Header() {
  return (
    <header className="border-b">
      <div className="container mx-auto px-4 py-4 flex items-center justify-between">
        <Link href="/" className="text-2xl font-bold">
          TheFankaarPK
        </Link>
        <nav>
          <ul className="flex items-center space-x-6">
            <li>
              <Link href="/" className="hover:text-gray-600">
                Home
              </Link>
            </li>
            <li>
              <Link href="/#products" className="hover:text-gray-600">
                Products
              </Link>
            </li>
            <li>
              <Button variant="outline" size="icon">
                <ShoppingCart className="h-5 w-5" />
              </Button>
            </li>
          </ul>
        </nav>
      </div>
    </header>
  )
}

export default function Footer() {
  return (
    <footer className="bg-gray-900 text-white">
      <div className="container mx-auto px-4 py-8">
        <div className="text-center">
          <h2 className="text-2xl font-bold mb-4">TheFankaarPK</h2>
          <p className="mb-4">Custom Apparel for the Creative Soul</p>
          <p className="text-gray-400">© 2024 TheFankaarPK. All rights reserved.</p>
        </div>
      </div>
    </footer>
  )
}

