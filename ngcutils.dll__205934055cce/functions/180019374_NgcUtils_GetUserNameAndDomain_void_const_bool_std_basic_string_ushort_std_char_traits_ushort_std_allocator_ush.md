# NgcUtils::GetUserNameAndDomain(void * const,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,bool *)

- ea: `0x180019374`
- end: `0x180019cc7`
- name: `?GetUserNameAndDomain@NgcUtils@@YAJQEAX_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2PEA_N@Z`
- size: `2387`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180010f40`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000530d`
- `0x18000a5b4`
- `0x180013fe4`
- `0x180014458`
- `0x1800152c8`
- `0x180015bec`
- `0x18001643c`
- `0x180016a84`
- `0x180017f08`
- `0x1800185d0`
- `0x180019374`
- `0x180019cd0`
- `0x18001a850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001972a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001983a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001987c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001972a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001983a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001987c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cad`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001971c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180019821`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001971c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180019821`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800194c7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800194c7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids2` at `0x1800195a8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids2` at `0x1800195a8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800195cc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800195eb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019663`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019674`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019799`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800197aa`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800198b0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800198c1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800199af`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800199c0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800199ff`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019a10`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019ad8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019ae9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019bb5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019bc6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800195cc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800195eb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019663`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019674`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019799`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800197aa`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800198b0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800198c1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800199af`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800199c0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800199ff`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019a10`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019ad8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019ae9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019bb5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019bc6`

## string_xrefs

- `0x1800193af`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NgcUtils::GetUserNameAndDomain(NgcUtils *Sid, unsigned __int8 a2, __int64 a3, char *a4, _BYTE *a5)
{
  int v7; // r12d
  int UserAccountType; // eax
  bool *v10; // rdx
  __int64 v11; // rdx
  int updated; // eax
  __int64 v13; // rdx
  __int64 v15; // rdx
  enum _SID_NAME_USE v16; // eax
  enum _SID_NAME_USE v17; // edi
  signed int v18; // edi
  void *v19; // rcx
  void *v20; // rcx
  signed int v21; // eax
  unsigned int v22; // ebx
  LPWSTR v23; // r9
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // rdx
  char *v26; // r15
  __int64 v27; // rbx
  LPWSTR v28; // r9
  char *v29; // r14
  int v30; // edx
  unsigned __int64 v31; // rdx
  const void *v32; // r9
  char *v33; // rdi
  __int64 v34; // rbx
  unsigned __int16 *v35; // rcx
  unsigned __int64 v36; // rdx
  const void *v37; // r9
  char *v38; // rdi
  __int64 v39; // rbx
  signed int v40; // eax
  int v41; // edx
  unsigned int v42; // r8d
  signed int v43; // eax
  int v44; // edx
  unsigned int v45; // r8d
  signed int v46; // eax
  int v47; // edx
  unsigned int v48; // r8d
  signed int v49; // eax
  int v50; // edx
  unsigned int v51; // r8d
  signed int v52; // eax
  int v53; // edx
  unsigned int v54; // r8d
  signed int LastError; // eax
  int v56; // edx
  unsigned int v57; // r8d
  signed int v58; // eax
  int v59; // edx
  unsigned int v60; // r8d
  signed int v61; // eax
  int v62; // edx
  unsigned int v63; // r8d
  int ReferencedDomains; // [rsp+20h] [rbp-E0h]
  _BYTE v65[4]; // [rsp+30h] [rbp-D0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v67; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchName; // [rsp+3Ch] [rbp-C4h] BYREF
  void **v69; // [rsp+40h] [rbp-C0h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-B8h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v72; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR Name; // [rsp+68h] [rbp-98h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST v75; // [rsp+70h] [rbp-90h] BYREF
  char v76; // [rsp+78h] [rbp-88h]
  PSID Sids; // [rsp+80h] [rbp-80h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+B8h] [rbp-48h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+C0h] [rbp-40h] BYREF
  char v81; // [rsp+C8h] [rbp-38h]
  enum _SID_NAME_USE *p_peUse; // [rsp+D8h] [rbp-28h]
  __int64 v83; // [rsp+E0h] [rbp-20h]
  _BYTE v84[32]; // [rsp+F0h] [rbp-10h] BYREF
  enum _SID_NAME_USE *v85; // [rsp+110h] [rbp+10h]
  __int64 v86; // [rsp+118h] [rbp+18h]
  unsigned int *v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v7 = a2;
  if ( a2 )
  {
    cchName = 0;
    UserAccountType = NgcUtils::GetUserAccountType(Sid, &cchName, (enum NgcUserAccountType *)a3);
    if ( UserAccountType < 0 )
    {
      v11 = 529;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)(unsigned int)UserAccountType,
        ReferencedDomains);
      goto LABEL_5;
    }
    v65[0] = 0;
    UserAccountType = NgcUtils::IsCloudTrustEnabled((NgcUtils *)v65, v10);
    if ( UserAccountType < 0 )
    {
      v11 = 532;
      goto LABEL_4;
    }
    if ( cchName == 3 && v65[0] )
      return NgcUtils::GetUserNameAndDomainForHybridCloudTrust(Sid, v15, a3, (__int64)a4, a5);
  }
LABEL_5:
  updated = NgcUtils::Detail::CacheUpdateVersion(Sid);
  if ( updated < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)updated,
      ReferencedDomains);
  LOBYTE(v13) = v7;
  if ( (int)NgcUtils::Detail::CacheGetUserNameAndDomain(Sid, v13, a3, a4) >= 0 )
  {
    if ( a5 )
      *a5 = 1;
    return 0;
  }
  if ( a5 )
    *a5 = 0;
  v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v16 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &PolicyHandle);
  v17 = v16;
  if ( v16 < 0 )
  {
    if ( (unsigned int)dword_180075000 > 2 )
    {
      peUse = v16;
      p_peUse = &peUse;
      v83 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180075000, &dword_1800689DC, 0, 0, 3, &ReferencedDomainName);
    }
    v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
    if ( PolicyHandle && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(&v69) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v56, v57);
      __debugbreak();
    }
    return (unsigned int)(v17 | 0x10000000);
  }
  Sids = Sid;
  v72 = 0;
  Buffer = 0;
  ReferencedDomainName = (LPWSTR)&Buffer;
  Names = 0;
  v81 = 1;
  Name = (LPWSTR)&v72;
  v75 = 0;
  v76 = 1;
  v17 = LsaLookupSids2(PolicyHandle, v7 << 30, 1u, &Sids, &v75, &Names);
  if ( v76 )
  {
    v19 = *(void **)Name;
    *(_QWORD *)Name = v75;
    if ( v19 )
      LsaFreeMemory(v19);
  }
  if ( v81 )
  {
    v20 = *(void **)ReferencedDomainName;
    *(_QWORD *)ReferencedDomainName = Names;
    if ( v20 )
      LsaFreeMemory(v20);
  }
  if ( v17 >= 0 )
  {
    if ( *(_DWORD *)Buffer > 8u || (v30 = 424, !_bittest(&v30, *(_DWORD *)Buffer)) )
    {
      v31 = (unsigned __int64)*((unsigned __int16 *)Buffer + 4) >> 1;
      v32 = (const void *)*((_QWORD *)Buffer + 2);
      if ( v31 > *(_QWORD *)(a3 + 24) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a3);
      }
      else
      {
        if ( *(_QWORD *)(a3 + 24) <= 7u )
          v33 = (char *)a3;
        else
          v33 = *(char **)a3;
        *(_QWORD *)(a3 + 16) = v31;
        v34 = 2 * v31;
        memmove_0(v33, v32, 2 * v31);
        *(_WORD *)&v33[v34] = 0;
      }
      v35 = (unsigned __int16 *)*((_QWORD *)v72 + 1);
      v36 = (unsigned __int64)*v35 >> 1;
      v37 = (const void *)*((_QWORD *)v35 + 1);
      if ( v36 > *((_QWORD *)a4 + 3) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a4);
      }
      else
      {
        if ( *((_QWORD *)a4 + 3) <= 7u )
          v38 = a4;
        else
          v38 = *(char **)a4;
        *((_QWORD *)a4 + 2) = v36;
        v39 = 2 * v36;
        memmove_0(v38, v37, 2 * v36);
        *(_WORD *)&v38[v39] = 0;
      }
      if ( Buffer )
        LsaFreeMemory(Buffer);
      if ( v72 )
        LsaFreeMemory(v72);
      v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
      if ( PolicyHandle
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(&v69) )
      {
        v52 = GetLastError();
        if ( v52 > 0 )
          v52 = (unsigned __int16)v52 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v52, v53, v54);
        __debugbreak();
      }
      return 0;
    }
    if ( (unsigned int)dword_180075000 > 2 )
    {
      v67 = *(_DWORD *)Buffer;
      peUse = -2147024809;
      v87 = &v67;
      v88 = 4;
      v85 = &peUse;
      v86 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180075000, byte_1800688F5, 0, 0, 4, v84);
    }
    if ( Buffer )
      LsaFreeMemory(Buffer);
    if ( v72 )
      LsaFreeMemory(v72);
    v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
    if ( PolicyHandle && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(&v69) )
    {
      v40 = GetLastError();
      if ( v40 > 0 )
        v40 = (unsigned __int16)v40 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v40, v41, v42);
      __debugbreak();
    }
    return 2147942487LL;
  }
  else
  {
    if ( (unsigned int)(v17 + 1073741428) > 1 )
    {
      if ( (unsigned int)dword_180075000 > 2 )
      {
        peUse = v17;
        p_peUse = &peUse;
        v83 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180075000, word_18006892A, 0, 0, 3, &ReferencedDomainName);
      }
      if ( Buffer )
        LsaFreeMemory(Buffer);
      if ( v72 )
        LsaFreeMemory(v72);
      v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
      if ( PolicyHandle
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(&v69) )
      {
        v43 = GetLastError();
        if ( v43 > 0 )
          v43 = (unsigned __int16)v43 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v43, v44, v45);
        __debugbreak();
      }
      return (unsigned int)(v17 | 0x10000000);
    }
    if ( (unsigned int)dword_180075000 > 3 )
    {
      v67 = v17;
      v85 = (enum _SID_NAME_USE *)&v67;
      v86 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180075000, &dword_1800689AC, 0, 0, 3, v84);
    }
    cchName = 0;
    cchReferencedDomainName = 0;
    peUse = SidTypeInvalid;
    if ( LookupAccountSidLocalW(Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
    {
      if ( Buffer )
        LsaFreeMemory(Buffer);
      if ( v72 )
        LsaFreeMemory(v72);
      v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
      if ( PolicyHandle
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(&v69) )
      {
        v61 = GetLastError();
        if ( v61 > 0 )
          v61 = (unsigned __int16)v61 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v61, v62, v63);
        JUMPOUT(0x180019CC6LL);
      }
      return 2147549183LL;
    }
    else
    {
      v18 = GetLastError();
      if ( v18 != 122 )
      {
        if ( (unsigned int)dword_180075000 > 2 )
        {
          v67 = v18;
          v85 = (enum _SID_NAME_USE *)&v67;
          v86 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_180075000, &word_18006897E, 0, 0, 3, v84);
        }
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        if ( Buffer )
          LsaFreeMemory(Buffer);
        if ( v72 )
          LsaFreeMemory(v72);
        v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
        if ( PolicyHandle
          && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(&v69) )
        {
          v46 = GetLastError();
          if ( v46 > 0 )
            v46 = (unsigned __int16)v46 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v46, v47, v48);
          __debugbreak();
        }
        return (unsigned int)v18;
      }
      std::vector<unsigned short>::vector<unsigned short>(&Name, cchName);
      std::vector<unsigned short>::vector<unsigned short>(&ReferencedDomainName, cchReferencedDomainName);
      if ( LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        v23 = Name;
        v24 = -1;
        v25 = -1;
        do
          ++v25;
        while ( Name[v25] );
        if ( v25 > *(_QWORD *)(a3 + 24) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a3);
        }
        else
        {
          if ( *(_QWORD *)(a3 + 24) <= 7u )
            v26 = (char *)a3;
          else
            v26 = *(char **)a3;
          *(_QWORD *)(a3 + 16) = v25;
          v27 = 2 * v25;
          memmove_0(v26, v23, 2 * v25);
          *(_WORD *)&v26[v27] = 0;
        }
        v28 = ReferencedDomainName;
        do
          ++v24;
        while ( ReferencedDomainName[v24] );
        if ( v24 > *((_QWORD *)a4 + 3) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a4);
        }
        else
        {
          if ( *((_QWORD *)a4 + 3) <= 7u )
            v29 = a4;
          else
            v29 = *(char **)a4;
          *((_QWORD *)a4 + 2) = v24;
          memmove_0(v29, v28, 2 * v24);
          *(_WORD *)&v29[2 * v24] = 0;
        }
        std::vector<unsigned short>::~vector<unsigned short>(&ReferencedDomainName);
        std::vector<unsigned short>::~vector<unsigned short>(&Name);
        if ( Buffer )
          LsaFreeMemory(Buffer);
        if ( v72 )
          LsaFreeMemory(v72);
        v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
        if ( PolicyHandle
          && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(&v69) )
        {
          v49 = GetLastError();
          if ( v49 > 0 )
            v49 = (unsigned __int16)v49 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v49, v50, v51);
          __debugbreak();
        }
        return 0;
      }
      if ( (unsigned int)dword_180075000 > 2 )
      {
        v67 = GetLastError();
        v85 = (enum _SID_NAME_USE *)&v67;
        v86 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180075000, &unk_180068950, 0, 0, 3, v84);
      }
      v21 = GetLastError();
      v22 = v21;
      if ( v21 > 0 )
        v22 = (unsigned __int16)v21 | 0x80070000;
      std::vector<unsigned short>::~vector<unsigned short>(&ReferencedDomainName);
      std::vector<unsigned short>::~vector<unsigned short>(&Name);
      if ( Buffer )
        LsaFreeMemory(Buffer);
      if ( v72 )
        LsaFreeMemory(v72);
      v69 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
      if ( PolicyHandle
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(&v69) )
      {
        v58 = GetLastError();
        if ( v58 > 0 )
          v58 = (unsigned __int16)v58 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v58, v59, v60);
        __debugbreak();
      }
      return v22;
    }
  }
}

```

## disassembly

```asm
0x180019374  push    rbp
0x180019376  push    rbx
0x180019377  push    rsi
0x180019378  push    rdi
0x180019379  push    r12
0x18001937b  push    r13
0x18001937d  push    r14
0x18001937f  push    r15
0x180019381  lea     rbp, [rsp-48h]
0x180019386  sub     rsp, 148h
0x18001938d  mov     rax, cs:__security_cookie
0x180019394  xor     rax, rsp
0x180019397  mov     [rbp+80h+var_50], rax
0x18001939b  mov     rsi, r9
0x18001939e  mov     r14, r8
0x1800193a1  movzx   r12d, dl
0x1800193a5  mov     r15, rcx
0x1800193a8  mov     rbx, [rbp+80h+arg_20]
0x1800193af  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800193b6  xor     r13d, r13d
0x1800193b9  test    dl, dl
0x1800193bb  jz      short loc_1800193E7
0x1800193bd  mov     [rsp+180h+cchName], r13d
0x1800193c2  lea     rdx, [rsp+180h+cchName]; void *
0x1800193c7  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x1800193cc  test    eax, eax
0x1800193ce  jns     short loc_180019446
0x1800193d0  mov     edx, 211h; void *
0x1800193d5  mov     r8, rdi; unsigned int
0x1800193d8  mov     r9d, eax; char *
0x1800193db  mov     rcx, [rbp+88h]; this
0x1800193e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800193e7  call    ?CacheUpdateVersion@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheUpdateVersion(void)
0x1800193ec  test    eax, eax
0x1800193ee  jns     short loc_180019407
0x1800193f0  mov     rcx, [rbp+88h]; this
0x1800193f7  mov     r9d, eax; char *
0x1800193fa  mov     r8, rdi; unsigned int
0x1800193fd  mov     edx, 22Ah; void *
0x180019402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019407  mov     r9, rsi
0x18001940a  mov     r8, r14
0x18001940d  mov     dl, r12b
0x180019410  mov     rcx, r15
0x180019413  call    ?CacheGetUserNameAndDomain@Detail@NgcUtils@@YAJQEAX_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; NgcUtils::Detail::CacheGetUserNameAndDomain(void * const,bool,std::wstring *,std::wstring *)
0x180019418  test    eax, eax
0x18001941a  js      short loc_18001948E
0x18001941c  test    rbx, rbx
0x18001941f  jz      short loc_180019424
0x180019421  mov     byte ptr [rbx], 1
0x180019424  xor     eax, eax
0x180019426  mov     rcx, [rbp+80h+var_50]
0x18001942a  xor     rcx, rsp; StackCookie
0x18001942d  call    __security_check_cookie
0x180019432  add     rsp, 148h
0x180019439  pop     r15
0x18001943b  pop     r14
0x18001943d  pop     r13
0x18001943f  pop     r12
0x180019441  pop     rdi
0x180019442  pop     rsi
0x180019443  pop     rbx
0x180019444  pop     rbp
0x180019445  retn
0x180019446  mov     [rsp+180h+var_150], r13b
0x18001944b  lea     rcx, [rsp+180h+var_150]; this
0x180019450  call    ?IsCloudTrustEnabled@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsCloudTrustEnabled(bool *)
0x180019455  test    eax, eax
0x180019457  jns     short loc_180019463
0x180019459  mov     edx, 214h
0x18001945e  jmp     loc_1800193D5
0x180019463  cmp     [rsp+180h+cchName], 3
0x180019468  jnz     loc_1800193E7
0x18001946e  cmp     [rsp+180h+var_150], r13b
0x180019473  jz      loc_1800193E7
0x180019479  mov     [rsp+180h+ReferencedDomains], rbx; __int64
0x18001947e  mov     r9, rsi
0x180019481  mov     r8, r14
0x180019484  mov     rcx, r15; Sid
0x180019487  call    NgcUtils__GetUserNameAndDomainForHybridCloudTrust
0x18001948c  jmp     short loc_180019426
0x18001948e  test    rbx, rbx
0x180019491  jz      short loc_180019496
0x180019493  mov     [rbx], r13b
0x180019496  lea     rbx, ??_7?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable'
0x18001949d  mov     [rsp+180h+var_140], rbx
0x1800194a2  mov     [rsp+180h+PolicyHandle], r13
0x1800194a7  xorps   xmm0, xmm0
0x1800194aa  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x1800194ae  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x1800194b2  movups  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800194b6  lea     r9, [rsp+180h+PolicyHandle]; PolicyHandle
0x1800194bb  mov     r8d, 801h; DesiredAccess
0x1800194c1  lea     rdx, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x1800194c5  xor     ecx, ecx; SystemName
0x1800194c7  call    cs:__imp_LsaOpenPolicy
0x1800194cd  mov     edi, eax
0x1800194cf  test    eax, eax
0x1800194d1  jns     short loc_18001954D
0x1800194d3  mov     ecx, cs:dword_180075000
0x1800194d9  cmp     ecx, 2
0x1800194dc  jbe     short loc_180019524
0x1800194de  mov     [rsp+180h+peUse], eax
0x1800194e2  lea     rax, [rsp+180h+peUse]
0x1800194e7  mov     [rbp+80h+var_A8], rax
0x1800194eb  mov     [rbp+80h+var_A0], 4
0x1800194f3  lea     rax, [rbp+80h+ReferencedDomainName]
0x1800194f7  mov     [rsp+180h+Names], rax
0x1800194fc  mov     dword ptr [rsp+180h+ReferencedDomains], 3
0x180019504  xor     r9d, r9d
0x180019507  xor     r8d, r8d
0x18001950a  lea     rdx, dword_1800689DC
0x180019511  lea     rcx, dword_180075000
0x180019518  call    _tlgWriteTransfer_EventWriteTransfer
0x18001951d  lea     rbx, ??_7?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable'
0x180019524  mov     [rsp+180h+var_140], rbx
0x180019529  cmp     [rsp+180h+PolicyHandle], r13
0x18001952e  jz      short loc_180019542
0x180019530  lea     rcx, [rsp+180h+var_140]
0x180019535  call    ?InternalClose@?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(void)
0x18001953a  test    al, al
0x18001953c  jz      loc_180019C79
0x180019542  bts     edi, 1Ch
0x180019546  mov     eax, edi
0x180019548  jmp     loc_180019426
0x18001954d  mov     [rbp+80h+Sids], r15
0x180019551  mov     [rsp+180h+var_128], r13
0x180019556  mov     [rsp+180h+Buffer], r13
0x18001955b  lea     rax, [rsp+180h+Buffer]
0x180019560  mov     [rbp+80h+ReferencedDomainName], rax
0x180019564  mov     [rbp+80h+var_C0], r13
0x180019568  mov     [rbp+80h+var_B8], 1
0x18001956c  lea     rax, [rsp+180h+var_128]
0x180019571  mov     [rsp+180h+Name], rax
0x180019576  mov     [rsp+180h+var_110], r13
0x18001957b  mov     [rsp+180h+var_108], 1
0x180019580  mov     edx, r12d
0x180019583  shl     edx, 1Eh; LookupOptions
0x180019586  lea     rax, [rbp+80h+var_C0]
0x18001958a  mov     [rsp+180h+Names], rax; Names
0x18001958f  lea     rax, [rsp+180h+var_110]
0x180019594  mov     [rsp+180h+ReferencedDomains], rax; ReferencedDomains
0x180019599  lea     r9, [rbp+80h+Sids]; Sids
0x18001959d  mov     r8d, 1; Count
0x1800195a3  mov     rcx, [rsp+180h+PolicyHandle]; PolicyHandle
0x1800195a8  call    cs:__imp_LsaLookupSids2
0x1800195ae  mov     edi, eax
0x1800195b0  cmp     [rsp+180h+var_108], r13b
0x1800195b5  jz      short loc_1800195D2
0x1800195b7  mov     r8, [rsp+180h+Name]
0x1800195bc  mov     rcx, [r8]; Buffer
0x1800195bf  mov     rdx, [rsp+180h+var_110]
0x1800195c4  mov     [r8], rdx
0x1800195c7  test    rcx, rcx
0x1800195ca  jz      short loc_1800195D2
0x1800195cc  call    cs:__imp_LsaFreeMemory
0x1800195d2  cmp     [rbp+80h+var_B8], r13b
0x1800195d6  jz      short loc_1800195F1
0x1800195d8  mov     rdx, [rbp+80h+ReferencedDomainName]
0x1800195dc  mov     rcx, [rdx]; Buffer
0x1800195df  mov     rax, [rbp+80h+var_C0]
0x1800195e3  mov     [rdx], rax
0x1800195e6  test    rcx, rcx
0x1800195e9  jz      short loc_1800195F1
0x1800195eb  call    cs:__imp_LsaFreeMemory
0x1800195f1  test    edi, edi
0x1800195f3  jns     loc_180019A46
0x1800195f9  lea     eax, [rdi+3FFFFE74h]
0x1800195ff  cmp     eax, 1
0x180019602  mov     eax, cs:dword_180075000
0x180019608  jbe     loc_1800196A2
0x18001960e  cmp     eax, 2
0x180019611  jbe     short loc_180019659
0x180019613  mov     [rsp+180h+peUse], edi
0x180019617  lea     rax, [rsp+180h+peUse]
0x18001961c  mov     [rbp+80h+var_A8], rax
0x180019620  mov     [rbp+80h+var_A0], 4
0x180019628  lea     rax, [rbp+80h+ReferencedDomainName]
0x18001962c  mov     [rsp+180h+Names], rax
0x180019631  mov     dword ptr [rsp+180h+ReferencedDomains], 3
0x180019639  xor     r9d, r9d
0x18001963c  xor     r8d, r8d
0x18001963f  lea     rdx, word_18006892A
0x180019646  lea     rcx, dword_180075000
0x18001964d  call    _tlgWriteTransfer_EventWriteTransfer
0x180019652  lea     rbx, ??_7?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable'
0x180019659  mov     rcx, [rsp+180h+Buffer]; Buffer
0x18001965e  test    rcx, rcx
0x180019661  jz      short loc_18001966A
0x180019663  call    cs:__imp_LsaFreeMemory
0x180019669  nop
0x18001966a  mov     rcx, [rsp+180h+var_128]; Buffer
0x18001966f  test    rcx, rcx
0x180019672  jz      short loc_18001967B
0x180019674  call    cs:__imp_LsaFreeMemory
0x18001967a  nop
0x18001967b  mov     [rsp+180h+var_140], rbx
0x180019680  cmp     [rsp+180h+PolicyHandle], r13
0x180019685  jz      loc_180019542
0x18001968b  lea     rcx, [rsp+180h+var_140]
0x180019690  call    ?InternalClose@?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(void)
0x180019695  test    al, al
0x180019697  jz      loc_180019C11
0x18001969d  jmp     loc_180019542
0x1800196a2  mov     r12d, 3
0x1800196a8  cmp     eax, r12d
0x1800196ab  jbe     short loc_1800196E9
0x1800196ad  mov     [rsp+180h+var_148], edi
0x1800196b1  lea     rax, [rsp+180h+var_148]
0x1800196b6  mov     [rbp+80h+var_70], rax
0x1800196ba  mov     [rbp+80h+var_68], 4
0x1800196c2  lea     rax, [rbp+80h+var_90]
0x1800196c6  mov     [rsp+180h+Names], rax
0x1800196cb  mov     dword ptr [rsp+180h+ReferencedDomains], r12d
0x1800196d0  xor     r9d, r9d
0x1800196d3  xor     r8d, r8d
0x1800196d6  lea     rdx, dword_1800689AC
0x1800196dd  lea     rcx, dword_180075000
0x1800196e4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800196e9  mov     [rsp+180h+cchName], r13d
0x1800196ee  mov     [rsp+180h+cchReferencedDomainName], r13d
0x1800196f3  mov     [rsp+180h+peUse], 7
0x1800196fb  lea     rax, [rsp+180h+peUse]
0x180019700  mov     [rsp+180h+Names], rax; peUse
0x180019705  lea     rax, [rsp+180h+cchReferencedDomainName]
0x18001970a  mov     [rsp+180h+ReferencedDomains], rax; cchReferencedDomainName
0x18001970f  xor     r9d, r9d; ReferencedDomainName
0x180019712  lea     r8, [rsp+180h+cchName]; cchName
0x180019717  xor     edx, edx; Name
0x180019719  mov     rcx, r15; Sid
0x18001971c  call    cs:__imp_LookupAccountSidLocalW
0x180019722  test    eax, eax
0x180019724  jnz     loc_1800199F5
0x18001972a  call    cs:__imp_GetLastError
0x180019730  mov     edi, eax
0x180019732  cmp     eax, 7Ah ; 'z'
0x180019735  jz      loc_1800197DF
0x18001973b  mov     eax, cs:dword_180075000
0x180019741  cmp     eax, 2
0x180019744  jbe     short loc_180019782
0x180019746  mov     [rsp+180h+var_148], edi
0x18001974a  lea     rax, [rsp+180h+var_148]
0x18001974f  mov     [rbp+80h+var_70], rax
0x180019753  mov     [rbp+80h+var_68], 4
0x18001975b  lea     rax, [rbp+80h+var_90]
0x18001975f  mov     [rsp+180h+Names], rax
0x180019764  mov     dword ptr [rsp+180h+ReferencedDomains], r12d
0x180019769  xor     r9d, r9d
0x18001976c  xor     r8d, r8d
0x18001976f  lea     rdx, word_18006897E
0x180019776  lea     rcx, dword_180075000
0x18001977d  call    _tlgWriteTransfer_EventWriteTransfer
0x180019782  test    edi, edi
0x180019784  jle     short loc_18001978F
0x180019786  movzx   edi, di
0x180019789  or      edi, 80070000h
0x18001978f  mov     rcx, [rsp+180h+Buffer]; Buffer
0x180019794  test    rcx, rcx
0x180019797  jz      short loc_1800197A0
0x180019799  call    cs:__imp_LsaFreeMemory
0x18001979f  nop
0x1800197a0  mov     rcx, [rsp+180h+var_128]; Buffer
0x1800197a5  test    rcx, rcx
0x1800197a8  jz      short loc_1800197B1
0x1800197aa  call    cs:__imp_LsaFreeMemory
0x1800197b0  nop
0x1800197b1  lea     rax, ??_7?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable'
0x1800197b8  mov     [rsp+180h+var_140], rax
0x1800197bd  cmp     [rsp+180h+PolicyHandle], r13
0x1800197c2  jz      loc_180019546
0x1800197c8  lea     rcx, [rsp+180h+var_140]
0x1800197cd  call    ?InternalClose@?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(void)
0x1800197d2  test    al, al
0x1800197d4  jz      loc_180019C2B
0x1800197da  jmp     loc_180019546
0x1800197df  mov     edx, [rsp+180h+cchName]
0x1800197e3  lea     rcx, [rsp+180h+Name]
0x1800197e8  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x1800197ed  nop
0x1800197ee  mov     edx, [rsp+180h+cchReferencedDomainName]
0x1800197f2  lea     rcx, [rbp+80h+ReferencedDomainName]
0x1800197f6  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x1800197fb  nop
0x1800197fc  lea     rax, [rsp+180h+peUse]
0x180019801  mov     [rsp+180h+Names], rax; peUse
0x180019806  lea     rax, [rsp+180h+cchReferencedDomainName]
0x18001980b  mov     [rsp+180h+ReferencedDomains], rax; cchReferencedDomainName
0x180019810  mov     r9, [rbp+80h+ReferencedDomainName]; ReferencedDomainName
0x180019814  lea     r8, [rsp+180h+cchName]; cchName
0x180019819  mov     rdx, [rsp+180h+Name]; Name
0x18001981e  mov     rcx, r15; Sid
0x180019821  call    cs:__imp_LookupAccountSidLocalW
0x180019827  test    eax, eax
0x180019829  jnz     loc_1800198F4
0x18001982f  mov     eax, cs:dword_180075000
0x180019835  cmp     eax, 2
0x180019838  jbe     short loc_18001987C
0x18001983a  call    cs:__imp_GetLastError
0x180019840  mov     [rsp+180h+var_148], eax
0x180019844  lea     rax, [rsp+180h+var_148]
  ... truncated ...
```
