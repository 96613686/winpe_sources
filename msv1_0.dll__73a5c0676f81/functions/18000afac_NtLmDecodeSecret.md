# NtLmDecodeSecret

- ea: `0x18000afac`
- end: `0x18000b191`
- name: `NtLmDecodeSecret`
- size: `485`
- prototype: `__int64 __fastcall(LPWSTR pszProtectedCredentials, HANDLE Token)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007a20`
- `0x18001a470`
- `0x1800323f8`

## callees

- `0x180006c50`
- `0x180007700`
- `0x18000afac`
- `0x18000cba0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b067`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b112`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b0ba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b0ba`
- `ntdll!RtlInitUnicodeString` at `0x18000b04d`
- `ntdll!RtlInitUnicodeString` at `0x18000b04d`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18000b012`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18000b012`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x18000b104`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x18000b15f`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x18000b104`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x18000b15f`

## pseudocode

```c
__int64 __fastcall NtLmDecodeSecret(LPWSTR pszProtectedCredentials, HANDLE Token, _OWORD *a3)
{
  __int64 v7; // rbp
  int v8; // ebx
  char v9; // r15
  DWORD v10; // r12d
  WCHAR *v11; // rdi
  __int64 v12; // rcx
  WCHAR *v13; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  DWORD pcchMaxChars; // [rsp+90h] [rbp+18h] BYREF
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+98h] [rbp+20h] BYREF

  pcchMaxChars = 0;
  pProtectionType = CredUnprotected;
  DestinationString = 0;
  if ( !a3 )
    return 3221225485LL;
  *a3 = 0;
  if ( !pszProtectedCredentials )
    return 0;
  v7 = -1;
  do
    ++v7;
  while ( pszProtectedCredentials[v7] );
  if ( CredIsProtectedW(pszProtectedCredentials, &pProtectionType) )
  {
    v9 = 0;
    v10 = 0;
    if ( pProtectionType )
    {
      if ( pProtectionType == CredUserProtection )
      {
        if ( Token )
        {
          if ( !SetThreadToken(0, Token) )
            return (unsigned int)-1073741555;
        }
        else
        {
          v8 = LsaFunctions->ImpersonateClient();
          if ( v8 < 0 )
            return (unsigned int)v8;
        }
        v9 = 1;
      }
      else if ( pProtectionType != CredTrustedProtection )
      {
        goto LABEL_12;
      }
      v11 = 0;
      if ( !CredUnprotectEx(2u, pszProtectedCredentials, v7 + 1, 0, &pcchMaxChars) )
      {
        if ( GetLastError() != 122 || !pcchMaxChars )
          goto LABEL_33;
        v10 = 2 * pcchMaxChars;
        v11 = (WCHAR *)NtLmAllocate(2 * pcchMaxChars);
        if ( !v11 )
        {
          v8 = -1073741670;
          goto LABEL_14;
        }
        if ( !CredUnprotectEx(2u, pszProtectedCredentials, v7 + 1, v11, &pcchMaxChars)
          || pcchMaxChars && v11[pcchMaxChars - 1] )
        {
LABEL_33:
          v8 = -1073741811;
          goto LABEL_14;
        }
      }
LABEL_13:
      RtlInitUnicodeString(&DestinationString, v11);
      v8 = NtLmDuplicateUnicodeString(a3, &DestinationString);
LABEL_14:
      if ( v9 )
        RevertToSelf();
      if ( v11 && v11 != pszProtectedCredentials )
      {
        v12 = v10;
        v13 = v11;
        if ( v10 )
        {
          do
          {
            *(_BYTE *)v13 = 0;
            v13 = (WCHAR *)((char *)v13 + 1);
            --v12;
          }
          while ( v12 );
        }
        NtLmFree(v11);
      }
      return (unsigned int)v8;
    }
LABEL_12:
    v11 = pszProtectedCredentials;
    goto LABEL_13;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x18000afac  mov     rax, rsp
0x18000afaf  mov     [rax+8], rbx
0x18000afb3  push    rbp
0x18000afb4  push    rsi
0x18000afb5  push    rdi
0x18000afb6  push    r12
0x18000afb8  push    r13
0x18000afba  push    r14
0x18000afbc  push    r15
0x18000afbe  sub     rsp, 40h
0x18000afc2  xor     r13d, r13d
0x18000afc5  xorps   xmm0, xmm0
0x18000afc8  mov     [rax+18h], r13d
0x18000afcc  mov     r14, r8
0x18000afcf  mov     [rax+20h], r13d
0x18000afd3  mov     rbx, rdx
0x18000afd6  mov     rsi, rcx
0x18000afd9  movups  xmmword ptr [rax-48h], xmm0
0x18000afdd  test    r8, r8
0x18000afe0  jnz     short loc_18000AFEC
0x18000afe2  mov     eax, 0C000000Dh
0x18000afe7  jmp     loc_18000B098
0x18000afec  movups  xmmword ptr [r8], xmm0
0x18000aff0  test    rsi, rsi
0x18000aff3  jnz     short loc_18000AFFC
0x18000aff5  xor     eax, eax
0x18000aff7  jmp     loc_18000B098
0x18000affc  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b000  inc     rbp
0x18000b003  cmp     [rcx+rbp*2], r13w
0x18000b008  jnz     short loc_18000B000
0x18000b00a  lea     rdx, [rsp+78h+pProtectionType]; pProtectionType
0x18000b012  call    cs:__imp_CredIsProtectedW
0x18000b018  test    eax, eax
0x18000b01a  jnz     short loc_18000B023
0x18000b01c  mov     ebx, 0C000000Dh
0x18000b021  jmp     short loc_18000B096
0x18000b023  mov     ecx, [rsp+78h+pProtectionType]
0x18000b02a  mov     r15b, r13b
0x18000b02d  mov     r12d, r13d
0x18000b030  test    ecx, ecx
0x18000b032  jz      short loc_18000B042
0x18000b034  sub     ecx, 1
0x18000b037  jz      short loc_18000B0B0
0x18000b039  cmp     ecx, 1
0x18000b03c  jz      loc_18000B0E4
0x18000b042  mov     rdi, rsi
0x18000b045  mov     rdx, rdi; SourceString
0x18000b048  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18000b04d  call    cs:__imp_RtlInitUnicodeString
0x18000b053  lea     rdx, [rsp+78h+DestinationString]
0x18000b058  mov     rcx, r14
0x18000b05b  call    NtLmDuplicateUnicodeString
0x18000b060  mov     ebx, eax
0x18000b062  test    r15b, r15b
0x18000b065  jz      short loc_18000B06D
0x18000b067  call    cs:__imp_RevertToSelf
0x18000b06d  test    rdi, rdi
0x18000b070  jz      short loc_18000B096
0x18000b072  cmp     rdi, rsi
0x18000b075  jz      short loc_18000B096
0x18000b077  mov     ecx, r12d
0x18000b07a  mov     rax, rdi
0x18000b07d  test    r12d, r12d
0x18000b080  jz      short loc_18000B08E
0x18000b082  mov     [rax], r13b
0x18000b085  inc     rax
0x18000b088  sub     rcx, 1
0x18000b08c  jnz     short loc_18000B082
0x18000b08e  mov     rcx, rdi
0x18000b091  call    NtLmFree
0x18000b096  mov     eax, ebx
0x18000b098  mov     rbx, [rsp+78h+arg_0]
0x18000b0a0  add     rsp, 40h
0x18000b0a4  pop     r15
0x18000b0a6  pop     r14
0x18000b0a8  pop     r13
0x18000b0aa  pop     r12
0x18000b0ac  pop     rdi
0x18000b0ad  pop     rsi
0x18000b0ae  pop     rbp
0x18000b0af  retn
0x18000b0b0  test    rbx, rbx
0x18000b0b3  jz      short loc_18000B0CB
0x18000b0b5  mov     rdx, rbx; Token
0x18000b0b8  xor     ecx, ecx; Thread
0x18000b0ba  call    cs:__imp_SetThreadToken
0x18000b0c0  test    eax, eax
0x18000b0c2  jnz     short loc_18000B0E1
0x18000b0c4  mov     ebx, 0C000010Dh
0x18000b0c9  jmp     short loc_18000B096
0x18000b0cb  mov     rax, cs:LsaFunctions
0x18000b0d2  mov     rax, [rax+58h]
0x18000b0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0db  mov     ebx, eax
0x18000b0dd  test    eax, eax
0x18000b0df  js      short loc_18000B096
0x18000b0e1  mov     r15b, 1
0x18000b0e4  xor     r9d, r9d; pszCredentials
0x18000b0e7  lea     rax, [rsp+78h+arg_10]
0x18000b0ef  lea     r8d, [rbp+1]; cchProtectedCredentials
0x18000b0f3  mov     [rsp+78h+pcchMaxChars], rax; pcchMaxChars
0x18000b0f8  mov     rdx, rsi; pszProtectedCredentials
0x18000b0fb  mov     rdi, r13
0x18000b0fe  lea     ebx, [r9+2]
0x18000b102  mov     ecx, ebx; Flags
0x18000b104  call    cs:__imp_CredUnprotectEx
0x18000b10a  test    eax, eax
0x18000b10c  jnz     loc_18000B045
0x18000b112  call    cs:__imp_GetLastError
0x18000b118  cmp     eax, 7Ah ; 'z'
0x18000b11b  jnz     short loc_18000B169
0x18000b11d  mov     eax, [rsp+78h+arg_10]
0x18000b124  test    eax, eax
0x18000b126  jz      short loc_18000B169
0x18000b128  lea     r12d, [rax+rax]
0x18000b12c  mov     ecx, r12d; uBytes
0x18000b12f  call    NtLmAllocate
0x18000b134  mov     rdi, rax
0x18000b137  test    rax, rax
0x18000b13a  jnz     short loc_18000B146
0x18000b13c  mov     ebx, 0C000009Ah
0x18000b141  jmp     loc_18000B062
0x18000b146  lea     rax, [rsp+78h+arg_10]
0x18000b14e  mov     r9, rdi; pszCredentials
0x18000b151  lea     r8d, [rbp+1]; cchProtectedCredentials
0x18000b155  mov     [rsp+78h+pcchMaxChars], rax; pcchMaxChars
0x18000b15a  mov     rdx, rsi; pszProtectedCredentials
0x18000b15d  mov     ecx, ebx; Flags
0x18000b15f  call    cs:__imp_CredUnprotectEx
0x18000b165  test    eax, eax
0x18000b167  jnz     short loc_18000B173
0x18000b169  mov     ebx, 0C000000Dh
0x18000b16e  jmp     loc_18000B062
0x18000b173  mov     eax, [rsp+78h+arg_10]
0x18000b17a  test    eax, eax
0x18000b17c  jz      loc_18000B045
0x18000b182  dec     eax
0x18000b184  cmp     [rdi+rax*2], r13w
0x18000b189  jz      loc_18000B045
0x18000b18f  jmp     short loc_18000B169
```
