# _dynamic_initializer_for__gc_wszRegMultivariant__

- ea: `0x180001ec0`
- end: `0x180001f3e`
- name: `_dynamic_initializer_for__gc_wszRegMultivariant__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001ef7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001ef7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001f0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001f0b`

## pseudocode

```c
const WCHAR *dynamic_initializer_for__gc_wszRegMultivariant__()
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
  result = L"OSData\\Software\\Microsoft\\Multivariant";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant";
  gc_wszRegMultivariant = result;
  return result;
}

```

## disassembly

```asm
0x180001ec0  sub     rsp, 38h
0x180001ec4  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001ecb  jnz     short loc_180001F18
0x180001ecd  lea     rax, [rsp+38h+hKey]
0x180001ed2  mov     [rsp+38h+hKey], 0
0x180001edb  mov     r9d, 20119h; samDesired
0x180001ee1  mov     [rsp+38h+phkResult], rax; phkResult
0x180001ee6  xor     r8d, r8d; ulOptions
0x180001ee9  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180001ef0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001ef7  call    cs:__imp_RegOpenKeyExW
0x180001efd  mov     rcx, [rsp+38h+hKey]; hKey
0x180001f02  test    eax, eax
0x180001f04  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001f0b  call    cs:__imp_RegCloseKey
0x180001f11  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001f18  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001f1e  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Multivariant"
0x180001f25  test    cl, cl
0x180001f27  lea     rax, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Multivaria"...
0x180001f2e  cmovz   rax, rdx
0x180001f32  mov     cs:?gc_wszRegMultivariant@@3PEBGEB, rax; ushort const * const gc_wszRegMultivariant
0x180001f39  add     rsp, 38h
0x180001f3d  retn
```
