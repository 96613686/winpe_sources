# DfsGetGlobalRegistrySettings(void)

- ea: `0x140018a50`
- end: `0x140018ada`
- name: `?DfsGetGlobalRegistrySettings@@YAEXZ`
- size: `138`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x140018e88`

## callees

- `0x140018a50`
- `0x140018b08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018a97`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018a97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018aac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018aac`

## string_xrefs

- `0x140018a65`: `System\CurrentControlSet\Services\Dfs\Parameters`

## pseudocode

```c
unsigned __int8 DfsGetGlobalRegistrySettings(void)
{
  unsigned int SiteSupportRefreshIntervalSetting; // eax
  DWORD v2; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v2 = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\Dfs\\Parameters",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          &v2) )
    RegCloseKey(hKey);
  SiteSupportRefreshIntervalSetting = DfsGetSiteSupportRefreshIntervalSetting();
  dword_140071590 = 1;
  dwMilliseconds = SiteSupportRefreshIntervalSetting - 120000;
  return 1;
}

```

## disassembly

```asm
0x140018a50  mov     r11, rsp
0x140018a53  sub     rsp, 58h
0x140018a57  and     qword ptr [r11+10h], 0
0x140018a5c  lea     rax, [r11+8]
0x140018a60  and     [rsp+58h+arg_0], 0
0x140018a65  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Df"...
0x140018a6c  mov     [r11-18h], rax
0x140018a70  xor     r9d, r9d; lpClass
0x140018a73  lea     rax, [r11+10h]
0x140018a77  xor     r8d, r8d; Reserved
0x140018a7a  mov     [r11-20h], rax
0x140018a7e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018a85  and     qword ptr [r11-28h], 0
0x140018a8a  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x140018a92  and     [rsp+58h+var_38], 0
0x140018a97  call    cs:__imp_RegCreateKeyExW
0x140018a9e  nop     dword ptr [rax+rax+00h]
0x140018aa3  test    eax, eax
0x140018aa5  jnz     short loc_140018AB8
0x140018aa7  mov     rcx, [rsp+58h+hKey]; hKey
0x140018aac  call    cs:__imp_RegCloseKey
0x140018ab3  nop     dword ptr [rax+rax+00h]
0x140018ab8  call    ?DfsGetSiteSupportRefreshIntervalSetting@@YAKXZ; DfsGetSiteSupportRefreshIntervalSetting(void)
0x140018abd  sub     eax, 1D4C0h
0x140018ac2  mov     cs:dword_140071590, 1
0x140018acc  mov     cs:dwMilliseconds, eax
0x140018ad2  mov     al, 1
0x140018ad4  add     rsp, 58h
0x140018ad8  retn
```
