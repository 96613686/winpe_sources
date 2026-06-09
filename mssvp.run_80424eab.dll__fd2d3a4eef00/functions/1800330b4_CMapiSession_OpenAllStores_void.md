# CMapiSession::OpenAllStores(void)

- ea: `0x1800330b4`
- end: `0x18003342c`
- name: `?OpenAllStores@CMapiSession@@QEAAJXZ`
- size: `888`
- prototype: `__int64 __fastcall(CMapiSession *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180033434`

## callees

- `0x1800031c0`
- `0x180003fe0`
- `0x180004058`
- `0x180004850`
- `0x1800048c0`
- `0x180004d40`
- `0x180005210`
- `0x180006270`
- `0x180018758`
- `0x180019084`
- `0x180022110`
- `0x18002a1e8`
- `0x18002a25c`
- `0x18002a8ec`
- `0x18002ede8`
- `0x18002ef70`
- `0x18002f7f8`
- `0x1800330b4`
- `0x180033890`
- `0x18003d010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800333e5`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800333e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMapiSession::OpenAllStores(CMapiSession *this)
{
  int v2; // ebx
  __int64 v3; // rdx
  ULONG v4; // r15d
  struct _SRowSet *v5; // rbx
  struct _SPropValue *lpProps; // rsi
  struct _MAPIUID *v7; // r14
  LPSPropValue v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  enum POLICY_RESULT_ID *v12; // r8
  struct CMapiStore *v13; // rcx
  BOOL v14; // ebx
  __int64 v15; // rax
  _QWORD *v16; // rcx
  int *v17; // rbx
  __int64 v18; // rdi
  unsigned int v20; // [rsp+30h] [rbp-F8h] BYREF
  struct CMapiStore *v21; // [rsp+38h] [rbp-F0h] BYREF
  _BYTE v22[8]; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v23; // [rsp+48h] [rbp-E0h] BYREF
  LPSRowSet lpRows; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+58h] [rbp-D0h] BYREF
  _BYTE v26[8]; // [rsp+60h] [rbp-C8h] BYREF
  ATL::CAtlException *v27; // [rsp+68h] [rbp-C0h] BYREF
  unsigned int v28[13]; // [rsp+70h] [rbp-B8h] BYREF
  int v29; // [rsp+A4h] [rbp-84h]
  __int64 v30; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v31; // [rsp+C8h] [rbp-60h]
  _DWORD v32[6]; // [rsp+D0h] [rbp-58h] BYREF
  void *retaddr; // [rsp+128h] [rbp+0h]

  try
  {
    v32[0] = 5;
    v32[1] = 268370178;
    v32[2] = 805896195;
    v32[3] = 873726210;
    v32[4] = 805371935;
    v32[5] = 805371934;
    v23 = 0;
    v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 3) + 32LL))(
           *((_QWORD *)this + 3),
           0,
           &v23);
    if ( v2 >= 0 )
      v2 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v23 + 56LL))(v23, v32, 2);
    v3 = 0;
    v20 = 0;
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v23 + 72LL))(v23, 0, &v20);
      v3 = v20;
      if ( v20 > 0x64 )
      {
        v3 = 100;
        v20 = 100;
      }
    }
    lpRows = 0;
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPSRowSet *))(*(_QWORD *)v23 + 152LL))(
             v23,
             v3,
             0,
             &lpRows);
      if ( v2 >= 0 )
      {
        v4 = 0;
        v5 = lpRows;
        while ( 1 )
        {
          if ( v4 >= v5->cRows )
          {
            FreeProws(v5);
            lpRows = 0;
            v2 = 0;
            goto LABEL_39;
          }
          lpProps = v5->aRow[v4].lpProps;
          v7 = lpProps[2].ulPropTag == 873726210 ? (struct _MAPIUID *)lpProps[2].Value.bin.lpb : 0LL;
          if ( lpProps->ulPropTag == 268370178 )
            break;
LABEL_37:
          ++v4;
        }
        CStoreEntryId::CStoreEntryId((CStoreEntryId *)v28);
        if ( (int)CStoreEntryId::Initialize((CStoreEntryId *)v28, *((struct IMAPISession **)this + 3), v7, lpProps) < 0 )
        {
LABEL_36:
          CStoreEntryId::~CStoreEntryId((CStoreEntryId *)v28);
          v5 = lpRows;
          goto LABEL_37;
        }
        v21 = 0;
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
          v22,
          &lParam);
        v8 = v5->aRow[v4].lpProps;
        if ( LOWORD(v8[3].ulPropTag) == 10 )
        {
          if ( LOWORD(v8[4].ulPropTag) == 10 )
          {
LABEL_35:
            ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v22);
            goto LABEL_36;
          }
          ((void (__fastcall *)(_QWORD, _QWORD))ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=)(
            v22,
            (CURRENCY)v8[4].Value.cur.int64);
        }
        else
        {
          v9 = ocslen(v8[3].Value.lpszW);
          ATL::CSimpleStringT<wchar_t,0>::SetString(v22, v10, v9);
        }
        v11 = CMapiSession::OpenStoreInternal((__int64)this, v28, &v21, (__int64)v22, 1);
        v13 = v21;
        if ( (!v21 || v11 >= 0) && v29 )
        {
          if ( !v21 )
            goto LABEL_29;
          LODWORD(v21) = 0;
          if ( (int)CMapiSupport::CheckPolicyOnStore(v13, (int *)&v21, v12) < 0 || !(_DWORD)v21 )
            goto LABEL_29;
          v14 = 1;
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v25);
          if ( !(unsigned int)CMapiSupport::GetInstalledOutlookVersion(&v25) )
          {
            v15 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                    v26,
                    &v25);
            v14 = CMapiSupport::ConvertToIntVersion(v15) > 0xB000000000000LL;
          }
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v25);
          if ( v14 )
          {
LABEL_29:
            v21 = 0;
            v28[10] = 1;
            v29 = 1;
            v16 = (_QWORD *)(v31 - 24);
            v17 = (int *)(v30 - 24);
            if ( v31 - 24 != v30 - 24 )
            {
              if ( v17[4] >= 0 && *v16 == *(_QWORD *)v17 )
              {
                v18 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v16);
                ATL::CStringData::Release((ATL::CStringData *)v17);
                v30 = v18 + 24;
              }
              else
              {
                ATL::CSimpleStringT<wchar_t,0>::SetString(&v30, v31, *(unsigned int *)(v31 - 16));
              }
            }
            CMapiSession::OpenStoreInternal((__int64)this, v28, &v21, (__int64)v22, 1);
          }
        }
        goto LABEL_35;
      }
    }
LABEL_39:
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v23);
  }
  catch ( ATL::CAtlException *v27 )
  {
    v20 = *(_DWORD *)v27;
    CLogger::Error(v20, L"CMapiSession::OpenAllStores threw an exception");
    return v20;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<0>(
      retaddr,
      838,
      "onecoreuap\\base\\appmodel\\search\\common\\mapilib\\mapisession.cxx");
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800330b4  mov     r11, rsp
0x1800330b7  push    rbx
0x1800330b8  push    rsi
0x1800330b9  push    rdi
0x1800330ba  push    r13
0x1800330bc  push    r14
0x1800330be  push    r15
0x1800330c0  sub     rsp, 0F8h
0x1800330c7  mov     rax, cs:__security_cookie
0x1800330ce  xor     rax, rsp
0x1800330d1  mov     [rsp+128h+var_40], rax
0x1800330d9  mov     r13, rcx
0x1800330dc  mov     dword ptr [r11-58h], 5
0x1800330e4  mov     dword ptr [r11-54h], 0FFF0102h
0x1800330ec  mov     dword ptr [r11-50h], 30090003h
0x1800330f4  mov     dword ptr [r11-4Ch], 34140102h
0x1800330fc  mov     dword ptr [r11-48h], 3001001Fh
0x180033104  mov     dword ptr [r11-44h], 3001001Eh
0x18003310c  mov     [rsp+128h+var_E0], 0
0x180033115  mov     rcx, [rcx+18h]
0x180033119  mov     rax, [rcx]
0x18003311c  lea     r8, [rsp+128h+var_E0]
0x180033121  xor     edx, edx
0x180033123  mov     rax, [rax+20h]
0x180033127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003312c  mov     ebx, eax
0x18003312e  test    eax, eax
0x180033130  js      short loc_180033153
0x180033132  mov     rcx, [rsp+128h+var_E0]
0x180033137  mov     rax, [rcx]
0x18003313a  mov     r8d, 2
0x180033140  lea     rdx, [rsp+128h+var_58]
0x180033148  mov     rax, [rax+38h]
0x18003314c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033151  mov     ebx, eax
0x180033153  xor     edx, edx
0x180033155  mov     [rsp+128h+var_F8], edx
0x180033159  test    ebx, ebx
0x18003315b  js      short loc_180033187
0x18003315d  mov     rcx, [rsp+128h+var_E0]
0x180033162  mov     rax, [rcx]
0x180033165  lea     r8, [rsp+128h+var_F8]
0x18003316a  mov     rax, [rax+48h]
0x18003316e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033173  mov     ebx, eax
0x180033175  mov     edx, [rsp+128h+var_F8]
0x180033179  cmp     edx, 64h ; 'd'
0x18003317c  jbe     short loc_180033187
0x18003317e  mov     edx, 64h ; 'd'
0x180033183  mov     [rsp+128h+var_F8], edx
0x180033187  mov     [rsp+128h+lpRows], 0
0x180033190  test    ebx, ebx
0x180033192  js      loc_1800333F6
0x180033198  mov     rcx, [rsp+128h+var_E0]
0x18003319d  mov     rax, [rcx]
0x1800331a0  lea     r9, [rsp+128h+lpRows]
0x1800331a5  xor     r8d, r8d
0x1800331a8  mov     rax, [rax+98h]
0x1800331af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331b4  mov     ebx, eax
0x1800331b6  test    eax, eax
0x1800331b8  js      loc_1800333F6
0x1800331be  xor     r15d, r15d
0x1800331c1  mov     rbx, [rsp+128h+lpRows]
0x1800331c6  cmp     r15d, [rbx]
0x1800331c9  jnb     loc_1800333E2
0x1800331cf  mov     edi, r15d
0x1800331d2  inc     rdi
0x1800331d5  add     rdi, rdi
0x1800331d8  mov     rsi, [rbx+rdi*8]
0x1800331dc  cmp     dword ptr [rsi+30h], 34140102h
0x1800331e3  jnz     short loc_1800331EB
0x1800331e5  mov     r14, [rsi+40h]
0x1800331e9  jmp     short loc_1800331EE
0x1800331eb  xor     r14d, r14d
0x1800331ee  cmp     dword ptr [rsi], 0FFF0102h
0x1800331f4  jnz     loc_1800333DA
0x1800331fa  lea     rcx, [rsp+128h+var_B8]; this
0x1800331ff  call    ??0CStoreEntryId@@QEAA@XZ; CStoreEntryId::CStoreEntryId(void)
0x180033204  nop
0x180033205  mov     r9, rsi; struct _SPropValue *
0x180033208  mov     r8, r14; struct _MAPIUID *
0x18003320b  mov     rdx, [r13+18h]; struct IMAPISession *
0x18003320f  lea     rcx, [rsp+128h+var_B8]; this
0x180033214  call    ?Initialize@CStoreEntryId@@QEAAJPEAUIMAPISession@@PEAU_MAPIUID@@PEAU_SPropValue@@@Z; CStoreEntryId::Initialize(IMAPISession *,_MAPIUID *,_SPropValue *)
0x180033219  test    eax, eax
0x18003321b  js      loc_1800333CB
0x180033221  mov     [rsp+128h+var_F0], 0
0x18003322a  lea     rdx, lParam
0x180033231  lea     rcx, [rsp+128h+var_E8]
0x180033236  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18003323b  nop
0x18003323c  mov     rcx, [rbx+rdi*8]
0x180033240  cmp     word ptr [rcx+48h], 0Ah
0x180033245  jnz     short loc_180033262
0x180033247  cmp     word ptr [rcx+60h], 0Ah
0x18003324c  jz      loc_1800333C0
0x180033252  mov     rdx, [rcx+68h]
0x180033256  lea     rcx, [rsp+128h+var_E8]
0x18003325b  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(char const *)
0x180033260  jmp     short loc_18003327B
0x180033262  mov     rcx, [rcx+50h]; wchar_t *
0x180033266  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18003326b  mov     r8d, eax
0x18003326e  mov     rdx, rcx
0x180033271  lea     rcx, [rsp+128h+var_E8]
0x180033276  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18003327b  mov     esi, 1
0x180033280  mov     [rsp+128h+var_108], esi
0x180033284  lea     r9, [rsp+128h+var_E8]
0x180033289  lea     r8, [rsp+128h+var_F0]
0x18003328e  lea     rdx, [rsp+128h+var_B8]
0x180033293  mov     rcx, r13
0x180033296  call    ?OpenStoreInternal@CMapiSession@@AEAAJAEAVCStoreEntryId@@PEAPEAVCMapiStore@@PEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiSession::OpenStoreInternal(CStoreEntryId &,CMapiStore * *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x18003329b  mov     rcx, [rsp+128h+var_F0]; struct CMapiStore *
0x1800332a0  test    rcx, rcx
0x1800332a3  jz      short loc_1800332AD
0x1800332a5  test    eax, eax
0x1800332a7  js      loc_1800333C0
0x1800332ad  cmp     [rsp+128h+var_84], 0
0x1800332b5  jz      loc_1800333C0
0x1800332bb  test    rcx, rcx
0x1800332be  jz      short loc_180033333
0x1800332c0  mov     dword ptr [rsp+128h+var_F0], 0
0x1800332c8  lea     rdx, [rsp+128h+var_F0]; int *
0x1800332cd  call    ?CheckPolicyOnStore@CMapiSupport@@SAJPEAVCMapiStore@@PEAHPEAW4POLICY_RESULT_ID@@@Z; CMapiSupport::CheckPolicyOnStore(CMapiStore *,int *,POLICY_RESULT_ID *)
0x1800332d2  test    eax, eax
0x1800332d4  js      short loc_180033333
0x1800332d6  cmp     dword ptr [rsp+128h+var_F0], 0
0x1800332db  jz      short loc_180033333
0x1800332dd  mov     ebx, esi
0x1800332df  lea     rcx, [rsp+128h+var_D0]
0x1800332e4  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800332e9  nop
0x1800332ea  lea     rcx, [rsp+128h+var_D0]
0x1800332ef  call    ?GetInstalledOutlookVersion@CMapiSupport@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::GetInstalledOutlookVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800332f4  test    eax, eax
0x1800332f6  jnz     short loc_180033321
0x1800332f8  lea     rdx, [rsp+128h+var_D0]
0x1800332fd  lea     rcx, [rsp+128h+var_C8]
0x180033302  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180033307  mov     rcx, rax
0x18003330a  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x18003330f  xor     ebx, ebx
0x180033311  mov     rcx, 0B000000000000h
0x18003331b  cmp     rax, rcx
0x18003331e  setnle  bl
0x180033321  lea     rcx, [rsp+128h+var_D0]
0x180033326  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18003332b  test    ebx, ebx
0x18003332d  jz      loc_1800333C0
0x180033333  mov     [rsp+128h+var_F0], 0
0x18003333c  mov     [rsp+128h+var_90], esi
0x180033343  mov     [rsp+128h+var_84], esi
0x18003334a  mov     rdx, [rsp+128h+var_60]
0x180033352  lea     rcx, [rdx-18h]
0x180033356  mov     rbx, [rsp+128h+var_68]
0x18003335e  add     rbx, 0FFFFFFFFFFFFFFE8h
0x180033362  cmp     rcx, rbx
0x180033365  jz      short loc_1800333A4
0x180033367  cmp     dword ptr [rbx+10h], 0
0x18003336b  jl      short loc_180033393
0x18003336d  mov     rax, [rbx]
0x180033370  cmp     [rcx], rax
0x180033373  jnz     short loc_180033393
0x180033375  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x18003337a  mov     rdi, rax
0x18003337d  mov     rcx, rbx; this
0x180033380  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180033385  lea     rax, [rdi+18h]
0x180033389  mov     [rsp+128h+var_68], rax
0x180033391  jmp     short loc_1800333A4
0x180033393  mov     r8d, [rdx-10h]
0x180033397  lea     rcx, [rsp+128h+var_68]
0x18003339f  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800333a4  mov     [rsp+128h+var_108], esi
0x1800333a8  lea     r9, [rsp+128h+var_E8]
0x1800333ad  lea     r8, [rsp+128h+var_F0]
0x1800333b2  lea     rdx, [rsp+128h+var_B8]
0x1800333b7  mov     rcx, r13
0x1800333ba  call    ?OpenStoreInternal@CMapiSession@@AEAAJAEAVCStoreEntryId@@PEAPEAVCMapiStore@@PEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiSession::OpenStoreInternal(CStoreEntryId &,CMapiStore * *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x1800333bf  nop
0x1800333c0  lea     rcx, [rsp+128h+var_E8]
0x1800333c5  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x1800333ca  nop
0x1800333cb  lea     rcx, [rsp+128h+var_B8]; this
0x1800333d0  call    ??1CStoreEntryId@@QEAA@XZ; CStoreEntryId::~CStoreEntryId(void)
0x1800333d5  mov     rbx, [rsp+128h+lpRows]
0x1800333da  inc     r15d
0x1800333dd  jmp     loc_1800331C6
0x1800333e2  mov     rcx, rbx; lpRows
0x1800333e5  call    cs:__imp_FreeProws
0x1800333eb  mov     [rsp+128h+lpRows], 0
0x1800333f4  xor     ebx, ebx
0x1800333f6  lea     rcx, [rsp+128h+var_E0]
0x1800333fb  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180033400  nop
0x180033401  jmp     short loc_180033409
0x180033403  jmp     short $+2
0x180033405  mov     ebx, [rsp+128h+var_F8]
0x180033409  mov     eax, ebx
0x18003340b  mov     rcx, [rsp+128h+var_40]
0x180033413  xor     rcx, rsp; StackCookie
0x180033416  call    __security_check_cookie
0x18003341b  add     rsp, 0F8h
0x180033422  pop     r15
0x180033424  pop     r14
0x180033426  pop     r13
0x180033428  pop     rdi
0x180033429  pop     rsi
0x18003342a  pop     rbx
0x18003342b  retn
```
