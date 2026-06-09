# IkeGetGroupsFromToken

- ea: `0x18007e1c4`
- end: `0x18007e366`
- name: `IkeGetGroupsFromToken`
- size: `418`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007c768`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x18004cad0`
- `0x180050850`
- `0x18007e1c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e2e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e2e3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007e228`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007e280`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007e228`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007e280`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007e2d4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007e2d4`

## string_xrefs

- `0x18007e290`: `GetTokenInformation`
- `0x18007e2e9`: `ConvertSidToStringSidW`
- `0x18007e1f5`: `IkeGetGroupsFromToken`
- `0x18007e240`: `IkeGetGroupsFromToken`
- `0x18007e325`: `IkeGetGroupsFromToken`
- `0x18007e331`: `IkeGetGroupsFromToken`

## pseudocode

```c
__int64 __fastcall IkeGetGroupsFromToken(HANDLE TokenHandle, _QWORD *a2, _DWORD *a3)
{
  _DWORD *v3; // rbx
  __int64 v4; // rsi
  DWORD LastError; // eax
  __int64 v9; // rcx
  const char *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 i; // r14
  LPVOID TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF
  DWORD TokenInformationLength; // [rsp+40h] [rbp-10h] BYREF

  v3 = 0;
  v4 = 0;
  *a2 = 0;
  v17 = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  *a3 = 0;
  TraceLogHelper("IkeGetGroupsFromToken", 1);
  if ( !GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      v10 = "IkeGetGroupsFromToken";
      goto LABEL_13;
    }
  }
  v11 = WfpMemAlloc(TokenInformationLength, 0, &TokenInformation);
  v3 = TokenInformation;
  v12 = v11;
  if ( !v11 )
  {
    if ( !GetTokenInformation(
            TokenHandle,
            TokenGroups,
            TokenInformation,
            TokenInformationLength,
            &TokenInformationLength) )
    {
      LastError = GetLastError();
      v10 = "GetTokenInformation";
LABEL_13:
      v12 = WfpReportSysErrorAsWinError(v9, v10, LastError, 1);
      if ( !v12 )
        goto LABEL_16;
      goto LABEL_14;
    }
    v13 = WfpMemAlloc(8LL * (unsigned int)*v3, 8u, &v17);
    v4 = v17;
    v12 = v13;
    if ( !v13 )
    {
      for ( i = 0; (unsigned int)i < *v3; i = (unsigned int)(i + 1) )
      {
        if ( !ConvertSidToStringSidW(*(PSID *)&v3[4 * (unsigned int)i + 2], (LPWSTR *)(v4 + 8 * i)) )
        {
          LastError = GetLastError();
          v10 = "ConvertSidToStringSidW";
          goto LABEL_13;
        }
      }
      *a2 = v4;
      *a3 = *v3;
      goto LABEL_16;
    }
  }
LABEL_14:
  if ( !v3 )
    goto LABEL_18;
  IkeFreeGroupArray(v4, (unsigned int)*v3);
LABEL_16:
  if ( v3 )
    WfpMemFree((LPCVOID *)&TokenInformation);
LABEL_18:
  TraceLogHelper("IkeGetGroupsFromToken", 0);
  return IkeReturnError(v12, "IkeGetGroupsFromToken");
}

```

## disassembly

```asm
0x18007e1c4  push    rbp
0x18007e1c6  push    rbx
0x18007e1c7  push    rsi
0x18007e1c8  push    rdi
0x18007e1c9  push    r12
0x18007e1cb  push    r14
0x18007e1cd  push    r15
0x18007e1cf  mov     rbp, rsp
0x18007e1d2  sub     rsp, 50h
0x18007e1d6  mov     rax, cs:__security_cookie
0x18007e1dd  xor     rax, rsp
0x18007e1e0  mov     [rbp+var_8], rax
0x18007e1e4  xor     ebx, ebx
0x18007e1e6  xor     esi, esi
0x18007e1e8  mov     [rdx], rbx
0x18007e1eb  mov     r15, rdx
0x18007e1ee  mov     r14, rcx
0x18007e1f1  mov     [rbp+var_18], rsi
0x18007e1f5  lea     rcx, aIkegetgroupsfr; "IkeGetGroupsFromToken"
0x18007e1fc  mov     [rbp+TokenInformation], rbx
0x18007e200  lea     edi, [rsi+1]
0x18007e203  mov     [rbp+TokenInformationLength], ebx
0x18007e206  mov     edx, edi
0x18007e208  mov     [r8], ebx
0x18007e20b  mov     r12, r8
0x18007e20e  call    TraceLogHelper
0x18007e213  lea     rax, [rbp+TokenInformationLength]
0x18007e217  xor     r9d, r9d; TokenInformationLength
0x18007e21a  xor     r8d, r8d; TokenInformation
0x18007e21d  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18007e222  lea     edx, [rsi+2]; TokenInformationClass
0x18007e225  mov     rcx, r14; TokenHandle
0x18007e228  call    cs:__imp_GetTokenInformation
0x18007e22e  test    eax, eax
0x18007e230  jnz     short loc_18007E24C
0x18007e232  call    cs:__imp_GetLastError
0x18007e238  cmp     eax, 7Ah ; 'z'
0x18007e23b  jz      short loc_18007E24C
0x18007e23d  mov     r9d, edi
0x18007e240  lea     rdx, aIkegetgroupsfr; "IkeGetGroupsFromToken"
0x18007e247  jmp     loc_18007E2F6
0x18007e24c  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x18007e24f  lea     r8, [rbp+TokenInformation]
0x18007e253  xor     edx, edx; dwFlags
0x18007e255  call    WfpMemAlloc
0x18007e25a  mov     rbx, [rbp+TokenInformation]
0x18007e25e  mov     rdi, rax
0x18007e261  test    rax, rax
0x18007e264  jnz     loc_18007E306
0x18007e26a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18007e26e  lea     rax, [rbp+TokenInformationLength]
0x18007e272  mov     r8, rbx; TokenInformation
0x18007e275  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18007e27a  lea     edx, [rdi+2]; TokenInformationClass
0x18007e27d  mov     rcx, r14; TokenHandle
0x18007e280  call    cs:__imp_GetTokenInformation
0x18007e286  test    eax, eax
0x18007e288  jnz     short loc_18007E299
0x18007e28a  call    cs:__imp_GetLastError
0x18007e290  lea     rdx, aGettokeninform; "GetTokenInformation"
0x18007e297  jmp     short loc_18007E2F0
0x18007e299  mov     ecx, [rbx]
0x18007e29b  lea     r8, [rbp+var_18]
0x18007e29f  shl     rcx, 3; dwBytes
0x18007e2a3  mov     edx, 8; dwFlags
0x18007e2a8  call    WfpMemAlloc
0x18007e2ad  mov     rsi, [rbp+var_18]
0x18007e2b1  mov     rdi, rax
0x18007e2b4  test    rax, rax
0x18007e2b7  jnz     short loc_18007E306
0x18007e2b9  xor     r14d, r14d
0x18007e2bc  cmp     r14d, [rbx]
0x18007e2bf  jnb     loc_18007E35B
0x18007e2c5  mov     ecx, r14d
0x18007e2c8  lea     rdx, [rsi+r14*8]; StringSid
0x18007e2cc  add     rcx, rcx
0x18007e2cf  mov     rcx, [rbx+rcx*8+8]; Sid
0x18007e2d4  call    cs:__imp_ConvertSidToStringSidW
0x18007e2da  test    eax, eax
0x18007e2dc  jz      short loc_18007E2E3
0x18007e2de  inc     r14d
0x18007e2e1  jmp     short loc_18007E2BC
0x18007e2e3  call    cs:__imp_GetLastError
0x18007e2e9  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSidW"
0x18007e2f0  mov     r9d, 1
0x18007e2f6  mov     r8d, eax
0x18007e2f9  call    WfpReportSysErrorAsWinError
0x18007e2fe  mov     rdi, rax
0x18007e301  test    rax, rax
0x18007e304  jz      short loc_18007E315
0x18007e306  test    rbx, rbx
0x18007e309  jz      short loc_18007E323
0x18007e30b  mov     edx, [rbx]
0x18007e30d  mov     rcx, rsi
0x18007e310  call    IkeFreeGroupArray
0x18007e315  test    rbx, rbx
0x18007e318  jz      short loc_18007E323
0x18007e31a  lea     rcx, [rbp+TokenInformation]
0x18007e31e  call    WfpMemFree
0x18007e323  xor     edx, edx
0x18007e325  lea     rcx, aIkegetgroupsfr; "IkeGetGroupsFromToken"
0x18007e32c  call    TraceLogHelper
0x18007e331  lea     rdx, aIkegetgroupsfr; "IkeGetGroupsFromToken"
0x18007e338  mov     rcx, rdi
0x18007e33b  call    IkeReturnError
0x18007e340  mov     rcx, [rbp+var_8]
0x18007e344  xor     rcx, rsp; StackCookie
0x18007e347  call    __security_check_cookie
0x18007e34c  add     rsp, 50h
0x18007e350  pop     r15
0x18007e352  pop     r14
0x18007e354  pop     r12
0x18007e356  pop     rdi
0x18007e357  pop     rsi
0x18007e358  pop     rbx
0x18007e359  pop     rbp
0x18007e35a  retn
0x18007e35b  mov     [r15], rsi
0x18007e35e  mov     eax, [rbx]
0x18007e360  mov     [r12], eax
0x18007e364  jmp     short loc_18007E315
```
