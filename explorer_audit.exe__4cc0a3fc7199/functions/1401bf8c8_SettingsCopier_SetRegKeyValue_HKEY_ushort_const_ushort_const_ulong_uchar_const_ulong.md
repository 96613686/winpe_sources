# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x1401bf8c8`
- end: `0x1401bfa2b`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `355`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x1401bf1f0`

## callees

- `0x1401bf8c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bf938`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bf938`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf959`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf9bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf9de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bfa14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf959`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf9bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf9de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bfa14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bf97a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bf97a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401bf9a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401bf9a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bfa08`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bfa08`

## string_xrefs

- `0x1401bf9a1`: `SymbolicLinkValue`

## pseudocode

```c
LSTATUS __fastcall SettingsCopier::SetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        DWORD dwType,
        BYTE *lpData,
        DWORD a6)
{
  LSTATUS result; // eax
  bool v11; // cc
  LSTATUS v12; // eax
  LSTATUS v13; // ebx
  bool v14; // cc
  DWORD Type; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+58h] [rbp-18h] BYREF
  HKEY v18; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-8h] BYREF

  hKeya = 0;
  v18 = 0;
  dwDisposition = 0;
  Type = 0;
  cbData = 0;
  result = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, 0x2001Fu, 0, &hKeya, &dwDisposition);
  v11 = result <= 0;
  if ( result
    || (RegCloseKey(hKeya), result = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x2001Fu, &v18), v11 = result <= 0, result) )
  {
    if ( !v11 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v12 = RegQueryValueExW(v18, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
  v13 = v12;
  if ( !v12 )
  {
    if ( Type == 6 )
    {
      RegCloseKey(v18);
      return -2147023432;
    }
LABEL_13:
    v13 = RegSetValueExW(v18, lpValueName, 0, dwType, lpData, a6);
    RegCloseKey(v18);
    v14 = v13 <= 0;
    if ( !v13 )
      return 0;
    goto LABEL_8;
  }
  if ( v12 == 2 )
    goto LABEL_13;
  RegCloseKey(v18);
  v14 = v13 <= 0;
LABEL_8:
  if ( !v14 )
    return (unsigned __int16)v13 | 0x80070000;
  return v13;
}

```

## disassembly

```asm
0x1401bf8c8  push    rbp
0x1401bf8ca  push    rbx
0x1401bf8cb  push    rsi
0x1401bf8cc  push    rdi
0x1401bf8cd  push    r14
0x1401bf8cf  mov     rbp, rsp
0x1401bf8d2  sub     rsp, 70h
0x1401bf8d6  lea     rax, [rbp+dwDisposition]
0x1401bf8da  mov     [rbp+hKey], 0
0x1401bf8e2  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1401bf8e7  mov     esi, r9d
0x1401bf8ea  lea     rax, [rbp+hKey]
0x1401bf8ee  mov     [rbp+var_10], 0
0x1401bf8f6  mov     [rsp+70h+phkResult], rax; phkResult
0x1401bf8fb  mov     r14, r8
0x1401bf8fe  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401bf907  xor     r9d, r9d; lpClass
0x1401bf90a  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x1401bf912  xor     r8d, r8d; Reserved
0x1401bf915  mov     [rsp+70h+dwOptions], 1; dwOptions
0x1401bf91d  mov     rbx, rdx
0x1401bf920  mov     rdi, rcx
0x1401bf923  mov     [rbp+dwDisposition], 0
0x1401bf92a  mov     [rbp+Type], 0
0x1401bf931  mov     [rbp+cbData], 0
0x1401bf938  call    cs:__imp_RegCreateKeyExW
0x1401bf93e  test    eax, eax
0x1401bf940  jz      short loc_1401BF955
0x1401bf942  jle     loc_1401BFA20
0x1401bf948  movzx   eax, ax
0x1401bf94b  or      eax, 80070000h
0x1401bf950  jmp     loc_1401BFA20
0x1401bf955  mov     rcx, [rbp+hKey]; hKey
0x1401bf959  call    cs:__imp_RegCloseKey
0x1401bf95f  lea     rax, [rbp+var_10]
0x1401bf963  mov     r9d, 2001Fh; samDesired
0x1401bf969  mov     r8d, 8; ulOptions
0x1401bf96f  mov     qword ptr [rsp+70h+dwOptions], rax; phkResult
0x1401bf974  mov     rdx, rbx; lpSubKey
0x1401bf977  mov     rcx, rdi; hKey
0x1401bf97a  call    cs:__imp_RegOpenKeyExW
0x1401bf980  test    eax, eax
0x1401bf982  jnz     short loc_1401BF942
0x1401bf984  mov     rcx, [rbp+var_10]; hKey
0x1401bf988  lea     rax, [rbp+cbData]
0x1401bf98c  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x1401bf991  lea     r9, [rbp+Type]; lpType
0x1401bf995  xor     r8d, r8d; lpReserved
0x1401bf998  mov     qword ptr [rsp+70h+dwOptions], 0; lpData
0x1401bf9a1  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1401bf9a8  call    cs:__imp_RegQueryValueExW
0x1401bf9ae  mov     ebx, eax
0x1401bf9b0  test    eax, eax
0x1401bf9b2  jz      short loc_1401BF9D4
0x1401bf9b4  cmp     eax, 2
0x1401bf9b7  jz      short loc_1401BF9EB
0x1401bf9b9  mov     rcx, [rbp+var_10]; hKey
0x1401bf9bd  call    cs:__imp_RegCloseKey
0x1401bf9c3  test    ebx, ebx
0x1401bf9c5  jle     short loc_1401BF9D0
0x1401bf9c7  movzx   ebx, bx
0x1401bf9ca  or      ebx, 80070000h
0x1401bf9d0  mov     eax, ebx
0x1401bf9d2  jmp     short loc_1401BFA20
0x1401bf9d4  cmp     [rbp+Type], 6
0x1401bf9d8  jnz     short loc_1401BF9EB
0x1401bf9da  mov     rcx, [rbp+var_10]; hKey
0x1401bf9de  call    cs:__imp_RegCloseKey
0x1401bf9e4  mov     eax, 800705B8h
0x1401bf9e9  jmp     short loc_1401BFA20
0x1401bf9eb  mov     eax, [rbp+arg_28]
0x1401bf9ee  mov     r9d, esi; dwType
0x1401bf9f1  mov     rcx, [rbp+var_10]; hKey
0x1401bf9f5  xor     r8d, r8d; Reserved
0x1401bf9f8  mov     [rsp+70h+samDesired], eax; cbData
0x1401bf9fc  mov     rdx, r14; lpValueName
0x1401bf9ff  mov     rax, [rbp+lpData]
0x1401bfa03  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x1401bfa08  call    cs:__imp_RegSetValueExW
0x1401bfa0e  mov     rcx, [rbp+var_10]; hKey
0x1401bfa12  mov     ebx, eax
0x1401bfa14  call    cs:__imp_RegCloseKey
0x1401bfa1a  test    ebx, ebx
0x1401bfa1c  jnz     short loc_1401BF9C5
0x1401bfa1e  xor     eax, eax
0x1401bfa20  add     rsp, 70h
0x1401bfa24  pop     r14
0x1401bfa26  pop     rdi
0x1401bfa27  pop     rsi
0x1401bfa28  pop     rbx
0x1401bfa29  pop     rbp
0x1401bfa2a  retn
```
