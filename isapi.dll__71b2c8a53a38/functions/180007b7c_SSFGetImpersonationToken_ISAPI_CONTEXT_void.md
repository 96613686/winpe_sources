# SSFGetImpersonationToken(ISAPI_CONTEXT *,void * *)

- ea: `0x180007b7c`
- end: `0x180007c4a`
- name: `?SSFGetImpersonationToken@@YAJPEAVISAPI_CONTEXT@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180005f08`
- `0x180007b7c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007bd4`
- `iisutil!PuDbgPrint` at `0x180007c25`
- `iisutil!PuDbgPrint` at `0x180007bd4`
- `iisutil!PuDbgPrint` at `0x180007c25`

## string_xrefs

- `0x180007bcd`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007c1e`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007bad`: `\n  HSE_REQ_GET_IMPERSONATION_TOKEN[%p]: Function Entry\n  <END>\n\n`
- `0x180007bbb`: `SSFGetImpersonationToken`
- `0x180007c0c`: `SSFGetImpersonationToken`
- `0x180007c00`: `\n  HSE_REQ_GET_IMPERSONATION_TOKEN[%p]: Parameter validation failure\n    Token Ptr: NULL\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFGetImpersonationToken(struct ISAPI_CONTEXT *this, void **a2)
{
  int v2; // r9d

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      806,
      "SSFGetImpersonationToken",
      "\r\n  HSE_REQ_GET_IMPERSONATION_TOKEN[%p]: Function Entry\r\n  <END>\r\n\r\n",
      this);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    *a2 = ISAPI_CONTEXT::QueryToken(this);
    return 0;
  }
  else
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        822,
        "SSFGetImpersonationToken",
        "\r\n"
        "  HSE_REQ_GET_IMPERSONATION_TOKEN[%p]: Parameter validation failure\r\n"
        "    Token Ptr: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180007b7c  mov     [rsp+arg_0], rbx
0x180007b81  push    rdi
0x180007b82  sub     rsp, 30h
0x180007b86  mov     r9d, cs:g_dwDebugFlags
0x180007b8d  mov     rdi, rdx
0x180007b90  test    r9b, 3
0x180007b94  mov     rbx, rcx
0x180007b97  setnz   r8b
0x180007b9b  bt      r9d, 1Ah
0x180007ba0  setb    al
0x180007ba3  test    al, r8b
0x180007ba6  jz      short loc_180007BE1
0x180007ba8  mov     [rsp+38h+var_10], rcx
0x180007bad  lea     rax, aHseReqGetImper_1; "\r\n  HSE_REQ_GET_IMPERSONATION_TOKEN[%"...
0x180007bb4  mov     rcx, cs:g_pDebug
0x180007bbb  lea     r9, aSsfgetimperson; "SSFGetImpersonationToken"
0x180007bc2  mov     r8d, 326h
0x180007bc8  mov     [rsp+38h+var_18], rax
0x180007bcd  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007bd4  call    cs:__imp_PuDbgPrint
0x180007bda  mov     r9d, cs:g_dwDebugFlags
0x180007be1  test    rdi, rdi
0x180007be4  jnz     short loc_180007C32
0x180007be6  test    r9b, 3
0x180007bea  setnz   cl
0x180007bed  bt      r9d, 14h
0x180007bf2  setb    al
0x180007bf5  test    al, cl
0x180007bf7  jz      short loc_180007C2B
0x180007bf9  mov     rcx, cs:g_pDebug
0x180007c00  lea     rax, aHseReqGetImper_0; "\r\n  HSE_REQ_GET_IMPERSONATION_TOKEN[%"...
0x180007c07  mov     [rsp+38h+var_10], rbx
0x180007c0c  lea     r9, aSsfgetimperson; "SSFGetImpersonationToken"
0x180007c13  mov     r8d, 336h
0x180007c19  mov     [rsp+38h+var_18], rax
0x180007c1e  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007c25  call    cs:__imp_PuDbgPrint
0x180007c2b  mov     eax, 80070057h
0x180007c30  jmp     short loc_180007C3F
0x180007c32  mov     rcx, rbx; this
0x180007c35  call    ?QueryToken@ISAPI_CONTEXT@@QEAAPEAXXZ; ISAPI_CONTEXT::QueryToken(void)
0x180007c3a  mov     [rdi], rax
0x180007c3d  xor     eax, eax
0x180007c3f  mov     rbx, [rsp+38h+arg_0]
0x180007c44  add     rsp, 30h
0x180007c48  pop     rdi
0x180007c49  retn
```
