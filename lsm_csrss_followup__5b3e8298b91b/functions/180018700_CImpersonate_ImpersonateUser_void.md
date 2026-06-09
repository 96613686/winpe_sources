# CImpersonate::ImpersonateUser(void *)

- ea: `0x180018700`
- end: `0x1800189ce`
- name: `?ImpersonateUser@CImpersonate@@QEAAJPEAX@Z`
- size: `718`
- prototype: `int(CImpersonate *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018288`

## callees

- `0x1800074c0`
- `0x180018700`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18001885a`
- `ntdll!RtlEqualSid` at `0x18001885a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001886d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001886d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018938`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018742`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018742`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001887f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001887f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800187a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001881e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800187a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001881e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001888d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001889b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001888d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001889b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001877b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001884a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001877b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001884a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800188fc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800188fc`

## string_xrefs

- `0x1800188c0`: `CheckCurrentContext: FAILED to get token infomration for input token, Error %x`
- `0x1800189ac`: `CImpersonate::ImpersonateUser`
- `0x180018962`: `CheckCurrentContext: FAILED to get size infomration for input token, Error %x`
- `0x18001897b`: `CheckCurrentContext: FAILED to get size infomration for current token, Error %x`
- `0x180018991`: `TERMSRV: CheckCurrentContext - Different user is being impersonated`

## pseudocode

```c
int __fastcall CImpersonate::ImpersonateUser(CImpersonate *this, void *a2)
{
  PSID *v3; // rdi
  PSID *v4; // rsi
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  DWORD v8; // eax
  DWORD v9; // ebx
  DWORD v10; // eax
  DWORD v11; // ebx
  bool v12; // sf
  int result; // eax
  int v14; // edi
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+20h] BYREF

  TokenHandle = 0;
  v3 = 0;
  TokenInformationLength = 0;
  v4 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    goto LABEL_14;
  }
  LastError = 1375;
  if ( !a2 )
    goto LABEL_14;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v8 = GetLastError();
    LastError = v8;
    if ( v8 != 122 )
    {
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for input token, Error %x", v8);
      goto LABEL_14;
    }
  }
  v9 = TokenInformationLength;
  v3 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  if ( !v3 )
    goto LABEL_31;
  if ( !GetTokenInformation(a2, TokenUser, v3, v9, &TokenInformationLength) )
  {
LABEL_25:
    LastError = GetLastError();
    _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get token infomration for input token, Error %x", LastError);
    goto LABEL_14;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v10 = GetLastError();
    LastError = v10;
    if ( v10 != 122 )
    {
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for current token, Error %x", v10);
      goto LABEL_14;
    }
  }
  v11 = TokenInformationLength;
  v4 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  if ( !v4 )
  {
LABEL_31:
    LastError = 8;
    _DbgPrintMessage(8, "CheckCurrentContext: FAILED to allocate memory");
    goto LABEL_14;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v4, v11, &TokenInformationLength) )
    goto LABEL_25;
  if ( RtlEqualSid(*v3, *v4) )
  {
    LastError = 0;
  }
  else
  {
    _DbgPrintMessage(4, "TERMSRV: CheckCurrentContext - Different user is being impersonated");
    LastError = 1375;
  }
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v3 )
    LocalFree(v3);
  if ( v4 )
    LocalFree(v4);
  v12 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = LastError < 0;
  }
  if ( !v12 )
    return LastError;
  v14 = 0;
  if ( LastError != -2147023888 )
    v14 = LastError;
  if ( v14 < 0 )
  {
    _DbgPrintMessage(8, "CheckCurrentContext failed: 0x%x in %s", v14, "CImpersonate::ImpersonateUser");
    return v14;
  }
  else if ( ImpersonateLoggedOnUser(a2) )
  {
    *(_WORD *)this = 1;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180018700  mov     [rsp+arg_0], rbx
0x180018705  push    rbp
0x180018706  push    rsi
0x180018707  push    rdi
0x180018708  push    r14
0x18001870a  push    r15
0x18001870c  sub     rsp, 30h
0x180018710  xor     r15d, r15d
0x180018713  mov     rbp, rdx
0x180018716  mov     [rsp+58h+TokenHandle], r15
0x18001871b  mov     edi, r15d
0x18001871e  mov     [rsp+58h+TokenInformationLength], r15d
0x180018723  mov     esi, r15d
0x180018726  mov     r14, rcx
0x180018729  call    cs:__imp_GetCurrentThread
0x18001872f  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180018734  mov     edx, 0Eh; DesiredAccess
0x180018739  mov     rcx, rax; ThreadHandle
0x18001873c  mov     r8d, 1; OpenAsSelf
0x180018742  call    cs:__imp_OpenThreadToken
0x180018748  test    eax, eax
0x18001874a  jz      loc_18001886D
0x180018750  mov     ebx, 55Fh
0x180018755  test    rbp, rbp
0x180018758  jz      loc_180018875
0x18001875e  lea     rax, [rsp+58h+TokenInformationLength]
0x180018763  mov     [rsp+58h+TokenInformationLength], r15d
0x180018768  xor     r9d, r9d; TokenInformationLength
0x18001876b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180018770  xor     r8d, r8d; TokenInformation
0x180018773  mov     edx, 1; TokenInformationClass
0x180018778  mov     rcx, rbp; TokenHandle
0x18001877b  call    cs:__imp_GetTokenInformation
0x180018781  test    eax, eax
0x180018783  jnz     short loc_180018796
0x180018785  call    cs:__imp_GetLastError
0x18001878b  mov     ebx, eax
0x18001878d  cmp     eax, 7Ah ; 'z'
0x180018790  jnz     loc_18001895F
0x180018796  mov     ebx, [rsp+58h+TokenInformationLength]
0x18001879a  mov     ecx, 40h ; '@'; uFlags
0x18001879f  mov     edx, ebx; uBytes
0x1800187a1  call    cs:__imp_LocalAlloc
0x1800187a7  mov     rdi, rax
0x1800187aa  test    rax, rax
0x1800187ad  jz      loc_180018920
0x1800187b3  lea     rax, [rsp+58h+TokenInformationLength]
0x1800187b8  mov     r9d, ebx; TokenInformationLength
0x1800187bb  mov     r8, rdi; TokenInformation
0x1800187be  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800187c3  mov     edx, 1; TokenInformationClass
0x1800187c8  mov     rcx, rbp; TokenHandle
0x1800187cb  call    cs:__imp_GetTokenInformation
0x1800187d1  test    eax, eax
0x1800187d3  jz      loc_1800188BA
0x1800187d9  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800187de  lea     rax, [rsp+58h+TokenInformationLength]
0x1800187e3  xor     r9d, r9d; TokenInformationLength
0x1800187e6  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800187eb  xor     r8d, r8d; TokenInformation
0x1800187ee  mov     [rsp+58h+TokenInformationLength], r15d
0x1800187f3  mov     edx, 1; TokenInformationClass
0x1800187f8  call    cs:__imp_GetTokenInformation
0x1800187fe  test    eax, eax
0x180018800  jnz     short loc_180018813
0x180018802  call    cs:__imp_GetLastError
0x180018808  mov     ebx, eax
0x18001880a  cmp     eax, 7Ah ; 'z'
0x18001880d  jnz     loc_180018978
0x180018813  mov     ebx, [rsp+58h+TokenInformationLength]
0x180018817  mov     ecx, 40h ; '@'; uFlags
0x18001881c  mov     edx, ebx; uBytes
0x18001881e  call    cs:__imp_LocalAlloc
0x180018824  mov     rsi, rax
0x180018827  test    rax, rax
0x18001882a  jz      loc_180018920
0x180018830  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180018835  lea     rax, [rsp+58h+TokenInformationLength]
0x18001883a  mov     r9d, ebx; TokenInformationLength
0x18001883d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180018842  mov     r8, rsi; TokenInformation
0x180018845  mov     edx, 1; TokenInformationClass
0x18001884a  call    cs:__imp_GetTokenInformation
0x180018850  test    eax, eax
0x180018852  jz      short loc_1800188BA
0x180018854  mov     rdx, [rsi]; Sid2
0x180018857  mov     rcx, [rdi]; Sid1
0x18001885a  call    cs:__imp_RtlEqualSid
0x180018860  test    al, al
0x180018862  jz      loc_180018991
0x180018868  mov     ebx, r15d
0x18001886b  jmp     short loc_180018875
0x18001886d  call    cs:__imp_GetLastError
0x180018873  mov     ebx, eax
0x180018875  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18001887a  test    rcx, rcx
0x18001887d  jz      short loc_180018885
0x18001887f  call    cs:__imp_CloseHandle
0x180018885  test    rdi, rdi
0x180018888  jz      short loc_180018893
0x18001888a  mov     rcx, rdi; hMem
0x18001888d  call    cs:__imp_LocalFree
0x180018893  test    rsi, rsi
0x180018896  jz      short loc_1800188A1
0x180018898  mov     rcx, rsi; hMem
0x18001889b  call    cs:__imp_LocalFree
0x1800188a1  test    ebx, ebx
0x1800188a3  jg      short loc_1800188D8
0x1800188a5  js      short loc_1800188E5
0x1800188a7  mov     eax, ebx
0x1800188a9  mov     rbx, [rsp+58h+arg_0]
0x1800188ae  add     rsp, 30h
0x1800188b2  pop     r15
0x1800188b4  pop     r14
0x1800188b6  pop     rdi
0x1800188b7  pop     rsi
0x1800188b8  pop     rbp
0x1800188b9  retn
0x1800188ba  call    cs:__imp_GetLastError
0x1800188c0  lea     rdx, aCheckcurrentco; "CheckCurrentContext: FAILED to get toke"...
0x1800188c7  mov     ecx, 8; int
0x1800188cc  mov     r8d, eax
0x1800188cf  mov     ebx, eax
0x1800188d1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800188d6  jmp     short loc_180018875
0x1800188d8  movzx   ebx, bx
0x1800188db  or      ebx, 80070000h
0x1800188e1  test    ebx, ebx
0x1800188e3  jmp     short loc_1800188A5
0x1800188e5  cmp     ebx, 800703F0h
0x1800188eb  mov     edi, r15d
0x1800188ee  cmovnz  edi, ebx
0x1800188f1  test    edi, edi
0x1800188f3  js      loc_1800189AC
0x1800188f9  mov     rcx, rbp; hToken
0x1800188fc  call    cs:__imp_ImpersonateLoggedOnUser
0x180018902  test    eax, eax
0x180018904  jz      short loc_180018938
0x180018906  mov     word ptr [r14], 1
0x18001890c  mov     eax, r15d
0x18001890f  mov     rbx, [rsp+58h+arg_0]
0x180018914  add     rsp, 30h
0x180018918  pop     r15
0x18001891a  pop     r14
0x18001891c  pop     rdi
0x18001891d  pop     rsi
0x18001891e  pop     rbp
0x18001891f  retn
0x180018920  mov     ebx, 8
0x180018925  lea     rdx, aCheckcurrentco_3; "CheckCurrentContext: FAILED to allocate"...
0x18001892c  mov     ecx, ebx; int
0x18001892e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018933  jmp     loc_180018875
0x180018938  call    cs:__imp_GetLastError
0x18001893e  test    eax, eax
0x180018940  jle     loc_1800188A9
0x180018946  mov     rbx, [rsp+58h+arg_0]
0x18001894b  movzx   eax, ax
0x18001894e  or      eax, 80070000h
0x180018953  add     rsp, 30h
0x180018957  pop     r15
0x180018959  pop     r14
0x18001895b  pop     rdi
0x18001895c  pop     rsi
0x18001895d  pop     rbp
0x18001895e  retn
0x18001895f  mov     r8d, eax
0x180018962  lea     rdx, aCheckcurrentco_0; "CheckCurrentContext: FAILED to get size"...
0x180018969  mov     ecx, 8; int
0x18001896e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018973  jmp     loc_180018875
0x180018978  mov     r8d, eax
0x18001897b  lea     rdx, aCheckcurrentco_1; "CheckCurrentContext: FAILED to get size"...
0x180018982  mov     ecx, 8; int
0x180018987  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001898c  jmp     loc_180018875
0x180018991  lea     rdx, aTermsrvCheckcu; "TERMSRV: CheckCurrentContext - Differen"...
0x180018998  mov     ecx, 4; int
0x18001899d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800189a2  mov     ebx, 55Fh
0x1800189a7  jmp     loc_180018875
0x1800189ac  lea     r9, aCimpersonateIm; "CImpersonate::ImpersonateUser"
0x1800189b3  mov     r8d, edi
0x1800189b6  lea     rdx, aCheckcurrentco_2; "CheckCurrentContext failed: 0x%x in %s"
0x1800189bd  mov     ecx, 8; int
0x1800189c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800189c7  mov     eax, edi
0x1800189c9  jmp     loc_1800188A9
```
