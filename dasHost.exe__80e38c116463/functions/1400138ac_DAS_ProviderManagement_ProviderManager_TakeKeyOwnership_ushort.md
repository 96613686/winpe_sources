# DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(ushort *)

- ea: `0x1400138ac`
- end: `0x140013d31`
- name: `?TakeKeyOwnership@ProviderManager@ProviderManagement@DAS@@CAJPEAG@Z`
- size: `1157`
- prototype: `__int64 __fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400128a0`

## callees

- `0x1400018d4`
- `0x140002214`
- `0x140006cc4`
- `0x140006ce4`
- `0x140011cc8`
- `0x1400137b8`
- `0x1400138ac`
- `0x14001450c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013a81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013b5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013ba8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013c69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013ccc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013a81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013b5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013ba8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013c69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013ccc`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140013923`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140013923`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140013aa1`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140013bc8`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140013c89`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140013cec`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140013aa1`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140013bc8`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140013c89`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140013cec`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x140013994`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x140013c1c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x140013994`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x140013c1c`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x140013a34`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x140013a34`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140013b37`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140013b37`

## string_xrefs

- `0x140013a4a`: `failed to get DACL`
- `0x140013b71`: `failed to modify ACL`
- `0x140013c32`: `Failed to change the DACL on the reg key`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(WCHAR *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  void *v5; // rbx
  const char *v6; // r9
  unsigned int LastError; // edi
  unsigned __int64 v8; // rdx
  int v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  DWORD v13; // eax
  unsigned int v14; // edi
  unsigned __int64 v15; // rdx
  int v16; // eax
  void *v17; // rdx
  DWORD NamedSecurityInfoW; // eax
  unsigned __int64 v19; // rdx
  unsigned int v20; // edi
  HLOCAL v21; // rcx
  int v22; // eax
  void *v23; // rdx
  DWORD v24; // esi
  HLOCAL v25; // rcx
  unsigned __int64 v26; // rdx
  unsigned int v27; // edi
  HLOCAL v28; // rcx
  int v29; // eax
  void *v30; // rdx
  DWORD v31; // eax
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rdx
  unsigned int v34; // edi
  HLOCAL v35; // rcx
  int v36; // eax
  void *v37; // rdx
  HLOCAL v38; // rcx
  int v39; // eax
  void *v40; // rdx
  int psidGroup; // [rsp+20h] [rbp-A8h]
  int psidGroupa; // [rsp+20h] [rbp-A8h]
  int psidGroupb; // [rsp+20h] [rbp-A8h]
  int psidGroupc; // [rsp+20h] [rbp-A8h]
  int psidGroupd; // [rsp+20h] [rbp-A8h]
  int psidGroupe; // [rsp+20h] [rbp-A8h]
  PACL pDacl; // [rsp+28h] [rbp-A0h]
  PACL pDacla; // [rsp+28h] [rbp-A0h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+40h] [rbp-88h] BYREF
  PACL ppDacl; // [rsp+48h] [rbp-80h] BYREF
  HLOCAL *p_hMem; // [rsp+50h] [rbp-78h]
  PACL NewAcl; // [rsp+58h] [rbp-70h] BYREF
  char v53; // [rsp+60h] [rbp-68h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+D8h] [rbp+10h] BYREF
  DWORD cbSid; // [rsp+E0h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+E8h] [rbp+20h] BYREF

  v2 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    BYTE1(ObjectDescriptor) = 1;
    cbSid = 68;
    try
    {
      v5 = operator new[](0x44u);
      if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v5, &cbSid) )
      {
        v13 = SetNamedSecurityInfoW(a1, SE_REGISTRY_KEY, 1u, v5, 0, 0, 0);
        if ( v13 )
        {
          v14 = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x3F5,
                  (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                  (const char *)v13,
                  (unsigned int)"falied to change %ls ownerhsip",
                  (const char *)a1);
          operator delete(v5, v15);
          v16 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
          if ( v16 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, v17, v11, (const char *)(unsigned int)v16, psidGroupa);
          result = v14;
        }
        else
        {
          ppDacl = 0;
          hMem = 0;
          ppSecurityDescriptor = 0;
          NamedSecurityInfoW = GetNamedSecurityInfoW(a1, SE_REGISTRY_KEY, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
          if ( NamedSecurityInfoW )
          {
            v20 = wil::details::in1diag3::Return_Win32Msg(
                    retaddr,
                    (void *)0x402,
                    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                    (const char *)NamedSecurityInfoW,
                    (unsigned int)"failed to get DACL",
                    (const char *)pDacl);
            v21 = hMem;
            hMem = 0;
            if ( v21 )
              LocalFree(v21);
            if ( ppSecurityDescriptor )
            {
              ObjectDescriptor = ppSecurityDescriptor;
              DestroyPrivateObjectSecurity(&ObjectDescriptor);
            }
            operator delete(v5, v19);
            v22 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
            if ( v22 < 0 )
              wil::details::in1diag3::_Log_Hr(retaddr, v23, v11, (const char *)(unsigned int)v22, psidGroupb);
            result = v20;
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
            v53 = 1;
            v24 = SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
            if ( v53 )
            {
              v25 = *p_hMem;
              *p_hMem = NewAcl;
              if ( v25 )
                LocalFree(v25);
            }
            if ( v24 )
            {
              v27 = wil::details::in1diag3::Return_Win32Msg(
                      retaddr,
                      (void *)0x40E,
                      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                      (const char *)v24,
                      (unsigned int)"failed to modify ACL",
                      (const char *)pDacl);
              v28 = hMem;
              hMem = 0;
              if ( v28 )
                LocalFree(v28);
              if ( ppSecurityDescriptor )
              {
                ObjectDescriptor = ppSecurityDescriptor;
                DestroyPrivateObjectSecurity(&ObjectDescriptor);
              }
              operator delete(v5, v26);
              v29 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
              if ( v29 < 0 )
                wil::details::in1diag3::_Log_Hr(retaddr, v30, v11, (const char *)(unsigned int)v29, psidGroupc);
              result = v27;
            }
            else
            {
              v31 = SetNamedSecurityInfoW(a1, SE_REGISTRY_KEY, 4u, 0, 0, (PACL)hMem, 0);
              if ( v31 )
              {
                v34 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0x416,
                        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                        (const char *)v31,
                        (unsigned int)"Failed to change the DACL on the reg key",
                        (const char *)pDacla);
                v35 = hMem;
                hMem = 0;
                if ( v35 )
                  LocalFree(v35);
                if ( ppSecurityDescriptor )
                {
                  ObjectDescriptor = ppSecurityDescriptor;
                  DestroyPrivateObjectSecurity(&ObjectDescriptor);
                }
                operator delete(v5, v33);
                v36 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
                if ( v36 < 0 )
                  wil::details::in1diag3::_Log_Hr(retaddr, v37, v11, (const char *)(unsigned int)v36, psidGroupe);
                result = v34;
              }
              else
              {
                v38 = hMem;
                hMem = 0;
                if ( v38 )
                  LocalFree(v38);
                if ( ppSecurityDescriptor )
                {
                  ObjectDescriptor = ppSecurityDescriptor;
                  DestroyPrivateObjectSecurity(&ObjectDescriptor);
                }
                operator delete(v5, v32);
                v39 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
                if ( v39 < 0 )
                  wil::details::in1diag3::_Log_Hr(retaddr, v40, v11, (const char *)(unsigned int)v39, psidGroupd);
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
        operator delete(v5, v8);
        v9 = DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(0);
        if ( v9 < 0 )
          wil::details::in1diag3::_Log_Hr(retaddr, v10, v11, (const char *)(unsigned int)v9, psidGroup);
        result = LastError;
      }
    }
    catch ( ... )
    {
      LODWORD(ObjectDescriptor) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x41A, v11, v12);
      return (unsigned int)ObjectDescriptor;
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
0x1400138ac  push    rbx
0x1400138ae  push    rsi
0x1400138af  push    rdi
0x1400138b0  push    r14
0x1400138b2  push    r15
0x1400138b4  sub     rsp, 0A0h
0x1400138bb  mov     rdi, rcx
0x1400138be  mov     esi, 1
0x1400138c3  mov     cl, sil; bool
0x1400138c6  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x1400138cb  mov     ebx, eax
0x1400138cd  xor     r14d, r14d
0x1400138d0  test    eax, eax
0x1400138d2  jns     short loc_1400138F7
0x1400138d4  mov     rcx, [rsp+0C8h]; this
0x1400138dc  mov     r9d, eax; char *
0x1400138df  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x1400138e6  mov     edx, 3E5h; void *
0x1400138eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400138f0  mov     eax, ebx
0x1400138f2  jmp     loc_140013D21
0x1400138f7  mov     byte ptr [rsp+0C8h+ObjectDescriptor+1], sil
0x1400138ff  mov     ecx, 44h ; 'D'; unsigned __int64
0x140013904  mov     [rsp+0C8h+cbSid], ecx
0x14001390b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140013910  mov     rbx, rax
0x140013913  lea     r9, [rsp+0C8h+cbSid]; cbSid
0x14001391b  mov     r8, rax; pSid
0x14001391e  xor     edx, edx; DomainSid
0x140013920  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x140013923  call    cs:__imp_CreateWellKnownSid
0x140013929  test    eax, eax
0x14001392b  jnz     short loc_140013973
0x14001392d  mov     rcx, [rsp+0C8h]; this
0x140013935  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x14001393c  mov     edx, 3EDh; void *
0x140013941  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140013946  mov     edi, eax
0x140013948  mov     rcx, rbx; void *
0x14001394b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013950  nop
0x140013951  xor     ecx, ecx; bool
0x140013953  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x140013958  mov     rcx, [rsp+0C8h]; this
0x140013960  test    eax, eax
0x140013962  jns     short loc_14001396C
0x140013964  mov     r9d, eax; char *
0x140013967  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001396c  mov     eax, edi
0x14001396e  jmp     loc_140013D21
0x140013973  mov     [rsp+0C8h+pSacl], r14; pSacl
0x140013978  mov     [rsp+0C8h+pDacl], r14; pDacl
0x14001397d  mov     [rsp+0C8h+psidGroup], r14; psidGroup
0x140013982  mov     r9, rbx; psidOwner
0x140013985  mov     r8d, esi; SecurityInfo
0x140013988  mov     r15d, 4
0x14001398e  mov     edx, r15d; ObjectType
0x140013991  mov     rcx, rdi; pObjectName
0x140013994  call    cs:__imp_SetNamedSecurityInfoW
0x14001399a  test    eax, eax
0x14001399c  jz      short loc_1400139F8
0x14001399e  mov     rcx, [rsp+0C8h]; this
0x1400139a6  mov     [rsp+0C8h+pDacl], rdi; char *
0x1400139ab  lea     rdx, aFaliedToChange; "falied to change %ls ownerhsip"
0x1400139b2  mov     [rsp+0C8h+psidGroup], rdx; int
0x1400139b7  mov     r9d, eax; char *
0x1400139ba  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x1400139c1  mov     edx, 3F5h; void *
0x1400139c6  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1400139cb  mov     edi, eax
0x1400139cd  mov     rcx, rbx; void *
0x1400139d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400139d5  nop
0x1400139d6  xor     ecx, ecx; bool
0x1400139d8  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x1400139dd  mov     rcx, [rsp+0C8h]; this
0x1400139e5  test    eax, eax
0x1400139e7  jns     short loc_1400139F1
0x1400139e9  mov     r9d, eax; char *
0x1400139ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400139f1  mov     eax, edi
0x1400139f3  jmp     loc_140013D21
0x1400139f8  mov     [rsp+0C8h+ppDacl], r14
0x1400139fd  mov     [rsp+0C8h+hMem], r14
0x140013a05  mov     [rsp+0C8h+var_88], r14
0x140013a0a  lea     rax, [rsp+0C8h+var_88]
0x140013a0f  mov     [rsp+0C8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x140013a14  mov     [rsp+0C8h+pSacl], r14; ppSacl
0x140013a19  lea     rax, [rsp+0C8h+ppDacl]
0x140013a1e  mov     [rsp+0C8h+pDacl], rax; char *
0x140013a23  mov     [rsp+0C8h+psidGroup], r14; ppsidGroup
0x140013a28  xor     r9d, r9d; ppsidOwner
0x140013a2b  mov     r8d, r15d; SecurityInfo
0x140013a2e  mov     edx, r15d; ObjectType
0x140013a31  mov     rcx, rdi; pObjectName
0x140013a34  call    cs:__imp_GetNamedSecurityInfoW
0x140013a3a  test    eax, eax
0x140013a3c  jz      loc_140013AD2
0x140013a42  mov     rcx, [rsp+0C8h]; this
0x140013a4a  lea     rdx, aFailedToGetDac; "failed to get DACL"
0x140013a51  mov     [rsp+0C8h+psidGroup], rdx; int
0x140013a56  mov     r9d, eax; char *
0x140013a59  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140013a60  mov     edx, 402h; void *
0x140013a65  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x140013a6a  mov     edi, eax
0x140013a6c  mov     rcx, [rsp+0C8h+hMem]; hMem
0x140013a74  mov     [rsp+0C8h+hMem], r14
0x140013a7c  test    rcx, rcx
0x140013a7f  jz      short loc_140013A87
0x140013a81  call    cs:__imp_LocalFree
0x140013a87  mov     rcx, [rsp+0C8h+var_88]
0x140013a8c  test    rcx, rcx
0x140013a8f  jz      short loc_140013AA7
0x140013a91  mov     [rsp+0D8h], rcx
0x140013a99  lea     rcx, [rsp+0C8h+ObjectDescriptor]; ObjectDescriptor
0x140013aa1  call    cs:__imp_DestroyPrivateObjectSecurity
0x140013aa7  mov     rcx, rbx; void *
0x140013aaa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013aaf  nop
0x140013ab0  xor     ecx, ecx; bool
0x140013ab2  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x140013ab7  mov     rcx, [rsp+0C8h]; this
0x140013abf  test    eax, eax
0x140013ac1  jns     short loc_140013ACB
0x140013ac3  mov     r9d, eax; char *
0x140013ac6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140013acb  mov     eax, edi
0x140013acd  jmp     loc_140013D21
0x140013ad2  xorps   xmm0, xmm0
0x140013ad5  movdqu  xmmword ptr [rsp+0C8h+pListOfExplicitEntries+0Ch], xmm0
0x140013adb  mov     qword ptr [rsp+0C8h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x140013ae7  mov     [rsp+0C8h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x140013aef  mov     [rsp+0C8h+pListOfExplicitEntries.grfAccessMode], 2
0x140013af7  mov     [rsp+0C8h+pListOfExplicitEntries.grfInheritance], 3
0x140013aff  mov     [rsp+0C8h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x140013b07  mov     [rsp+0C8h+pListOfExplicitEntries.Trustee.ptstrName], rbx
0x140013b0f  lea     rax, [rsp+0C8h+hMem]
0x140013b17  mov     [rsp+0C8h+var_78], rax
0x140013b1c  mov     [rsp+0C8h+NewAcl], r14
0x140013b21  mov     [rsp+0C8h+var_68], sil
0x140013b26  lea     r9, [rsp+0C8h+NewAcl]; NewAcl
0x140013b2b  mov     r8, [rsp+0C8h+ppDacl]; OldAcl
0x140013b30  lea     rdx, [rsp+0C8h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140013b35  mov     ecx, esi; cCountOfExplicitEntries
0x140013b37  call    cs:__imp_SetEntriesInAclW
0x140013b3d  mov     esi, eax
0x140013b3f  cmp     [rsp+0C8h+var_68], r14b
0x140013b44  jz      short loc_140013B61
0x140013b46  mov     r8, [rsp+0C8h+var_78]
0x140013b4b  mov     rcx, [r8]; hMem
0x140013b4e  mov     rdx, [rsp+0C8h+NewAcl]
0x140013b53  mov     [r8], rdx
0x140013b56  test    rcx, rcx
0x140013b59  jz      short loc_140013B61
0x140013b5b  call    cs:__imp_LocalFree
0x140013b61  test    esi, esi
0x140013b63  jz      loc_140013BF9
0x140013b69  mov     rcx, [rsp+0C8h]; this
0x140013b71  lea     rax, aFailedToModify; "failed to modify ACL"
0x140013b78  mov     [rsp+0C8h+psidGroup], rax; int
0x140013b7d  mov     r9d, esi; char *
0x140013b80  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140013b87  mov     edx, 40Eh; void *
0x140013b8c  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x140013b91  mov     edi, eax
0x140013b93  mov     rcx, [rsp+0C8h+hMem]; hMem
0x140013b9b  mov     [rsp+0C8h+hMem], r14
0x140013ba3  test    rcx, rcx
0x140013ba6  jz      short loc_140013BAE
0x140013ba8  call    cs:__imp_LocalFree
0x140013bae  mov     rcx, [rsp+0C8h+var_88]
0x140013bb3  test    rcx, rcx
0x140013bb6  jz      short loc_140013BCE
0x140013bb8  mov     [rsp+0C8h+ObjectDescriptor], rcx
0x140013bc0  lea     rcx, [rsp+0C8h+ObjectDescriptor]; ObjectDescriptor
0x140013bc8  call    cs:__imp_DestroyPrivateObjectSecurity
0x140013bce  mov     rcx, rbx; void *
0x140013bd1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013bd6  nop
0x140013bd7  xor     ecx, ecx; bool
0x140013bd9  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x140013bde  mov     rcx, [rsp+0C8h]; this
0x140013be6  test    eax, eax
0x140013be8  jns     short loc_140013BF2
0x140013bea  mov     r9d, eax; char *
0x140013bed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140013bf2  mov     eax, edi
0x140013bf4  jmp     loc_140013D21
0x140013bf9  mov     [rsp+0C8h+pSacl], r14; pSacl
0x140013bfe  mov     rax, [rsp+0C8h+hMem]
0x140013c06  mov     [rsp+0C8h+pDacl], rax; char *
0x140013c0b  mov     [rsp+0C8h+psidGroup], r14; int
0x140013c10  xor     r9d, r9d; psidOwner
0x140013c13  mov     r8d, r15d; SecurityInfo
0x140013c16  mov     edx, r15d; ObjectType
0x140013c19  mov     rcx, rdi; pObjectName
0x140013c1c  call    cs:__imp_SetNamedSecurityInfoW
0x140013c22  test    eax, eax
0x140013c24  jz      loc_140013CB7
0x140013c2a  mov     rcx, [rsp+0C8h]; this
0x140013c32  lea     rdx, aFailedToChange; "Failed to change the DACL on the reg ke"...
0x140013c39  mov     [rsp+0C8h+psidGroup], rdx; int
0x140013c3e  mov     r9d, eax; char *
0x140013c41  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140013c48  mov     edx, 416h; void *
0x140013c4d  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x140013c52  mov     edi, eax
0x140013c54  mov     rcx, [rsp+0C8h+hMem]; hMem
0x140013c5c  mov     [rsp+0C8h+hMem], r14
0x140013c64  test    rcx, rcx
0x140013c67  jz      short loc_140013C6F
0x140013c69  call    cs:__imp_LocalFree
0x140013c6f  mov     rcx, [rsp+0C8h+var_88]
0x140013c74  test    rcx, rcx
0x140013c77  jz      short loc_140013C8F
0x140013c79  mov     [rsp+0C8h+ObjectDescriptor], rcx
0x140013c81  lea     rcx, [rsp+0C8h+ObjectDescriptor]; ObjectDescriptor
0x140013c89  call    cs:__imp_DestroyPrivateObjectSecurity
0x140013c8f  mov     rcx, rbx; void *
0x140013c92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013c97  nop
0x140013c98  xor     ecx, ecx; bool
0x140013c9a  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x140013c9f  mov     rcx, [rsp+0C8h]; this
0x140013ca7  test    eax, eax
0x140013ca9  jns     short loc_140013CB3
0x140013cab  mov     r9d, eax; char *
0x140013cae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140013cb3  mov     eax, edi
0x140013cb5  jmp     short loc_140013D21
0x140013cb7  mov     rcx, [rsp+0C8h+hMem]; hMem
0x140013cbf  mov     [rsp+0C8h+hMem], r14
0x140013cc7  test    rcx, rcx
0x140013cca  jz      short loc_140013CD2
0x140013ccc  call    cs:__imp_LocalFree
0x140013cd2  mov     rax, [rsp+0C8h+var_88]
0x140013cd7  test    rax, rax
0x140013cda  jz      short loc_140013CF2
0x140013cdc  mov     [rsp+0C8h+ObjectDescriptor], rax
0x140013ce4  lea     rcx, [rsp+0C8h+ObjectDescriptor]; ObjectDescriptor
0x140013cec  call    cs:__imp_DestroyPrivateObjectSecurity
0x140013cf2  mov     rcx, rbx; void *
0x140013cf5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013cfa  nop
0x140013cfb  xor     ecx, ecx; bool
0x140013cfd  call    ?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z; DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)
0x140013d02  mov     rcx, [rsp+0C8h]; this
0x140013d0a  test    eax, eax
0x140013d0c  jns     short loc_140013D16
0x140013d0e  mov     r9d, eax; char *
0x140013d11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140013d16  xor     eax, eax
0x140013d18  jmp     short loc_140013D21
0x140013d1a  mov     eax, dword ptr [rsp+0C8h+ObjectDescriptor]
0x140013d21  add     rsp, 0A0h
0x140013d28  pop     r15
0x140013d2a  pop     r14
0x140013d2c  pop     rdi
0x140013d2d  pop     rsi
0x140013d2e  pop     rbx
0x140013d2f  retn
```
