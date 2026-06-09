# _dynamic_initializer_for__gc_wszRegDUSettingsGroups__

- ea: `0x180002cf0`
- end: `0x180002d6e`
- name: `_dynamic_initializer_for__gc_wszRegDUSettingsGroups__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002cf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d27`

## string_xrefs

- `0x180002d57`: `OSData\Software\Microsoft\Multivariant\DeviceUpdate\SettingsGroupsToApply`
- `0x180002d4e`: `Software\Microsoft\Multivariant\DeviceUpdate\SettingsGroupsToApply`

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
0x180002cf0  sub     rsp, 38h
0x180002cf4  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002cfb  jnz     short loc_180002D48
0x180002cfd  lea     rax, [rsp+38h+hKey]
0x180002d02  mov     [rsp+38h+hKey], 0
0x180002d0b  mov     r9d, 20119h; samDesired
0x180002d11  mov     [rsp+38h+phkResult], rax; phkResult
0x180002d16  xor     r8d, r8d; ulOptions
0x180002d19  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180002d20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002d27  call    cs:__imp_RegOpenKeyExW
0x180002d2d  mov     rcx, [rsp+38h+hKey]; hKey
0x180002d32  test    eax, eax
0x180002d34  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002d3b  call    cs:__imp_RegCloseKey
0x180002d41  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002d48  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002d4e  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Multivariant\\Devi"...
0x180002d55  test    cl, cl
0x180002d57  lea     rax, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Multivaria"...
0x180002d5e  cmovz   rax, rdx
0x180002d62  mov     cs:?gc_wszRegDUSettingsGroups@@3PEBGEB, rax; ushort const * const gc_wszRegDUSettingsGroups
0x180002d69  add     rsp, 38h
0x180002d6d  retn
```
