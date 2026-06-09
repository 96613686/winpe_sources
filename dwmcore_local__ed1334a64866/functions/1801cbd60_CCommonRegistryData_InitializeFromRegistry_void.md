# CCommonRegistryData::InitializeFromRegistry(void)

- ea: `0x1801cbd60`
- end: `0x1801cbe11`
- name: `?InitializeFromRegistry@CCommonRegistryData@@SAJXZ`
- size: `177`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180205d70`

## callees

- `0x1801cbd60`
- `0x1801cbe18`
- `0x180275c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801cbd96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801cbd96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801cbe03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801cbe03`

## pseudocode

```c
__int64 CCommonRegistryData::InitializeFromRegistry(void)
{
  unsigned int v1; // [rsp+40h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF

  hKey = 0;
  CCommonRegistryData::InitializeDWMKeysFromRegistry();
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Avalon.Graphics", 0, 1u, &hKey) )
  {
    v1 = 0;
    RegReadDWORD(hKey, L"UseD3DDebugLayer", &v1);
    v1 = 0;
    if ( RegReadDWORD(hKey, L"Force10Level9", &v1) )
      CCommonRegistryData::m_fForce10Level9 = v1;
    v1 = 0;
    RegReadDWORD(hKey, L"Force10OnWDDM1_0", &v1);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1801cbd60  push    rbp
0x1801cbd62  mov     rbp, rsp
0x1801cbd65  sub     rsp, 30h
0x1801cbd69  mov     [rbp+hKey], 0
0x1801cbd71  call    ?InitializeDWMKeysFromRegistry@CCommonRegistryData@@CAXXZ; CCommonRegistryData::InitializeDWMKeysFromRegistry(void)
0x1801cbd76  lea     rax, [rbp+hKey]
0x1801cbd7a  mov     r9d, 1; samDesired
0x1801cbd80  xor     r8d, r8d; ulOptions
0x1801cbd83  mov     [rsp+30h+phkResult], rax; phkResult
0x1801cbd88  lea     rdx, SubKey; "Software\\Microsoft\\Avalon.Graphics"
0x1801cbd8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801cbd96  call    cs:__imp_RegOpenKeyExW
0x1801cbd9c  test    eax, eax
0x1801cbd9e  jnz     short loc_1801CBDFA
0x1801cbda0  mov     rcx, [rbp+hKey]; HKEY
0x1801cbda4  lea     r8, [rbp+arg_0]; unsigned int *
0x1801cbda8  lea     rdx, aUsed3ddebuglay; "UseD3DDebugLayer"
0x1801cbdaf  mov     [rbp+arg_0], eax
0x1801cbdb2  call    ?RegReadDWORD@@YA_NPEAUHKEY__@@PEBGPEAK@Z; RegReadDWORD(HKEY__ *,ushort const *,ulong *)
0x1801cbdb7  mov     rcx, [rbp+hKey]; HKEY
0x1801cbdbb  lea     r8, [rbp+arg_0]; unsigned int *
0x1801cbdbf  lea     rdx, aForce10level9; "Force10Level9"
0x1801cbdc6  mov     [rbp+arg_0], 0
0x1801cbdcd  call    ?RegReadDWORD@@YA_NPEAUHKEY__@@PEBGPEAK@Z; RegReadDWORD(HKEY__ *,ushort const *,ulong *)
0x1801cbdd2  test    al, al
0x1801cbdd4  jz      short loc_1801CBDDF
0x1801cbdd6  mov     eax, [rbp+arg_0]
0x1801cbdd9  mov     cs:?m_fForce10Level9@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fForce10Level9
0x1801cbddf  mov     rcx, [rbp+hKey]; HKEY
0x1801cbde3  lea     r8, [rbp+arg_0]; unsigned int *
0x1801cbde7  lea     rdx, aForce10onwddm1; "Force10OnWDDM1_0"
0x1801cbdee  mov     [rbp+arg_0], 0
0x1801cbdf5  call    ?RegReadDWORD@@YA_NPEAUHKEY__@@PEBGPEAK@Z; RegReadDWORD(HKEY__ *,ushort const *,ulong *)
0x1801cbdfa  mov     rcx, [rbp+hKey]; hKey
0x1801cbdfe  test    rcx, rcx
0x1801cbe01  jz      short loc_1801CBE09
0x1801cbe03  call    cs:__imp_RegCloseKey
0x1801cbe09  xor     eax, eax
0x1801cbe0b  add     rsp, 30h
0x1801cbe0f  pop     rbp
0x1801cbe10  retn
```
