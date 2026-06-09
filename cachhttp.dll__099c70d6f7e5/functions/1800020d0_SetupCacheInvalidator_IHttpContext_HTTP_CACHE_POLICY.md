# SetupCacheInvalidator(IHttpContext *,_HTTP_CACHE_POLICY *)

- ea: `0x1800020d0`
- end: `0x1800025de`
- name: `?SetupCacheInvalidator@@YAJPEAVIHttpContext@@PEAU_HTTP_CACHE_POLICY@@@Z`
- size: `1294`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct _HTTP_CACHE_POLICY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180001280`

## callees

- `0x1800020d0`
- `0x1800025e4`
- `0x180002610`
- `0x180002670`
- `0x180002940`
- `0x1800029c4`
- `0x180005a0c`
- `0x180008bbe`
- `0x180008bf0`
- `0x180009010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18000228d`
- `msvcrt!_wcsupr` at `0x1800022ef`
- `msvcrt!_wcsupr` at `0x180002305`
- `msvcrt!_wcsupr` at `0x18000228d`
- `msvcrt!_wcsupr` at `0x1800022ef`
- `msvcrt!_wcsupr` at `0x180002305`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800024e0`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800024e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000220f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002219`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002223`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000222e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000220f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002219`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002223`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000222e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002284`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800022e6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800022fc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000233e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000247f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002284`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800022e6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800022fc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000233e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000247f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000212e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000212e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000226f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000226f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800022a1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800022b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800022d2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800024ba`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800022a1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800022b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800022d2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800024ba`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180002320`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180002320`

## string_xrefs

- `0x1800021c3`: `CACHE_URL`

## pseudocode

```c
__int64 __fastcall SetupCacheInvalidator(struct IHttpContext *a1, struct _HTTP_CACHE_POLICY *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  unsigned int v5; // r12d
  __int64 v6; // rax
  const unsigned __int16 *v7; // r14
  const unsigned __int16 *v8; // r13
  const unsigned __int16 *v9; // r15
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(struct IHttpContext *, const char *, const unsigned __int16 **, unsigned int *); // rax
  int CacheKey; // ebx
  wchar_t *Str; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  int Key; // eax
  UL_RESPONSE_CACHE_ENTRY *v18; // rdi
  const unsigned __int16 *v19; // rax
  __int64 v20; // rax
  struct _HTTP_CACHE_POLICY *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rax
  UL_RESPONSE_CACHE_ENTRY *v27; // rax
  __int64 v28; // rbx
  UL_RESPONSE_CACHE_ENTRY *v29; // rax
  int v30; // eax
  int inserted; // eax
  _DWORD *v32; // r8
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v36; // [rsp+38h] [rbp-C8h] BYREF
  UL_RESPONSE_CACHE_ENTRY *v37; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v38; // [rsp+48h] [rbp-B8h] BYREF
  struct _HTTP_CACHE_POLICY *v39; // [rsp+50h] [rbp-B0h]
  _BYTE v40[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v41[184]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v42[184]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v43[184]; // [rsp+200h] [rbp+100h] BYREF
  unsigned int v44; // [rsp+2B8h] [rbp+1B8h]
  unsigned __int16 v45[1024]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v39 = a2;
  memset_0(v45, 0, sizeof(v45));
  STRU::STRU((STRU *)v40, v45, 0x400u);
  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 176LL))(v3);
  v6 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a1)(a1);
  v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  v8 = *(const unsigned __int16 **)(v4 + 88);
  v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a1 + 184LL))(
                                   a1,
                                   0);
  UL_RESPONSE_CACHE_KEY::UL_RESPONSE_CACHE_KEY((UL_RESPONSE_CACHE_KEY *)v41);
  v10 = *(_QWORD *)a1;
  v35 = 0;
  v38 = 0;
  v11 = *(__int64 (__fastcall **)(struct IHttpContext *, const char *, const unsigned __int16 **, unsigned int *))(v10 + 128);
  v36 = 0;
  CacheKey = v11(a1, "CACHE_URL", &v38, &v36);
  if ( CacheKey >= 0 )
  {
    CacheKey = STRU::Copy((STRU *)v40, v38, v36);
    if ( CacheKey >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v40);
      _wcsupr(Str);
      v44 = v5;
      CacheKey = STRU::Copy((STRU *)v41, v8);
      if ( CacheKey >= 0 )
      {
        CacheKey = STRU::Copy((STRU *)v42, v7);
        if ( CacheKey >= 0 )
        {
          CacheKey = STRU::Copy((STRU *)v43, v9);
          if ( CacheKey >= 0 )
          {
            v15 = STRU::QueryStr((STRU *)v41);
            _wcsupr(v15);
            v16 = STRU::QueryStr((STRU *)v43);
            _wcsupr(v16);
            while ( 1 )
            {
              v37 = 0;
              Key = CLKRHashTable::FindKey(g_pUlCache, v41, &v37);
              v18 = v37;
              if ( !Key )
              {
                *((_DWORD *)v37 + 190) = 2;
                v19 = STRU::QueryStr((STRU *)v40);
                CacheKey = UL_RESPONSE_CACHE_ENTRY::AddInvalidationUrl(v18, v19);
LABEL_12:
                if ( !v18 )
                  goto LABEL_2;
LABEL_13:
                UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(v18);
                goto LABEL_2;
              }
              v20 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 208LL))(a1);
              v21 = v39;
              if ( v20
                || (v32 = g_pOutputCache, v39->Policy != HttpCachePolicyUserInvalidates)
                && v39->SecondsToLive <= *((_DWORD *)g_pOutputCache + 28) / 0x3E8u )
              {
                if ( v39->Policy == HttpCachePolicyUserInvalidates )
                {
                  v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
                  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
                  v24 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
                  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24) )
                  {
                    v33 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
                    v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                    v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 56LL))(v34);
                  }
                  else
                  {
                    v25 = 0;
                  }
                  CacheKey = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64, __int64, __int64 *))(*(_QWORD *)g_pGlobalInfo + 192LL))(
                               g_pGlobalInfo,
                               v23,
                               v25,
                               &v35);
                  if ( CacheKey < 0 )
                    goto LABEL_12;
                  v26 = (**(__int64 (__fastcall ***)(__int64))v35)(v35);
                  CacheKey = (*(__int64 (__fastcall **)(__int64, void *, void *))(*(_QWORD *)v26 + 8LL))(
                               v26,
                               g_pMonitorStoredContext,
                               g_pModuleId);
                  if ( (int)(CacheKey + 0x80000000) >= 0 && CacheKey != -2147024811 )
                    goto LABEL_12;
                }
              }
              else
              {
                v39->Policy = HttpCachePolicyTimeToLive;
                v21->SecondsToLive = v32[28] / 0x3E8u;
              }
              v27 = (UL_RESPONSE_CACHE_ENTRY *)operator new(0x320u);
              if ( !v27 || (v18 = UL_RESPONSE_CACHE_ENTRY::UL_RESPONSE_CACHE_ENTRY(v27)) == 0 )
              {
                CacheKey = -2147024888;
                goto LABEL_2;
              }
              v28 = v35;
              v29 = (UL_RESPONSE_CACHE_ENTRY *)STRU::QueryStr((STRU *)v40);
              *((_QWORD *)v18 + 99) = v28;
              v37 = v29;
              CacheKey = UL_RESPONSE_CACHE_KEY::CreateCacheKey(
                           (UL_RESPONSE_CACHE_ENTRY *)((char *)v18 + 16),
                           v8,
                           v5,
                           v7,
                           v9);
              if ( CacheKey < 0 )
              {
                v35 = 0;
                UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(v18);
                goto LABEL_2;
              }
              v30 = STRU::Copy((UL_RESPONSE_CACHE_ENTRY *)((char *)v18 + 576), (const unsigned __int16 *)v37);
              v35 = 0;
              CacheKey = v30;
              if ( v30 < 0 )
                goto LABEL_13;
              inserted = CLKRHashTable::InsertRecord(g_pUlCache, v18, 0);
              if ( inserted != 1 )
                break;
              UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(v18);
            }
            if ( inserted )
              CacheKey = -2147467259;
            else
              CacheKey = 0;
            UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(v18);
          }
        }
      }
    }
  }
LABEL_2:
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
    v35 = 0;
  }
  STRU::~STRU((STRU *)v43);
  STRU::~STRU((STRU *)v42);
  STRU::~STRU((STRU *)v41);
  STRU::~STRU((STRU *)v40);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x1800020d0  mov     [rsp-8+arg_10], rbx
0x1800020d5  push    rbp
0x1800020d6  push    rsi
0x1800020d7  push    rdi
0x1800020d8  push    r12
0x1800020da  push    r13
0x1800020dc  push    r14
0x1800020de  push    r15
0x1800020e0  lea     rbp, [rsp-9D0h]
0x1800020e8  sub     rsp, 0AD0h
0x1800020ef  mov     rax, cs:__security_cookie
0x1800020f6  xor     rax, rsp
0x1800020f9  mov     [rbp+0A00h+var_40], rax
0x180002100  mov     [rsp+0B00h+var_AB0], rdx
0x180002105  mov     rsi, rcx
0x180002108  xor     edx, edx; Val
0x18000210a  lea     rcx, [rbp+0A00h+var_840]; void *
0x180002111  mov     r8d, 800h; Size
0x180002117  call    memset_0
0x18000211c  mov     r8d, 400h
0x180002122  lea     rdx, [rbp+0A00h+var_840]
0x180002129  lea     rcx, [rsp+0B00h+var_AA8]
0x18000212e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002134  mov     rax, [rsi]
0x180002137  mov     rcx, rsi
0x18000213a  mov     rax, [rax+18h]
0x18000213e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002143  mov     rbx, rax
0x180002146  mov     rcx, [rax]
0x180002149  mov     rax, [rcx+8]
0x18000214d  mov     rcx, rbx
0x180002150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002155  mov     rcx, [rbx]
0x180002158  mov     rdi, rax
0x18000215b  mov     rax, [rcx+0B0h]
0x180002162  mov     rcx, rbx
0x180002165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000216a  mov     rcx, [rsi]
0x18000216d  mov     r12d, eax
0x180002170  mov     rax, [rcx]
0x180002173  mov     rcx, rsi
0x180002176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000217b  mov     rdx, rax
0x18000217e  mov     rcx, [rax]
0x180002181  mov     rax, [rcx+8]
0x180002185  mov     rcx, rdx
0x180002188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000218d  mov     rcx, [rsi]
0x180002190  mov     r14, rax
0x180002193  mov     r13, [rdi+58h]
0x180002197  xor     edx, edx
0x180002199  mov     rax, [rcx+0B8h]
0x1800021a0  mov     rcx, rsi
0x1800021a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a8  lea     rcx, [rbp+0A00h+var_A70]; this
0x1800021ac  mov     r15, rax
0x1800021af  call    ??0UL_RESPONSE_CACHE_KEY@@QEAA@XZ; UL_RESPONSE_CACHE_KEY::UL_RESPONSE_CACHE_KEY(void)
0x1800021b4  mov     rcx, [rsi]
0x1800021b7  lea     r9, [rsp+0B00h+var_AC8]
0x1800021bc  xor     edi, edi
0x1800021be  lea     r8, [rsp+0B00h+var_AB8]
0x1800021c3  lea     rdx, aCacheUrl; "CACHE_URL"
0x1800021ca  mov     [rsp+0B00h+var_AD0], rdi
0x1800021cf  mov     [rsp+0B00h+var_AB8], rdi
0x1800021d4  mov     rax, [rcx+80h]
0x1800021db  mov     rcx, rsi
0x1800021de  mov     [rsp+0B00h+var_AC8], edi
0x1800021e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021e7  mov     ebx, eax
0x1800021e9  test    eax, eax
0x1800021eb  jns     short loc_180002260
0x1800021ed  mov     rcx, [rsp+0B00h+var_AD0]
0x1800021f2  test    rcx, rcx
0x1800021f5  jz      short loc_180002208
0x1800021f7  mov     rax, [rcx]
0x1800021fa  mov     rax, [rax+8]
0x1800021fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002203  mov     [rsp+0B00h+var_AD0], rdi
0x180002208  lea     rcx, [rbp+0A00h+var_900]
0x18000220f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002215  lea     rcx, [rbp+0A00h+var_9B8]
0x180002219  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000221f  lea     rcx, [rbp+0A00h+var_A70]
0x180002223  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002229  lea     rcx, [rsp+0B00h+var_AA8]
0x18000222e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002234  mov     eax, ebx
0x180002236  mov     rcx, [rbp+0A00h+var_40]
0x18000223d  xor     rcx, rsp; StackCookie
0x180002240  call    __security_check_cookie
0x180002245  mov     rbx, [rsp+0B00h+arg_10]
0x18000224d  add     rsp, 0AD0h
0x180002254  pop     r15
0x180002256  pop     r14
0x180002258  pop     r13
0x18000225a  pop     r12
0x18000225c  pop     rdi
0x18000225d  pop     rsi
0x18000225e  pop     rbp
0x18000225f  retn
0x180002260  mov     r8d, [rsp+0B00h+var_AC8]
0x180002265  lea     rcx, [rsp+0B00h+var_AA8]
0x18000226a  mov     rdx, [rsp+0B00h+var_AB8]
0x18000226f  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180002275  mov     ebx, eax
0x180002277  test    eax, eax
0x180002279  js      loc_1800021ED
0x18000227f  lea     rcx, [rsp+0B00h+var_AA8]
0x180002284  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000228a  mov     rcx, rax; String
0x18000228d  call    cs:__imp__wcsupr
0x180002293  mov     rdx, r13
0x180002296  mov     [rbp+0A00h+var_848], r12d
0x18000229d  lea     rcx, [rbp+0A00h+var_A70]
0x1800022a1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800022a7  mov     ebx, eax
0x1800022a9  test    eax, eax
0x1800022ab  js      loc_180002500
0x1800022b1  mov     rdx, r14
0x1800022b4  lea     rcx, [rbp+0A00h+var_9B8]
0x1800022b8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800022be  mov     ebx, eax
0x1800022c0  test    eax, eax
0x1800022c2  js      loc_180002500
0x1800022c8  mov     rdx, r15
0x1800022cb  lea     rcx, [rbp+0A00h+var_900]
0x1800022d2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800022d8  mov     ebx, eax
0x1800022da  test    eax, eax
0x1800022dc  js      loc_180002500
0x1800022e2  lea     rcx, [rbp+0A00h+var_A70]
0x1800022e6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800022ec  mov     rcx, rax; String
0x1800022ef  call    cs:__imp__wcsupr
0x1800022f5  lea     rcx, [rbp+0A00h+var_900]
0x1800022fc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002302  mov     rcx, rax; String
0x180002305  call    cs:__imp__wcsupr
0x18000230b  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x180002312  lea     r8, [rsp+0B00h+var_AC0]
0x180002317  lea     rdx, [rbp+0A00h+var_A70]
0x18000231b  mov     [rsp+0B00h+var_AC0], rdi
0x180002320  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180002326  mov     rdi, [rsp+0B00h+var_AC0]
0x18000232b  test    eax, eax
0x18000232d  jnz     short loc_180002365
0x18000232f  lea     rcx, [rsp+0B00h+var_AA8]
0x180002334  mov     dword ptr [rdi+2F8h], 2
0x18000233e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002344  mov     rdx, rax; unsigned __int16 *
0x180002347  mov     rcx, rdi; this
0x18000234a  call    ?AddInvalidationUrl@UL_RESPONSE_CACHE_ENTRY@@QEAAJPEBG@Z; UL_RESPONSE_CACHE_ENTRY::AddInvalidationUrl(ushort const *)
0x18000234f  mov     ebx, eax
0x180002351  test    rdi, rdi
0x180002354  jz      short loc_18000235E
0x180002356  mov     rcx, rdi; this
0x180002359  call    ?DereferenceCacheData@UL_RESPONSE_CACHE_ENTRY@@QEAAXXZ; UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(void)
0x18000235e  xor     edi, edi
0x180002360  jmp     loc_1800021ED
0x180002365  mov     rax, [rsi]
0x180002368  mov     rcx, rsi
0x18000236b  mov     rax, [rax+0D0h]
0x180002372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002377  mov     rcx, [rsp+0B00h+var_AB0]
0x18000237c  test    rax, rax
0x18000237f  jz      loc_180002565
0x180002385  cmp     dword ptr [rcx], 1
0x180002388  jnz     loc_18000244E
0x18000238e  mov     rax, [rsi]
0x180002391  mov     rcx, rsi
0x180002394  mov     rax, [rax+0A0h]
0x18000239b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a0  mov     rdx, rax
0x1800023a3  mov     rcx, [rax]
0x1800023a6  mov     rax, [rcx+8]
0x1800023aa  mov     rcx, rdx
0x1800023ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023b2  mov     rcx, [rsi]
0x1800023b5  mov     rbx, rax
0x1800023b8  mov     rax, [rcx+0A0h]
0x1800023bf  mov     rcx, rsi
0x1800023c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c7  mov     rdx, rax
0x1800023ca  mov     rcx, [rax]
0x1800023cd  mov     rax, [rcx+10h]
0x1800023d1  mov     rcx, rdx
0x1800023d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d9  test    rax, rax
0x1800023dc  jnz     loc_1800025A0
0x1800023e2  xor     r8d, r8d
0x1800023e5  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800023ec  lea     r9, [rsp+0B00h+var_AD0]
0x1800023f1  mov     rdx, [rcx]
0x1800023f4  mov     rax, [rdx+0C0h]
0x1800023fb  mov     rdx, rbx
0x1800023fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002403  mov     ebx, eax
0x180002405  test    eax, eax
0x180002407  js      loc_180002351
0x18000240d  mov     rcx, [rsp+0B00h+var_AD0]
0x180002412  mov     rax, [rcx]
0x180002415  mov     rax, [rax]
0x180002418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000241d  mov     r8, cs:?g_pModuleId@@3PEAXEA; void * g_pModuleId
0x180002424  mov     r9, rax
0x180002427  mov     rdx, cs:?g_pMonitorStoredContext@@3PEAVMonitorStoredContext@@EA; MonitorStoredContext * g_pMonitorStoredContext
0x18000242e  mov     rcx, [rax]
0x180002431  mov     rax, [rcx+8]
0x180002435  mov     rcx, r9
0x180002438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000243d  mov     ecx, 80000000h
0x180002442  mov     ebx, eax
0x180002444  add     eax, ecx
0x180002446  test    ecx, eax
0x180002448  jz      loc_180002525
0x18000244e  mov     ecx, 320h; Size
0x180002453  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002458  test    rax, rax
0x18000245b  jz      loc_180002536
0x180002461  mov     rcx, rax; this
0x180002464  call    ??0UL_RESPONSE_CACHE_ENTRY@@QEAA@XZ; UL_RESPONSE_CACHE_ENTRY::UL_RESPONSE_CACHE_ENTRY(void)
0x180002469  mov     rdi, rax
0x18000246c  test    rax, rax
0x18000246f  jz      loc_180002536
0x180002475  mov     rbx, [rsp+0B00h+var_AD0]
0x18000247a  lea     rcx, [rsp+0B00h+var_AA8]
0x18000247f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002485  lea     rcx, [rdi+10h]; this
0x180002489  mov     [rdi+318h], rbx
0x180002490  mov     r9, r14; unsigned __int16 *
0x180002493  mov     [rsp+0B00h+var_AC0], rax
0x180002498  mov     r8d, r12d; unsigned int
0x18000249b  mov     [rsp+0B00h+var_AE0], r15; unsigned __int16 *
0x1800024a0  mov     rdx, r13; unsigned __int16 *
0x1800024a3  call    ?CreateCacheKey@UL_RESPONSE_CACHE_KEY@@QEAAJPEBGK00@Z; UL_RESPONSE_CACHE_KEY::CreateCacheKey(ushort const *,ulong,ushort const *,ushort const *)
0x1800024a8  mov     ebx, eax
0x1800024aa  test    eax, eax
0x1800024ac  js      short loc_18000250D
0x1800024ae  mov     rdx, [rsp+0B00h+var_AC0]
0x1800024b3  lea     rcx, [rdi+240h]
0x1800024ba  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800024c0  mov     [rsp+0B00h+var_AD0], 0
0x1800024c9  mov     ebx, eax
0x1800024cb  test    eax, eax
0x1800024cd  js      loc_180002356
0x1800024d3  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x1800024da  xor     r8d, r8d
0x1800024dd  mov     rdx, rdi
0x1800024e0  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800024e6  cmp     eax, 1
0x1800024e9  jz      short loc_180002556
0x1800024eb  test    eax, eax
0x1800024ed  jnz     short loc_180002542
0x1800024ef  mov     rcx, rdi; this
0x1800024f2  xor     ebx, ebx
0x1800024f4  call    ?DereferenceCacheData@UL_RESPONSE_CACHE_ENTRY@@QEAAXXZ; UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(void)
0x1800024f9  xor     edi, edi
0x1800024fb  jmp     loc_1800021ED
0x180002500  test    ebx, ebx
0x180002502  jns     loc_18000230B
0x180002508  jmp     loc_1800021ED
0x18000250d  mov     rcx, rdi; this
0x180002510  mov     [rsp+0B00h+var_AD0], 0
0x180002519  call    ?DereferenceCacheData@UL_RESPONSE_CACHE_ENTRY@@QEAAXXZ; UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(void)
0x18000251e  xor     edi, edi
0x180002520  jmp     loc_1800021ED
0x180002525  cmp     ebx, 80070055h
0x18000252b  jz      loc_18000244E
0x180002531  jmp     loc_180002351
0x180002536  mov     ebx, 80070008h
0x18000253b  xor     edi, edi
0x18000253d  jmp     loc_1800021ED
0x180002542  mov     rcx, rdi; this
0x180002545  mov     ebx, 80004005h
0x18000254a  call    ?DereferenceCacheData@UL_RESPONSE_CACHE_ENTRY@@QEAAXXZ; UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(void)
0x18000254f  xor     edi, edi
0x180002551  jmp     loc_1800021ED
0x180002556  mov     rcx, rdi; this
0x180002559  call    ?DereferenceCacheData@UL_RESPONSE_CACHE_ENTRY@@QEAAXXZ; UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(void)
0x18000255e  xor     edi, edi
0x180002560  jmp     loc_18000230B
0x180002565  cmp     dword ptr [rcx], 1
0x180002568  mov     r8, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x18000256f  jz      short loc_180002586
0x180002571  mov     eax, 10624DD3h
0x180002576  mul     dword ptr [r8+70h]
0x18000257a  shr     edx, 6
0x18000257d  cmp     [rcx+4], edx
0x180002580  jbe     loc_180002385
0x180002586  mov     eax, 10624DD3h
0x18000258b  mov     dword ptr [rcx], 2
0x180002591  mul     dword ptr [r8+70h]
0x180002595  shr     edx, 6
0x180002598  mov     [rcx+4], edx
0x18000259b  jmp     loc_18000244E
0x1800025a0  mov     rax, [rsi]
0x1800025a3  mov     rcx, rsi
0x1800025a6  mov     rax, [rax+0A0h]
0x1800025ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b2  mov     rdx, rax
  ... truncated ...
```
