# CImpersonate::CheckCurrentContext(void *)

- ea: `0x180008cb0`
- end: `0x180008efb`
- name: `?CheckCurrentContext@CImpersonate@@AEAAJPEAX@Z`
- size: `587`
- prototype: `int(CImpersonate *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180031400`

## callees

- `0x1800074c0`
- `0x180008cb0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180008e0e`
- `ntdll!RtlEqualSid` at `0x180008e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e6e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008cf6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008cf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008cdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008cdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008dd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008dd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008d2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008d7f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008dac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008dfe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008d2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008d7f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008dac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008dfe`

## string_xrefs

- `0x180008e74`: `CheckCurrentContext: FAILED to get token infomration for input token, Error %x`
- `0x180008eb1`: `CheckCurrentContext: FAILED to get size infomration for input token, Error %x`
- `0x180008eca`: `CheckCurrentContext: FAILED to get size infomration for current token, Error %x`
- `0x180008ee0`: `TERMSRV: CheckCurrentContext - Different user is being impersonated`

## pseudocode

```c
__int64 __fastcall CImpersonate::CheckCurrentContext(CImpersonate *this, void *a2)
{
  PSID *v3; // rsi
  PSID *v4; // rdi
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  DWORD v7; // eax
  DWORD v8; // ebx
  DWORD v9; // eax
  DWORD v10; // ebx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+54h] [rbp+Ch]
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  v13 = HIDWORD(this);
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
    v7 = GetLastError();
    LastError = v7;
    if ( v7 != 122 )
    {
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for input token, Error %x", v7);
      goto LABEL_14;
    }
  }
  v8 = TokenInformationLength;
  v3 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  if ( !v3 )
    goto LABEL_24;
  if ( !GetTokenInformation(a2, TokenUser, v3, v8, &TokenInformationLength) )
  {
LABEL_22:
    LastError = GetLastError();
    _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get token infomration for input token, Error %x", LastError);
    goto LABEL_14;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v9 = GetLastError();
    LastError = v9;
    if ( v9 != 122 )
    {
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for current token, Error %x", v9);
      goto LABEL_14;
    }
  }
  v10 = TokenInformationLength;
  v4 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  if ( !v4 )
  {
LABEL_24:
    LastError = 8;
    _DbgPrintMessage(8, "CheckCurrentContext: FAILED to allocate memory");
    goto LABEL_14;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v4, v10, &TokenInformationLength) )
    goto LABEL_22;
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
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  else
    return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180008cb0  mov     [rsp+arg_8], rbx
0x180008cb5  mov     [rsp+arg_18], rbp
0x180008cba  mov     qword ptr [rsp+TokenInformationLength], rcx
0x180008cbf  push    rsi
0x180008cc0  push    rdi
0x180008cc1  push    r14
0x180008cc3  sub     rsp, 30h
0x180008cc7  xor     r14d, r14d
0x180008cca  mov     rbp, rdx
0x180008ccd  mov     [rsp+48h+TokenHandle], r14
0x180008cd2  mov     esi, r14d
0x180008cd5  mov     [rsp+48h+TokenInformationLength], r14d
0x180008cda  mov     edi, r14d
0x180008cdd  call    cs:__imp_GetCurrentThread
0x180008ce3  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180008ce8  mov     edx, 0Eh; DesiredAccess
0x180008ced  mov     rcx, rax; ThreadHandle
0x180008cf0  mov     r8d, 1; OpenAsSelf
0x180008cf6  call    cs:__imp_OpenThreadToken
0x180008cfc  test    eax, eax
0x180008cfe  jz      loc_180008E21
0x180008d04  mov     ebx, 55Fh
0x180008d09  test    rbp, rbp
0x180008d0c  jz      loc_180008E29
0x180008d12  lea     rax, [rsp+48h+TokenInformationLength]
0x180008d17  mov     [rsp+48h+TokenInformationLength], r14d
0x180008d1c  xor     r9d, r9d; TokenInformationLength
0x180008d1f  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008d24  xor     r8d, r8d; TokenInformation
0x180008d27  mov     edx, 1; TokenInformationClass
0x180008d2c  mov     rcx, rbp; TokenHandle
0x180008d2f  call    cs:__imp_GetTokenInformation
0x180008d35  test    eax, eax
0x180008d37  jnz     short loc_180008D4A
0x180008d39  call    cs:__imp_GetLastError
0x180008d3f  mov     ebx, eax
0x180008d41  cmp     eax, 7Ah ; 'z'
0x180008d44  jnz     loc_180008EAE
0x180008d4a  mov     ebx, [rsp+48h+TokenInformationLength]
0x180008d4e  mov     ecx, 40h ; '@'; uFlags
0x180008d53  mov     edx, ebx; uBytes
0x180008d55  call    cs:__imp_LocalAlloc
0x180008d5b  mov     rsi, rax
0x180008d5e  test    rax, rax
0x180008d61  jz      loc_180008E96
0x180008d67  lea     rax, [rsp+48h+TokenInformationLength]
0x180008d6c  mov     r9d, ebx; TokenInformationLength
0x180008d6f  mov     r8, rsi; TokenInformation
0x180008d72  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008d77  mov     edx, 1; TokenInformationClass
0x180008d7c  mov     rcx, rbp; TokenHandle
0x180008d7f  call    cs:__imp_GetTokenInformation
0x180008d85  test    eax, eax
0x180008d87  jz      loc_180008E6E
0x180008d8d  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180008d92  lea     rax, [rsp+48h+TokenInformationLength]
0x180008d97  xor     r9d, r9d; TokenInformationLength
0x180008d9a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008d9f  xor     r8d, r8d; TokenInformation
0x180008da2  mov     [rsp+48h+TokenInformationLength], r14d
0x180008da7  mov     edx, 1; TokenInformationClass
0x180008dac  call    cs:__imp_GetTokenInformation
0x180008db2  test    eax, eax
0x180008db4  jnz     short loc_180008DC7
0x180008db6  call    cs:__imp_GetLastError
0x180008dbc  mov     ebx, eax
0x180008dbe  cmp     eax, 7Ah ; 'z'
0x180008dc1  jnz     loc_180008EC7
0x180008dc7  mov     ebx, [rsp+48h+TokenInformationLength]
0x180008dcb  mov     ecx, 40h ; '@'; uFlags
0x180008dd0  mov     edx, ebx; uBytes
0x180008dd2  call    cs:__imp_LocalAlloc
0x180008dd8  mov     rdi, rax
0x180008ddb  test    rax, rax
0x180008dde  jz      loc_180008E96
0x180008de4  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180008de9  lea     rax, [rsp+48h+TokenInformationLength]
0x180008dee  mov     r9d, ebx; TokenInformationLength
0x180008df1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008df6  mov     r8, rdi; TokenInformation
0x180008df9  mov     edx, 1; TokenInformationClass
0x180008dfe  call    cs:__imp_GetTokenInformation
0x180008e04  test    eax, eax
0x180008e06  jz      short loc_180008E6E
0x180008e08  mov     rdx, [rdi]; Sid2
0x180008e0b  mov     rcx, [rsi]; Sid1
0x180008e0e  call    cs:__imp_RtlEqualSid
0x180008e14  test    al, al
0x180008e16  jz      loc_180008EE0
0x180008e1c  mov     ebx, r14d
0x180008e1f  jmp     short loc_180008E29
0x180008e21  call    cs:__imp_GetLastError
0x180008e27  mov     ebx, eax
0x180008e29  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180008e2e  test    rcx, rcx
0x180008e31  jz      short loc_180008E39
0x180008e33  call    cs:__imp_CloseHandle
0x180008e39  test    rsi, rsi
0x180008e3c  jz      short loc_180008E47
0x180008e3e  mov     rcx, rsi; hMem
0x180008e41  call    cs:__imp_LocalFree
0x180008e47  test    rdi, rdi
0x180008e4a  jz      short loc_180008E55
0x180008e4c  mov     rcx, rdi; hMem
0x180008e4f  call    cs:__imp_LocalFree
0x180008e55  test    ebx, ebx
0x180008e57  jg      short loc_180008E8C
0x180008e59  mov     eax, ebx
0x180008e5b  mov     rbx, [rsp+48h+arg_8]
0x180008e60  mov     rbp, [rsp+48h+arg_18]
0x180008e65  add     rsp, 30h
0x180008e69  pop     r14
0x180008e6b  pop     rdi
0x180008e6c  pop     rsi
0x180008e6d  retn
0x180008e6e  call    cs:__imp_GetLastError
0x180008e74  lea     rdx, aCheckcurrentco; "CheckCurrentContext: FAILED to get toke"...
0x180008e7b  mov     ecx, 8; int
0x180008e80  mov     r8d, eax
0x180008e83  mov     ebx, eax
0x180008e85  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008e8a  jmp     short loc_180008E29
0x180008e8c  movzx   eax, bx
0x180008e8f  or      eax, 80070000h
0x180008e94  jmp     short loc_180008E5B
0x180008e96  mov     ebx, 8
0x180008e9b  lea     rdx, aCheckcurrentco_3; "CheckCurrentContext: FAILED to allocate"...
0x180008ea2  mov     ecx, ebx; int
0x180008ea4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008ea9  jmp     loc_180008E29
0x180008eae  mov     r8d, eax
0x180008eb1  lea     rdx, aCheckcurrentco_0; "CheckCurrentContext: FAILED to get size"...
0x180008eb8  mov     ecx, 8; int
0x180008ebd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008ec2  jmp     loc_180008E29
0x180008ec7  mov     r8d, eax
0x180008eca  lea     rdx, aCheckcurrentco_1; "CheckCurrentContext: FAILED to get size"...
0x180008ed1  mov     ecx, 8; int
0x180008ed6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008edb  jmp     loc_180008E29
0x180008ee0  lea     rdx, aTermsrvCheckcu; "TERMSRV: CheckCurrentContext - Differen"...
0x180008ee7  mov     ecx, 4; int
0x180008eec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008ef1  mov     ebx, 55Fh
0x180008ef6  jmp     loc_180008E29
```
