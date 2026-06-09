# _dynamic_initializer_for__gc_wszRegMultivariantStatus__

- ea: `0x180001d30`
- end: `0x180001dae`
- name: `_dynamic_initializer_for__gc_wszRegMultivariantStatus__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001d30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001d67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001d67`

## pseudocode

```c
const WCHAR *dynamic_initializer_for__gc_wszRegMultivariantStatus__()
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
  result = L"OSData\\Software\\Microsoft\\Multivariant\\Status";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant\\Status";
  gc_wszRegMultivariantStatus = result;
  return result;
}

```

## disassembly

```asm
0x180001d30  sub     rsp, 38h
0x180001d34  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001d3b  jnz     short loc_180001D88
0x180001d3d  lea     rax, [rsp+38h+hKey]
0x180001d42  mov     [rsp+38h+hKey], 0
0x180001d4b  mov     r9d, 20119h; samDesired
0x180001d51  mov     [rsp+38h+phkResult], rax; phkResult
0x180001d56  xor     r8d, r8d; ulOptions
0x180001d59  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180001d60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001d67  call    cs:__imp_RegOpenKeyExW
0x180001d6d  mov     rcx, [rsp+38h+hKey]; hKey
0x180001d72  test    eax, eax
0x180001d74  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001d7b  call    cs:__imp_RegCloseKey
0x180001d81  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001d88  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001d8e  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Multivariant\\Stat"...
0x180001d95  test    cl, cl
0x180001d97  lea     rax, aOsdataSoftware; "OSData\\Software\\Microsoft\\Multivaria"...
0x180001d9e  cmovz   rax, rdx
0x180001da2  mov     cs:?gc_wszRegMultivariantStatus@@3PEBGEB, rax; ushort const * const gc_wszRegMultivariantStatus
0x180001da9  add     rsp, 38h
0x180001dad  retn
```
