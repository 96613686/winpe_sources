# CFontManager::_SetSkipSystemFontWarning(void)

- ea: `0x18001f2fc`
- end: `0x18001f395`
- name: `?_SetSkipSystemFontWarning@CFontManager@@AEAAXXZ`
- size: `153`
- prototype: `void __fastcall(CFontManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e168`

## callees

- `0x18001f2fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f37f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f37f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f34b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f34b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f38a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f38a`

## string_xrefs

- `0x18001f370`: `SkipDeleteSystemFontWarning`

## pseudocode

```c
void __fastcall CFontManager::_SetSkipSystemFontWarning(CFontManager *this)
{
  CFontManager *Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = this;
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
    LODWORD(Data) = 1;
    RegSetValueExW(hKey, L"SkipDeleteSystemFontWarning", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18001f2fc  mov     r11, rsp
0x18001f2ff  mov     [r11+8], rcx
0x18001f303  sub     rsp, 58h
0x18001f307  mov     qword ptr [r11-18h], 0
0x18001f30f  lea     rax, [r11+10h]
0x18001f313  mov     [r11-20h], rax
0x18001f317  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001f31e  mov     qword ptr [r11-28h], 0
0x18001f326  xor     r9d, r9d; lpClass
0x18001f329  mov     [rsp+58h+samDesired], 2; samDesired
0x18001f331  xor     r8d, r8d; Reserved
0x18001f334  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001f33b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001f343  mov     qword ptr [r11+10h], 0
0x18001f34b  call    cs:__imp_RegCreateKeyExW
0x18001f351  test    eax, eax
0x18001f353  jnz     short loc_18001F390
0x18001f355  mov     rcx, [rsp+58h+hKey]; hKey
0x18001f35a  lea     r9d, [rax+4]; dwType
0x18001f35e  lea     rax, [rsp+58h+Data]
0x18001f363  mov     [rsp+58h+samDesired], r9d; cbData
0x18001f368  xor     r8d, r8d; Reserved
0x18001f36b  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001f370  lea     rdx, aSkipdeletesyst; "SkipDeleteSystemFontWarning"
0x18001f377  mov     dword ptr [rsp+58h+Data], 1
0x18001f37f  call    cs:__imp_RegSetValueExW
0x18001f385  mov     rcx, [rsp+58h+hKey]; hKey
0x18001f38a  call    cs:__imp_RegCloseKey
0x18001f390  add     rsp, 58h
0x18001f394  retn
```
