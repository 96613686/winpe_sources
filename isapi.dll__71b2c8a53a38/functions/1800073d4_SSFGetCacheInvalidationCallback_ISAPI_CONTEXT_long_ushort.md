# SSFGetCacheInvalidationCallback(ISAPI_CONTEXT *,long (**)(ushort *))

- ea: `0x1800073d4`
- end: `0x180007503`
- name: `?SSFGetCacheInvalidationCallback@@YAJPEAVISAPI_CONTEXT@@PEAP6AJPEAG@Z@Z`
- size: `303`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, int (**)(unsigned __int16 *))`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x1800073d4`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000742c`
- `iisutil!PuDbgPrint` at `0x18000747d`
- `iisutil!PuDbgPrint` at `0x1800074f0`
- `iisutil!PuDbgPrint` at `0x18000742c`
- `iisutil!PuDbgPrint` at `0x18000747d`
- `iisutil!PuDbgPrint` at `0x1800074f0`

## string_xrefs

- `0x180007425`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007476`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800074d2`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007405`: `\n  HSE_REQ_GET_CACHE_INVALIDATION_CALLBACK[%p]: Function Entry\n  <END>\n\n`
- `0x180007413`: `SSFGetCacheInvalidationCallback`
- `0x180007464`: `SSFGetCacheInvalidationCallback`
- `0x1800074c7`: `SSFGetCacheInvalidationCallback`
- `0x180007458`: `\n  HSE_REQ_GET_CACHE_INVALIDATION_CALLBACK[%p]: Parameter validation failure\n    Callback Ptr: NULL\n  <END>\n\n`
- `0x1800074d9`: `\n  HSE_REQ_GET_CACHE_INVALIDATION_CALLBACK[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFGetCacheInvalidationCallback(struct ISAPI_CONTEXT *a1, int (**a2)(unsigned __int16 *))
{
  int v2; // r9d
  int v6; // eax
  unsigned int v7; // edi

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4356,
      "SSFGetCacheInvalidationCallback",
      "\r\n  HSE_REQ_GET_CACHE_INVALIDATION_CALLBACK[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, int (**)(unsigned __int16 *)))(**((_QWORD **)a1 + 24) + 192LL))(
           *((_QWORD *)a1 + 24),
           a2);
    v7 = v6;
    if ( v6 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4389,
        "SSFGetCacheInvalidationCallback",
        "\r\n  HSE_REQ_GET_CACHE_INVALIDATION_CALLBACK[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        v6);
    return v7;
  }
  else
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4371,
        "SSFGetCacheInvalidationCallback",
        "\r\n"
        "  HSE_REQ_GET_CACHE_INVALIDATION_CALLBACK[%p]: Parameter validation failure\r\n"
        "    Callback Ptr: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800073d4  mov     [rsp+arg_0], rbx
0x1800073d9  push    rdi
0x1800073da  sub     rsp, 40h
0x1800073de  mov     r9d, cs:g_dwDebugFlags
0x1800073e5  mov     rdi, rdx
0x1800073e8  test    r9b, 3
0x1800073ec  mov     rbx, rcx
0x1800073ef  setnz   r8b
0x1800073f3  bt      r9d, 1Ah
0x1800073f8  setb    al
0x1800073fb  test    al, r8b
0x1800073fe  jz      short loc_180007439
0x180007400  mov     [rsp+48h+var_20], rcx
0x180007405  lea     rax, aHseReqGetCache; "\r\n  HSE_REQ_GET_CACHE_INVALIDATION_CA"...
0x18000740c  mov     rcx, cs:g_pDebug
0x180007413  lea     r9, aSsfgetcacheinv; "SSFGetCacheInvalidationCallback"
0x18000741a  mov     r8d, 1104h
0x180007420  mov     [rsp+48h+var_28], rax
0x180007425  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000742c  call    cs:__imp_PuDbgPrint
0x180007432  mov     r9d, cs:g_dwDebugFlags
0x180007439  test    rdi, rdi
0x18000743c  jnz     short loc_18000748A
0x18000743e  test    r9b, 3
0x180007442  setnz   cl
0x180007445  bt      r9d, 14h
0x18000744a  setb    al
0x18000744d  test    al, cl
0x18000744f  jz      short loc_180007483
0x180007451  mov     rcx, cs:g_pDebug
0x180007458  lea     rax, aHseReqGetCache_1; "\r\n  HSE_REQ_GET_CACHE_INVALIDATION_CA"...
0x18000745f  mov     [rsp+48h+var_20], rbx
0x180007464  lea     r9, aSsfgetcacheinv; "SSFGetCacheInvalidationCallback"
0x18000746b  mov     r8d, 1113h
0x180007471  mov     [rsp+48h+var_28], rax
0x180007476  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000747d  call    cs:__imp_PuDbgPrint
0x180007483  mov     eax, 80070057h
0x180007488  jmp     short loc_1800074F8
0x18000748a  mov     rcx, [rbx+0C0h]
0x180007491  mov     rdx, rdi
0x180007494  mov     rax, [rcx]
0x180007497  mov     rax, [rax+0C0h]
0x18000749e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074a3  mov     edi, eax
0x1800074a5  test    eax, eax
0x1800074a7  jns     short loc_1800074F6
0x1800074a9  mov     ecx, cs:g_dwDebugFlags
0x1800074af  test    cl, 3
0x1800074b2  setnz   dl
0x1800074b5  bt      ecx, 14h
0x1800074b9  setb    cl
0x1800074bc  test    cl, dl
0x1800074be  jz      short loc_1800074F6
0x1800074c0  mov     rcx, cs:g_pDebug
0x1800074c7  lea     r9, aSsfgetcacheinv; "SSFGetCacheInvalidationCallback"
0x1800074ce  mov     [rsp+48h+var_18], eax
0x1800074d2  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800074d9  lea     rax, aHseReqGetCache_2; "\r\n  HSE_REQ_GET_CACHE_INVALIDATION_CA"...
0x1800074e0  mov     [rsp+48h+var_20], rbx
0x1800074e5  mov     r8d, 1125h
0x1800074eb  mov     [rsp+48h+var_28], rax
0x1800074f0  call    cs:__imp_PuDbgPrint
0x1800074f6  mov     eax, edi
0x1800074f8  mov     rbx, [rsp+48h+arg_0]
0x1800074fd  add     rsp, 40h
0x180007501  pop     rdi
0x180007502  retn
```
