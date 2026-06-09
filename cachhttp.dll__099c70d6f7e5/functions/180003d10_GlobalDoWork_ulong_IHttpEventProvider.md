# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x180003d10`
- end: `0x180003fd6`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `14`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003d00`
- `0x180006940`
- `0x180006950`
- `0x180006960`
- `0x180006970`
- `0x180006980`
- `0x180006990`
- `0x1800069a0`
- `0x1800069b0`
- `0x1800069c0`
- `0x1800069d0`
- `0x1800069e0`
- `0x1800069f0`
- `0x180006a00`

## callees

- `0x180003d10`
- `0x18000653c`
- `0x180008bbe`
- `0x180008bf0`
- `0x180009010`

## import_xrefs

- `msvcrt!wcschr` at `0x180003ed0`
- `msvcrt!wcschr` at `0x180003ed0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003da5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003da5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003f34`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003f34`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003d58`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003d58`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003eae`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003fa3`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003fcb`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003eae`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003fa3`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003fcb`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x180003fb5`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x180003fb5`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x180003e9c`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x180003e9c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003f19`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003f19`
- `iisutil!?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z` at `0x180003e63`
- `iisutil!?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z` at `0x180003e63`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180003e1d`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180003e4c`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180003e1d`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180003e4c`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(int a1, __int64 a2)
{
  int v4; // ebx
  int v5; // ebx
  void *v6; // rsi
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 (__fastcall ***v9)(_QWORD, void *); // rax
  const unsigned __int16 *v10; // rax
  __int64 v11; // rdi
  const unsigned __int16 *v12; // r14
  __int64 v13; // rsi
  CLKRHashTable *v14; // rcx
  const wchar_t *v15; // r14
  wchar_t *v16; // rsi
  __int128 v17; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h]
  _QWORD v19[3]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v20[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[56]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v22[64]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(v22, 0, sizeof(v22));
  STRU::STRU((STRU *)v21, v22, 0x40u);
  v4 = a1 - 4;
  if ( v4 )
  {
    v5 = v4 - 60;
    if ( v5 )
    {
      if ( v5 == 64 )
      {
        v6 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
        v7 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
        if ( v7 )
        {
          v9 = (__int64 (__fastcall ***)(_QWORD, void *))(**v7)(v7);
          if ( (**v9)(v9, g_pModuleId) )
          {
            v19[0] = &UL_RESPONSE_CACHE::CacheFlushByFileChange;
            v19[1] = 0;
            v19[2] = v6;
            CLKRHashTable::DeleteIf(
              (CLKRHashTable *)g_pUlCache,
              (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred,
              v19);
            v20[0] = &OUTPUT_CACHE::CacheFlushByFileChange;
            v20[1] = 0;
            v20[2] = v6;
            CLKRHashTable::DeleteIf(
              (CLKRHashTable *)g_pOutputCache,
              (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred,
              v20);
            TREE_HASH_TABLE::DeleteIf(
              (TREE_HASH_TABLE *)g_pVaryByCache,
              (int (*)(void *, void *))VARY_BY_CACHE::CacheFlushByFileChange,
              v6);
          }
        }
      }
      goto LABEL_5;
    }
    v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v11 = -1;
    v12 = v10;
    v13 = -1;
    do
      ++v13;
    while ( v10[v13] );
    TREE_HASH_TABLE::DeletePath((TREE_HASH_TABLE *)g_pVaryByCache, v10);
    if ( (unsigned int)v13 < 0x18 )
    {
      CLKRHashTable::Clear((CLKRHashTable *)g_pUlCache);
      v14 = (CLKRHashTable *)g_pOutputCache;
LABEL_26:
      CLKRHashTable::Clear(v14);
      goto LABEL_5;
    }
    v15 = v12 + 24;
    v16 = wcschr(v15, 0x2Fu);
    v18 = 0;
    v17 = 0;
    if ( v16 )
    {
      if ( (int)STRU::Copy((STRU *)v21, v15, v16 - v15) < 0 )
      {
        v14 = (CLKRHashTable *)g_pUlCache;
        goto LABEL_26;
      }
      *(_QWORD *)&v17 = STRU::QueryStr((STRU *)v21);
      *((_QWORD *)&v17 + 1) = v16;
      do
        ++v11;
      while ( v16[v11] );
      LODWORD(v18) = v11;
      if ( v16[(unsigned int)(v11 - 1)] == 47 )
        LODWORD(v18) = v11 - 1;
    }
    else
    {
      *(_QWORD *)&v17 = v15;
      *((_QWORD *)&v17 + 1) = L"/";
      LODWORD(v18) = 1;
    }
    CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(
      g_pUlCache,
      &UL_RESPONSE_CACHE::CacheFlushByMetadata,
      &v17);
    CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(
      g_pOutputCache,
      &OUTPUT_CACHE::CacheFlushByMetadata,
      &v17);
    goto LABEL_5;
  }
  if ( g_pUlCache )
    CLKRHashTable::Clear((CLKRHashTable *)g_pUlCache);
  if ( g_pVaryByCache )
    TREE_HASH_TABLE::Clear((TREE_HASH_TABLE *)g_pVaryByCache);
  v14 = (CLKRHashTable *)g_pOutputCache;
  if ( g_pOutputCache )
    goto LABEL_26;
LABEL_5:
  STRU::~STRU((STRU *)v21);
  return 0;
}

```

## disassembly

```asm
0x180003d10  push    rbp
0x180003d12  push    rbx
0x180003d13  push    rsi
0x180003d14  push    rdi
0x180003d15  push    r14
0x180003d17  push    r15
0x180003d19  lea     rbp, [rsp-38h]
0x180003d1e  sub     rsp, 138h
0x180003d25  mov     rax, cs:__security_cookie
0x180003d2c  xor     rax, rsp
0x180003d2f  mov     [rbp+60h+var_40], rax
0x180003d33  mov     rdi, rdx
0x180003d36  mov     ebx, ecx
0x180003d38  xor     edx, edx; Val
0x180003d3a  lea     rcx, [rbp+60h+var_C0]; void *
0x180003d3e  mov     r8d, 80h; Size
0x180003d44  call    memset_0
0x180003d49  mov     r8d, 40h ; '@'
0x180003d4f  lea     rdx, [rbp+60h+var_C0]
0x180003d53  lea     rcx, [rsp+160h+var_F8]
0x180003d58  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003d5e  sub     ebx, 4
0x180003d61  jz      loc_180003F97
0x180003d67  sub     ebx, 3Ch ; '<'
0x180003d6a  jz      loc_180003E6E
0x180003d70  cmp     ebx, 40h ; '@'
0x180003d73  jnz     short loc_180003DA0
0x180003d75  mov     rax, [rdi]
0x180003d78  mov     rcx, rdi
0x180003d7b  mov     rax, [rax+8]
0x180003d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d84  mov     rdx, [rdi]
0x180003d87  mov     rsi, rax
0x180003d8a  mov     rcx, rdi
0x180003d8d  mov     rax, [rdx+10h]
0x180003d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d96  xor     ebx, ebx
0x180003d98  mov     rdx, rax
0x180003d9b  test    rax, rax
0x180003d9e  jnz     short loc_180003DC9
0x180003da0  lea     rcx, [rsp+160h+var_F8]
0x180003da5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003dab  xor     eax, eax
0x180003dad  mov     rcx, [rbp+60h+var_40]
0x180003db1  xor     rcx, rsp; StackCookie
0x180003db4  call    __security_check_cookie
0x180003db9  add     rsp, 138h
0x180003dc0  pop     r15
0x180003dc2  pop     r14
0x180003dc4  pop     rdi
0x180003dc5  pop     rsi
0x180003dc6  pop     rbx
0x180003dc7  pop     rbp
0x180003dc8  retn
0x180003dc9  mov     rcx, [rax]
0x180003dcc  mov     rax, [rcx]
0x180003dcf  mov     rcx, rdx
0x180003dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd7  mov     rdx, cs:?g_pModuleId@@3PEAXEA; void * g_pModuleId
0x180003dde  mov     r8, rax
0x180003de1  mov     rcx, [rax]
0x180003de4  mov     rax, [rcx]
0x180003de7  mov     rcx, r8
0x180003dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003def  test    rax, rax
0x180003df2  jz      short loc_180003DA0
0x180003df4  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x180003dfb  lea     rax, ?CacheFlushByFileChange@UL_RESPONSE_CACHE@@SA?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z; UL_RESPONSE_CACHE::CacheFlushByFileChange(UL_RESPONSE_CACHE_ENTRY *,void *)
0x180003e02  lea     r8, [rsp+160h+var_128]
0x180003e07  mov     [rsp+160h+var_128], rax
0x180003e0c  lea     rdx, ?_Pred@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x180003e13  mov     [rsp+160h+var_120], rbx
0x180003e18  mov     [rsp+160h+var_118], rsi
0x180003e1d  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180003e23  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180003e2a  lea     rax, ?CacheFlushByFileChange@OUTPUT_CACHE@@SA?AW4LK_PREDICATE@@PEAVOUTPUT_ENTRY@@PEAX@Z; OUTPUT_CACHE::CacheFlushByFileChange(OUTPUT_ENTRY *,void *)
0x180003e31  lea     r8, [rsp+160h+var_110]
0x180003e36  mov     [rsp+160h+var_110], rax
0x180003e3b  lea     rdx, ?_Pred@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x180003e42  mov     [rsp+160h+var_108], rbx
0x180003e47  mov     [rsp+160h+var_100], rsi
0x180003e4c  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180003e52  mov     rcx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; VARY_BY_CACHE * g_pVaryByCache
0x180003e59  lea     rdx, ?CacheFlushByFileChange@VARY_BY_CACHE@@SAHPEAX0@Z; VARY_BY_CACHE::CacheFlushByFileChange(void *,void *)
0x180003e60  mov     r8, rsi
0x180003e63  call    cs:__imp_?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z; TREE_HASH_TABLE::DeleteIf(int (*)(void *,void *),void *)
0x180003e69  jmp     loc_180003DA0
0x180003e6e  mov     rax, [rdi]
0x180003e71  mov     rcx, rdi
0x180003e74  mov     rax, [rax+8]
0x180003e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003e81  mov     r14, rax
0x180003e84  mov     rsi, rdi
0x180003e87  xor     ebx, ebx
0x180003e89  inc     rsi
0x180003e8c  cmp     [rax+rsi*2], bx
0x180003e90  jnz     short loc_180003E89
0x180003e92  mov     rcx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; VARY_BY_CACHE * g_pVaryByCache
0x180003e99  mov     rdx, r14
0x180003e9c  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x180003ea2  cmp     esi, 18h
0x180003ea5  jnb     short loc_180003EC0
0x180003ea7  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x180003eae  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180003eb4  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180003ebb  jmp     loc_180003FCB
0x180003ec0  add     r14, 30h ; '0'
0x180003ec4  mov     r15d, 2Fh ; '/'
0x180003eca  mov     edx, r15d; Ch
0x180003ecd  mov     rcx, r14; Str
0x180003ed0  call    cs:__imp_wcschr
0x180003ed6  mov     rsi, rax
0x180003ed9  xorps   xmm0, xmm0
0x180003edc  xor     eax, eax
0x180003ede  mov     [rsp+160h+var_130], rax
0x180003ee3  movups  [rsp+160h+var_140], xmm0
0x180003ee8  test    rsi, rsi
0x180003eeb  jnz     short loc_180003F08
0x180003eed  lea     rax, asc_18000AF64; "/"
0x180003ef4  mov     qword ptr [rsp+160h+var_140], r14
0x180003ef9  mov     qword ptr [rsp+160h+var_140+8], rax
0x180003efe  mov     dword ptr [rsp+160h+var_130], 1
0x180003f06  jmp     short loc_180003F62
0x180003f08  mov     r8, rsi
0x180003f0b  lea     rcx, [rsp+160h+var_F8]
0x180003f10  sub     r8, r14
0x180003f13  mov     rdx, r14
0x180003f16  sar     r8, 1
0x180003f19  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180003f1f  test    eax, eax
0x180003f21  jns     short loc_180003F2F
0x180003f23  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x180003f2a  jmp     loc_180003FCB
0x180003f2f  lea     rcx, [rsp+160h+var_F8]
0x180003f34  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003f3a  mov     qword ptr [rsp+160h+var_140], rax
0x180003f3f  mov     qword ptr [rsp+160h+var_140+8], rsi
0x180003f44  inc     rdi
0x180003f47  cmp     [rsi+rdi*2], bx
0x180003f4b  jnz     short loc_180003F44
0x180003f4d  lea     eax, [rdi-1]
0x180003f50  mov     dword ptr [rsp+160h+var_130], edi
0x180003f54  cmp     [rsi+rax*2], r15w
0x180003f59  jnz     short loc_180003F62
0x180003f5b  lea     eax, [rdi-1]
0x180003f5e  mov     dword ptr [rsp+160h+var_130], eax
0x180003f62  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x180003f69  lea     r8, [rsp+160h+var_140]
0x180003f6e  lea     rdx, ?CacheFlushByMetadata@UL_RESPONSE_CACHE@@SA?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z; UL_RESPONSE_CACHE::CacheFlushByMetadata(UL_RESPONSE_CACHE_ENTRY *,void *)
0x180003f75  call    ?DeleteIf@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@QEAAKP6A?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z1@Z; CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(LK_PREDICATE (*)(UL_RESPONSE_CACHE_ENTRY *,void *),void *)
0x180003f7a  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180003f81  lea     r8, [rsp+160h+var_140]
0x180003f86  lea     rdx, ?CacheFlushByMetadata@OUTPUT_CACHE@@SA?AW4LK_PREDICATE@@PEAVOUTPUT_ENTRY@@PEAX@Z; OUTPUT_CACHE::CacheFlushByMetadata(OUTPUT_ENTRY *,void *)
0x180003f8d  call    ?DeleteIf@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@QEAAKP6A?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z1@Z; CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(LK_PREDICATE (*)(UL_RESPONSE_CACHE_ENTRY *,void *),void *)
0x180003f92  jmp     loc_180003DA0
0x180003f97  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x180003f9e  test    rcx, rcx
0x180003fa1  jz      short loc_180003FA9
0x180003fa3  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180003fa9  mov     rcx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; VARY_BY_CACHE * g_pVaryByCache
0x180003fb0  test    rcx, rcx
0x180003fb3  jz      short loc_180003FBB
0x180003fb5  call    cs:__imp_?Clear@TREE_HASH_TABLE@@QEAAXXZ; TREE_HASH_TABLE::Clear(void)
0x180003fbb  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180003fc2  test    rcx, rcx
0x180003fc5  jz      loc_180003DA0
0x180003fcb  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180003fd1  jmp     loc_180003DA0
```
