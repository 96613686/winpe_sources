# _dynamic_initializer_for__gc_wszRegCellularEmulator__

- ea: `0x180001c10`
- end: `0x180001c8e`
- name: `_dynamic_initializer_for__gc_wszRegCellularEmulator__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001c5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001c5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001c47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001c47`

## pseudocode

```c
const WCHAR *dynamic_initializer_for__gc_wszRegCellularEmulator__()
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
  result = L"OSData\\Software\\Microsoft\\Multivariant\\CellularEmulator";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant\\CellularEmulator";
  gc_wszRegCellularEmulator = result;
  return result;
}

```

## disassembly

```asm
0x180001c10  sub     rsp, 38h
0x180001c14  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001c1b  jnz     short loc_180001C68
0x180001c1d  lea     rax, [rsp+38h+hKey]
0x180001c22  mov     [rsp+38h+hKey], 0
0x180001c2b  mov     r9d, 20119h; samDesired
0x180001c31  mov     [rsp+38h+phkResult], rax; phkResult
0x180001c36  xor     r8d, r8d; ulOptions
0x180001c39  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180001c40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001c47  call    cs:__imp_RegOpenKeyExW
0x180001c4d  mov     rcx, [rsp+38h+hKey]; hKey
0x180001c52  test    eax, eax
0x180001c54  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001c5b  call    cs:__imp_RegCloseKey
0x180001c61  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001c68  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001c6e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Multivariant\\Cell"...
0x180001c75  test    cl, cl
0x180001c77  lea     rax, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Multivaria"...
0x180001c7e  cmovz   rax, rdx
0x180001c82  mov     cs:?gc_wszRegCellularEmulator@@3PEBGEB, rax; ushort const * const gc_wszRegCellularEmulator
0x180001c89  add     rsp, 38h
0x180001c8d  retn
```
