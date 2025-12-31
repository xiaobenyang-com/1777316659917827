# 必应搜索工具 

一个基于MCP协议的中文必应搜索工具，支持通过Claude等AI工具调用，无需API密钥即可获取网页内容。
A Chinese Bing search tool based on MCP protocol, which supports calling through AI tools such as Claude, and can obtain webpage content without API keys.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| bing_search | 使用必应搜索指定的关键词，并返回搜索结果列表，包括标题、链接、摘要和ID |
| fetch_webpage | 根据提供的ID获取对应网页的内容 |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659917827](https://mcp.xiaobenyang.com/inspector/1777316659917827)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659917827](https://mcp.xiaobenyang.com/inspector/1777316659917827)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "必应搜索工具": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659917827/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "必应搜索工具": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659917827/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "必应搜索工具": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659917827",
          },
          "transport": "stdio"
        }
      }
}

```
