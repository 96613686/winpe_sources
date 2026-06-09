# _dynamic_initializer_for__c_provAgentKey__

- ea: `0x180002b20`
- end: `0x180002b9e`
- name: `_dynamic_initializer_for__c_provAgentKey__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002b20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002b6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002b6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002b57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002b57`

## string_xrefs

- `0x180002b87`: `OSData\Software\Microsoft\Provisioning\Agent`
- `0x180002b7e`: `Software\Microsoft\Provisioning\Agent`

## pseudocode

```c
const WCHAR *dynamic_initializer_for__c_provAgentKey__()
{
  const WCHAR *result; // rax
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
  result = L"OSData\\Software\\Microsoft\\Provisioning\\Agent";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Provisioning\\Agent";
  c_provAgentKey = result;
  return result;
}

```

## disassembly

```asm
0x180002b20  sub     rsp, 38h
0x180002b24  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002b2b  jnz     short loc_180002B78
0x180002b2d  lea     rax, [rsp+38h+hKey]
0x180002b32  mov     [rsp+38h+hKey], 0
0x180002b3b  mov     r9d, 20119h; samDesired
0x180002b41  mov     [rsp+38h+phkResult], rax; phkResult
0x180002b46  xor     r8d, r8d; ulOptions
0x180002b49  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180002b50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002b57  call    cs:__imp_RegOpenKeyExW
0x180002b5d  mov     rcx, [rsp+38h+hKey]; hKey
0x180002b62  test    eax, eax
0x180002b64  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002b6b  call    cs:__imp_RegCloseKey
0x180002b71  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002b78  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002b7e  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Provisioning\\Agen"...
0x180002b85  test    cl, cl
0x180002b87  lea     rax, aOsdataSoftware_7; "OSData\\Software\\Microsoft\\Provisioni"...
0x180002b8e  cmovz   rax, rdx
0x180002b92  mov     cs:?c_provAgentKey@@3PEBGEB, rax; ushort const * const c_provAgentKey
0x180002b99  add     rsp, 38h
0x180002b9d  retn
```
