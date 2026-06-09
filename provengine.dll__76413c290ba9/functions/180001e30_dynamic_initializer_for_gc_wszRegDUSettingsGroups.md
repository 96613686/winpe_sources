# _dynamic_initializer_for__gc_wszRegDUSettingsGroups__

- ea: `0x180001e30`
- end: `0x180001eae`
- name: `_dynamic_initializer_for__gc_wszRegDUSettingsGroups__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001e30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e7b`

## string_xrefs

- `0x180001e97`: `OSData\Software\Microsoft\Multivariant\DeviceUpdate\SettingsGroupsToApply`
- `0x180001e8e`: `Software\Microsoft\Multivariant\DeviceUpdate\SettingsGroupsToApply`

## pseudocode

```c
const unsigned __int16 *dynamic_initializer_for__gc_wszRegDUSettingsGroups__()
{
  const unsigned __int16 *result; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !`MVIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    hKey = 0;
    `MVIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                         HKEY_LOCAL_MACHINE,
                                                         L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                         0,
                                                         0x20119u,
                                                         &hKey) == 0;
    RegCloseKey(hKey);
    `MVIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  result = L"OSData\\Software\\Microsoft\\Multivariant\\DeviceUpdate\\SettingsGroupsToApply";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant\\DeviceUpdate\\SettingsGroupsToApply";
  gc_wszRegDUSettingsGroups = result;
  return result;
}

```

## disassembly

```asm
0x180001e30  sub     rsp, 38h
0x180001e34  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0
0x180001e3b  jnz     short loc_180001E88
0x180001e3d  lea     rax, [rsp+38h+hKey]
0x180001e42  mov     [rsp+38h+hKey], 0
0x180001e4b  mov     r9d, 20119h; samDesired
0x180001e51  mov     [rsp+38h+phkResult], rax; phkResult
0x180001e56  xor     r8d, r8d; ulOptions
0x180001e59  lea     rdx, SubKey
0x180001e60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001e67  call    cs:__imp_RegOpenKeyExW
0x180001e6d  mov     rcx, [rsp+38h+hKey]; hKey
0x180001e72  test    eax, eax
0x180001e74  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA
0x180001e7b  call    cs:__imp_RegCloseKey
0x180001e81  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1
0x180001e88  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA
0x180001e8e  lea     rdx, aSoftwareMicros_3
0x180001e95  test    cl, cl
0x180001e97  lea     rax, aOsdataSoftware_1
0x180001e9e  cmovz   rax, rdx
0x180001ea2  mov     cs:?gc_wszRegDUSettingsGroups@@3PEBGEB, rax
0x180001ea9  add     rsp, 38h
0x180001ead  retn
```
