# SSFGetConfigObject(ISAPI_CONTEXT *,IAppHostAdminManager * *)

- ea: `0x180007714`
- end: `0x1800077ed`
- name: `?SSFGetConfigObject@@YAJPEAVISAPI_CONTEXT@@PEAPEAUIAppHostAdminManager@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct IAppHostAdminManager **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180007714`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000776c`
- `iisutil!PuDbgPrint` at `0x1800077bd`
- `iisutil!PuDbgPrint` at `0x18000776c`
- `iisutil!PuDbgPrint` at `0x1800077bd`

## string_xrefs

- `0x180007765`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800077b6`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007745`: `\n  HSE_REQ_GET_CONFIG_OBJECT[%p]: Function Entry\n  <END>\n\n`
- `0x180007753`: `SSFGetConfigObject`
- `0x1800077a4`: `SSFGetConfigObject`
- `0x180007798`: `\n  HSE_REQ_GET_CONFIG_OBJECT[%p]: Failed\n    NULL parameter passed to the call\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFGetConfigObject(struct ISAPI_CONTEXT *a1, struct IAppHostAdminManager **a2)
{
  int v2; // r9d

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4862,
      "SSFGetConfigObject",
      "\r\n  HSE_REQ_GET_CONFIG_OBJECT[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    *a2 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo
                                                                                         + 56LL))(g_pGlobalInfo);
    return 0;
  }
  else
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4874,
        "SSFGetConfigObject",
        "\r\n  HSE_REQ_GET_CONFIG_OBJECT[%p]: Failed\r\n    NULL parameter passed to the call\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180007714  mov     [rsp+arg_0], rbx
0x180007719  push    rdi
0x18000771a  sub     rsp, 30h
0x18000771e  mov     r9d, cs:g_dwDebugFlags
0x180007725  mov     rbx, rdx
0x180007728  test    r9b, 3
0x18000772c  mov     rdi, rcx
0x18000772f  setnz   r8b
0x180007733  bt      r9d, 1Ah
0x180007738  setb    al
0x18000773b  test    al, r8b
0x18000773e  jz      short loc_180007779
0x180007740  mov     [rsp+38h+var_10], rcx
0x180007745  lea     rax, aHseReqGetConfi_0; "\r\n  HSE_REQ_GET_CONFIG_OBJECT[%p]: Fu"...
0x18000774c  mov     rcx, cs:g_pDebug
0x180007753  lea     r9, aSsfgetconfigob; "SSFGetConfigObject"
0x18000775a  mov     r8d, 12FEh
0x180007760  mov     [rsp+38h+var_18], rax
0x180007765  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000776c  call    cs:__imp_PuDbgPrint
0x180007772  mov     r9d, cs:g_dwDebugFlags
0x180007779  test    rbx, rbx
0x18000777c  jnz     short loc_1800077CA
0x18000777e  test    r9b, 3
0x180007782  setnz   cl
0x180007785  bt      r9d, 14h
0x18000778a  setb    al
0x18000778d  test    al, cl
0x18000778f  jz      short loc_1800077C3
0x180007791  mov     rcx, cs:g_pDebug
0x180007798  lea     rax, aHseReqGetConfi_1; "\r\n  HSE_REQ_GET_CONFIG_OBJECT[%p]: Fa"...
0x18000779f  mov     [rsp+38h+var_10], rdi
0x1800077a4  lea     r9, aSsfgetconfigob; "SSFGetConfigObject"
0x1800077ab  mov     r8d, 130Ah
0x1800077b1  mov     [rsp+38h+var_18], rax
0x1800077b6  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800077bd  call    cs:__imp_PuDbgPrint
0x1800077c3  mov     eax, 80070057h
0x1800077c8  jmp     short loc_1800077E2
0x1800077ca  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800077d1  mov     rax, [rcx]
0x1800077d4  mov     rax, [rax+38h]
0x1800077d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077dd  mov     [rbx], rax
0x1800077e0  xor     eax, eax
0x1800077e2  mov     rbx, [rsp+38h+arg_0]
0x1800077e7  add     rsp, 30h
0x1800077eb  pop     rdi
0x1800077ec  retn
```
