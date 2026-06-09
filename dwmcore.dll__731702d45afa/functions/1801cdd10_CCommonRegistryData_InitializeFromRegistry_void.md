# CCommonRegistryData::InitializeFromRegistry(void)

- ea: `0x1801cdd10`
- end: `0x1801cddc1`
- name: `?InitializeFromRegistry@CCommonRegistryData@@SAJXZ`
- size: `177`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180205d90`

## callees

- `0x1801cdd10`
- `0x1801cddc8`
- `0x180275c50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801cdd46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801cdd46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801cddb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801cddb3`

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
0x1801cdd10  push    rbp
0x1801cdd12  mov     rbp, rsp
0x1801cdd15  sub     rsp, 30h
0x1801cdd19  mov     [rbp+hKey], 0
0x1801cdd21  call    ?InitializeDWMKeysFromRegistry@CCommonRegistryData@@CAXXZ; CCommonRegistryData::InitializeDWMKeysFromRegistry(void)
0x1801cdd26  lea     rax, [rbp+hKey]
0x1801cdd2a  mov     r9d, 1; samDesired
0x1801cdd30  xor     r8d, r8d; ulOptions
0x1801cdd33  mov     [rsp+30h+phkResult], rax; phkResult
0x1801cdd38  lea     rdx, SubKey; "Software\\Microsoft\\Avalon.Graphics"
0x1801cdd3f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801cdd46  call    cs:__imp_RegOpenKeyExW
0x1801cdd4c  test    eax, eax
0x1801cdd4e  jnz     short loc_1801CDDAA
0x1801cdd50  mov     rcx, [rbp+hKey]; HKEY
0x1801cdd54  lea     r8, [rbp+arg_0]; unsigned int *
0x1801cdd58  lea     rdx, aUsed3ddebuglay; "UseD3DDebugLayer"
0x1801cdd5f  mov     [rbp+arg_0], eax
0x1801cdd62  call    ?RegReadDWORD@@YA_NPEAUHKEY__@@PEBGPEAK@Z; RegReadDWORD(HKEY__ *,ushort const *,ulong *)
0x1801cdd67  mov     rcx, [rbp+hKey]; HKEY
0x1801cdd6b  lea     r8, [rbp+arg_0]; unsigned int *
0x1801cdd6f  lea     rdx, aForce10level9; "Force10Level9"
0x1801cdd76  mov     [rbp+arg_0], 0
0x1801cdd7d  call    ?RegReadDWORD@@YA_NPEAUHKEY__@@PEBGPEAK@Z; RegReadDWORD(HKEY__ *,ushort const *,ulong *)
0x1801cdd82  test    al, al
0x1801cdd84  jz      short loc_1801CDD8F
0x1801cdd86  mov     eax, [rbp+arg_0]
0x1801cdd89  mov     cs:?m_fForce10Level9@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fForce10Level9
0x1801cdd8f  mov     rcx, [rbp+hKey]; HKEY
0x1801cdd93  lea     r8, [rbp+arg_0]; unsigned int *
0x1801cdd97  lea     rdx, aForce10onwddm1; "Force10OnWDDM1_0"
0x1801cdd9e  mov     [rbp+arg_0], 0
0x1801cdda5  call    ?RegReadDWORD@@YA_NPEAUHKEY__@@PEBGPEAK@Z; RegReadDWORD(HKEY__ *,ushort const *,ulong *)
0x1801cddaa  mov     rcx, [rbp+hKey]; hKey
0x1801cddae  test    rcx, rcx
0x1801cddb1  jz      short loc_1801CDDB9
0x1801cddb3  call    cs:__imp_RegCloseKey
0x1801cddb9  xor     eax, eax
0x1801cddbb  add     rsp, 30h
0x1801cddbf  pop     rbp
0x1801cddc0  retn
```
