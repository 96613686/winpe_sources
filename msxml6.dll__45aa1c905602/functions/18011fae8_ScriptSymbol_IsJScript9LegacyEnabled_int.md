# ScriptSymbol::IsJScript9LegacyEnabled(int *)

- ea: `0x18011fae8`
- end: `0x18011fc4b`
- name: `?IsJScript9LegacyEnabled@ScriptSymbol@@IEAAJPEAH@Z`
- size: `355`
- prototype: `HRESULT __fastcall(ScriptSymbol *this, int *isEnabled)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c9c44`

## callees

- `0x18011fae8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011fb8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011fc1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011fb8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011fc1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011fb36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011fbc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011fb36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011fbc5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011fb78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011fc09`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011fb78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011fc09`

## string_xrefs

- `0x18011fb6a`: `JScriptReplacement`
- `0x18011fbfb`: `JScriptReplacement`

## pseudocode

```c
__int64 __fastcall ScriptSymbol::IsJScript9LegacyEnabled(ScriptSymbol *this, int *isEnabled)
{
  LSTATUS v3; // ebx
  int v4; // ecx
  BOOL v5; // eax
  HKEY__ *hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 dwPolicyValueInHKLM; // [rsp+60h] [rbp+20h] BYREF
  unsigned int dwPolicyValueInHKCU; // [rsp+68h] [rbp+28h] BYREF
  unsigned int dwSize; // [rsp+70h] [rbp+30h] BYREF
  unsigned int dwValueType; // [rsp+78h] [rbp+38h] BYREF

  HIDWORD(dwPolicyValueInHKLM) = HIDWORD(this);
  *isEnabled = 0;
  hKey[0] = 0;
  LODWORD(dwPolicyValueInHKLM) = 0;
  dwPolicyValueInHKCU = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, hKey) < 0
    || (dwValueType = 11,
        dwSize = 4,
        v3 = RegQueryValueExW(hKey[0], L"JScriptReplacement", 0, &dwValueType, (LPBYTE)&dwPolicyValueInHKLM, &dwSize),
        RegCloseKey(hKey[0]),
        v3 < 0)
    || (v4 = dwPolicyValueInHKLM) == 0 )
  {
    v3 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, hKey);
    if ( v3 < 0 )
      return (unsigned int)v3;
    dwValueType = 11;
    dwSize = 4;
    v3 = RegQueryValueExW(hKey[0], L"JScriptReplacement", 0, &dwValueType, (LPBYTE)&dwPolicyValueInHKCU, &dwSize);
    RegCloseKey(hKey[0]);
    if ( v3 < 0 )
      return (unsigned int)v3;
    v4 = dwPolicyValueInHKLM;
  }
  v5 = 1;
  if ( v4 != 1 )
    v5 = dwPolicyValueInHKCU == 1;
  *isEnabled = v5;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18011fae8  mov     [rsp-18h+dwPolicyValueInHKLM], rcx
0x18011faed  push    rbp
0x18011faee  push    rbx
0x18011faef  push    rdi
0x18011faf0  mov     rbp, rsp
0x18011faf3  sub     rsp, 40h
0x18011faf7  mov     rdi, isEnabled
0x18011fafa  mov     dword ptr [isEnabled], 0
0x18011fb00  lea     rax, [rbp+hKey]
0x18011fb04  mov     [rbp+hKey], 0
0x18011fb0c  lea     isEnabled, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x18011fb13  mov     [rsp+40h+phkResult], rax; phkResult
0x18011fb18  mov     r9d, 20019h; samDesired
0x18011fb1e  mov     dword ptr [rbp+dwPolicyValueInHKLM], 0
0x18011fb25  xor     r8d, r8d; ulOptions
0x18011fb28  mov     [rbp+dwPolicyValueInHKCU], 0
0x18011fb2f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011fb36  call    cs:__imp_RegOpenKeyExW
0x18011fb3d  nop     dword ptr [rax+rax+00h]
0x18011fb42  test    eax, eax
0x18011fb44  js      short loc_18011FBA5
0x18011fb46  mov     rcx, [rbp+hKey]; hKey
0x18011fb4a  lea     rax, [rbp+dwSize]
0x18011fb4e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18011fb53  lea     r9, [rbp+dwValueType]; lpType
0x18011fb57  lea     rax, [rbp+dwPolicyValueInHKLM]
0x18011fb5b  mov     [rbp+dwValueType], 0Bh
0x18011fb62  xor     r8d, r8d; lpReserved
0x18011fb65  mov     [rsp+40h+phkResult], rax; lpData
0x18011fb6a  lea     isEnabled, aJscriptreplace; "JScriptReplacement"
0x18011fb71  mov     [rbp+dwSize], 4
0x18011fb78  call    cs:__imp_RegQueryValueExW
0x18011fb7f  nop     dword ptr [rax+rax+00h]
0x18011fb84  mov     rcx, [rbp+hKey]; hKey
0x18011fb88  mov     ebx, eax
0x18011fb8a  call    cs:__imp_RegCloseKey
0x18011fb91  nop     dword ptr [rax+rax+00h]
0x18011fb96  test    ebx, ebx
0x18011fb98  js      short loc_18011FBA5
0x18011fb9a  mov     ecx, dword ptr [rbp+dwPolicyValueInHKLM]
0x18011fb9d  test    ecx, ecx
0x18011fb9f  jnz     loc_18011FC2E
0x18011fba5  lea     rax, [rbp+hKey]
0x18011fba9  mov     r9d, 20019h; samDesired
0x18011fbaf  xor     r8d, r8d; ulOptions
0x18011fbb2  mov     [rsp+40h+phkResult], rax; phkResult
0x18011fbb7  lea     isEnabled, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x18011fbbe  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18011fbc5  call    cs:__imp_RegOpenKeyExW
0x18011fbcc  nop     dword ptr [rax+rax+00h]
0x18011fbd1  mov     ebx, eax
0x18011fbd3  test    eax, eax
0x18011fbd5  js      short loc_18011FC40
0x18011fbd7  mov     rcx, [rbp+hKey]; hKey
0x18011fbdb  lea     rax, [rbp+dwSize]
0x18011fbdf  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18011fbe4  lea     r9, [rbp+dwValueType]; lpType
0x18011fbe8  lea     rax, [rbp+dwPolicyValueInHKCU]
0x18011fbec  mov     [rbp+dwValueType], 0Bh
0x18011fbf3  xor     r8d, r8d; lpReserved
0x18011fbf6  mov     [rsp+40h+phkResult], rax; lpData
0x18011fbfb  lea     isEnabled, aJscriptreplace; "JScriptReplacement"
0x18011fc02  mov     [rbp+dwSize], 4
0x18011fc09  call    cs:__imp_RegQueryValueExW
0x18011fc10  nop     dword ptr [rax+rax+00h]
0x18011fc15  mov     rcx, [rbp+hKey]; hKey
0x18011fc19  mov     ebx, eax
0x18011fc1b  call    cs:__imp_RegCloseKey
0x18011fc22  nop     dword ptr [rax+rax+00h]
0x18011fc27  test    ebx, ebx
0x18011fc29  js      short loc_18011FC40
0x18011fc2b  mov     ecx, dword ptr [rbp+dwPolicyValueInHKLM]
0x18011fc2e  mov     eax, 1
0x18011fc33  cmp     ecx, eax
0x18011fc35  jz      short loc_18011FC3E
0x18011fc37  cmp     [rbp+dwPolicyValueInHKCU], eax
0x18011fc3a  jz      short loc_18011FC3E
0x18011fc3c  xor     eax, eax
0x18011fc3e  mov     [rdi], eax
0x18011fc40  mov     eax, ebx
0x18011fc42  add     rsp, 40h
0x18011fc46  pop     rdi
0x18011fc47  pop     rbx
0x18011fc48  pop     rbp
0x18011fc49  retn
```
