# IRegOpenKeyAudio

- ea: `0x180008860`
- end: `0x18000890f`
- name: `IRegOpenKeyAudio`
- size: `175`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800084c0`
- `0x180008660`
- `0x180011434`

## callees

- `0x180008860`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800088f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800088f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800088a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800088ee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800088a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800088ee`

## pseudocode

```c
HKEY __fastcall IRegOpenKeyAudio(LPCWSTR lpSubKey)
{
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  phkResult = 0;
  RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\Audio\\", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( !lpSubKey )
    return hKey;
  if ( hKey )
  {
    RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
    RegCloseKey(hKey);
  }
  return phkResult;
}

```

## disassembly

```asm
0x180008860  mov     r11, rsp
0x180008863  mov     [r11+18h], rbx
0x180008867  push    rdi
0x180008868  sub     rsp, 50h
0x18000886c  xor     edi, edi
0x18000886e  lea     rax, [r11+8]
0x180008872  mov     [r11-18h], rdi
0x180008876  lea     rdx, gszAudioProfileKey; "Software\\Microsoft\\Multimedia\\Audio"...
0x18000887d  mov     [r11-20h], rax
0x180008881  mov     rbx, rcx
0x180008884  mov     [r11-28h], rdi
0x180008888  xor     r9d, r9d; lpClass
0x18000888b  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180008893  xor     r8d, r8d; Reserved
0x180008896  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000889d  mov     [rsp+58h+dwOptions], edi; dwOptions
0x1800088a1  mov     [r11+8], rdi
0x1800088a5  mov     [r11+10h], rdi
0x1800088a9  call    cs:__imp_RegCreateKeyExW
0x1800088af  test    rbx, rbx
0x1800088b2  jnz     short loc_1800088BB
0x1800088b4  mov     rax, [rsp+58h+hKey]
0x1800088b9  jmp     short loc_180008904
0x1800088bb  mov     rcx, [rsp+58h+hKey]; hKey
0x1800088c0  test    rcx, rcx
0x1800088c3  jz      short loc_1800088FF
0x1800088c5  mov     [rsp+58h+lpdwDisposition], rdi; lpdwDisposition
0x1800088ca  lea     rax, [rsp+58h+arg_8]
0x1800088cf  mov     [rsp+58h+phkResult], rax; phkResult
0x1800088d4  xor     r9d, r9d; lpClass
0x1800088d7  mov     [rsp+58h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800088dc  xor     r8d, r8d; Reserved
0x1800088df  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800088e7  mov     rdx, rbx; lpSubKey
0x1800088ea  mov     [rsp+58h+dwOptions], edi; dwOptions
0x1800088ee  call    cs:__imp_RegCreateKeyExW
0x1800088f4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800088f9  call    cs:__imp_RegCloseKey
0x1800088ff  mov     rax, [rsp+58h+arg_8]
0x180008904  mov     rbx, [rsp+58h+arg_10]
0x180008909  add     rsp, 50h
0x18000890d  pop     rdi
0x18000890e  retn
```
