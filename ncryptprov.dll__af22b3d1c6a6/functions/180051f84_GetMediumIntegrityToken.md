# GetMediumIntegrityToken

- ea: `0x180051f84`
- end: `0x1800522fc`
- name: `GetMediumIntegrityToken`
- size: `888`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180051e8c`

## callees

- `0x18000af80`
- `0x180038970`
- `0x180051f84`
- `0x180062310`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x1800521be`
- `ntdll!NtDuplicateToken` at `0x1800521be`
- `ntdll!NtQueryInformationToken` at `0x180052023`
- `ntdll!NtQueryInformationToken` at `0x1800520a3`
- `ntdll!NtQueryInformationToken` at `0x180052023`
- `ntdll!NtQueryInformationToken` at `0x1800520a3`
- `ntdll!RtlFreeSid` at `0x180052297`
- `ntdll!RtlFreeSid` at `0x180052297`
- `ntdll!RtlSidDominates` at `0x180052123`
- `ntdll!RtlSidDominates` at `0x180052123`
- `ntdll!NtSetInformationToken` at `0x1800521f9`
- `ntdll!NtSetInformationToken` at `0x1800521f9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800520f4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800520f4`
- `ntdll!NtSetInformationThread` at `0x180052163`
- `ntdll!NtSetInformationThread` at `0x180052223`
- `ntdll!NtSetInformationThread` at `0x180052260`
- `ntdll!NtSetInformationThread` at `0x180052163`
- `ntdll!NtSetInformationThread` at `0x180052223`
- `ntdll!NtSetInformationThread` at `0x180052260`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800522ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800522ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052069`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800522ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800522ad`

## string_xrefs

- `0x180052046`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180052239`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall GetMediumIntegrityToken(HANDLE TokenHandle, void **a2)
{
  __int64 *v4; // rdi
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  NTSTATUS v9; // eax
  __int64 v10; // r9
  _BYTE v12[4]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG TokenInformationLength; // [rsp+64h] [rbp-9Ch] BYREF
  void *NewTokenHandle; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandlea; // [rsp+78h] [rbp-88h] BYREF
  __int64 ThreadInformation; // [rsp+80h] [rbp-80h] BYREF
  __int128 v18; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE TokenInformation[128]; // [rsp+D0h] [rbp-30h] BYREF

  TokenHandlea = TokenHandle;
  NewTokenHandle = 0;
  ThreadInformation = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  TokenInformationLength = 128;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  Sid = 0;
  *a2 = 0;
  v18 = 0;
  v4 = (__int64 *)TokenInformation;
  v5 = NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x80u, &TokenInformationLength);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -1073741789 )
    {
      v7 = 1263;
LABEL_4:
      DebugTraceError((unsigned int)v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", v7);
      goto LABEL_26;
    }
    v4 = (__int64 *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v4 )
    {
      v6 = -1073741670;
      goto LABEL_26;
    }
    v5 = NtQueryInformationToken(TokenHandlea, TokenIntegrityLevel, v4, TokenInformationLength, &TokenInformationLength);
    v6 = v5;
    if ( v5 )
    {
      v7 = 1288;
      goto LABEL_4;
    }
  }
  v5 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x2000u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  v6 = v5;
  if ( v5 )
  {
    v7 = 1306;
    goto LABEL_4;
  }
  v8 = *v4;
  v12[0] = 0;
  v5 = RtlSidDominates(v8, Sid, v12);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1328;
    goto LABEL_4;
  }
  if ( v12[0] )
    goto LABEL_25;
  v5 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1351;
    goto LABEL_4;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtDuplicateToken(TokenHandlea, 0x8Eu, &ObjectAttributes, 0, TokenImpersonation, &NewTokenHandle);
  if ( v9 < 0 )
  {
    v10 = 1376;
    goto LABEL_22;
  }
  *(_QWORD *)&v18 = Sid;
  DWORD2(v18) = 96;
  v9 = NtSetInformationToken(NewTokenHandle, TokenIntegrityLevel, &v18, 0x10u);
  if ( v9 < 0 )
  {
    v10 = 1395;
    goto LABEL_22;
  }
  v9 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &NewTokenHandle, 8u);
  if ( !v9 )
  {
    *a2 = NewTokenHandle;
    NewTokenHandle = 0;
LABEL_25:
    v6 = 0;
    goto LABEL_26;
  }
  v10 = 1411;
LABEL_22:
  DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", v10);
  v5 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandlea, 8u);
  v6 = v5;
  if ( v5 )
  {
    v7 = 1434;
    goto LABEL_4;
  }
LABEL_26:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( NewTokenHandle )
    CloseHandle(NewTokenHandle);
  if ( v4 && v4 != (__int64 *)TokenInformation )
    LocalFree(v4);
  return v6;
}

```

## disassembly

```asm
0x180051f84  mov     [rsp-8+arg_10], rbx
0x180051f89  push    rbp
0x180051f8a  push    rsi
0x180051f8b  push    rdi
0x180051f8c  push    r13
0x180051f8e  push    r15
0x180051f90  lea     rbp, [rsp-60h]
0x180051f95  sub     rsp, 160h
0x180051f9c  mov     rax, cs:__security_cookie
0x180051fa3  xor     rax, rsp
0x180051fa6  mov     [rbp+80h+var_30], rax
0x180051faa  xorps   xmm0, xmm0
0x180051fad  mov     [rsp+180h+TokenHandle], rcx
0x180051fb2  mov     rsi, rdx
0x180051fb5  mov     rbx, rcx
0x180051fb8  xor     r15d, r15d
0x180051fbb  lea     rcx, [rbp+80h+TokenInformation]; void *
0x180051fbf  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x180051fc3  xor     eax, eax
0x180051fc5  mov     [rsp+180h+NewTokenHandle], r15
0x180051fca  xor     edx, edx; Val
0x180051fcc  mov     [rbp+80h+ThreadInformation], r15
0x180051fd0  mov     r8d, 80h; Size
0x180051fd6  movups  xmmword ptr [rbp+80h+ObjectAttributes+1Ch], xmm0
0x180051fda  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x180051fde  call    memset_0
0x180051fe3  xorps   xmm0, xmm0
0x180051fe6  mov     [rsp+180h+TokenInformationLength], 80h
0x180051fee  lea     rax, [rsp+180h+TokenInformationLength]
0x180051ff3  mov     dword ptr [rbp+80h+IdentifierAuthority.Value], r15d
0x180051ff7  mov     r9d, 80h; TokenInformationLength
0x180051ffd  mov     [rsp+180h+ReturnLength], rax; ReturnLength
0x180052002  lea     r8, [rbp+80h+TokenInformation]; TokenInformation
0x180052006  mov     word ptr [rbp+80h+IdentifierAuthority.Value+4], 1000h
0x18005200c  lea     edx, [r15+19h]; TokenInformationClass
0x180052010  mov     [rsp+180h+var_110], r15
0x180052015  mov     rcx, rbx; TokenHandle
0x180052018  mov     [rsi], r15
0x18005201b  movups  [rbp+80h+var_F8], xmm0
0x18005201f  lea     rdi, [rbp+80h+TokenInformation]
0x180052023  call    cs:__imp_NtQueryInformationToken
0x18005202a  nop     dword ptr [rax+rax+00h]
0x18005202f  mov     ebx, eax
0x180052031  test    eax, eax
0x180052033  jns     loc_1800520BD
0x180052039  cmp     eax, 0C0000023h
0x18005203e  jz      short loc_180052060
0x180052040  mov     r9d, 4EFh
0x180052046  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005204d  mov     ecx, eax
0x18005204f  lea     rdx, aStatus; "Status"
0x180052056  call    DebugTraceError
0x18005205b  jmp     loc_18005228D
0x180052060  mov     edx, [rsp+180h+TokenInformationLength]; uBytes
0x180052064  mov     ecx, 40h ; '@'; uFlags
0x180052069  call    cs:__imp_LocalAlloc
0x180052070  nop     dword ptr [rax+rax+00h]
0x180052075  mov     rdi, rax
0x180052078  test    rax, rax
0x18005207b  jnz     short loc_180052087
0x18005207d  mov     ebx, 0C000009Ah
0x180052082  jmp     loc_18005228D
0x180052087  mov     r9d, [rsp+180h+TokenInformationLength]; TokenInformationLength
0x18005208c  lea     rax, [rsp+180h+TokenInformationLength]
0x180052091  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x180052096  mov     r8, rdi; TokenInformation
0x180052099  mov     edx, 19h; TokenInformationClass
0x18005209e  mov     [rsp+180h+ReturnLength], rax; ReturnLength
0x1800520a3  call    cs:__imp_NtQueryInformationToken
0x1800520aa  nop     dword ptr [rax+rax+00h]
0x1800520af  mov     ebx, eax
0x1800520b1  test    eax, eax
0x1800520b3  jz      short loc_1800520BD
0x1800520b5  mov     r9d, 508h
0x1800520bb  jmp     short loc_180052046
0x1800520bd  lea     rax, [rsp+180h+var_110]
0x1800520c2  xor     r9d, r9d; SubAuthority1
0x1800520c5  mov     [rsp+180h+Sid], rax; Sid
0x1800520ca  lea     rcx, [rbp+80h+IdentifierAuthority]; IdentifierAuthority
0x1800520ce  mov     [rsp+180h+SubAuthority7], r15d; SubAuthority7
0x1800520d3  mov     r8d, 2000h; SubAuthority0
0x1800520d9  mov     [rsp+180h+SubAuthority6], r15d; SubAuthority6
0x1800520de  mov     dl, 1; SubAuthorityCount
0x1800520e0  mov     [rsp+180h+SubAuthority5], r15d; SubAuthority5
0x1800520e5  mov     [rsp+180h+SubAuthority4], r15d; SubAuthority4
0x1800520ea  mov     [rsp+180h+SubAuthority3], r15d; SubAuthority3
0x1800520ef  mov     dword ptr [rsp+180h+ReturnLength], r15d; SubAuthority2
0x1800520f4  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800520fb  nop     dword ptr [rax+rax+00h]
0x180052100  mov     ebx, eax
0x180052102  test    eax, eax
0x180052104  jz      short loc_180052111
0x180052106  mov     r9d, 51Ah
0x18005210c  jmp     loc_180052046
0x180052111  mov     rdx, [rsp+180h+var_110]
0x180052116  lea     r8, [rsp+180h+var_120]
0x18005211b  mov     rcx, [rdi]
0x18005211e  mov     [rsp+180h+var_120], r15b
0x180052123  call    cs:__imp_RtlSidDominates
0x18005212a  nop     dword ptr [rax+rax+00h]
0x18005212f  mov     ebx, eax
0x180052131  test    eax, eax
0x180052133  jns     short loc_180052140
0x180052135  mov     r9d, 530h
0x18005213b  jmp     loc_180052046
0x180052140  cmp     [rsp+180h+var_120], r15b
0x180052145  jnz     loc_18005228A
0x18005214b  mov     r9d, 8; ThreadInformationLength
0x180052151  lea     r8, [rbp+80h+ThreadInformation]; ThreadInformation
0x180052155  mov     r13, 0FFFFFFFFFFFFFFFEh
0x18005215c  mov     rcx, r13; ThreadHandle
0x18005215f  lea     edx, [r9-3]; ThreadInformationClass
0x180052163  call    cs:__imp_NtSetInformationThread
0x18005216a  nop     dword ptr [rax+rax+00h]
0x18005216f  mov     ebx, eax
0x180052171  test    eax, eax
0x180052173  jns     short loc_180052180
0x180052175  mov     r9d, 547h
0x18005217b  jmp     loc_180052046
0x180052180  mov     rcx, [rsp+180h+TokenHandle]; ExistingTokenHandle
0x180052185  lea     rax, [rsp+180h+NewTokenHandle]
0x18005218a  xorps   xmm0, xmm0
0x18005218d  mov     qword ptr [rsp+180h+SubAuthority3], rax; NewTokenHandle
0x180052192  xor     r9d, r9d; EffectiveOnly
0x180052195  mov     dword ptr [rsp+180h+ReturnLength], 2; TokenType
0x18005219d  lea     r8, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x1800521a1  mov     [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x1800521a8  mov     edx, 8Eh; DesiredAccess
0x1800521ad  mov     [rbp+80h+ObjectAttributes.RootDirectory], r15
0x1800521b1  mov     [rbp+80h+ObjectAttributes.Attributes], r15d
0x1800521b5  mov     [rbp+80h+ObjectAttributes.ObjectName], r15
0x1800521b9  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800521be  call    cs:__imp_NtDuplicateToken
0x1800521c5  nop     dword ptr [rax+rax+00h]
0x1800521ca  test    eax, eax
0x1800521cc  jns     short loc_1800521D6
0x1800521ce  mov     r9d, 560h
0x1800521d4  jmp     short loc_180052239
0x1800521d6  mov     rax, [rsp+180h+var_110]
0x1800521db  lea     r8, [rbp+80h+var_F8]; TokenInformation
0x1800521df  mov     rcx, [rsp+180h+NewTokenHandle]; TokenHandle
0x1800521e4  mov     r9d, 10h; TokenInformationLength
0x1800521ea  mov     qword ptr [rbp+80h+var_F8], rax
0x1800521ee  mov     dword ptr [rbp+80h+var_F8+8], 60h ; '`'
0x1800521f5  lea     edx, [r9+9]; TokenInformationClass
0x1800521f9  call    cs:__imp_NtSetInformationToken
0x180052200  nop     dword ptr [rax+rax+00h]
0x180052205  test    eax, eax
0x180052207  jns     short loc_180052211
0x180052209  mov     r9d, 573h
0x18005220f  jmp     short loc_180052239
0x180052211  mov     r9d, 8; ThreadInformationLength
0x180052217  lea     r8, [rsp+180h+NewTokenHandle]; ThreadInformation
0x18005221c  mov     rcx, r13; ThreadHandle
0x18005221f  lea     edx, [r9-3]; ThreadInformationClass
0x180052223  call    cs:__imp_NtSetInformationThread
0x18005222a  nop     dword ptr [rax+rax+00h]
0x18005222f  test    eax, eax
0x180052231  jz      short loc_18005227D
0x180052233  mov     r9d, 583h
0x180052239  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052240  mov     ecx, eax
0x180052242  lea     rdx, aStatus; "Status"
0x180052249  call    DebugTraceError
0x18005224e  mov     r9d, 8; ThreadInformationLength
0x180052254  lea     r8, [rsp+180h+TokenHandle]; ThreadInformation
0x180052259  mov     rcx, r13; ThreadHandle
0x18005225c  lea     edx, [r9-3]; ThreadInformationClass
0x180052260  call    cs:__imp_NtSetInformationThread
0x180052267  nop     dword ptr [rax+rax+00h]
0x18005226c  mov     ebx, eax
0x18005226e  test    eax, eax
0x180052270  jz      short loc_18005228D
0x180052272  mov     r9d, 59Ah
0x180052278  jmp     loc_180052046
0x18005227d  mov     rax, [rsp+180h+NewTokenHandle]
0x180052282  mov     [rsi], rax
0x180052285  mov     [rsp+180h+NewTokenHandle], r15
0x18005228a  mov     ebx, r15d
0x18005228d  mov     rcx, [rsp+180h+var_110]; Sid
0x180052292  test    rcx, rcx
0x180052295  jz      short loc_1800522A3
0x180052297  call    cs:__imp_RtlFreeSid
0x18005229e  nop     dword ptr [rax+rax+00h]
0x1800522a3  mov     rcx, [rsp+180h+NewTokenHandle]; hObject
0x1800522a8  test    rcx, rcx
0x1800522ab  jz      short loc_1800522B9
0x1800522ad  call    cs:__imp_CloseHandle
0x1800522b4  nop     dword ptr [rax+rax+00h]
0x1800522b9  test    rdi, rdi
0x1800522bc  jz      short loc_1800522D6
0x1800522be  lea     rax, [rbp+80h+TokenInformation]
0x1800522c2  cmp     rdi, rax
0x1800522c5  jz      short loc_1800522D6
0x1800522c7  mov     rcx, rdi; hMem
0x1800522ca  call    cs:__imp_LocalFree
0x1800522d1  nop     dword ptr [rax+rax+00h]
0x1800522d6  mov     eax, ebx
0x1800522d8  mov     rcx, [rbp+80h+var_30]
0x1800522dc  xor     rcx, rsp; StackCookie
0x1800522df  call    __security_check_cookie
0x1800522e4  mov     rbx, [rsp+180h+arg_10]
0x1800522ec  add     rsp, 160h
0x1800522f3  pop     r15
0x1800522f5  pop     r13
0x1800522f7  pop     rdi
0x1800522f8  pop     rsi
0x1800522f9  pop     rbp
0x1800522fa  retn
```
