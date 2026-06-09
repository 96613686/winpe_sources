# IkeGetPrimaryGroupFromToken

- ea: `0x18007f158`
- end: `0x18007f2e0`
- name: `IkeGetPrimaryGroupFromToken`
- size: `392`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800025cc`
- `0x1800ed920`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x18004cad0`
- `0x180050850`
- `0x18007f158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f1c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f1c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f257`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007f1bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007f20e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007f1bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007f20e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007f249`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007f249`

## string_xrefs

- `0x18007f21e`: `GetTokenInformation`
- `0x18007f25d`: `ConvertSidToStringSidW`
- `0x18007f18b`: `IkeGetPrimaryGroupFromToken`
- `0x18007f1d2`: `IkeGetPrimaryGroupFromToken`
- `0x18007f298`: `IkeGetPrimaryGroupFromToken`
- `0x18007f2a4`: `IkeGetPrimaryGroupFromToken`

## pseudocode

```c
__int64 __fastcall IkeGetPrimaryGroupFromToken(HANDLE TokenHandle, LPWSTR **a2, _DWORD *a3)
{
  LPWSTR *v3; // rdi
  DWORD LastError; // eax
  __int64 v8; // rcx
  const char *v9; // rdx
  __int64 v10; // rbx
  LPVOID TokenInformation; // [rsp+30h] [rbp-20h]
  LPWSTR *StringSid; // [rsp+38h] [rbp-18h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp-10h] BYREF

  v3 = 0;
  StringSid = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  TraceLogHelper("IkeGetPrimaryGroupFromToken", 1);
  if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      v9 = "IkeGetPrimaryGroupFromToken";
      goto LABEL_10;
    }
  }
  v10 = WfpMemAlloc(TokenInformationLength, 0);
  if ( !v10 )
  {
    if ( !GetTokenInformation(
            TokenHandle,
            TokenPrimaryGroup,
            TokenInformation,
            TokenInformationLength,
            &TokenInformationLength) )
    {
      LastError = GetLastError();
      v9 = "GetTokenInformation";
      goto LABEL_10;
    }
    v3 = StringSid;
    v10 = WfpMemAlloc(8u, 8u);
    if ( !v10 )
    {
      if ( ConvertSidToStringSidW(*(PSID *)TokenInformation, StringSid) )
      {
        *a2 = StringSid;
        *a3 = 1;
        goto LABEL_13;
      }
      LastError = GetLastError();
      v9 = "ConvertSidToStringSidW";
LABEL_10:
      v10 = WfpReportSysErrorAsWinError(v8, v9, LastError, 1);
      if ( !v10 )
        goto LABEL_13;
    }
  }
  if ( *v3 )
    IkeFreeGroupArray(v3, 1);
LABEL_13:
  TraceLogHelper("IkeGetPrimaryGroupFromToken", 0);
  return IkeReturnError(v10, "IkeGetPrimaryGroupFromToken");
}

```

## disassembly

```asm
0x18007f158  mov     [rsp-38h+arg_18], rbx
0x18007f15d  push    rbp
0x18007f15e  push    rsi
0x18007f15f  push    rdi
0x18007f160  push    r12
0x18007f162  push    r13
0x18007f164  push    r14
0x18007f166  push    r15
0x18007f168  mov     rbp, rsp
0x18007f16b  sub     rsp, 50h
0x18007f16f  mov     rax, cs:__security_cookie
0x18007f176  xor     rax, rsp
0x18007f179  mov     [rbp+var_8], rax
0x18007f17d  xor     edi, edi
0x18007f17f  mov     r15, rdx
0x18007f182  mov     r14, rcx
0x18007f185  mov     [rbp+StringSid], rdi
0x18007f189  xor     esi, esi
0x18007f18b  lea     rcx, aIkegetprimaryg; "IkeGetPrimaryGroupFromToken"
0x18007f192  mov     r12, r8
0x18007f195  mov     [rbp+TokenInformation], rsi
0x18007f199  lea     r13d, [rdi+1]
0x18007f19d  mov     [rbp+TokenInformationLength], esi
0x18007f1a0  mov     edx, r13d
0x18007f1a3  call    TraceLogHelper
0x18007f1a8  lea     rax, [rbp+TokenInformationLength]
0x18007f1ac  xor     r9d, r9d; TokenInformationLength
0x18007f1af  xor     r8d, r8d; TokenInformation
0x18007f1b2  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18007f1b7  lea     edx, [rdi+5]; TokenInformationClass
0x18007f1ba  mov     rcx, r14; TokenHandle
0x18007f1bd  call    cs:__imp_GetTokenInformation
0x18007f1c3  test    eax, eax
0x18007f1c5  jnz     short loc_18007F1DE
0x18007f1c7  call    cs:__imp_GetLastError
0x18007f1cd  cmp     eax, 7Ah ; 'z'
0x18007f1d0  jz      short loc_18007F1DE
0x18007f1d2  lea     rdx, aIkegetprimaryg; "IkeGetPrimaryGroupFromToken"
0x18007f1d9  jmp     loc_18007F264
0x18007f1de  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x18007f1e1  lea     r8, [rbp+TokenInformation]
0x18007f1e5  xor     edx, edx; dwFlags
0x18007f1e7  call    WfpMemAlloc
0x18007f1ec  mov     rsi, [rbp+TokenInformation]
0x18007f1f0  mov     rbx, rax
0x18007f1f3  test    rax, rax
0x18007f1f6  jnz     short loc_18007F277
0x18007f1f8  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18007f1fc  lea     rax, [rbp+TokenInformationLength]
0x18007f200  mov     r8, rsi; TokenInformation
0x18007f203  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18007f208  lea     edx, [rbx+5]; TokenInformationClass
0x18007f20b  mov     rcx, r14; TokenHandle
0x18007f20e  call    cs:__imp_GetTokenInformation
0x18007f214  test    eax, eax
0x18007f216  jnz     short loc_18007F227
0x18007f218  call    cs:__imp_GetLastError
0x18007f21e  lea     rdx, aGettokeninform; "GetTokenInformation"
0x18007f225  jmp     short loc_18007F264
0x18007f227  mov     ecx, 8; dwBytes
0x18007f22c  lea     r8, [rbp+StringSid]
0x18007f230  mov     edx, ecx; dwFlags
0x18007f232  call    WfpMemAlloc
0x18007f237  mov     rdi, [rbp+StringSid]
0x18007f23b  mov     rbx, rax
0x18007f23e  test    rax, rax
0x18007f241  jnz     short loc_18007F277
0x18007f243  mov     rcx, [rsi]; Sid
0x18007f246  mov     rdx, rdi; StringSid
0x18007f249  call    cs:__imp_ConvertSidToStringSidW
0x18007f24f  test    eax, eax
0x18007f251  jnz     loc_18007F2D7
0x18007f257  call    cs:__imp_GetLastError
0x18007f25d  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSidW"
0x18007f264  mov     r9d, r13d
0x18007f267  mov     r8d, eax
0x18007f26a  call    WfpReportSysErrorAsWinError
0x18007f26f  mov     rbx, rax
0x18007f272  test    rax, rax
0x18007f275  jz      short loc_18007F288
0x18007f277  cmp     qword ptr [rdi], 0
0x18007f27b  jz      short loc_18007F288
0x18007f27d  mov     edx, r13d
0x18007f280  mov     rcx, rdi
0x18007f283  call    IkeFreeGroupArray
0x18007f288  test    rsi, rsi
0x18007f28b  jz      short loc_18007F296
0x18007f28d  lea     rcx, [rbp+TokenInformation]
0x18007f291  call    WfpMemFree
0x18007f296  xor     edx, edx
0x18007f298  lea     rcx, aIkegetprimaryg; "IkeGetPrimaryGroupFromToken"
0x18007f29f  call    TraceLogHelper
0x18007f2a4  lea     rdx, aIkegetprimaryg; "IkeGetPrimaryGroupFromToken"
0x18007f2ab  mov     rcx, rbx
0x18007f2ae  call    IkeReturnError
0x18007f2b3  mov     rcx, [rbp+var_8]
0x18007f2b7  xor     rcx, rsp; StackCookie
0x18007f2ba  call    __security_check_cookie
0x18007f2bf  mov     rbx, [rsp+50h+arg_18]
0x18007f2c7  add     rsp, 50h
0x18007f2cb  pop     r15
0x18007f2cd  pop     r14
0x18007f2cf  pop     r13
0x18007f2d1  pop     r12
0x18007f2d3  pop     rdi
0x18007f2d4  pop     rsi
0x18007f2d5  pop     rbp
0x18007f2d6  retn
0x18007f2d7  mov     [r15], rdi
0x18007f2da  mov     [r12], r13d
0x18007f2de  jmp     short loc_18007F288
```
