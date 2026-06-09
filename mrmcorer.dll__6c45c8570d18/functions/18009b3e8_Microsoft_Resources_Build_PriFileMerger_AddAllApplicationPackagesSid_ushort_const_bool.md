# Microsoft::Resources::Build::PriFileMerger::AddAllApplicationPackagesSid(ushort const *,bool)

- ea: `0x18009b3e8`
- end: `0x18009b6e9`
- name: `?AddAllApplicationPackagesSid@PriFileMerger@Build@Resources@Microsoft@@SAJPEBG_N@Z`
- size: `769`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009bc10`

## callees

- `0x180019570`
- `0x18002c8d0`
- `0x180030c6c`
- `0x18005fdf8`
- `0x180063bb4`
- `0x180064884`
- `0x180083978`
- `0x180083aa8`
- `0x1800862f0`
- `0x180086ee0`
- `0x18008fb04`
- `0x18009b350`
- `0x18009b3e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009b5a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009b5a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009b58e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009b58e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009b4e7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009b4e7`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009b524`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009b524`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18009b5f0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18009b5f0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009b56b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009b56b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009b545`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009b545`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18009b478`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18009b478`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18009b639`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18009b639`

## string_xrefs

- `0x18009b6bc`: `Microsoft::Resources::Build::PriFileMerger::AddAllApplicationPackagesSid::<lambda_d31154f69198aa15570e7c0f3e9d7c18>::operator ()`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Build::PriFileMerger::AddAllApplicationPackagesSid(LPWSTR pObjectName)
{
  unsigned int LastError; // ebx
  DWORD NamedSecurityInfoW; // eax
  const char *v4; // r9
  __int64 v5; // rdx
  DWORD i; // edi
  _DWORD *v7; // rbx
  DWORD LengthSid; // eax
  DWORD v9; // edx
  DWORD v10; // ebx
  HANDLE ProcessHeap; // rax
  Microsoft::Resources *v12; // rax
  Microsoft::Resources *v13; // rdi
  __int64 v14; // rdx
  const char *v15; // r9
  int v16; // eax
  void *v17; // rdx
  DWORD v18; // eax
  void *v19; // rdx
  __int64 v21; // rax
  int ppsidGroup; // [rsp+20h] [rbp-59h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-59h]
  int ppsidGroupb; // [rsp+20h] [rbp-59h]
  unsigned int ppsidGroupc; // [rsp+20h] [rbp-59h]
  PSID pSid2; // [rsp+60h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+68h] [rbp-11h] BYREF
  PACL pAcl; // [rsp+70h] [rbp-9h] BYREF
  LPVOID pAce; // [rsp+78h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( (unsigned __int8)DefString_IsEmpty(pObjectName) )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
      (const char *)0x80070057LL,
      ppsidGroup);
    return LastError;
  }
  pAcl = 0;
  ppSecurityDescriptor = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppSecurityDescriptor,
    0);
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &ppSecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x1C,
                  (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
                  (const char *)NamedSecurityInfoW,
                  ppsidGroupa);
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppSecurityDescriptor);
    v21 = RemovePiiFromString(pObjectName);
    MrtRuntimeTelemetry_GenericEventParam1(
      L"Microsoft::Resources::Build::PriFileMerger::AddAllApplicationPackagesSid::<lambda_d31154f69198aa15570e7c0f3e9d7c18>::operator ()",
      v21,
      0);
    return LastError;
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  pSid2 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &pSid2) )
  {
    v5 = 44;
LABEL_7:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
                  v4);
    goto LABEL_32;
  }
  pAce = 0;
  for ( i = 0; i < pAcl->AceCount; ++i )
  {
    if ( !GetAce(pAcl, i, &pAce) )
    {
      v5 = 49;
      goto LABEL_7;
    }
    v7 = pAce;
    if ( !*(_BYTE *)pAce
      && (*((_BYTE *)pAce + 1) & 8) == 0
      && EqualSid((char *)pAce + 8, pSid2)
      && (v7[1] & 0x120089) != 0 )
    {
      goto LABEL_27;
    }
  }
  LengthSid = GetLengthSid(pSid2);
  v9 = LengthSid + 12;
  if ( LengthSid + 12 < LengthSid )
  {
    v14 = 68;
    goto LABEL_30;
  }
  v10 = v9 + pAcl->AclSize;
  if ( v10 < v9 )
  {
    v14 = 69;
LABEL_30:
    LastError = -2147024362;
    goto LABEL_31;
  }
  ProcessHeap = GetProcessHeap();
  v12 = (Microsoft::Resources *)HeapAlloc(ProcessHeap, 8u, v10);
  v13 = v12;
  if ( !v12 )
  {
    LastError = -2147024882;
    v14 = 72;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
      (const char *)LastError,
      ppsidGroupb);
LABEL_32:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid2);
    goto LABEL_33;
  }
  memcpy_s_1(v12, v10, pAcl, pAcl->AclSize);
  *((_WORD *)v13 + 1) = v10;
  if ( !AddAccessAllowedAceEx((PACL)v13, 2u, 3u, 0x120089u, pSid2) )
  {
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4D,
            (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
            v15);
LABEL_23:
    LastError = v16;
    Microsoft::Resources::DefFreeMemory(v13, v17);
    goto LABEL_32;
  }
  v18 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, (PACL)v13, 0);
  if ( v18 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x50,
            (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
            (const char *)v18,
            ppsidGroupc);
    goto LABEL_23;
  }
  Microsoft::Resources::DefFreeMemory(v13, v19);
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid2);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppSecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x18009b3e8  push    rbp
0x18009b3ea  push    rbx
0x18009b3eb  push    rsi
0x18009b3ec  push    rdi
0x18009b3ed  push    r14
0x18009b3ef  push    r15
0x18009b3f1  lea     rbp, [rsp-2Fh]
0x18009b3f6  sub     rsp, 0A8h
0x18009b3fd  mov     rax, cs:__security_cookie
0x18009b404  xor     rax, rsp
0x18009b407  mov     [rbp+57h+var_40], rax
0x18009b40b  mov     rsi, rcx
0x18009b40e  call    DefString_IsEmpty
0x18009b413  xor     r15d, r15d
0x18009b416  test    al, al
0x18009b418  jz      short loc_18009B43B
0x18009b41a  mov     rcx, [rbp+5Fh]; this
0x18009b41e  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x18009b425  mov     ebx, 80070057h
0x18009b42a  lea     edx, [r15+14h]; void *
0x18009b42e  mov     r9d, ebx; char *
0x18009b431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b436  jmp     loc_18009B6CB
0x18009b43b  xor     edx, edx
0x18009b43d  mov     [rbp+57h+pAcl], r15
0x18009b441  lea     rcx, [rbp+57h+var_68]
0x18009b445  mov     [rbp+57h+var_68], r15
0x18009b449  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18009b44e  xor     r9d, r9d; ppsidOwner
0x18009b451  lea     rax, [rbp+57h+var_68]
0x18009b455  mov     [rsp+0D0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18009b45a  mov     rcx, rsi; pObjectName
0x18009b45d  lea     rax, [rbp+57h+pAcl]
0x18009b461  mov     [rsp+0D0h+ppSacl], r15; ppSacl
0x18009b466  mov     [rsp+0D0h+ppDacl], rax; ppDacl
0x18009b46b  lea     edx, [r9+1]; ObjectType
0x18009b46f  mov     [rsp+0D0h+ppsidGroup], r15; unsigned int
0x18009b474  lea     r8d, [r9+4]; SecurityInfo
0x18009b478  call    cs:__imp_GetNamedSecurityInfoW
0x18009b47e  test    eax, eax
0x18009b480  jz      short loc_18009B4A1
0x18009b482  mov     rcx, [rbp+5Fh]; this
0x18009b486  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x18009b48d  mov     r9d, eax; char *
0x18009b490  mov     edx, 1Ch; void *
0x18009b495  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009b49a  mov     ebx, eax
0x18009b49c  jmp     loc_18009B6A8
0x18009b4a1  lea     rax, [rbp+57h+pSid2]
0x18009b4a5  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x18009b4a9  mov     [rsp+0D0h+pSid], rax; pSid
0x18009b4ae  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18009b4b2  mov     [rsp+0D0h+nSubAuthority7], r15d; nSubAuthority7
0x18009b4b7  mov     r9d, 1; nSubAuthority1
0x18009b4bd  mov     [rsp+0D0h+nSubAuthority6], r15d; nSubAuthority6
0x18009b4c2  mov     dword ptr [rsp+0D0h+ppSecurityDescriptor], r15d; nSubAuthority5
0x18009b4c7  mov     dword ptr [rsp+0D0h+ppSacl], r15d; nSubAuthority4
0x18009b4cc  lea     r8d, [r9+1]; nSubAuthority0
0x18009b4d0  mov     dword ptr [rsp+0D0h+ppDacl], r15d; nSubAuthority3
0x18009b4d5  mov     dl, r8b; nSubAuthorityCount
0x18009b4d8  mov     dword ptr [rsp+0D0h+ppsidGroup], r15d; int
0x18009b4dd  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 0F00h
0x18009b4e3  mov     [rbp+57h+pSid2], r15
0x18009b4e7  call    cs:__imp_AllocateAndInitializeSid
0x18009b4ed  test    eax, eax
0x18009b4ef  jnz     short loc_18009B50B
0x18009b4f1  lea     edx, [rax+2Ch]; void *
0x18009b4f4  mov     rcx, [rbp+5Fh]; this
0x18009b4f8  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x18009b4ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009b504  mov     ebx, eax
0x18009b506  jmp     loc_18009B69F
0x18009b50b  mov     [rbp+57h+pAce], r15
0x18009b50f  mov     edi, r15d
0x18009b512  mov     rcx, [rbp+57h+pAcl]; pAcl
0x18009b516  movzx   eax, word ptr [rcx+4]
0x18009b51a  cmp     edi, eax
0x18009b51c  jnb     short loc_18009B567
0x18009b51e  lea     r8, [rbp+57h+pAce]; pAce
0x18009b522  mov     edx, edi; dwAceIndex
0x18009b524  call    cs:__imp_GetAce
0x18009b52a  test    eax, eax
0x18009b52c  jz      short loc_18009B560
0x18009b52e  mov     rbx, [rbp+57h+pAce]
0x18009b532  cmp     [rbx], r15b
0x18009b535  jnz     short loc_18009B55C
0x18009b537  test    byte ptr [rbx+1], 8
0x18009b53b  jnz     short loc_18009B55C
0x18009b53d  mov     rdx, [rbp+57h+pSid2]; pSid2
0x18009b541  lea     rcx, [rbx+8]; pSid1
0x18009b545  call    cs:__imp_EqualSid
0x18009b54b  test    eax, eax
0x18009b54d  jz      short loc_18009B55C
0x18009b54f  test    dword ptr [rbx+4], 120089h
0x18009b556  jnz     loc_18009B665
0x18009b55c  inc     edi
0x18009b55e  jmp     short loc_18009B512
0x18009b560  mov     edx, 31h ; '1'
0x18009b565  jmp     short loc_18009B4F4
0x18009b567  mov     rcx, [rbp+57h+pSid2]; pSid
0x18009b56b  call    cs:__imp_GetLengthSid
0x18009b571  lea     edx, [rax+0Ch]
0x18009b574  cmp     edx, eax
0x18009b576  jb      loc_18009B682
0x18009b57c  mov     rax, [rbp+57h+pAcl]
0x18009b580  movzx   ebx, word ptr [rax+2]
0x18009b584  add     ebx, edx
0x18009b586  cmp     ebx, edx
0x18009b588  jb      loc_18009B67B
0x18009b58e  call    cs:__imp_GetProcessHeap
0x18009b594  mov     r8d, ebx; dwBytes
0x18009b597  mov     edx, 8; dwFlags
0x18009b59c  mov     rcx, rax; hHeap
0x18009b59f  mov     r14d, ebx
0x18009b5a2  call    cs:__imp_HeapAlloc
0x18009b5a8  mov     rdi, rax
0x18009b5ab  test    rax, rax
0x18009b5ae  jnz     short loc_18009B5BD
0x18009b5b0  mov     ebx, 8007000Eh
0x18009b5b5  lea     edx, [rax+48h]
0x18009b5b8  jmp     loc_18009B68C
0x18009b5bd  mov     r8, [rbp+57h+pAcl]; Source
0x18009b5c1  mov     rdx, r14; DestinationSize
0x18009b5c4  mov     rcx, rdi; Destination
0x18009b5c7  movzx   r9d, word ptr [r8+2]; SourceSize
0x18009b5cc  call    memcpy_s_1
0x18009b5d1  mov     edx, 2; dwAceRevision
0x18009b5d6  mov     [rdi+2], bx
0x18009b5da  mov     rax, [rbp+57h+pSid2]
0x18009b5de  mov     r9d, 120089h; AccessMask
0x18009b5e4  mov     rcx, rdi; pAcl
0x18009b5e7  mov     [rsp+0D0h+ppsidGroup], rax; pSid
0x18009b5ec  lea     r8d, [rdx+1]; AceFlags
0x18009b5f0  call    cs:__imp_AddAccessAllowedAceEx
0x18009b5f6  test    eax, eax
0x18009b5f8  jnz     short loc_18009B61C
0x18009b5fa  mov     rcx, [rbp+5Fh]; this
0x18009b5fe  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x18009b605  lea     edx, [rax+4Dh]; void *
0x18009b608  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009b60d  mov     rcx, rdi; this
0x18009b610  mov     ebx, eax
0x18009b612  call    ?DefFreeMemory@Resources@Microsoft@@YAXPEAX@Z; Microsoft::Resources::DefFreeMemory(void *)
0x18009b617  jmp     loc_18009B69F
0x18009b61c  xor     r9d, r9d; psidOwner
0x18009b61f  mov     [rsp+0D0h+ppSacl], r15; pSacl
0x18009b624  mov     [rsp+0D0h+ppDacl], rdi; pDacl
0x18009b629  mov     rcx, rsi; pObjectName
0x18009b62c  mov     [rsp+0D0h+ppsidGroup], r15; unsigned int
0x18009b631  lea     edx, [r9+1]; ObjectType
0x18009b635  lea     r8d, [r9+4]; SecurityInfo
0x18009b639  call    cs:__imp_SetNamedSecurityInfoW
0x18009b63f  test    eax, eax
0x18009b641  jz      short loc_18009B65D
0x18009b643  mov     rcx, [rbp+5Fh]; this
0x18009b647  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x18009b64e  mov     r9d, eax; char *
0x18009b651  mov     edx, 50h ; 'P'; void *
0x18009b656  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009b65b  jmp     short loc_18009B60D
0x18009b65d  mov     rcx, rdi; this
0x18009b660  call    ?DefFreeMemory@Resources@Microsoft@@YAXPEAX@Z; Microsoft::Resources::DefFreeMemory(void *)
0x18009b665  lea     rcx, [rbp+57h+pSid2]
0x18009b669  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009b66e  lea     rcx, [rbp+57h+var_68]
0x18009b672  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009b677  xor     eax, eax
0x18009b679  jmp     short loc_18009B6CD
0x18009b67b  mov     edx, 45h ; 'E'
0x18009b680  jmp     short loc_18009B687
0x18009b682  mov     edx, 44h ; 'D'; void *
0x18009b687  mov     ebx, 80070216h
0x18009b68c  mov     rcx, [rbp+5Fh]; this
0x18009b690  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x18009b697  mov     r9d, ebx; char *
0x18009b69a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b69f  lea     rcx, [rbp+57h+pSid2]
0x18009b6a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009b6a8  lea     rcx, [rbp+57h+var_68]
0x18009b6ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009b6b1  mov     rcx, rsi
0x18009b6b4  call    RemovePiiFromString
0x18009b6b9  xor     r8d, r8d
0x18009b6bc  lea     rcx, aMicrosoftResou_1; "Microsoft::Resources::Build::PriFileMer"...
0x18009b6c3  mov     rdx, rax
0x18009b6c6  call    MrtRuntimeTelemetry_GenericEventParam1
0x18009b6cb  mov     eax, ebx
0x18009b6cd  mov     rcx, [rbp+57h+var_40]
0x18009b6d1  xor     rcx, rsp; StackCookie
0x18009b6d4  call    __security_check_cookie
0x18009b6d9  add     rsp, 0A8h
0x18009b6e0  pop     r15
0x18009b6e2  pop     r14
0x18009b6e4  pop     rdi
0x18009b6e5  pop     rsi
0x18009b6e6  pop     rbx
0x18009b6e7  pop     rbp
0x18009b6e8  retn
```
