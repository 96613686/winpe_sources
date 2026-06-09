# ClRtlBuildDefaultClusterApiSD

- ea: `0x18009f6fc`
- end: `0x18009fa62`
- name: `ClRtlBuildDefaultClusterApiSD`
- size: `870`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078c80`

## callees

- `0x180002f50`
- `0x18009f6fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f9cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f9cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f9d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fa25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fa33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f9d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fa25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fa33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f852`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f871`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f9a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f852`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f871`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f9a9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18009f89f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18009f89f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009f989`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009f9c3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009f989`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009f9c3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009f91c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009f91c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18009f968`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18009f968`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18009f94c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18009f94c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009f8f3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009f8f3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009f88e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009f8ad`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009f88e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009f8ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f83c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f83c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18009fa05`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18009fa05`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18009f934`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18009f934`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f8d0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f8d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18009f80c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18009f80c`

## pseudocode

```c
__int64 __fastcall ClRtlBuildDefaultClusterApiSD(__int64 a1, _QWORD *a2, DWORD *a3)
{
  struct _ACL *v3; // r14
  struct _ACL *v5; // r15
  unsigned int v6; // ebx
  DWORD LastError; // ebx
  PSID v8; // r12
  DWORD v9; // esi
  __int64 i; // rbx
  struct _ACL *v11; // rax
  __int64 j; // rbx
  DWORD k; // ebx
  HLOCAL v14; // rax
  void *v15; // rsi
  DWORD *v16; // rcx
  DWORD v17; // eax
  __int64 m; // rdi
  PSID v19; // rcx
  DWORD dwBufferLength; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pAce; // [rsp+28h] [rbp-D8h] BYREF
  DWORD *v23; // [rsp+30h] [rbp-D0h]
  LPCWSTR StringSid; // [rsp+40h] [rbp-C0h]
  DWORD AccessMask; // [rsp+48h] [rbp-B8h]
  PSID pSid[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  const wchar_t *v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+78h] [rbp-88h]
  PSID pOwner; // [rsp+80h] [rbp-80h]
  const wchar_t *v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  const wchar_t *v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  const wchar_t *v38; // [rsp+B8h] [rbp-48h]
  int v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  const wchar_t *v41; // [rsp+D0h] [rbp-30h]
  int v42; // [rsp+D8h] [rbp-28h]
  __int64 v43; // [rsp+E0h] [rbp-20h]
  const wchar_t *v44; // [rsp+E8h] [rbp-18h]
  int v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  const wchar_t *v47; // [rsp+100h] [rbp+0h]
  int v48; // [rsp+108h] [rbp+8h]
  __int64 v49; // [rsp+110h] [rbp+10h]
  _BYTE pSecurityDescriptor[40]; // [rsp+120h] [rbp+20h] BYREF

  v3 = 0;
  v23 = a3;
  pAce = 0;
  StringSid = L"S-1-5-18";
  dwBufferLength = 0;
  pSid[1] = L"S-1-5-20";
  AccessMask = 3;
  v29 = L"S-1-5-32-544";
  v5 = 0;
  pSid[0] = 0;
  v32 = L"S-1-5-32-582";
  v6 = 0;
  v27 = 1;
  v35 = L"S-1-5-80-230328282-2568015442-686465752-3474446193-2137307224";
  v38 = L"S-1-5-80-1116079416-1731319938-396994126-3102800949-670876498";
  v41 = L"S-1-5-80-1071656157-3689046577-4105049408-574495319-1522408424";
  v44 = L"S-1-5-80-4130899010-3337817248-2959896732-3640118089-1866760602";
  v47 = L"S-1-5-80-2818357584-3387065753-4000393942-342927828-138088443";
  v28 = 0;
  v30 = 3;
  pOwner = 0;
  v33 = 3;
  v34 = 0;
  v36 = 3;
  v37 = 0;
  v39 = 3;
  v40 = 0;
  v42 = 3;
  v43 = 0;
  v45 = 3;
  v46 = 0;
  v48 = 3;
  v49 = 0;
  while ( v6 < 9 )
  {
    if ( !ConvertStringSidToSidW((&StringSid)[3 * v6], &pSid[3 * v6]) )
      goto LABEL_5;
    ++v6;
  }
  v8 = pOwner;
  v9 = 80;
  for ( i = 0; i != 9; ++i )
    v9 += GetLengthSid(pSid[3 * i]);
  v3 = (struct _ACL *)LocalAlloc(0x40u, v9);
  if ( !v3 )
  {
    LastError = 8;
    goto LABEL_31;
  }
  v11 = (struct _ACL *)LocalAlloc(0, 8u);
  v5 = v11;
  if ( !v11 )
  {
LABEL_30:
    LastError = 8;
    goto LABEL_31;
  }
  if ( !InitializeAcl(v11, 8u, 2u) )
    goto LABEL_5;
  InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
  InitializeAcl(v3, v9, 2u);
  for ( j = 0; (unsigned int)j < 9; j = (unsigned int)(j + 1) )
  {
    if ( !AddAccessAllowedAce(v3, 2u, (DWORD)pSid[3 * j], pSid[3 * j]) )
      goto LABEL_5;
  }
  for ( k = 0; k < 9; ++k )
  {
    if ( !GetAce(v3, k, &pAce) )
      goto LABEL_5;
    *((_BYTE *)pAce + 1) |= 3u;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v3, 0)
    || !SetSecurityDescriptorOwner(pSecurityDescriptor, v8, 0)
    || !SetSecurityDescriptorGroup(pSecurityDescriptor, v8, 0)
    || !SetSecurityDescriptorSacl(pSecurityDescriptor, 1, v5, 0) )
  {
LABEL_5:
    LastError = GetLastError();
    goto LABEL_31;
  }
  dwBufferLength = 0;
  if ( MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength) || (LastError = GetLastError(), LastError == 122) )
  {
    v14 = LocalAlloc(0x40u, dwBufferLength);
    v15 = v14;
    if ( v14 )
    {
      if ( MakeSelfRelativeSD(pSecurityDescriptor, v14, &dwBufferLength) )
      {
        v16 = v23;
        LastError = 0;
        v17 = dwBufferLength;
        *a2 = v15;
        *v16 = v17;
      }
      else
      {
        LastError = GetLastError();
        LocalFree(v15);
      }
      goto LABEL_31;
    }
    goto LABEL_30;
  }
LABEL_31:
  for ( m = 0; m != 9; ++m )
  {
    v19 = pSid[3 * m];
    if ( v19 )
    {
      FreeSid(v19);
      pSid[3 * m] = 0;
    }
  }
  if ( v3 )
    LocalFree(v3);
  if ( v5 )
    LocalFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x18009f6fc  mov     [rsp-8+arg_0], rbx
0x18009f701  push    rbp
0x18009f702  push    rsi
0x18009f703  push    rdi
0x18009f704  push    r12
0x18009f706  push    r13
0x18009f708  push    r14
0x18009f70a  push    r15
0x18009f70c  lea     rbp, [rsp-50h]
0x18009f711  sub     rsp, 150h
0x18009f718  mov     rax, cs:__security_cookie
0x18009f71f  xor     rax, rsp
0x18009f722  mov     [rbp+80h+var_38], rax
0x18009f726  xor     r14d, r14d
0x18009f729  mov     [rsp+180h+var_150], r8
0x18009f72e  lea     rax, aS1518; "S-1-5-18"
0x18009f735  mov     [rsp+180h+pAce], r14
0x18009f73a  mov     [rsp+180h+StringSid], rax
0x18009f73f  mov     r13, rdx
0x18009f742  lea     rax, aS1520; "S-1-5-20"
0x18009f749  mov     [rsp+180h+dwBufferLength], r14d
0x18009f74e  lea     ecx, [r14+3]
0x18009f752  mov     [rsp+180h+var_128], rax
0x18009f757  lea     rax, aS1532544; "S-1-5-32-544"
0x18009f75e  mov     [rsp+180h+AccessMask], ecx
0x18009f762  mov     [rsp+180h+var_110], rax
0x18009f767  mov     r15d, r14d
0x18009f76a  lea     rax, aS1532582; "S-1-5-32-582"
0x18009f771  mov     [rsp+180h+pSid], r14
0x18009f776  mov     [rbp+80h+var_F8], rax
0x18009f77a  mov     ebx, r14d
0x18009f77d  lea     rax, aS1580230328282; "S-1-5-80-230328282-2568015442-686465752"...
0x18009f784  mov     [rsp+180h+var_120], 1
0x18009f78c  mov     [rbp+80h+var_E0], rax
0x18009f790  lea     rax, aS1580111607941; "S-1-5-80-1116079416-1731319938-39699412"...
0x18009f797  mov     [rbp+80h+var_C8], rax
0x18009f79b  lea     rax, aS1580107165615; "S-1-5-80-1071656157-3689046577-41050494"...
0x18009f7a2  mov     [rbp+80h+var_B0], rax
0x18009f7a6  lea     rax, aS1580413089901; "S-1-5-80-4130899010-3337817248-29598967"...
0x18009f7ad  mov     [rbp+80h+var_98], rax
0x18009f7b1  lea     rax, aS1580281835758; "S-1-5-80-2818357584-3387065753-40003939"...
0x18009f7b8  mov     [rbp+80h+var_80], rax
0x18009f7bc  mov     [rsp+180h+var_118], r14
0x18009f7c1  mov     [rsp+180h+var_108], ecx
0x18009f7c5  mov     [rbp+80h+pOwner], r14
0x18009f7c9  mov     [rbp+80h+var_F0], ecx
0x18009f7cc  mov     [rbp+80h+var_E8], r14
0x18009f7d0  mov     [rbp+80h+var_D8], ecx
0x18009f7d3  mov     [rbp+80h+var_D0], r14
0x18009f7d7  mov     [rbp+80h+var_C0], ecx
0x18009f7da  mov     [rbp+80h+var_B8], r14
0x18009f7de  mov     [rbp+80h+var_A8], ecx
0x18009f7e1  mov     [rbp+80h+var_A0], r14
0x18009f7e5  mov     [rbp+80h+var_90], ecx
0x18009f7e8  mov     [rbp+80h+var_88], r14
0x18009f7ec  mov     [rbp+80h+var_78], ecx
0x18009f7ef  mov     [rbp+80h+var_70], r14
0x18009f7f3  cmp     ebx, 9
0x18009f7f6  jnb     short loc_18009F827
0x18009f7f8  mov     eax, ebx
0x18009f7fa  lea     rdx, [rsp+180h+pSid]
0x18009f7ff  lea     rcx, [rax+rax*2]
0x18009f803  lea     rdx, [rdx+rcx*8]; Sid
0x18009f807  mov     rcx, [rsp+rcx*8+180h+StringSid]; StringSid
0x18009f80c  call    cs:__imp_ConvertStringSidToSidW
0x18009f812  test    eax, eax
0x18009f814  jz      short loc_18009F81A
0x18009f816  inc     ebx
0x18009f818  jmp     short loc_18009F7F3
0x18009f81a  call    cs:__imp_GetLastError
0x18009f820  mov     ebx, eax
0x18009f822  jmp     loc_18009F9F5
0x18009f827  mov     r12, [rbp+80h+pOwner]
0x18009f82b  mov     esi, 50h ; 'P'
0x18009f830  mov     rbx, r14
0x18009f833  lea     rcx, [rbx+rbx*2]
0x18009f837  mov     rcx, [rsp+rcx*8+180h+pSid]; pSid
0x18009f83c  call    cs:__imp_GetLengthSid
0x18009f842  add     esi, eax
0x18009f844  inc     rbx
0x18009f847  cmp     rbx, 9
0x18009f84b  jnz     short loc_18009F833
0x18009f84d  mov     edx, esi; uBytes
0x18009f84f  lea     ecx, [rbx+37h]; uFlags
0x18009f852  call    cs:__imp_LocalAlloc
0x18009f858  mov     r14, rax
0x18009f85b  test    rax, rax
0x18009f85e  jnz     short loc_18009F868
0x18009f860  lea     ebx, [rax+8]
0x18009f863  jmp     loc_18009F9F5
0x18009f868  mov     edi, 8
0x18009f86d  xor     ecx, ecx; uFlags
0x18009f86f  mov     edx, edi; uBytes
0x18009f871  call    cs:__imp_LocalAlloc
0x18009f877  mov     r15, rax
0x18009f87a  test    rax, rax
0x18009f87d  jz      loc_18009F9F3
0x18009f883  lea     ebx, [rdi-6]
0x18009f886  mov     edx, edi; nAclLength
0x18009f888  mov     r8d, ebx; dwAclRevision
0x18009f88b  mov     rcx, rax; pAcl
0x18009f88e  call    cs:__imp_InitializeAcl
0x18009f894  test    eax, eax
0x18009f896  jz      short loc_18009F81A
0x18009f898  lea     edx, [rdi-7]; dwRevision
0x18009f89b  lea     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x18009f89f  call    cs:__imp_InitializeSecurityDescriptor
0x18009f8a5  mov     r8d, ebx; dwAclRevision
0x18009f8a8  mov     edx, esi; nAclLength
0x18009f8aa  mov     rcx, r14; pAcl
0x18009f8ad  call    cs:__imp_InitializeAcl
0x18009f8b3  xor     ebx, ebx
0x18009f8b5  cmp     ebx, 9
0x18009f8b8  jnb     short loc_18009F8E2
0x18009f8ba  lea     r8, [rbx+rbx*2]
0x18009f8be  mov     edx, 2; dwAceRevision
0x18009f8c3  mov     r9, [rsp+r8*8+180h+pSid]; pSid
0x18009f8c8  mov     rcx, r14; pAcl
0x18009f8cb  mov     r8d, [rsp+r8*8+180h+AccessMask]; AccessMask
0x18009f8d0  call    cs:__imp_AddAccessAllowedAce
0x18009f8d6  test    eax, eax
0x18009f8d8  jz      loc_18009F81A
0x18009f8de  inc     ebx
0x18009f8e0  jmp     short loc_18009F8B5
0x18009f8e2  xor     ebx, ebx
0x18009f8e4  cmp     ebx, 9
0x18009f8e7  jnb     short loc_18009F90E
0x18009f8e9  lea     r8, [rsp+180h+pAce]; pAce
0x18009f8ee  mov     edx, ebx; dwAceIndex
0x18009f8f0  mov     rcx, r14; pAcl
0x18009f8f3  call    cs:__imp_GetAce
0x18009f8f9  test    eax, eax
0x18009f8fb  jz      loc_18009F81A
0x18009f901  mov     rax, [rsp+180h+pAce]
0x18009f906  or      byte ptr [rax+1], 3
0x18009f90a  inc     ebx
0x18009f90c  jmp     short loc_18009F8E4
0x18009f90e  xor     r9d, r9d; bDaclDefaulted
0x18009f911  lea     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x18009f915  mov     r8, r14; pDacl
0x18009f918  lea     edx, [r9+1]; bDaclPresent
0x18009f91c  call    cs:__imp_SetSecurityDescriptorDacl
0x18009f922  test    eax, eax
0x18009f924  jz      loc_18009F81A
0x18009f92a  xor     r8d, r8d; bOwnerDefaulted
0x18009f92d  lea     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x18009f931  mov     rdx, r12; pOwner
0x18009f934  call    cs:__imp_SetSecurityDescriptorOwner
0x18009f93a  test    eax, eax
0x18009f93c  jz      loc_18009F81A
0x18009f942  xor     r8d, r8d; bGroupDefaulted
0x18009f945  lea     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x18009f949  mov     rdx, r12; pGroup
0x18009f94c  call    cs:__imp_SetSecurityDescriptorGroup
0x18009f952  test    eax, eax
0x18009f954  jz      loc_18009F81A
0x18009f95a  xor     r9d, r9d; bSaclDefaulted
0x18009f95d  lea     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x18009f961  mov     r8, r15; pSacl
0x18009f964  lea     edx, [r9+1]; bSaclPresent
0x18009f968  call    cs:__imp_SetSecurityDescriptorSacl
0x18009f96e  test    eax, eax
0x18009f970  jz      loc_18009F81A
0x18009f976  lea     r8, [rsp+180h+dwBufferLength]; lpdwBufferLength
0x18009f97b  mov     [rsp+180h+dwBufferLength], 0
0x18009f983  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18009f985  lea     rcx, [rbp+80h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18009f989  call    cs:__imp_MakeSelfRelativeSD
0x18009f98f  test    eax, eax
0x18009f991  jnz     short loc_18009F9A0
0x18009f993  call    cs:__imp_GetLastError
0x18009f999  mov     ebx, eax
0x18009f99b  cmp     eax, 7Ah ; 'z'
0x18009f99e  jnz     short loc_18009F9F5
0x18009f9a0  mov     edx, [rsp+180h+dwBufferLength]; uBytes
0x18009f9a4  mov     ecx, 40h ; '@'; uFlags
0x18009f9a9  call    cs:__imp_LocalAlloc
0x18009f9af  mov     rsi, rax
0x18009f9b2  test    rax, rax
0x18009f9b5  jz      short loc_18009F9F3
0x18009f9b7  lea     r8, [rsp+180h+dwBufferLength]; lpdwBufferLength
0x18009f9bc  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18009f9bf  lea     rcx, [rbp+80h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18009f9c3  call    cs:__imp_MakeSelfRelativeSD
0x18009f9c9  test    eax, eax
0x18009f9cb  jnz     short loc_18009F9E0
0x18009f9cd  call    cs:__imp_GetLastError
0x18009f9d3  mov     rcx, rsi; hMem
0x18009f9d6  mov     ebx, eax
0x18009f9d8  call    cs:__imp_LocalFree
0x18009f9de  jmp     short loc_18009F9F5
0x18009f9e0  mov     rcx, [rsp+180h+var_150]
0x18009f9e5  xor     ebx, ebx
0x18009f9e7  mov     eax, [rsp+180h+dwBufferLength]
0x18009f9eb  mov     [r13+0], rsi
0x18009f9ef  mov     [rcx], eax
0x18009f9f1  jmp     short loc_18009F9F5
0x18009f9f3  mov     ebx, edi
0x18009f9f5  xor     edi, edi
0x18009f9f7  lea     rsi, [rdi+rdi*2]
0x18009f9fb  mov     rcx, [rsp+rsi*8+180h+pSid]; pSid
0x18009fa00  test    rcx, rcx
0x18009fa03  jz      short loc_18009FA14
0x18009fa05  call    cs:__imp_FreeSid
0x18009fa0b  mov     [rsp+rsi*8+180h+pSid], 0
0x18009fa14  inc     rdi
0x18009fa17  cmp     rdi, 9
0x18009fa1b  jnz     short loc_18009F9F7
0x18009fa1d  test    r14, r14
0x18009fa20  jz      short loc_18009FA2B
0x18009fa22  mov     rcx, r14; hMem
0x18009fa25  call    cs:__imp_LocalFree
0x18009fa2b  test    r15, r15
0x18009fa2e  jz      short loc_18009FA39
0x18009fa30  mov     rcx, r15; hMem
0x18009fa33  call    cs:__imp_LocalFree
0x18009fa39  mov     eax, ebx
0x18009fa3b  mov     rcx, [rbp+80h+var_38]
0x18009fa3f  xor     rcx, rsp; StackCookie
0x18009fa42  call    __security_check_cookie
0x18009fa47  mov     rbx, [rsp+180h+arg_0]
0x18009fa4f  add     rsp, 150h
0x18009fa56  pop     r15
0x18009fa58  pop     r14
0x18009fa5a  pop     r13
0x18009fa5c  pop     r12
0x18009fa5e  pop     rdi
0x18009fa5f  pop     rsi
0x18009fa60  pop     rbp
0x18009fa61  retn
```
