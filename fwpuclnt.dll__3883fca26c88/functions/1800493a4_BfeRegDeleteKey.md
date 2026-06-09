# BfeRegDeleteKey

- ea: `0x1800493a4`
- end: `0x18004944c`
- name: `BfeRegDeleteKey`
- size: `168`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, HANDLE hTransaction)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001dc80`
- `0x1800491ec`

## callees

- `0x1800034e0`
- `0x180007e38`
- `0x1800491ec`
- `0x1800492c8`
- `0x1800493a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180049407`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180049407`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x1800493e3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x1800493e3`

## string_xrefs

- `0x18004941a`: `RegDeleteKeyExW`
- `0x180049430`: `BfeRegDeleteKey`
- `0x1800493f6`: `RegDeleteKeyTransactedW`

## pseudocode

```c
__int64 __fastcall BfeRegDeleteKey(HKEY hKey, LPCWSTR lpSubKey, HANDLE hTransaction)
{
  __int64 v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rcx
  const char *v9; // rdx
  __int64 v10; // rax

  v6 = BfeRegDeleteAllSubKeys(hKey);
  if ( v6 )
    goto LABEL_11;
  if ( lpSubKey )
  {
    if ( hTransaction )
    {
      v7 = RegDeleteKeyTransactedW(hKey, lpSubKey, 0, 0, hTransaction, 0);
      if ( (v7 & 0xFFFFFFFD) == 0 )
        return v6;
      v9 = "RegDeleteKeyTransactedW";
    }
    else
    {
      v7 = RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
      if ( (v7 & 0xFFFFFFFD) == 0 )
        return v6;
      v9 = "RegDeleteKeyExW";
    }
    v10 = WfpReportSysErrorAsWinError(v8, v9, v7);
  }
  else
  {
    v10 = BfeRegDeleteAllValues(hKey);
  }
  v6 = v10;
  if ( v10 )
LABEL_11:
    WfpReportError(v6, "BfeRegDeleteKey");
  return v6;
}

```

## disassembly

```asm
0x1800493a4  push    rbx
0x1800493a6  push    rbp
0x1800493a7  push    rsi
0x1800493a8  push    rdi
0x1800493a9  sub     rsp, 38h
0x1800493ad  mov     rbp, r8
0x1800493b0  mov     rdi, rdx
0x1800493b3  mov     rsi, rcx
0x1800493b6  call    BfeRegDeleteAllSubKeys
0x1800493bb  mov     rbx, rax
0x1800493be  test    rax, rax
0x1800493c1  jnz     short loc_180049430
0x1800493c3  mov     rcx, rsi; hKey
0x1800493c6  test    rdi, rdi
0x1800493c9  jz      short loc_180049423
0x1800493cb  xor     r9d, r9d; Reserved
0x1800493ce  xor     r8d, r8d; samDesired
0x1800493d1  mov     rdx, rdi; lpSubKey
0x1800493d4  test    rbp, rbp
0x1800493d7  jz      short loc_180049407
0x1800493d9  mov     [rsp+58h+pExtendedParameter], r8; pExtendedParameter
0x1800493de  mov     [rsp+58h+hTransaction], rbp; hTransaction
0x1800493e3  call    cs:__imp_RegDeleteKeyTransactedW
0x1800493ea  nop     dword ptr [rax+rax+00h]
0x1800493ef  test    eax, 0FFFFFFFDh
0x1800493f4  jz      short loc_18004943F
0x1800493f6  lea     rdx, aRegdeletekeytr_0; "RegDeleteKeyTransactedW"
0x1800493fd  mov     r8d, eax
0x180049400  call    WfpReportSysErrorAsWinError
0x180049405  jmp     short loc_180049428
0x180049407  call    cs:__imp_RegDeleteKeyExW
0x18004940e  nop     dword ptr [rax+rax+00h]
0x180049413  test    eax, 0FFFFFFFDh
0x180049418  jz      short loc_18004943F
0x18004941a  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180049421  jmp     short loc_1800493FD
0x180049423  call    BfeRegDeleteAllValues
0x180049428  mov     rbx, rax
0x18004942b  test    rax, rax
0x18004942e  jz      short loc_18004943F
0x180049430  lea     rdx, aBferegdeleteke; "BfeRegDeleteKey"
0x180049437  mov     rcx, rbx
0x18004943a  call    WfpReportError
0x18004943f  mov     rax, rbx
0x180049442  add     rsp, 38h
0x180049446  pop     rdi
0x180049447  pop     rsi
0x180049448  pop     rbp
0x180049449  pop     rbx
0x18004944a  retn
```
