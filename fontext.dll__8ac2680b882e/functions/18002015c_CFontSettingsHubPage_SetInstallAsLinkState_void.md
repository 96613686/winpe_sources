# CFontSettingsHubPage::_SetInstallAsLinkState(void)

- ea: `0x18002015c`
- end: `0x1800201ef`
- name: `?_SetInstallAsLinkState@CFontSettingsHubPage@@AEAAXXZ`
- size: `147`
- prototype: `void __fastcall(CFontSettingsHubPage *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001fe20`
- `0x18001ff78`

## callees

- `0x18002015c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800201d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800201d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800201ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800201ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800201e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800201e3`

## string_xrefs

- `0x1800201c4`: `InstallAsLink`

## pseudocode

```c
void __fastcall CFontSettingsHubPage::_SetInstallAsLinkState(const BYTE *this)
{
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Font Management",
          0,
          0,
          0,
          2u,
          0,
          &hKey,
          0) )
  {
    RegSetValueExW(hKey, L"InstallAsLink", 0, 4u, this + 36, 4u);
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18002015c  mov     r11, rsp
0x18002015f  push    rbx
0x180020160  sub     rsp, 50h
0x180020164  mov     qword ptr [r11-18h], 0
0x18002016c  lea     rax, [r11+10h]
0x180020170  mov     [r11-20h], rax
0x180020174  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002017b  mov     qword ptr [r11-28h], 0
0x180020183  mov     rbx, rcx
0x180020186  mov     [rsp+58h+samDesired], 2; samDesired
0x18002018e  xor     r9d, r9d; lpClass
0x180020191  xor     r8d, r8d; Reserved
0x180020194  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002019c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800201a3  mov     qword ptr [r11+10h], 0
0x1800201ab  call    cs:__imp_RegCreateKeyExW
0x1800201b1  test    eax, eax
0x1800201b3  jnz     short loc_1800201E9
0x1800201b5  mov     rcx, [rsp+58h+hKey]; hKey
0x1800201ba  lea     rax, [rbx+24h]
0x1800201be  mov     r9d, 4; dwType
0x1800201c4  lea     rdx, ValueName; "InstallAsLink"
0x1800201cb  mov     [rsp+58h+samDesired], r9d; cbData
0x1800201d0  xor     r8d, r8d; Reserved
0x1800201d3  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800201d8  call    cs:__imp_RegSetValueExW
0x1800201de  mov     rcx, [rsp+58h+hKey]; hKey
0x1800201e3  call    cs:__imp_RegCloseKey
0x1800201e9  add     rsp, 50h
0x1800201ed  pop     rbx
0x1800201ee  retn
```
