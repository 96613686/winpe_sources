# IkeGetLuidFromToken

- ea: `0x180078ea8`
- end: `0x180078f5c`
- name: `IkeGetLuidFromToken`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c69e0`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180050850`
- `0x180078ea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078f09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078eff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078eff`

## string_xrefs

- `0x180078f16`: `GetTokenInformation`
- `0x180078f2f`: `IkeGetLuidFromToken`

## pseudocode

```c
__int64 __fastcall IkeGetLuidFromToken(void *a1, _QWORD *a2)
{
  __int64 v2; // rbx
  DWORD LastError; // eax
  __int64 v5; // rcx
  DWORD v7; // [rsp+30h] [rbp-58h] BYREF
  _OWORD v8[3]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v9; // [rsp+68h] [rbp-20h]

  v2 = 0;
  v7 = 0;
  memset(v8, 0, sizeof(v8));
  v9 = 0;
  if ( a1 )
  {
    if ( GetTokenInformation(a1, TokenStatistics, v8, 0x38u, &v7) )
    {
      *a2 = v9;
    }
    else
    {
      LastError = GetLastError();
      v2 = WfpReportSysErrorAsWinError(v5, "GetTokenInformation", LastError, 1);
    }
  }
  return IkeReturnError(v2, "IkeGetLuidFromToken");
}

```

## disassembly

```asm
0x180078ea8  mov     r11, rsp
0x180078eab  mov     [r11+18h], rbx
0x180078eaf  push    rdi
0x180078eb0  sub     rsp, 80h
0x180078eb7  mov     rax, cs:__security_cookie
0x180078ebe  xor     rax, rsp
0x180078ec1  mov     [rsp+88h+var_18], rax
0x180078ec6  xorps   xmm0, xmm0
0x180078ec9  xor     eax, eax
0x180078ecb  xor     ebx, ebx
0x180078ecd  mov     [rsp+88h+var_58], eax
0x180078ed1  mov     rdi, rdx
0x180078ed4  movups  [rsp+88h+var_50], xmm0
0x180078ed9  movups  [rsp+88h+var_40], xmm0
0x180078ede  movups  [rsp+88h+var_30], xmm0
0x180078ee3  mov     [r11-20h], rax
0x180078ee7  test    rcx, rcx
0x180078eea  jz      short loc_180078F2F
0x180078eec  lea     rax, [r11-58h]
0x180078ef0  lea     r9d, [rbx+38h]; TokenInformationLength
0x180078ef4  mov     [r11-68h], rax
0x180078ef8  lea     r8, [r11-50h]; TokenInformation
0x180078efc  lea     edx, [rbx+0Ah]; TokenInformationClass
0x180078eff  call    cs:__imp_GetTokenInformation
0x180078f05  test    eax, eax
0x180078f07  jnz     short loc_180078F27
0x180078f09  call    cs:__imp_GetLastError
0x180078f0f  mov     r8d, eax
0x180078f12  lea     r9d, [rbx+1]
0x180078f16  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180078f1d  call    WfpReportSysErrorAsWinError
0x180078f22  mov     rbx, rax
0x180078f25  jmp     short loc_180078F2F
0x180078f27  mov     rax, [rsp+88h+var_20]
0x180078f2c  mov     [rdi], rax
0x180078f2f  lea     rdx, aIkegetluidfrom; "IkeGetLuidFromToken"
0x180078f36  mov     rcx, rbx
0x180078f39  call    IkeReturnError
0x180078f3e  mov     rcx, [rsp+88h+var_18]
0x180078f43  xor     rcx, rsp; StackCookie
0x180078f46  call    __security_check_cookie
0x180078f4b  mov     rbx, [rsp+88h+arg_10]
0x180078f53  add     rsp, 80h
0x180078f5a  pop     rdi
0x180078f5b  retn
```
