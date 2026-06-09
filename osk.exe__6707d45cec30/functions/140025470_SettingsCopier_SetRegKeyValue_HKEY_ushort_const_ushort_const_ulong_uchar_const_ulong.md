# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x140025470`
- end: `0x1400255d3`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `355`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x14002491c`

## callees

- `0x140025470`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140025522`
- `ADVAPI32!RegOpenKeyExW` at `0x140025522`
- `ADVAPI32!RegSetValueExW` at `0x1400255b0`
- `ADVAPI32!RegSetValueExW` at `0x1400255b0`
- `ADVAPI32!RegCloseKey` at `0x140025501`
- `ADVAPI32!RegCloseKey` at `0x140025565`
- `ADVAPI32!RegCloseKey` at `0x140025586`
- `ADVAPI32!RegCloseKey` at `0x1400255bc`
- `ADVAPI32!RegCloseKey` at `0x140025501`
- `ADVAPI32!RegCloseKey` at `0x140025565`
- `ADVAPI32!RegCloseKey` at `0x140025586`
- `ADVAPI32!RegCloseKey` at `0x1400255bc`
- `ADVAPI32!RegQueryValueExW` at `0x140025550`
- `ADVAPI32!RegQueryValueExW` at `0x140025550`
- `ADVAPI32!RegCreateKeyExW` at `0x1400254e0`
- `ADVAPI32!RegCreateKeyExW` at `0x1400254e0`

## string_xrefs

- `0x140025549`: `SymbolicLinkValue`

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
0x140025470  push    rbp
0x140025472  push    rbx
0x140025473  push    rsi
0x140025474  push    rdi
0x140025475  push    r14
0x140025477  mov     rbp, rsp
0x14002547a  sub     rsp, 70h
0x14002547e  lea     rax, [rbp+dwDisposition]
0x140025482  mov     [rbp+hKey], 0
0x14002548a  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x14002548f  mov     esi, r9d
0x140025492  lea     rax, [rbp+hKey]
0x140025496  mov     [rbp+var_10], 0
0x14002549e  mov     [rsp+70h+phkResult], rax; phkResult
0x1400254a3  mov     r14, r8
0x1400254a6  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400254af  xor     r9d, r9d; lpClass
0x1400254b2  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x1400254ba  xor     r8d, r8d; Reserved
0x1400254bd  mov     [rsp+70h+dwOptions], 1; dwOptions
0x1400254c5  mov     rbx, rdx
0x1400254c8  mov     rdi, rcx
0x1400254cb  mov     [rbp+dwDisposition], 0
0x1400254d2  mov     [rbp+Type], 0
0x1400254d9  mov     [rbp+cbData], 0
0x1400254e0  call    cs:__imp_RegCreateKeyExW
0x1400254e6  test    eax, eax
0x1400254e8  jz      short loc_1400254FD
0x1400254ea  jle     loc_1400255C8
0x1400254f0  movzx   eax, ax
0x1400254f3  or      eax, 80070000h
0x1400254f8  jmp     loc_1400255C8
0x1400254fd  mov     rcx, [rbp+hKey]; hKey
0x140025501  call    cs:__imp_RegCloseKey
0x140025507  lea     rax, [rbp+var_10]
0x14002550b  mov     r9d, 2001Fh; samDesired
0x140025511  mov     r8d, 8; ulOptions
0x140025517  mov     qword ptr [rsp+70h+dwOptions], rax; phkResult
0x14002551c  mov     rdx, rbx; lpSubKey
0x14002551f  mov     rcx, rdi; hKey
0x140025522  call    cs:__imp_RegOpenKeyExW
0x140025528  test    eax, eax
0x14002552a  jnz     short loc_1400254EA
0x14002552c  mov     rcx, [rbp+var_10]; hKey
0x140025530  lea     rax, [rbp+cbData]
0x140025534  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x140025539  lea     r9, [rbp+Type]; lpType
0x14002553d  xor     r8d, r8d; lpReserved
0x140025540  mov     qword ptr [rsp+70h+dwOptions], 0; lpData
0x140025549  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140025550  call    cs:__imp_RegQueryValueExW
0x140025556  mov     ebx, eax
0x140025558  test    eax, eax
0x14002555a  jz      short loc_14002557C
0x14002555c  cmp     eax, 2
0x14002555f  jz      short loc_140025593
0x140025561  mov     rcx, [rbp+var_10]; hKey
0x140025565  call    cs:__imp_RegCloseKey
0x14002556b  test    ebx, ebx
0x14002556d  jle     short loc_140025578
0x14002556f  movzx   ebx, bx
0x140025572  or      ebx, 80070000h
0x140025578  mov     eax, ebx
0x14002557a  jmp     short loc_1400255C8
0x14002557c  cmp     [rbp+Type], 6
0x140025580  jnz     short loc_140025593
0x140025582  mov     rcx, [rbp+var_10]; hKey
0x140025586  call    cs:__imp_RegCloseKey
0x14002558c  mov     eax, 800705B8h
0x140025591  jmp     short loc_1400255C8
0x140025593  mov     eax, [rbp+arg_28]
0x140025596  mov     r9d, esi; dwType
0x140025599  mov     rcx, [rbp+var_10]; hKey
0x14002559d  xor     r8d, r8d; Reserved
0x1400255a0  mov     [rsp+70h+samDesired], eax; cbData
0x1400255a4  mov     rdx, r14; lpValueName
0x1400255a7  mov     rax, [rbp+lpData]
0x1400255ab  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x1400255b0  call    cs:__imp_RegSetValueExW
0x1400255b6  mov     rcx, [rbp+var_10]; hKey
0x1400255ba  mov     ebx, eax
0x1400255bc  call    cs:__imp_RegCloseKey
0x1400255c2  test    ebx, ebx
0x1400255c4  jnz     short loc_14002556D
0x1400255c6  xor     eax, eax
0x1400255c8  add     rsp, 70h
0x1400255cc  pop     r14
0x1400255ce  pop     rdi
0x1400255cf  pop     rsi
0x1400255d0  pop     rbx
0x1400255d1  pop     rbp
0x1400255d2  retn
```
