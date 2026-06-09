# SSFGetWorkerProcessSettings(ISAPI_CONTEXT *,IWpfSettings * *)

- ea: `0x1800084a4`
- end: `0x18000857e`
- name: `?SSFGetWorkerProcessSettings@@YAJPEAVISAPI_CONTEXT@@PEAPEAVIWpfSettings@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct IWpfSettings **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x1800084a4`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800084fc`
- `iisutil!PuDbgPrint` at `0x18000854d`
- `iisutil!PuDbgPrint` at `0x1800084fc`
- `iisutil!PuDbgPrint` at `0x18000854d`

## string_xrefs

- `0x1800084f5`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008546`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFGetWorkerProcessSettings(struct ISAPI_CONTEXT *a1, struct IWpfSettings **a2)
{
  int v2; // r9d

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4922,
      "SSFGetWorkerProcessSettings",
      "\r\n  HSE_REQ_GET_WORKER_PROCESS_SETTINGS[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
    return (*(__int64 (__fastcall **)(struct IHttpServer *, struct IWpfSettings **))(*(_QWORD *)g_pGlobalInfo + 160LL))(
             g_pGlobalInfo,
             a2);
  if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4934,
      "SSFGetWorkerProcessSettings",
      "\r\n"
      "  HSE_REQ_GET_WORKER_PROCESS_SETTINGS[%p]: Failed\r\n"
      "    NULL parameter passed to the call\r\n"
      "  <END>\r\n"
      "\r\n",
      a1);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800084a4  mov     [rsp+arg_0], rbx
0x1800084a9  push    rdi
0x1800084aa  sub     rsp, 30h
0x1800084ae  mov     r9d, cs:g_dwDebugFlags
0x1800084b5  mov     rbx, rdx
0x1800084b8  test    r9b, 3
0x1800084bc  mov     rdi, rcx
0x1800084bf  setnz   r8b
0x1800084c3  bt      r9d, 1Ah
0x1800084c8  setb    al
0x1800084cb  test    al, r8b
0x1800084ce  jz      short loc_180008509
0x1800084d0  mov     [rsp+38h+var_10], rcx
0x1800084d5  lea     rax, aHseReqGetWorke_1; "\r\n  HSE_REQ_GET_WORKER_PROCESS_SETTIN"...
0x1800084dc  mov     rcx, cs:g_pDebug
0x1800084e3  lea     r9, aSsfgetworkerpr; "SSFGetWorkerProcessSettings"
0x1800084ea  mov     r8d, 133Ah
0x1800084f0  mov     [rsp+38h+var_18], rax
0x1800084f5  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800084fc  call    cs:__imp_PuDbgPrint
0x180008502  mov     r9d, cs:g_dwDebugFlags
0x180008509  test    rbx, rbx
0x18000850c  jnz     short loc_18000855A
0x18000850e  test    r9b, 3
0x180008512  setnz   cl
0x180008515  bt      r9d, 14h
0x18000851a  setb    al
0x18000851d  test    al, cl
0x18000851f  jz      short loc_180008553
0x180008521  mov     rcx, cs:g_pDebug
0x180008528  lea     rax, aHseReqGetWorke_0; "\r\n  HSE_REQ_GET_WORKER_PROCESS_SETTIN"...
0x18000852f  mov     [rsp+38h+var_10], rdi
0x180008534  lea     r9, aSsfgetworkerpr; "SSFGetWorkerProcessSettings"
0x18000853b  mov     r8d, 1346h
0x180008541  mov     [rsp+38h+var_18], rax
0x180008546  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000854d  call    cs:__imp_PuDbgPrint
0x180008553  mov     eax, 80070057h
0x180008558  jmp     short loc_180008573
0x18000855a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180008561  mov     rdx, rbx
0x180008564  mov     rax, [rcx]
0x180008567  mov     rax, [rax+0A0h]
0x18000856e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008573  mov     rbx, [rsp+38h+arg_0]
0x180008578  add     rsp, 30h
0x18000857c  pop     rdi
0x18000857d  retn
```
