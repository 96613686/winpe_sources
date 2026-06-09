# SetSymLinksOptions

- ea: `0x18000f89c`
- end: `0x18000f9ec`
- name: `SetSymLinksOptions`
- size: `336`
- prototype: `LSTATUS __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000c738`

## callees

- `0x18000f89c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000f9b3`
- `ADVAPI32!RegCloseKey` at `0x18000f9b3`
- `ADVAPI32!RegQueryValueExW` at `0x18000f937`
- `ADVAPI32!RegQueryValueExW` at `0x18000f96d`
- `ADVAPI32!RegQueryValueExW` at `0x18000f9a3`
- `ADVAPI32!RegQueryValueExW` at `0x18000f937`
- `ADVAPI32!RegQueryValueExW` at `0x18000f96d`
- `ADVAPI32!RegQueryValueExW` at `0x18000f9a3`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f8f9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f8f9`

## string_xrefs

- `0x18000f91a`: `SymLinks`
- `0x18000f950`: `DeleteSymlinks`
- `0x18000f986`: `DisplayAllLinks`

## pseudocode

```c
LSTATUS __fastcall SetSymLinksOptions(__int64 a1, __int64 a2, __int64 a3)
{
  LSTATUS result; // eax
  BYTE v5[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+50h] [rbp+10h] BYREF
  int v8; // [rsp+54h] [rbp+14h]
  DWORD cbData; // [rsp+58h] [rbp+18h] BYREF
  int v10; // [rsp+5Ch] [rbp+1Ch]
  int lpData; // [rsp+68h] [rbp+28h] BYREF

  v10 = HIDWORD(a2);
  v8 = HIDWORD(a1);
  hKey = 0;
  cbData = 0;
  Data = 1;
  lpData = 0;
  *(_DWORD *)v5 = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"SymLinks", 0, 0, (LPBYTE)&Data, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"DeleteSymlinks", 0, 0, (LPBYTE)&lpData, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"DisplayAllLinks", 0, 0, v5, &cbData);
    result = RegCloseKey(hKey);
  }
  if ( Data )
    *(_DWORD *)(a3 + 56) |= 0x200u;
  if ( lpData )
    *(_DWORD *)(a3 + 56) |= 0x1000u;
  if ( *(_DWORD *)v5 )
    *(_DWORD *)(a3 + 56) |= 0x800u;
  return result;
}

```

## disassembly

```asm
0x18000f89c  mov     r11, rsp
0x18000f89f  mov     [r11+18h], rbx
0x18000f8a3  mov     [r11+10h], rdx
0x18000f8a7  mov     [r11+8], rcx
0x18000f8ab  push    rbp
0x18000f8ac  mov     rbp, rsp
0x18000f8af  sub     rsp, 40h
0x18000f8b3  mov     rbx, r8
0x18000f8b6  mov     [rbp+hKey], 0
0x18000f8be  lea     rax, [rbp+hKey]
0x18000f8c2  mov     [rbp+cbData], 0
0x18000f8c9  xor     r8d, r8d; ulOptions
0x18000f8cc  mov     [r11-28h], rax
0x18000f8d0  mov     r9d, 20019h; samDesired
0x18000f8d6  mov     [rbp+Data], 1
0x18000f8dd  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000f8e4  mov     [rbp+arg_18], 0
0x18000f8eb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f8f2  mov     dword ptr [rbp+var_10], 0
0x18000f8f9  call    cs:__imp_RegOpenKeyExW
0x18000f900  nop     dword ptr [rax+rax+00h]
0x18000f905  test    eax, eax
0x18000f907  jnz     loc_18000F9BF
0x18000f90d  mov     rcx, [rbp+hKey]; hKey
0x18000f911  lea     rax, [rbp+cbData]
0x18000f915  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000f91a  lea     rdx, aSymlinks; "SymLinks"
0x18000f921  lea     rax, [rbp+Data]
0x18000f925  mov     [rbp+cbData], 4
0x18000f92c  xor     r9d, r9d; lpType
0x18000f92f  mov     [rsp+40h+lpData], rax; lpData
0x18000f934  xor     r8d, r8d; lpReserved
0x18000f937  call    cs:__imp_RegQueryValueExW
0x18000f93e  nop     dword ptr [rax+rax+00h]
0x18000f943  mov     rcx, [rbp+hKey]; hKey
0x18000f947  lea     rax, [rbp+cbData]
0x18000f94b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000f950  lea     rdx, aDeletesymlinks; "DeleteSymlinks"
0x18000f957  lea     rax, [rbp+arg_18]
0x18000f95b  mov     [rbp+cbData], 4
0x18000f962  xor     r9d, r9d; lpType
0x18000f965  mov     [rsp+40h+lpData], rax; lpData
0x18000f96a  xor     r8d, r8d; lpReserved
0x18000f96d  call    cs:__imp_RegQueryValueExW
0x18000f974  nop     dword ptr [rax+rax+00h]
0x18000f979  mov     rcx, [rbp+hKey]; hKey
0x18000f97d  lea     rax, [rbp+cbData]
0x18000f981  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000f986  lea     rdx, aDisplayalllink; "DisplayAllLinks"
0x18000f98d  lea     rax, [rbp+var_10]
0x18000f991  mov     [rbp+cbData], 4
0x18000f998  xor     r9d, r9d; lpType
0x18000f99b  mov     [rsp+40h+lpData], rax; lpData
0x18000f9a0  xor     r8d, r8d; lpReserved
0x18000f9a3  call    cs:__imp_RegQueryValueExW
0x18000f9aa  nop     dword ptr [rax+rax+00h]
0x18000f9af  mov     rcx, [rbp+hKey]; hKey
0x18000f9b3  call    cs:__imp_RegCloseKey
0x18000f9ba  nop     dword ptr [rax+rax+00h]
0x18000f9bf  cmp     [rbp+Data], 0
0x18000f9c3  jz      short loc_18000F9CA
0x18000f9c5  bts     dword ptr [rbx+38h], 9
0x18000f9ca  cmp     [rbp+arg_18], 0
0x18000f9ce  jz      short loc_18000F9D5
0x18000f9d0  bts     dword ptr [rbx+38h], 0Ch
0x18000f9d5  cmp     dword ptr [rbp+var_10], 0
0x18000f9d9  jz      short loc_18000F9E0
0x18000f9db  bts     dword ptr [rbx+38h], 0Bh
0x18000f9e0  mov     rbx, [rsp+40h+arg_10]
0x18000f9e5  add     rsp, 40h
0x18000f9e9  pop     rbp
0x18000f9ea  retn
```
