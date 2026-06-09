# ProvIsStateSeparationEnabled(void)

- ea: `0x18001434c`
- end: `0x1800143af`
- name: `?ProvIsStateSeparationEnabled@@YA_NXZ`
- size: `99`
- prototype: `char(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f8d0`
- `0x180011884`
- `0x180016d64`
- `0x180027208`
- `0x180028854`
- `0x180029f08`
- `0x18002be94`
- `0x18002d090`

## callees

- `0x18001434c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014397`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014397`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014383`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014383`

## pseudocode

```c
char ProvIsStateSeparationEnabled(void)
{
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
  return `ProvIsStateSeparationEnabled'::`2'::s_Redirection;
}

```

## disassembly

```asm
0x18001434c  sub     rsp, 38h
0x180014350  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180014357  jnz     short loc_1800143A4
0x180014359  lea     rax, [rsp+38h+hKey]
0x18001435e  mov     [rsp+38h+hKey], 0
0x180014367  mov     r9d, 20119h; samDesired
0x18001436d  mov     [rsp+38h+phkResult], rax; phkResult
0x180014372  xor     r8d, r8d; ulOptions
0x180014375  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x18001437c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014383  call    cs:__imp_RegOpenKeyExW
0x180014389  mov     rcx, [rsp+38h+hKey]; hKey
0x18001438e  test    eax, eax
0x180014390  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180014397  call    cs:__imp_RegCloseKey
0x18001439d  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800143a4  mov     al, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800143aa  add     rsp, 38h
0x1800143ae  retn
```
