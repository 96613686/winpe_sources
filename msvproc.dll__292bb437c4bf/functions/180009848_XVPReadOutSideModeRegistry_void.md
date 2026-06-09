# XVPReadOutSideModeRegistry(void)

- ea: `0x180009848`
- end: `0x18000992f`
- name: `?XVPReadOutSideModeRegistry@@YAIXZ`
- size: `231`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011a8c`
- `0x180060600`

## callees

- `0x180009848`
- `0x180009940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000990c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000990c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800098cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800098cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800098fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800098fd`

## string_xrefs

- `0x180009851`: `EnableOutsideModeFeature`
- `0x1800098f1`: `EnableOutsideModeFeature`
- `0x18000986f`: `OEMOutsideModeEnableByDefault`

## pseudocode

```c
_BOOL8 XVPReadOutSideModeRegistry(void)
{
  BOOL v0; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v0 = (unsigned int)AccessRegistryInt(
                       L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP",
                       L"EnableOutsideModeFeature",
                       0)
    || (unsigned int)AccessRegistryInt(
                       L"Software\\Microsoft\\Windows Media Foundation\\Platform",
                       L"OEMOutsideModeEnableByDefault",
                       0);
  hKey = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\VideoSettings", 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"EnableOutsideModeFeature", 0, &Type, (LPBYTE)&Data, &cbData) )
      v0 = Data != 0;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180009848  push    rbx
0x18000984a  sub     rsp, 30h
0x18000984e  xor     r8d, r8d; int
0x180009851  lea     rdx, aEnableoutsidem; "EnableOutsideModeFeature"
0x180009858  lea     rcx, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x18000985f  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x180009864  test    eax, eax
0x180009866  jnz     loc_18000991A
0x18000986c  xor     r8d, r8d; int
0x18000986f  lea     rdx, aOemoutsidemode_0; "OEMOutsideModeEnableByDefault"
0x180009876  lea     rcx, aSoftwareMicros_2; "Software\\Microsoft\\Windows Media Foun"...
0x18000987d  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x180009882  test    eax, eax
0x180009884  jnz     loc_18000991A
0x18000988a  xor     ebx, ebx
0x18000988c  mov     eax, 4
0x180009891  mov     [rsp+38h+hKey], 0
0x18000989a  mov     [rsp+38h+Type], eax
0x18000989e  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800098a5  mov     [rsp+38h+cbData], eax
0x1800098a9  mov     r9d, 1; samDesired
0x1800098af  lea     rax, [rsp+38h+hKey]
0x1800098b4  mov     [rsp+38h+Data], 0
0x1800098bc  xor     r8d, r8d; ulOptions
0x1800098bf  mov     [rsp+38h+phkResult], rax; phkResult
0x1800098c4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800098cb  call    cs:__imp_RegOpenKeyExW
0x1800098d1  test    eax, eax
0x1800098d3  jnz     short loc_180009912
0x1800098d5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800098da  lea     rax, [rsp+38h+cbData]
0x1800098df  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800098e4  lea     r9, [rsp+38h+Type]; lpType
0x1800098e9  lea     rax, [rsp+38h+Data]
0x1800098ee  xor     r8d, r8d; lpReserved
0x1800098f1  lea     rdx, aEnableoutsidem; "EnableOutsideModeFeature"
0x1800098f8  mov     [rsp+38h+phkResult], rax; lpData
0x1800098fd  call    cs:__imp_RegQueryValueExW
0x180009903  test    eax, eax
0x180009905  jz      short loc_180009924
0x180009907  mov     rcx, [rsp+38h+hKey]; hKey
0x18000990c  call    cs:__imp_RegCloseKey
0x180009912  mov     eax, ebx
0x180009914  add     rsp, 30h
0x180009918  pop     rbx
0x180009919  retn
0x18000991a  mov     ebx, 1
0x18000991f  jmp     loc_18000988C
0x180009924  xor     ebx, ebx
0x180009926  cmp     [rsp+38h+Data], ebx
0x18000992a  setnz   bl
0x18000992d  jmp     short loc_180009907
```
