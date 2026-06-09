# SSFSendRedirect(ISAPI_CONTEXT *,char *)

- ea: `0x180009b88`
- end: `0x180009d39`
- name: `?SSFSendRedirect@@YAJPEAVISAPI_CONTEXT@@PEAD@Z`
- size: `433`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180009b88`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009be4`
- `iisutil!PuDbgPrint` at `0x180009c40`
- `iisutil!PuDbgPrint` at `0x180009cd5`
- `iisutil!PuDbgPrint` at `0x180009d23`
- `iisutil!PuDbgPrint` at `0x180009be4`
- `iisutil!PuDbgPrint` at `0x180009c40`
- `iisutil!PuDbgPrint` at `0x180009cd5`
- `iisutil!PuDbgPrint` at `0x180009d23`

## string_xrefs

- `0x180009bd3`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009c39`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009cb7`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009d11`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFSendRedirect(struct ISAPI_CONTEXT *a1, char *a2)
{
  int v2; // r9d
  __int64 v5; // rcx
  __int64 result; // rax
  unsigned int v7; // edi

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1669,
      "SSFSendRedirect",
      "\r\n  HSE_REQ_SEND_REDIRECT[%p]: Function Entry\r\n    URL: '%s'\r\n  <END>\r\n\r\n",
      a1,
      a2);
    v2 = g_dwDebugFlags;
  }
  v5 = *((_QWORD *)a1 + 24);
  if ( !v5 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1682,
        "SSFSendRedirect",
        "\r\n  HSE_REQ_SEND_REDIRECT[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1703,
        "SSFSendRedirect",
        "\r\n  HSE_REQ_SEND_REDIRECT[%p]: Parameter validation failure\r\n    szUrl: '%s'\r\n  <END>\r\n\r\n",
        a1,
        0);
    return 2147942487LL;
  }
  if ( *((_DWORD *)a1 + 62) )
    *((_DWORD *)a1 + 63) = 1;
  result = (*(__int64 (__fastcall **)(__int64, char *, bool))(*(_QWORD *)v5 + 64LL))(v5, a2, *((_DWORD *)a1 + 63) == 0);
  v7 = result;
  if ( (int)result < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1729,
        "SSFSendRedirect",
        "\r\n  HSE_REQ_SEND_REDIRECT[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        result);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180009b88  mov     r11, rsp
0x180009b8b  mov     [r11+8], rbx
0x180009b8f  push    rdi
0x180009b90  sub     rsp, 40h
0x180009b94  mov     r9d, cs:g_dwDebugFlags
0x180009b9b  mov     rdi, rdx
0x180009b9e  test    r9b, 3
0x180009ba2  mov     rbx, rcx
0x180009ba5  setnz   r8b
0x180009ba9  bt      r9d, 1Ah
0x180009bae  setb    al
0x180009bb1  test    al, r8b
0x180009bb4  jz      short loc_180009BF1
0x180009bb6  mov     [r11-18h], rdx
0x180009bba  lea     rax, aHseReqSendRedi_2; "\r\n  HSE_REQ_SEND_REDIRECT[%p]: Functi"...
0x180009bc1  mov     [r11-20h], rcx
0x180009bc5  lea     r9, aSsfsendredirec; "SSFSendRedirect"
0x180009bcc  mov     rcx, cs:g_pDebug
0x180009bd3  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009bda  mov     r8d, 685h
0x180009be0  mov     [r11-28h], rax
0x180009be4  call    cs:__imp_PuDbgPrint
0x180009bea  mov     r9d, cs:g_dwDebugFlags
0x180009bf1  mov     rcx, [rbx+0C0h]
0x180009bf8  test    rcx, rcx
0x180009bfb  jnz     short loc_180009C4B
0x180009bfd  test    r9b, 3
0x180009c01  setnz   cl
0x180009c04  bt      r9d, 14h
0x180009c09  setb    al
0x180009c0c  test    al, cl
0x180009c0e  jz      loc_180009D29
0x180009c14  mov     rcx, cs:g_pDebug
0x180009c1b  lea     rax, aHseReqSendRedi_0; "\r\n  HSE_REQ_SEND_REDIRECT[%p]: Failed"...
0x180009c22  mov     [rsp+48h+var_20], rbx
0x180009c27  lea     r9, aSsfsendredirec; "SSFSendRedirect"
0x180009c2e  mov     r8d, 692h
0x180009c34  mov     [rsp+48h+var_28], rax
0x180009c39  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009c40  call    cs:__imp_PuDbgPrint
0x180009c46  jmp     loc_180009D29
0x180009c4b  test    rdi, rdi
0x180009c4e  jz      loc_180009CDF
0x180009c54  cmp     dword ptr [rbx+0F8h], 0
0x180009c5b  jz      short loc_180009C67
0x180009c5d  mov     dword ptr [rbx+0FCh], 1
0x180009c67  mov     rax, [rcx]
0x180009c6a  xor     r8d, r8d
0x180009c6d  cmp     [rbx+0FCh], r8d
0x180009c74  mov     rdx, rdi
0x180009c77  setz    r8b
0x180009c7b  mov     rax, [rax+40h]
0x180009c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c84  mov     edi, eax
0x180009c86  test    eax, eax
0x180009c88  jns     loc_180009D2E
0x180009c8e  mov     ecx, cs:g_dwDebugFlags
0x180009c94  test    cl, 3
0x180009c97  setnz   dl
0x180009c9a  bt      ecx, 14h
0x180009c9e  setb    cl
0x180009ca1  test    cl, dl
0x180009ca3  jz      short loc_180009CDB
0x180009ca5  mov     rcx, cs:g_pDebug
0x180009cac  lea     r9, aSsfsendredirec; "SSFSendRedirect"
0x180009cb3  mov     dword ptr [rsp+48h+var_18], eax
0x180009cb7  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009cbe  lea     rax, aHseReqSendRedi_1; "\r\n  HSE_REQ_SEND_REDIRECT[%p]: Failed"...
0x180009cc5  mov     [rsp+48h+var_20], rbx
0x180009cca  mov     r8d, 6C1h
0x180009cd0  mov     [rsp+48h+var_28], rax
0x180009cd5  call    cs:__imp_PuDbgPrint
0x180009cdb  mov     eax, edi
0x180009cdd  jmp     short loc_180009D2E
0x180009cdf  test    r9b, 3
0x180009ce3  setnz   cl
0x180009ce6  bt      r9d, 14h
0x180009ceb  setb    al
0x180009cee  test    al, cl
0x180009cf0  jz      short loc_180009D29
0x180009cf2  mov     rcx, cs:g_pDebug
0x180009cf9  lea     rax, aHseReqSendRedi; "\r\n  HSE_REQ_SEND_REDIRECT[%p]: Parame"...
0x180009d00  mov     [rsp+48h+var_18], rdi
0x180009d05  lea     r9, aSsfsendredirec; "SSFSendRedirect"
0x180009d0c  mov     [rsp+48h+var_20], rbx
0x180009d11  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009d18  mov     r8d, 6A7h
0x180009d1e  mov     [rsp+48h+var_28], rax
0x180009d23  call    cs:__imp_PuDbgPrint
0x180009d29  mov     eax, 80070057h
0x180009d2e  mov     rbx, [rsp+48h+arg_0]
0x180009d33  add     rsp, 40h
0x180009d37  pop     rdi
0x180009d38  retn
```
