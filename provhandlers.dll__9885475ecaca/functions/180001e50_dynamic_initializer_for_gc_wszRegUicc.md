# _dynamic_initializer_for__gc_wszRegUicc__

- ea: `0x180001e50`
- end: `0x180001ece`
- name: `_dynamic_initializer_for__gc_wszRegUicc__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001e50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e87`

## pseudocode

```c
const WCHAR *dynamic_initializer_for__gc_wszRegUicc__()
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
  result = L"OSData\\Software\\Microsoft\\Multivariant\\UICC";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant\\UICC";
  gc_wszRegUicc = result;
  return result;
}

```

## disassembly

```asm
0x180001e50  sub     rsp, 38h
0x180001e54  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001e5b  jnz     short loc_180001EA8
0x180001e5d  lea     rax, [rsp+38h+hKey]
0x180001e62  mov     [rsp+38h+hKey], 0
0x180001e6b  mov     r9d, 20119h; samDesired
0x180001e71  mov     [rsp+38h+phkResult], rax; phkResult
0x180001e76  xor     r8d, r8d; ulOptions
0x180001e79  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180001e80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001e87  call    cs:__imp_RegOpenKeyExW
0x180001e8d  mov     rcx, [rsp+38h+hKey]; hKey
0x180001e92  test    eax, eax
0x180001e94  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001e9b  call    cs:__imp_RegCloseKey
0x180001ea1  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001ea8  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001eae  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Multivariant\\UICC"
0x180001eb5  test    cl, cl
0x180001eb7  lea     rax, aOsdataSoftware_3; "OSData\\Software\\Microsoft\\Multivaria"...
0x180001ebe  cmovz   rax, rdx
0x180001ec2  mov     cs:?gc_wszRegUicc@@3PEBGEB, rax; ushort const * const gc_wszRegUicc
0x180001ec9  add     rsp, 38h
0x180001ecd  retn
```
