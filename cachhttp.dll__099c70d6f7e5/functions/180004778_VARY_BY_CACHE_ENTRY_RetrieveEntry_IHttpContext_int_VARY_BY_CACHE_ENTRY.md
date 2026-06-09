# VARY_BY_CACHE_ENTRY::RetrieveEntry(IHttpContext *,int,VARY_BY_CACHE_ENTRY * *)

- ea: `0x180004778`
- end: `0x180004a6e`
- name: `?RetrieveEntry@VARY_BY_CACHE_ENTRY@@SAJPEAVIHttpContext@@HPEAPEAV1@@Z`
- size: `758`
- prototype: `__int64 __fastcall(struct IHttpContext *, int, struct VARY_BY_CACHE_ENTRY **)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180002f20`
- `0x180004220`

## callees

- `0x180004744`
- `0x180004778`
- `0x180004a74`
- `0x180004b0c`
- `0x1800059e0`
- `0x180005a0c`
- `0x180008bf0`
- `0x180009010`

## import_xrefs

- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x1800048f1`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x1800048f1`
- `iisutil!?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z` at `0x1800049aa`
- `iisutil!?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z` at `0x1800049aa`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800048dc`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800048dc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004a31`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004a3c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004a31`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004a3c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004821`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004838`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004821`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004838`

## pseudocode

```c
__int64 __fastcall VARY_BY_CACHE_ENTRY::RetrieveEntry(struct IHttpContext *a1, int a2, struct VARY_BY_CACHE_ENTRY **a3)
{
  __int64 v3; // rax
  int v7; // esi
  __int64 (__fastcall ***v8)(_QWORD); // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // r13d
  unsigned int v17; // r13d
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // r15
  int CacheKey; // ebx
  const unsigned __int16 *Str; // rax
  VARY_BY_CACHE_ENTRY *v23; // rax
  VARY_BY_CACHE_ENTRY *v24; // rax
  volatile signed __int32 *v25; // rax
  VARY_BY_CACHE_ENTRY *v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v27; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v28; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v29; // [rsp+48h] [rbp-B8h]
  _BYTE v30[56]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v31[128]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v32[56]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int16 v33[128]; // [rsp+1C0h] [rbp+C0h] BYREF

  v3 = *(_QWORD *)a1;
  v26 = 0;
  v7 = 1;
  v8 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 152))(a1);
  v9 = (**v8)(v8);
  v10 = (**(__int64 (__fastcall ***)(__int64, void *))v9)(v9, g_pModuleId);
  v26 = (VARY_BY_CACHE_ENTRY *)v10;
  if ( v10 )
  {
    if ( !*(_DWORD *)(v10 + 1328) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 12));
      *((_DWORD *)v26 + 4) = 2;
      *a3 = v26;
      return 0;
    }
    v7 = 0;
  }
  STRU::STRU((STRU *)v30, v31, 0x80u);
  STRU::STRU((STRU *)v32, v33, 0x80u);
  v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v13 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a1)(a1);
  v14 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  v15 = *(_QWORD *)a1;
  v16 = *(unsigned __int16 *)(v12 + 68);
  v28 = v14;
  v27 = *(unsigned __int16 **)(v12 + 88);
  v17 = v16 >> 1;
  v18 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(v15 + 184))(a1, 0);
  v19 = v28;
  v29 = v18;
  CacheKey = VARY_BY_CACHE_KEY::CreateCacheKey((VARY_BY_CACHE_KEY *)v30, v27, v17, v28, v18);
  if ( CacheKey < 0 )
    goto LABEL_25;
  Str = STRU::QueryStr((STRU *)v30);
  TREE_HASH_TABLE::FindRecord((TREE_HASH_TABLE *)g_pVaryByCache, Str, (void **)&v26);
  if ( !v26 )
  {
    if ( !a2 )
    {
      CacheKey = -2147023728;
      goto LABEL_10;
    }
    v23 = (VARY_BY_CACHE_ENTRY *)operator new(0x538u);
    if ( v23 )
    {
      v24 = VARY_BY_CACHE_ENTRY::VARY_BY_CACHE_ENTRY(v23);
      v26 = v24;
      if ( v24 )
      {
        CacheKey = VARY_BY_CACHE_KEY::CreateCacheKey((VARY_BY_CACHE_ENTRY *)((char *)v24 + 24), v27, v17, v19, v29);
        if ( CacheKey < 0 )
        {
          VARY_BY_CACHE_ENTRY::DereferenceCacheData(v26);
          goto LABEL_10;
        }
        TREE_HASH_TABLE::InsertRecord((TREE_HASH_TABLE *)g_pVaryByCache, v26);
        goto LABEL_16;
      }
    }
    else
    {
      v26 = 0;
    }
    CacheKey = -2147024888;
    goto LABEL_25;
  }
  *((_DWORD *)v26 + 4) = 2;
LABEL_16:
  if ( !v7 )
  {
LABEL_22:
    CacheKey = 0;
    *a3 = v26;
LABEL_25:
    STRU::~STRU((STRU *)v32);
    STRU::~STRU((STRU *)v30);
    return (unsigned int)CacheKey;
  }
  CacheKey = (*(__int64 (__fastcall **)(__int64, VARY_BY_CACHE_ENTRY *, void *))(*(_QWORD *)v9 + 8LL))(
               v9,
               v26,
               g_pModuleId);
  if ( CacheKey >= 0 )
  {
    v25 = (volatile signed __int32 *)v26;
    goto LABEL_21;
  }
  VARY_BY_CACHE_ENTRY::DereferenceCacheData(v26);
  if ( CacheKey == -2147024811 )
  {
    v25 = (volatile signed __int32 *)(**(__int64 (__fastcall ***)(__int64, void *))v9)(v9, g_pModuleId);
    v26 = (VARY_BY_CACHE_ENTRY *)v25;
LABEL_21:
    _InterlockedIncrement(v25 + 3);
    goto LABEL_22;
  }
LABEL_10:
  VARY_BY_CACHE_KEY::~VARY_BY_CACHE_KEY((VARY_BY_CACHE_KEY *)v30);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x180004778  mov     [rsp-8+arg_8], rbx
0x18000477d  push    rbp
0x18000477e  push    rsi
0x18000477f  push    rdi
0x180004780  push    r12
0x180004782  push    r13
0x180004784  push    r14
0x180004786  push    r15
0x180004788  lea     rbp, [rsp-1D0h]
0x180004790  sub     rsp, 2D0h
0x180004797  mov     rax, cs:__security_cookie
0x18000479e  xor     rax, rsp
0x1800047a1  mov     [rbp+200h+var_40], rax
0x1800047a8  mov     rax, [rcx]
0x1800047ab  mov     r14, r8
0x1800047ae  mov     r12d, edx
0x1800047b1  mov     [rsp+300h+var_2D0], 0
0x1800047ba  mov     r15, rcx
0x1800047bd  mov     esi, 1
0x1800047c2  mov     rax, [rax+98h]
0x1800047c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ce  mov     rdx, rax
0x1800047d1  mov     rcx, [rax]
0x1800047d4  mov     rax, [rcx]
0x1800047d7  mov     rcx, rdx
0x1800047da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047df  mov     rdx, cs:?g_pModuleId@@3PEAXEA; void * g_pModuleId
0x1800047e6  mov     rdi, rax
0x1800047e9  mov     rcx, [rax]
0x1800047ec  mov     rax, [rcx]
0x1800047ef  mov     rcx, rdi
0x1800047f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f7  mov     [rsp+300h+var_2D0], rax
0x1800047fc  test    rax, rax
0x1800047ff  jz      short loc_180004810
0x180004801  cmp     dword ptr [rax+530h], 0
0x180004808  jz      loc_18000490D
0x18000480e  xor     esi, esi
0x180004810  mov     ebx, 80h
0x180004815  lea     rdx, [rbp+200h+var_278]
0x180004819  mov     r8d, ebx
0x18000481c  lea     rcx, [rsp+300h+var_2B0]
0x180004821  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004827  mov     r8d, ebx
0x18000482a  lea     rdx, [rbp+200h+var_140]
0x180004831  lea     rcx, [rbp+200h+var_178]
0x180004838  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000483e  mov     rax, [r15]
0x180004841  mov     rcx, r15
0x180004844  mov     rax, [rax+18h]
0x180004848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000484d  mov     rdx, rax
0x180004850  mov     rcx, [rax]
0x180004853  mov     rax, [rcx+8]
0x180004857  mov     rcx, rdx
0x18000485a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000485f  mov     rcx, [r15]
0x180004862  mov     rbx, rax
0x180004865  mov     rax, [rcx]
0x180004868  mov     rcx, r15
0x18000486b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004870  mov     rcx, rax
0x180004873  mov     rdx, [rax]
0x180004876  mov     rax, [rdx+8]
0x18000487a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487f  mov     rdx, [r15]
0x180004882  mov     rcx, r15
0x180004885  movzx   r13d, word ptr [rbx+44h]
0x18000488a  mov     [rsp+300h+var_2C0], rax
0x18000488f  mov     rax, [rbx+58h]
0x180004893  mov     [rsp+300h+var_2C8], rax
0x180004898  mov     rax, [rdx+0B8h]
0x18000489f  xor     edx, edx
0x1800048a1  shr     r13d, 1
0x1800048a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a9  mov     r15, [rsp+300h+var_2C0]
0x1800048ae  lea     rcx, [rsp+300h+var_2B0]; this
0x1800048b3  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x1800048b8  mov     r9, r15; unsigned __int16 *
0x1800048bb  mov     r8d, r13d; unsigned int
0x1800048be  mov     [rsp+300h+var_2B8], rax
0x1800048c3  mov     [rsp+300h+var_2E0], rax; unsigned __int16 *
0x1800048c8  call    ?CreateCacheKey@VARY_BY_CACHE_KEY@@QEAAJPEBGK00@Z; VARY_BY_CACHE_KEY::CreateCacheKey(ushort const *,ulong,ushort const *,ushort const *)
0x1800048cd  mov     ebx, eax
0x1800048cf  test    eax, eax
0x1800048d1  js      loc_180004A2A
0x1800048d7  lea     rcx, [rsp+300h+var_2B0]
0x1800048dc  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800048e2  mov     rcx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; VARY_BY_CACHE * g_pVaryByCache
0x1800048e9  lea     r8, [rsp+300h+var_2D0]
0x1800048ee  mov     rdx, rax
0x1800048f1  call    cs:__imp_?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z; TREE_HASH_TABLE::FindRecord(ushort const *,void * *)
0x1800048f7  mov     rax, [rsp+300h+var_2D0]
0x1800048fc  test    rax, rax
0x1800048ff  jz      short loc_18000492C
0x180004901  mov     dword ptr [rax+10h], 2
0x180004908  jmp     loc_1800049B0
0x18000490d  lock inc dword ptr [rax+0Ch]
0x180004911  mov     rax, [rsp+300h+var_2D0]
0x180004916  mov     dword ptr [rax+10h], 2
0x18000491d  mov     rax, [rsp+300h+var_2D0]
0x180004922  mov     [r14], rax
0x180004925  xor     eax, eax
0x180004927  jmp     loc_180004A44
0x18000492c  test    r12d, r12d
0x18000492f  jnz     short loc_180004945
0x180004931  mov     ebx, 80070490h
0x180004936  lea     rcx, [rsp+300h+var_2B0]; this
0x18000493b  call    ??1VARY_BY_CACHE_KEY@@QEAA@XZ; VARY_BY_CACHE_KEY::~VARY_BY_CACHE_KEY(void)
0x180004940  jmp     loc_180004A42
0x180004945  mov     ecx, 538h; Size
0x18000494a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000494f  test    rax, rax
0x180004952  jz      loc_180004A1C
0x180004958  mov     rcx, rax; this
0x18000495b  call    ??0VARY_BY_CACHE_ENTRY@@QEAA@XZ; VARY_BY_CACHE_ENTRY::VARY_BY_CACHE_ENTRY(void)
0x180004960  mov     [rsp+300h+var_2D0], rax
0x180004965  test    rax, rax
0x180004968  jz      loc_180004A25
0x18000496e  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x180004973  lea     rcx, [rax+18h]; this
0x180004977  mov     rax, [rsp+300h+var_2B8]
0x18000497c  mov     r9, r15; unsigned __int16 *
0x18000497f  mov     r8d, r13d; unsigned int
0x180004982  mov     [rsp+300h+var_2E0], rax; unsigned __int16 *
0x180004987  call    ?CreateCacheKey@VARY_BY_CACHE_KEY@@QEAAJPEBGK00@Z; VARY_BY_CACHE_KEY::CreateCacheKey(ushort const *,ulong,ushort const *,ushort const *)
0x18000498c  mov     ebx, eax
0x18000498e  test    eax, eax
0x180004990  jns     short loc_18000499E
0x180004992  mov     rcx, [rsp+300h+var_2D0]; this
0x180004997  call    ?DereferenceCacheData@VARY_BY_CACHE_ENTRY@@QEAAXXZ; VARY_BY_CACHE_ENTRY::DereferenceCacheData(void)
0x18000499c  jmp     short loc_180004936
0x18000499e  mov     rdx, [rsp+300h+var_2D0]
0x1800049a3  mov     rcx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; VARY_BY_CACHE * g_pVaryByCache
0x1800049aa  call    cs:__imp_?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z; TREE_HASH_TABLE::InsertRecord(void *)
0x1800049b0  test    esi, esi
0x1800049b2  jz      short loc_180004A10
0x1800049b4  mov     rax, [rdi]
0x1800049b7  mov     rcx, rdi
0x1800049ba  mov     r8, cs:?g_pModuleId@@3PEAXEA; void * g_pModuleId
0x1800049c1  mov     rdx, [rsp+300h+var_2D0]
0x1800049c6  mov     rax, [rax+8]
0x1800049ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049cf  mov     ebx, eax
0x1800049d1  test    eax, eax
0x1800049d3  jns     short loc_180004A07
0x1800049d5  mov     rcx, [rsp+300h+var_2D0]; this
0x1800049da  call    ?DereferenceCacheData@VARY_BY_CACHE_ENTRY@@QEAAXXZ; VARY_BY_CACHE_ENTRY::DereferenceCacheData(void)
0x1800049df  cmp     ebx, 80070055h
0x1800049e5  jnz     loc_180004936
0x1800049eb  mov     rax, [rdi]
0x1800049ee  mov     rcx, rdi
0x1800049f1  mov     rdx, cs:?g_pModuleId@@3PEAXEA; void * g_pModuleId
0x1800049f8  mov     rax, [rax]
0x1800049fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a00  mov     [rsp+300h+var_2D0], rax
0x180004a05  jmp     short loc_180004A0C
0x180004a07  mov     rax, [rsp+300h+var_2D0]
0x180004a0c  lock inc dword ptr [rax+0Ch]
0x180004a10  mov     rax, [rsp+300h+var_2D0]
0x180004a15  xor     ebx, ebx
0x180004a17  mov     [r14], rax
0x180004a1a  jmp     short loc_180004A2A
0x180004a1c  mov     [rsp+300h+var_2D0], 0
0x180004a25  mov     ebx, 80070008h
0x180004a2a  lea     rcx, [rbp+200h+var_178]
0x180004a31  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004a37  lea     rcx, [rsp+300h+var_2B0]
0x180004a3c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004a42  mov     eax, ebx
0x180004a44  mov     rcx, [rbp+200h+var_40]
0x180004a4b  xor     rcx, rsp; StackCookie
0x180004a4e  call    __security_check_cookie
0x180004a53  mov     rbx, [rsp+300h+arg_8]
0x180004a5b  add     rsp, 2D0h
0x180004a62  pop     r15
0x180004a64  pop     r14
0x180004a66  pop     r13
0x180004a68  pop     r12
0x180004a6a  pop     rdi
0x180004a6b  pop     rsi
0x180004a6c  pop     rbp
0x180004a6d  retn
```
