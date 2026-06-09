# ClearTargetOfflineRegistryKey(void)

- ea: `0x180006dd8`
- end: `0x180006e54`
- name: `?ClearTargetOfflineRegistryKey@@YAXXZ`
- size: `124`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ba0`

## callees

- `0x180006dd8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180006e49`
- `ADVAPI32!RegCloseKey` at `0x180006e49`
- `ADVAPI32!RegCreateKeyExW` at `0x180006e23`
- `ADVAPI32!RegCreateKeyExW` at `0x180006e23`
- `ADVAPI32!RegDeleteValueW` at `0x180006e39`
- `ADVAPI32!RegDeleteValueW` at `0x180006e39`

## pseudocode

```c
void ClearTargetOfflineRegistryKey(void)
{
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          0) )
    RegDeleteValueW(hKey, L"RehydrationTargetOfflineSinceTime");
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180006dd8  mov     r11, rsp
0x180006ddb  sub     rsp, 58h
0x180006ddf  mov     qword ptr [r11-18h], 0
0x180006de7  lea     rax, [r11+8]
0x180006deb  mov     [r11-20h], rax
0x180006def  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180006df6  mov     qword ptr [r11-28h], 0
0x180006dfe  xor     r9d, r9d; lpClass
0x180006e01  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180006e09  xor     r8d, r8d; Reserved
0x180006e0c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180006e13  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180006e1b  mov     qword ptr [r11+8], 0
0x180006e23  call    cs:__imp_RegCreateKeyExW
0x180006e29  test    eax, eax
0x180006e2b  jnz     short loc_180006E3F
0x180006e2d  mov     rcx, [rsp+58h+hKey]; hKey
0x180006e32  lea     rdx, ValueName; "RehydrationTargetOfflineSinceTime"
0x180006e39  call    cs:__imp_RegDeleteValueW
0x180006e3f  mov     rcx, [rsp+58h+hKey]; hKey
0x180006e44  test    rcx, rcx
0x180006e47  jz      short loc_180006E4F
0x180006e49  call    cs:__imp_RegCloseKey
0x180006e4f  add     rsp, 58h
0x180006e53  retn
```
