# W3_CGI_HANDLER::Terminate(void)

- ea: `0x1800062a0`
- end: `0x180006308`
- name: `?Terminate@W3_CGI_HANDLER@@SAXXZ`
- size: `104`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800028f0`
- `0x180004344`

## callees

- `0x180001048`
- `0x1800062a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006301`
- `iisutil!PuDbgPrint` at `0x1800062d4`
- `iisutil!PuDbgPrint` at `0x1800062d4`

## string_xrefs

- `0x1800062cd`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`

## pseudocode

```c
void W3_CGI_HANDLER::Terminate(void)
{
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
      2538,
      "W3_CGI_HANDLER::Terminate",
      "W3_CGI_HANDLER::Terminate() called\n");
  if ( W3_CGI_HANDLER::sm_pEnvString )
  {
    operator delete(W3_CGI_HANDLER::sm_pEnvString);
    W3_CGI_HANDLER::sm_pEnvString = 0;
  }
  DeleteCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
}

```

## disassembly

```asm
0x1800062a0  sub     rsp, 38h
0x1800062a4  test    cs:g_dwDebugFlags, 3
0x1800062ab  jz      short loc_1800062DA
0x1800062ad  mov     rcx, cs:g_pDebug
0x1800062b4  lea     rax, aW3CgiHandlerTe_0; "W3_CGI_HANDLER::Terminate() called\n"
0x1800062bb  lea     r9, aW3CgiHandlerTe; "W3_CGI_HANDLER::Terminate"
0x1800062c2  mov     [rsp+38h+var_18], rax
0x1800062c7  mov     r8d, 9EAh
0x1800062cd  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800062d4  call    cs:__imp_PuDbgPrint
0x1800062da  mov     rcx, cs:?sm_pEnvString@W3_CGI_HANDLER@@0PEAGEA; Block
0x1800062e1  test    rcx, rcx
0x1800062e4  jz      short loc_1800062F6
0x1800062e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800062eb  mov     cs:?sm_pEnvString@W3_CGI_HANDLER@@0PEAGEA, 0; ushort * W3_CGI_HANDLER::sm_pEnvString
0x1800062f6  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION W3_CGI_HANDLER::sm_CgiListLock
0x1800062fd  add     rsp, 38h
0x180006301  jmp     cs:__imp_DeleteCriticalSection
```
