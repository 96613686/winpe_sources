# ExtractLsaAuthenticationIdFromToken

- ea: `0x180027c34`
- end: `0x180027d12`
- name: `ExtractLsaAuthenticationIdFromToken`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027a48`
- `0x1800d5388`

## callees

- `0x180027c34`
- `0x1800a3420`
- `0x1800f9948`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180027cef`
- `ntdll!RtlCopyLuid` at `0x180027cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ca6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027c8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027c8a`

## pseudocode

```c
void __fastcall ExtractLsaAuthenticationIdFromToken(void *a1, struct _LUID *a2)
{
  unsigned int LastError; // eax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-59h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-49h] BYREF
  __int128 v6; // [rsp+48h] [rbp-41h]
  unsigned int v7; // [rsp+58h] [rbp-31h]
  int v8; // [rsp+5Ch] [rbp-2Dh]
  int v9; // [rsp+60h] [rbp-29h]
  _OWORD TokenInformation[3]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v11; // [rsp+D0h] [rbp+47h]

  ReturnLength[0] = 0;
  v11 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !GetTokenInformation(a1, TokenStatistics, TokenInformation, 0x38u, ReturnLength) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v7 = LastError;
    pExceptionObject = &ComError::`vftable';
    v8 = 835;
    v9 = 1;
    v6 = 0;
    throw (ComError *)&pExceptionObject;
  }
  RtlCopyLuid(a2, (PLUID)TokenInformation + 1);
}

```

## disassembly

```asm
0x180027c34  mov     [rsp-8+arg_10], rbx
0x180027c39  push    rbp
0x180027c3a  lea     rbp, [rsp-57h]
0x180027c3f  sub     rsp, 0E0h
0x180027c46  mov     rax, cs:__security_cookie
0x180027c4d  xor     rax, rsp
0x180027c50  mov     [rbp+57h+var_8], rax
0x180027c54  xorps   xmm0, xmm0
0x180027c57  mov     [rbp+57h+var_B0], 0
0x180027c5e  xor     eax, eax
0x180027c60  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180027c64  mov     r9d, 38h ; '8'; TokenInformationLength
0x180027c6a  mov     [rbp+57h+var_10], rax
0x180027c6e  mov     rbx, rdx
0x180027c71  lea     rax, [rbp+57h+var_B0]
0x180027c75  movups  [rbp+57h+TokenInformation], xmm0
0x180027c79  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180027c7e  lea     edx, [r9-2Eh]; TokenInformationClass
0x180027c82  movups  [rbp+57h+var_30], xmm0
0x180027c86  movups  [rbp+57h+var_20], xmm0
0x180027c8a  call    cs:__imp_GetTokenInformation
0x180027c90  test    eax, eax
0x180027c92  jnz     short loc_180027CE8
0x180027c94  call    cs:__imp_GetLastError
0x180027c9a  test    eax, eax
0x180027c9c  jg      short loc_180027CA6
0x180027c9e  call    cs:__imp_GetLastError
0x180027ca4  jmp     short loc_180027CB4
0x180027ca6  call    cs:__imp_GetLastError
0x180027cac  movzx   eax, ax
0x180027caf  or      eax, 80070000h
0x180027cb4  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180027cbb  mov     [rbp+57h+var_88], eax
0x180027cbe  mov     [rbp+57h+pExceptionObject], rcx
0x180027cc2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180027cc9  xorps   xmm0, xmm0
0x180027ccc  mov     [rbp+57h+var_84], 343h
0x180027cd3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027cd7  mov     [rbp+57h+var_80], 1
0x180027cde  movups  [rbp+57h+var_98], xmm0
0x180027ce2  call    _CxxThrowException_0
0x180027ce8  lea     rdx, [rbp+57h+TokenInformation+8]; SourceLuid
0x180027cec  mov     rcx, rbx; DestinationLuid
0x180027cef  call    cs:__imp_RtlCopyLuid
0x180027cf5  mov     rcx, [rbp+57h+var_8]
0x180027cf9  xor     rcx, rsp; StackCookie
0x180027cfc  call    __security_check_cookie
0x180027d01  mov     rbx, [rsp+0E0h+arg_10]
0x180027d09  add     rsp, 0E0h
0x180027d10  pop     rbp
0x180027d11  retn
```
