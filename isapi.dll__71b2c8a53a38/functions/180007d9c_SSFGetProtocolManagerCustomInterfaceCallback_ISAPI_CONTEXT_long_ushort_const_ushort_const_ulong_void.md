# SSFGetProtocolManagerCustomInterfaceCallback(ISAPI_CONTEXT *,long (**)(ushort const *,ushort const *,ulong,void * *))

- ea: `0x180007d9c`
- end: `0x180007e69`
- name: `?SSFGetProtocolManagerCustomInterfaceCallback@@YAJPEAVISAPI_CONTEXT@@PEAP6AJPEBG1KPEAPEAX@Z@Z`
- size: `205`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, int (**)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **))`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180007d9c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007df4`
- `iisutil!PuDbgPrint` at `0x180007e45`
- `iisutil!PuDbgPrint` at `0x180007df4`
- `iisutil!PuDbgPrint` at `0x180007e45`

## string_xrefs

- `0x180007ded`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007e3e`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007dcd`: `\n  HSE_REQ_GET_PROTOCOL_MANAGER_CUSTOM_INTERFACE_CALLBACK[%p]: Function Entry\n  <END>\n\n`
- `0x180007ddb`: `SSFGetProtocolManagerCustomInterfaceCallback`
- `0x180007e2c`: `SSFGetProtocolManagerCustomInterfaceCallback`
- `0x180007e20`: `\n  HSE_REQ_GET_PROTOCOL_MANAGER_CUSTOM_INTERFACE_CALLBACK[%p]: Failed\n    NULL parameter passed to the call\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFGetProtocolManagerCustomInterfaceCallback(
        struct ISAPI_CONTEXT *a1,
        int (**a2)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **))
{
  int v2; // r9d

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      5015,
      "SSFGetProtocolManagerCustomInterfaceCallback",
      "\r\n  HSE_REQ_GET_PROTOCOL_MANAGER_CUSTOM_INTERFACE_CALLBACK[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    *a2 = (int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **))HelperGetProtocolManagerCustomInterface;
    return 0;
  }
  else
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        5027,
        "SSFGetProtocolManagerCustomInterfaceCallback",
        "\r\n"
        "  HSE_REQ_GET_PROTOCOL_MANAGER_CUSTOM_INTERFACE_CALLBACK[%p]: Failed\r\n"
        "    NULL parameter passed to the call\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180007d9c  mov     [rsp+arg_0], rbx
0x180007da1  push    rdi
0x180007da2  sub     rsp, 30h
0x180007da6  mov     r9d, cs:g_dwDebugFlags
0x180007dad  mov     rbx, rdx
0x180007db0  test    r9b, 3
0x180007db4  mov     rdi, rcx
0x180007db7  setnz   r8b
0x180007dbb  bt      r9d, 1Ah
0x180007dc0  setb    al
0x180007dc3  test    al, r8b
0x180007dc6  jz      short loc_180007E01
0x180007dc8  mov     [rsp+38h+var_10], rcx
0x180007dcd  lea     rax, aHseReqGetProto_0; "\r\n  HSE_REQ_GET_PROTOCOL_MANAGER_CUST"...
0x180007dd4  mov     rcx, cs:g_pDebug
0x180007ddb  lea     r9, aSsfgetprotocol; "SSFGetProtocolManagerCustomInterfaceCal"...
0x180007de2  mov     r8d, 1397h
0x180007de8  mov     [rsp+38h+var_18], rax
0x180007ded  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007df4  call    cs:__imp_PuDbgPrint
0x180007dfa  mov     r9d, cs:g_dwDebugFlags
0x180007e01  test    rbx, rbx
0x180007e04  jnz     short loc_180007E52
0x180007e06  test    r9b, 3
0x180007e0a  setnz   cl
0x180007e0d  bt      r9d, 14h
0x180007e12  setb    al
0x180007e15  test    al, cl
0x180007e17  jz      short loc_180007E4B
0x180007e19  mov     rcx, cs:g_pDebug
0x180007e20  lea     rax, aHseReqGetProto_1; "\r\n  HSE_REQ_GET_PROTOCOL_MANAGER_CUST"...
0x180007e27  mov     [rsp+38h+var_10], rdi
0x180007e2c  lea     r9, aSsfgetprotocol; "SSFGetProtocolManagerCustomInterfaceCal"...
0x180007e33  mov     r8d, 13A3h
0x180007e39  mov     [rsp+38h+var_18], rax
0x180007e3e  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007e45  call    cs:__imp_PuDbgPrint
0x180007e4b  mov     eax, 80070057h
0x180007e50  jmp     short loc_180007E5E
0x180007e52  lea     rax, ?HelperGetProtocolManagerCustomInterface@@YAJPEBG0KPEAPEAX@Z; HelperGetProtocolManagerCustomInterface(ushort const *,ushort const *,ulong,void * *)
0x180007e59  mov     [rbx], rax
0x180007e5c  xor     eax, eax
0x180007e5e  mov     rbx, [rsp+38h+arg_0]
0x180007e63  add     rsp, 30h
0x180007e67  pop     rdi
0x180007e68  retn
```
