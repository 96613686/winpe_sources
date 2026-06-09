# CMapiSession::OpenStore(wchar_t const *,CMapiStore * *,int)

- ea: `0x180033434`
- end: `0x180033889`
- name: `?OpenStore@CMapiSession@@QEAAJPEB_WPEAPEAVCMapiStore@@H@Z`
- size: `1109`
- prototype: `__int64 __fastcall(CMapiSession *__hidden this, const wchar_t *, struct CMapiStore **, int)`
- caller_count: `4`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800229b0`
- `0x180025e80`
- `0x180028374`
- `0x180030ec4`

## callees

- `0x180003fe0`
- `0x180004850`
- `0x1800048c0`
- `0x180005210`
- `0x180006270`
- `0x180029170`
- `0x18002a1e8`
- `0x18002a25c`
- `0x18002ac1c`
- `0x18002d33c`
- `0x18002d71c`
- `0x180032b58`
- `0x180032d48`
- `0x1800330b4`
- `0x180033434`
- `0x180033890`
- `0x180033da0`
- `0x18003d010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x180033805`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x180033805`

## string_xrefs

- `0x180033529`: `OpenStore() because the store is disabled in classic mode (online or offline)`
- `0x18003354b`: `OpenStore() because the store is disabled in classic mode (online or offline)`
- `0x18003381e`: `CMapiSession::OpenStore at least one instance of the store was found but was unavailable`
- `0x180033764`: `OpenStore() will fail because Exchange online is disabled`
- `0x1800337b8`: `CMapiSession::OpenStore Found delegate store but it not available`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMapiSession::OpenStore(CMapiSession *this, const wchar_t *a2, struct CMapiStore **a3, int a4)
{
  int v7; // r13d
  __int64 CachedStore; // rax
  int v10; // ebx
  struct CMapiStore *v11; // rax
  unsigned int v12; // edi
  __int64 v13; // rdx
  int v14; // r12d
  __int64 v15; // rax
  LPSPropValue lpProps; // r13
  int v17; // ecx
  unsigned __int16 *v18; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-91h] BYREF
  int v20; // [rsp+3Ch] [rbp-8Dh]
  __int64 v21; // [rsp+40h] [rbp-89h] BYREF
  LPSRowSet lpRows; // [rsp+48h] [rbp-81h] BYREF
  __int64 v23; // [rsp+50h] [rbp-79h] BYREF
  __int64 v24; // [rsp+58h] [rbp-71h] BYREF
  int v25; // [rsp+60h] [rbp-69h]
  LPBYTE lpb; // [rsp+68h] [rbp-61h]
  _BYTE v27[48]; // [rsp+70h] [rbp-59h] BYREF
  int v28; // [rsp+A0h] [rbp-29h]
  int v29; // [rsp+A8h] [rbp-21h]
  unsigned __int16 *v30; // [rsp+C0h] [rbp-9h] BYREF
  _DWORD v31[4]; // [rsp+D0h] [rbp+7h] BYREF

  v25 = a4;
  v7 = 0;
  if ( !*((_QWORD *)this + 3) )
    return 2147500037LL;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v18,
    a2);
  CachedStore = CMapiSession::FindCachedStore(this, &v18);
  *a3 = (struct CMapiStore *)CachedStore;
  if ( CachedStore )
  {
    if ( *(_QWORD *)(CachedStore + 48) || !*(_DWORD *)(CachedStore + 128) )
    {
      if ( a4 || !*(_DWORD *)(CachedStore + 116) )
      {
        v12 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)CachedStore + 8LL))(CachedStore);
      }
      else
      {
        *a3 = 0;
        v12 = -2147216890;
        CLogger::Info(-2147216890, L"OpenStore() because the store is disabled in classic mode (online or offline)");
      }
LABEL_17:
      ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v18);
      return v12;
    }
    *a3 = 0;
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v24);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v23);
  v10 = CMapiStore::LookupHash(&v18, &v24, &v23);
  if ( v10 )
  {
    if ( !(unsigned int)CMapiSession::OpenAllStores(this) )
    {
      v11 = (struct CMapiStore *)CMapiSession::FindCachedStore(this, &v18);
      *a3 = v11;
      if ( v11 )
      {
        if ( a4 || !*((_DWORD *)v11 + 29) )
        {
          v12 = 0;
          (*(void (__fastcall **)(struct CMapiStore *))(*(_QWORD *)v11 + 8LL))(v11);
        }
        else
        {
          *a3 = 0;
          v12 = -2147216890;
          CLogger::Info(-2147216890, L"OpenStore() because the store is disabled in classic mode (online or offline)");
        }
        ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v23);
        ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v24);
        goto LABEL_17;
      }
    }
    if ( v10 >= 0 )
      v10 = -2147467259;
  }
  else
  {
    v31[0] = 2;
    v31[1] = 268370178;
    v31[2] = 873726210;
    v21 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 3) + 32LL))(
            *((_QWORD *)this + 3),
            0,
            &v21);
    if ( v10 >= 0 )
      v10 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v21 + 56LL))(v21, v31, 2);
    v13 = 0;
    v19 = 0;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v21 + 72LL))(v21, 0, &v19);
      v13 = v19;
      if ( v19 > 0x64 )
      {
        v13 = 100;
        v19 = 100;
      }
    }
    lpRows = 0;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPSRowSet *))(*(_QWORD *)v21 + 152LL))(
              v21,
              v13,
              0,
              &lpRows);
      if ( v10 >= 0 )
      {
        v14 = 0;
        v15 = 0;
        while ( 1 )
        {
          v20 = v15;
          if ( (unsigned int)v15 >= lpRows->cRows )
            break;
          lpProps = lpRows->aRow[v15].lpProps;
          if ( lpProps[1].ulPropTag == 873726210 )
            lpb = lpProps[1].Value.bin.lpb;
          else
            lpb = 0;
          if ( lpProps->ulPropTag == 268370178 )
          {
            CStoreEntryId::CStoreEntryId((CStoreEntryId *)v27);
            v29 = *((_DWORD *)this + 41);
            v10 = CStoreEntryId::InitializeWithHint(
                    (unsigned int)v27,
                    *((_QWORD *)this + 3),
                    (_DWORD)lpb,
                    (_DWORD)lpProps,
                    (__int64)&v18);
            if ( v10 < 0 )
            {
              v10 = 0;
            }
            else if ( v28
                   || !(unsigned int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Compare(
                                       &v30,
                                       (__int64)v18) )
            {
              v7 = 1;
              CMapiSession::ReleaseStore(this, &v18);
              v10 = CMapiSession::OpenStoreInternal(this, v27, a3, 0, 0);
              if ( v10 )
              {
                if ( v10 >= 0 )
                  v10 = -2147467259;
              }
              else if ( v25 || *((_DWORD *)*a3 + 29) == v10 )
              {
                if ( !v28
                  || *a3
                  && !(unsigned int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Compare(
                                      &v18,
                                      *((_QWORD *)*a3 + 5)) )
                {
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
LABEL_56:
                  CStoreEntryId::~CStoreEntryId((CStoreEntryId *)v27);
                  break;
                }
                v10 = -2147467259;
                *a3 = 0;
              }
              else
              {
                *a3 = 0;
                v10 = -2147216890;
                CLogger::Info(-2147216890, L"OpenStore() will fail because Exchange online is disabled");
              }
              if ( !v28 )
                goto LABEL_56;
              if ( (unsigned int)IsSoftError(v10) )
              {
                CLogger::Info(v17, L"CMapiSession::OpenStore Found delegate store but it not available");
                v14 = v10;
              }
            }
            CStoreEntryId::~CStoreEntryId((CStoreEntryId *)v27);
          }
          v15 = (unsigned int)(v20 + 1);
          v7 = 0;
        }
        if ( lpRows )
        {
          FreeProws(lpRows);
          lpRows = 0;
        }
        if ( !v7 )
        {
          if ( v14 >= 0 )
          {
            v10 = -2147221233;
          }
          else
          {
            CLogger::Info(
              v14,
              L"CMapiSession::OpenStore at least one instance of the store was found but was unavailable");
            v10 = v14;
          }
        }
      }
    }
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v21);
  }
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v23);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v24);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180033434  mov     [rsp-8+arg_18], rbx
0x180033439  push    rbp
0x18003343a  push    rsi
0x18003343b  push    rdi
0x18003343c  push    r12
0x18003343e  push    r13
0x180033440  push    r14
0x180033442  push    r15
0x180033444  lea     rbp, [rsp-27h]
0x180033449  sub     rsp, 0F0h
0x180033450  mov     rax, cs:__security_cookie
0x180033457  xor     rax, rsp
0x18003345a  mov     [rbp+57h+var_40], rax
0x18003345e  mov     edi, r9d
0x180033461  mov     [rbp+57h+var_C0], r9d
0x180033465  mov     rsi, r8
0x180033468  mov     r15, rcx
0x18003346b  xor     r13d, r13d
0x18003346e  cmp     [rcx+18h], r13
0x180033472  jnz     short loc_18003347E
0x180033474  mov     eax, 80004005h
0x180033479  jmp     loc_180033862
0x18003347e  lea     rcx, [rsp+120h+var_F0]
0x180033483  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180033488  nop
0x180033489  lea     rdx, [rsp+120h+var_F0]
0x18003348e  mov     rcx, r15
0x180033491  call    ?FindCachedStore@CMapiSession@@AEAAPEAVCMapiStore@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::FindCachedStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180033496  mov     rcx, rax
0x180033499  mov     [rsi], rax
0x18003349c  test    rax, rax
0x18003349f  jz      short loc_1800334BB
0x1800334a1  cmp     [rax+30h], r13
0x1800334a5  jnz     loc_180033539
0x1800334ab  cmp     [rax+80h], r13d
0x1800334b2  jz      loc_180033539
0x1800334b8  mov     [rsi], r13
0x1800334bb  lea     rcx, [rbp+57h+var_C8]
0x1800334bf  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800334c4  nop
0x1800334c5  lea     rcx, [rbp+57h+var_D0]
0x1800334c9  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800334ce  nop
0x1800334cf  lea     r8, [rbp+57h+var_D0]
0x1800334d3  lea     rdx, [rbp+57h+var_C8]
0x1800334d7  lea     rcx, [rsp+120h+var_F0]
0x1800334dc  call    ?LookupHash@CMapiStore@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@00@Z; CMapiStore::LookupHash(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800334e1  mov     ebx, eax
0x1800334e3  test    eax, eax
0x1800334e5  jz      loc_1800335B2
0x1800334eb  mov     rcx, r15; this
0x1800334ee  call    ?OpenAllStores@CMapiSession@@QEAAJXZ; CMapiSession::OpenAllStores(void)
0x1800334f3  test    eax, eax
0x1800334f5  jnz     loc_1800335A1
0x1800334fb  lea     rdx, [rsp+120h+var_F0]
0x180033500  mov     rcx, r15
0x180033503  call    ?FindCachedStore@CMapiSession@@AEAAPEAVCMapiStore@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::FindCachedStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180033508  mov     rcx, rax
0x18003350b  mov     [rsi], rax
0x18003350e  test    rax, rax
0x180033511  jz      loc_1800335A1
0x180033517  test    edi, edi
0x180033519  jnz     short loc_18003357C
0x18003351b  cmp     [rax+74h], r13d
0x18003351f  jz      short loc_18003357C
0x180033521  mov     [rsi], r13
0x180033524  mov     edi, 80041206h
0x180033529  lea     rdx, aOpenstoreBecau; "OpenStore() because the store is disabl"...
0x180033530  mov     ecx, edi; int
0x180033532  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180033537  jmp     short loc_18003358C
0x180033539  test    edi, edi
0x18003353b  jnz     short loc_18003355B
0x18003353d  cmp     [rax+74h], r13d
0x180033541  jz      short loc_18003355B
0x180033543  mov     [rsi], r13
0x180033546  mov     edi, 80041206h
0x18003354b  lea     rdx, aOpenstoreBecau; "OpenStore() because the store is disabl"...
0x180033552  mov     ecx, edi; int
0x180033554  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180033559  jmp     short loc_18003356B
0x18003355b  mov     edi, r13d
0x18003355e  mov     rax, [rax]
0x180033561  mov     rax, [rax+8]
0x180033565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003356a  nop
0x18003356b  lea     rcx, [rsp+120h+var_F0]
0x180033570  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180033575  mov     eax, edi
0x180033577  jmp     loc_180033862
0x18003357c  mov     edi, r13d
0x18003357f  mov     rax, [rax]
0x180033582  mov     rax, [rax+8]
0x180033586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003358b  nop
0x18003358c  lea     rcx, [rbp+57h+var_D0]
0x180033590  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180033595  nop
0x180033596  lea     rcx, [rbp+57h+var_C8]
0x18003359a  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18003359f  jmp     short loc_18003356B
0x1800335a1  mov     r14d, 80004005h
0x1800335a7  test    ebx, ebx
0x1800335a9  cmovns  ebx, r14d
0x1800335ad  jmp     loc_180033842
0x1800335b2  mov     edi, 2
0x1800335b7  mov     [rbp+57h+var_50], edi
0x1800335ba  mov     [rbp+57h+var_4C], 0FFF0102h
0x1800335c1  mov     [rbp+57h+var_48], 34140102h
0x1800335c8  mov     [rsp+120h+var_E0], r13
0x1800335cd  mov     rcx, [r15+18h]
0x1800335d1  mov     rax, [rcx]
0x1800335d4  lea     r8, [rsp+120h+var_E0]
0x1800335d9  xor     edx, edx
0x1800335db  mov     rax, [rax+20h]
0x1800335df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335e4  mov     ebx, eax
0x1800335e6  test    eax, eax
0x1800335e8  js      short loc_180033604
0x1800335ea  mov     rcx, [rsp+120h+var_E0]
0x1800335ef  mov     rax, [rcx]
0x1800335f2  mov     r8d, edi
0x1800335f5  lea     rdx, [rbp+57h+var_50]
0x1800335f9  mov     rax, [rax+38h]
0x1800335fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033602  mov     ebx, eax
0x180033604  mov     edx, r13d
0x180033607  mov     [rsp+120h+var_E8], edx
0x18003360b  test    ebx, ebx
0x18003360d  js      short loc_180033639
0x18003360f  mov     rcx, [rsp+120h+var_E0]
0x180033614  mov     rax, [rcx]
0x180033617  lea     r8, [rsp+120h+var_E8]
0x18003361c  mov     rax, [rax+48h]
0x180033620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033625  mov     ebx, eax
0x180033627  mov     edx, [rsp+120h+var_E8]
0x18003362b  cmp     edx, 64h ; 'd'
0x18003362e  jbe     short loc_180033639
0x180033630  mov     edx, 64h ; 'd'
0x180033635  mov     [rsp+120h+var_E8], edx
0x180033639  mov     [rsp+120h+lpRows], r13
0x18003363e  test    ebx, ebx
0x180033640  js      loc_180033837
0x180033646  mov     rcx, [rsp+120h+var_E0]
0x18003364b  mov     rax, [rcx]
0x18003364e  lea     r9, [rsp+120h+lpRows]
0x180033653  xor     r8d, r8d
0x180033656  mov     rax, [rax+98h]
0x18003365d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033662  mov     ebx, eax
0x180033664  test    eax, eax
0x180033666  js      loc_180033837
0x18003366c  mov     r12d, r13d
0x18003366f  mov     eax, r13d
0x180033672  mov     edi, 80041206h
0x180033677  mov     r14d, 80004005h
0x18003367d  mov     [rsp+120h+var_E4], eax
0x180033681  mov     rcx, [rsp+120h+lpRows]
0x180033686  cmp     eax, [rcx]
0x180033688  jnb     loc_1800337FB
0x18003368e  inc     rax
0x180033691  add     rax, rax
0x180033694  mov     r13, [rcx+rax*8]
0x180033698  cmp     dword ptr [r13+18h], 34140102h
0x1800336a0  jnz     short loc_1800336AC
0x1800336a2  mov     rax, [r13+28h]
0x1800336a6  mov     [rbp+57h+var_B8], rax
0x1800336aa  jmp     short loc_1800336B4
0x1800336ac  mov     [rbp+57h+var_B8], 0
0x1800336b4  cmp     dword ptr [r13+0], 0FFF0102h
0x1800336bc  jnz     loc_1800337D4
0x1800336c2  lea     rcx, [rbp+57h+var_B0]; this
0x1800336c6  call    ??0CStoreEntryId@@QEAA@XZ; CStoreEntryId::CStoreEntryId(void)
0x1800336cb  nop
0x1800336cc  mov     eax, [r15+0A4h]
0x1800336d3  mov     [rbp+57h+var_78], eax
0x1800336d6  lea     rax, [rsp+120h+var_F0]
0x1800336db  mov     [rsp+120h+var_100], rax
0x1800336e0  mov     r9, r13
0x1800336e3  mov     r8, [rbp+57h+var_B8]
0x1800336e7  mov     rdx, [r15+18h]
0x1800336eb  lea     rcx, [rbp+57h+var_B0]
0x1800336ef  call    ?InitializeWithHint@CStoreEntryId@@QEAAJPEAUIMAPISession@@PEAU_MAPIUID@@PEAU_SPropValue@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CStoreEntryId::InitializeWithHint(IMAPISession *,_MAPIUID *,_SPropValue *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800336f4  mov     ebx, eax
0x1800336f6  test    eax, eax
0x1800336f8  js      loc_1800337C9
0x1800336fe  cmp     [rbp+57h+var_80], 0
0x180033702  jnz     short loc_18003371B
0x180033704  mov     rdx, [rsp+120h+var_F0]
0x180033709  lea     rcx, [rbp+57h+var_60]
0x18003370d  call    ?Compare@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAHPEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Compare(wchar_t const *)
0x180033712  nop
0x180033713  test    eax, eax
0x180033715  jnz     loc_1800337CB
0x18003371b  mov     r13d, 1
0x180033721  lea     rdx, [rsp+120h+var_F0]
0x180033726  mov     rcx, r15
0x180033729  call    ?ReleaseStore@CMapiSession@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::ReleaseStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18003372e  mov     dword ptr [rsp+120h+var_100], 0
0x180033736  xor     r9d, r9d
0x180033739  mov     r8, rsi
0x18003373c  lea     rdx, [rbp+57h+var_B0]
0x180033740  mov     rcx, r15
0x180033743  call    ?OpenStoreInternal@CMapiSession@@AEAAJAEAVCStoreEntryId@@PEAPEAVCMapiStore@@PEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiSession::OpenStoreInternal(CStoreEntryId &,CMapiStore * *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x180033748  mov     ebx, eax
0x18003374a  test    eax, eax
0x18003374c  jnz     short loc_1800337A1
0x18003374e  cmp     [rbp+57h+var_C0], eax
0x180033751  jnz     short loc_180033774
0x180033753  mov     rax, [rsi]
0x180033756  cmp     [rax+74h], ebx
0x180033759  jz      short loc_180033774
0x18003375b  mov     qword ptr [rsi], 0
0x180033762  mov     ebx, edi
0x180033764  lea     rdx, aOpenstoreWillF; "OpenStore() will fail because Exchange "...
0x18003376b  mov     ecx, edi; int
0x18003376d  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180033772  jmp     short loc_1800337A7
0x180033774  cmp     [rbp+57h+var_80], 0
0x180033778  jz      short loc_1800337E2
0x18003377a  mov     rdx, [rsi]
0x18003377d  test    rdx, rdx
0x180033780  jz      short loc_180033795
0x180033782  mov     rdx, [rdx+28h]
0x180033786  lea     rcx, [rsp+120h+var_F0]
0x18003378b  call    ?Compare@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAHPEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Compare(wchar_t const *)
0x180033790  nop
0x180033791  test    eax, eax
0x180033793  jz      short loc_1800337E2
0x180033795  mov     ebx, r14d
0x180033798  mov     qword ptr [rsi], 0
0x18003379f  jmp     short loc_1800337A7
0x1800337a1  test    ebx, ebx
0x1800337a3  cmovns  ebx, r14d
0x1800337a7  cmp     [rbp+57h+var_80], 0
0x1800337ab  jz      short loc_1800337F2
0x1800337ad  mov     ecx, ebx; int
0x1800337af  call    ?IsSoftError@@YAHJ@Z; IsSoftError(long)
0x1800337b4  test    eax, eax
0x1800337b6  jz      short loc_1800337CB
0x1800337b8  lea     rdx, aCmapisessionOp_1; "CMapiSession::OpenStore Found delegate "...
0x1800337bf  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x1800337c4  mov     r12d, ebx
0x1800337c7  jmp     short loc_1800337CB
0x1800337c9  xor     ebx, ebx
0x1800337cb  lea     rcx, [rbp+57h+var_B0]; this
0x1800337cf  call    ??1CStoreEntryId@@QEAA@XZ; CStoreEntryId::~CStoreEntryId(void)
0x1800337d4  mov     eax, [rsp+120h+var_E4]
0x1800337d8  inc     eax
0x1800337da  xor     r13d, r13d
0x1800337dd  jmp     loc_18003367D
0x1800337e2  mov     rcx, [rsi]
0x1800337e5  mov     rax, [rcx]
0x1800337e8  mov     rax, [rax+8]
0x1800337ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337f1  nop
0x1800337f2  lea     rcx, [rbp+57h+var_B0]; this
0x1800337f6  call    ??1CStoreEntryId@@QEAA@XZ; CStoreEntryId::~CStoreEntryId(void)
0x1800337fb  mov     rcx, [rsp+120h+lpRows]; lpRows
0x180033800  test    rcx, rcx
0x180033803  jz      short loc_180033814
0x180033805  call    cs:__imp_FreeProws
0x18003380b  mov     [rsp+120h+lpRows], 0
0x180033814  test    r13d, r13d
0x180033817  jnz     short loc_180033837
0x180033819  test    r12d, r12d
0x18003381c  jns     short loc_180033832
0x18003381e  lea     rdx, aCmapisessionOp_0; "CMapiSession::OpenStore at least one in"...
0x180033825  mov     ecx, r12d; int
0x180033828  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18003382d  mov     ebx, r12d
0x180033830  jmp     short loc_180033837
0x180033832  mov     ebx, 8004010Fh
0x180033837  lea     rcx, [rsp+120h+var_E0]
0x18003383c  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180033841  nop
0x180033842  lea     rcx, [rbp+57h+var_D0]
0x180033846  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18003384b  nop
0x18003384c  lea     rcx, [rbp+57h+var_C8]
0x180033850  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180033855  nop
0x180033856  lea     rcx, [rsp+120h+var_F0]
0x18003385b  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180033860  mov     eax, ebx
0x180033862  mov     rcx, [rbp+57h+var_40]
0x180033866  xor     rcx, rsp; StackCookie
0x180033869  call    __security_check_cookie
0x18003386e  mov     rbx, [rsp+120h+arg_18]
0x180033876  add     rsp, 0F0h
0x18003387d  pop     r15
0x18003387f  pop     r14
0x180033881  pop     r13
0x180033883  pop     r12
0x180033885  pop     rdi
0x180033886  pop     rsi
0x180033887  pop     rbp
0x180033888  retn
```
