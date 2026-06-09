# DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(ushort *)

- ea: `0x18003a3ec`
- end: `0x18003a871`
- name: `?TakeKeyOwnership@ProviderManager@ProviderManagement@DAS@@CAJPEAG@Z`
- size: `1157`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180060c78`
- `0x180060ec0`

## callees

- `0x180021fc8`
- `0x18002a948`
- `0x18002aa34`
- `0x18003a3ec`
- `0x18003a878`
- `0x18003aa24`
- `0x18003aa4c`
- `0x18003d6a4`
- `0x180045df0`
- `0x18005ff48`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a465`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a465`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a5e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a7ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a80c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a5e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a7ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a80c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003a699`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003a699`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18003a599`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18003a599`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18003a4e8`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18003a761`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18003a4e8`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18003a761`

## string_xrefs

- `0x18003a5af`: `failed to get DACL`
- `0x18003a6bb`: `failed to modify ACL`
- `0x18003a777`: `Failed to change the DACL on the reg key`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(LPWSTR pObjectName)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  void *v5; // rbx
  const char *v6; // r9
  unsigned int LastError; // ebx
  int v8; // eax
  const char *v9; // r9
  DWORD v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  DWORD NamedSecurityInfoW; // eax
  unsigned int v14; // ebx
  HLOCAL v15; // rcx
  int v16; // eax
  DWORD v17; // ebx
  unsigned int v18; // ebx
  HLOCAL v19; // rcx
  int v20; // eax
  DWORD v21; // eax
  unsigned int v22; // ebx
  HLOCAL v23; // rcx
  int v24; // eax
  HLOCAL v25; // rcx
  int v26; // eax
  int psidGroup; // [rsp+20h] [rbp-98h]
  int psidGroupa; // [rsp+20h] [rbp-98h]
  int psidGroupb; // [rsp+20h] [rbp-98h]
  int psidGroupc; // [rsp+20h] [rbp-98h]
  int psidGroupd; // [rsp+20h] [rbp-98h]
  int psidGroupe; // [rsp+20h] [rbp-98h]
  PACL pDacl; // [rsp+28h] [rbp-90h]
  PACL pDacla; // [rsp+28h] [rbp-90h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+40h] [rbp-78h] BYREF
  PACL ppDacl; // [rsp+48h] [rbp-70h] BYREF
  HLOCAL *p_hMem; // [rsp+50h] [rbp-68h] BYREF
  PACL NewAcl; // [rsp+58h] [rbp-60h] BYREF
  char v39; // [rsp+60h] [rbp-58h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  void *v42; // [rsp+C8h] [rbp+10h] BYREF
  DWORD cbSid; // [rsp+D0h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp+20h] BYREF

  v2 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    BYTE1(v42) = 1;
    cbSid = 68;
    try
    {
      v5 = operator new[](0x44u);
      v42 = v5;
      if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v5, &cbSid) )
      {
        v10 = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 1u, v5, 0, 0, 0);
        if ( v10 )
        {
          v11 = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x3F5,
                  (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                  (const char *)v10,
                  (unsigned int)"falied to change %ls ownerhsip",
                  (const char *)pObjectName);
          std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v42);
          v12 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
          if ( v12 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x3E6,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
              (const char *)(unsigned int)v12,
              psidGroupa);
          result = v11;
        }
        else
        {
          ppDacl = 0;
          hMem = 0;
          ppSecurityDescriptor = 0;
          NamedSecurityInfoW = GetNamedSecurityInfoW(
                                 pObjectName,
                                 SE_REGISTRY_KEY,
                                 4u,
                                 0,
                                 0,
                                 &ppDacl,
                                 0,
                                 &ppSecurityDescriptor);
          if ( NamedSecurityInfoW )
          {
            v14 = wil::details::in1diag3::Return_Win32Msg(
                    retaddr,
                    (void *)0x402,
                    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                    (const char *)NamedSecurityInfoW,
                    (unsigned int)"failed to get DACL",
                    (const char *)pDacl);
            v15 = hMem;
            hMem = 0;
            if ( v15 )
              LocalFree(v15);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&ppSecurityDescriptor);
            std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v42);
            v16 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
            if ( v16 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x3E6,
                (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                (const char *)(unsigned int)v16,
                psidGroupb);
            result = v14;
          }
          else
          {
            memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
            *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 5;
            pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
            pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
            pListOfExplicitEntries.grfInheritance = 3;
            pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v5;
            p_hMem = &hMem;
            NewAcl = 0;
            v39 = 1;
            v17 = SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
            wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
            if ( v17 )
            {
              v18 = wil::details::in1diag3::Return_Win32Msg(
                      retaddr,
                      (void *)0x40E,
                      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                      (const char *)v17,
                      (unsigned int)"failed to modify ACL",
                      (const char *)pDacl);
              v19 = hMem;
              hMem = 0;
              if ( v19 )
                LocalFree(v19);
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&ppSecurityDescriptor);
              std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v42);
              v20 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
              if ( v20 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x3E6,
                  (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                  (const char *)(unsigned int)v20,
                  psidGroupc);
              result = v18;
            }
            else
            {
              v21 = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, (PACL)hMem, 0);
              if ( v21 )
              {
                v22 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0x416,
                        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                        (const char *)v21,
                        (unsigned int)"Failed to change the DACL on the reg key",
                        (const char *)pDacla);
                v23 = hMem;
                hMem = 0;
                if ( v23 )
                  LocalFree(v23);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&ppSecurityDescriptor);
                std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v42);
                v24 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
                if ( v24 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x3E6,
                    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                    (const char *)(unsigned int)v24,
                    psidGroupe);
                result = v22;
              }
              else
              {
                v25 = hMem;
                hMem = 0;
                if ( v25 )
                  LocalFree(v25);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&ppSecurityDescriptor);
                std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v42);
                v26 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
                if ( v26 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x3E6,
                    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                    (const char *)(unsigned int)v26,
                    psidGroupd);
                result = 0;
              }
            }
          }
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x3ED,
                      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                      v6);
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v42);
        v8 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
        if ( v8 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3E6,
            (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
            (const char *)(unsigned int)v8,
            psidGroup);
        result = LastError;
      }
    }
    catch ( ... )
    {
      LODWORD(v42) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x41A,
                       (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                       v9);
      return (unsigned int)v42;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
      (const char *)(unsigned int)v2,
      psidGroup);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18003a3ec  mov     [rsp+arg_0], rbx
0x18003a3f1  push    rsi
0x18003a3f2  push    rdi
0x18003a3f3  push    r15
0x18003a3f5  sub     rsp, 0A0h
0x18003a3fc  mov     rdi, rcx
0x18003a3ff  mov     cl, 1; bool
0x18003a401  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x18003a406  mov     ebx, eax
0x18003a408  xor     esi, esi
0x18003a40a  test    eax, eax
0x18003a40c  jns     short loc_18003A431
0x18003a40e  mov     rcx, [rsp+0B8h]; this
0x18003a416  mov     r9d, eax; char *
0x18003a419  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a420  mov     edx, 3E5h; void *
0x18003a425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a42a  mov     eax, ebx
0x18003a42c  jmp     loc_18003A85C
0x18003a431  mov     byte ptr [rsp+0B8h+arg_8+1], 1
0x18003a439  mov     ecx, 44h ; 'D'; unsigned __int64
0x18003a43e  mov     [rsp+0B8h+cbSid], ecx
0x18003a445  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003a44a  mov     rbx, rax
0x18003a44d  mov     [rsp+0C8h], rax
0x18003a455  lea     r9, [rsp+0B8h+cbSid]; cbSid
0x18003a45d  mov     r8, rax; pSid
0x18003a460  xor     edx, edx; DomainSid
0x18003a462  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18003a465  call    cs:__imp_CreateWellKnownSid
0x18003a46b  test    eax, eax
0x18003a46d  jnz     short loc_18003A4C6
0x18003a46f  mov     rcx, [rsp+0B8h]; this
0x18003a477  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a47e  mov     edx, 3EDh; void *
0x18003a483  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a488  mov     ebx, eax
0x18003a48a  lea     rcx, [rsp+0B8h+arg_8]
0x18003a492  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18003a497  nop
0x18003a498  xor     ecx, ecx; bool
0x18003a49a  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x18003a49f  mov     rcx, [rsp+0B8h]; this
0x18003a4a7  test    eax, eax
0x18003a4a9  jns     short loc_18003A4BF
0x18003a4ab  mov     r9d, eax; char *
0x18003a4ae  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a4b5  mov     edx, 3E6h; void *
0x18003a4ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a4bf  mov     eax, ebx
0x18003a4c1  jmp     loc_18003A85C
0x18003a4c6  mov     [rsp+0B8h+pSacl], rsi; pSacl
0x18003a4cb  mov     [rsp+0B8h+pDacl], rsi; pDacl
0x18003a4d0  mov     [rsp+0B8h+psidGroup], rsi; psidGroup
0x18003a4d5  mov     r9, rbx; psidOwner
0x18003a4d8  mov     r8d, 1; SecurityInfo
0x18003a4de  lea     r15d, [r8+3]
0x18003a4e2  mov     edx, r15d; ObjectType
0x18003a4e5  mov     rcx, rdi; pObjectName
0x18003a4e8  call    cs:__imp_SetNamedSecurityInfoW
0x18003a4ee  test    eax, eax
0x18003a4f0  jz      short loc_18003A55D
0x18003a4f2  mov     rcx, [rsp+0B8h]; this
0x18003a4fa  mov     [rsp+0B8h+pDacl], rdi; char *
0x18003a4ff  lea     rdx, aFaliedToChange; "falied to change %ls ownerhsip"
0x18003a506  mov     [rsp+0B8h+psidGroup], rdx; int
0x18003a50b  mov     r9d, eax; char *
0x18003a50e  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a515  mov     edx, 3F5h; void *
0x18003a51a  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003a51f  mov     ebx, eax
0x18003a521  lea     rcx, [rsp+0B8h+arg_8]
0x18003a529  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18003a52e  nop
0x18003a52f  xor     ecx, ecx; bool
0x18003a531  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x18003a536  mov     rcx, [rsp+0B8h]; this
0x18003a53e  test    eax, eax
0x18003a540  jns     short loc_18003A556
0x18003a542  mov     r9d, eax; char *
0x18003a545  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a54c  mov     edx, 3E6h; void *
0x18003a551  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a556  mov     eax, ebx
0x18003a558  jmp     loc_18003A85C
0x18003a55d  mov     [rsp+0B8h+ppDacl], rsi
0x18003a562  mov     [rsp+0B8h+hMem], rsi
0x18003a56a  mov     [rsp+0B8h+var_78], rsi
0x18003a56f  lea     rax, [rsp+0B8h+var_78]
0x18003a574  mov     [rsp+0B8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18003a579  mov     [rsp+0B8h+pSacl], rsi; ppSacl
0x18003a57e  lea     rax, [rsp+0B8h+ppDacl]
0x18003a583  mov     [rsp+0B8h+pDacl], rax; char *
0x18003a588  mov     [rsp+0B8h+psidGroup], rsi; ppsidGroup
0x18003a58d  xor     r9d, r9d; ppsidOwner
0x18003a590  mov     r8d, r15d; SecurityInfo
0x18003a593  mov     edx, r15d; ObjectType
0x18003a596  mov     rcx, rdi; pObjectName
0x18003a599  call    cs:__imp_GetNamedSecurityInfoW
0x18003a59f  test    eax, eax
0x18003a5a1  jz      loc_18003A632
0x18003a5a7  mov     rcx, [rsp+0B8h]; this
0x18003a5af  lea     rdx, aFailedToGetDac; "failed to get DACL"
0x18003a5b6  mov     [rsp+0B8h+psidGroup], rdx; int
0x18003a5bb  mov     r9d, eax; char *
0x18003a5be  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a5c5  mov     edx, 402h; void *
0x18003a5ca  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003a5cf  mov     ebx, eax
0x18003a5d1  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18003a5d9  mov     [rsp+0B8h+hMem], rsi
0x18003a5e1  test    rcx, rcx
0x18003a5e4  jz      short loc_18003A5EC
0x18003a5e6  call    cs:__imp_LocalFree
0x18003a5ec  lea     rcx, [rsp+0B8h+var_78]
0x18003a5f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003a5f6  lea     rcx, [rsp+0B8h+arg_8]
0x18003a5fe  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18003a603  nop
0x18003a604  xor     ecx, ecx; bool
0x18003a606  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x18003a60b  mov     rcx, [rsp+0B8h]; this
0x18003a613  test    eax, eax
0x18003a615  jns     short loc_18003A62B
0x18003a617  mov     r9d, eax; char *
0x18003a61a  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a621  mov     edx, 3E6h; void *
0x18003a626  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a62b  mov     eax, ebx
0x18003a62d  jmp     loc_18003A85C
0x18003a632  xorps   xmm0, xmm0
0x18003a635  movdqu  xmmword ptr [rsp+0B8h+pListOfExplicitEntries+0Ch], xmm0
0x18003a63b  mov     qword ptr [rsp+0B8h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18003a647  mov     [rsp+0B8h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18003a64f  mov     [rsp+0B8h+pListOfExplicitEntries.grfAccessMode], 2
0x18003a657  mov     [rsp+0B8h+pListOfExplicitEntries.grfInheritance], 3
0x18003a65f  mov     [rsp+0B8h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x18003a666  mov     [rsp+0B8h+pListOfExplicitEntries.Trustee.ptstrName], rbx
0x18003a66e  lea     rax, [rsp+0B8h+hMem]
0x18003a676  mov     [rsp+0B8h+var_68], rax
0x18003a67b  mov     [rsp+0B8h+NewAcl], rsi
0x18003a680  mov     [rsp+0B8h+var_58], 1
0x18003a685  lea     r9, [rsp+0B8h+NewAcl]; NewAcl
0x18003a68a  mov     r8, [rsp+0B8h+ppDacl]; OldAcl
0x18003a68f  lea     rdx, [rsp+0B8h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18003a694  mov     ecx, 1; cCountOfExplicitEntries
0x18003a699  call    cs:__imp_SetEntriesInAclW
0x18003a69f  mov     ebx, eax
0x18003a6a1  lea     rcx, [rsp+0B8h+var_68]
0x18003a6a6  call    ??1?$out_param_ptr_t@PEAPEAU_ACL@@V?$unique_ptr@U_ACL@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18003a6ab  test    ebx, ebx
0x18003a6ad  jz      loc_18003A73E
0x18003a6b3  mov     rcx, [rsp+0B8h]; this
0x18003a6bb  lea     rax, aFailedToModify; "failed to modify ACL"
0x18003a6c2  mov     [rsp+0B8h+psidGroup], rax; int
0x18003a6c7  mov     r9d, ebx; char *
0x18003a6ca  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a6d1  mov     edx, 40Eh; void *
0x18003a6d6  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003a6db  mov     ebx, eax
0x18003a6dd  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18003a6e5  mov     [rsp+0B8h+hMem], rsi
0x18003a6ed  test    rcx, rcx
0x18003a6f0  jz      short loc_18003A6F8
0x18003a6f2  call    cs:__imp_LocalFree
0x18003a6f8  lea     rcx, [rsp+0B8h+var_78]
0x18003a6fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003a702  lea     rcx, [rsp+0B8h+arg_8]
0x18003a70a  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18003a70f  nop
0x18003a710  xor     ecx, ecx; bool
0x18003a712  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x18003a717  mov     rcx, [rsp+0B8h]; this
0x18003a71f  test    eax, eax
0x18003a721  jns     short loc_18003A737
0x18003a723  mov     r9d, eax; char *
0x18003a726  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a72d  mov     edx, 3E6h; void *
0x18003a732  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a737  mov     eax, ebx
0x18003a739  jmp     loc_18003A85C
0x18003a73e  mov     [rsp+0B8h+pSacl], rsi; pSacl
0x18003a743  mov     rax, [rsp+0B8h+hMem]
0x18003a74b  mov     [rsp+0B8h+pDacl], rax; char *
0x18003a750  mov     [rsp+0B8h+psidGroup], rsi; int
0x18003a755  xor     r9d, r9d; psidOwner
0x18003a758  mov     r8d, r15d; SecurityInfo
0x18003a75b  mov     edx, r15d; ObjectType
0x18003a75e  mov     rcx, rdi; pObjectName
0x18003a761  call    cs:__imp_SetNamedSecurityInfoW
0x18003a767  test    eax, eax
0x18003a769  jz      loc_18003A7F7
0x18003a76f  mov     rcx, [rsp+0B8h]; this
0x18003a777  lea     rdx, aFailedToChange; "Failed to change the DACL on the reg ke"...
0x18003a77e  mov     [rsp+0B8h+psidGroup], rdx; int
0x18003a783  mov     r9d, eax; char *
0x18003a786  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a78d  mov     edx, 416h; void *
0x18003a792  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003a797  mov     ebx, eax
0x18003a799  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18003a7a1  mov     [rsp+0B8h+hMem], rsi
0x18003a7a9  test    rcx, rcx
0x18003a7ac  jz      short loc_18003A7B4
0x18003a7ae  call    cs:__imp_LocalFree
0x18003a7b4  lea     rcx, [rsp+0B8h+var_78]
0x18003a7b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003a7be  lea     rcx, [rsp+0B8h+arg_8]
0x18003a7c6  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18003a7cb  nop
0x18003a7cc  xor     ecx, ecx; bool
0x18003a7ce  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x18003a7d3  mov     rcx, [rsp+0B8h]; this
0x18003a7db  test    eax, eax
0x18003a7dd  jns     short loc_18003A7F3
0x18003a7df  mov     r9d, eax; char *
0x18003a7e2  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a7e9  mov     edx, 3E6h; void *
0x18003a7ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a7f3  mov     eax, ebx
0x18003a7f5  jmp     short loc_18003A85C
0x18003a7f7  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18003a7ff  mov     [rsp+0B8h+hMem], rsi
0x18003a807  test    rcx, rcx
0x18003a80a  jz      short loc_18003A812
0x18003a80c  call    cs:__imp_LocalFree
0x18003a812  lea     rcx, [rsp+0B8h+var_78]
0x18003a817  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003a81c  lea     rcx, [rsp+0B8h+arg_8]
0x18003a824  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18003a829  nop
0x18003a82a  xor     ecx, ecx; bool
0x18003a82c  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x18003a831  mov     rcx, [rsp+0B8h]; this
0x18003a839  test    eax, eax
0x18003a83b  jns     short loc_18003A851
0x18003a83d  mov     r9d, eax; char *
0x18003a840  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a847  mov     edx, 3E6h; void *
0x18003a84c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a851  xor     eax, eax
0x18003a853  jmp     short loc_18003A85C
0x18003a855  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x18003a85c  mov     rbx, [rsp+0B8h+arg_0]
0x18003a864  add     rsp, 0A0h
0x18003a86b  pop     r15
0x18003a86d  pop     rdi
0x18003a86e  pop     rsi
0x18003a86f  retn
```
