# CONFIG_PATH_MAPPER::ReInitializePathMapTable(void)

- ea: `0x18005329c`
- end: `0x180053477`
- name: `?ReInitializePathMapTable@CONFIG_PATH_MAPPER@@AEAAJXZ`
- size: `475`
- prototype: `__int64 __fastcall(CONFIG_PATH_MAPPER *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18004ff30`
- `0x1800536b4`

## callees

- `0x180007de0`
- `0x180019564`
- `0x18001c250`
- `0x18005329c`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x180053317`
- `iisutil!SAFE_snwprintf` at `0x180053317`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005344a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005344a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005332b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053420`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005332b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053420`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800532eb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800532eb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053339`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053339`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180053404`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180053404`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800532f8`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800532f8`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180053365`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180053365`

## string_xrefs

- `0x1800533ec`: `PATHMAP_TABLE`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::ReInitializePathMapTable(CONFIG_PATH_MAPPER *this)
{
  int appended; // ebx
  const unsigned __int16 *Str; // rax
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  char *v5; // rax
  PATHMAP_TABLE *v6; // rbx
  const unsigned __int16 *v7; // rax
  _BYTE v9[64]; // [rsp+50h] [rbp-158h] BYREF
  unsigned __int16 v10[128]; // [rsp+90h] [rbp-118h] BYREF

  memset_0(v10, 0, sizeof(v10));
  STRU::STRU((STRU *)v9, v10, 0x80u);
  STRU::Reset((CONFIG_PATH_MAPPER *)((char *)this + 112));
  appended = SAFE_snwprintf((CONFIG_PATH_MAPPER *)((char *)this + 112), L"v%d.%d.%d", 4);
  if ( appended >= 0 )
  {
    Str = STRU::QueryStr((CONFIG_PATH_MAPPER *)((char *)this + 56));
    appended = STRU::Copy((STRU *)v9, Str);
    if ( appended >= 0 )
    {
      appended = CONFIG_PATH_MAPPER::AppendTrailingSlash((struct STRU *)v9);
      if ( appended >= 0 )
      {
        appended = STRU::Append((STRU *)v9, (CONFIG_PATH_MAPPER *)((char *)this + 112));
        if ( appended >= 0 )
        {
          v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 24);
          if ( v4 )
          {
            (**v4)(v4, 1);
            *((_QWORD *)this + 24) = 0;
          }
          v5 = (char *)operator new(0x50u);
          v6 = (PATHMAP_TABLE *)v5;
          if ( v5 )
          {
            CLKRHashTable::CLKRHashTable(
              (CLKRHashTable *)(v5 + 8),
              "PATHMAP_TABLE",
              (unsigned __int64 (*)(const void *))CTypedHashTable<PATHMAP_TABLE,PATHMAP_ENTRY,unsigned short const *,CLKRHashTable>::_ExtractKey,
              (unsigned int (*)(unsigned __int64))CTypedHashTable<PATHMAP_TABLE,PATHMAP_ENTRY,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
              (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<SITE_NAME_TABLE,SITE_ENTRY,unsigned short const *,CLKRHashTable>::_EqualKeys,
              (void (*)(const void *, int))CTypedHashTable<PATHMAP_TABLE,PATHMAP_ENTRY,unsigned short const *,CLKRHashTable>::_AddRefRecord,
              4.0,
              1u,
              0,
              0);
            *(_QWORD *)v6 = &SIMPLE_SITE_ID_TABLE::`vftable';
            *((_QWORD *)this + 24) = v6;
            v7 = STRU::QueryStr((STRU *)v9);
            appended = PATHMAP_TABLE::Create(v6, v7);
          }
          else
          {
            *((_QWORD *)this + 24) = 0;
            appended = -2147024888;
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v9);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18005329c  mov     [rsp+arg_8], rbx
0x1800532a1  mov     [rsp+arg_10], rsi
0x1800532a6  push    rdi
0x1800532a7  sub     rsp, 1A0h
0x1800532ae  mov     rax, cs:__security_cookie
0x1800532b5  xor     rax, rsp
0x1800532b8  mov     [rsp+1A8h+var_18], rax
0x1800532c0  mov     rdi, rcx
0x1800532c3  xor     edx, edx; Val
0x1800532c5  lea     rcx, [rsp+1A8h+var_118]; void *
0x1800532cd  mov     r8d, 100h; Size
0x1800532d3  call    memset_0
0x1800532d8  mov     r8d, 80h
0x1800532de  lea     rdx, [rsp+1A8h+var_118]
0x1800532e6  lea     rcx, [rsp+1A8h+var_158]
0x1800532eb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800532f1  lea     rsi, [rdi+70h]
0x1800532f5  mov     rcx, rsi
0x1800532f8  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x1800532fe  xor     r9d, r9d
0x180053301  mov     dword ptr [rsp+1A8h+var_188], 766Fh
0x180053309  lea     rdx, aVDDD; "v%d.%d.%d"
0x180053310  mov     rcx, rsi
0x180053313  lea     r8d, [r9+4]
0x180053317  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18005331d  mov     ebx, eax
0x18005331f  test    eax, eax
0x180053321  js      loc_180053445
0x180053327  lea     rcx, [rdi+38h]
0x18005332b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180053331  mov     rdx, rax
0x180053334  lea     rcx, [rsp+1A8h+var_158]
0x180053339  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005333f  mov     ebx, eax
0x180053341  test    eax, eax
0x180053343  js      loc_180053445
0x180053349  lea     rcx, [rsp+1A8h+var_158]; struct STRU *
0x18005334e  call    ?AppendTrailingSlash@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@@Z; CONFIG_PATH_MAPPER::AppendTrailingSlash(STRU *)
0x180053353  mov     ebx, eax
0x180053355  test    eax, eax
0x180053357  js      loc_180053445
0x18005335d  mov     rdx, rsi
0x180053360  lea     rcx, [rsp+1A8h+var_158]
0x180053365  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18005336b  mov     ebx, eax
0x18005336d  test    eax, eax
0x18005336f  js      loc_180053445
0x180053375  mov     rcx, [rdi+0C0h]
0x18005337c  mov     esi, 1
0x180053381  test    rcx, rcx
0x180053384  jz      short loc_18005339E
0x180053386  mov     rax, [rcx]
0x180053389  mov     edx, esi
0x18005338b  mov     rax, [rax]
0x18005338e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053393  mov     qword ptr [rdi+0C0h], 0
0x18005339e  mov     ecx, 50h ; 'P'; Size
0x1800533a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800533a8  mov     rbx, rax
0x1800533ab  test    rax, rax
0x1800533ae  jz      loc_180053435
0x1800533b4  movsd   xmm0, cs:__real@4010000000000000
0x1800533bc  lea     rcx, [rax+8]
0x1800533c0  mov     [rsp+1A8h+var_160], 0
0x1800533c5  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VPATHMAP_TABLE@@VPATHMAP_ENTRY@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<PATHMAP_TABLE,PATHMAP_ENTRY,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x1800533cc  mov     [rsp+1A8h+var_168], 0
0x1800533d4  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VPATHMAP_TABLE@@VPATHMAP_ENTRY@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<PATHMAP_TABLE,PATHMAP_ENTRY,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x1800533db  mov     [rsp+1A8h+var_170], esi
0x1800533df  lea     r8, ?_ExtractKey@?$CTypedHashTable@VPATHMAP_TABLE@@VPATHMAP_ENTRY@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<PATHMAP_TABLE,PATHMAP_ENTRY,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x1800533e6  movsd   [rsp+1A8h+var_178], xmm0
0x1800533ec  lea     rdx, aPathmapTable; "PATHMAP_TABLE"
0x1800533f3  mov     [rsp+1A8h+var_180], rax
0x1800533f8  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSITE_NAME_TABLE@@VSITE_ENTRY@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<SITE_NAME_TABLE,SITE_ENTRY,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800533ff  mov     [rsp+1A8h+var_188], rax
0x180053404  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18005340a  lea     rax, ??_7SIMPLE_SITE_ID_TABLE@@6B@; const SIMPLE_SITE_ID_TABLE::`vftable'
0x180053411  mov     [rbx], rax
0x180053414  lea     rcx, [rsp+1A8h+var_158]
0x180053419  mov     [rdi+0C0h], rbx
0x180053420  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180053426  mov     rdx, rax; unsigned __int16 *
0x180053429  mov     rcx, rbx; this
0x18005342c  call    ?Create@PATHMAP_TABLE@@QEAAJPEBG@Z; PATHMAP_TABLE::Create(ushort const *)
0x180053431  mov     ebx, eax
0x180053433  jmp     short loc_180053445
0x180053435  mov     qword ptr [rdi+0C0h], 0
0x180053440  mov     ebx, 80070008h
0x180053445  lea     rcx, [rsp+1A8h+var_158]
0x18005344a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180053450  mov     eax, ebx
0x180053452  mov     rcx, [rsp+1A8h+var_18]
0x18005345a  xor     rcx, rsp; StackCookie
0x18005345d  call    __security_check_cookie
0x180053462  lea     r11, [rsp+1A8h+var_8]
0x18005346a  mov     rbx, [r11+18h]
0x18005346e  mov     rsi, [r11+20h]
0x180053472  mov     rsp, r11
0x180053475  pop     rdi
0x180053476  retn
```
