# UL_RESPONSE_CACHE_ENTRY::~UL_RESPONSE_CACHE_ENTRY(void)

- ea: `0x180001048`
- end: `0x180001178`
- name: `??1UL_RESPONSE_CACHE_ENTRY@@UEAA@XZ`
- size: `304`
- prototype: `void __fastcall(UL_RESPONSE_CACHE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001048`
- `0x180001180`
- `0x1800011b8`
- `0x180009010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800010f1`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800010f1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800010fa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800010fa`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001090`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000113b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001090`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000113b`
- `iisutil!PuDbgPrint` at `0x18000116d`
- `iisutil!PuDbgPrint` at `0x18000116d`

## string_xrefs

- `0x180001148`: `UL_RESPONSE_CACHE_ENTRY::~UL_RESPONSE_CACHE_ENTRY`
- `0x180001154`: `servercommon\inetsrv\iis\iisrearc\iis70\ul_cache\ul_cache.cxx`

## pseudocode

```c
void __fastcall UL_RESPONSE_CACHE_ENTRY::~UL_RESPONSE_CACHE_ENTRY(UL_RESPONSE_CACHE_ENTRY *this)
{
  bool v1; // zf
  STRU *v2; // rsi
  void (__fastcall *v4)(struct IHttpServer *, unsigned __int16 *); // rbx
  unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  _QWORD **v7; // rbx
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // r8
  unsigned __int16 *Str; // rax

  v1 = (g_dwDebugFlags & 3) == 0;
  *(_QWORD *)this = &UL_RESPONSE_CACHE_ENTRY::`vftable';
  v2 = (UL_RESPONSE_CACHE_ENTRY *)((char *)this + 576);
  *((_DWORD *)this + 2) = 2020764789;
  if ( !v1 )
  {
    Str = STRU::QueryStr((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 576));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\ul_cache\\ul_cache.cxx",
      1458,
      "UL_RESPONSE_CACHE_ENTRY::~UL_RESPONSE_CACHE_ENTRY",
      "Invalidating URL %ws\n",
      Str);
  }
  v4 = *(void (__fastcall **)(struct IHttpServer *, unsigned __int16 *))(*(_QWORD *)g_pGlobalInfo + 72LL);
  v5 = STRU::QueryStr(v2);
  v4(g_pGlobalInfo, v5);
  v6 = *((_QWORD *)this + 99);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    *((_QWORD *)this + 99) = 0;
  }
  v7 = (_QWORD **)((char *)this + 768);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 )
      break;
    v9 = *v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 || (v10 = (_QWORD *)v8[1], (_QWORD *)*v10 != v8) )
      __fastfail(3u);
    *v10 = v9;
    *(_QWORD *)(v9 + 8) = v10;
    if ( v8 != (_QWORD *)8 )
      INVALIDATION_URL_LIST_ENTRY::`scalar deleting destructor'((INVALIDATION_URL_LIST_ENTRY *)(v8 - 1), v9);
  }
  CReaderWriterLock3::~CReaderWriterLock3((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 784));
  STRU::~STRU(v2);
  UL_RESPONSE_CACHE_KEY::~UL_RESPONSE_CACHE_KEY((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 16));
}

```

## disassembly

```asm
0x180001048  mov     [rsp+arg_0], rbx
0x18000104d  mov     [rsp+arg_8], rsi
0x180001052  push    rdi
0x180001053  sub     rsp, 30h
0x180001057  test    cs:g_dwDebugFlags, 3
0x18000105e  lea     rax, ??_7UL_RESPONSE_CACHE_ENTRY@@6B@; const UL_RESPONSE_CACHE_ENTRY::`vftable'
0x180001065  mov     [rcx], rax
0x180001068  lea     rsi, [rcx+240h]
0x18000106f  mov     rdi, rcx
0x180001072  mov     dword ptr [rcx+8], 78726C75h
0x180001079  jnz     loc_180001138
0x18000107f  mov     rax, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001086  mov     rcx, [rax]
0x180001089  mov     rbx, [rcx+48h]
0x18000108d  mov     rcx, rsi
0x180001090  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001096  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000109d  mov     rdx, rax
0x1800010a0  mov     rax, rbx
0x1800010a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010a8  mov     rcx, [rdi+318h]
0x1800010af  test    rcx, rcx
0x1800010b2  jz      short loc_1800010CB
0x1800010b4  mov     rax, [rcx]
0x1800010b7  mov     rax, [rax+8]
0x1800010bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010c0  mov     qword ptr [rdi+318h], 0
0x1800010cb  lea     rbx, [rdi+300h]
0x1800010d2  mov     rax, [rbx]
0x1800010d5  cmp     rax, rbx
0x1800010d8  jz      short loc_1800010EA
0x1800010da  mov     rdx, [rax]; unsigned int
0x1800010dd  cmp     [rdx+8], rax
0x1800010e1  jz      short loc_180001118
0x1800010e3  mov     ecx, 3
0x1800010e8  int     29h; Win8: RtlFailFast(ecx)
0x1800010ea  lea     rcx, [rdi+310h]
0x1800010f1  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800010f7  mov     rcx, rsi
0x1800010fa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001100  lea     rcx, [rdi+10h]; this
0x180001104  mov     rbx, [rsp+38h+arg_0]
0x180001109  mov     rsi, [rsp+38h+arg_8]
0x18000110e  add     rsp, 30h
0x180001112  pop     rdi
0x180001113  jmp     ??1UL_RESPONSE_CACHE_KEY@@QEAA@XZ; UL_RESPONSE_CACHE_KEY::~UL_RESPONSE_CACHE_KEY(void)
0x180001118  mov     r8, [rax+8]
0x18000111c  cmp     [r8], rax
0x18000111f  jnz     short loc_1800010E3
0x180001121  lea     rcx, [rax-8]; this
0x180001125  mov     [r8], rdx
0x180001128  mov     [rdx+8], r8
0x18000112c  test    rcx, rcx
0x18000112f  jz      short loc_1800010D2
0x180001131  call    ??_GINVALIDATION_URL_LIST_ENTRY@@QEAAPEAXI@Z; INVALIDATION_URL_LIST_ENTRY::`scalar deleting destructor'(uint)
0x180001136  jmp     short loc_1800010D2
0x180001138  mov     rcx, rsi
0x18000113b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001141  mov     rcx, cs:g_pDebug
0x180001148  lea     r9, aUlResponseCach; "UL_RESPONSE_CACHE_ENTRY::~UL_RESPONSE_C"...
0x18000114f  mov     [rsp+38h+var_10], rax
0x180001154  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000115b  lea     rax, aInvalidatingUr; "Invalidating URL %ws\n"
0x180001162  mov     r8d, 5B2h
0x180001168  mov     [rsp+38h+var_18], rax
0x18000116d  call    cs:__imp_PuDbgPrint
0x180001173  jmp     loc_18000107F
```
