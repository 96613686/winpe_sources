# DwmpResetColorizationParameters

- ea: `0x180015050`
- end: `0x180015123`
- name: `DwmpResetColorizationParameters`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180015050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150b1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001510b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150b1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800150f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001510b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015116`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001509b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001509b`

## pseudocode

```c
__int64 DwmpResetColorizationParameters()
{
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\DWM", 0, 0, 0, 2u, 0, &hKey, 0) )
  {
    RegDeleteValueW(hKey, L"ColorizationColor");
    RegDeleteValueW(hKey, L"ColorizationColorBalance");
    RegDeleteValueW(hKey, L"ColorizationAfterglow");
    RegDeleteValueW(hKey, L"ColorizationAfterglowBalance");
    RegDeleteValueW(hKey, L"ColorizationBlurBalance");
    RegDeleteValueW(hKey, L"EnableWindowColorization");
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180015050  mov     r11, rsp
0x180015053  sub     rsp, 58h
0x180015057  mov     qword ptr [r11-18h], 0
0x18001505f  lea     rax, [r11+8]
0x180015063  mov     [r11-20h], rax
0x180015067  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\DWM"
0x18001506e  mov     qword ptr [r11-28h], 0
0x180015076  xor     r9d, r9d; lpClass
0x180015079  mov     [rsp+58h+samDesired], 2; samDesired
0x180015081  xor     r8d, r8d; Reserved
0x180015084  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001508b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180015093  mov     qword ptr [r11+8], 0
0x18001509b  call    cs:__imp_RegCreateKeyExW
0x1800150a1  test    eax, eax
0x1800150a3  jnz     short loc_18001511C
0x1800150a5  mov     rcx, [rsp+58h+hKey]; hKey
0x1800150aa  lea     rdx, ValueName; "ColorizationColor"
0x1800150b1  call    cs:__imp_RegDeleteValueW
0x1800150b7  mov     rcx, [rsp+58h+hKey]; hKey
0x1800150bc  lea     rdx, aColorizationco_0; "ColorizationColorBalance"
0x1800150c3  call    cs:__imp_RegDeleteValueW
0x1800150c9  mov     rcx, [rsp+58h+hKey]; hKey
0x1800150ce  lea     rdx, aColorizationaf_0; "ColorizationAfterglow"
0x1800150d5  call    cs:__imp_RegDeleteValueW
0x1800150db  mov     rcx, [rsp+58h+hKey]; hKey
0x1800150e0  lea     rdx, aColorizationaf; "ColorizationAfterglowBalance"
0x1800150e7  call    cs:__imp_RegDeleteValueW
0x1800150ed  mov     rcx, [rsp+58h+hKey]; hKey
0x1800150f2  lea     rdx, aColorizationbl; "ColorizationBlurBalance"
0x1800150f9  call    cs:__imp_RegDeleteValueW
0x1800150ff  mov     rcx, [rsp+58h+hKey]; hKey
0x180015104  lea     rdx, aEnablewindowco; "EnableWindowColorization"
0x18001510b  call    cs:__imp_RegDeleteValueW
0x180015111  mov     rcx, [rsp+58h+hKey]; hKey
0x180015116  call    cs:__imp_RegCloseKey
0x18001511c  xor     eax, eax
0x18001511e  add     rsp, 58h
0x180015122  retn
```
