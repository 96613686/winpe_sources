# _dynamic_initializer_for__gc_wszRegUicc__

- ea: `0x180002ea0`
- end: `0x180002f1e`
- name: `_dynamic_initializer_for__gc_wszRegUicc__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002ea0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002eeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002eeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002ed7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002ed7`

## pseudocode

```c
const unsigned __int16 *dynamic_initializer_for__gc_wszRegUicc__()
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
  result = L"OSData\\Software\\Microsoft\\Multivariant\\UICC";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant\\UICC";
  gc_wszRegUicc = result;
  return result;
}

```

## disassembly

```asm
0x180002ea0  sub     rsp, 38h
0x180002ea4  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002eab  jnz     short loc_180002EF8
0x180002ead  lea     rax, [rsp+38h+hKey]
0x180002eb2  mov     [rsp+38h+hKey], 0
0x180002ebb  mov     r9d, 20119h; samDesired
0x180002ec1  mov     [rsp+38h+phkResult], rax; phkResult
0x180002ec6  xor     r8d, r8d; ulOptions
0x180002ec9  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180002ed0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002ed7  call    cs:__imp_RegOpenKeyExW
0x180002edd  mov     rcx, [rsp+38h+hKey]; hKey
0x180002ee2  test    eax, eax
0x180002ee4  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002eeb  call    cs:__imp_RegCloseKey
0x180002ef1  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002ef8  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002efe  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Multivariant\\UICC"
0x180002f05  test    cl, cl
0x180002f07  lea     rax, aOsdataSoftware_11; "OSData\\Software\\Microsoft\\Multivaria"...
0x180002f0e  cmovz   rax, rdx
0x180002f12  mov     cs:?gc_wszRegUicc@@3PEBGEB, rax; ushort const * const gc_wszRegUicc
0x180002f19  add     rsp, 38h
0x180002f1d  retn
```
