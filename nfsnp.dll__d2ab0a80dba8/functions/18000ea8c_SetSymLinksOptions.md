# SetSymLinksOptions

- ea: `0x18000ea8c`
- end: `0x18000ebbd`
- name: `SetSymLinksOptions`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000be24`

## callees

- `0x18000ea8c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000eb8b`
- `ADVAPI32!RegCloseKey` at `0x18000eb8b`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb21`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb51`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb81`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb21`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb51`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb81`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eae9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eae9`

## string_xrefs

- `0x18000eb04`: `SymLinks`
- `0x18000eb34`: `DeleteSymlinks`
- `0x18000eb64`: `DisplayAllLinks`

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
0x18000ea8c  mov     r11, rsp
0x18000ea8f  mov     [r11+18h], rbx
0x18000ea93  mov     [r11+10h], rdx
0x18000ea97  mov     [r11+8], rcx
0x18000ea9b  push    rbp
0x18000ea9c  mov     rbp, rsp
0x18000ea9f  sub     rsp, 40h
0x18000eaa3  mov     rbx, r8
0x18000eaa6  mov     [rbp+hKey], 0
0x18000eaae  lea     rax, [rbp+hKey]
0x18000eab2  mov     [rbp+cbData], 0
0x18000eab9  xor     r8d, r8d; ulOptions
0x18000eabc  mov     [r11-28h], rax
0x18000eac0  mov     r9d, 20019h; samDesired
0x18000eac6  mov     [rbp+Data], 1
0x18000eacd  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000ead4  mov     [rbp+arg_18], 0
0x18000eadb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000eae2  mov     dword ptr [rbp+var_10], 0
0x18000eae9  call    cs:__imp_RegOpenKeyExW
0x18000eaef  test    eax, eax
0x18000eaf1  jnz     loc_18000EB91
0x18000eaf7  mov     rcx, [rbp+hKey]; hKey
0x18000eafb  lea     rax, [rbp+cbData]
0x18000eaff  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000eb04  lea     rdx, aSymlinks; "SymLinks"
0x18000eb0b  lea     rax, [rbp+Data]
0x18000eb0f  mov     [rbp+cbData], 4
0x18000eb16  xor     r9d, r9d; lpType
0x18000eb19  mov     [rsp+40h+lpData], rax; lpData
0x18000eb1e  xor     r8d, r8d; lpReserved
0x18000eb21  call    cs:__imp_RegQueryValueExW
0x18000eb27  mov     rcx, [rbp+hKey]; hKey
0x18000eb2b  lea     rax, [rbp+cbData]
0x18000eb2f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000eb34  lea     rdx, aDeletesymlinks; "DeleteSymlinks"
0x18000eb3b  lea     rax, [rbp+arg_18]
0x18000eb3f  mov     [rbp+cbData], 4
0x18000eb46  xor     r9d, r9d; lpType
0x18000eb49  mov     [rsp+40h+lpData], rax; lpData
0x18000eb4e  xor     r8d, r8d; lpReserved
0x18000eb51  call    cs:__imp_RegQueryValueExW
0x18000eb57  mov     rcx, [rbp+hKey]; hKey
0x18000eb5b  lea     rax, [rbp+cbData]
0x18000eb5f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000eb64  lea     rdx, aDisplayalllink; "DisplayAllLinks"
0x18000eb6b  lea     rax, [rbp+var_10]
0x18000eb6f  mov     [rbp+cbData], 4
0x18000eb76  xor     r9d, r9d; lpType
0x18000eb79  mov     [rsp+40h+lpData], rax; lpData
0x18000eb7e  xor     r8d, r8d; lpReserved
0x18000eb81  call    cs:__imp_RegQueryValueExW
0x18000eb87  mov     rcx, [rbp+hKey]; hKey
0x18000eb8b  call    cs:__imp_RegCloseKey
0x18000eb91  cmp     [rbp+Data], 0
0x18000eb95  jz      short loc_18000EB9C
0x18000eb97  bts     dword ptr [rbx+38h], 9
0x18000eb9c  cmp     [rbp+arg_18], 0
0x18000eba0  jz      short loc_18000EBA7
0x18000eba2  bts     dword ptr [rbx+38h], 0Ch
0x18000eba7  cmp     dword ptr [rbp+var_10], 0
0x18000ebab  jz      short loc_18000EBB2
0x18000ebad  bts     dword ptr [rbx+38h], 0Bh
0x18000ebb2  mov     rbx, [rsp+40h+arg_10]
0x18000ebb7  add     rsp, 40h
0x18000ebbb  pop     rbp
0x18000ebbc  retn
```
