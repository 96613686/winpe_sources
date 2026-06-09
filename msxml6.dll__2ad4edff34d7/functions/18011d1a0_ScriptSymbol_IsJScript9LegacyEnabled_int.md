# ScriptSymbol::IsJScript9LegacyEnabled(int *)

- ea: `0x18011d1a0`
- end: `0x18011d2da`
- name: `?IsJScript9LegacyEnabled@ScriptSymbol@@IEAAJPEAH@Z`
- size: `314`
- prototype: `HRESULT __fastcall(ScriptSymbol *this, int *isEnabled)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c8354`

## callees

- `0x18011d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011d236`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011d2b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011d236`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011d2b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011d1ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011d267`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011d1ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011d267`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011d22a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011d2a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011d22a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011d2a5`

## string_xrefs

- `0x18011d21c`: `JScriptReplacement`
- `0x18011d297`: `JScriptReplacement`

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
0x18011d1a0  mov     [rsp-18h+dwPolicyValueInHKLM], rcx
0x18011d1a5  push    rbp
0x18011d1a6  push    rbx
0x18011d1a7  push    rdi
0x18011d1a8  mov     rbp, rsp
0x18011d1ab  sub     rsp, 40h
0x18011d1af  mov     rdi, isEnabled
0x18011d1b2  mov     dword ptr [isEnabled], 0
0x18011d1b8  lea     rax, [rbp+hKey]
0x18011d1bc  mov     [rbp+hKey], 0
0x18011d1c4  lea     isEnabled, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x18011d1cb  mov     [rsp+40h+phkResult], rax; phkResult
0x18011d1d0  mov     r9d, 20019h; samDesired
0x18011d1d6  mov     dword ptr [rbp+dwPolicyValueInHKLM], 0
0x18011d1dd  xor     r8d, r8d; ulOptions
0x18011d1e0  mov     [rbp+dwPolicyValueInHKCU], 0
0x18011d1e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011d1ee  call    cs:__imp_RegOpenKeyExW
0x18011d1f4  test    eax, eax
0x18011d1f6  js      short loc_18011D247
0x18011d1f8  mov     rcx, [rbp+hKey]; hKey
0x18011d1fc  lea     rax, [rbp+dwSize]
0x18011d200  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18011d205  lea     r9, [rbp+dwValueType]; lpType
0x18011d209  lea     rax, [rbp+dwPolicyValueInHKLM]
0x18011d20d  mov     [rbp+dwValueType], 0Bh
0x18011d214  xor     r8d, r8d; lpReserved
0x18011d217  mov     [rsp+40h+phkResult], rax; lpData
0x18011d21c  lea     isEnabled, aJscriptreplace; "JScriptReplacement"
0x18011d223  mov     [rbp+dwSize], 4
0x18011d22a  call    cs:__imp_RegQueryValueExW
0x18011d230  mov     rcx, [rbp+hKey]; hKey
0x18011d234  mov     ebx, eax
0x18011d236  call    cs:__imp_RegCloseKey
0x18011d23c  test    ebx, ebx
0x18011d23e  js      short loc_18011D247
0x18011d240  mov     ecx, dword ptr [rbp+dwPolicyValueInHKLM]
0x18011d243  test    ecx, ecx
0x18011d245  jnz     short loc_18011D2BE
0x18011d247  lea     rax, [rbp+hKey]
0x18011d24b  mov     r9d, 20019h; samDesired
0x18011d251  xor     r8d, r8d; ulOptions
0x18011d254  mov     [rsp+40h+phkResult], rax; phkResult
0x18011d259  lea     isEnabled, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x18011d260  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18011d267  call    cs:__imp_RegOpenKeyExW
0x18011d26d  mov     ebx, eax
0x18011d26f  test    eax, eax
0x18011d271  js      short loc_18011D2D0
0x18011d273  mov     rcx, [rbp+hKey]; hKey
0x18011d277  lea     rax, [rbp+dwSize]
0x18011d27b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18011d280  lea     r9, [rbp+dwValueType]; lpType
0x18011d284  lea     rax, [rbp+dwPolicyValueInHKCU]
0x18011d288  mov     [rbp+dwValueType], 0Bh
0x18011d28f  xor     r8d, r8d; lpReserved
0x18011d292  mov     [rsp+40h+phkResult], rax; lpData
0x18011d297  lea     isEnabled, aJscriptreplace; "JScriptReplacement"
0x18011d29e  mov     [rbp+dwSize], 4
0x18011d2a5  call    cs:__imp_RegQueryValueExW
0x18011d2ab  mov     rcx, [rbp+hKey]; hKey
0x18011d2af  mov     ebx, eax
0x18011d2b1  call    cs:__imp_RegCloseKey
0x18011d2b7  test    ebx, ebx
0x18011d2b9  js      short loc_18011D2D0
0x18011d2bb  mov     ecx, dword ptr [rbp+dwPolicyValueInHKLM]
0x18011d2be  mov     eax, 1
0x18011d2c3  cmp     ecx, eax
0x18011d2c5  jz      short loc_18011D2CE
0x18011d2c7  cmp     [rbp+dwPolicyValueInHKCU], eax
0x18011d2ca  jz      short loc_18011D2CE
0x18011d2cc  xor     eax, eax
0x18011d2ce  mov     [rdi], eax
0x18011d2d0  mov     eax, ebx
0x18011d2d2  add     rsp, 40h
0x18011d2d6  pop     rdi
0x18011d2d7  pop     rbx
0x18011d2d8  pop     rbp
0x18011d2d9  retn
```
