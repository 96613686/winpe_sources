# ScriptSymbol::IsJScript9LegacyEnabled(int *)

- ea: `0x100e3e07`
- end: `0x100e3ef3`
- name: `?IsJScript9LegacyEnabled@ScriptSymbol@@IAEJPAH@Z`
- size: `236`
- prototype: `HRESULT __thiscall(ScriptSymbol *this, int *isEnabled)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100649be`

## callees

- `0x100e3e07`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100e3e63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100e3ec2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100e3e63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100e3ec2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100e3e6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100e3ecd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100e3e6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100e3ecd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100e3e36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100e3e93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100e3e36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100e3e93`

## string_xrefs

- `0x100e3e5b`: `JScriptReplacement`
- `0x100e3eba`: `JScriptReplacement`

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
0x100e3e07  mov     edi, edi
0x100e3e09  push    ebp
0x100e3e0a  mov     ebp, esp
0x100e3e0c  sub     esp, 14h
0x100e3e0f  push    ebx
0x100e3e10  push    esi
0x100e3e11  push    edi
0x100e3e12  mov     edi, [ebp+isEnabled]
0x100e3e15  lea     eax, [ebp+hKey]
0x100e3e18  push    eax; phkResult
0x100e3e19  xor     ebx, ebx
0x100e3e1b  push    20019h; samDesired
0x100e3e20  push    ebx; ulOptions
0x100e3e21  push    offset aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x100e3e26  push    80000002h; hKey
0x100e3e2b  mov     [ebp+hKey], ebx
0x100e3e2e  mov     [ebp+dwPolicyValueInHKLM], ebx
0x100e3e31  mov     [ebp+dwPolicyValueInHKCU], ebx
0x100e3e34  mov     [edi], ebx
0x100e3e36  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100e3e3c  test    eax, eax
0x100e3e3e  js      short loc_100E3E7F
0x100e3e40  lea     eax, [ebp+dwSize]
0x100e3e43  mov     [ebp+dwValueType], 0Bh
0x100e3e4a  push    eax; lpcbData
0x100e3e4b  lea     eax, [ebp+dwPolicyValueInHKLM]
0x100e3e4e  mov     [ebp+dwSize], 4
0x100e3e55  push    eax; lpData
0x100e3e56  lea     eax, [ebp+dwValueType]
0x100e3e59  push    eax; lpType
0x100e3e5a  push    ebx; lpReserved
0x100e3e5b  push    offset aJscriptreplace; "JScriptReplacement"
0x100e3e60  push    [ebp+hKey]; hKey
0x100e3e63  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100e3e69  push    [ebp+hKey]; hKey
0x100e3e6c  mov     esi, eax
0x100e3e6e  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100e3e74  test    esi, esi
0x100e3e76  js      short loc_100E3E7F
0x100e3e78  mov     ecx, [ebp+dwPolicyValueInHKLM]
0x100e3e7b  test    ecx, ecx
0x100e3e7d  jnz     short loc_100E3EDA
0x100e3e7f  lea     eax, [ebp+hKey]
0x100e3e82  push    eax; phkResult
0x100e3e83  push    20019h; samDesired
0x100e3e88  push    ebx; ulOptions
0x100e3e89  push    offset aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x100e3e8e  push    80000001h; hKey
0x100e3e93  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100e3e99  mov     esi, eax
0x100e3e9b  test    esi, esi
0x100e3e9d  js      short loc_100E3EEA
0x100e3e9f  lea     eax, [ebp+dwValueType]
0x100e3ea2  mov     [ebp+dwSize], 0Bh
0x100e3ea9  push    eax; lpcbData
0x100e3eaa  lea     eax, [ebp+dwPolicyValueInHKCU]
0x100e3ead  mov     [ebp+dwValueType], 4
0x100e3eb4  push    eax; lpData
0x100e3eb5  lea     eax, [ebp+dwSize]
0x100e3eb8  push    eax; lpType
0x100e3eb9  push    ebx; lpReserved
0x100e3eba  push    offset aJscriptreplace; "JScriptReplacement"
0x100e3ebf  push    [ebp+hKey]; hKey
0x100e3ec2  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100e3ec8  push    [ebp+hKey]; hKey
0x100e3ecb  mov     esi, eax
0x100e3ecd  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100e3ed3  test    esi, esi
0x100e3ed5  js      short loc_100E3EEA
0x100e3ed7  mov     ecx, [ebp+dwPolicyValueInHKLM]
0x100e3eda  xor     eax, eax
0x100e3edc  inc     eax
0x100e3edd  cmp     ecx, eax
0x100e3edf  jz      short loc_100E3EE8
0x100e3ee1  cmp     [ebp+dwPolicyValueInHKCU], eax
0x100e3ee4  jz      short loc_100E3EE8
0x100e3ee6  mov     eax, ebx
0x100e3ee8  mov     [edi], eax
0x100e3eea  pop     edi
0x100e3eeb  mov     eax, esi
0x100e3eed  pop     esi
0x100e3eee  pop     ebx
0x100e3eef  leave
0x100e3ef0  retn    4
```
