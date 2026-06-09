# RetrieveResponse(IHttpContext *,int *,IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *,int)

- ea: `0x180002f20`
- end: `0x180003386`
- name: `?RetrieveResponse@@YAXPEAVIHttpContext@@PEAHPEAW4enumResult@OUTPUT_CACHE_LOOKUP_END@IISCacheEvents@@H@Z`
- size: `1126`
- prototype: `void __fastcall(struct IHttpContext *, int *, enum IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180001280`

## callees

- `0x180002f20`
- `0x18000338c`
- `0x180004744`
- `0x180004778`
- `0x180005200`
- `0x180005270`
- `0x18000534c`
- `0x1800064fc`
- `0x18000657c`
- `0x1800065c8`
- `0x180006628`
- `0x180007d40`
- `0x18000838c`
- `0x180008bf0`
- `0x180009010`

## import_xrefs

- `msvcrt!_ultow` at `0x180003268`
- `msvcrt!_ultow` at `0x180003268`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800031e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800031e8`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800032e7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180003319`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800032e7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180003319`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003057`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003061`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800032c5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800032cf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003057`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003061`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800032c5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800032cf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000308f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000308f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000306e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000307b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003085`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000306e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000307b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003085`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800032f7`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800032f7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002fd7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002fd7`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180002fef`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x18000300d`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180002fef`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x18000300d`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000302a`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000302a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003350`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003350`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002ffc`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000301b`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002ffc`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000301b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003361`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003361`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002f91`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002fa6`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002f91`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002fa6`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000315b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003168`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000315b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003168`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000333b`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000333b`

## pseudocode

```c
void __fastcall RetrieveResponse(
        struct IHttpContext *a1,
        int *a2,
        enum IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *a3,
        int a4)
{
  volatile signed __int32 *v6; // rsi
  VARY_BY_CACHE_ENTRY *v7; // r13
  struct RESPONSE_ENTRY *RefedResponseEntry; // r15
  CReaderWriterLock3 *v9; // rdi
  int v10; // ebx
  const char *Str; // rax
  const char *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  void *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const char *v20; // rdi
  const char *v21; // rbx
  const char *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  const char *v25; // rax
  int *v26; // r8
  DWORD TickCount; // eax
  DWORD v28; // r12d
  int v29; // ebx
  unsigned int v30; // edi
  __int64 v31; // rax
  __int64 v32; // rdx
  const unsigned __int16 *v33; // rax
  VARY_BY_CACHE_ENTRY *v35; // [rsp+38h] [rbp-C8h] BYREF
  OUTPUT_ENTRY *v36; // [rsp+40h] [rbp-C0h] BYREF
  int *v37; // [rsp+48h] [rbp-B8h]
  enum IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *v38; // [rsp+50h] [rbp-B0h]
  _BYTE v39[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v40[64]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v41[56]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v42[120]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v43[312]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v44[312]; // [rsp+2B8h] [rbp+1B8h] BYREF
  wchar_t Buffer[4]; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v46; // [rsp+3F8h] [rbp+2F8h]
  const unsigned __int16 *v47; // [rsp+400h] [rbp+300h]
  char v48[256]; // [rsp+410h] [rbp+310h] BYREF
  char v49[256]; // [rsp+510h] [rbp+410h] BYREF

  v38 = a3;
  v37 = a2;
  v35 = 0;
  OUTPUT_KEY::OUTPUT_KEY((OUTPUT_KEY *)v41);
  v6 = 0;
  v36 = 0;
  STRA::STRA((STRA *)v40, v48, 0x100u);
  STRA::STRA((STRA *)v39, v49, 0x100u);
  *a2 = 0;
  if ( (int)VARY_BY_CACHE_ENTRY::RetrieveEntry(a1, 0, &v35) < 0 )
  {
    STRA::~STRA((STRA *)v39);
    STRA::~STRA((STRA *)v40);
    OUTPUT_KEY::~OUTPUT_KEY((OUTPUT_KEY *)v41);
  }
  else
  {
    v7 = v35;
    RefedResponseEntry = 0;
    v9 = (VARY_BY_CACHE_ENTRY *)((char *)v35 + 1320);
    CReaderWriterLock3::ReadLock((VARY_BY_CACHE_ENTRY *)((char *)v35 + 1320));
    v10 = *((_DWORD *)v7 + 172);
    if ( v10 )
    {
      Str = STRA::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)v7 + 696));
      if ( (int)STRA::Copy((STRA *)v40, Str) < 0
        || (v12 = STRA::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)v7 + 1008)), (int)STRA::Copy((STRA *)v39, v12) < 0) )
      {
        v10 = 0;
      }
    }
    CReaderWriterLock3::ReadUnlock(v9);
    if ( v10 )
    {
      v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v15 = *(_QWORD *)a1;
      if ( v14 )
      {
        v31 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v15 + 160))(a1);
        v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v17 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 56LL))(v32);
      }
      else
      {
        v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v15 + 48))(a1);
        v17 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
      }
      if ( VARY_BY_CACHE_ENTRY::CheckIfFileHasChanged(v7, v17) )
      {
        v33 = STRU::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)v7 + 24));
        TREE_HASH_TABLE::DeletePath((TREE_HASH_TABLE *)g_pVaryByCache, v33);
        v46 = 0;
        *(_QWORD *)Buffer = &OUTPUT_CACHE::CacheFlushByFileChange;
        v47 = STRU::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)v7 + 336));
        CLKRHashTable::DeleteIf(
          (CLKRHashTable *)g_pOutputCache,
          (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred,
          Buffer);
      }
      else
      {
        v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
        v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v20 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 64LL))(v19);
        v21 = STRA::QueryStr((STRA *)v39);
        v22 = STRA::QueryStr((STRA *)v40);
        if ( OUTPUT_KEY::Initialize((OUTPUT_KEY *)v41, a1, v22, v21, v20) >= 0 )
        {
          CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::FindKey(v23, v41, &v36);
          v6 = (volatile signed __int32 *)v36;
          if ( v36 )
          {
            v24 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
            v25 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 16LL))(v24, 22);
            RefedResponseEntry = OUTPUT_ENTRY::GetRefedResponseEntry((OUTPUT_ENTRY *)v6, v25, v26);
            if ( RefedResponseEntry )
            {
              TickCount = GetTickCount();
              v28 = TickCount;
              if ( a4
                || (v29 = *((_DWORD *)RefedResponseEntry + 147),
                    v30 = *((_DWORD *)RefedResponseEntry + 148),
                    TickCount - v29 > v30) )
              {
                CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v6 + 204));
                OUTPUT_ENTRY::ClearIdentityResponseEntry((OUTPUT_ENTRY *)v6);
                CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v6 + 204));
              }
              else
              {
                _InterlockedIncrement(v6 + 202);
                _InterlockedIncrement((volatile signed __int32 *)g_pOutputCache + 30);
                RESPONSE_ENTRY::AddToResponse(RefedResponseEntry, a1, v37, v38);
                RefedResponseEntry = 0;
                if ( *v37 && v30 != -1 )
                {
                  _ultow(v30 + v29 - v28, Buffer, 10);
                  (*(void (__fastcall **)(struct IHttpContext *, const char *, wchar_t *))(*(_QWORD *)a1 + 136LL))(
                    a1,
                    "OC_DURATION",
                    Buffer);
                }
              }
            }
          }
        }
      }
    }
    VARY_BY_CACHE_ENTRY::DereferenceCacheData(v7);
    if ( RefedResponseEntry )
      RESPONSE_ENTRY::DereferenceResponseEntry(RefedResponseEntry);
    if ( v6 )
      OUTPUT_ENTRY::DereferenceOutputEntry((OUTPUT_ENTRY *)v6);
    STRA::~STRA((STRA *)v39);
    STRA::~STRA((STRA *)v40);
    STRU::~STRU((STRU *)v44);
    STRU::~STRU((STRU *)v43);
    STRU::~STRU((STRU *)v42);
    BUFFER::~BUFFER((BUFFER *)v41);
  }
}

```

## disassembly

```asm
0x180002f20  mov     [rsp-8+arg_18], rbx
0x180002f25  push    rbp
0x180002f26  push    rsi
0x180002f27  push    rdi
0x180002f28  push    r12
0x180002f2a  push    r13
0x180002f2c  push    r14
0x180002f2e  push    r15
0x180002f30  lea     rbp, [rsp-520h]
0x180002f38  sub     rsp, 620h
0x180002f3f  mov     rax, cs:__security_cookie
0x180002f46  xor     rax, rsp
0x180002f49  mov     [rbp+550h+var_40], rax
0x180002f50  mov     r14, rcx
0x180002f53  mov     [rsp+650h+var_620], r9d
0x180002f58  lea     rcx, [rbp+550h+var_580]; this
0x180002f5c  mov     [rsp+650h+var_600], r8
0x180002f61  mov     rbx, rdx
0x180002f64  mov     [rsp+650h+var_608], rdx
0x180002f69  mov     [rsp+650h+var_618], 0
0x180002f72  call    ??0OUTPUT_KEY@@QEAA@XZ; OUTPUT_KEY::OUTPUT_KEY(void)
0x180002f77  mov     edi, 100h
0x180002f7c  lea     rdx, [rbp+550h+var_240]
0x180002f83  xor     esi, esi
0x180002f85  lea     rcx, [rbp+550h+var_5C0]
0x180002f89  mov     r8d, edi
0x180002f8c  mov     [rsp+650h+var_610], rsi
0x180002f91  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002f97  mov     r8d, edi
0x180002f9a  lea     rdx, [rbp+550h+var_140]
0x180002fa1  lea     rcx, [rsp+650h+var_5F8]
0x180002fa6  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002fac  lea     r8, [rsp+650h+var_618]; struct VARY_BY_CACHE_ENTRY **
0x180002fb1  mov     [rbx], esi
0x180002fb3  xor     edx, edx; int
0x180002fb5  mov     rcx, r14; struct IHttpContext *
0x180002fb8  call    ?RetrieveEntry@VARY_BY_CACHE_ENTRY@@SAJPEAVIHttpContext@@HPEAPEAV1@@Z; VARY_BY_CACHE_ENTRY::RetrieveEntry(IHttpContext *,int,VARY_BY_CACHE_ENTRY * *)
0x180002fbd  test    eax, eax
0x180002fbf  js      loc_1800032C0
0x180002fc5  mov     r13, [rsp+650h+var_618]
0x180002fca  xor     r15d, r15d
0x180002fcd  lea     rdi, [r13+528h]
0x180002fd4  mov     rcx, rdi
0x180002fd7  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180002fdd  mov     ebx, [r13+2B0h]
0x180002fe4  test    ebx, ebx
0x180002fe6  jz      short loc_180003027
0x180002fe8  lea     rcx, [r13+2B8h]
0x180002fef  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x180002ff5  mov     rdx, rax
0x180002ff8  lea     rcx, [rbp+550h+var_5C0]
0x180002ffc  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180003002  test    eax, eax
0x180003004  js      short loc_180003025
0x180003006  lea     rcx, [r13+3F0h]
0x18000300d  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x180003013  mov     rdx, rax
0x180003016  lea     rcx, [rsp+650h+var_5F8]
0x18000301b  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180003021  test    eax, eax
0x180003023  jns     short loc_180003027
0x180003025  xor     ebx, ebx
0x180003027  mov     rcx, rdi
0x18000302a  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180003030  test    ebx, ebx
0x180003032  jnz     loc_1800030BF
0x180003038  mov     rcx, r13; this
0x18000303b  call    ?DereferenceCacheData@VARY_BY_CACHE_ENTRY@@QEAAXXZ; VARY_BY_CACHE_ENTRY::DereferenceCacheData(void)
0x180003040  test    r15, r15
0x180003043  jnz     loc_18000336C
0x180003049  test    rsi, rsi
0x18000304c  jnz     loc_180003379
0x180003052  lea     rcx, [rsp+650h+var_5F8]
0x180003057  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000305d  lea     rcx, [rbp+550h+var_5C0]
0x180003061  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003067  lea     rcx, [rbp+550h+var_398]
0x18000306e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003074  lea     rcx, [rbp+550h+var_4D0]
0x18000307b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003081  lea     rcx, [rbp+550h+var_548]
0x180003085  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000308b  lea     rcx, [rbp+550h+var_580]
0x18000308f  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003095  mov     rcx, [rbp+550h+var_40]
0x18000309c  xor     rcx, rsp; StackCookie
0x18000309f  call    __security_check_cookie
0x1800030a4  mov     rbx, [rsp+650h+arg_18]
0x1800030ac  add     rsp, 620h
0x1800030b3  pop     r15
0x1800030b5  pop     r14
0x1800030b7  pop     r13
0x1800030b9  pop     r12
0x1800030bb  pop     rdi
0x1800030bc  pop     rsi
0x1800030bd  pop     rbp
0x1800030be  retn
0x1800030bf  mov     rax, [r14]
0x1800030c2  mov     rcx, r14
0x1800030c5  mov     rax, [rax+0A0h]
0x1800030cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d1  mov     rdx, rax
0x1800030d4  mov     rcx, [rax]
0x1800030d7  mov     rax, [rcx+10h]
0x1800030db  mov     rcx, rdx
0x1800030de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e3  mov     rdx, [r14]
0x1800030e6  mov     rcx, r14
0x1800030e9  test    rax, rax
0x1800030ec  jnz     loc_180003293
0x1800030f2  mov     rax, [rdx+30h]
0x1800030f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030fb  mov     rdx, rax
0x1800030fe  mov     rcx, [rax]
0x180003101  mov     rax, [rcx+20h]
0x180003105  mov     rcx, rdx
0x180003108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000310d  mov     rdx, rax; void *
0x180003110  mov     rcx, r13; this
0x180003113  call    ?CheckIfFileHasChanged@VARY_BY_CACHE_ENTRY@@QEAAHPEAX@Z; VARY_BY_CACHE_ENTRY::CheckIfFileHasChanged(void *)
0x180003118  test    eax, eax
0x18000311a  jnz     loc_1800032E3
0x180003120  mov     rax, [r14]
0x180003123  mov     rcx, r14
0x180003126  mov     rax, [rax+20h]
0x18000312a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000312f  mov     rdx, rax
0x180003132  mov     rcx, [rax]
0x180003135  mov     rax, [rcx+10h]
0x180003139  mov     rcx, rdx
0x18000313c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003141  mov     rdx, rax
0x180003144  mov     rcx, [rax]
0x180003147  mov     rax, [rcx+40h]
0x18000314b  mov     rcx, rdx
0x18000314e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003153  lea     rcx, [rsp+650h+var_5F8]
0x180003158  mov     rdi, rax
0x18000315b  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003161  lea     rcx, [rbp+550h+var_5C0]
0x180003165  mov     rbx, rax
0x180003168  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000316e  mov     r9, rbx; char *
0x180003171  mov     [rsp+650h+var_630], rdi; char *
0x180003176  mov     r8, rax; char *
0x180003179  lea     rcx, [rbp+550h+var_580]; this
0x18000317d  mov     rdx, r14; struct IHttpContext *
0x180003180  call    ?Initialize@OUTPUT_KEY@@QEAAJPEAVIHttpContext@@PEBD11@Z; OUTPUT_KEY::Initialize(IHttpContext *,char const *,char const *,char const *)
0x180003185  test    eax, eax
0x180003187  js      loc_180003038
0x18000318d  lea     r8, [rsp+650h+var_610]
0x180003192  lea     rdx, [rbp+550h+var_580]
0x180003196  call    ?FindKey@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEAVOUTPUT_KEY@@PEAPEAVOUTPUT_ENTRY@@@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::FindKey(OUTPUT_KEY * const,OUTPUT_ENTRY * *)
0x18000319b  mov     rsi, [rsp+650h+var_610]
0x1800031a0  test    rsi, rsi
0x1800031a3  jz      loc_180003038
0x1800031a9  mov     rax, [r14]
0x1800031ac  mov     rcx, r14
0x1800031af  mov     rax, [rax+18h]
0x1800031b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b8  mov     r9, rax
0x1800031bb  xor     r8d, r8d
0x1800031be  mov     rcx, [rax]
0x1800031c1  lea     edx, [r8+16h]
0x1800031c5  mov     rax, [rcx+10h]
0x1800031c9  mov     rcx, r9
0x1800031cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d1  mov     rdx, rax; char *
0x1800031d4  mov     rcx, rsi; this
0x1800031d7  call    ?GetRefedResponseEntry@OUTPUT_ENTRY@@QEAAPEAVRESPONSE_ENTRY@@PEBDPEAH@Z; OUTPUT_ENTRY::GetRefedResponseEntry(char const *,int *)
0x1800031dc  mov     r15, rax
0x1800031df  test    rax, rax
0x1800031e2  jz      loc_180003038
0x1800031e8  call    cs:__imp_GetTickCount
0x1800031ee  cmp     [rsp+650h+var_620], 0
0x1800031f3  mov     r12d, eax
0x1800031f6  jnz     loc_180003346
0x1800031fc  mov     ebx, [r15+24Ch]
0x180003203  mov     ecx, eax
0x180003205  mov     edi, [r15+250h]
0x18000320c  sub     ecx, ebx
0x18000320e  cmp     ecx, edi
0x180003210  ja      loc_180003346
0x180003216  lock inc dword ptr [rsi+328h]
0x18000321d  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180003224  lock inc dword ptr [rcx+78h]
0x180003228  mov     r9, [rsp+650h+var_600]; enum IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *
0x18000322d  mov     rdx, r14; struct IHttpContext *
0x180003230  mov     r8, [rsp+650h+var_608]; int *
0x180003235  mov     rcx, r15; this
0x180003238  call    ?AddToResponse@RESPONSE_ENTRY@@QEAAJPEAVIHttpContext@@PEAHPEAW4enumResult@OUTPUT_CACHE_LOOKUP_END@IISCacheEvents@@@Z; RESPONSE_ENTRY::AddToResponse(IHttpContext *,int *,IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *)
0x18000323d  mov     rax, [rsp+650h+var_608]
0x180003242  xor     r15d, r15d
0x180003245  cmp     [rax], r15d
0x180003248  jz      loc_180003038
0x18000324e  cmp     edi, 0FFFFFFFFh
0x180003251  jz      loc_180003038
0x180003257  sub     ebx, r12d
0x18000325a  lea     r8d, [r15+0Ah]; Radix
0x18000325e  lea     rdx, [rbp+550h+Buffer]; Buffer
0x180003265  lea     ecx, [rdi+rbx]; Value
0x180003268  call    cs:__imp__ultow
0x18000326e  mov     rax, [r14]
0x180003271  lea     r8, [rbp+550h+Buffer]
0x180003278  lea     rdx, aOcDuration; "OC_DURATION"
0x18000327f  mov     rcx, r14
0x180003282  mov     rax, [rax+88h]
0x180003289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328e  jmp     loc_180003038
0x180003293  mov     rax, [rdx+0A0h]
0x18000329a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000329f  mov     rdx, rax
0x1800032a2  mov     rcx, [rax]
0x1800032a5  mov     rax, [rcx+10h]
0x1800032a9  mov     rcx, rdx
0x1800032ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b1  mov     rdx, rax
0x1800032b4  mov     rcx, [rax]
0x1800032b7  mov     rax, [rcx+38h]
0x1800032bb  jmp     loc_180003105
0x1800032c0  lea     rcx, [rsp+650h+var_5F8]
0x1800032c5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800032cb  lea     rcx, [rbp+550h+var_5C0]
0x1800032cf  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800032d5  lea     rcx, [rbp+550h+var_580]; this
0x1800032d9  call    ??1OUTPUT_KEY@@QEAA@XZ; OUTPUT_KEY::~OUTPUT_KEY(void)
0x1800032de  jmp     loc_180003095
0x1800032e3  lea     rcx, [r13+18h]
0x1800032e7  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800032ed  mov     rcx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; VARY_BY_CACHE * g_pVaryByCache
0x1800032f4  mov     rdx, rax
0x1800032f7  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x1800032fd  lea     rax, ?CacheFlushByFileChange@OUTPUT_CACHE@@SA?AW4LK_PREDICATE@@PEAVOUTPUT_ENTRY@@PEAX@Z; OUTPUT_CACHE::CacheFlushByFileChange(OUTPUT_ENTRY *,void *)
0x180003304  mov     [rbp+550h+var_258], rsi
0x18000330b  lea     rcx, [r13+150h]
0x180003312  mov     qword ptr [rbp+550h+Buffer], rax
0x180003319  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000331f  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180003326  lea     r8, [rbp+550h+Buffer]
0x18000332d  lea     rdx, ?_Pred@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x180003334  mov     [rbp+550h+var_250], rax
0x18000333b  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180003341  jmp     loc_180003038
0x180003346  lea     rbx, [rsi+330h]
0x18000334d  mov     rcx, rbx
0x180003350  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180003356  mov     rcx, rsi; this
0x180003359  call    ?ClearIdentityResponseEntry@OUTPUT_ENTRY@@QEAAXXZ; OUTPUT_ENTRY::ClearIdentityResponseEntry(void)
0x18000335e  mov     rcx, rbx
0x180003361  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180003367  jmp     loc_180003038
0x18000336c  mov     rcx, r15; this
0x18000336f  call    ?DereferenceResponseEntry@RESPONSE_ENTRY@@QEAAXXZ; RESPONSE_ENTRY::DereferenceResponseEntry(void)
0x180003374  jmp     loc_180003049
0x180003379  mov     rcx, rsi; this
0x18000337c  call    ?DereferenceOutputEntry@OUTPUT_ENTRY@@QEAAXXZ; OUTPUT_ENTRY::DereferenceOutputEntry(void)
0x180003381  jmp     loc_180003052
```
