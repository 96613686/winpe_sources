# RsopCreateToken(ushort const *,tagSAFEARRAY *,void * *)

- ea: `0x180072aa8`
- end: `0x180072f3d`
- name: `?RsopCreateToken@@YAJPEBGPEAUtagSAFEARRAY@@PEAPEAX@Z`
- size: `1173`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName, SAFEARRAY *psa, void **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x180095704`

## callees

- `0x180071690`
- `0x180072a08`
- `0x180072aa8`
- `0x180072f8c`
- `0x180072fc0`
- `0x180072fec`
- `0x18007d72c`
- `0x1800a83a8`
- `0x1800a8688`
- `0x1800a8834`
- `0x1800a8964`
- `0x1800a8a74`
- `0x1800a8dd8`
- `0x1800b7e94`
- `0x1800b8358`
- `0x1800b8408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d8e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180072db3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180072db3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180072e7f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180072eb7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180072ed1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180072eeb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180072e7f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180072eb7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180072ed1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180072eeb`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072d05`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072d14`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072dc3`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072e76`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072eae`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072ec8`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072ee2`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072d05`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072d14`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072dc3`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072e76`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072eae`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072ec8`
- `AUTHZ!AuthzFreeResourceManager` at `0x180072ee2`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180072c8f`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180072d67`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180072c8f`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180072d67`

## string_xrefs

- `0x180072ca2`: `RsopCreateToken - AuthzInitializeResourceManager failed. Error - %d`
- `0x180072d7a`: `RsopCreateToken - AuthzInitializeResourceManager failed. Error - %d`
- `0x180072af4`: `RsopCreateToken - Entering...`
- `0x180072b61`: `RsopCreateToken - Operator new returned NULL. Creation of a CSid failed.`
- `0x180072b7e`: `RsopCreateToken - Call to CSid::IsValid failed.`
- `0x180072ced`: `RsopCreateToken - ExpandGrp failed for user. Error - 0x%x`
- `0x180072e92`: `RsopCreateToken - %s is invalid`
- `0x180072e5a`: `RsopCreateToken - ExpandGrp failed. Error - 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RsopCreateToken(LPCWSTR lpAccountName, SAFEARRAY *psa, CRsopToken **a3)
{
  signed int v6; // r15d
  CRsopToken *v7; // r14
  const unsigned __int16 *v8; // r8
  CSid *v9; // rax
  unsigned int v10; // edx
  int UserInfo; // edi
  const unsigned __int16 *v12; // r8
  CSid *v13; // rax
  DWORD v14; // eax
  signed int v15; // eax
  int v16; // eax
  DWORD LastError; // eax
  signed int v18; // eax
  signed int cElements; // r12d
  const unsigned __int16 *v20; // r8
  CSid *v21; // rax
  PSID *v22; // rbx
  int v23; // eax
  unsigned int v24; // edx
  bool phAuthzResourceManager; // [rsp+28h] [rbp-58h]
  AUTHZ_RESOURCE_MANAGER_HANDLE hAuthzResourceManager; // [rsp+30h] [rbp-50h] BYREF
  void *ppvData[2]; // [rsp+38h] [rbp-48h] BYREF
  CRsopToken *v29; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v30[16]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v31[16]; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v32[16]; // [rsp+70h] [rbp-10h] BYREF
  struct CSid *v33; // [rsp+D0h] [rbp+50h] BYREF
  AUTHZ_RESOURCE_MANAGER_HANDLE v34; // [rsp+D8h] [rbp+58h] BYREF

  CDebugWrapper::Initialize(
    (CDebugWrapper *)dbgAccessCheck,
    &psa->cDims,
    L"ChkAccDebugLevel",
    L"ChkAcc.log",
    L"ChkAcc.bak",
    phAuthzResourceManager);
  CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 4u, L"RsopCreateToken - Entering...");
  v6 = 0;
  *a3 = 0;
  v7 = (CRsopToken *)operator new(0x10u);
  *(_QWORD *)v7 = 0;
  *((_QWORD *)v7 + 1) = 0;
  v29 = v7;
  v33 = 0;
  if ( !lpAccountName )
    goto LABEL_8;
  v34 = (AUTHZ_RESOURCE_MANAGER_HANDLE)operator new(0x58u);
  v9 = CSid::CSid((CSid *)v34, lpAccountName, v8);
  XPtrST<CSid>::operator=(&v33, v9);
  if ( v33 )
  {
    if ( !*(_BYTE *)v33 )
    {
      CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 2u, L"RsopCreateToken - Call to CSid::IsValid failed.");
      UserInfo = -2147467259;
      goto LABEL_40;
    }
    UserInfo = CRsopToken::AddSid(v7, (PSID *)v33);
    if ( UserInfo < 0 )
      goto LABEL_40;
    v33 = 0;
LABEL_8:
    if ( psa )
    {
      ppvData[0] = 0;
      v34 = 0;
      if ( !AuthzInitializeResourceManager(0, 0, 0, 0, 0, &v34) )
      {
        LastError = GetLastError();
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgAccessCheck,
          2u,
          L"RsopCreateToken - AuthzInitializeResourceManager failed. Error - %d",
          LastError);
        v18 = GetLastError();
        UserInfo = v18;
        if ( v18 > 0 )
          UserInfo = (unsigned __int16)v18 | 0x80070000;
        goto LABEL_40;
      }
      UserInfo = SafeArrayAccessData(psa, ppvData);
      if ( UserInfo < 0 )
      {
        AuthzFreeResourceManager(v34);
        goto LABEL_40;
      }
      cElements = psa->rgsabound[0].cElements;
      while ( v6 < cElements )
      {
        hAuthzResourceManager = (AUTHZ_RESOURCE_MANAGER_HANDLE)operator new(0x58u);
        v21 = CSid::CSid((CSid *)hAuthzResourceManager, *((LPCWSTR *)ppvData[0] + v6), v20);
        XPtrST<CSid>::operator=(&v33, v21);
        v22 = (PSID *)v33;
        if ( !v33 )
        {
          AuthzFreeResourceManager(v34);
          SafeArrayUnaccessData(psa);
          goto LABEL_36;
        }
        if ( !*(_BYTE *)v33 )
        {
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgAccessCheck,
            2u,
            L"RsopCreateToken - %s is invalid",
            *((_QWORD *)ppvData[0] + v6));
          AuthzFreeResourceManager(v34);
          SafeArrayUnaccessData(psa);
          UserInfo = -2147023581;
          goto LABEL_40;
        }
        if ( *((_DWORD *)v33 + 20) != 5 )
        {
          v23 = ExpandGroup(v7, v34, v33);
          UserInfo = v23;
          if ( v23 < 0 )
          {
            CDebugWrapper::Msg(
              (CDebugWrapper *)dbgAccessCheck,
              2u,
              L"RsopCreateToken - ExpandGrp failed. Error - 0x%x",
              (unsigned int)v23);
LABEL_33:
            AuthzFreeResourceManager(v34);
            SafeArrayUnaccessData(psa);
            goto LABEL_40;
          }
        }
        UserInfo = CRsopToken::AddSid(v7, v22);
        if ( UserInfo < 0 )
          goto LABEL_33;
        v33 = 0;
        ++v6;
      }
      AuthzFreeResourceManager(v34);
      SafeArrayUnaccessData(psa);
    }
    else if ( lpAccountName )
    {
      CWString::CWString((CWString *)v32, lpAccountName);
      CWString::CWString((CWString *)v30);
      CWString::CWString((CWString *)v31);
      CWString::CWString((CWString *)ppvData);
      UserInfo = GetUserInfo(
                   (const struct CWString *)v32,
                   (struct CWString *)v30,
                   (struct CWString *)v31,
                   (struct CWString *)ppvData);
      if ( UserInfo < 0 )
        goto LABEL_11;
      UserInfo = AddLocalGroups((const struct CWString *)v30, (const struct CWString *)ppvData, v7);
      if ( UserInfo < 0 )
        goto LABEL_11;
      v34 = (AUTHZ_RESOURCE_MANAGER_HANDLE)operator new(0x58u);
      v13 = CSid::CSid((CSid *)v34, lpAccountName, v12);
      XPtrST<CSid>::operator=(&v33, v13);
      hAuthzResourceManager = 0;
      if ( !AuthzInitializeResourceManager(1u, 0, 0, 0, 0, &hAuthzResourceManager) )
      {
        v14 = GetLastError();
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgAccessCheck,
          2u,
          L"RsopCreateToken - AuthzInitializeResourceManager failed. Error - %d",
          v14);
        v15 = GetLastError();
        UserInfo = v15;
        if ( v15 > 0 )
          UserInfo = (unsigned __int16)v15 | 0x80070000;
        goto LABEL_11;
      }
      v16 = ExpandGroup(v7, hAuthzResourceManager, v33);
      UserInfo = v16;
      if ( v16 < 0 )
      {
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgAccessCheck,
          2u,
          L"RsopCreateToken - ExpandGrp failed for user. Error - 0x%x",
          (unsigned int)v16);
        AuthzFreeResourceManager(hAuthzResourceManager);
LABEL_11:
        CWString::Reset((CWString *)ppvData);
        CWString::Reset((CWString *)v31);
        CWString::Reset((CWString *)v30);
        CWString::Reset((CWString *)v32);
        goto LABEL_40;
      }
      AuthzFreeResourceManager(hAuthzResourceManager);
      CWString::Reset((CWString *)ppvData);
      CWString::Reset((CWString *)v31);
      CWString::Reset((CWString *)v30);
      CWString::Reset((CWString *)v32);
    }
    UserInfo = AddSpecialGroups(v7);
    if ( UserInfo >= 0 )
    {
      *a3 = v7;
      v29 = 0;
      UserInfo = 0;
    }
    goto LABEL_40;
  }
  CDebugWrapper::Msg(
    (CDebugWrapper *)dbgAccessCheck,
    2u,
    L"RsopCreateToken - Operator new returned NULL. Creation of a CSid failed.");
LABEL_36:
  UserInfo = -2147024882;
LABEL_40:
  XPtrST<CSid>::~XPtrST<CSid>(&v33, v10);
  XPtrST<CRsopToken>::~XPtrST<CRsopToken>(&v29, v24);
  return (unsigned int)UserInfo;
}

```

## disassembly

```asm
0x180072aa8  mov     [rsp-38h+arg_0], rbx
0x180072aad  push    rbp
0x180072aae  push    rsi
0x180072aaf  push    rdi
0x180072ab0  push    r12
0x180072ab2  push    r13
0x180072ab4  push    r14
0x180072ab6  push    r15
0x180072ab8  mov     rbp, rsp
0x180072abb  sub     rsp, 80h
0x180072ac2  mov     r13, r8
0x180072ac5  mov     rsi, rdx
0x180072ac8  mov     rbx, rcx
0x180072acb  lea     rax, aChkaccBak; "ChkAcc.bak"
0x180072ad2  mov     [rsp+80h+szResourceManagerName], rax; unsigned __int16 *
0x180072ad7  lea     r9, aChkaccLog; "ChkAcc.log"
0x180072ade  lea     r8, aChkaccdebuglev; "ChkAccDebugLevel"
0x180072ae5  lea     r12, ?dbgAccessCheck@@3VCDebugWrapper@@A; CDebugWrapper dbgAccessCheck
0x180072aec  mov     rcx, r12; this
0x180072aef  call    ?Initialize@CDebugWrapper@@QEAA_NPEBG000_N@Z; CDebugWrapper::Initialize(ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x180072af4  lea     r8, aRsopcreatetoke_8; "RsopCreateToken - Entering..."
0x180072afb  mov     edx, 4; unsigned int
0x180072b00  mov     rcx, r12; this
0x180072b03  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180072b08  xor     r15d, r15d
0x180072b0b  mov     [r13+0], r15
0x180072b0f  lea     ecx, [r15+10h]; Size
0x180072b13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072b18  mov     r14, rax
0x180072b1b  mov     [rbp+arg_10], rax
0x180072b1f  mov     [rax], r15
0x180072b22  mov     [rax+8], r15
0x180072b26  mov     [rbp+var_38], rax
0x180072b2a  mov     [rbp+arg_10], r15
0x180072b2e  test    rbx, rbx
0x180072b31  jz      short loc_180072BB2
0x180072b33  lea     ecx, [r15+58h]; Size
0x180072b37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072b3c  mov     [rbp+arg_18], rax
0x180072b40  mov     rdx, rbx; lpAccountName
0x180072b43  mov     rcx, rax; this
0x180072b46  call    ??0CSid@@QEAA@PEBG0@Z; CSid::CSid(ushort const *,ushort const *)
0x180072b4b  nop
0x180072b4c  mov     rdx, rax
0x180072b4f  lea     rcx, [rbp+arg_10]
0x180072b53  call    ??4?$XPtrST@VCSid@@@@QEAAPEAVCSid@@PEAV1@@Z; XPtrST<CSid>::operator=(CSid *)
0x180072b58  mov     rdx, [rbp+arg_10]; struct CSid *
0x180072b5c  test    rdx, rdx
0x180072b5f  jnz     short loc_180072B79
0x180072b61  lea     r8, aRsopcreatetoke_7; "RsopCreateToken - Operator new returned"...
0x180072b68  lea     edx, [r15+2]; unsigned int
0x180072b6c  mov     rcx, r12; this
0x180072b6f  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180072b74  jmp     loc_180072ED7
0x180072b79  cmp     [rdx], r15b
0x180072b7c  jnz     short loc_180072B9C
0x180072b7e  lea     r8, aRsopcreatetoke; "RsopCreateToken - Call to CSid::IsValid"...
0x180072b85  mov     edx, 2; unsigned int
0x180072b8a  mov     rcx, r12; this
0x180072b8d  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180072b92  mov     edi, 80004005h
0x180072b97  jmp     loc_180072F0D
0x180072b9c  mov     rcx, r14; this
0x180072b9f  call    ?AddSid@CRsopToken@@QEAAJPEAVCSid@@@Z; CRsopToken::AddSid(CSid *)
0x180072ba4  mov     edi, eax
0x180072ba6  test    eax, eax
0x180072ba8  js      loc_180072F0D
0x180072bae  mov     [rbp+arg_10], r15
0x180072bb2  test    rsi, rsi
0x180072bb5  jnz     loc_180072D47
0x180072bbb  test    rbx, rbx
0x180072bbe  jz      loc_180072EF4
0x180072bc4  mov     rdx, rbx; unsigned __int16 *
0x180072bc7  lea     rcx, [rbp+var_10]; this
0x180072bcb  call    ??0CWString@@QEAA@PEBG@Z; CWString::CWString(ushort const *)
0x180072bd0  nop
0x180072bd1  lea     rcx, [rbp+var_30]; this
0x180072bd5  call    ??0CWString@@QEAA@XZ; CWString::CWString(void)
0x180072bda  nop
0x180072bdb  lea     rcx, [rbp+var_20]; this
0x180072bdf  call    ??0CWString@@QEAA@XZ; CWString::CWString(void)
0x180072be4  nop
0x180072be5  lea     rcx, [rbp+ppvData]; this
0x180072be9  call    ??0CWString@@QEAA@XZ; CWString::CWString(void)
0x180072bee  nop
0x180072bef  lea     r9, [rbp+ppvData]; struct CWString *
0x180072bf3  lea     r8, [rbp+var_20]; struct CWString *
0x180072bf7  lea     rdx, [rbp+var_30]; struct CWString *
0x180072bfb  lea     rcx, [rbp+var_10]; struct CWString *
0x180072bff  call    ?GetUserInfo@@YAJAEBVCWString@@AEAV1@11@Z; GetUserInfo(CWString const &,CWString &,CWString &,CWString &)
0x180072c04  mov     edi, eax
0x180072c06  test    eax, eax
0x180072c08  jns     short loc_180072C36
0x180072c0a  lea     rcx, [rbp+ppvData]; this
0x180072c0e  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180072c13  nop
0x180072c14  lea     rcx, [rbp+var_20]; this
0x180072c18  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180072c1d  nop
0x180072c1e  lea     rcx, [rbp+var_30]; this
0x180072c22  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180072c27  nop
0x180072c28  lea     rcx, [rbp+var_10]; this
0x180072c2c  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180072c31  jmp     loc_180072F0D
0x180072c36  mov     r8, r14; void *
0x180072c39  lea     rdx, [rbp+ppvData]; struct CWString *
0x180072c3d  lea     rcx, [rbp+var_30]; struct CWString *
0x180072c41  call    ?AddLocalGroups@@YAJAEBVCWString@@0PEAX@Z; AddLocalGroups(CWString const &,CWString const &,void *)
0x180072c46  mov     edi, eax
0x180072c48  test    eax, eax
0x180072c4a  js      short loc_180072C0A
0x180072c4c  mov     ecx, 58h ; 'X'; Size
0x180072c51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072c56  mov     [rbp+arg_18], rax
0x180072c5a  mov     rdx, rbx; lpAccountName
0x180072c5d  mov     rcx, rax; this
0x180072c60  call    ??0CSid@@QEAA@PEBG0@Z; CSid::CSid(ushort const *,ushort const *)
0x180072c65  nop
0x180072c66  mov     rdx, rax
0x180072c69  lea     rcx, [rbp+arg_10]
0x180072c6d  call    ??4?$XPtrST@VCSid@@@@QEAAPEAVCSid@@PEAV1@@Z; XPtrST<CSid>::operator=(CSid *)
0x180072c72  mov     [rbp+hAuthzResourceManager], r15
0x180072c76  lea     rax, [rbp+hAuthzResourceManager]
0x180072c7a  mov     [rsp+80h+phAuthzResourceManager], rax; phAuthzResourceManager
0x180072c7f  mov     [rsp+80h+szResourceManagerName], r15; szResourceManagerName
0x180072c84  xor     r9d, r9d; pfnFreeDynamicGroups
0x180072c87  xor     r8d, r8d; pfnComputeDynamicGroups
0x180072c8a  xor     edx, edx; pfnDynamicAccessCheck
0x180072c8c  lea     ecx, [rdx+1]; Flags
0x180072c8f  call    cs:__imp_AuthzInitializeResourceManager
0x180072c95  test    eax, eax
0x180072c97  jnz     short loc_180072CD4
0x180072c99  call    cs:__imp_GetLastError
0x180072c9f  mov     r9d, eax
0x180072ca2  lea     r8, aRsopcreatetoke_2; "RsopCreateToken - AuthzInitializeResour"...
0x180072ca9  mov     edx, 2; unsigned int
0x180072cae  mov     rcx, r12; this
0x180072cb1  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180072cb6  call    cs:__imp_GetLastError
0x180072cbc  mov     edi, eax
0x180072cbe  test    eax, eax
0x180072cc0  jle     loc_180072C0A
0x180072cc6  movzx   edi, ax
0x180072cc9  or      edi, 80070000h
0x180072ccf  jmp     loc_180072C0A
0x180072cd4  mov     r8, [rbp+arg_10]; struct CSid *
0x180072cd8  mov     rdx, [rbp+hAuthzResourceManager]; struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *
0x180072cdc  mov     rcx, r14; this
0x180072cdf  call    ?ExpandGroup@@YAJPEAUCRsopToken@@PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@PEAVCSid@@@Z; ExpandGroup(CRsopToken *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,CSid *)
0x180072ce4  mov     edi, eax
0x180072ce6  test    eax, eax
0x180072ce8  jns     short loc_180072D10
0x180072cea  mov     r9d, eax
0x180072ced  lea     r8, aRsopcreatetoke_6; "RsopCreateToken - ExpandGrp failed for "...
0x180072cf4  mov     edx, 2; unsigned int
0x180072cf9  mov     rcx, r12; this
0x180072cfc  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180072d01  mov     rcx, [rbp+hAuthzResourceManager]; hAuthzResourceManager
0x180072d05  call    cs:__imp_AuthzFreeResourceManager
0x180072d0b  jmp     loc_180072C0A
0x180072d10  mov     rcx, [rbp+hAuthzResourceManager]; hAuthzResourceManager
0x180072d14  call    cs:__imp_AuthzFreeResourceManager
0x180072d1a  nop
0x180072d1b  lea     rcx, [rbp+ppvData]; this
0x180072d1f  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180072d24  nop
0x180072d25  lea     rcx, [rbp+var_20]; this
0x180072d29  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180072d2e  nop
0x180072d2f  lea     rcx, [rbp+var_30]; this
0x180072d33  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180072d38  nop
0x180072d39  lea     rcx, [rbp+var_10]; this
0x180072d3d  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180072d42  jmp     loc_180072EF4
0x180072d47  mov     [rbp+ppvData], r15
0x180072d4b  mov     [rbp+arg_18], r15
0x180072d4f  lea     rax, [rbp+arg_18]
0x180072d53  mov     [rsp+80h+phAuthzResourceManager], rax; phAuthzResourceManager
0x180072d58  mov     [rsp+80h+szResourceManagerName], r15; szResourceManagerName
0x180072d5d  xor     r9d, r9d; pfnFreeDynamicGroups
0x180072d60  xor     r8d, r8d; pfnComputeDynamicGroups
0x180072d63  xor     edx, edx; pfnDynamicAccessCheck
0x180072d65  xor     ecx, ecx; Flags
0x180072d67  call    cs:__imp_AuthzInitializeResourceManager
0x180072d6d  test    eax, eax
0x180072d6f  jnz     short loc_180072DAC
0x180072d71  call    cs:__imp_GetLastError
0x180072d77  mov     r9d, eax
0x180072d7a  lea     r8, aRsopcreatetoke_2; "RsopCreateToken - AuthzInitializeResour"...
0x180072d81  mov     edx, 2; unsigned int
0x180072d86  mov     rcx, r12; this
0x180072d89  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180072d8e  call    cs:__imp_GetLastError
0x180072d94  mov     edi, eax
0x180072d96  test    eax, eax
0x180072d98  jle     loc_180072F0D
0x180072d9e  movzx   edi, ax
0x180072da1  or      edi, 80070000h
0x180072da7  jmp     loc_180072F0D
0x180072dac  lea     rdx, [rbp+ppvData]; ppvData
0x180072db0  mov     rcx, rsi; psa
0x180072db3  call    cs:__imp_SafeArrayAccessData
0x180072db9  mov     edi, eax
0x180072dbb  test    eax, eax
0x180072dbd  jns     short loc_180072DCE
0x180072dbf  mov     rcx, [rbp+arg_18]; hAuthzResourceManager
0x180072dc3  call    cs:__imp_AuthzFreeResourceManager
0x180072dc9  jmp     loc_180072F0D
0x180072dce  mov     r12d, [rsi+18h]
0x180072dd2  cmp     r15d, r12d
0x180072dd5  jge     loc_180072EDE
0x180072ddb  mov     ecx, 58h ; 'X'; Size
0x180072de0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072de5  mov     [rbp+hAuthzResourceManager], rax
0x180072de9  movsxd  rdi, r15d
0x180072dec  mov     rdx, [rbp+ppvData]
0x180072df0  mov     rdx, [rdx+rdi*8]; lpAccountName
0x180072df4  mov     rcx, rax; this
0x180072df7  call    ??0CSid@@QEAA@PEBG0@Z; CSid::CSid(ushort const *,ushort const *)
0x180072dfc  nop
0x180072dfd  mov     rdx, rax
0x180072e00  lea     rcx, [rbp+arg_10]
0x180072e04  call    ??4?$XPtrST@VCSid@@@@QEAAPEAVCSid@@PEAV1@@Z; XPtrST<CSid>::operator=(CSid *)
0x180072e09  mov     rbx, [rbp+arg_10]
0x180072e0d  test    rbx, rbx
0x180072e10  jz      loc_180072EC4
0x180072e16  cmp     byte ptr [rbx], 0
0x180072e19  jz      short loc_180072E8A
0x180072e1b  cmp     dword ptr [rbx+50h], 5
0x180072e1f  jz      short loc_180072E36
0x180072e21  mov     r8, rbx; struct CSid *
0x180072e24  mov     rdx, [rbp+arg_18]; struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *
0x180072e28  mov     rcx, r14; this
0x180072e2b  call    ?ExpandGroup@@YAJPEAUCRsopToken@@PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@PEAVCSid@@@Z; ExpandGroup(CRsopToken *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,CSid *)
0x180072e30  mov     edi, eax
0x180072e32  test    eax, eax
0x180072e34  js      short loc_180072E57
0x180072e36  mov     rdx, rbx; struct CSid *
0x180072e39  mov     rcx, r14; this
0x180072e3c  call    ?AddSid@CRsopToken@@QEAAJPEAVCSid@@@Z; CRsopToken::AddSid(CSid *)
0x180072e41  mov     edi, eax
0x180072e43  test    eax, eax
0x180072e45  js      short loc_180072E72
0x180072e47  mov     [rbp+arg_10], 0
0x180072e4f  inc     r15d
0x180072e52  jmp     loc_180072DD2
0x180072e57  mov     r9d, eax
0x180072e5a  lea     r8, aRsopcreatetoke_5; "RsopCreateToken - ExpandGrp failed. Err"...
0x180072e61  mov     edx, 2; unsigned int
0x180072e66  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x180072e6d  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180072e72  mov     rcx, [rbp+arg_18]; hAuthzResourceManager
0x180072e76  call    cs:__imp_AuthzFreeResourceManager
0x180072e7c  mov     rcx, rsi; psa
0x180072e7f  call    cs:__imp_SafeArrayUnaccessData
0x180072e85  jmp     loc_180072F0D
0x180072e8a  mov     r9, [rbp+ppvData]
0x180072e8e  mov     r9, [r9+rdi*8]
0x180072e92  lea     r8, aRsopcreatetoke_1; "RsopCreateToken - %s is invalid"
0x180072e99  mov     edx, 2; unsigned int
0x180072e9e  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x180072ea5  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180072eaa  mov     rcx, [rbp+arg_18]; hAuthzResourceManager
0x180072eae  call    cs:__imp_AuthzFreeResourceManager
0x180072eb4  mov     rcx, rsi; psa
0x180072eb7  call    cs:__imp_SafeArrayUnaccessData
0x180072ebd  mov     edi, 80070523h
0x180072ec2  jmp     short loc_180072F0D
0x180072ec4  mov     rcx, [rbp+arg_18]; hAuthzResourceManager
0x180072ec8  call    cs:__imp_AuthzFreeResourceManager
0x180072ece  mov     rcx, rsi; psa
0x180072ed1  call    cs:__imp_SafeArrayUnaccessData
0x180072ed7  mov     edi, 8007000Eh
0x180072edc  jmp     short loc_180072F0D
0x180072ede  mov     rcx, [rbp+arg_18]; hAuthzResourceManager
0x180072ee2  call    cs:__imp_AuthzFreeResourceManager
0x180072ee8  mov     rcx, rsi; psa
0x180072eeb  call    cs:__imp_SafeArrayUnaccessData
0x180072ef1  xor     r15d, r15d
0x180072ef4  mov     rcx, r14; this
0x180072ef7  call    ?AddSpecialGroups@@YAJPEAX@Z; AddSpecialGroups(void *)
0x180072efc  mov     edi, eax
0x180072efe  test    eax, eax
0x180072f00  js      short loc_180072F0D
0x180072f02  mov     [r13+0], r14
0x180072f06  mov     [rbp+var_38], r15
0x180072f0a  mov     edi, r15d
0x180072f0d  lea     rcx, [rbp+arg_10]
0x180072f11  call    ??1?$XPtrST@VCSid@@@@QEAA@XZ; XPtrST<CSid>::~XPtrST<CSid>(void)
0x180072f16  nop
0x180072f17  lea     rcx, [rbp+var_38]
0x180072f1b  call    ??1?$XPtrST@UCRsopToken@@@@QEAA@XZ; XPtrST<CRsopToken>::~XPtrST<CRsopToken>(void)
0x180072f20  mov     eax, edi
0x180072f22  mov     rbx, [rsp+80h+arg_0]
0x180072f2a  add     rsp, 80h
0x180072f31  pop     r15
0x180072f33  pop     r14
0x180072f35  pop     r13
  ... truncated ...
```
