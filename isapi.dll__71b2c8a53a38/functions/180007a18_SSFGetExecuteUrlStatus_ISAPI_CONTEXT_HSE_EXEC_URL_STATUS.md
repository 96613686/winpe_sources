# SSFGetExecuteUrlStatus(ISAPI_CONTEXT *,_HSE_EXEC_URL_STATUS *)

- ea: `0x180007a18`
- end: `0x180007b73`
- name: `?SSFGetExecuteUrlStatus@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_EXEC_URL_STATUS@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct _HSE_EXEC_URL_STATUS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180007a18`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007a70`
- `iisutil!PuDbgPrint` at `0x180007aef`
- `iisutil!PuDbgPrint` at `0x180007b60`
- `iisutil!PuDbgPrint` at `0x180007a70`
- `iisutil!PuDbgPrint` at `0x180007aef`
- `iisutil!PuDbgPrint` at `0x180007b60`

## string_xrefs

- `0x180007a69`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007ae3`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007b42`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFGetExecuteUrlStatus(struct ISAPI_CONTEXT *a1, struct _HSE_EXEC_URL_STATUS *a2)
{
  int v2; // r9d
  __int64 v5; // rcx
  int v7; // eax
  unsigned int v8; // edi

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      2528,
      "SSFGetExecuteUrlStatus",
      "\r\n  HSE_REQ_GET_EXEC_URL_STATUS[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  v5 = *((_QWORD *)a1 + 24);
  if ( !v5 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2541,
        "SSFGetExecuteUrlStatus",
        "\r\n  HSE_REQ_GET_EXEC_URL_STATUS[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2556,
        "SSFGetExecuteUrlStatus",
        "\r\n"
        "  HSE_REQ_GET_EXEC_URL_STATUS[%p]: Parameter validation failure\r\n"
        "    EXEC_URL Status Ptr: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, struct _HSE_EXEC_URL_STATUS *, USHORT *, DWORD *))(*(_QWORD *)v5 + 96LL))(
         v5,
         a2,
         &a2->uHttpSubStatus,
         &a2->dwWin32Error);
  v8 = v7;
  if ( v7 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      2578,
      "SSFGetExecuteUrlStatus",
      "\r\n  HSE_REQ_GET_EXEC_URL_STATUS[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v7);
  return v8;
}

```

## disassembly

```asm
0x180007a18  mov     [rsp+arg_0], rbx
0x180007a1d  push    rdi
0x180007a1e  sub     rsp, 40h
0x180007a22  mov     r9d, cs:g_dwDebugFlags
0x180007a29  mov     rdi, rdx
0x180007a2c  test    r9b, 3
0x180007a30  mov     rbx, rcx
0x180007a33  setnz   r8b
0x180007a37  bt      r9d, 1Ah
0x180007a3c  setb    al
0x180007a3f  test    al, r8b
0x180007a42  jz      short loc_180007A7D
0x180007a44  mov     [rsp+48h+var_20], rcx
0x180007a49  lea     rax, aHseReqGetExecU_0; "\r\n  HSE_REQ_GET_EXEC_URL_STATUS[%p]: "...
0x180007a50  mov     rcx, cs:g_pDebug
0x180007a57  lea     r9, aSsfgetexecuteu; "SSFGetExecuteUrlStatus"
0x180007a5e  mov     r8d, 9E0h
0x180007a64  mov     [rsp+48h+var_28], rax
0x180007a69  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007a70  call    cs:__imp_PuDbgPrint
0x180007a76  mov     r9d, cs:g_dwDebugFlags
0x180007a7d  mov     rcx, [rbx+0C0h]
0x180007a84  test    rcx, rcx
0x180007a87  jnz     short loc_180007AAB
0x180007a89  test    r9b, 3
0x180007a8d  setnz   cl
0x180007a90  bt      r9d, 14h
0x180007a95  setb    al
0x180007a98  test    al, cl
0x180007a9a  jz      short loc_180007AF5
0x180007a9c  lea     rax, aHseReqGetExecU_1; "\r\n  HSE_REQ_GET_EXEC_URL_STATUS[%p]: "...
0x180007aa3  mov     r8d, 9EDh
0x180007aa9  jmp     short loc_180007AD0
0x180007aab  test    rdi, rdi
0x180007aae  jnz     short loc_180007AFC
0x180007ab0  test    r9b, 3
0x180007ab4  setnz   cl
0x180007ab7  bt      r9d, 14h
0x180007abc  setb    al
0x180007abf  test    al, cl
0x180007ac1  jz      short loc_180007AF5
0x180007ac3  lea     rax, aHseReqGetExecU; "\r\n  HSE_REQ_GET_EXEC_URL_STATUS[%p]: "...
0x180007aca  mov     r8d, 9FCh
0x180007ad0  mov     rcx, cs:g_pDebug
0x180007ad7  lea     r9, aSsfgetexecuteu; "SSFGetExecuteUrlStatus"
0x180007ade  mov     [rsp+48h+var_20], rbx
0x180007ae3  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007aea  mov     [rsp+48h+var_28], rax
0x180007aef  call    cs:__imp_PuDbgPrint
0x180007af5  mov     eax, 80070057h
0x180007afa  jmp     short loc_180007B68
0x180007afc  mov     rax, [rcx]
0x180007aff  lea     r9, [rdi+4]
0x180007b03  lea     r8, [rdi+2]
0x180007b07  mov     rdx, rdi
0x180007b0a  mov     rax, [rax+60h]
0x180007b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b13  mov     edi, eax
0x180007b15  test    eax, eax
0x180007b17  jns     short loc_180007B66
0x180007b19  mov     ecx, cs:g_dwDebugFlags
0x180007b1f  test    cl, 3
0x180007b22  setnz   dl
0x180007b25  bt      ecx, 14h
0x180007b29  setb    cl
0x180007b2c  test    cl, dl
0x180007b2e  jz      short loc_180007B66
0x180007b30  mov     rcx, cs:g_pDebug
0x180007b37  lea     r9, aSsfgetexecuteu; "SSFGetExecuteUrlStatus"
0x180007b3e  mov     [rsp+48h+var_18], eax
0x180007b42  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007b49  lea     rax, aHseReqGetExecU_2; "\r\n  HSE_REQ_GET_EXEC_URL_STATUS[%p]: "...
0x180007b50  mov     [rsp+48h+var_20], rbx
0x180007b55  mov     r8d, 0A12h
0x180007b5b  mov     [rsp+48h+var_28], rax
0x180007b60  call    cs:__imp_PuDbgPrint
0x180007b66  mov     eax, edi
0x180007b68  mov     rbx, [rsp+48h+arg_0]
0x180007b6d  add     rsp, 40h
0x180007b71  pop     rdi
0x180007b72  retn
```
