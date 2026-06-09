# GenerateDefaultAccessPermissionsSecurityDescriptor(_SECURITY_DESCRIPTOR_RELATIVE *,ulong,_SECURITY_DESCRIPTOR_RELATIVE * *)

- ea: `0x18005e858`
- end: `0x18005eda3`
- name: `?GenerateDefaultAccessPermissionsSecurityDescriptor@@YAJPEAU_SECURITY_DESCRIPTOR_RELATIVE@@KPEAPEAU1@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(_SECURITY_DESCRIPTOR_RELATIVE *pRegistrySd, unsigned int registrySdSize, _SECURITY_DESCRIPTOR_RELATIVE **ppSdOut)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180120b30`

## callees

- `0x180022710`
- `0x18003a8bc`
- `0x18003cf8c`
- `0x18005e858`
- `0x18005edb0`
- `0x18005ede0`
- `0x18005ee20`
- `0x18005ef40`
- `0x18005f728`
- `0x18005f9b8`
- `0x180075a8c`
- `0x1800d33b8`
- `0x1801446f0`
- `0x18018ab84`
- `0x1801999b0`
- `0x18019a654`
- `0x1801b240c`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18005e9cb`
- `ntdll!RtlIsMultiSessionSku` at `0x18005ec1c`
- `ntdll!RtlIsMultiSessionSku` at `0x18005e9cb`
- `ntdll!RtlIsMultiSessionSku` at `0x18005ec1c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea75`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea75`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802478f3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802478f3`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005ea56`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005ea56`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18024793b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180247963`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18024793b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180247963`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18024788a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18024788a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18005ed76`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18005ed76`

## string_xrefs

- `0x18005eac4`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005eb40`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005ec40`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005ec73`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005eca6`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005ecd5`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005ed88`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180247898`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1802478b2`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180247918`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005eaa4`: `onecore\com\combase\common\core\securityutilities.cpp`
- `0x18005ebf9`: `onecore\com\combase\common\core\securityutilities.cpp`

## pseudocode

```c
__int64 __fastcall GenerateDefaultAccessPermissionsSecurityDescriptor(
        _SECURITY_DESCRIPTOR_RELATIVE *pRegistrySd,
        unsigned int registrySdSize,
        _SECURITY_DESCRIPTOR_RELATIVE **ppSdOut)
{
  int v5; // edi
  ProcessToken *v6; // rcx
  AppModelPolicy_PolicyValue AppModelPolicyValue; // r15d
  bool v8; // r13
  bool v9; // r12
  char v10; // r14
  char v11; // al
  __int64 v12; // rdi
  wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > *v13; // rbx
  __int64 v14; // rsi
  unsigned int v15; // edx
  unsigned __int64 v16; // rbx
  HRESULT v17; // eax
  unsigned __int8 *v18; // rbx
  unsigned int LastError; // esi
  signed int i; // esi
  PDWORD SidSubAuthority; // rax
  __int64 v23; // rcx
  unsigned int v24; // edx
  HRESULT AccessAllowedAceFromSid; // eax
  HRESULT v26; // r9d
  unsigned int v27; // edx
  HRESULT v28; // eax
  unsigned int v29; // ebx
  HRESULT WellKnownAccessAllowedAce; // eax
  HRESULT v31; // eax
  unsigned int v32; // edx
  unsigned __int64 v33; // rbx
  HRESULT v34; // eax
  unsigned __int8 *v35; // rbx
  unsigned __int8 *v36; // rbx
  unsigned __int8 *v37; // rbx
  int v38; // eax
  NTSTATUS v39; // eax
  NTSTATUS v40; // eax
  HRESULT v41; // eax
  unsigned int v42; // edx
  HRESULT v43; // eax
  _POLICY_ACCOUNT_DOMAIN_INFO *v44; // rcx
  _POLICY_ACCOUNT_DOMAIN_INFO *value; // rcx
  char v46; // [rsp+20h] [rbp-E0h]
  wistd::unique_ptr<_POLICY_ACCOUNT_DOMAIN_INFO,wil::function_deleter<long (__cdecl*)(void *),&LsaLookupFreeMemory> > domainInfo; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int sidBufferSize; // [rsp+30h] [rbp-D0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (__cdecl*)(void *),&LsaLookupClose,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > lsalookup; // [rsp+38h] [rbp-C8h] BYREF
  void *pSdIn; // [rsp+40h] [rbp-C0h]
  _SECURITY_DESCRIPTOR_RELATIVE **v51; // [rsp+48h] [rbp-B8h]
  _OBJECT_ATTRIBUTES lsaAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _SID_IDENTIFIER_AUTHORITY appPackageAuthority; // [rsp+80h] [rbp-80h] BYREF
  wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > newAces[7]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 sidBuffer[68]; // [rsp+C0h] [rbp-40h] BYREF
  void *retaddr; // [rsp+158h] [rbp+58h]

  v51 = ppSdOut;
  *ppSdOut = 0;
  if ( pRegistrySd )
  {
    pSdIn = pRegistrySd;
  }
  else
  {
    registrySdSize = CRpcResolver::_dwNoRegAccessPermissionsSDSize;
    pSdIn = CRpcResolver::_pNoRegAccessPermissionsSD;
  }
  v5 = IsProcessILGreaterThanOrEqual(0x2100u);
  sidBufferSize = IsRunningInDCOMLAUNCH();
  AppModelPolicyValue = ProcessToken::GetAppModelPolicyValue(v6, AppModelPolicy_Type_ComSecurityInitialization);
  v8 = !v5 || AppModelPolicyValue == AppModelPolicy_ComSecurityInitialization_SystemManaged || sidBufferSize;
  v9 = !pRegistrySd
    && !(unsigned __int8)RtlIsMultiSessionSku()
    && AppModelPolicyValue == AppModelPolicy_ComSecurityInitialization_SystemManaged;
  if ( !v5 || AppModelPolicyValue == AppModelPolicy_ComSecurityInitialization_SystemManaged )
  {
    v10 = 1;
    if ( !v5 && !(unsigned __int8)RtlIsMultiSessionSku() )
    {
      v11 = 1;
      goto LABEL_10;
    }
  }
  else
  {
    v10 = 0;
  }
  v11 = 0;
LABEL_10:
  v46 = v11;
  if ( v8
    || v9
    || AppModelPolicyValue == AppModelPolicy_ComSecurityInitialization_SystemManaged
    || sidBufferSize
    || v10
    || v11 )
  {
    v12 = 7;
    v13 = newAces;
    v14 = 7;
    do
    {
      ObjectLibrary::ReferencedPtr<WinrtAsyncProxyMethodInfo>::ReferencedPtr<WinrtAsyncProxyMethodInfo>((ObjectLibrary::ReferencedPtr<WinrtAsyncProxyMethodInfo> *)v13++);
      --v14;
    }
    while ( v14 );
    v16 = 0;
    if ( v8 )
    {
      WellKnownAccessAllowedAce = CreateWellKnownAccessAllowedAce(WinBuiltinAnyPackageSid, v15, newAces);
      LastError = WellKnownAccessAllowedAce;
      if ( WellKnownAccessAllowedAce < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0x165Eu,
          "onecore\\com\\combase\\dcomrem\\security.cxx",
          WellKnownAccessAllowedAce);
        v35 = sidBuffer;
        do
        {
          v35 -= 8;
          wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>((wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > *)v35);
          --v12;
        }
        while ( v12 );
        return LastError;
      }
      v16 = 1;
    }
    if ( v9 )
    {
      v38 = CreateWellKnownAccessAllowedAce(WinInteractiveSid, v15, &newAces[v16]);
      LastError = v38;
      if ( v38 < 0 )
      {
        v27 = 5730;
        goto LABEL_75;
      }
      ++v16;
    }
    if ( AppModelPolicyValue == AppModelPolicy_ComSecurityInitialization_SystemManaged )
    {
      v31 = CreateWellKnownAccessAllowedAce(WinLocalServiceSid, v15, &newAces[v16]);
      LastError = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x1666u, "onecore\\com\\combase\\dcomrem\\security.cxx", v31);
        v36 = sidBuffer;
        do
        {
          v36 -= 8;
          wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>((wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > *)v36);
          --v12;
        }
        while ( v12 );
        return LastError;
      }
      v33 = v16 + 1;
      v34 = CreateWellKnownAccessAllowedAce(WinNetworkServiceSid, v32, &newAces[v33]);
      LastError = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x1667u, "onecore\\com\\combase\\dcomrem\\security.cxx", v34);
        v37 = sidBuffer;
        do
        {
          v37 -= 8;
          wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>((wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > *)v37);
          --v12;
        }
        while ( v12 );
        return LastError;
      }
      v16 = v33 + 1;
    }
    if ( !sidBufferSize )
    {
LABEL_17:
      if ( !v10 )
        goto LABEL_18;
      *(_DWORD *)appPackageAuthority.Value = 0;
      *(_WORD *)&appPackageAuthority.Value[4] = 3840;
      lsaAttributes.Length = 3;
      *(&lsaAttributes.Length + 1) = 1024;
      lsaAttributes.RootDirectory = (void *)0x3418BB9A8F6027A1LL;
      lsaAttributes.ObjectName = (_UNICODE_STRING *)0x6CB6D59DFF77B663LL;
      lsaAttributes.Attributes = 1746547431;
      *(&lsaAttributes.Attributes + 1) = -1841081848;
      lsaAttributes.SecurityDescriptor = (void *)0x3B1B1798D81FA686LL;
      if ( InitializeSid(sidBuffer, &appPackageAuthority, 0xAu) )
      {
        for ( i = 0; i < 10; ++i )
        {
          SidSubAuthority = GetSidSubAuthority(sidBuffer, i);
          v23 = (unsigned int)i;
          v24 = *(&lsaAttributes.Length + v23);
          *SidSubAuthority = v24;
        }
        AccessAllowedAceFromSid = CreateAccessAllowedAceFromSid(sidBuffer, v24, &newAces[v16]);
        LastError = AccessAllowedAceFromSid;
        if ( AccessAllowedAceFromSid < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            0x43u,
            "onecore\\com\\combase\\common\\core\\securityutilities.cpp",
            AccessAllowedAceFromSid);
LABEL_30:
          v26 = LastError;
          v27 = 5745;
LABEL_31:
          wil::details::in1diag3::Return_Hr(retaddr, v27, "onecore\\com\\combase\\dcomrem\\security.cxx", v26);
LABEL_32:
          `vector destructor iterator'(
            newAces,
            8u,
            7u,
            (void (__fastcall *)(void *))wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>);
          return LastError;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      0x3Cu,
                      "onecore\\com\\combase\\common\\core\\securityutilities.cpp");
        if ( (LastError & 0x80000000) != 0 )
          goto LABEL_30;
      }
      ++v16;
LABEL_18:
      if ( !v46 )
      {
LABEL_19:
        v17 = AddAcesToSecurityDescriptorViaApi(pSdIn, (_ACE_HEADER **)newAces, v16, (void **)v51);
        v18 = sidBuffer;
        LastError = v17;
        if ( v17 >= 0 )
        {
          do
          {
            v18 -= 8;
            wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>((wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > *)v18);
            --v12;
          }
          while ( v12 );
          return 0;
        }
        wil::details::in1diag3::Return_Hr(retaddr, 0x1687u, "onecore\\com\\combase\\dcomrem\\security.cxx", v17);
        do
        {
          v18 -= 8;
          wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>((wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > *)v18);
          --v12;
        }
        while ( v12 );
        return LastError;
      }
      lsalookup.m_ptr = 0;
      memset(&lsaAttributes, 0, sizeof(lsaAttributes));
      v39 = LsaLookupOpenLocalPolicy(&lsaAttributes, 1u, &lsalookup.m_ptr);
      if ( v39 < 0 )
      {
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      0x1678u,
                      "onecore\\com\\combase\\dcomrem\\security.cxx",
                      v39);
LABEL_86:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lsalookup);
        goto LABEL_32;
      }
      domainInfo.__ptr_.__value_ = 0;
      v40 = LsaLookupGetDomainInfo(lsalookup.m_ptr, AccountDomainInformation, (PVOID *)&domainInfo.__ptr_.__value_);
      if ( v40 >= 0 )
      {
        memset_0(sidBuffer, 0, sizeof(sidBuffer));
        sidBufferSize = 68;
        if ( CreateWellKnownSid(
               WinAccountDefaultSystemManagedSid,
               domainInfo.__ptr_.__value_->DomainSid,
               sidBuffer,
               &sidBufferSize) )
        {
          v43 = CreateAccessAllowedAceFromSid(sidBuffer, v42, &newAces[v16]);
          LastError = v43;
          if ( v43 >= 0 )
          {
            value = domainInfo.__ptr_.__value_;
            ++v16;
            domainInfo.__ptr_.__value_ = 0;
            if ( value )
              LsaLookupFreeMemory(value);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lsalookup);
            goto LABEL_19;
          }
          wil::details::in1diag3::Return_Hr(retaddr, 0x1680u, "onecore\\com\\combase\\dcomrem\\security.cxx", v43);
          goto LABEL_84;
        }
        v41 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                0x167Fu,
                "onecore\\com\\combase\\dcomrem\\security.cxx");
      }
      else
      {
        v41 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                0x167Bu,
                "onecore\\com\\combase\\dcomrem\\security.cxx",
                v40);
      }
      LastError = v41;
LABEL_84:
      v44 = domainInfo.__ptr_.__value_;
      domainInfo.__ptr_.__value_ = 0;
      if ( v44 )
        LsaLookupFreeMemory(v44);
      goto LABEL_86;
    }
    v38 = CreateWellKnownAccessAllowedAce(WinAuthenticatedUserSid, v15, &newAces[v16]);
    LastError = v38;
    if ( v38 >= 0 )
    {
      ++v16;
      goto LABEL_17;
    }
    v27 = 5739;
LABEL_75:
    v26 = v38;
    goto LABEL_31;
  }
  v28 = CopySelfRelativeSd((_SECURITY_DESCRIPTOR_RELATIVE *)pSdIn, registrySdSize, v51);
  v29 = v28;
  if ( v28 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(retaddr, 0x1654u, "onecore\\com\\combase\\dcomrem\\security.cxx", v28);
  return v29;
}

```

## disassembly

```asm
0x18005e858  mov     [rsp-8+arg_18], rbx
0x18005e85d  push    rbp
0x18005e85e  push    rsi
0x18005e85f  push    rdi
0x18005e860  push    r12
0x18005e862  push    r13
0x18005e864  push    r14
0x18005e866  push    r15
0x18005e868  lea     rbp, [rsp-20h]
0x18005e86d  sub     rsp, 120h
0x18005e874  mov     rax, cs:__security_cookie
0x18005e87b  xor     rax, rsp
0x18005e87e  mov     [rbp+50h+var_40], rax
0x18005e882  mov     [rsp+150h+var_108], ppSdOut
0x18005e887  mov     esi, registrySdSize
0x18005e889  mov     qword ptr [ppSdOut], 0
0x18005e890  mov     rbx, pRegistrySd
0x18005e893  test    pRegistrySd, pRegistrySd
0x18005e896  jnz     loc_18005EC32
0x18005e89c  mov     rax, cs:?_pNoRegAccessPermissionsSD@CRpcResolver@@0PEAXEA; void * CRpcResolver::_pNoRegAccessPermissionsSD
0x18005e8a3  mov     esi, cs:?_dwNoRegAccessPermissionsSDSize@CRpcResolver@@0KA; ulong CRpcResolver::_dwNoRegAccessPermissionsSDSize
0x18005e8a9  mov     [rsp+150h+pSdIn], rax
0x18005e8ae  mov     ecx, 2100h; dwRID
0x18005e8b3  call    ?IsProcessILGreaterThanOrEqual@@YAHK@Z; IsProcessILGreaterThanOrEqual(ulong)
0x18005e8b8  mov     edi, eax
0x18005e8ba  call    ?IsRunningInDCOMLAUNCH@@YAHXZ; IsRunningInDCOMLAUNCH(void)
0x18005e8bf  mov     registrySdSize, 18h; policyType
0x18005e8c4  mov     [rsp+150h+sidBufferSize], eax
0x18005e8c8  mov     r14d, eax
0x18005e8cb  call    ?GetAppModelPolicyValue@ProcessToken@@QEAA?AW4AppModelPolicy_PolicyValue@@W4AppModelPolicy_Type@@@Z; ProcessToken::GetAppModelPolicyValue(AppModelPolicy_Type)
0x18005e8d0  mov     r15d, eax
0x18005e8d3  test    edi, edi
0x18005e8d5  jnz     loc_18005EB94
0x18005e8db  mov     r13b, 1
0x18005e8de  test    rbx, rbx
0x18005e8e1  jz      loc_18005E9CB
0x18005e8e7  xor     r12b, r12b
0x18005e8ea  test    edi, edi
0x18005e8ec  jnz     loc_18005EB5B
0x18005e8f2  mov     r14b, 1
0x18005e8f5  test    edi, edi
0x18005e8f7  jz      loc_18005EC1C
0x18005e8fd  xor     al, al
0x18005e8ff  mov     [rsp+150h+var_130], al
0x18005e903  test    r13b, r13b
0x18005e906  jz      loc_18005EAEF
0x18005e90c  mov     edi, 7
0x18005e911  lea     rbx, [rbp+50h+newAces]
0x18005e915  mov     esi, edi
0x18005e917  mov     pRegistrySd, rbx; this
0x18005e91a  call    ??0?$ReferencedPtr@VWinrtAsyncProxyMethodInfo@@@ObjectLibrary@@QEAA@XZ; ObjectLibrary::ReferencedPtr<WinrtAsyncProxyMethodInfo>::ReferencedPtr<WinrtAsyncProxyMethodInfo>(void)
0x18005e91f  add     rbx, 8
0x18005e923  sub     rsi, 1
0x18005e927  jnz     short loc_18005E917
0x18005e929  xor     ebx, ebx
0x18005e92b  test    r13b, r13b
0x18005e92e  jnz     loc_18005EB70
0x18005e934  xor     r13d, r13d
0x18005e937  test    r12b, r12b
0x18005e93a  jnz     loc_18005ED04
0x18005e940  cmp     r15d, 180001h
0x18005e947  jz      loc_18005EBB2
0x18005e94d  cmp     [rsp+150h+sidBufferSize], r13d
0x18005e952  jnz     loc_18005ED2A
0x18005e958  test    r14b, r14b
0x18005e95b  jnz     loc_18005E9EE
0x18005e961  cmp     [rsp+150h+var_130], r13b
0x18005e966  jnz     loc_18005ED50
0x18005e96c  mov     r9, [rsp+150h+var_108]; ppSdOut
0x18005e971  lea     rdx, [rbp+50h+newAces]; ppAcesIn
0x18005e975  mov     pRegistrySd, [rsp+150h+pSdIn]; pSdIn
0x18005e97a  mov     ppSdOut, rbx; cAcesIn
0x18005e97d  call    ?AddAcesToSecurityDescriptorViaApi@@YAJPEAXPEAPEAU_ACE_HEADER@@_KPEAPEAX@Z; AddAcesToSecurityDescriptorViaApi(void *,_ACE_HEADER * *,unsigned __int64,void * *)
0x18005e982  lea     rbx, [rbp+50h+sidBuffer]
0x18005e986  mov     esi, eax
0x18005e988  test    eax, eax
0x18005e98a  js      loc_18005ECA2
0x18005e990  sub     rbx, 8
0x18005e994  mov     pRegistrySd, rbx; this
0x18005e997  call    ??1?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>(void)
0x18005e99c  sub     rdi, 1
0x18005e9a0  jnz     short loc_18005E990
0x18005e9a2  xor     eax, eax
0x18005e9a4  mov     pRegistrySd, [rbp+50h+var_40]
0x18005e9a8  xor     pRegistrySd, rsp; StackCookie
0x18005e9ab  call    __security_check_cookie
0x18005e9b0  mov     rbx, [rsp+150h+arg_18]
0x18005e9b8  add     rsp, 120h
0x18005e9bf  pop     r15
0x18005e9c1  pop     r14
0x18005e9c3  pop     r13
0x18005e9c5  pop     r12
0x18005e9c7  pop     rdi
0x18005e9c8  pop     rsi
0x18005e9c9  pop     rbp
0x18005e9ca  retn
0x18005e9cb  call    cs:__imp_RtlIsMultiSessionSku
0x18005e9d1  test    al, al
0x18005e9d3  jnz     loc_18005E8E7
0x18005e9d9  cmp     r15d, 180001h
0x18005e9e0  jnz     loc_18005E8E7
0x18005e9e6  mov     r12b, 1
0x18005e9e9  jmp     loc_18005E8EA
0x18005e9ee  mov     r8b, 0Ah; nSubAuthorityCount
0x18005e9f1  mov     dword ptr [rbp+50h+appPackageAuthority.Value], 0
0x18005e9f8  lea     rdx, [rbp+50h+appPackageAuthority]; pIdentifierAuthority
0x18005e9fc  mov     word ptr [rbp+50h+appPackageAuthority.Value+4], 0F00h
0x18005ea02  lea     pRegistrySd, [rbp+50h+sidBuffer]; Sid
0x18005ea06  mov     [rsp+150h+lsaAttributes.Length], 3
0x18005ea0e  mov     dword ptr [rsp+150h+lsaAttributes+4], 400h
0x18005ea16  mov     dword ptr [rsp+150h+lsaAttributes.RootDirectory], 8F6027A1h
0x18005ea1e  mov     dword ptr [rsp+150h+lsaAttributes.RootDirectory+4], 3418BB9Ah
0x18005ea26  mov     dword ptr [rsp+150h+lsaAttributes.ObjectName], 0FF77B663h
0x18005ea2e  mov     dword ptr [rsp+150h+lsaAttributes.ObjectName+4], 6CB6D59Dh
0x18005ea36  mov     [rsp+150h+lsaAttributes.Attributes], 681A32E7h
0x18005ea3e  mov     dword ptr [rsp+150h+lsaAttributes+1Ch], 92435208h
0x18005ea46  mov     dword ptr [rsp+150h+lsaAttributes.SecurityDescriptor], 0D81FA686h
0x18005ea4e  mov     dword ptr [rsp+150h+lsaAttributes.SecurityDescriptor+4], 3B1B1798h
0x18005ea56  call    cs:__imp_InitializeSid
0x18005ea5c  test    eax, eax
0x18005ea5e  jz      loc_18005EBF5
0x18005ea64  lea     r14, [rbp+50h+newAces]
0x18005ea68  mov     esi, r13d
0x18005ea6b  lea     r14, [r14+rbx*8]
0x18005ea6f  mov     registrySdSize, esi; nSubAuthority
0x18005ea71  lea     pRegistrySd, [rbp+50h+sidBuffer]; pSid
0x18005ea75  call    cs:__imp_GetSidSubAuthority
0x18005ea7b  mov     ecx, esi
0x18005ea7d  inc     esi
0x18005ea7f  mov     registrySdSize, [rsp+pRegistrySd*4+150h+lsaAttributes.Length]; newAceOut
0x18005ea83  mov     [rax], registrySdSize
0x18005ea85  cmp     esi, 0Ah
0x18005ea88  jl      short loc_18005EA6F
0x18005ea8a  mov     ppSdOut, r14; pSid
0x18005ea8d  lea     pRegistrySd, [rbp+50h+sidBuffer]; pSid
0x18005ea91  call    ?CreateAccessAllowedAceFromSid@@YAJPEAXKAEAV?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z; CreateAccessAllowedAceFromSid(void *,ulong,wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> &)
0x18005ea96  mov     esi, eax
0x18005ea98  test    eax, eax
0x18005ea9a  jns     loc_18005EC14
0x18005eaa0  mov     pRegistrySd, [rbp+58h]; callerReturnAddress
0x18005eaa4  lea     ppSdOut, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005eaab  mov     r9d, eax; hr
0x18005eaae  mov     registrySdSize, 43h ; 'C'; lineNumber
0x18005eab3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eab8  mov     r9d, esi; hr
0x18005eabb  mov     registrySdSize, 1671h; lineNumber
0x18005eac0  mov     pRegistrySd, [rbp+58h]; callerReturnAddress
0x18005eac4  lea     ppSdOut, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005eacb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ead0  lea     r9, ??1?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ; __f
0x18005ead7  mov     ppSdOut, rdi; __n
0x18005eada  mov     registrySdSize, 8; __s
0x18005eadf  lea     pRegistrySd, [rbp+50h+newAces]; __t
0x18005eae3  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18005eae8  mov     eax, esi
0x18005eaea  jmp     loc_18005E9A4
0x18005eaef  test    r12b, r12b
0x18005eaf2  jnz     loc_18005E90C
0x18005eaf8  cmp     r15d, 180001h
0x18005eaff  jz      loc_18005E90C
0x18005eb05  cmp     [rsp+150h+sidBufferSize], 0
0x18005eb0a  jnz     loc_18005E90C
0x18005eb10  test    r14b, r14b
0x18005eb13  jnz     loc_18005E90C
0x18005eb19  test    al, al
0x18005eb1b  jnz     loc_18005E90C
0x18005eb21  mov     ppSdOut, [rsp+150h+var_108]; ppSdOut
0x18005eb26  mov     registrySdSize, esi; dwSdInSize
0x18005eb28  mov     pRegistrySd, [rsp+150h+pSdIn]; pSdIn
0x18005eb2d  call    ?CopySelfRelativeSd@@YAJPEAU_SECURITY_DESCRIPTOR_RELATIVE@@KPEAPEAU1@@Z; CopySelfRelativeSd(_SECURITY_DESCRIPTOR_RELATIVE *,ulong,_SECURITY_DESCRIPTOR_RELATIVE * *)
0x18005eb32  mov     ebx, eax
0x18005eb34  test    eax, eax
0x18005eb36  jns     loc_18005E9A2
0x18005eb3c  mov     pRegistrySd, [rbp+58h]; callerReturnAddress
0x18005eb40  lea     ppSdOut, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005eb47  mov     r9d, eax; hr
0x18005eb4a  mov     registrySdSize, 1654h; lineNumber
0x18005eb4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eb54  mov     eax, ebx
0x18005eb56  jmp     loc_18005E9A4
0x18005eb5b  cmp     r15d, 180001h
0x18005eb62  jz      loc_18005E8F2
0x18005eb68  xor     r14b, r14b
0x18005eb6b  jmp     loc_18005E8FD
0x18005eb70  lea     ppSdOut, [rbp+50h+newAces]; WellKnownSidType
0x18005eb74  mov     ecx, 54h ; 'T'; WellKnownSidType
0x18005eb79  call    ?CreateWellKnownAccessAllowedAce@@YAJW4WELL_KNOWN_SID_TYPE@@KAEAV?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z; CreateWellKnownAccessAllowedAce(WELL_KNOWN_SID_TYPE,ulong,wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> &)
0x18005eb7e  xor     r13d, r13d
0x18005eb81  mov     esi, eax
0x18005eb83  test    eax, eax
0x18005eb85  js      loc_18005EC3C
0x18005eb8b  lea     ebx, [r13+1]
0x18005eb8f  jmp     loc_18005E937
0x18005eb94  cmp     r15d, 180001h
0x18005eb9b  jz      loc_18005E8DB
0x18005eba1  test    r14d, r14d
0x18005eba4  jnz     loc_18005E8DB
0x18005ebaa  xor     r13b, r13b
0x18005ebad  jmp     loc_18005E8DE
0x18005ebb2  lea     ppSdOut, [rbp+50h+newAces]
0x18005ebb6  mov     ecx, 17h; WellKnownSidType
0x18005ebbb  lea     ppSdOut, [ppSdOut+rbx*8]; WellKnownSidType
0x18005ebbf  call    ?CreateWellKnownAccessAllowedAce@@YAJW4WELL_KNOWN_SID_TYPE@@KAEAV?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z; CreateWellKnownAccessAllowedAce(WELL_KNOWN_SID_TYPE,ulong,wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> &)
0x18005ebc4  mov     esi, eax
0x18005ebc6  test    eax, eax
0x18005ebc8  js      loc_18005EC6F
0x18005ebce  inc     rbx
0x18005ebd1  lea     ppSdOut, [rbp+50h+newAces]
0x18005ebd5  mov     ecx, 18h; WellKnownSidType
0x18005ebda  lea     ppSdOut, [ppSdOut+rbx*8]; WellKnownSidType
0x18005ebde  call    ?CreateWellKnownAccessAllowedAce@@YAJW4WELL_KNOWN_SID_TYPE@@KAEAV?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z; CreateWellKnownAccessAllowedAce(WELL_KNOWN_SID_TYPE,ulong,wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> &)
0x18005ebe3  mov     esi, eax
0x18005ebe5  test    eax, eax
0x18005ebe7  js      loc_18005ECD1
0x18005ebed  inc     rbx
0x18005ebf0  jmp     loc_18005E94D
0x18005ebf5  mov     pRegistrySd, [rbp+58h]; callerReturnAddress
0x18005ebf9  lea     ppSdOut, aOnecoreComComb_149; "onecore\\com\\combase\\common\\core\\se"...
0x18005ec00  mov     registrySdSize, 3Ch ; '<'; lineNumber
0x18005ec05  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005ec0a  mov     esi, eax
0x18005ec0c  test    eax, eax
0x18005ec0e  js      loc_18005EAB8
0x18005ec14  inc     rbx
0x18005ec17  jmp     loc_18005E961
0x18005ec1c  call    cs:__imp_RtlIsMultiSessionSku
0x18005ec22  test    al, al
0x18005ec24  jnz     loc_18005E8FD
0x18005ec2a  mov     al, r14b
0x18005ec2d  jmp     loc_18005E8FF
0x18005ec32  mov     [rsp+150h+pSdIn], rbx
0x18005ec37  jmp     loc_18005E8AE
0x18005ec3c  mov     pRegistrySd, [rbp+58h]; callerReturnAddress
0x18005ec40  lea     ppSdOut, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005ec47  mov     r9d, esi; hr
0x18005ec4a  mov     registrySdSize, 165Eh; lineNumber
0x18005ec4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ec54  lea     rbx, [rbp+50h+sidBuffer]
0x18005ec58  sub     rbx, 8
0x18005ec5c  mov     pRegistrySd, rbx; this
0x18005ec5f  call    ??1?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>(void)
0x18005ec64  sub     rdi, 1
0x18005ec68  jnz     short loc_18005EC58
0x18005ec6a  jmp     loc_18005EAE8
0x18005ec6f  mov     pRegistrySd, [rbp+58h]; callerReturnAddress
0x18005ec73  lea     ppSdOut, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005ec7a  mov     r9d, esi; hr
0x18005ec7d  mov     registrySdSize, 1666h; lineNumber
0x18005ec82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ec87  lea     rbx, [rbp+50h+sidBuffer]
0x18005ec8b  sub     rbx, 8
0x18005ec8f  mov     pRegistrySd, rbx; this
0x18005ec92  call    ??1?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>(void)
0x18005ec97  sub     rdi, 1
0x18005ec9b  jnz     short loc_18005EC8B
0x18005ec9d  jmp     loc_18005EAE8
0x18005eca2  mov     pRegistrySd, [rbp+58h]; callerReturnAddress
0x18005eca6  lea     ppSdOut, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005ecad  mov     r9d, esi; hr
0x18005ecb0  mov     registrySdSize, 1687h; lineNumber
0x18005ecb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ecba  sub     rbx, 8
0x18005ecbe  mov     pRegistrySd, rbx; this
0x18005ecc1  call    ??1?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>(void)
0x18005ecc6  sub     rdi, 1
0x18005ecca  jnz     short loc_18005ECBA
0x18005eccc  jmp     loc_18005EAE8
0x18005ecd1  mov     pRegistrySd, [rbp+58h]; callerReturnAddress
0x18005ecd5  lea     ppSdOut, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005ecdc  mov     r9d, esi; hr
0x18005ecdf  mov     registrySdSize, 1667h; lineNumber
0x18005ece4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ece9  lea     rbx, [rbp+50h+sidBuffer]
0x18005eced  sub     rbx, 8
0x18005ecf1  mov     pRegistrySd, rbx; this
0x18005ecf4  call    ??1?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>::~unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>(void)
0x18005ecf9  sub     rdi, 1
0x18005ecfd  jnz     short loc_18005ECED
0x18005ecff  jmp     loc_18005EAE8
0x18005ed04  lea     ppSdOut, [rbp+50h+newAces]
0x18005ed08  mov     ecx, 0Bh; WellKnownSidType
0x18005ed0d  lea     ppSdOut, [ppSdOut+rbx*8]; WellKnownSidType
0x18005ed11  call    ?CreateWellKnownAccessAllowedAce@@YAJW4WELL_KNOWN_SID_TYPE@@KAEAV?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z; CreateWellKnownAccessAllowedAce(WELL_KNOWN_SID_TYPE,ulong,wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> &)
0x18005ed16  mov     esi, eax
0x18005ed18  test    eax, eax
0x18005ed1a  jns     loc_18024785E
0x18005ed20  mov     registrySdSize, 1662h
0x18005ed25  jmp     loc_180247866
0x18005ed2a  lea     ppSdOut, [rbp+50h+newAces]
0x18005ed2e  mov     ecx, 11h; WellKnownSidType
0x18005ed33  lea     ppSdOut, [ppSdOut+rbx*8]; WellKnownSidType
0x18005ed37  call    ?CreateWellKnownAccessAllowedAce@@YAJW4WELL_KNOWN_SID_TYPE@@KAEAV?$unique_ptr@U_ACCESS_ALLOWED_ACE@@U?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z; CreateWellKnownAccessAllowedAce(WELL_KNOWN_SID_TYPE,ulong,wistd::unique_ptr<_ACCESS_ALLOWED_ACE,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> &)
0x18005ed3c  mov     esi, eax
0x18005ed3e  test    eax, eax
0x18005ed40  jns     loc_18024786E
0x18005ed46  mov     registrySdSize, 166Bh
0x18005ed4b  jmp     loc_180247866
0x18005ed50  xorps   xmm0, xmm0
0x18005ed53  mov     [rsp+150h+lsalookup.m_ptr], r13
0x18005ed58  lea     ppSdOut, [rsp+150h+lsalookup]; PolicyHandle
  ... truncated ...
```
