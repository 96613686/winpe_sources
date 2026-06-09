# ProvIsStateSeparationEnabled(void)

- ea: `0x1800092dc`
- end: `0x18000933f`
- name: `?ProvIsStateSeparationEnabled@@YA_NXZ`
- size: `99`
- prototype: `bool(void)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002060`
- `0x180008050`
- `0x180008900`
- `0x180014cf8`
- `0x180018438`
- `0x180018f74`
- `0x180038b58`
- `0x180039304`
- `0x18003b2b4`
- `0x18003cedc`
- `0x180040480`
- `0x180040fd4`
- `0x180041070`

## callees

- `0x1800092dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009313`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009313`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009327`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009327`

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
0x1800092dc  sub     rsp, 38h
0x1800092e0  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800092e7  jnz     short loc_180009334
0x1800092e9  lea     rax, [rsp+38h+hKey]
0x1800092ee  mov     [rsp+38h+hKey], 0
0x1800092f7  mov     r9d, 20119h; samDesired
0x1800092fd  mov     [rsp+38h+phkResult], rax; phkResult
0x180009302  xor     r8d, r8d; ulOptions
0x180009305  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x18000930c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009313  call    cs:__imp_RegOpenKeyExW
0x180009319  mov     rcx, [rsp+38h+hKey]; hKey
0x18000931e  test    eax, eax
0x180009320  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180009327  call    cs:__imp_RegCloseKey
0x18000932d  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180009334  mov     al, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18000933a  add     rsp, 38h
0x18000933e  retn
```
