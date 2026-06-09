# _dynamic_initializer_for__gc_wszRegUICandidates__

- ea: `0x180001dc0`
- end: `0x180001e3e`
- name: `_dynamic_initializer_for__gc_wszRegUICandidates__`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001df7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001df7`

## pseudocode

```c
const wchar_t *dynamic_initializer_for__gc_wszRegUICandidates__()
{
  const wchar_t *result; // rax
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
  result = L"OSData\\Software\\Microsoft\\Multivariant\\UI\\Candidates";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant\\UI\\Candidates";
  gc_wszRegUICandidates = (void *)result;
  return result;
}

```

## disassembly

```asm
0x180001dc0  sub     rsp, 38h
0x180001dc4  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001dcb  jnz     short loc_180001E18
0x180001dcd  lea     rax, [rsp+38h+hKey]
0x180001dd2  mov     [rsp+38h+hKey], 0
0x180001ddb  mov     r9d, 20119h; samDesired
0x180001de1  mov     [rsp+38h+phkResult], rax; phkResult
0x180001de6  xor     r8d, r8d; ulOptions
0x180001de9  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180001df0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001df7  call    cs:__imp_RegOpenKeyExW
0x180001dfd  mov     rcx, [rsp+38h+hKey]; hKey
0x180001e02  test    eax, eax
0x180001e04  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001e0b  call    cs:__imp_RegCloseKey
0x180001e11  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180001e18  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180001e1e  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Multivariant\\UI\\"...
0x180001e25  test    cl, cl
0x180001e27  lea     rax, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Multivaria"...
0x180001e2e  cmovz   rax, rdx
0x180001e32  mov     cs:?gc_wszRegUICandidates@@3PEBGEB, rax; ushort const * const gc_wszRegUICandidates
0x180001e39  add     rsp, 38h
0x180001e3d  retn
```
