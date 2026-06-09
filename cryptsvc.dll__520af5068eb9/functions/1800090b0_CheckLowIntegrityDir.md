# _CheckLowIntegrityDir

- ea: `0x1800090b0`
- end: `0x1800092d9`
- name: `_CheckLowIntegrityDir`
- size: `553`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006db0`
- `0x180009030`

## callees

- `0x1800090b0`
- `0x18000e2f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000928e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000928e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800092d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800092d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000911d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000911d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000924e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000924e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800092a8`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800092a8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180009240`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180009240`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800091f1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800091f1`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180009147`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180009147`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180009164`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180009164`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180009195`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180009195`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000920b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000920b`

## pseudocode

```c
__int64 __fastcall CheckLowIntegrityDir(LPCWSTR lpFileName, int *a2)
{
  DWORD LastError; // r12d
  int v5; // esi
  HLOCAL v6; // rdi
  struct _ACL *v7; // rcx
  DWORD AceCount; // ebx
  LPVOID v9; // rax
  DWORD i; // r15d
  unsigned int v11; // ebx
  __int64 result; // rax
  HLOCAL v13; // rax
  DWORD nLengthNeeded; // [rsp+68h] [rbp-19h] BYREF
  LPVOID pAce; // [rsp+70h] [rbp-11h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+78h] [rbp-9h] BYREF
  WINBOOL bSaclPresent; // [rsp+7Ch] [rbp-5h] BYREF
  PACL pSacl; // [rsp+80h] [rbp-1h] BYREF
  PSID pSid; // [rsp+88h] [rbp+7h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+Fh] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  LastError = 0;
  pSacl = 0;
  v5 = 0;
  pAce = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  nLengthNeeded = 1024;
  v6 = LocalAlloc(0x40u, 0x400u);
  if ( !v6 )
    goto LABEL_22;
  while ( !GetFileSecurityW(lpFileName, 0x10u, v6, nLengthNeeded, &nLengthNeeded) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
      goto LABEL_22;
    v13 = LocalReAlloc(v6, nLengthNeeded, 0x40u);
    if ( !v13 )
      goto LABEL_22;
    v6 = v13;
  }
  if ( !GetSecurityDescriptorSacl(v6, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_22;
  v7 = pSacl;
  AceCount = 0;
  if ( pSacl )
    AceCount = pSacl->AceCount;
  v9 = pAce;
  for ( i = 0; i < AceCount; ++i )
  {
    if ( !GetAce(v7, i, &pAce) )
      goto LABEL_22;
    v9 = pAce;
    if ( *(_BYTE *)pAce == 17 )
      break;
    v7 = pSacl;
    v9 = 0;
    pAce = 0;
  }
  v11 = 1;
  if ( v9 )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( EqualSid(pSid, (char *)pAce + 8) && (*((_BYTE *)pAce + 1) & 3) == 3 )
        v5 = 1;
      goto LABEL_15;
    }
LABEL_22:
    v11 = 0;
    LastError = GetLastError();
  }
LABEL_15:
  if ( pSid )
    FreeSid(pSid);
  if ( v6 )
    LocalFree(v6);
  if ( !v11 )
    SetLastError(LastError);
  result = v11;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x1800090b0  mov     r11, rsp
0x1800090b3  push    rbp
0x1800090b4  push    rbx
0x1800090b5  push    rsi
0x1800090b6  push    r12
0x1800090b8  push    r14
0x1800090ba  lea     rbp, [r11-5Fh]
0x1800090be  sub     rsp, 0B0h
0x1800090c5  mov     rax, cs:__security_cookie
0x1800090cc  xor     rax, rsp
0x1800090cf  mov     [rbp+57h+var_40], rax
0x1800090d3  mov     [r11+18h], rdi
0x1800090d7  mov     r14, rdx
0x1800090da  mov     [r11-30h], r13
0x1800090de  mov     rbx, rcx
0x1800090e1  xor     r13d, r13d
0x1800090e4  mov     [r11-38h], r15
0x1800090e8  mov     edx, 400h; uBytes
0x1800090ed  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x1800090f1  mov     ecx, 40h ; '@'; uFlags
0x1800090f6  mov     [rbp+57h+pSid], r13
0x1800090fa  mov     r12d, r13d
0x1800090fd  mov     [rbp+57h+pSacl], r13
0x180009101  mov     esi, r13d
0x180009104  mov     [rbp+57h+pAce], r13
0x180009108  mov     [rbp+57h+bSaclPresent], r13d
0x18000910c  mov     [rbp+57h+bSaclDefaulted], r13d
0x180009110  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 1000h
0x180009116  mov     [rbp+57h+nLengthNeeded], 400h
0x18000911d  call    cs:__imp_LocalAlloc
0x180009123  mov     rdi, rax
0x180009126  test    rax, rax
0x180009129  jz      loc_180009280
0x18000912f  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180009133  lea     rax, [rbp+57h+nLengthNeeded]
0x180009137  mov     r8, rdi; pSecurityDescriptor
0x18000913a  mov     [rsp+0D0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000913f  mov     edx, 10h; RequestedInformation
0x180009144  mov     rcx, rbx; lpFileName
0x180009147  call    cs:__imp_GetFileSecurityW
0x18000914d  test    eax, eax
0x18000914f  jz      loc_18000928E
0x180009155  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x180009159  mov     rcx, rdi; pSecurityDescriptor
0x18000915c  lea     r8, [rbp+57h+pSacl]; pSacl
0x180009160  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x180009164  call    cs:__imp_GetSecurityDescriptorSacl
0x18000916a  test    eax, eax
0x18000916c  jz      loc_180009280
0x180009172  mov     rcx, [rbp+57h+pSacl]; pAcl
0x180009176  mov     ebx, r13d
0x180009179  test    rcx, rcx
0x18000917c  jz      short loc_180009182
0x18000917e  movzx   ebx, word ptr [rcx+4]
0x180009182  mov     rax, [rbp+57h+pAce]
0x180009186  mov     r15d, r13d
0x180009189  cmp     r15d, ebx
0x18000918c  jnb     short loc_1800091B0
0x18000918e  lea     r8, [rbp+57h+pAce]; pAce
0x180009192  mov     edx, r15d; dwAceIndex
0x180009195  call    cs:__imp_GetAce
0x18000919b  test    eax, eax
0x18000919d  jz      loc_180009280
0x1800091a3  mov     rax, [rbp+57h+pAce]
0x1800091a7  cmp     byte ptr [rax], 11h
0x1800091aa  jnz     loc_1800092BB
0x1800091b0  mov     ebx, 1
0x1800091b5  test    rax, rax
0x1800091b8  jz      short loc_180009227
0x1800091ba  lea     rax, [rbp+57h+pSid]
0x1800091be  xor     r9d, r9d; nSubAuthority1
0x1800091c1  mov     [rsp+50h], rax; pSid
0x1800091c6  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800091ca  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x1800091cf  mov     r8d, 1000h; nSubAuthority0
0x1800091d5  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x1800091da  movzx   edx, bl; nSubAuthorityCount
0x1800091dd  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x1800091e2  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x1800091e7  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x1800091ec  mov     dword ptr [rsp+0D0h+lpnLengthNeeded], r13d; nSubAuthority2
0x1800091f1  call    cs:__imp_AllocateAndInitializeSid
0x1800091f7  test    eax, eax
0x1800091f9  jz      loc_180009280
0x1800091ff  mov     rdx, [rbp+57h+pAce]
0x180009203  mov     rcx, [rbp+57h+pSid]; pSid1
0x180009207  add     rdx, 8; pSid2
0x18000920b  call    cs:__imp_EqualSid
0x180009211  test    eax, eax
0x180009213  jz      short loc_180009227
0x180009215  mov     rax, [rbp+57h+pAce]
0x180009219  movzx   ecx, byte ptr [rax+1]
0x18000921d  and     cl, 3
0x180009220  cmp     cl, 3
0x180009223  jnz     short loc_180009227
0x180009225  mov     esi, ebx
0x180009227  mov     rcx, [rbp+57h+pSid]; pSid
0x18000922b  mov     r15, [rsp+0D0h+var_30]
0x180009233  mov     r13, [rsp+0A8h]
0x18000923b  test    rcx, rcx
0x18000923e  jz      short loc_180009246
0x180009240  call    cs:__imp_FreeSid
0x180009246  test    rdi, rdi
0x180009249  jz      short loc_180009254
0x18000924b  mov     rcx, rdi; hMem
0x18000924e  call    cs:__imp_LocalFree
0x180009254  mov     rdi, [rsp+0D0h+arg_10]
0x18000925c  test    ebx, ebx
0x18000925e  jz      short loc_1800092CE
0x180009260  mov     eax, ebx
0x180009262  mov     [r14], esi
0x180009265  mov     rcx, [rbp+57h+var_40]
0x180009269  xor     rcx, rsp; StackCookie
0x18000926c  call    __security_check_cookie
0x180009271  add     rsp, 0B0h
0x180009278  pop     r14
0x18000927a  pop     r12
0x18000927c  pop     rsi
0x18000927d  pop     rbx
0x18000927e  pop     rbp
0x18000927f  retn
0x180009280  mov     ebx, r13d
0x180009283  call    cs:__imp_GetLastError
0x180009289  mov     r12d, eax
0x18000928c  jmp     short loc_180009227
0x18000928e  call    cs:__imp_GetLastError
0x180009294  mov     r12d, eax
0x180009297  cmp     eax, 7Ah ; 'z'
0x18000929a  jnz     short loc_180009280
0x18000929c  mov     edx, [rbp+57h+nLengthNeeded]; uBytes
0x18000929f  mov     r8d, 40h ; '@'; uFlags
0x1800092a5  mov     rcx, rdi; hMem
0x1800092a8  call    cs:__imp_LocalReAlloc
0x1800092ae  test    rax, rax
0x1800092b1  jz      short loc_180009280
0x1800092b3  mov     rdi, rax
0x1800092b6  jmp     loc_18000912F
0x1800092bb  mov     rcx, [rbp+57h+pSacl]
0x1800092bf  mov     rax, r13
0x1800092c2  mov     [rbp+57h+pAce], rax
0x1800092c6  inc     r15d
0x1800092c9  jmp     loc_180009189
0x1800092ce  mov     ecx, r12d; dwErrCode
0x1800092d1  call    cs:__imp_SetLastError
0x1800092d7  jmp     short loc_180009260
```
