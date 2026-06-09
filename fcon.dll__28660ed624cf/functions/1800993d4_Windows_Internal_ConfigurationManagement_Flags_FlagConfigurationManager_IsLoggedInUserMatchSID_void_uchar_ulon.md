# Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsLoggedInUserMatchSID(void *,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,bool &)

- ea: `0x1800993d4`
- end: `0x180099781`
- name: `?IsLoggedInUserMatchSID@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJPEAXEKKKKKKKKAEA_N@Z`
- size: `941`
- prototype: `__int64 __usercall@<rax>(HANDLE ClientToken@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180098df0`
- `0x180098f54`

## callees

- `0x180003220`
- `0x1800993d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009959f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800995ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009959f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800995ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800994dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099524`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009955f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800995b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800995be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009960e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009966d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009972f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099741`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800994dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099524`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009955f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800995b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800995be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009960e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009966d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009972f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099741`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180099491`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180099508`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180099491`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180099508`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180099720`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180099720`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180099466`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180099466`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800996f2`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800996f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800994fb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800994fb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800994bc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800994bc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009953f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009953f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180099595`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180099595`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18009964d`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18009964d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800995e5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800995e5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180099633`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180099633`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180099644`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180099644`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800994a4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800994d3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18009951b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180099556`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800995ac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800995fc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180099664`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180099751`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800994a4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800994d3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18009951b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180099556`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800995ac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800995fc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180099664`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180099751`

## pseudocode

```c
signed int __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsLoggedInUserMatchSID(
        HANDLE ClientToken,
        BYTE a2,
        DWORD a3,
        DWORD a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        bool *a11)
{
  signed int result; // eax
  const char *v13; // r9
  HLOCAL v14; // rax
  void *v15; // rbx
  signed int v16; // edi
  DWORD v17; // edi
  struct _ACL *v18; // rax
  struct _ACL *v19; // rsi
  signed int v20; // edi
  signed int v21; // edi
  signed int v22; // edi
  signed int LastError; // edi
  WINBOOL v24; // eax
  PSID pGroup; // [rsp+60h] [rbp-98h] BYREF
  WINBOOL AccessStatus; // [rsp+68h] [rbp-90h] BYREF
  DWORD PrivilegeSetLength; // [rsp+6Ch] [rbp-8Ch] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp-88h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp-80h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v30; // [rsp+80h] [rbp-78h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+88h] [rbp-70h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+98h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *a11 = 0;
  *(_DWORD *)v30.Value = 0;
  *(_WORD *)&v30.Value[4] = 1280;
  GrantedAccess = 0;
  PrivilegeSetLength = 20;
  pGroup = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping = 0;
  if ( AllocateAndInitializeSid(&v30, a2, a3, a4, 0, 0, 0, 0, 0, 0, &pGroup) )
  {
    v14 = LocalAlloc(0x40u, 0x28u);
    v15 = v14;
    if ( v14 )
    {
      if ( InitializeSecurityDescriptor(v14, 1u) )
      {
        v17 = GetLengthSid(pGroup) + 16;
        v18 = (struct _ACL *)LocalAlloc(0x40u, v17);
        v19 = v18;
        if ( v18 )
        {
          if ( InitializeAcl(v18, v17, 2u) )
          {
            if ( AddAccessAllowedAce(v19, 2u, 3u, pGroup) )
            {
              if ( SetSecurityDescriptorDacl(v15, 1, v19, 0) )
              {
                SetSecurityDescriptorGroup(v15, pGroup, 0);
                SetSecurityDescriptorOwner(v15, pGroup, 0);
                if ( IsValidSecurityDescriptor(v15) )
                {
                  GenericMapping.GenericRead = 1;
                  *(_QWORD *)&GenericMapping.GenericWrite = 2;
                  GenericMapping.GenericAll = 3;
                  AccessStatus = 0;
                  if ( AccessCheck(
                         v15,
                         ClientToken,
                         1u,
                         &GenericMapping,
                         &PrivilegeSet,
                         &PrivilegeSetLength,
                         &GrantedAccess,
                         &AccessStatus) )
                  {
                    v24 = AccessStatus;
                  }
                  else
                  {
                    v24 = 0;
                    AccessStatus = 0;
                  }
                  *a11 = v24 != 0;
                  StringSid = 0;
                  if ( ConvertSidToStringSidW(pGroup, &StringSid) )
                    LocalFree(StringSid);
                  LocalFree(v19);
                  LocalFree(v15);
                  if ( pGroup )
                    FreeSid(pGroup);
                  result = 0;
                }
                else
                {
                  LastError = GetLastError();
                  FreeSid(pGroup);
                  LocalFree(v15);
                  LocalFree(v19);
                  if ( LastError > 0 )
                    LastError = (unsigned __int16)LastError | 0x80070000;
                  result = LastError;
                }
              }
              else
              {
                v22 = GetLastError();
                FreeSid(pGroup);
                LocalFree(v15);
                LocalFree(v19);
                if ( v22 > 0 )
                  v22 = (unsigned __int16)v22 | 0x80070000;
                result = v22;
              }
            }
            else
            {
              v21 = GetLastError();
              FreeSid(pGroup);
              LocalFree(v15);
              LocalFree(v19);
              if ( v21 > 0 )
                v21 = (unsigned __int16)v21 | 0x80070000;
              result = v21;
            }
          }
          else
          {
            v20 = GetLastError();
            FreeSid(pGroup);
            LocalFree(v15);
            LocalFree(v19);
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            result = v20;
          }
        }
        else
        {
          FreeSid(pGroup);
          LocalFree(v15);
          result = -2147024882;
        }
      }
      else
      {
        v16 = GetLastError();
        FreeSid(pGroup);
        LocalFree(v15);
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        result = v16;
      }
    }
    else
    {
      FreeSid(pGroup);
      result = -2147024882;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      PrivilegeSetLength = wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x3B8,
                             (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\f"
                                           "lagconfigurationmanager.cpp",
                             v13);
      result = PrivilegeSetLength;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1800993d4  mov     r11, rsp
0x1800993d7  push    rbx
0x1800993d8  push    rsi
0x1800993d9  push    rdi
0x1800993da  push    r12
0x1800993dc  push    r14
0x1800993de  push    r15
0x1800993e0  sub     rsp, 0C8h
0x1800993e7  mov     rax, cs:__security_cookie
0x1800993ee  xor     rax, rsp
0x1800993f1  mov     [rsp+0F8h+var_48], rax
0x1800993f9  mov     r15, rcx
0x1800993fc  mov     r14, [rsp+0F8h+arg_50]
0x180099404  xor     r12d, r12d
0x180099407  mov     [r14], r12b
0x18009940a  mov     [r11-78h], r12d
0x18009940e  mov     word ptr [r11-74h], 500h
0x180099415  mov     [rsp+0F8h+GrantedAccess], r12d
0x18009941a  mov     [rsp+0F8h+PrivilegeSetLength], 14h
0x180099422  mov     [rsp+0F8h+pGroup], r12
0x180099427  xorps   xmm0, xmm0
0x18009942a  xor     eax, eax
0x18009942c  movups  xmmword ptr [r11-60h], xmm0
0x180099431  mov     [r11-50h], eax
0x180099435  movups  xmmword ptr [r11-70h], xmm0
0x18009943a  lea     rax, [rsp+0F8h+pGroup]
0x18009943f  mov     [rsp+0F8h+pSid], rax; pSid
0x180099444  mov     [rsp+0F8h+nSubAuthority7], r12d; nSubAuthority7
0x180099449  mov     [rsp+0F8h+nSubAuthority6], r12d; nSubAuthority6
0x18009944e  mov     [rsp+0F8h+nSubAuthority5], r12d; nSubAuthority5
0x180099453  mov     [rsp+0F8h+nSubAuthority4], r12d; nSubAuthority4
0x180099458  mov     [rsp+0F8h+nSubAuthority3], r12d; nSubAuthority3
0x18009945d  mov     [rsp+0F8h+nSubAuthority2], r12d; nSubAuthority2
0x180099462  lea     rcx, [r11-78h]; pIdentifierAuthority
0x180099466  call    cs:__imp_AllocateAndInitializeSid
0x18009946c  test    eax, eax
0x18009946e  jnz     short loc_180099487
0x180099470  call    cs:__imp_GetLastError
0x180099476  test    eax, eax
0x180099478  jle     short loc_180099482
0x18009947a  movzx   eax, ax
0x18009947d  or      eax, 80070000h
0x180099482  jmp     loc_18009975F
0x180099487  mov     edx, 28h ; '('; uBytes
0x18009948c  lea     esi, [rdx+18h]
0x18009948f  mov     ecx, esi; uFlags
0x180099491  call    cs:__imp_LocalAlloc
0x180099497  mov     rbx, rax
0x18009949a  test    rax, rax
0x18009949d  jnz     short loc_1800994B4
0x18009949f  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x1800994a4  call    cs:__imp_FreeSid
0x1800994aa  mov     eax, 8007000Eh
0x1800994af  jmp     loc_18009975F
0x1800994b4  mov     edx, 1; dwRevision
0x1800994b9  mov     rcx, rbx; pSecurityDescriptor
0x1800994bc  call    cs:__imp_InitializeSecurityDescriptor
0x1800994c2  test    eax, eax
0x1800994c4  jnz     short loc_1800994F6
0x1800994c6  call    cs:__imp_GetLastError
0x1800994cc  mov     edi, eax
0x1800994ce  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x1800994d3  call    cs:__imp_FreeSid
0x1800994d9  mov     rcx, rbx; hMem
0x1800994dc  call    cs:__imp_LocalFree
0x1800994e2  test    edi, edi
0x1800994e4  jle     short loc_1800994EF
0x1800994e6  movzx   edi, di
0x1800994e9  or      edi, 80070000h
0x1800994ef  mov     eax, edi
0x1800994f1  jmp     loc_18009975F
0x1800994f6  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x1800994fb  call    cs:__imp_GetLengthSid
0x180099501  lea     edi, [rax+10h]
0x180099504  mov     edx, edi; uBytes
0x180099506  mov     ecx, esi; uFlags
0x180099508  call    cs:__imp_LocalAlloc
0x18009950e  mov     rsi, rax
0x180099511  test    rax, rax
0x180099514  jnz     short loc_180099534
0x180099516  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x18009951b  call    cs:__imp_FreeSid
0x180099521  mov     rcx, rbx; hMem
0x180099524  call    cs:__imp_LocalFree
0x18009952a  mov     eax, 8007000Eh
0x18009952f  jmp     loc_18009975F
0x180099534  mov     r8d, 2; dwAclRevision
0x18009953a  mov     edx, edi; nAclLength
0x18009953c  mov     rcx, rsi; pAcl
0x18009953f  call    cs:__imp_InitializeAcl
0x180099545  test    eax, eax
0x180099547  jnz     short loc_180099582
0x180099549  call    cs:__imp_GetLastError
0x18009954f  mov     edi, eax
0x180099551  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x180099556  call    cs:__imp_FreeSid
0x18009955c  mov     rcx, rbx; hMem
0x18009955f  call    cs:__imp_LocalFree
0x180099565  mov     rcx, rsi; hMem
0x180099568  call    cs:__imp_LocalFree
0x18009956e  test    edi, edi
0x180099570  jle     short loc_18009957B
0x180099572  movzx   edi, di
0x180099575  or      edi, 80070000h
0x18009957b  mov     eax, edi
0x18009957d  jmp     loc_18009975F
0x180099582  mov     r9, [rsp+0F8h+pGroup]; pSid
0x180099587  mov     edi, 2
0x18009958c  lea     r8d, [rdi+1]; AccessMask
0x180099590  mov     edx, edi; dwAceRevision
0x180099592  mov     rcx, rsi; pAcl
0x180099595  call    cs:__imp_AddAccessAllowedAce
0x18009959b  test    eax, eax
0x18009959d  jnz     short loc_1800995D8
0x18009959f  call    cs:__imp_GetLastError
0x1800995a5  mov     edi, eax
0x1800995a7  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x1800995ac  call    cs:__imp_FreeSid
0x1800995b2  mov     rcx, rbx; hMem
0x1800995b5  call    cs:__imp_LocalFree
0x1800995bb  mov     rcx, rsi; hMem
0x1800995be  call    cs:__imp_LocalFree
0x1800995c4  test    edi, edi
0x1800995c6  jle     short loc_1800995D1
0x1800995c8  movzx   edi, di
0x1800995cb  or      edi, 80070000h
0x1800995d1  mov     eax, edi
0x1800995d3  jmp     loc_18009975F
0x1800995d8  xor     r9d, r9d; bDaclDefaulted
0x1800995db  mov     r8, rsi; pDacl
0x1800995de  lea     edx, [r9+1]; bDaclPresent
0x1800995e2  mov     rcx, rbx; pSecurityDescriptor
0x1800995e5  call    cs:__imp_SetSecurityDescriptorDacl
0x1800995eb  test    eax, eax
0x1800995ed  jnz     short loc_180099628
0x1800995ef  call    cs:__imp_GetLastError
0x1800995f5  mov     edi, eax
0x1800995f7  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x1800995fc  call    cs:__imp_FreeSid
0x180099602  mov     rcx, rbx; hMem
0x180099605  call    cs:__imp_LocalFree
0x18009960b  mov     rcx, rsi; hMem
0x18009960e  call    cs:__imp_LocalFree
0x180099614  test    edi, edi
0x180099616  jle     short loc_180099621
0x180099618  movzx   edi, di
0x18009961b  or      edi, 80070000h
0x180099621  mov     eax, edi
0x180099623  jmp     loc_18009975F
0x180099628  xor     r8d, r8d; bGroupDefaulted
0x18009962b  mov     rdx, [rsp+0F8h+pGroup]; pGroup
0x180099630  mov     rcx, rbx; pSecurityDescriptor
0x180099633  call    cs:__imp_SetSecurityDescriptorGroup
0x180099639  xor     r8d, r8d; bOwnerDefaulted
0x18009963c  mov     rdx, [rsp+0F8h+pGroup]; pOwner
0x180099641  mov     rcx, rbx; pSecurityDescriptor
0x180099644  call    cs:__imp_SetSecurityDescriptorOwner
0x18009964a  mov     rcx, rbx; pSecurityDescriptor
0x18009964d  call    cs:__imp_IsValidSecurityDescriptor
0x180099653  test    eax, eax
0x180099655  jnz     short loc_180099690
0x180099657  call    cs:__imp_GetLastError
0x18009965d  mov     edi, eax
0x18009965f  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x180099664  call    cs:__imp_FreeSid
0x18009966a  mov     rcx, rbx; hMem
0x18009966d  call    cs:__imp_LocalFree
0x180099673  mov     rcx, rsi; hMem
0x180099676  call    cs:__imp_LocalFree
0x18009967c  test    edi, edi
0x18009967e  jle     short loc_180099689
0x180099680  movzx   edi, di
0x180099683  or      edi, 80070000h
0x180099689  mov     eax, edi
0x18009968b  jmp     loc_18009975F
0x180099690  mov     [rsp+0F8h+GenericMapping.GenericRead], 1
0x18009969b  mov     qword ptr [rsp+0F8h+GenericMapping.GenericWrite], rdi
0x1800996a3  mov     [rsp+0F8h+GenericMapping.GenericAll], 3
0x1800996ae  mov     [rsp+0F8h+AccessStatus], r12d
0x1800996b3  lea     rax, [rsp+0F8h+AccessStatus]
0x1800996b8  mov     qword ptr [rsp+0F8h+nSubAuthority5], rax; AccessStatus
0x1800996bd  lea     rax, [rsp+0F8h+GrantedAccess]
0x1800996c2  mov     qword ptr [rsp+0F8h+nSubAuthority4], rax; GrantedAccess
0x1800996c7  lea     rax, [rsp+0F8h+PrivilegeSetLength]
0x1800996cc  mov     qword ptr [rsp+0F8h+nSubAuthority3], rax; PrivilegeSetLength
0x1800996d1  lea     rax, [rsp+0F8h+PrivilegeSet]
0x1800996d9  mov     qword ptr [rsp+0F8h+nSubAuthority2], rax; PrivilegeSet
0x1800996de  lea     r9, [rsp+0F8h+GenericMapping]; GenericMapping
0x1800996e6  mov     r8d, 1; DesiredAccess
0x1800996ec  mov     rdx, r15; ClientToken
0x1800996ef  mov     rcx, rbx; pSecurityDescriptor
0x1800996f2  call    cs:__imp_AccessCheck
0x1800996f8  test    eax, eax
0x1800996fa  jnz     short loc_180099705
0x1800996fc  mov     eax, r12d
0x1800996ff  mov     [rsp+0F8h+AccessStatus], eax
0x180099703  jmp     short loc_180099709
0x180099705  mov     eax, [rsp+0F8h+AccessStatus]
0x180099709  test    eax, eax
0x18009970b  setnz   al
0x18009970e  mov     [r14], al
0x180099711  mov     [rsp+0F8h+StringSid], r12
0x180099716  lea     rdx, [rsp+0F8h+StringSid]; StringSid
0x18009971b  mov     rcx, [rsp+0F8h+pGroup]; Sid
0x180099720  call    cs:__imp_ConvertSidToStringSidW
0x180099726  test    eax, eax
0x180099728  jz      short loc_180099735
0x18009972a  mov     rcx, [rsp+0F8h+StringSid]; hMem
0x18009972f  call    cs:__imp_LocalFree
0x180099735  mov     rcx, rsi; hMem
0x180099738  call    cs:__imp_LocalFree
0x18009973e  mov     rcx, rbx; hMem
0x180099741  call    cs:__imp_LocalFree
0x180099747  mov     rcx, [rsp+0F8h+pGroup]; pSid
0x18009974c  test    rcx, rcx
0x18009974f  jz      short loc_180099757
0x180099751  call    cs:__imp_FreeSid
0x180099757  xor     eax, eax
0x180099759  jmp     short loc_18009975F
0x18009975b  mov     eax, [rsp+0F8h+PrivilegeSetLength]
0x18009975f  mov     rcx, [rsp+0F8h+var_48]
0x180099767  xor     rcx, rsp; StackCookie
0x18009976a  call    __security_check_cookie
0x18009976f  add     rsp, 0C8h
0x180099776  pop     r15
0x180099778  pop     r14
0x18009977a  pop     r12
0x18009977c  pop     rdi
0x18009977d  pop     rsi
0x18009977e  pop     rbx
0x18009977f  retn
```
