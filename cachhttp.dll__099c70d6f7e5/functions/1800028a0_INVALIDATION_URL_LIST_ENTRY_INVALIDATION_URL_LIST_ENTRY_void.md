# INVALIDATION_URL_LIST_ENTRY::~INVALIDATION_URL_LIST_ENTRY(void)

- ea: `0x1800028a0`
- end: `0x180002937`
- name: `??1INVALIDATION_URL_LIST_ENTRY@@QEAA@XZ`
- size: `151`
- prototype: `void __fastcall(INVALIDATION_URL_LIST_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800011b8`
- `0x180002670`

## callees

- `0x1800028a0`
- `0x180009010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800028f3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800028ce`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800028fd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800028ce`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800028fd`
- `iisutil!PuDbgPrint` at `0x18000292f`
- `iisutil!PuDbgPrint` at `0x18000292f`

## string_xrefs

- `0x180002916`: `servercommon\inetsrv\iis\iisrearc\iis70\ul_cache\ul_cache.h`

## pseudocode

```c
void __fastcall INVALIDATION_URL_LIST_ENTRY::~INVALIDATION_URL_LIST_ENTRY(INVALIDATION_URL_LIST_ENTRY *this)
{
  bool v1; // zf
  STRU *v2; // rdi
  void (__fastcall *v3)(struct IHttpServer *, unsigned __int16 *); // rbx
  unsigned __int16 *v4; // rax
  unsigned __int16 *Str; // rax

  v1 = (g_dwDebugFlags & 3) == 0;
  v2 = (INVALIDATION_URL_LIST_ENTRY *)((char *)this + 24);
  *(_DWORD *)this = 1701606761;
  if ( !v1 )
  {
    Str = STRU::QueryStr((INVALIDATION_URL_LIST_ENTRY *)((char *)this + 24));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\ul_cache\\ul_cache.h",
      248,
      "INVALIDATION_URL_LIST_ENTRY::~INVALIDATION_URL_LIST_ENTRY",
      "Invalidating URL %ws\n",
      Str);
  }
  v3 = *(void (__fastcall **)(struct IHttpServer *, unsigned __int16 *))(*(_QWORD *)g_pGlobalInfo + 72LL);
  v4 = STRU::QueryStr(v2);
  v3(g_pGlobalInfo, v4);
  STRU::~STRU(v2);
}

```

## disassembly

```asm
0x1800028a0  mov     [rsp+arg_0], rbx
0x1800028a5  push    rdi
0x1800028a6  sub     rsp, 30h
0x1800028aa  test    cs:g_dwDebugFlags, 3
0x1800028b1  lea     rdi, [rcx+18h]
0x1800028b5  mov     dword ptr [rcx], 656C7569h
0x1800028bb  jnz     short loc_1800028FA
0x1800028bd  mov     rax, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800028c4  mov     rcx, rdi
0x1800028c7  mov     rdx, [rax]
0x1800028ca  mov     rbx, [rdx+48h]
0x1800028ce  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800028d4  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800028db  mov     rdx, rax
0x1800028de  mov     rax, rbx
0x1800028e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e6  mov     rcx, rdi
0x1800028e9  mov     rbx, [rsp+38h+arg_0]
0x1800028ee  add     rsp, 30h
0x1800028f2  pop     rdi
0x1800028f3  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800028fa  mov     rcx, rdi
0x1800028fd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002903  mov     rcx, cs:g_pDebug
0x18000290a  lea     r9, aInvalidationUr; "INVALIDATION_URL_LIST_ENTRY::~INVALIDAT"...
0x180002911  mov     [rsp+38h+var_10], rax
0x180002916  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000291d  lea     rax, aInvalidatingUr; "Invalidating URL %ws\n"
0x180002924  mov     r8d, 0F8h
0x18000292a  mov     [rsp+38h+var_18], rax
0x18000292f  call    cs:__imp_PuDbgPrint
0x180002935  jmp     short loc_1800028BD
```
