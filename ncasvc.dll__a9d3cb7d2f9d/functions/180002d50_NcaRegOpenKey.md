# NcaRegOpenKey

- ea: `0x180002d50`
- end: `0x180002e2f`
- name: `NcaRegOpenKey`
- size: `223`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, HKEY *, int *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005770`
- `0x18000ff30`
- `0x180014058`
- `0x180014b80`
- `0x18001a654`
- `0x18001ac78`

## callees

- `0x180002d50`
- `0x1800033bc`
- `0x1800199b4`
- `0x180019dac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002dc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002dc0`

## string_xrefs

- `0x180002de4`: `NcaRegOpenKey`
- `0x180002df6`: `NcaRegOpenKey`
- `0x180002ddd`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall NcaRegOpenKey(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, HKEY *a4, int *a5)
{
  unsigned int v9; // eax
  int v10; // edx
  __int64 result; // rax
  HKEY phkResult; // [rsp+68h] [rbp+20h] BYREF

  phkResult = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_149084e4aca63d179354f111bb13106e_Traceguids, lpSubKey);
  *a4 = 0;
  v9 = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, &phkResult);
  if ( v9 == 2 )
  {
    v10 = 0;
LABEL_10:
    result = 0;
    *a5 = v10;
    return result;
  }
  if ( !v9 )
  {
    v10 = 1;
    *a4 = phkResult;
    goto LABEL_10;
  }
  result = NcaReportErrorAsWinError("NcaRegOpenKey", "RegOpenKeyExW", v9);
  if ( (int)result < 0 )
    return NcaReportReturnError("NcaRegOpenKey", (unsigned int)result);
  return result;
}

```

## disassembly

```asm
0x180002d50  mov     [rsp+arg_0], rbx
0x180002d55  mov     [rsp+arg_8], rbp
0x180002d5a  push    rsi
0x180002d5b  push    rdi
0x180002d5c  push    r14
0x180002d5e  sub     rsp, 30h
0x180002d62  xor     r14d, r14d
0x180002d65  mov     rbx, r9
0x180002d68  mov     [rsp+48h+arg_18], r14
0x180002d6d  mov     esi, r8d
0x180002d70  mov     rdi, rdx
0x180002d73  mov     rbp, rcx
0x180002d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d7d  lea     rax, WPP_GLOBAL_Control
0x180002d84  cmp     rcx, rax
0x180002d87  jz      short loc_180002DA7
0x180002d89  test    byte ptr [rcx+1Ch], 8
0x180002d8d  jz      short loc_180002DA7
0x180002d8f  mov     rcx, [rcx+10h]
0x180002d93  lea     r8, WPP_149084e4aca63d179354f111bb13106e_Traceguids
0x180002d9a  mov     edx, 0Bh
0x180002d9f  mov     r9, rdi
0x180002da2  call    WPP_SF_S
0x180002da7  lea     rax, [rsp+48h+arg_18]
0x180002dac  mov     [rbx], r14
0x180002daf  mov     r9d, esi; samDesired
0x180002db2  mov     [rsp+48h+phkResult], rax; phkResult
0x180002db7  xor     r8d, r8d; ulOptions
0x180002dba  mov     rdx, rdi; lpSubKey
0x180002dbd  mov     rcx, rbp; hKey
0x180002dc0  call    cs:__imp_RegOpenKeyExW
0x180002dc7  nop     dword ptr [rax+rax+00h]
0x180002dcc  cmp     eax, 2
0x180002dcf  jnz     short loc_180002DD6
0x180002dd1  mov     edx, r14d
0x180002dd4  jmp     short loc_180002E11
0x180002dd6  test    eax, eax
0x180002dd8  jz      short loc_180002E04
0x180002dda  mov     r8d, eax
0x180002ddd  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180002de4  lea     rcx, aNcaregopenkey; "NcaRegOpenKey"
0x180002deb  call    NcaReportErrorAsWinError
0x180002df0  test    eax, eax
0x180002df2  jns     short loc_180002E1B
0x180002df4  mov     edx, eax
0x180002df6  lea     rcx, aNcaregopenkey; "NcaRegOpenKey"
0x180002dfd  call    NcaReportReturnError
0x180002e02  jmp     short loc_180002E1B
0x180002e04  mov     rax, [rsp+48h+arg_18]
0x180002e09  mov     edx, 1
0x180002e0e  mov     [rbx], rax
0x180002e11  mov     rcx, [rsp+48h+arg_20]
0x180002e16  mov     eax, r14d
0x180002e19  mov     [rcx], edx
0x180002e1b  mov     rbx, [rsp+48h+arg_0]
0x180002e20  mov     rbp, [rsp+48h+arg_8]
0x180002e25  add     rsp, 30h
0x180002e29  pop     r14
0x180002e2b  pop     rdi
0x180002e2c  pop     rsi
0x180002e2d  retn
```
