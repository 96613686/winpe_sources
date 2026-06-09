# CPluginCollectionSink::PushStoreAppProperties(void)

- ea: `0x1800a2b04`
- end: `0x1800a30a0`
- name: `?PushStoreAppProperties@CPluginCollectionSink@@QEAAJXZ`
- size: `1436`
- prototype: `__int64 __fastcall(CPluginCollectionSink *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c5670`

## callees

- `0x18000a23c`
- `0x18000f880`
- `0x18002dc6c`
- `0x1800495c0`
- `0x180062b80`
- `0x180066f50`
- `0x180079c44`
- `0x1800a2b04`
- `0x1800a35d8`
- `0x1800a3608`
- `0x1800a3790`
- `0x1800b9404`
- `0x1800bc958`
- `0x1800eacf8`
- `0x1800eaf44`
- `0x180104880`
- `0x1801244c0`
- `0x1801249ec`
- `0x180124d0c`
- `0x18012540e`
- `0x18019d12c`
- `0x18019d27c`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2c29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a2c00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a2c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2ecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2ecb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a2fc4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a2ffd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a2fc4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a2ffd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a2d48`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a2d95`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a2d48`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a2d95`
- `efswrt!CdplUnprotectSecret` at `0x1800a2cdd`
- `efswrt!CdplUnprotectSecret` at `0x1800a2cdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CPluginCollectionSink::PushStoreAppProperties(CFilterDriver **this)
{
  struct CTransaction *v2; // rbx
  int v3; // eax
  unsigned int v4; // edi
  __int64 v5; // r9
  __int64 v6; // rdx
  void *v7; // rdi
  int v8; // esi
  CRegistry *v9; // rdi
  __int64 v10; // rax
  void *v11; // rbx
  const char *v12; // r9
  int v13; // ebx
  void *v14; // rcx
  void *v15; // rcx
  struct IPropertyStore **v16; // r8
  int Property; // ebx
  __int64 v18; // rdx
  __int64 pBlobData_low; // rbx
  __int64 v20; // rax
  bool v21; // cf
  unsigned __int64 v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // r14
  __int64 v25; // rcx
  unsigned int i; // ebx
  int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  char v34[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct tagBLOB v35; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+58h] [rbp-A8h] BYREF
  struct CTransaction *v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h] BYREF
  int v41; // [rsp+80h] [rbp-80h]
  void *v42; // [rsp+88h] [rbp-78h]
  int v43; // [rsp+90h] [rbp-70h]
  __int128 v44; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v45; // [rsp+A8h] [rbp-58h] BYREF
  char *v46; // [rsp+B0h] [rbp-50h]
  __int128 v47; // [rsp+B8h] [rbp-48h] BYREF
  int v48; // [rsp+C8h] [rbp-38h]
  _BYTE v49[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v50; // [rsp+D4h] [rbp-2Ch]
  int v51; // [rsp+D8h] [rbp-28h]
  unsigned int v52; // [rsp+DCh] [rbp-24h] BYREF
  __int128 v53; // [rsp+E0h] [rbp-20h]
  int v54; // [rsp+F0h] [rbp-10h]
  int v55; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v45 = 0;
  v39 = 0;
  v44 = 0;
  CFilterDriver::GetTransaction(*this, &v39);
  v2 = v39;
  v3 = (*(__int64 (__fastcall **)(char *, __int128 *))(*((_QWORD *)v39 + 1) + 168LL))((char *)v39 + 8, &v44);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (unsigned int)v3;
    v6 = 4422;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
      (const char *)v5,
      v32);
LABEL_59:
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v39);
    std::unique_ptr<CComPropVariant [0]>::~unique_ptr<CComPropVariant [0]>(&v45);
    return v4;
  }
  if ( !*((_QWORD *)&v44 + 1) )
  {
    v4 = -2147024809;
    v5 = 2147942487LL;
    v6 = 4423;
    goto LABEL_5;
  }
  v7 = 0;
  v42 = 0;
  v8 = 0;
  v41 = 0;
  v40 = 0;
  v43 = 0;
  if ( IsCDPLEnabled() )
  {
    v9 = g_pGatheringService;
    *(_DWORD *)&pvar.vt = 0;
    pvar.hVal.QuadPart = 0;
    *((_DWORD *)&pvar.decVal + 4) = 0;
    CUserTokenKey::Init((CUserTokenKey *)&pvar, *((const wchar_t **)v2 + 131));
    v46 = (char *)v9 + 7056;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 7056));
    v10 = CTKPLiteHashMap<CUserTokenKey,CUserTokenValue>::Lookup((char *)v9 + 6752, &pvar);
    if ( v10 )
      v11 = *(void **)(v10 + 40);
    else
      v11 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 7056));
    if ( !v11 )
    {
      v4 = -2147023659;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x114E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
        (const char *)0x800704D5LL,
        v32);
LABEL_12:
      CBlob::Free((CBlob *)&v40);
      goto LABEL_59;
    }
    v34[0] = 0;
    if ( !CImpersonateLogonUser::Impersonate((CImpersonateLogonUser *)v34, v11) )
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x1153,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
        v12);
      v4 = -2147023659;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1154,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
        (const char *)0x800704D5LL,
        v32);
LABEL_18:
      if ( v34[0] )
        RevertToSelf();
      goto LABEL_12;
    }
    pv = 0;
    v37 = 0;
    *(_QWORD *)&pvar.vt = &pv;
    pvar.hVal.QuadPart = 0;
    *((_BYTE *)&pvar.decVal + 16) = 1;
    v13 = CdplUnprotectSecret(*((_QWORD *)&v44 + 1), (unsigned int)v44, &pvar.decVal.Lo32, &v37);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&pvar);
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x115C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
        (const char *)(unsigned int)v13,
        v32);
      v4 = -2147023659;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x115F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
        (const char *)0x800704D5LL,
        v33);
      v14 = pv;
      pv = 0;
      if ( v14 )
        CoTaskMemFree(v14);
      goto LABEL_18;
    }
    v8 = v37;
    v7 = pv;
    pv = 0;
    CBlob::Free((CBlob *)&v40);
    v41 = v8;
    v42 = v7;
    *((_QWORD *)&v44 + 1) = v7;
    LODWORD(v44) = v8;
    v15 = pv;
    pv = 0;
    if ( v15 )
      CoTaskMemFree(v15);
    if ( v34[0] )
      RevertToSelf();
  }
  *(_QWORD *)&v35.cbSize = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Property = StoreAppUserBlob::GetProperty((StoreAppUserBlob *)&v44, &v35, v16);
  if ( Property < 0 )
  {
    v18 = 4455;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
      (const char *)(unsigned int)Property,
      v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    CBlob::Free((CBlob *)&v40);
    v4 = Property;
    goto LABEL_59;
  }
  LODWORD(v35.pBlobData) = 0;
  Property = (*(__int64 (__fastcall **)(_QWORD, BYTE **))(**(_QWORD **)&v35.cbSize + 24LL))(
               *(_QWORD *)&v35.cbSize,
               &v35.pBlobData);
  if ( Property < 0 )
  {
    v18 = 4458;
    goto LABEL_26;
  }
  pBlobData_low = LODWORD(v35.pBlobData);
  v20 = 24LL * LODWORD(v35.pBlobData);
  if ( !is_mul_ok(LODWORD(v35.pBlobData), 0x18u) )
    v20 = -1;
  v21 = __CFADD__(v20, 8);
  v22 = v20 + 8;
  if ( v21 )
    v22 = -1;
  v23 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  v46 = (char *)v23;
  if ( v23 )
  {
    *v23 = pBlobData_low;
    v24 = v23 + 1;
    `eh vector constructor iterator'(
      v23 + 1,
      0x18u,
      (unsigned int)pBlobData_low,
      (void (*)(void *))CComPropVariant::CComPropVariant,
      (void (*)(void *))CPropVariant::~CPropVariant);
  }
  else
  {
    v24 = 0;
  }
  v45 = v24;
  if ( v24 )
  {
    for ( i = 0; i < LODWORD(v35.pBlobData); ++i )
    {
      v47 = 0;
      v48 = 0;
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**(_QWORD **)&v35.cbSize + 32LL))(
              *(_QWORD *)&v35.cbSize,
              i,
              &v47);
      v4 = v28;
      if ( v28 < 0 )
      {
        v31 = 4466;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
          (const char *)(unsigned int)v28,
          v32);
        goto LABEL_55;
      }
      memset(&pvar, 0, sizeof(pvar));
      v29 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, struct tagPROPVARIANT *))(**(_QWORD **)&v35.cbSize + 40LL))(
              *(_QWORD *)&v35.cbSize,
              &v47,
              &pvar);
      v4 = v29;
      if ( v29 < 0 )
      {
        v30 = 4469;
LABEL_52:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
          (const char *)(unsigned int)v29,
          v32);
        PropVariantClear((PROPVARIANT *)&pvar);
LABEL_55:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        goto LABEL_12;
      }
      memset_0(v49, 0, 0x40u);
      v29 = CPluginCollectionSink::DecodeStoreAppProperty(
              (CPluginCollectionSink *)(3LL * i),
              &pvar,
              &v52,
              (struct tagPROPVARIANT *)&v24[3 * i]);
      v4 = v29;
      if ( v29 < 0 )
      {
        v30 = 4472;
        goto LABEL_52;
      }
      v50 = 2;
      v51 = 2;
      v53 = v47;
      v54 = 1;
      v55 = v48;
      v32 = 0;
      v29 = CPluginCollectionSink::AddProperty(this, v49, &v24[3 * i], 2);
      v4 = v29;
      if ( v29 < 0 )
      {
        v30 = 4479;
        goto LABEL_52;
      }
      PropVariantClear((PROPVARIANT *)&pvar);
    }
    v28 = CPluginCollectionSink::PushProperties(this, 1, 1);
    v4 = v28;
    if ( v28 < 0 )
    {
      v31 = 4482;
      goto LABEL_54;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    CBlob::Free((CBlob *)&v40);
    v4 = 0;
    goto LABEL_59;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x116D,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
    (const char *)0x8007000ELL,
    v32);
  v25 = *(_QWORD *)&v35.cbSize;
  if ( *(_QWORD *)&v35.cbSize )
  {
    *(_QWORD *)&v35.cbSize = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( v8 )
    CoTaskMemFree(v7);
  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v39);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800a2b04  mov     [rsp-8+arg_8], rbx
0x1800a2b09  mov     [rsp-8+arg_10], rsi
0x1800a2b0e  push    rbp
0x1800a2b0f  push    rdi
0x1800a2b10  push    r12
0x1800a2b12  push    r14
0x1800a2b14  push    r15
0x1800a2b16  lea     rbp, [rsp-20h]
0x1800a2b1b  sub     rsp, 120h
0x1800a2b22  mov     rax, cs:__security_cookie
0x1800a2b29  xor     rax, rsp
0x1800a2b2c  mov     [rbp+40h+var_30], rax
0x1800a2b30  mov     r15, rcx
0x1800a2b33  xor     r12d, r12d
0x1800a2b36  mov     [rbp+40h+var_98], r12
0x1800a2b3a  mov     [rsp+140h+var_D0], r12
0x1800a2b3f  xorps   xmm0, xmm0
0x1800a2b42  movups  [rbp+40h+var_A8], xmm0
0x1800a2b46  lea     rdx, [rsp+140h+var_D0]; struct CTransaction **
0x1800a2b4b  mov     rcx, [rcx]; this
0x1800a2b4e  call    ?GetTransaction@CFilterDriver@@QEAAXPEAPEAVCTransaction@@@Z; CFilterDriver::GetTransaction(CTransaction * *)
0x1800a2b53  mov     rbx, [rsp+140h+var_D0]
0x1800a2b58  lea     rcx, [rbx+8]
0x1800a2b5c  mov     rax, [rcx]
0x1800a2b5f  lea     rdx, [rbp+40h+var_A8]
0x1800a2b63  mov     rax, [rax+0A8h]
0x1800a2b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2b6f  mov     edi, eax
0x1800a2b71  test    eax, eax
0x1800a2b73  jns     short loc_1800A2B7F
0x1800a2b75  mov     r9d, eax
0x1800a2b78  mov     edx, 1146h
0x1800a2b7d  jmp     short loc_1800A2B92
0x1800a2b7f  cmp     qword ptr [rbp+40h+var_A8+8], r12
0x1800a2b83  jnz     short loc_1800A2BA7
0x1800a2b85  mov     edi, 80070057h
0x1800a2b8a  mov     r9d, edi; char *
0x1800a2b8d  mov     edx, 1147h; void *
0x1800a2b92  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a2b99  mov     rcx, [rbp+48h]; this
0x1800a2b9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2ba2  jmp     loc_1800A3062
0x1800a2ba7  mov     rdi, r12
0x1800a2baa  mov     [rbp+40h+var_B8], r12
0x1800a2bae  mov     esi, r12d
0x1800a2bb1  mov     [rbp+40h+var_C0], r12d
0x1800a2bb5  mov     [rsp+140h+var_C8], r12d
0x1800a2bba  mov     [rbp+40h+var_B0], r12d
0x1800a2bbe  call    ?IsCDPLEnabled@@YA_NXZ; IsCDPLEnabled(void)
0x1800a2bc3  test    al, al
0x1800a2bc5  jz      loc_1800A2D9B
0x1800a2bcb  mov     rdi, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800a2bd2  mov     dword ptr [rsp+140h+pvar], r12d
0x1800a2bd7  mov     [rsp+140h+pvar+8], r12
0x1800a2bdc  mov     dword ptr [rsp+140h+var_D8], r12d
0x1800a2be1  mov     rdx, [rbx+418h]; wchar_t *
0x1800a2be8  lea     rcx, [rsp+140h+pvar]; this
0x1800a2bed  call    ?Init@CUserTokenKey@@QEAAXPEB_W@Z; CUserTokenKey::Init(wchar_t const *)
0x1800a2bf2  lea     rsi, [rdi+1B90h]
0x1800a2bf9  mov     [rbp+40h+var_90], rsi
0x1800a2bfd  mov     rcx, rsi; lpCriticalSection
0x1800a2c00  call    cs:__imp_EnterCriticalSection
0x1800a2c06  nop
0x1800a2c07  lea     rcx, [rdi+1A60h]
0x1800a2c0e  lea     rdx, [rsp+140h+pvar]
0x1800a2c13  call    ?Lookup@?$CTKPLiteHashMap@VCUserTokenKey@@VCUserTokenValue@@@@QEBAPEAVCUserTokenValue@@PEBVCUserTokenKey@@@Z; CTKPLiteHashMap<CUserTokenKey,CUserTokenValue>::Lookup(CUserTokenKey const *)
0x1800a2c18  test    rax, rax
0x1800a2c1b  jz      short loc_1800A2C23
0x1800a2c1d  mov     rbx, [rax+28h]
0x1800a2c21  jmp     short loc_1800A2C26
0x1800a2c23  mov     rbx, r12
0x1800a2c26  mov     rcx, rsi; lpCriticalSection
0x1800a2c29  call    cs:__imp_LeaveCriticalSection
0x1800a2c2f  test    rbx, rbx
0x1800a2c32  jnz     short loc_1800A2C61
0x1800a2c34  mov     rcx, [rbp+48h]; this
0x1800a2c38  mov     edi, 800704D5h
0x1800a2c3d  mov     r9d, edi; char *
0x1800a2c40  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a2c47  mov     edx, 114Eh; void *
0x1800a2c4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2c51  nop
0x1800a2c52  lea     rcx, [rsp+140h+var_C8]; this
0x1800a2c57  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x1800a2c5c  jmp     loc_1800A3062
0x1800a2c61  mov     [rsp+140h+var_110], r12b
0x1800a2c66  mov     rdx, rbx; void *
0x1800a2c69  lea     rcx, [rsp+140h+var_110]; this
0x1800a2c6e  call    ?Impersonate@CImpersonateLogonUser@@QEAA_NPEAX@Z; CImpersonateLogonUser::Impersonate(void *)
0x1800a2c73  test    al, al
0x1800a2c75  jnz     short loc_1800A2CAE
0x1800a2c77  mov     rcx, [rbp+48h]; this
0x1800a2c7b  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a2c82  mov     edx, 1153h; void *
0x1800a2c87  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800a2c8c  mov     rcx, [rbp+48h]; this
0x1800a2c90  mov     edi, 800704D5h
0x1800a2c95  mov     r9d, edi; char *
0x1800a2c98  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a2c9f  mov     edx, 1154h; void *
0x1800a2ca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2ca9  jmp     loc_1800A2D3D
0x1800a2cae  mov     [rsp+140h+pv], r12
0x1800a2cb3  mov     [rsp+140h+var_F0], r12d
0x1800a2cb8  lea     rax, [rsp+140h+pv]
0x1800a2cbd  mov     [rsp+140h+pvar], rax
0x1800a2cc2  mov     [rsp+140h+pvar+8], r12
0x1800a2cc7  mov     byte ptr [rsp+140h+var_D8], 1
0x1800a2ccc  lea     r9, [rsp+140h+var_F0]
0x1800a2cd1  lea     r8, [rsp+140h+pvar+8]
0x1800a2cd6  mov     edx, dword ptr [rbp+40h+var_A8]
0x1800a2cd9  mov     rcx, qword ptr [rbp+40h+var_A8+8]
0x1800a2cdd  call    cs:__imp_CdplUnprotectSecret
0x1800a2ce3  mov     ebx, eax
0x1800a2ce5  lea     rcx, [rsp+140h+pvar]
0x1800a2cea  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800a2cef  test    ebx, ebx
0x1800a2cf1  jns     short loc_1800A2D53
0x1800a2cf3  mov     rcx, [rbp+48h]; this
0x1800a2cf7  mov     r9d, ebx; char *
0x1800a2cfa  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a2d01  mov     edx, 115Ch; void *
0x1800a2d06  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800a2d0b  mov     rcx, [rbp+48h]; this
0x1800a2d0f  mov     edi, 800704D5h
0x1800a2d14  mov     r9d, edi; char *
0x1800a2d17  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a2d1e  mov     edx, 115Fh; void *
0x1800a2d23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2d28  mov     rcx, [rsp+140h+pv]; pv
0x1800a2d2d  mov     [rsp+140h+pv], r12
0x1800a2d32  test    rcx, rcx
0x1800a2d35  jz      short loc_1800A2D3D
0x1800a2d37  call    cs:__imp_CoTaskMemFree
0x1800a2d3d  cmp     [rsp+140h+var_110], r12b
0x1800a2d42  jz      loc_1800A2C52
0x1800a2d48  call    cs:__imp_RevertToSelf
0x1800a2d4e  jmp     loc_1800A2C52
0x1800a2d53  mov     esi, [rsp+140h+var_F0]
0x1800a2d57  mov     rdi, [rsp+140h+pv]
0x1800a2d5c  mov     [rsp+140h+pv], r12
0x1800a2d61  lea     rcx, [rsp+140h+var_C8]; this
0x1800a2d66  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x1800a2d6b  mov     [rbp+40h+var_C0], esi
0x1800a2d6e  mov     [rbp+40h+var_B8], rdi
0x1800a2d72  mov     qword ptr [rbp+40h+var_A8+8], rdi
0x1800a2d76  mov     dword ptr [rbp+40h+var_A8], esi
0x1800a2d79  mov     rcx, [rsp+140h+pv]; pv
0x1800a2d7e  mov     [rsp+140h+pv], r12
0x1800a2d83  test    rcx, rcx
0x1800a2d86  jz      short loc_1800A2D8E
0x1800a2d88  call    cs:__imp_CoTaskMemFree
0x1800a2d8e  cmp     [rsp+140h+var_110], r12b
0x1800a2d93  jz      short loc_1800A2D9B
0x1800a2d95  call    cs:__imp_RevertToSelf
0x1800a2d9b  mov     qword ptr [rsp+140h+var_108.cbSize], r12
0x1800a2da0  lea     rcx, [rsp+140h+var_108]
0x1800a2da5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2daa  lea     rdx, [rsp+140h+var_108]; struct tagBLOB *
0x1800a2daf  lea     rcx, [rbp+40h+var_A8]; this
0x1800a2db3  call    ?GetProperty@StoreAppUserBlob@@YAJPEBUtagBLOB@@PEAPEAUIPropertyStore@@@Z; StoreAppUserBlob::GetProperty(tagBLOB const *,IPropertyStore * *)
0x1800a2db8  mov     ebx, eax
0x1800a2dba  test    eax, eax
0x1800a2dbc  jns     short loc_1800A2DF3
0x1800a2dbe  mov     edx, 1167h; void *
0x1800a2dc3  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a2dca  mov     r9d, ebx; char *
0x1800a2dcd  mov     rcx, [rbp+48h]; this
0x1800a2dd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2dd6  nop
0x1800a2dd7  lea     rcx, [rsp+140h+var_108]
0x1800a2ddc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2de1  nop
0x1800a2de2  lea     rcx, [rsp+140h+var_C8]; this
0x1800a2de7  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x1800a2dec  mov     edi, ebx
0x1800a2dee  jmp     loc_1800A3062
0x1800a2df3  mov     dword ptr [rsp+140h+var_108.pBlobData], r12d
0x1800a2df8  mov     rcx, qword ptr [rsp+140h+var_108.cbSize]
0x1800a2dfd  mov     rax, [rcx]
0x1800a2e00  lea     rdx, [rsp+140h+var_108.pBlobData]
0x1800a2e05  mov     rax, [rax+18h]
0x1800a2e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e0e  mov     ebx, eax
0x1800a2e10  test    eax, eax
0x1800a2e12  jns     short loc_1800A2E1B
0x1800a2e14  mov     edx, 116Ah
0x1800a2e19  jmp     short loc_1800A2DC3
0x1800a2e1b  mov     ebx, dword ptr [rsp+140h+var_108.pBlobData]
0x1800a2e1f  mov     eax, 18h
0x1800a2e24  mul     rbx
0x1800a2e27  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a2e2e  cmovb   rax, rcx
0x1800a2e32  add     rax, 8
0x1800a2e36  cmovb   rax, rcx
0x1800a2e3a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a2e41  mov     rcx, rax; unsigned __int64
0x1800a2e44  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a2e49  mov     [rbp+40h+var_90], rax
0x1800a2e4d  test    rax, rax
0x1800a2e50  jz      short loc_1800A2E7E
0x1800a2e52  mov     [rax], rbx
0x1800a2e55  lea     r14, [rax+8]
0x1800a2e59  lea     rax, ??1CPropVariant@@QEAA@XZ; CPropVariant::~CPropVariant(void)
0x1800a2e60  mov     qword ptr [rsp+140h+var_120], rax; void (*)(void *)
0x1800a2e65  lea     r9, ??0CComPropVariant@@QEAA@XZ; void (*)(void *)
0x1800a2e6c  mov     r8d, ebx; unsigned __int64
0x1800a2e6f  mov     edx, 18h; unsigned __int64
0x1800a2e74  mov     rcx, r14; void *
0x1800a2e77  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800a2e7c  jmp     short loc_1800A2E81
0x1800a2e7e  mov     r14, r12
0x1800a2e81  mov     [rbp+40h+var_98], r14
0x1800a2e85  test    r14, r14
0x1800a2e88  jnz     short loc_1800A2EE4
0x1800a2e8a  mov     rcx, [rbp+48h]; this
0x1800a2e8e  mov     ebx, 8007000Eh
0x1800a2e93  mov     r9d, ebx; char *
0x1800a2e96  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a2e9d  mov     edx, 116Dh; void *
0x1800a2ea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2ea7  nop
0x1800a2ea8  mov     rcx, qword ptr [rsp+140h+var_108.cbSize]
0x1800a2ead  test    rcx, rcx
0x1800a2eb0  jz      short loc_1800A2EC4
0x1800a2eb2  mov     qword ptr [rsp+140h+var_108.cbSize], r12
0x1800a2eb7  mov     rax, [rcx]
0x1800a2eba  mov     rax, [rax+10h]
0x1800a2ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2ec3  nop
0x1800a2ec4  test    esi, esi
0x1800a2ec6  jz      short loc_1800A2ED2
0x1800a2ec8  mov     rcx, rdi; pv
0x1800a2ecb  call    cs:__imp_CoTaskMemFree
0x1800a2ed1  nop
0x1800a2ed2  lea     rcx, [rsp+140h+var_D0]
0x1800a2ed7  call    ??1?$TComPointer@UIGatherStoreManagerProvider@@@@QEAA@XZ; TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(void)
0x1800a2edc  nop
0x1800a2edd  mov     eax, ebx
0x1800a2edf  jmp     loc_1800A3078
0x1800a2ee4  mov     ebx, r12d
0x1800a2ee7  cmp     ebx, dword ptr [rsp+140h+var_108.pBlobData]
0x1800a2eeb  jnb     loc_1800A302D
0x1800a2ef1  xorps   xmm0, xmm0
0x1800a2ef4  xor     eax, eax
0x1800a2ef6  movups  [rbp+40h+var_88], xmm0
0x1800a2efa  mov     [rbp+40h+var_78], eax
0x1800a2efd  mov     rcx, qword ptr [rsp+140h+var_108.cbSize]
0x1800a2f02  mov     rax, [rcx]
0x1800a2f05  lea     r8, [rbp+40h+var_88]
0x1800a2f09  mov     edx, ebx
0x1800a2f0b  mov     rax, [rax+20h]
0x1800a2f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f14  mov     edi, eax
0x1800a2f16  test    eax, eax
0x1800a2f18  js      loc_1800A3005
0x1800a2f1e  xorps   xmm0, xmm0
0x1800a2f21  xor     eax, eax
0x1800a2f23  movups  xmmword ptr [rsp+140h+pvar], xmm0
0x1800a2f28  mov     [rsp+140h+var_D8], rax
0x1800a2f2d  mov     rcx, qword ptr [rsp+140h+var_108.cbSize]
0x1800a2f32  mov     rax, [rcx]
0x1800a2f35  lea     r8, [rsp+140h+pvar]
0x1800a2f3a  lea     rdx, [rbp+40h+var_88]
0x1800a2f3e  mov     rax, [rax+28h]
0x1800a2f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f47  mov     edi, eax
0x1800a2f49  test    eax, eax
0x1800a2f4b  js      loc_1800A2FDF
0x1800a2f51  xor     edx, edx; Val
0x1800a2f53  lea     r8d, [rdx+40h]; Size
0x1800a2f57  lea     rcx, [rbp+40h+var_70]; void *
0x1800a2f5b  call    memset_0
0x1800a2f60  mov     eax, ebx
0x1800a2f62  lea     rcx, [rax+rax*2]; this
0x1800a2f66  lea     rsi, [r14+rcx*8]
0x1800a2f6a  mov     r9, rsi; struct tagPROPVARIANT *
0x1800a2f6d  lea     r8, [rbp+40h+var_64]; unsigned int *
0x1800a2f71  lea     rdx, [rsp+140h+pvar]; struct tagPROPVARIANT *
0x1800a2f76  call    ?DecodeStoreAppProperty@CPluginCollectionSink@@AEAAJPEAUtagPROPVARIANT@@PEAK0@Z; CPluginCollectionSink::DecodeStoreAppProperty(tagPROPVARIANT *,ulong *,tagPROPVARIANT *)
0x1800a2f7b  mov     edi, eax
0x1800a2f7d  test    eax, eax
0x1800a2f7f  js      short loc_1800A2FD8
0x1800a2f81  mov     ecx, 2
0x1800a2f86  mov     [rbp+40h+var_6C], ecx
0x1800a2f89  mov     [rbp+40h+var_68], ecx
0x1800a2f8c  movups  xmm0, [rbp+40h+var_88]
0x1800a2f90  movdqu  [rbp+40h+var_60], xmm0
0x1800a2f95  mov     [rbp+40h+var_50], 1
0x1800a2f9c  mov     eax, [rbp+40h+var_78]
0x1800a2f9f  mov     [rbp+40h+var_48], eax
0x1800a2fa2  mov     [rsp+140h+var_120], r12d
0x1800a2fa7  mov     r9d, ecx
0x1800a2faa  mov     r8, rsi
0x1800a2fad  lea     rdx, [rbp+40h+var_70]
0x1800a2fb1  mov     rcx, r15
0x1800a2fb4  call    ?AddProperty@CPluginCollectionSink@@AEAAJPEAUtagSTAT_CHUNK@@PEAUtagPROPVARIANT@@W4TagGATHER_CHUNK_ORIGIN@@H@Z; CPluginCollectionSink::AddProperty(tagSTAT_CHUNK *,tagPROPVARIANT *,TagGATHER_CHUNK_ORIGIN,int)
0x1800a2fb9  mov     edi, eax
0x1800a2fbb  test    eax, eax
0x1800a2fbd  js      short loc_1800A2FD1
  ... truncated ...
```
