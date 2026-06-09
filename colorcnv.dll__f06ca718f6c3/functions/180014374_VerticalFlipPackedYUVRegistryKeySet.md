# VerticalFlipPackedYUVRegistryKeySet

- ea: `0x180014374`
- end: `0x18001440a`
- name: `VerticalFlipPackedYUVRegistryKeySet`
- size: `150`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010bec`

## callees

- `0x180014374`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800143d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800143d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800143f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800143f6`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800143a6`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800143a6`

## pseudocode

```c
_BOOL8 VerticalFlipPackedYUVRegistryKeySet()
{
  int v0; // ebx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  v0 = 0;
  if ( !RegOpenKeyW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Scrunch\\WMVideo", &hKey)
    && !RegQueryValueExW(hKey, L"Vertical Flip Packed YUV", 0, &Type, (LPBYTE)&Data, &cbData)
    && Type == 4 )
  {
    v0 = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0 == 1;
}

```

## disassembly

```asm
0x180014374  mov     rax, rsp
0x180014377  push    rbx
0x180014378  sub     rsp, 30h
0x18001437c  lea     r8, [rax+20h]; phkResult
0x180014380  mov     qword ptr [rax+20h], 0
0x180014388  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Scrunch\\WMVideo"
0x18001438f  mov     dword ptr [rax+8], 0
0x180014396  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001439d  mov     dword ptr [rax+10h], 4
0x1800143a4  xor     ebx, ebx
0x1800143a6  call    cs:__imp_RegOpenKeyW
0x1800143ac  test    eax, eax
0x1800143ae  jnz     short loc_1800143EC
0x1800143b0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800143b5  lea     rax, [rsp+38h+cbData]
0x1800143ba  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800143bf  lea     r9, [rsp+38h+Type]; lpType
0x1800143c4  lea     rax, [rsp+38h+Data]
0x1800143c9  xor     r8d, r8d; lpReserved
0x1800143cc  lea     rdx, aVerticalFlipPa; "Vertical Flip Packed YUV"
0x1800143d3  mov     [rsp+38h+lpData], rax; lpData
0x1800143d8  call    cs:__imp_RegQueryValueExW
0x1800143de  test    eax, eax
0x1800143e0  jnz     short loc_1800143EC
0x1800143e2  cmp     [rsp+38h+Type], 4
0x1800143e7  cmovz   ebx, [rsp+38h+Data]
0x1800143ec  mov     rcx, [rsp+38h+hKey]; hKey
0x1800143f1  test    rcx, rcx
0x1800143f4  jz      short loc_1800143FC
0x1800143f6  call    cs:__imp_RegCloseKey
0x1800143fc  xor     eax, eax
0x1800143fe  cmp     ebx, 1
0x180014401  setz    al
0x180014404  add     rsp, 30h
0x180014408  pop     rbx
0x180014409  retn
```
