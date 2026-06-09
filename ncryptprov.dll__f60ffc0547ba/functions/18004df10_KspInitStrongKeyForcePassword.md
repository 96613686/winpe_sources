# KspInitStrongKeyForcePassword

- ea: `0x18004df10`
- end: `0x18004dfdf`
- name: `KspInitStrongKeyForcePassword`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800096e0`

## callees

- `0x18000af80`
- `0x18004df10`

## import_xrefs

- `ntdll!NtClose` at `0x18004dfc9`
- `ntdll!NtClose` at `0x18004dfc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004df51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004df51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004dfa2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004dfa2`

## string_xrefs

- `0x18004df67`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 KspInitStrongKeyForcePassword()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  v1 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Policies\\Microsoft\\Cryptography", 0, 0x20119u, &hKey);
  if ( v1 )
  {
    DebugTraceError(v1, "lResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 589);
  }
  else if ( !RegQueryValueExA(hKey, "ForceKeyProtection", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
  {
    v0 = Data;
  }
  if ( hKey )
    NtClose(hKey);
  return v0;
}

```

## disassembly

```asm
0x18004df10  push    rbp
0x18004df12  push    rbx
0x18004df13  mov     rbp, rsp
0x18004df16  sub     rsp, 38h
0x18004df1a  xor     ebx, ebx
0x18004df1c  mov     [rbp+hKey], 0
0x18004df24  lea     rax, [rbp+hKey]
0x18004df28  mov     [rbp+Data], ebx
0x18004df2b  mov     r9d, 20119h; samDesired
0x18004df31  mov     [rbp+Type], ebx
0x18004df34  xor     r8d, r8d; ulOptions
0x18004df37  mov     [rsp+38h+phkResult], rax; phkResult
0x18004df3c  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Cryptogr"...
0x18004df43  mov     [rbp+cbData], 4
0x18004df4a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004df51  call    cs:__imp_RegOpenKeyExA
0x18004df58  nop     dword ptr [rax+rax+00h]
0x18004df5d  test    eax, eax
0x18004df5f  jz      short loc_18004DF7E
0x18004df61  mov     r9d, 24Dh
0x18004df67  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004df6e  lea     rdx, aLresult; "lResult"
0x18004df75  mov     ecx, eax
0x18004df77  call    DebugTraceError
0x18004df7c  jmp     short loc_18004DFC0
0x18004df7e  mov     rcx, [rbp+hKey]; hKey
0x18004df82  lea     rax, [rbp+cbData]
0x18004df86  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004df8b  lea     r9, [rbp+Type]; lpType
0x18004df8f  lea     rax, [rbp+Data]
0x18004df93  xor     r8d, r8d; lpReserved
0x18004df96  lea     rdx, aForcekeyprotec; "ForceKeyProtection"
0x18004df9d  mov     [rsp+38h+phkResult], rax; lpData
0x18004dfa2  call    cs:__imp_RegQueryValueExA
0x18004dfa9  nop     dword ptr [rax+rax+00h]
0x18004dfae  test    eax, eax
0x18004dfb0  jnz     short loc_18004DFC0
0x18004dfb2  cmp     [rbp+Type], 4
0x18004dfb6  jnz     short loc_18004DFC0
0x18004dfb8  cmp     [rbp+cbData], 4
0x18004dfbc  cmovz   ebx, [rbp+Data]
0x18004dfc0  mov     rcx, [rbp+hKey]; Handle
0x18004dfc4  test    rcx, rcx
0x18004dfc7  jz      short loc_18004DFD5
0x18004dfc9  call    cs:__imp_NtClose
0x18004dfd0  nop     dword ptr [rax+rax+00h]
0x18004dfd5  mov     eax, ebx
0x18004dfd7  add     rsp, 38h
0x18004dfdb  pop     rbx
0x18004dfdc  pop     rbp
0x18004dfdd  retn
```
