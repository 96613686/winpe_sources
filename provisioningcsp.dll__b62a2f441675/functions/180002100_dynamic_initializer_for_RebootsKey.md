# _dynamic_initializer_for__RebootsKey__

- ea: `0x180002100`
- end: `0x18000218b`
- name: `_dynamic_initializer_for__RebootsKey__`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002100`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002151`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002151`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002137`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002137`

## pseudocode

```c
const WCHAR *dynamic_initializer_for__RebootsKey__()
{
  const WCHAR *result; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !`ProvIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    hKey = 0;
    `ProvIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                           HKEY_LOCAL_MACHINE,
                                                           L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                           0,
                                                           0x20119u,
                                                           &hKey) == 0;
    RegCloseKey(hKey);
    `ProvIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  result = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\ReloadsForced";
  if ( !`ProvIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"SOFTWARE\\Microsoft\\Provisioning\\ReloadsForced";
  lpSubKey = result;
  return result;
}

```

## disassembly

```asm
0x180002100  sub     rsp, 38h
0x180002104  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18000210b  jnz     short loc_180002164
0x18000210d  lea     rax, [rsp+38h+hKey]
0x180002112  mov     [rsp+38h+hKey], 0
0x18000211b  mov     r9d, 20119h; samDesired
0x180002121  mov     [rsp+38h+phkResult], rax; phkResult
0x180002126  xor     r8d, r8d; ulOptions
0x180002129  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x180002130  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002137  call    cs:__imp_RegOpenKeyExW
0x18000213e  nop     dword ptr [rax+rax+00h]
0x180002143  mov     rcx, [rsp+38h+hKey]; hKey
0x180002148  test    eax, eax
0x18000214a  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180002151  call    cs:__imp_RegCloseKey
0x180002158  nop     dword ptr [rax+rax+00h]
0x18000215d  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180002164  mov     cl, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18000216a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Provisioning\\Relo"...
0x180002171  test    cl, cl
0x180002173  lea     rax, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18000217a  cmovz   rax, rdx
0x18000217e  mov     cs:lpSubKey, rax
0x180002185  add     rsp, 38h
0x180002189  retn
```
