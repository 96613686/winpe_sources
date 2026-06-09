# GetUserTextualSidHKCU

- ea: `0x18003381c`
- end: `0x180033a0b`
- name: `GetUserTextualSidHKCU`
- size: `495`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800334f8`
- `0x1800336b8`
- `0x1800c8058`

## callees

- `0x18003381c`
- `0x180033a14`
- `0x180033a4c`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003387a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003387a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033943`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033943`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800338f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800339e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800338f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800339e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033870`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033870`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003389b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003389b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033855`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033855`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003388b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003388b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003393b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003393b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800338cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800339b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800338cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800339b4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003390d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003390d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800338e9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800338e9`

## pseudocode

```c
__int64 __fastcall GetUserTextualSidHKCU(STRSAFE_LPWSTR pszDest)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v4; // r15
  unsigned int TextualSidHKCU; // esi
  PSID *v6; // rbx
  PSID *v7; // r14
  DWORD LengthSid; // r15d
  HLOCAL v9; // rax
  void *v10; // rdi
  void *v11; // r14
  DWORD LastError; // ebx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE TokenInformation[256]; // [rsp+40h] [rbp-C0h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return 0;
  }
  v4 = TokenHandle;
  TokenInformationLength = 256;
  TextualSidHKCU = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, &TokenInformationLength);
  if ( TextualSidHKCU )
  {
    v6 = 0;
    v7 = (PSID *)TokenInformation;
LABEL_6:
    TextualSidHKCU = 0;
    LengthSid = GetLengthSid(*v7);
    v9 = LocalAlloc(0, LengthSid);
    v10 = v9;
    if ( v9 )
    {
      TextualSidHKCU = CopySid(LengthSid, v9, *v7);
      if ( !TextualSidHKCU )
      {
        freeWithSavedLastError(v10);
        v10 = 0;
      }
    }
    if ( !v6 )
      goto LABEL_10;
    goto LABEL_19;
  }
  v10 = 0;
  if ( GetLastError() != 122 )
    goto LABEL_10;
  v6 = (PSID *)LocalAlloc(0, TokenInformationLength);
  if ( !v6 )
    goto LABEL_10;
  v7 = v6;
  TextualSidHKCU = GetTokenInformation(v4, TokenUser, v6, TokenInformationLength, &TokenInformationLength);
  if ( TextualSidHKCU )
    goto LABEL_6;
LABEL_19:
  freeWithSavedLastError(v6);
LABEL_10:
  v11 = TokenHandle;
  if ( TokenHandle )
  {
    LastError = GetLastError();
    CloseHandle(v11);
    SetLastError(LastError);
  }
  if ( TextualSidHKCU )
    TextualSidHKCU = GetTextualSidHKCU(v10, pszDest);
  if ( v10 )
    freeWithSavedLastError(v10);
  return TextualSidHKCU;
}

```

## disassembly

```asm
0x18003381c  mov     [rsp-8+arg_10], rbx
0x180033821  push    rbp
0x180033822  push    rsi
0x180033823  push    rdi
0x180033824  push    r12
0x180033826  push    r13
0x180033828  push    r14
0x18003382a  push    r15
0x18003382c  lea     rbp, [rsp-50h]
0x180033831  sub     rsp, 150h
0x180033838  mov     rax, cs:__security_cookie
0x18003383f  xor     rax, rsp
0x180033842  mov     [rbp+80h+var_40], rax
0x180033846  mov     r13, rdx
0x180033849  mov     [rsp+180h+TokenHandle], 0
0x180033852  mov     r12, rcx
0x180033855  call    cs:__imp_GetCurrentThread
0x18003385b  mov     edi, 1
0x180033860  lea     r9, [rsp+180h+TokenHandle]; TokenHandle
0x180033865  mov     rcx, rax; ThreadHandle
0x180033868  mov     r8d, edi; OpenAsSelf
0x18003386b  lea     ebx, [rdi+7]
0x18003386e  mov     edx, ebx; DesiredAccess
0x180033870  call    cs:__imp_OpenThreadToken
0x180033876  test    eax, eax
0x180033878  jnz     short loc_1800338A9
0x18003387a  call    cs:__imp_GetLastError
0x180033880  cmp     eax, 3F0h
0x180033885  jnz     loc_180033993
0x18003388b  call    cs:__imp_GetCurrentProcess
0x180033891  lea     r8, [rsp+180h+TokenHandle]; TokenHandle
0x180033896  mov     edx, ebx; DesiredAccess
0x180033898  mov     rcx, rax; ProcessHandle
0x18003389b  call    cs:__imp_OpenProcessToken
0x1800338a1  test    eax, eax
0x1800338a3  jz      loc_180033993
0x1800338a9  mov     r15, [rsp+180h+TokenHandle]
0x1800338ae  lea     rax, [rsp+180h+TokenInformationLength]
0x1800338b3  mov     r9d, 100h; TokenInformationLength
0x1800338b9  mov     [rsp+180h+ReturnLength], rax; ReturnLength
0x1800338be  mov     rcx, r15; TokenHandle
0x1800338c1  mov     [rsp+180h+TokenInformationLength], r9d
0x1800338c6  lea     r8, [rsp+180h+TokenInformation]; TokenInformation
0x1800338cb  mov     edx, edi; TokenInformationClass
0x1800338cd  call    cs:__imp_GetTokenInformation
0x1800338d3  mov     esi, eax
0x1800338d5  test    eax, eax
0x1800338d7  jz      loc_1800339D1
0x1800338dd  xor     ebx, ebx
0x1800338df  lea     r14, [rsp+180h+TokenInformation]
0x1800338e4  mov     rcx, [r14]; pSid
0x1800338e7  xor     esi, esi
0x1800338e9  call    cs:__imp_GetLengthSid
0x1800338ef  mov     edx, eax; uBytes
0x1800338f1  xor     ecx, ecx; uFlags
0x1800338f3  mov     r15d, eax
0x1800338f6  call    cs:__imp_LocalAlloc
0x1800338fc  mov     rdi, rax
0x1800338ff  test    rax, rax
0x180033902  jz      short loc_18003391D
0x180033904  mov     r8, [r14]; pSourceSid
0x180033907  mov     rdx, rax; pDestinationSid
0x18003390a  mov     ecx, r15d; nDestinationSidLength
0x18003390d  call    cs:__imp_CopySid
0x180033913  mov     esi, eax
0x180033915  test    eax, eax
0x180033917  jz      loc_1800339FC
0x18003391d  test    rbx, rbx
0x180033920  jnz     loc_1800339C4
0x180033926  mov     r14, [rsp+180h+TokenHandle]
0x18003392b  test    r14, r14
0x18003392e  jz      short loc_180033949
0x180033930  call    cs:__imp_GetLastError
0x180033936  mov     rcx, r14; hObject
0x180033939  mov     ebx, eax
0x18003393b  call    cs:__imp_CloseHandle
0x180033941  mov     ecx, ebx; dwErrCode
0x180033943  call    cs:__imp_SetLastError
0x180033949  test    esi, esi
0x18003394b  jz      short loc_18003395D
0x18003394d  mov     r8, r13
0x180033950  mov     rdx, r12; pszDest
0x180033953  mov     rcx, rdi; pSid
0x180033956  call    GetTextualSidHKCU
0x18003395b  mov     esi, eax
0x18003395d  test    rdi, rdi
0x180033960  jz      short loc_18003396A
0x180033962  mov     rcx, rdi; hMem
0x180033965  call    freeWithSavedLastError
0x18003396a  mov     eax, esi
0x18003396c  mov     rcx, [rbp+80h+var_40]
0x180033970  xor     rcx, rsp; StackCookie
0x180033973  call    __security_check_cookie
0x180033978  mov     rbx, [rsp+180h+arg_10]
0x180033980  add     rsp, 150h
0x180033987  pop     r15
0x180033989  pop     r14
0x18003398b  pop     r13
0x18003398d  pop     r12
0x18003398f  pop     rdi
0x180033990  pop     rsi
0x180033991  pop     rbp
0x180033992  retn
0x180033993  xor     eax, eax
0x180033995  jmp     short loc_18003396C
0x180033997  mov     r9d, [rsp+180h+TokenInformationLength]; TokenInformationLength
0x18003399c  lea     rax, [rsp+180h+TokenInformationLength]
0x1800339a1  mov     r8, rbx; TokenInformation
0x1800339a4  mov     [rsp+180h+ReturnLength], rax; ReturnLength
0x1800339a9  mov     edx, 1; TokenInformationClass
0x1800339ae  mov     rcx, r15; TokenHandle
0x1800339b1  mov     r14, rbx
0x1800339b4  call    cs:__imp_GetTokenInformation
0x1800339ba  mov     esi, eax
0x1800339bc  test    eax, eax
0x1800339be  jnz     loc_1800338E4
0x1800339c4  mov     rcx, rbx; hMem
0x1800339c7  call    freeWithSavedLastError
0x1800339cc  jmp     loc_180033926
0x1800339d1  xor     edi, edi
0x1800339d3  call    cs:__imp_GetLastError
0x1800339d9  cmp     eax, 7Ah ; 'z'
0x1800339dc  jnz     loc_180033926
0x1800339e2  mov     edx, [rsp+180h+TokenInformationLength]; uBytes
0x1800339e6  xor     ecx, ecx; uFlags
0x1800339e8  call    cs:__imp_LocalAlloc
0x1800339ee  mov     rbx, rax
0x1800339f1  test    rax, rax
0x1800339f4  jz      loc_180033926
0x1800339fa  jmp     short loc_180033997
0x1800339fc  mov     rcx, rdi; hMem
0x1800339ff  call    freeWithSavedLastError
0x180033a04  xor     edi, edi
0x180033a06  jmp     loc_18003391D
```
