# KerbDecodeSecretEx(ushort *,void *,uchar,_UNICODE_STRING *,uchar,_CRED_PROTECTION_TYPE *)

- ea: `0x1800326a0`
- end: `0x18003295c`
- name: `?KerbDecodeSecretEx@@YAJPEAGPEAXEPEAU_UNICODE_STRING@@EPEAW4_CRED_PROTECTION_TYPE@@@Z`
- size: `700`
- prototype: `__int64 __fastcall(LPWSTR pszProtectedCredentials, HANDLE Token, char, struct _UNICODE_STRING *, unsigned __int8, enum _CRED_PROTECTION_TYPE *)`
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007f00`
- `0x180025680`
- `0x180059ed0`
- `0x1800974f0`
- `0x1800adccc`
- `0x1800b2c30`
- `0x1800b7a24`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18000b300`
- `0x1800326a0`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032838`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180032787`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180032787`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032904`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032904`
- `ntdll!RtlInitUnicodeString` at `0x180032772`
- `ntdll!RtlInitUnicodeString` at `0x180032772`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x180032714`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x180032714`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x18003282a`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x180032885`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x18003282a`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x180032885`

## string_xrefs

- `0x180032797`: `Unable to impersonate the client token handle %d.\n`
- `0x1800327d9`: `Unable to impersonate client, 0x%x.\n`

## pseudocode

```c
__int64 __fastcall KerbDecodeSecretEx(
        LPWSTR pszProtectedCredentials,
        HANDLE Token,
        char a3,
        struct _UNICODE_STRING *a4,
        unsigned __int8 a5,
        enum _CRED_PROTECTION_TYPE *a6)
{
  DWORD v6; // r15d
  __int64 v12; // rbx
  __int64 v13; // rdi
  int v15; // ebx
  char v16; // r14
  WCHAR *v17; // rbp
  DWORD LastError; // eax
  int v19; // eax
  bool v20; // cf
  ULONG v21; // ebx
  __int64 v22; // rcx
  WCHAR *v23; // rax
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-40h] BYREF
  DWORD pcchMaxChars; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  pcchMaxChars = 0;
  pProtectionType = CredUnprotected;
  DestinationString = 0;
  if ( !a4 )
    return 3221225485LL;
  *a4 = 0;
  if ( !pszProtectedCredentials )
    return 0;
  v12 = -1;
  v13 = -1;
  while ( pszProtectedCredentials[++v13] != 0 )
    ;
  if ( CredIsProtectedW(pszProtectedCredentials, &pProtectionType) )
  {
    v16 = 0;
    switch ( pProtectionType )
    {
      case CredUnprotected:
        goto LABEL_12;
      case CredUserProtection:
        if ( Token )
        {
          if ( !SetThreadToken(0, Token) )
          {
            LastError = GetLastError();
            KerbTracerT::Log(
              1,
              "KerbDecodeSecretEx",
              4372,
              "Unable to impersonate the client token handle %d.\n",
              LastError);
            return (unsigned int)-1073741555;
          }
        }
        else
        {
          v19 = LsaFunctions->ImpersonateClient();
          v15 = v19;
          if ( v19 < 0 )
          {
            KerbTracerT::Log(1, "KerbDecodeSecretEx", 4384, "Unable to impersonate client, 0x%x.\n", v19);
            return (unsigned int)v15;
          }
        }
        v16 = 1;
        break;
      case CredTrustedProtection:
        break;
      default:
LABEL_12:
        v17 = pszProtectedCredentials;
        do
          ++v12;
        while ( pszProtectedCredentials[v12] );
        pcchMaxChars = v12;
        goto LABEL_15;
    }
    v17 = 0;
    v20 = a5 != 0;
    a5 = -a5;
    v21 = v20 ? 2 : 0;
    if ( CredUnprotectEx(v21, pszProtectedCredentials, v13 + 1, 0, &pcchMaxChars) )
    {
      LOWORD(v12) = pcchMaxChars;
LABEL_15:
      if ( a3 )
      {
        RtlInitUnicodeString(&DestinationString, v17);
      }
      else
      {
        DestinationString.Buffer = v17;
        DestinationString.Length = 2 * v12;
        DestinationString.MaximumLength = 2 * v12;
      }
      v15 = KerbDuplicateStringEx(a4, &DestinationString);
      if ( v15 >= 0 && a6 )
        *a6 = pProtectionType;
      goto LABEL_38;
    }
    if ( GetLastError() == 122 && pcchMaxChars )
    {
      v6 = 2 * pcchMaxChars;
      v17 = (WCHAR *)MIDL_user_allocate(2 * pcchMaxChars);
      if ( !v17 )
      {
        v15 = -1073741670;
        goto LABEL_38;
      }
      if ( CredUnprotectEx(v21, pszProtectedCredentials, v13 + 1, v17, &pcchMaxChars) )
      {
        LOWORD(v12) = pcchMaxChars;
        if ( !pcchMaxChars || !v17[pcchMaxChars - 1] )
          goto LABEL_15;
        v15 = -1073741811;
LABEL_38:
        if ( v16 )
          RevertToSelf();
        if ( v17 && v17 != pszProtectedCredentials )
        {
          v22 = v6;
          v23 = v17;
          if ( v6 )
          {
            do
            {
              *(_BYTE *)v23 = 0;
              v23 = (WCHAR *)((char *)v23 + 1);
              --v22;
            }
            while ( v22 );
          }
          KerbFree(v17);
        }
        return (unsigned int)v15;
      }
    }
    v15 = -1073741811;
    goto LABEL_38;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x1800326a0  mov     rax, rsp
0x1800326a3  mov     [rax+18h], rbx
0x1800326a7  push    rbp
0x1800326a8  push    rsi
0x1800326a9  push    r12
0x1800326ab  push    r13
0x1800326ad  push    r15
0x1800326af  sub     rsp, 50h
0x1800326b3  xor     r15d, r15d
0x1800326b6  xorps   xmm0, xmm0
0x1800326b9  mov     [rax+20h], r15d
0x1800326bd  mov     r12, r9
0x1800326c0  mov     [rax-48h], r15d
0x1800326c4  movzx   r13d, r8b
0x1800326c8  mov     rbp, rdx
0x1800326cb  mov     rsi, rcx
0x1800326ce  movups  xmmword ptr [rax-40h], xmm0
0x1800326d2  test    r9, r9
0x1800326d5  jnz     short loc_1800326E1
0x1800326d7  mov     eax, 0C000000Dh
0x1800326dc  jmp     loc_180032947
0x1800326e1  movups  xmmword ptr [r9], xmm0
0x1800326e5  test    rsi, rsi
0x1800326e8  jnz     short loc_1800326F1
0x1800326ea  xor     eax, eax
0x1800326ec  jmp     loc_180032947
0x1800326f1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800326f8  mov     [rsp+78h+arg_0], rdi
0x180032700  mov     rdi, rbx
0x180032703  cmp     [rcx+rdi*2+2], r15w
0x180032709  lea     rdi, [rdi+1]
0x18003270d  jnz     short loc_180032703
0x18003270f  lea     rdx, [rsp+78h+pProtectionType]; pProtectionType
0x180032714  call    cs:__imp_CredIsProtectedW
0x18003271a  test    eax, eax
0x18003271c  jnz     short loc_180032728
0x18003271e  mov     ebx, 0C000000Dh
0x180032723  jmp     loc_18003293D
0x180032728  mov     ecx, [rsp+78h+pProtectionType]
0x18003272c  mov     [rsp+78h+arg_8], r14
0x180032734  xor     r14b, r14b
0x180032737  test    ecx, ecx
0x180032739  jz      short loc_180032749
0x18003273b  sub     ecx, 1
0x18003273e  jz      short loc_18003277D
0x180032740  cmp     ecx, 1
0x180032743  jz      loc_180032803
0x180032749  mov     rbp, rsi
0x18003274c  nop     dword ptr [rax+00h]
0x180032750  inc     rbx
0x180032753  cmp     [rsi+rbx*2], r15w
0x180032758  jnz     short loc_180032750
0x18003275a  mov     [rsp+78h+arg_18], ebx
0x180032761  test    r13b, r13b
0x180032764  jz      loc_1800328C7
0x18003276a  mov     rdx, rbp; SourceString
0x18003276d  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180032772  call    cs:__imp_RtlInitUnicodeString
0x180032778  jmp     loc_1800328D9
0x18003277d  test    rbp, rbp
0x180032780  jz      short loc_1800327C3
0x180032782  mov     rdx, rbp; Token
0x180032785  xor     ecx, ecx; Thread
0x180032787  call    cs:__imp_SetThreadToken
0x18003278d  test    eax, eax
0x18003278f  jnz     short loc_180032800
0x180032791  call    cs:__imp_GetLastError
0x180032797  lea     r9, aUnableToImpers; "Unable to impersonate the client token "...
0x18003279e  mov     r8d, 1114h
0x1800327a4  lea     rdx, aKerbdecodesecr; "KerbDecodeSecretEx"
0x1800327ab  mov     dword ptr [rsp+78h+pcchMaxChars], eax
0x1800327af  mov     ecx, 1
0x1800327b4  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800327b9  mov     ebx, 0C000010Dh
0x1800327be  jmp     loc_180032935
0x1800327c3  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800327ca  mov     rax, [rax+58h]
0x1800327ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327d3  mov     ebx, eax
0x1800327d5  test    eax, eax
0x1800327d7  jns     short loc_180032800
0x1800327d9  lea     r9, aUnableToImpers_2; "Unable to impersonate client, 0x%x.\n"
0x1800327e0  mov     dword ptr [rsp+78h+pcchMaxChars], eax
0x1800327e4  mov     r8d, 1120h
0x1800327ea  lea     rdx, aKerbdecodesecr; "KerbDecodeSecretEx"
0x1800327f1  mov     ecx, 1
0x1800327f6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800327fb  jmp     loc_180032935
0x180032800  mov     r14b, 1
0x180032803  lea     rax, [rsp+78h+arg_18]
0x18003280b  xor     ebp, ebp
0x18003280d  neg     [rsp+78h+arg_20]
0x180032814  lea     r8d, [rdi+1]; cchProtectedCredentials
0x180032818  mov     rdx, rsi; pszProtectedCredentials
0x18003281b  mov     [rsp+78h+pcchMaxChars], rax; pcchMaxChars
0x180032820  sbb     ebx, ebx
0x180032822  xor     r9d, r9d; pszCredentials
0x180032825  and     ebx, 2
0x180032828  mov     ecx, ebx; Flags
0x18003282a  call    cs:__imp_CredUnprotectEx
0x180032830  test    eax, eax
0x180032832  jnz     loc_1800328BB
0x180032838  call    cs:__imp_GetLastError
0x18003283e  cmp     eax, 7Ah ; 'z'
0x180032841  jnz     short loc_18003288F
0x180032843  mov     eax, [rsp+78h+arg_18]
0x18003284a  test    eax, eax
0x18003284c  jz      short loc_18003288F
0x18003284e  lea     r15d, [rax+rax]
0x180032852  mov     ecx, r15d; size
0x180032855  call    MIDL_user_allocate
0x18003285a  mov     rbp, rax
0x18003285d  test    rax, rax
0x180032860  jnz     short loc_18003286C
0x180032862  mov     ebx, 0C000009Ah
0x180032867  jmp     loc_1800328FF
0x18003286c  lea     rax, [rsp+78h+arg_18]
0x180032874  mov     r9, rbp; pszCredentials
0x180032877  lea     r8d, [rdi+1]; cchProtectedCredentials
0x18003287b  mov     [rsp+78h+pcchMaxChars], rax; pcchMaxChars
0x180032880  mov     rdx, rsi; pszProtectedCredentials
0x180032883  mov     ecx, ebx; Flags
0x180032885  call    cs:__imp_CredUnprotectEx
0x18003288b  test    eax, eax
0x18003288d  jnz     short loc_180032896
0x18003288f  mov     ebx, 0C000000Dh
0x180032894  jmp     short loc_1800328FF
0x180032896  mov     ebx, [rsp+78h+arg_18]
0x18003289d  test    ebx, ebx
0x18003289f  jz      loc_180032761
0x1800328a5  lea     eax, [rbx-1]
0x1800328a8  cmp     word ptr [rbp+rax*2+0], 0
0x1800328ae  jz      loc_180032761
0x1800328b4  mov     ebx, 0C000000Dh
0x1800328b9  jmp     short loc_1800328FF
0x1800328bb  mov     ebx, [rsp+78h+arg_18]
0x1800328c2  jmp     loc_180032761
0x1800328c7  add     bx, bx
0x1800328ca  mov     [rsp+78h+DestinationString.Buffer], rbp
0x1800328cf  mov     [rsp+78h+DestinationString.Length], bx
0x1800328d4  mov     [rsp+78h+DestinationString.MaximumLength], bx
0x1800328d9  lea     rdx, [rsp+78h+DestinationString]; struct _UNICODE_STRING *
0x1800328de  mov     rcx, r12; struct _UNICODE_STRING *
0x1800328e1  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800328e6  mov     ebx, eax
0x1800328e8  test    eax, eax
0x1800328ea  js      short loc_1800328FF
0x1800328ec  mov     rcx, [rsp+78h+arg_28]
0x1800328f4  test    rcx, rcx
0x1800328f7  jz      short loc_1800328FF
0x1800328f9  mov     eax, [rsp+78h+pProtectionType]
0x1800328fd  mov     [rcx], eax
0x1800328ff  test    r14b, r14b
0x180032902  jz      short loc_18003290A
0x180032904  call    cs:__imp_RevertToSelf
0x18003290a  test    rbp, rbp
0x18003290d  jz      short loc_180032935
0x18003290f  cmp     rbp, rsi
0x180032912  jz      short loc_180032935
0x180032914  mov     ecx, r15d
0x180032917  mov     rax, rbp
0x18003291a  test    r15d, r15d
0x18003291d  jz      short loc_18003292D
0x18003291f  nop
0x180032920  mov     byte ptr [rax], 0
0x180032923  lea     rax, [rax+1]
0x180032927  sub     rcx, 1
0x18003292b  jnz     short loc_180032920
0x18003292d  mov     rcx, rbp
0x180032930  call    KerbFree
0x180032935  mov     r14, [rsp+78h+arg_8]
0x18003293d  mov     rdi, [rsp+78h+arg_0]
0x180032945  mov     eax, ebx
0x180032947  mov     rbx, [rsp+78h+arg_10]
0x18003294f  add     rsp, 50h
0x180032953  pop     r15
0x180032955  pop     r13
0x180032957  pop     r12
0x180032959  pop     rsi
0x18003295a  pop     rbp
0x18003295b  retn
```
