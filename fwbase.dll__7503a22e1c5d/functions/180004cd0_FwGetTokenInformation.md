# FwGetTokenInformation

- ea: `0x180004cd0`
- end: `0x180004ded`
- name: `FwGetTokenInformation`
- size: `285`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x180004cd0`
- `0x18001e1d0`
- `0x18002f43c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004daa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004d14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004d51`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004d14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004d51`

## string_xrefs

- `0x180004db3`: `FwGetTokenInformation`
- `0x180004dd2`: `FwGetTokenInformation`
- `0x180004d8c`: `GetTokenInformation`
- `0x180004da3`: `GetTokenInformation`

## pseudocode

```c
__int64 __fastcall FwGetTokenInformation(
        HANDLE TokenHandle,
        TOKEN_INFORMATION_CLASS TokenInformationClass,
        _QWORD *a3,
        DWORD *a4)
{
  DWORD LastError; // eax
  __int64 v9; // rdx
  void *v10; // rdi
  unsigned int v11; // ebx
  const char *v13; // rbx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-38h] BYREF

  *a3 = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenInformationClass, 0, 0, &TokenInformationLength) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LastError = GetLastError();
  if ( LastError != 122 && LastError )
  {
    v10 = 0;
    v13 = "GetTokenInformation";
    goto LABEL_13;
  }
  v10 = (void *)FwAlloc(TokenInformationLength, v9);
  if ( !v10 )
  {
    v13 = "FwAlloc";
    LastError = 8;
    goto LABEL_13;
  }
  if ( !GetTokenInformation(TokenHandle, TokenInformationClass, v10, TokenInformationLength, &TokenInformationLength) )
  {
    v13 = "GetTokenInformation";
    LastError = GetLastError();
LABEL_13:
    v11 = FwReportErrorAsWinError("FwGetTokenInformation", v13, LastError);
    if ( (v11 & 0x80000000) != 0 )
    {
      FwFree(v10);
      return (unsigned int)FwReportReturnError("FwGetTokenInformation", v11);
    }
    return v11;
  }
  v11 = 0;
  *a3 = v10;
  if ( a4 )
    *a4 = TokenInformationLength;
  return v11;
}

```

## disassembly

```asm
0x180004cd0  push    rbx
0x180004cd2  push    rbp
0x180004cd3  push    rsi
0x180004cd4  push    rdi
0x180004cd5  push    r14
0x180004cd7  sub     rsp, 40h
0x180004cdb  mov     rax, cs:__security_cookie
0x180004ce2  xor     rax, rsp
0x180004ce5  mov     [rsp+68h+var_30], rax
0x180004cea  mov     rsi, r9
0x180004ced  mov     qword ptr [r8], 0
0x180004cf4  mov     r14, r8
0x180004cf7  mov     [rsp+68h+TokenInformationLength], 0
0x180004cff  lea     rax, [rsp+68h+TokenInformationLength]
0x180004d04  xor     r9d, r9d; TokenInformationLength
0x180004d07  xor     r8d, r8d; TokenInformation
0x180004d0a  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180004d0f  mov     ebp, edx
0x180004d11  mov     rbx, rcx
0x180004d14  call    cs:__imp_GetTokenInformation
0x180004d1a  test    eax, eax
0x180004d1c  jnz     short loc_180004D7F
0x180004d1e  call    cs:__imp_GetLastError
0x180004d24  cmp     eax, 7Ah ; 'z'
0x180004d27  jnz     short loc_180004D86
0x180004d29  mov     ecx, [rsp+68h+TokenInformationLength]
0x180004d2d  call    FwAlloc
0x180004d32  mov     rdi, rax
0x180004d35  test    rax, rax
0x180004d38  jz      short loc_180004D95
0x180004d3a  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x180004d3f  lea     rax, [rsp+68h+TokenInformationLength]
0x180004d44  mov     r8, rdi; TokenInformation
0x180004d47  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180004d4c  mov     edx, ebp; TokenInformationClass
0x180004d4e  mov     rcx, rbx; TokenHandle
0x180004d51  call    cs:__imp_GetTokenInformation
0x180004d57  test    eax, eax
0x180004d59  jz      short loc_180004DA3
0x180004d5b  xor     ebx, ebx
0x180004d5d  mov     [r14], rdi
0x180004d60  test    rsi, rsi
0x180004d63  jnz     short loc_180004DE2
0x180004d65  mov     eax, ebx
0x180004d67  mov     rcx, [rsp+68h+var_30]
0x180004d6c  xor     rcx, rsp; StackCookie
0x180004d6f  call    __security_check_cookie
0x180004d74  add     rsp, 40h
0x180004d78  pop     r14
0x180004d7a  pop     rdi
0x180004d7b  pop     rsi
0x180004d7c  pop     rbp
0x180004d7d  pop     rbx
0x180004d7e  retn
0x180004d7f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!success")
0x180004d84  jmp     short loc_180004D1E
0x180004d86  test    eax, eax
0x180004d88  jz      short loc_180004D29
0x180004d8a  xor     edi, edi
0x180004d8c  lea     rbx, aGettokeninform; "GetTokenInformation"
0x180004d93  jmp     short loc_180004DB0
0x180004d95  lea     rbx, aFwalloc_0; "FwAlloc"
0x180004d9c  mov     eax, 8
0x180004da1  jmp     short loc_180004DB0
0x180004da3  lea     rbx, aGettokeninform; "GetTokenInformation"
0x180004daa  call    cs:__imp_GetLastError
0x180004db0  mov     r8d, eax
0x180004db3  lea     rcx, aFwgettokeninfo_0; "FwGetTokenInformation"
0x180004dba  mov     rdx, rbx
0x180004dbd  call    FwReportErrorAsWinError
0x180004dc2  mov     ebx, eax
0x180004dc4  test    eax, eax
0x180004dc6  jns     short loc_180004D65
0x180004dc8  mov     rcx, rdi
0x180004dcb  call    FwFree
0x180004dd0  mov     edx, ebx
0x180004dd2  lea     rcx, aFwgettokeninfo_0; "FwGetTokenInformation"
0x180004dd9  call    FwReportReturnError
0x180004dde  mov     ebx, eax
0x180004de0  jmp     short loc_180004D65
0x180004de2  mov     eax, [rsp+68h+TokenInformationLength]
0x180004de6  mov     [rsi], eax
0x180004de8  jmp     loc_180004D65
```
