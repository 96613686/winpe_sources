# CPIDPlugin::_InitializeGlobalOOBEPKValues(void)

- ea: `0x1800456e4`
- end: `0x1800457e7`
- name: `?_InitializeGlobalOOBEPKValues@CPIDPlugin@@AEAAJXZ`
- size: `259`
- prototype: `__int64 __fastcall(CPIDPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180045310`

## callees

- `0x1800456e4`
- `0x1800b8834`
- `0x1800bf488`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045791`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045791`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800457c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800457c3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004574c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004574c`

## string_xrefs

- `0x1800457ce`: `Failed to create HasOOBERun key in registry. [hr=0x%08X]`
- `0x1800457ad`: `Failed to set HasOOBERun key in registry. [hr=0x%08X]`

## pseudocode

```c
__int64 __fastcall CPIDPlugin::_InitializeGlobalOOBEPKValues(CPIDPlugin *this)
{
  signed int v1; // ebx
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v1 = CBasePlugin::_SetGlobalSettingDWORD(this, L"PRODUCTKEYSTATUS", 0);
  if ( v1 >= 0 )
  {
    hKey = 0;
    v2 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SoftwareProtectionPlatform",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           0);
    v1 = v2;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    if ( v1 < 0 )
    {
      UnattendLogW(1, L"Failed to create HasOOBERun key in registry. [hr=0x%08X]", (unsigned int)v1);
    }
    else
    {
      Data = 1;
      v3 = RegSetValueExW(hKey, L"HasOOBERun", 0, 4u, (const BYTE *)&Data, 4u);
      v1 = v3;
      if ( v3 > 0 )
        v1 = (unsigned __int16)v3 | 0x80070000;
      if ( v1 < 0 )
        UnattendLogW(1, L"Failed to set HasOOBERun key in registry. [hr=0x%08X]", (unsigned int)v1);
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800456e4  push    rbx
0x1800456e6  sub     rsp, 50h
0x1800456ea  xor     r8d, r8d; unsigned int
0x1800456ed  lea     rdx, aProductkeystat; "PRODUCTKEYSTATUS"
0x1800456f4  call    ?_SetGlobalSettingDWORD@CBasePlugin@@IEAAJPEBGK@Z; CBasePlugin::_SetGlobalSettingDWORD(ushort const *,ulong)
0x1800456f9  mov     ebx, eax
0x1800456fb  test    eax, eax
0x1800456fd  js      loc_1800457DF
0x180045703  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18004570c  lea     rax, [rsp+58h+hKey]
0x180045711  mov     [rsp+58h+phkResult], rax; phkResult
0x180045716  lea     rdx, aSoftwareMicros_26; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004571d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180045726  xor     r9d, r9d; lpClass
0x180045729  mov     [rsp+58h+samDesired], 2; samDesired
0x180045731  xor     r8d, r8d; Reserved
0x180045734  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004573b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180045743  mov     [rsp+58h+hKey], 0
0x18004574c  call    cs:__imp_RegCreateKeyExW
0x180045752  mov     ebx, eax
0x180045754  test    eax, eax
0x180045756  jle     short loc_180045761
0x180045758  movzx   ebx, ax
0x18004575b  or      ebx, 80070000h
0x180045761  test    ebx, ebx
0x180045763  js      short loc_1800457CB
0x180045765  mov     rcx, [rsp+58h+hKey]; hKey
0x18004576a  lea     rax, [rsp+58h+Data]
0x18004576f  mov     r9d, 4; dwType
0x180045775  mov     [rsp+58h+Data], 1
0x18004577d  mov     [rsp+58h+samDesired], r9d; cbData
0x180045782  lea     rdx, ValueName; "HasOOBERun"
0x180045789  xor     r8d, r8d; Reserved
0x18004578c  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180045791  call    cs:__imp_RegSetValueExW
0x180045797  mov     ebx, eax
0x180045799  test    eax, eax
0x18004579b  jle     short loc_1800457A6
0x18004579d  movzx   ebx, ax
0x1800457a0  or      ebx, 80070000h
0x1800457a6  test    ebx, ebx
0x1800457a8  jns     short loc_1800457BE
0x1800457aa  mov     r8d, ebx
0x1800457ad  lea     rdx, aFailedToSetHas; "Failed to set HasOOBERun key in registr"...
0x1800457b4  mov     ecx, 1
0x1800457b9  call    UnattendLogW
0x1800457be  mov     rcx, [rsp+58h+hKey]; hKey
0x1800457c3  call    cs:__imp_RegCloseKey
0x1800457c9  jmp     short loc_1800457DF
0x1800457cb  mov     r8d, ebx
0x1800457ce  lea     rdx, aFailedToCreate_3; "Failed to create HasOOBERun key in regi"...
0x1800457d5  mov     ecx, 1
0x1800457da  call    UnattendLogW
0x1800457df  mov     eax, ebx
0x1800457e1  add     rsp, 50h
0x1800457e5  pop     rbx
0x1800457e6  retn
```
