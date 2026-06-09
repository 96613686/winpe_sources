# FunctionManager::IsJScript9LegacyEnabled(int *)

- ea: `0x1800ad340`
- end: `0x1800ad47a`
- name: `?IsJScript9LegacyEnabled@FunctionManager@@QEAAJPEAH@Z`
- size: `314`
- prototype: `__int64 __fastcall(FunctionManager *__hidden this, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005298c`

## callees

- `0x1800ad340`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ad3ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ad445`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ad3ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ad445`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad3d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad451`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad3d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad451`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ad38e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ad407`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ad38e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ad407`

## string_xrefs

- `0x1800ad3bc`: `JScriptReplacement`
- `0x1800ad437`: `JScriptReplacement`

## pseudocode

```c
__int64 __fastcall FunctionManager::IsJScript9LegacyEnabled(FunctionManager *this, int *a2)
{
  LSTATUS v3; // ebx
  int v4; // ecx
  BOOL v5; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  int v9; // [rsp+64h] [rbp+24h]
  int v10; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  v9 = HIDWORD(this);
  *a2 = 0;
  hKey[0] = 0;
  Data = 0;
  v10 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, hKey) < 0
    || (Type = 11,
        cbData = 4,
        v3 = RegQueryValueExW(hKey[0], L"JScriptReplacement", 0, &Type, (LPBYTE)&Data, &cbData),
        RegCloseKey(hKey[0]),
        v3 < 0)
    || (v4 = Data) == 0 )
  {
    v3 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, hKey);
    if ( v3 < 0 )
      return (unsigned int)v3;
    Type = 11;
    cbData = 4;
    v3 = RegQueryValueExW(hKey[0], L"JScriptReplacement", 0, &Type, (LPBYTE)&v10, &cbData);
    RegCloseKey(hKey[0]);
    if ( v3 < 0 )
      return (unsigned int)v3;
    v4 = Data;
  }
  v5 = 1;
  if ( v4 != 1 )
    v5 = v10 == 1;
  *a2 = v5;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800ad340  mov     qword ptr [rsp-18h+Data], rcx
0x1800ad345  push    rbp
0x1800ad346  push    rbx
0x1800ad347  push    rdi
0x1800ad348  mov     rbp, rsp
0x1800ad34b  sub     rsp, 40h
0x1800ad34f  mov     rdi, rdx
0x1800ad352  mov     dword ptr [rdx], 0
0x1800ad358  lea     rax, [rbp+hKey]
0x1800ad35c  mov     [rbp+hKey], 0
0x1800ad364  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Internet"...
0x1800ad36b  mov     [rsp+40h+phkResult], rax; phkResult
0x1800ad370  mov     r9d, 20019h; samDesired
0x1800ad376  mov     [rbp+Data], 0
0x1800ad37d  xor     r8d, r8d; ulOptions
0x1800ad380  mov     [rbp+arg_8], 0
0x1800ad387  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ad38e  call    cs:__imp_RegOpenKeyExW
0x1800ad394  test    eax, eax
0x1800ad396  js      short loc_1800AD3E7
0x1800ad398  mov     rcx, [rbp+hKey]; hKey
0x1800ad39c  lea     rax, [rbp+cbData]
0x1800ad3a0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800ad3a5  lea     r9, [rbp+Type]; lpType
0x1800ad3a9  lea     rax, [rbp+Data]
0x1800ad3ad  mov     [rbp+Type], 0Bh
0x1800ad3b4  xor     r8d, r8d; lpReserved
0x1800ad3b7  mov     [rsp+40h+phkResult], rax; lpData
0x1800ad3bc  lea     rdx, ValueName; "JScriptReplacement"
0x1800ad3c3  mov     [rbp+cbData], 4
0x1800ad3ca  call    cs:__imp_RegQueryValueExW
0x1800ad3d0  mov     rcx, [rbp+hKey]; hKey
0x1800ad3d4  mov     ebx, eax
0x1800ad3d6  call    cs:__imp_RegCloseKey
0x1800ad3dc  test    ebx, ebx
0x1800ad3de  js      short loc_1800AD3E7
0x1800ad3e0  mov     ecx, [rbp+Data]
0x1800ad3e3  test    ecx, ecx
0x1800ad3e5  jnz     short loc_1800AD45E
0x1800ad3e7  lea     rax, [rbp+hKey]
0x1800ad3eb  mov     r9d, 20019h; samDesired
0x1800ad3f1  xor     r8d, r8d; ulOptions
0x1800ad3f4  mov     [rsp+40h+phkResult], rax; phkResult
0x1800ad3f9  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Internet"...
0x1800ad400  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800ad407  call    cs:__imp_RegOpenKeyExW
0x1800ad40d  mov     ebx, eax
0x1800ad40f  test    eax, eax
0x1800ad411  js      short loc_1800AD470
0x1800ad413  mov     rcx, [rbp+hKey]; hKey
0x1800ad417  lea     rax, [rbp+cbData]
0x1800ad41b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800ad420  lea     r9, [rbp+Type]; lpType
0x1800ad424  lea     rax, [rbp+arg_8]
0x1800ad428  mov     [rbp+Type], 0Bh
0x1800ad42f  xor     r8d, r8d; lpReserved
0x1800ad432  mov     [rsp+40h+phkResult], rax; lpData
0x1800ad437  lea     rdx, ValueName; "JScriptReplacement"
0x1800ad43e  mov     [rbp+cbData], 4
0x1800ad445  call    cs:__imp_RegQueryValueExW
0x1800ad44b  mov     rcx, [rbp+hKey]; hKey
0x1800ad44f  mov     ebx, eax
0x1800ad451  call    cs:__imp_RegCloseKey
0x1800ad457  test    ebx, ebx
0x1800ad459  js      short loc_1800AD470
0x1800ad45b  mov     ecx, [rbp+Data]
0x1800ad45e  mov     eax, 1
0x1800ad463  cmp     ecx, eax
0x1800ad465  jz      short loc_1800AD46E
0x1800ad467  cmp     [rbp+arg_8], eax
0x1800ad46a  jz      short loc_1800AD46E
0x1800ad46c  xor     eax, eax
0x1800ad46e  mov     [rdi], eax
0x1800ad470  mov     eax, ebx
0x1800ad472  add     rsp, 40h
0x1800ad476  pop     rdi
0x1800ad477  pop     rbx
0x1800ad478  pop     rbp
0x1800ad479  retn
```
