# CImpersonate::ImpersonateUser(void *)

- ea: `0x18000c720`
- end: `0x18000ca61`
- name: `?ImpersonateUser@CImpersonate@@QEAAJPEAX@Z`
- size: `833`
- prototype: `int(CImpersonate *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c208`

## callees

- `0x1800077a0`
- `0x18000c720`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000c8ba`
- `ntdll!RtlEqualSid` at `0x18000c8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c84c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c84c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c768`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c749`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c7d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c86e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c7d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c86e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c913`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c7a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c809`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c83c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c8a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c7a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c809`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c83c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c8a0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000c981`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000c981`

## string_xrefs

- `0x18000c945`: `CheckCurrentContext: FAILED to get token infomration for input token, Error %x`
- `0x18000ca3f`: `CImpersonate::ImpersonateUser`
- `0x18000c9f5`: `CheckCurrentContext: FAILED to get size infomration for input token, Error %x`
- `0x18000ca24`: `TERMSRV: CheckCurrentContext - Different user is being impersonated`
- `0x18000ca0e`: `CheckCurrentContext: FAILED to get size infomration for current token, Error %x`

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
0x18000c720  mov     [rsp+arg_0], rbx
0x18000c725  push    rbp
0x18000c726  push    rsi
0x18000c727  push    rdi
0x18000c728  push    r14
0x18000c72a  push    r15
0x18000c72c  sub     rsp, 30h
0x18000c730  xor     r15d, r15d
0x18000c733  mov     rbp, rdx
0x18000c736  mov     [rsp+58h+TokenHandle], r15
0x18000c73b  mov     edi, r15d
0x18000c73e  mov     [rsp+58h+TokenInformationLength], r15d
0x18000c743  mov     esi, r15d
0x18000c746  mov     r14, rcx
0x18000c749  call    cs:__imp_GetCurrentThread
0x18000c750  nop     dword ptr [rax+rax+00h]
0x18000c755  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18000c75a  mov     edx, 0Eh; DesiredAccess
0x18000c75f  mov     rcx, rax; ThreadHandle
0x18000c762  mov     r8d, 1; OpenAsSelf
0x18000c768  call    cs:__imp_OpenThreadToken
0x18000c76f  nop     dword ptr [rax+rax+00h]
0x18000c774  test    eax, eax
0x18000c776  jz      loc_18000C8D3
0x18000c77c  mov     ebx, 55Fh
0x18000c781  test    rbp, rbp
0x18000c784  jz      loc_18000C8E1
0x18000c78a  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c78f  mov     [rsp+58h+TokenInformationLength], r15d
0x18000c794  xor     r9d, r9d; TokenInformationLength
0x18000c797  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c79c  xor     r8d, r8d; TokenInformation
0x18000c79f  mov     edx, 1; TokenInformationClass
0x18000c7a4  mov     rcx, rbp; TokenHandle
0x18000c7a7  call    cs:__imp_GetTokenInformation
0x18000c7ae  nop     dword ptr [rax+rax+00h]
0x18000c7b3  test    eax, eax
0x18000c7b5  jnz     short loc_18000C7CE
0x18000c7b7  call    cs:__imp_GetLastError
0x18000c7be  nop     dword ptr [rax+rax+00h]
0x18000c7c3  mov     ebx, eax
0x18000c7c5  cmp     eax, 7Ah ; 'z'
0x18000c7c8  jnz     loc_18000C9F2
0x18000c7ce  mov     ebx, [rsp+58h+TokenInformationLength]
0x18000c7d2  mov     ecx, 40h ; '@'; uFlags
0x18000c7d7  mov     edx, ebx; uBytes
0x18000c7d9  call    cs:__imp_LocalAlloc
0x18000c7e0  nop     dword ptr [rax+rax+00h]
0x18000c7e5  mov     rdi, rax
0x18000c7e8  test    rax, rax
0x18000c7eb  jz      loc_18000C9AC
0x18000c7f1  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c7f6  mov     r9d, ebx; TokenInformationLength
0x18000c7f9  mov     r8, rdi; TokenInformation
0x18000c7fc  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c801  mov     edx, 1; TokenInformationClass
0x18000c806  mov     rcx, rbp; TokenHandle
0x18000c809  call    cs:__imp_GetTokenInformation
0x18000c810  nop     dword ptr [rax+rax+00h]
0x18000c815  test    eax, eax
0x18000c817  jz      loc_18000C939
0x18000c81d  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000c822  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c827  xor     r9d, r9d; TokenInformationLength
0x18000c82a  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c82f  xor     r8d, r8d; TokenInformation
0x18000c832  mov     [rsp+58h+TokenInformationLength], r15d
0x18000c837  mov     edx, 1; TokenInformationClass
0x18000c83c  call    cs:__imp_GetTokenInformation
0x18000c843  nop     dword ptr [rax+rax+00h]
0x18000c848  test    eax, eax
0x18000c84a  jnz     short loc_18000C863
0x18000c84c  call    cs:__imp_GetLastError
0x18000c853  nop     dword ptr [rax+rax+00h]
0x18000c858  mov     ebx, eax
0x18000c85a  cmp     eax, 7Ah ; 'z'
0x18000c85d  jnz     loc_18000CA0B
0x18000c863  mov     ebx, [rsp+58h+TokenInformationLength]
0x18000c867  mov     ecx, 40h ; '@'; uFlags
0x18000c86c  mov     edx, ebx; uBytes
0x18000c86e  call    cs:__imp_LocalAlloc
0x18000c875  nop     dword ptr [rax+rax+00h]
0x18000c87a  mov     rsi, rax
0x18000c87d  test    rax, rax
0x18000c880  jz      loc_18000C9AC
0x18000c886  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000c88b  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c890  mov     r9d, ebx; TokenInformationLength
0x18000c893  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c898  mov     r8, rsi; TokenInformation
0x18000c89b  mov     edx, 1; TokenInformationClass
0x18000c8a0  call    cs:__imp_GetTokenInformation
0x18000c8a7  nop     dword ptr [rax+rax+00h]
0x18000c8ac  test    eax, eax
0x18000c8ae  jz      loc_18000C939
0x18000c8b4  mov     rdx, [rsi]; Sid2
0x18000c8b7  mov     rcx, [rdi]; Sid1
0x18000c8ba  call    cs:__imp_RtlEqualSid
0x18000c8c1  nop     dword ptr [rax+rax+00h]
0x18000c8c6  test    al, al
0x18000c8c8  jz      loc_18000CA24
0x18000c8ce  mov     ebx, r15d
0x18000c8d1  jmp     short loc_18000C8E1
0x18000c8d3  call    cs:__imp_GetLastError
0x18000c8da  nop     dword ptr [rax+rax+00h]
0x18000c8df  mov     ebx, eax
0x18000c8e1  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000c8e6  test    rcx, rcx
0x18000c8e9  jz      short loc_18000C8F7
0x18000c8eb  call    cs:__imp_CloseHandle
0x18000c8f2  nop     dword ptr [rax+rax+00h]
0x18000c8f7  test    rdi, rdi
0x18000c8fa  jz      short loc_18000C90B
0x18000c8fc  mov     rcx, rdi; hMem
0x18000c8ff  call    cs:__imp_LocalFree
0x18000c906  nop     dword ptr [rax+rax+00h]
0x18000c90b  test    rsi, rsi
0x18000c90e  jz      short loc_18000C91F
0x18000c910  mov     rcx, rsi; hMem
0x18000c913  call    cs:__imp_LocalFree
0x18000c91a  nop     dword ptr [rax+rax+00h]
0x18000c91f  test    ebx, ebx
0x18000c921  jg      short loc_18000C95D
0x18000c923  js      short loc_18000C96A
0x18000c925  mov     eax, ebx
0x18000c927  mov     rbx, [rsp+58h+arg_0]
0x18000c92c  add     rsp, 30h
0x18000c930  pop     r15
0x18000c932  pop     r14
0x18000c934  pop     rdi
0x18000c935  pop     rsi
0x18000c936  pop     rbp
0x18000c937  retn
0x18000c939  call    cs:__imp_GetLastError
0x18000c940  nop     dword ptr [rax+rax+00h]
0x18000c945  lea     rdx, aCheckcurrentco; "CheckCurrentContext: FAILED to get toke"...
0x18000c94c  mov     ecx, 8; int
0x18000c951  mov     r8d, eax
0x18000c954  mov     ebx, eax
0x18000c956  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c95b  jmp     short loc_18000C8E1
0x18000c95d  movzx   ebx, bx
0x18000c960  or      ebx, 80070000h
0x18000c966  test    ebx, ebx
0x18000c968  jmp     short loc_18000C923
0x18000c96a  cmp     ebx, 800703F0h
0x18000c970  mov     edi, r15d
0x18000c973  cmovnz  edi, ebx
0x18000c976  test    edi, edi
0x18000c978  js      loc_18000CA3F
0x18000c97e  mov     rcx, rbp; hToken
0x18000c981  call    cs:__imp_ImpersonateLoggedOnUser
0x18000c988  nop     dword ptr [rax+rax+00h]
0x18000c98d  test    eax, eax
0x18000c98f  jz      short loc_18000C9C4
0x18000c991  mov     word ptr [r14], 1
0x18000c997  mov     eax, r15d
0x18000c99a  mov     rbx, [rsp+58h+arg_0]
0x18000c99f  add     rsp, 30h
0x18000c9a3  pop     r15
0x18000c9a5  pop     r14
0x18000c9a7  pop     rdi
0x18000c9a8  pop     rsi
0x18000c9a9  pop     rbp
0x18000c9aa  retn
0x18000c9ac  mov     ebx, 8
0x18000c9b1  lea     rdx, aCheckcurrentco_3; "CheckCurrentContext: FAILED to allocate"...
0x18000c9b8  mov     ecx, ebx; int
0x18000c9ba  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c9bf  jmp     loc_18000C8E1
0x18000c9c4  call    cs:__imp_GetLastError
0x18000c9cb  nop     dword ptr [rax+rax+00h]
0x18000c9d0  test    eax, eax
0x18000c9d2  jle     loc_18000C927
0x18000c9d8  mov     rbx, [rsp+58h+arg_0]
0x18000c9dd  movzx   eax, ax
0x18000c9e0  or      eax, 80070000h
0x18000c9e5  add     rsp, 30h
0x18000c9e9  pop     r15
0x18000c9eb  pop     r14
0x18000c9ed  pop     rdi
0x18000c9ee  pop     rsi
0x18000c9ef  pop     rbp
0x18000c9f0  retn
0x18000c9f2  mov     r8d, eax
0x18000c9f5  lea     rdx, aCheckcurrentco_0; "CheckCurrentContext: FAILED to get size"...
0x18000c9fc  mov     ecx, 8; int
0x18000ca01  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ca06  jmp     loc_18000C8E1
0x18000ca0b  mov     r8d, eax
0x18000ca0e  lea     rdx, aCheckcurrentco_1; "CheckCurrentContext: FAILED to get size"...
0x18000ca15  mov     ecx, 8; int
0x18000ca1a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ca1f  jmp     loc_18000C8E1
0x18000ca24  lea     rdx, aTermsrvCheckcu; "TERMSRV: CheckCurrentContext - Differen"...
0x18000ca2b  mov     ecx, 4; int
0x18000ca30  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ca35  mov     ebx, 55Fh
0x18000ca3a  jmp     loc_18000C8E1
0x18000ca3f  lea     r9, aCimpersonateIm; "CImpersonate::ImpersonateUser"
0x18000ca46  mov     r8d, edi
0x18000ca49  lea     rdx, aCheckcurrentco_2; "CheckCurrentContext failed: 0x%x in %s"
0x18000ca50  mov     ecx, 8; int
0x18000ca55  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ca5a  mov     eax, edi
0x18000ca5c  jmp     loc_18000C927
```
