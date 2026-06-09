# MVIsStateSeparationEnabled(void)

- ea: `0x18000882c`
- end: `0x18000889c`
- name: `?MVIsStateSeparationEnabled@@YA_NXZ`
- size: `112`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800020a0`

## callees

- `0x18000882c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000887d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000887d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008863`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008863`

## pseudocode

```c
char MVIsStateSeparationEnabled(void)
{
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
  return `MVIsStateSeparationEnabled'::`2'::s_Redirection;
}

```

## disassembly

```asm
0x18000882c  sub     rsp, 38h
0x180008830  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180008837  jnz     short loc_180008890
0x180008839  lea     rax, [rsp+38h+hKey]
0x18000883e  mov     [rsp+38h+hKey], 0
0x180008847  mov     r9d, 20119h; samDesired
0x18000884d  mov     [rsp+38h+phkResult], rax; phkResult
0x180008852  xor     r8d, r8d; ulOptions
0x180008855  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x18000885c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008863  call    cs:__imp_RegOpenKeyExW
0x18000886a  nop     dword ptr [rax+rax+00h]
0x18000886f  mov     rcx, [rsp+38h+hKey]; hKey
0x180008874  test    eax, eax
0x180008876  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18000887d  call    cs:__imp_RegCloseKey
0x180008884  nop     dword ptr [rax+rax+00h]
0x180008889  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180008890  mov     al, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180008896  add     rsp, 38h
0x18000889a  retn
```
