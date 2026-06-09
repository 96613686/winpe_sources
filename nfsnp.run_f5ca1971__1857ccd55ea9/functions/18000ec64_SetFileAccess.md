# SetFileAccess

- ea: `0x18000ec64`
- end: `0x18000ed9c`
- name: `SetFileAccess`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000ec64`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000ecee`
- `msvcrt!wcscat_s` at `0x18000ecee`
- `msvcrt!wcsncpy_s` at `0x18000ecd1`
- `msvcrt!wcsncpy_s` at `0x18000ecd1`
- `ADVAPI32!RegCloseKey` at `0x18000ed6a`
- `ADVAPI32!RegCloseKey` at `0x18000ed6a`
- `ADVAPI32!RegQueryValueExW` at `0x18000ed57`
- `ADVAPI32!RegQueryValueExW` at `0x18000ed57`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ed19`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ed19`

## string_xrefs

- `0x18000ed38`: `Access`

## pseudocode

```c
LSTATUS __fastcall SetFileAccess(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  LSTATUS v5; // edi
  LSTATUS result; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = 493;
  hKey = 0;
  *(_DWORD *)Data = 493;
  cbData = 0;
  v5 = 13;
  memset_0(Destination, 0, 0x208u);
  wcsncpy_s(Destination, 0x104u, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default", 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Defaults");
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Destination, 0, 0x20019u, &hKey);
  if ( !result )
  {
    cbData = 4;
    v5 = RegQueryValueExW(hKey, L"Access", 0, 0, Data, &cbData);
    result = RegCloseKey(hKey);
  }
  if ( !v5 )
    v3 = *(_DWORD *)Data;
  *(_DWORD *)(a3 + 32) = v3;
  return result;
}

```

## disassembly

```asm
0x18000ec64  push    rbp
0x18000ec66  push    rbx
0x18000ec67  push    rsi
0x18000ec68  push    rdi
0x18000ec69  lea     rbp, [rsp-168h]
0x18000ec71  sub     rsp, 268h
0x18000ec78  mov     rax, cs:__security_cookie
0x18000ec7f  xor     rax, rsp
0x18000ec82  mov     [rbp+180h+var_30], rax
0x18000ec89  mov     ebx, 1EDh
0x18000ec8e  mov     [rsp+280h+hKey], 0
0x18000ec97  mov     rsi, r8
0x18000ec9a  mov     dword ptr [rsp+280h+Data], ebx
0x18000ec9e  xor     edx, edx; Val
0x18000eca0  mov     [rsp+280h+cbData], 0
0x18000eca8  lea     rcx, [rsp+280h+Destination]; void *
0x18000ecad  mov     edi, 0Dh
0x18000ecb2  lea     r8d, [rbx+1Bh]; Size
0x18000ecb6  call    memset_0
0x18000ecbb  mov     r9d, 103h; MaxCount
0x18000ecc1  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000ecc8  lea     rcx, [rsp+280h+Destination]; Destination
0x18000eccd  lea     edx, [r9+1]; SizeInWords
0x18000ecd1  call    cs:__imp_wcsncpy_s
0x18000ecd8  nop     dword ptr [rax+rax+00h]
0x18000ecdd  lea     r8, aDefaults; "\\Defaults"
0x18000ece4  mov     edx, 104h; SizeInWords
0x18000ece9  lea     rcx, [rsp+280h+Destination]; Destination
0x18000ecee  call    cs:__imp_wcscat_s
0x18000ecf5  nop     dword ptr [rax+rax+00h]
0x18000ecfa  lea     rax, [rsp+280h+hKey]
0x18000ecff  mov     r9d, 20019h; samDesired
0x18000ed05  xor     r8d, r8d; ulOptions
0x18000ed08  mov     [rsp+280h+phkResult], rax; phkResult
0x18000ed0d  lea     rdx, [rsp+280h+Destination]; lpSubKey
0x18000ed12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ed19  call    cs:__imp_RegOpenKeyExW
0x18000ed20  nop     dword ptr [rax+rax+00h]
0x18000ed25  test    eax, eax
0x18000ed27  jnz     short loc_18000ED76
0x18000ed29  mov     rcx, [rsp+280h+hKey]; hKey
0x18000ed2e  lea     rax, [rsp+280h+cbData]
0x18000ed33  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000ed38  lea     rdx, aAccess; "Access"
0x18000ed3f  lea     rax, [rsp+280h+Data]
0x18000ed44  mov     [rsp+280h+cbData], 4
0x18000ed4c  xor     r9d, r9d; lpType
0x18000ed4f  mov     [rsp+280h+phkResult], rax; lpData
0x18000ed54  xor     r8d, r8d; lpReserved
0x18000ed57  call    cs:__imp_RegQueryValueExW
0x18000ed5e  nop     dword ptr [rax+rax+00h]
0x18000ed63  mov     rcx, [rsp+280h+hKey]; hKey
0x18000ed68  mov     edi, eax
0x18000ed6a  call    cs:__imp_RegCloseKey
0x18000ed71  nop     dword ptr [rax+rax+00h]
0x18000ed76  test    edi, edi
0x18000ed78  cmovz   ebx, dword ptr [rsp+280h+Data]
0x18000ed7d  mov     [rsi+20h], ebx
0x18000ed80  mov     rcx, [rbp+180h+var_30]
0x18000ed87  xor     rcx, rsp; StackCookie
0x18000ed8a  call    __security_check_cookie
0x18000ed8f  add     rsp, 268h
0x18000ed96  pop     rdi
0x18000ed97  pop     rsi
0x18000ed98  pop     rbx
0x18000ed99  pop     rbp
0x18000ed9a  retn
```
