# _dynamic_initializer_for__gc_wszRegMultivariantStatus__

- ea: `0x180002e10`
- end: `0x180002e8e`
- name: `_dynamic_initializer_for__gc_wszRegMultivariantStatus__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002e10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e47`

## pseudocode

```c
const unsigned __int16 *dynamic_initializer_for__gc_wszRegMultivariantStatus__()
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
  result = L"OSData\\Software\\Microsoft\\Multivariant\\Status";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant\\Status";
  gc_wszRegMultivariantStatus = result;
  return result;
}

```

## disassembly

```asm
0x180002e10  sub     rsp, 38h
0x180002e14  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002e1b  jnz     short loc_180002E68
0x180002e1d  lea     rax, [rsp+38h+hKey]
0x180002e22  mov     [rsp+38h+hKey], 0
0x180002e2b  mov     r9d, 20119h; samDesired
0x180002e31  mov     [rsp+38h+phkResult], rax; phkResult
0x180002e36  xor     r8d, r8d; ulOptions
0x180002e39  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180002e40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002e47  call    cs:__imp_RegOpenKeyExW
0x180002e4d  mov     rcx, [rsp+38h+hKey]; hKey
0x180002e52  test    eax, eax
0x180002e54  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002e5b  call    cs:__imp_RegCloseKey
0x180002e61  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002e68  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002e6e  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Multivariant\\Stat"...
0x180002e75  test    cl, cl
0x180002e77  lea     rax, aOsdataSoftware; "OSData\\Software\\Microsoft\\Multivaria"...
0x180002e7e  cmovz   rax, rdx
0x180002e82  mov     cs:?gc_wszRegMultivariantStatus@@3PEBGEB, rax; ushort const * const gc_wszRegMultivariantStatus
0x180002e89  add     rsp, 38h
0x180002e8d  retn
```
