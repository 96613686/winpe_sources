# _DecodePin(void * (*)(ulong),void (*)(void *),ushort *,void *,_UNICODE_STRING *)

- ea: `0x1800625ec`
- end: `0x1800627c1`
- name: `?_DecodePin@@YAJP6APEAXK@ZP6AXPEAX@ZPEAG1PEAU_UNICODE_STRING@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(void *(*)(unsigned int), void (*)(void *), LPWSTR pszProtectedCredentials, HANDLE Token, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002db50`

## callees

- `0x1800625ec`
- `0x1800629a8`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062744`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180062709`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180062709`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800626bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800626bf`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18006265c`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18006265c`
- `ntdll!RtlInitUnicodeString` at `0x180062698`
- `ntdll!RtlInitUnicodeString` at `0x180062698`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x180062736`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x180062791`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x180062736`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x180062791`

## pseudocode

```c
__int64 __fastcall _DecodePin(
        void *(*a1)(unsigned int),
        void (*a2)(void *),
        LPWSTR pszProtectedCredentials,
        HANDLE Token,
        struct _UNICODE_STRING *a5)
{
  DWORD v5; // r15d
  unsigned int v11; // ebx
  __int64 v12; // rbx
  char v13; // r14
  WCHAR *v14; // rdi
  __int64 v15; // rcx
  WCHAR *v16; // rax
  DWORD pcchMaxChars; // [rsp+30h] [rbp-68h] BYREF
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+34h] [rbp-64h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-60h] BYREF

  v5 = 0;
  pcchMaxChars = 0;
  pProtectionType = CredUnprotected;
  DestinationString = 0;
  if ( !a5 )
    return 3221225485LL;
  *a5 = 0;
  if ( pszProtectedCredentials )
  {
    v12 = -1;
    do
      ++v12;
    while ( pszProtectedCredentials[v12] );
    if ( !CredIsProtectedW(pszProtectedCredentials, &pProtectionType) )
      return (unsigned int)-1073741811;
    v13 = 0;
    switch ( pProtectionType )
    {
      case CredUnprotected:
        goto LABEL_12;
      case CredUserProtection:
        if ( !SetThreadToken(0, Token) )
          return (unsigned int)-1073741555;
        v13 = 1;
        break;
      case CredTrustedProtection:
        break;
      default:
LABEL_12:
        v14 = pszProtectedCredentials;
        goto LABEL_13;
    }
    v14 = 0;
    if ( !CredUnprotectEx(2u, pszProtectedCredentials, v12 + 1, 0, &pcchMaxChars) )
    {
      if ( GetLastError() != 122 || !pcchMaxChars )
        goto LABEL_31;
      v5 = 2 * pcchMaxChars;
      v14 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))a1)(2 * pcchMaxChars);
      if ( !v14 )
      {
        v11 = -1073741670;
        goto LABEL_14;
      }
      if ( !CredUnprotectEx(2u, pszProtectedCredentials, v12 + 1, v14, &pcchMaxChars)
        || pcchMaxChars && v14[pcchMaxChars - 1] )
      {
LABEL_31:
        v11 = -1073741811;
        goto LABEL_14;
      }
    }
LABEL_13:
    RtlInitUnicodeString(&DestinationString, v14);
    v11 = _DuplicateUnicodeString(a1, a2, 0, &DestinationString, a5);
LABEL_14:
    if ( v13 )
      RevertToSelf();
    if ( v14 && v14 != pszProtectedCredentials )
    {
      v15 = v5;
      v16 = v14;
      if ( v5 )
      {
        do
        {
          *(_BYTE *)v16 = 0;
          v16 = (WCHAR *)((char *)v16 + 1);
          --v15;
        }
        while ( v15 );
      }
      ((void (__fastcall *)(WCHAR *))a2)(v14);
    }
    return v11;
  }
  return 0;
}

```

## disassembly

```asm
0x1800625ec  push    rbx
0x1800625ee  push    rbp
0x1800625ef  push    rsi
0x1800625f0  push    rdi
0x1800625f1  push    r12
0x1800625f3  push    r13
0x1800625f5  push    r14
0x1800625f7  push    r15
0x1800625f9  sub     rsp, 58h
0x1800625fd  mov     rbp, [rsp+98h+arg_20]
0x180062605  xor     r15d, r15d
0x180062608  mov     [rsp+98h+var_68], r15d
0x18006260d  xorps   xmm0, xmm0
0x180062610  mov     [rsp+98h+pProtectionType], r15d
0x180062615  mov     rdi, r9
0x180062618  mov     rsi, r8
0x18006261b  mov     r13, rdx
0x18006261e  mov     r12, rcx
0x180062621  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x180062626  test    rbp, rbp
0x180062629  jnz     short loc_180062635
0x18006262b  mov     eax, 0C000000Dh
0x180062630  jmp     loc_1800626F3
0x180062635  movups  xmmword ptr [rbp+0], xmm0
0x180062639  test    rsi, rsi
0x18006263c  jnz     short loc_180062646
0x18006263e  mov     ebx, r15d
0x180062641  jmp     loc_1800626F1
0x180062646  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006264a  inc     rbx
0x18006264d  cmp     [r8+rbx*2], r15w
0x180062652  jnz     short loc_18006264A
0x180062654  lea     rdx, [rsp+98h+pProtectionType]; pProtectionType
0x180062659  mov     rcx, rsi; pszProtectedCredentials
0x18006265c  call    cs:__imp_CredIsProtectedW
0x180062662  test    eax, eax
0x180062664  jnz     short loc_180062670
0x180062666  mov     ebx, 0C000000Dh
0x18006266b  jmp     loc_1800626F1
0x180062670  mov     ecx, [rsp+98h+pProtectionType]
0x180062674  mov     r14b, r15b
0x180062677  test    ecx, ecx
0x180062679  jz      short loc_18006268D
0x18006267b  sub     ecx, 1
0x18006267e  jz      loc_180062704
0x180062684  cmp     ecx, 1
0x180062687  jz      loc_18006271D
0x18006268d  mov     rdi, rsi
0x180062690  mov     rdx, rdi; SourceString
0x180062693  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180062698  call    cs:__imp_RtlInitUnicodeString
0x18006269e  lea     r9, [rsp+98h+DestinationString]; struct _UNICODE_STRING *
0x1800626a3  mov     [rsp+98h+pcchMaxChars], rbp; struct _UNICODE_STRING *
0x1800626a8  xor     r8d, r8d; int
0x1800626ab  mov     rdx, r13; void (*)(void *)
0x1800626ae  mov     rcx, r12; void *(*)(unsigned int)
0x1800626b1  call    ?_DuplicateUnicodeString@@YAJP6APEAXK@ZP6AXPEAX@ZHPEAU_UNICODE_STRING@@3@Z; _DuplicateUnicodeString(void * (*)(ulong),void (*)(void *),int,_UNICODE_STRING *,_UNICODE_STRING *)
0x1800626b6  mov     ebx, eax
0x1800626b8  xor     ebp, ebp
0x1800626ba  test    r14b, r14b
0x1800626bd  jz      short loc_1800626C5
0x1800626bf  call    cs:__imp_RevertToSelf
0x1800626c5  test    rdi, rdi
0x1800626c8  jz      short loc_1800626F1
0x1800626ca  cmp     rdi, rsi
0x1800626cd  jz      short loc_1800626F1
0x1800626cf  mov     ecx, r15d
0x1800626d2  mov     rax, rdi
0x1800626d5  test    r15d, r15d
0x1800626d8  jz      short loc_1800626E6
0x1800626da  mov     [rax], bpl
0x1800626dd  inc     rax
0x1800626e0  sub     rcx, 1
0x1800626e4  jnz     short loc_1800626DA
0x1800626e6  mov     rcx, rdi
0x1800626e9  mov     rax, r13
0x1800626ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626f1  mov     eax, ebx
0x1800626f3  add     rsp, 58h
0x1800626f7  pop     r15
0x1800626f9  pop     r14
0x1800626fb  pop     r13
0x1800626fd  pop     r12
0x1800626ff  pop     rdi
0x180062700  pop     rsi
0x180062701  pop     rbp
0x180062702  pop     rbx
0x180062703  retn
0x180062704  mov     rdx, rdi; Token
0x180062707  xor     ecx, ecx; Thread
0x180062709  call    cs:__imp_SetThreadToken
0x18006270f  test    eax, eax
0x180062711  jnz     short loc_18006271A
0x180062713  mov     ebx, 0C000010Dh
0x180062718  jmp     short loc_1800626F1
0x18006271a  mov     r14b, 1
0x18006271d  lea     rax, [rsp+98h+var_68]
0x180062722  xor     edi, edi
0x180062724  xor     r9d, r9d; pszCredentials
0x180062727  mov     [rsp+98h+pcchMaxChars], rax; pcchMaxChars
0x18006272c  lea     r8d, [rbx+1]; cchProtectedCredentials
0x180062730  mov     rdx, rsi; pszProtectedCredentials
0x180062733  lea     ecx, [rdi+2]; Flags
0x180062736  call    cs:__imp_CredUnprotectEx
0x18006273c  test    eax, eax
0x18006273e  jnz     loc_180062690
0x180062744  call    cs:__imp_GetLastError
0x18006274a  cmp     eax, 7Ah ; 'z'
0x18006274d  jnz     short loc_18006279D
0x18006274f  mov     eax, [rsp+98h+var_68]
0x180062753  test    eax, eax
0x180062755  jz      short loc_18006279D
0x180062757  lea     r15d, [rax+rax]
0x18006275b  mov     rax, r12
0x18006275e  mov     ecx, r15d
0x180062761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062766  mov     rdi, rax
0x180062769  test    rax, rax
0x18006276c  jnz     short loc_180062778
0x18006276e  mov     ebx, 0C000009Ah
0x180062773  jmp     loc_1800626B8
0x180062778  lea     rax, [rsp+98h+var_68]
0x18006277d  mov     r9, rdi; pszCredentials
0x180062780  lea     r8d, [rbx+1]; cchProtectedCredentials
0x180062784  mov     [rsp+98h+pcchMaxChars], rax; pcchMaxChars
0x180062789  mov     rdx, rsi; pszProtectedCredentials
0x18006278c  mov     ecx, 2; Flags
0x180062791  call    cs:__imp_CredUnprotectEx
0x180062797  xor     edx, edx
0x180062799  test    eax, eax
0x18006279b  jnz     short loc_1800627A7
0x18006279d  mov     ebx, 0C000000Dh
0x1800627a2  jmp     loc_1800626B8
0x1800627a7  mov     eax, [rsp+98h+var_68]
0x1800627ab  test    eax, eax
0x1800627ad  jz      loc_180062690
0x1800627b3  dec     eax
0x1800627b5  cmp     [rdi+rax*2], dx
0x1800627b9  jz      loc_180062690
0x1800627bf  jmp     short loc_18006279D
```
