# BfeRegOpenKey

- ea: `0x18000e5b8`
- end: `0x18000e6a5`
- name: `BfeRegOpenKey`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e374`
- `0x1800491ec`

## callees

- `0x1800034e0`
- `0x180007e38`
- `0x18000e5b8`
- `0x180012bd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e63c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e63c`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18000e615`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18000e615`

## string_xrefs

- `0x18000e64f`: `RegOpenKeyExW`
- `0x18000e628`: `RegOpenKeyTransactedW`
- `0x18000e666`: `BfeRegOpenKey`

## pseudocode

```c
__int64 __fastcall BfeRegOpenKey(HKEY a1, const WCHAR *a2, REGSAM a3, void *a4, _QWORD *a5, _DWORD *a6)
{
  unsigned int v6; // eax
  __int64 v7; // rcx
  const char *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rbx
  HKEY phkResult; // [rsp+40h] [rbp-28h] BYREF

  phkResult = 0;
  *a5 = 0;
  *a6 = 0;
  if ( a4 )
  {
    v6 = RegOpenKeyTransactedW(a1, a2, 0, a3, &phkResult, a4, 0);
    if ( (v6 & 0xFFFFFFFD) != 0 )
    {
      v8 = "RegOpenKeyTransactedW";
      goto LABEL_6;
    }
  }
  else
  {
    v6 = RegOpenKeyExW(a1, a2, 0, a3, &phkResult);
    if ( (v6 & 0xFFFFFFFD) != 0 )
    {
      v8 = "RegOpenKeyExW";
LABEL_6:
      v9 = WfpReportSysErrorAsWinError(v7, v8, v6);
      v10 = v9;
      if ( v9 )
        WfpReportError(v9, "BfeRegOpenKey");
      return v10;
    }
  }
  v10 = 0;
  if ( v6 != 2 )
  {
    *a5 = phkResult;
    *a6 = 1;
  }
  return v10;
}

```

## disassembly

```asm
0x18000e5b8  mov     r11, rsp
0x18000e5bb  push    rbx
0x18000e5bc  push    rsi
0x18000e5bd  push    rdi
0x18000e5be  sub     rsp, 50h
0x18000e5c2  mov     rax, cs:__security_cookie
0x18000e5c9  xor     rax, rsp
0x18000e5cc  mov     [rsp+68h+var_20], rax
0x18000e5d1  mov     rdi, [rsp+68h+arg_20]
0x18000e5d9  lea     rax, [r11-28h]
0x18000e5dd  mov     rsi, [rsp+68h+arg_28]
0x18000e5e5  mov     qword ptr [r11-28h], 0
0x18000e5ed  mov     qword ptr [rdi], 0
0x18000e5f4  mov     dword ptr [rsi], 0
0x18000e5fa  test    r9, r9
0x18000e5fd  jz      short loc_18000E631
0x18000e5ff  mov     qword ptr [r11-38h], 0
0x18000e607  mov     [r11-40h], r9
0x18000e60b  mov     r9d, r8d; samDesired
0x18000e60e  xor     r8d, r8d; ulOptions
0x18000e611  mov     [r11-48h], rax
0x18000e615  call    cs:__imp_RegOpenKeyTransactedW
0x18000e61c  nop     dword ptr [rax+rax+00h]
0x18000e621  test    eax, 0FFFFFFFDh
0x18000e626  jz      short loc_18000E677
0x18000e628  lea     rdx, SubKey; "RegOpenKeyTransactedW"
0x18000e62f  jmp     short loc_18000E656
0x18000e631  mov     r9d, r8d; samDesired
0x18000e634  mov     [rsp+68h+phkResult], rax; phkResult
0x18000e639  xor     r8d, r8d; ulOptions
0x18000e63c  call    cs:__imp_RegOpenKeyExW
0x18000e643  nop     dword ptr [rax+rax+00h]
0x18000e648  test    eax, 0FFFFFFFDh
0x18000e64d  jz      short loc_18000E677
0x18000e64f  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18000e656  mov     r8d, eax
0x18000e659  call    WfpReportSysErrorAsWinError
0x18000e65e  mov     rbx, rax
0x18000e661  test    rax, rax
0x18000e664  jz      short loc_18000E68C
0x18000e666  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x18000e66d  mov     rcx, rax
0x18000e670  call    WfpReportError
0x18000e675  jmp     short loc_18000E68C
0x18000e677  xor     ebx, ebx
0x18000e679  cmp     eax, 2
0x18000e67c  jz      short loc_18000E68C
0x18000e67e  mov     rax, [rsp+68h+var_28]
0x18000e683  mov     [rdi], rax
0x18000e686  mov     dword ptr [rsi], 1
0x18000e68c  mov     rax, rbx
0x18000e68f  mov     rcx, [rsp+68h+var_20]
0x18000e694  xor     rcx, rsp; StackCookie
0x18000e697  call    __security_check_cookie
0x18000e69c  add     rsp, 50h
0x18000e6a0  pop     rdi
0x18000e6a1  pop     rsi
0x18000e6a2  pop     rbx
0x18000e6a3  retn
```
