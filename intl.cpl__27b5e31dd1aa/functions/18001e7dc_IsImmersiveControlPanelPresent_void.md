# IsImmersiveControlPanelPresent(void)

- ea: `0x18001e7dc`
- end: `0x18001e8b7`
- name: `?IsImmersiveControlPanelPresent@@YA_NXZ`
- size: `219`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fcac`

## callees

- `0x18001e7dc`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e82c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e82c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e876`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e876`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e88c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e88c`

## pseudocode

```c
bool IsImmersiveControlPanelPresent(void)
{
  DWORD cbData; // [rsp+30h] [rbp-138h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-130h] BYREF
  BYTE Data[272]; // [rsp+40h] [rbp-128h] BYREF

  if ( !g_fImmersiveControlPanelChecked )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\SystemSettings", 0, 0x20019u, &hKey) )
    {
      memset_0(Data, 0, 0x106u);
      cbData = 262;
      if ( !RegQueryValueExW(hKey, L"SystemSettingsAUMID", 0, 0, Data, &cbData) )
        g_fImmersiveControlPanelPresent = 1;
      RegCloseKey(hKey);
    }
    g_fImmersiveControlPanelChecked = 1;
  }
  return g_fImmersiveControlPanelPresent;
}

```

## disassembly

```asm
0x18001e7dc  sub     rsp, 168h
0x18001e7e3  mov     rax, cs:__security_cookie
0x18001e7ea  xor     rax, rsp
0x18001e7ed  mov     [rsp+168h+var_18], rax
0x18001e7f5  cmp     cs:?g_fImmersiveControlPanelChecked@@3_NA, 0; bool g_fImmersiveControlPanelChecked
0x18001e7fc  jnz     loc_18001E899
0x18001e802  lea     rax, [rsp+168h+hKey]
0x18001e807  mov     [rsp+168h+hKey], 0
0x18001e810  mov     r9d, 20019h; samDesired
0x18001e816  mov     [rsp+168h+phkResult], rax; phkResult
0x18001e81b  xor     r8d, r8d; ulOptions
0x18001e81e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\SystemSettings"
0x18001e825  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e82c  call    cs:__imp_RegOpenKeyExW
0x18001e832  test    eax, eax
0x18001e834  jnz     short loc_18001E892
0x18001e836  xor     edx, edx; Val
0x18001e838  lea     rcx, [rsp+168h+Data]; void *
0x18001e83d  mov     r8d, 106h; Size
0x18001e843  call    memset_0
0x18001e848  mov     rcx, [rsp+168h+hKey]; hKey
0x18001e84d  lea     rax, [rsp+168h+cbData]
0x18001e852  mov     [rsp+168h+lpcbData], rax; lpcbData
0x18001e857  lea     rdx, aSystemsettings; "SystemSettingsAUMID"
0x18001e85e  lea     rax, [rsp+168h+Data]
0x18001e863  mov     [rsp+168h+cbData], 106h
0x18001e86b  xor     r9d, r9d; lpType
0x18001e86e  mov     [rsp+168h+phkResult], rax; lpData
0x18001e873  xor     r8d, r8d; lpReserved
0x18001e876  call    cs:__imp_RegQueryValueExW
0x18001e87c  test    eax, eax
0x18001e87e  jnz     short loc_18001E887
0x18001e880  mov     cs:?g_fImmersiveControlPanelPresent@@3_NA, 1; bool g_fImmersiveControlPanelPresent
0x18001e887  mov     rcx, [rsp+168h+hKey]; hKey
0x18001e88c  call    cs:__imp_RegCloseKey
0x18001e892  mov     cs:?g_fImmersiveControlPanelChecked@@3_NA, 1; bool g_fImmersiveControlPanelChecked
0x18001e899  mov     al, cs:?g_fImmersiveControlPanelPresent@@3_NA; bool g_fImmersiveControlPanelPresent
0x18001e89f  mov     rcx, [rsp+168h+var_18]
0x18001e8a7  xor     rcx, rsp; StackCookie
0x18001e8aa  call    __security_check_cookie
0x18001e8af  add     rsp, 168h
0x18001e8b6  retn
```
