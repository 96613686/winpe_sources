# W3_CGI_HANDLER::CGITerminateProcess(void *,uchar)

- ea: `0x180003140`
- end: `0x180003253`
- name: `?CGITerminateProcess@W3_CGI_HANDLER@@CAXPEAXE@Z`
- size: `275`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b20`

## callees

- `0x180003140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000316f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000316f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003217`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000315c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000315c`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x1800031b7`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x180003204`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x1800031b7`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x180003204`
- `iisutil!PuDbgPrint` at `0x1800031a0`
- `iisutil!PuDbgPrint` at `0x1800031f4`
- `iisutil!PuDbgPrint` at `0x180003241`
- `iisutil!PuDbgPrint` at `0x1800031a0`
- `iisutil!PuDbgPrint` at `0x1800031f4`
- `iisutil!PuDbgPrint` at `0x180003241`

## string_xrefs

- `0x180003187`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x1800031e2`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x18000322f`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`

## pseudocode

```c
void __fastcall W3_CGI_HANDLER::CGITerminateProcess(_QWORD *a1)
{
  void *v2; // rcx
  DWORD LastError; // eax
  void *v4; // rcx
  DWORD v5; // eax
  void *v6; // rcx
  DWORD v7; // eax

  v2 = (void *)a1[5];
  if ( v2 && !TerminateProcess(v2, 0xF1256323) && (g_dwDebugFlags & 3) != 0 )
  {
    LastError = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
      912,
      "W3_CGI_HANDLER::CGITerminateProcess",
      "CGITerminateProcess - TerminateProcess failed, error %d\n",
      LastError);
  }
  v4 = (void *)a1[4];
  if ( v4 != (void *)-1LL && !DisconnectNamedPipe(v4) && (g_dwDebugFlags & 3) != 0 )
  {
    v5 = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
      920,
      "W3_CGI_HANDLER::CGITerminateProcess",
      "CGITerminateProcess - DisconnectNamedPipe failed, error %d\n",
      v5);
  }
  v6 = (void *)a1[3];
  if ( v6 != (void *)-1LL && !DisconnectNamedPipe(v6) && (g_dwDebugFlags & 3) != 0 )
  {
    v7 = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
      928,
      "W3_CGI_HANDLER::CGITerminateProcess",
      "CGITerminateProcess - DisconnectNamedPipe failed, error %d\n",
      v7);
  }
}

```

## disassembly

```asm
0x180003140  mov     [rsp+arg_0], rbx
0x180003145  push    r14
0x180003147  sub     rsp, 30h
0x18000314b  mov     rbx, rcx
0x18000314e  mov     rcx, [rcx+28h]; hProcess
0x180003152  test    rcx, rcx
0x180003155  jz      short loc_1800031A6
0x180003157  mov     edx, 0F1256323h; uExitCode
0x18000315c  call    cs:__imp_TerminateProcess
0x180003162  test    eax, eax
0x180003164  jnz     short loc_1800031A6
0x180003166  test    cs:g_dwDebugFlags, 3
0x18000316d  jz      short loc_1800031A6
0x18000316f  call    cs:__imp_GetLastError
0x180003175  mov     rcx, cs:g_pDebug
0x18000317c  lea     r9, aW3CgiHandlerCg_1; "W3_CGI_HANDLER::CGITerminateProcess"
0x180003183  mov     [rsp+38h+var_10], eax
0x180003187  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000318e  lea     rax, aCgiterminatepr_0; "CGITerminateProcess - TerminateProcess "...
0x180003195  mov     r8d, 390h
0x18000319b  mov     [rsp+38h+var_18], rax
0x1800031a0  call    cs:__imp_PuDbgPrint
0x1800031a6  mov     rcx, [rbx+20h]; hNamedPipe
0x1800031aa  lea     r14, aCgiterminatepr; "CGITerminateProcess - DisconnectNamedPi"...
0x1800031b1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800031b5  jz      short loc_1800031FA
0x1800031b7  call    cs:__imp_DisconnectNamedPipe
0x1800031bd  test    eax, eax
0x1800031bf  jnz     short loc_1800031FA
0x1800031c1  test    cs:g_dwDebugFlags, 3
0x1800031c8  jz      short loc_1800031FA
0x1800031ca  call    cs:__imp_GetLastError
0x1800031d0  mov     rcx, cs:g_pDebug
0x1800031d7  lea     r9, aW3CgiHandlerCg_1; "W3_CGI_HANDLER::CGITerminateProcess"
0x1800031de  mov     [rsp+38h+var_10], eax
0x1800031e2  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800031e9  mov     r8d, 398h
0x1800031ef  mov     [rsp+38h+var_18], r14
0x1800031f4  call    cs:__imp_PuDbgPrint
0x1800031fa  mov     rcx, [rbx+18h]; hNamedPipe
0x1800031fe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003202  jz      short loc_180003247
0x180003204  call    cs:__imp_DisconnectNamedPipe
0x18000320a  test    eax, eax
0x18000320c  jnz     short loc_180003247
0x18000320e  test    cs:g_dwDebugFlags, 3
0x180003215  jz      short loc_180003247
0x180003217  call    cs:__imp_GetLastError
0x18000321d  mov     rcx, cs:g_pDebug
0x180003224  lea     r9, aW3CgiHandlerCg_1; "W3_CGI_HANDLER::CGITerminateProcess"
0x18000322b  mov     [rsp+38h+var_10], eax
0x18000322f  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003236  mov     r8d, 3A0h
0x18000323c  mov     [rsp+38h+var_18], r14
0x180003241  call    cs:__imp_PuDbgPrint
0x180003247  mov     rbx, [rsp+38h+arg_0]
0x18000324c  add     rsp, 30h
0x180003250  pop     r14
0x180003252  retn
```
