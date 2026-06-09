# ScriptSymbol::IsJScript9LegacyEnabled(int *)

- ea: `0x100e3ce7`
- end: `0x100e3dd3`
- name: `?IsJScript9LegacyEnabled@ScriptSymbol@@IAEJPAH@Z`
- size: `236`
- prototype: `HRESULT __thiscall(ScriptSymbol *this, int *isEnabled)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10064a5e`

## callees

- `0x100e3ce7`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100e3d43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100e3da2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100e3d43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100e3da2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100e3d4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100e3dad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100e3d4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100e3dad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100e3d16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100e3d73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100e3d16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100e3d73`

## string_xrefs

- `0x100e3d3b`: `JScriptReplacement`
- `0x100e3d9a`: `JScriptReplacement`

## pseudocode

```c
HRESULT __thiscall ScriptSymbol::IsJScript9LegacyEnabled(ScriptSymbol *this, int *isEnabled)
{
  LSTATUS v2; // esi
  unsigned int v3; // ecx
  BOOL v4; // eax
  unsigned int dwValueType; // [esp+Ch] [ebp-14h] BYREF
  unsigned int dwSize; // [esp+10h] [ebp-10h] BYREF
  unsigned int dwPolicyValueInHKCU; // [esp+14h] [ebp-Ch] BYREF
  unsigned int dwPolicyValueInHKLM; // [esp+18h] [ebp-8h] BYREF
  HKEY__ *hKey; // [esp+1Ch] [ebp-4h] BYREF

  hKey = 0;
  dwPolicyValueInHKLM = 0;
  dwPolicyValueInHKCU = 0;
  *isEnabled = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, &hKey) < 0
    || (dwValueType = 11,
        dwSize = 4,
        v2 = RegQueryValueExW(hKey, L"JScriptReplacement", 0, &dwValueType, (LPBYTE)&dwPolicyValueInHKLM, &dwSize),
        RegCloseKey(hKey),
        v2 < 0)
    || (v3 = dwPolicyValueInHKLM) == 0 )
  {
    v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, &hKey);
    if ( v2 < 0 )
      return v2;
    dwSize = 11;
    dwValueType = 4;
    v2 = RegQueryValueExW(hKey, L"JScriptReplacement", 0, &dwSize, (LPBYTE)&dwPolicyValueInHKCU, &dwValueType);
    RegCloseKey(hKey);
    if ( v2 < 0 )
      return v2;
    v3 = dwPolicyValueInHKLM;
  }
  v4 = 1;
  if ( v3 != 1 )
    v4 = dwPolicyValueInHKCU == 1;
  *isEnabled = v4;
  return v2;
}

```

## disassembly

```asm
0x100e3ce7  mov     edi, edi
0x100e3ce9  push    ebp
0x100e3cea  mov     ebp, esp
0x100e3cec  sub     esp, 14h
0x100e3cef  push    ebx
0x100e3cf0  push    esi
0x100e3cf1  push    edi
0x100e3cf2  mov     edi, [ebp+isEnabled]
0x100e3cf5  lea     eax, [ebp+hKey]
0x100e3cf8  push    eax; phkResult
0x100e3cf9  xor     ebx, ebx
0x100e3cfb  push    20019h; samDesired
0x100e3d00  push    ebx; ulOptions
0x100e3d01  push    offset aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x100e3d06  push    80000002h; hKey
0x100e3d0b  mov     [ebp+hKey], ebx
0x100e3d0e  mov     [ebp+dwPolicyValueInHKLM], ebx
0x100e3d11  mov     [ebp+dwPolicyValueInHKCU], ebx
0x100e3d14  mov     [edi], ebx
0x100e3d16  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100e3d1c  test    eax, eax
0x100e3d1e  js      short loc_100E3D5F
0x100e3d20  lea     eax, [ebp+dwSize]
0x100e3d23  mov     [ebp+dwValueType], 0Bh
0x100e3d2a  push    eax; lpcbData
0x100e3d2b  lea     eax, [ebp+dwPolicyValueInHKLM]
0x100e3d2e  mov     [ebp+dwSize], 4
0x100e3d35  push    eax; lpData
0x100e3d36  lea     eax, [ebp+dwValueType]
0x100e3d39  push    eax; lpType
0x100e3d3a  push    ebx; lpReserved
0x100e3d3b  push    offset aJscriptreplace; "JScriptReplacement"
0x100e3d40  push    [ebp+hKey]; hKey
0x100e3d43  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100e3d49  push    [ebp+hKey]; hKey
0x100e3d4c  mov     esi, eax
0x100e3d4e  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100e3d54  test    esi, esi
0x100e3d56  js      short loc_100E3D5F
0x100e3d58  mov     ecx, [ebp+dwPolicyValueInHKLM]
0x100e3d5b  test    ecx, ecx
0x100e3d5d  jnz     short loc_100E3DBA
0x100e3d5f  lea     eax, [ebp+hKey]
0x100e3d62  push    eax; phkResult
0x100e3d63  push    20019h; samDesired
0x100e3d68  push    ebx; ulOptions
0x100e3d69  push    offset aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x100e3d6e  push    80000001h; hKey
0x100e3d73  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100e3d79  mov     esi, eax
0x100e3d7b  test    esi, esi
0x100e3d7d  js      short loc_100E3DCA
0x100e3d7f  lea     eax, [ebp+dwValueType]
0x100e3d82  mov     [ebp+dwSize], 0Bh
0x100e3d89  push    eax; lpcbData
0x100e3d8a  lea     eax, [ebp+dwPolicyValueInHKCU]
0x100e3d8d  mov     [ebp+dwValueType], 4
0x100e3d94  push    eax; lpData
0x100e3d95  lea     eax, [ebp+dwSize]
0x100e3d98  push    eax; lpType
0x100e3d99  push    ebx; lpReserved
0x100e3d9a  push    offset aJscriptreplace; "JScriptReplacement"
0x100e3d9f  push    [ebp+hKey]; hKey
0x100e3da2  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100e3da8  push    [ebp+hKey]; hKey
0x100e3dab  mov     esi, eax
0x100e3dad  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100e3db3  test    esi, esi
0x100e3db5  js      short loc_100E3DCA
0x100e3db7  mov     ecx, [ebp+dwPolicyValueInHKLM]
0x100e3dba  xor     eax, eax
0x100e3dbc  inc     eax
0x100e3dbd  cmp     ecx, eax
0x100e3dbf  jz      short loc_100E3DC8
0x100e3dc1  cmp     [ebp+dwPolicyValueInHKCU], eax
0x100e3dc4  jz      short loc_100E3DC8
0x100e3dc6  mov     eax, ebx
0x100e3dc8  mov     [edi], eax
0x100e3dca  pop     edi
0x100e3dcb  mov     eax, esi
0x100e3dcd  pop     esi
0x100e3dce  pop     ebx
0x100e3dcf  leave
0x100e3dd0  retn    4
```
