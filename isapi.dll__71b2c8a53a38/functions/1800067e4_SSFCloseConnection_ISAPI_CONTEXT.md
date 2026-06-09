# SSFCloseConnection(ISAPI_CONTEXT *)

- ea: `0x1800067e4`
- end: `0x1800068b4`
- name: `?SSFCloseConnection@@YAJPEAVISAPI_CONTEXT@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x1800067e4`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000683a`
- `iisutil!PuDbgPrint` at `0x1800068a1`
- `iisutil!PuDbgPrint` at `0x18000683a`
- `iisutil!PuDbgPrint` at `0x1800068a1`

## string_xrefs

- `0x180006833`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180006883`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFCloseConnection(struct ISAPI_CONTEXT *a1)
{
  __int64 v2; // rbx
  int v3; // eax
  unsigned int v4; // ebx

  v2 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4416,
      "SSFCloseConnection",
      "\r\n  HSE_REQ_CLOSE_CONNECTION[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
  v4 = v3;
  if ( v3 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4431,
      "SSFCloseConnection",
      "\r\n  HSE_REQ_CLOSE_CONNECTION[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v3);
  return v4;
}

```

## disassembly

```asm
0x1800067e4  mov     [rsp+arg_0], rbx
0x1800067e9  push    rdi
0x1800067ea  sub     rsp, 40h
0x1800067ee  mov     eax, cs:g_dwDebugFlags
0x1800067f4  mov     rdi, rcx
0x1800067f7  mov     rbx, [rcx+0C0h]
0x1800067fe  test    al, 3
0x180006800  setnz   dl
0x180006803  bt      eax, 1Ah
0x180006807  setb    al
0x18000680a  test    al, dl
0x18000680c  jz      short loc_180006840
0x18000680e  mov     [rsp+48h+var_20], rcx
0x180006813  lea     rax, aHseReqCloseCon_1; "\r\n  HSE_REQ_CLOSE_CONNECTION[%p]: Fun"...
0x18000681a  mov     rcx, cs:g_pDebug
0x180006821  lea     r9, aSsfcloseconnec; "SSFCloseConnection"
0x180006828  mov     r8d, 1140h
0x18000682e  mov     [rsp+48h+var_28], rax
0x180006833  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000683a  call    cs:__imp_PuDbgPrint
0x180006840  mov     rax, [rbx]
0x180006843  mov     rcx, rbx
0x180006846  mov     rax, [rax+0C8h]
0x18000684d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006852  mov     ebx, eax
0x180006854  test    eax, eax
0x180006856  jns     short loc_1800068A7
0x180006858  mov     ecx, cs:g_dwDebugFlags
0x18000685e  test    cl, 3
0x180006861  setnz   r8b
0x180006865  bt      ecx, 14h
0x180006869  setb    cl
0x18000686c  test    cl, r8b
0x18000686f  jz      short loc_1800068A7
0x180006871  mov     rcx, cs:g_pDebug
0x180006878  lea     r9, aSsfcloseconnec; "SSFCloseConnection"
0x18000687f  mov     [rsp+48h+var_18], eax
0x180006883  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000688a  lea     rax, aHseReqCloseCon_0; "\r\n  HSE_REQ_CLOSE_CONNECTION[%p]: Fai"...
0x180006891  mov     [rsp+48h+var_20], rdi
0x180006896  mov     r8d, 114Fh
0x18000689c  mov     [rsp+48h+var_28], rax
0x1800068a1  call    cs:__imp_PuDbgPrint
0x1800068a7  mov     eax, ebx
0x1800068a9  mov     rbx, [rsp+48h+arg_0]
0x1800068ae  add     rsp, 40h
0x1800068b2  pop     rdi
0x1800068b3  retn
```
