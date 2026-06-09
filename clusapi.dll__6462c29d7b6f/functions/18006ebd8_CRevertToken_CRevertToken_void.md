# CRevertToken::CRevertToken(void)

- ea: `0x18006ebd8`
- end: `0x18006ed19`
- name: `??0CRevertToken@@QEAA@XZ`
- size: `321`
- prototype: `CRevertToken *__fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003db80`
- `0x1800465e0`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18003180c`
- `0x18006ebd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ec71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ec9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ecc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ec71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ec9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ecc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ec01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ec01`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ec14`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ec14`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006ec67`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006ec67`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006ec4e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006ec4e`

## string_xrefs

- `0x18006eca4`: `Failed to get information about current thread token.`
- `0x18006ecf4`: `Failed to get current thread token.`

## pseudocode

```c
void **__fastcall CRevertToken::CRevertToken(void **TokenHandle)
{
  HANDLE CurrentThread; // rax
  void *v3; // rcx
  bool v4; // al
  DWORD v5; // eax
  DWORD LastError; // eax
  DWORD v7; // eax
  int TokenInformation; // [rsp+30h] [rbp-138h] BYREF
  DWORD ReturnLength[3]; // [rsp+34h] [rbp-134h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+40h] [rbp-128h] BYREF

  *TokenHandle = 0;
  *((_BYTE *)TokenHandle + 8) = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 0, TokenHandle) )
  {
    v3 = *TokenHandle;
    TokenInformation = 0;
    ReturnLength[0] = 0;
    if ( !GetTokenInformation(v3, TokenType, &TokenInformation, 4u, ReturnLength) )
    {
      LastError = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        LastError,
        L"Failed to get information about current thread token.");
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    v4 = TokenInformation == 2;
    *((_BYTE *)TokenHandle + 8) = TokenInformation == 2;
    if ( v4 && !RevertToSelf() )
    {
      v5 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)pExceptionObject, v5, L"Failed to revert to self.");
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
  }
  else
  {
    v7 = GetLastError();
    if ( v7 != 1008 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        v7,
        L"Failed to get current thread token.");
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    *((_BYTE *)TokenHandle + 8) = 0;
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x18006ebd8  push    rbx
0x18006ebda  sub     rsp, 160h
0x18006ebe1  mov     rax, cs:__security_cookie
0x18006ebe8  xor     rax, rsp
0x18006ebeb  mov     [rsp+168h+var_18], rax
0x18006ebf3  mov     rbx, rcx
0x18006ebf6  mov     qword ptr [rcx], 0
0x18006ebfd  mov     byte ptr [rcx+8], 0
0x18006ec01  call    cs:__imp_GetCurrentThread
0x18006ec07  xor     r8d, r8d; OpenAsSelf
0x18006ec0a  mov     r9, rbx; TokenHandle
0x18006ec0d  mov     rcx, rax; ThreadHandle
0x18006ec10  lea     edx, [r8+0Ch]; DesiredAccess
0x18006ec14  call    cs:__imp_OpenThreadToken
0x18006ec1a  test    eax, eax
0x18006ec1c  jz      loc_18006ECC7
0x18006ec22  mov     rcx, [rbx]; TokenHandle
0x18006ec25  lea     rax, [rsp+168h+var_134]
0x18006ec2a  mov     r9d, 4; TokenInformationLength
0x18006ec30  mov     [rsp+168h+TokenInformation], 0
0x18006ec38  lea     r8, [rsp+168h+TokenInformation]; TokenInformation
0x18006ec3d  mov     [rsp+168h+var_134], 0
0x18006ec45  mov     [rsp+168h+ReturnLength], rax; ReturnLength
0x18006ec4a  lea     edx, [r9+4]; TokenInformationClass
0x18006ec4e  call    cs:__imp_GetTokenInformation
0x18006ec54  test    eax, eax
0x18006ec56  jz      short loc_18006EC9C
0x18006ec58  cmp     [rsp+168h+TokenInformation], 2
0x18006ec5d  setz    al
0x18006ec60  mov     [rbx+8], al
0x18006ec63  test    al, al
0x18006ec65  jz      short loc_18006ECD8
0x18006ec67  call    cs:__imp_RevertToSelf
0x18006ec6d  test    eax, eax
0x18006ec6f  jnz     short loc_18006ECD8
0x18006ec71  call    cs:__imp_GetLastError
0x18006ec77  mov     edx, eax; int
0x18006ec79  lea     r8, aFailedToRevert; "Failed to revert to self."
0x18006ec80  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18006ec85  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18006ec8a  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18006ec91  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18006ec96  call    _CxxThrowException_0
0x18006ec9c  call    cs:__imp_GetLastError
0x18006eca2  mov     edx, eax; int
0x18006eca4  lea     r8, aFailedToGetInf; "Failed to get information about current"...
0x18006ecab  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18006ecb0  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18006ecb5  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18006ecbc  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18006ecc1  call    _CxxThrowException_0
0x18006ecc7  call    cs:__imp_GetLastError
0x18006eccd  cmp     eax, 3F0h
0x18006ecd2  jnz     short loc_18006ECF4
0x18006ecd4  mov     byte ptr [rbx+8], 0
0x18006ecd8  mov     rax, rbx
0x18006ecdb  mov     rcx, [rsp+168h+var_18]
0x18006ece3  xor     rcx, rsp; StackCookie
0x18006ece6  call    __security_check_cookie
0x18006eceb  add     rsp, 160h
0x18006ecf2  pop     rbx
0x18006ecf3  retn
0x18006ecf4  lea     r8, aFailedToGetCur; "Failed to get current thread token."
0x18006ecfb  mov     edx, eax; int
0x18006ecfd  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18006ed02  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18006ed07  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18006ed0e  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18006ed13  call    _CxxThrowException_0
```
