# ControlPanelRegKey::InitRegData(void)

- ea: `0x1800f6c00`
- end: `0x1800f6c41`
- name: `?InitRegData@ControlPanelRegKey@@SAXXZ`
- size: `65`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f67e8`

## callees

- `0x1800f6c00`
- `0x1802d84d8`
- `0x1802d8a24`
- `0x1802d8aa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6c2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6c2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802fd483`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802fd483`

## pseudocode

```c
void ControlPanelRegKey::InitRegData(void)
{
  const unsigned __int16 *v0; // rdx
  unsigned int v1; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Direct3D\\Direct2D", 0, 1u, &hKey) )
  {
    if ( AppInExeList() )
    {
      ControlPanelRegKey::s_useControlPanelSettings = 1;
      ControlPanelRegKey::s_forceOnDebugLayer = RegDWORDPresentAndNonZero(hKey, L"DebugLayerForceOn");
      ControlPanelRegKey::s_appControlled = RegDWORDPresentAndNonZero(hKey, L"DebugLayerAppControlled");
      v1 = 0;
      if ( RegDWORD(hKey, v0, &v1) && (v1 < 2 || v1 - 2 <= 1) )
        ControlPanelRegKey::s_debugLevel = v1;
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x1800f6c00  sub     rsp, 38h
0x1800f6c04  lea     rax, [rsp+38h+hKey]
0x1800f6c09  mov     [rsp+38h+hKey], 0
0x1800f6c12  mov     r9d, 1; samDesired
0x1800f6c18  mov     [rsp+38h+phkResult], rax; phkResult
0x1800f6c1d  xor     r8d, r8d; ulOptions
0x1800f6c20  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Direct3D\\Direct2D"
0x1800f6c27  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800f6c2e  call    cs:__imp_RegOpenKeyExW
0x1800f6c34  test    eax, eax
0x1800f6c36  jz      loc_1802FD406
0x1800f6c3c  add     rsp, 38h
0x1800f6c40  retn
0x1802fd406  call    ?AppInExeList@@YA_NXZ; AppInExeList(void)
0x1802fd40b  test    al, al
0x1802fd40d  jz      short loc_1802FD47E
0x1802fd40f  mov     rcx, [rsp+38h+hKey]; HKEY
0x1802fd414  lea     rdx, aDebuglayerforc; "DebugLayerForceOn"
0x1802fd41b  mov     cs:?s_useControlPanelSettings@ControlPanelRegKey@@0_NA, 1; bool ControlPanelRegKey::s_useControlPanelSettings
0x1802fd422  call    ?RegDWORDPresentAndNonZero@@YA_NPEAUHKEY__@@PEBG@Z; RegDWORDPresentAndNonZero(HKEY__ *,ushort const *)
0x1802fd427  mov     rcx, [rsp+38h+hKey]; HKEY
0x1802fd42c  lea     rdx, aDebuglayerappc; "DebugLayerAppControlled"
0x1802fd433  mov     cs:?s_forceOnDebugLayer@ControlPanelRegKey@@0_NA, al; bool ControlPanelRegKey::s_forceOnDebugLayer
0x1802fd439  call    ?RegDWORDPresentAndNonZero@@YA_NPEAUHKEY__@@PEBG@Z; RegDWORDPresentAndNonZero(HKEY__ *,ushort const *)
0x1802fd43e  mov     rcx, [rsp+38h+hKey]; HKEY
0x1802fd443  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x1802fd448  mov     cs:?s_appControlled@ControlPanelRegKey@@0_NA, al; bool ControlPanelRegKey::s_appControlled
0x1802fd44e  mov     [rsp+38h+arg_0], 0
0x1802fd456  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBGPEAK@Z; RegDWORD(HKEY__ *,ushort const *,ulong *)
0x1802fd45b  test    al, al
0x1802fd45d  jz      short loc_1802FD47E
0x1802fd45f  mov     edx, [rsp+38h+arg_0]
0x1802fd463  mov     ecx, edx
0x1802fd465  test    edx, edx
0x1802fd467  jz      short loc_1802FD478
0x1802fd469  sub     ecx, 1
0x1802fd46c  jz      short loc_1802FD478
0x1802fd46e  sub     ecx, 1
0x1802fd471  jz      short loc_1802FD478
0x1802fd473  cmp     ecx, 1
0x1802fd476  jnz     short loc_1802FD47E
0x1802fd478  mov     cs:?s_debugLevel@ControlPanelRegKey@@0W4D2D1_DEBUG_LEVEL@@A, edx; D2D1_DEBUG_LEVEL ControlPanelRegKey::s_debugLevel
0x1802fd47e  mov     rcx, [rsp+38h+hKey]; hKey
0x1802fd483  call    cs:__imp_RegCloseKey
0x1802fd489  nop
0x1802fd48a  jmp     loc_1800F6C3C
```
