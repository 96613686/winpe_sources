# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x1401be090`
- end: `0x1401be224`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `404`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x1401bd918`

## callees

- `0x1401be090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be1f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be1f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be100`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be100`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be14e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be14e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401be127`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401be19d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401be1c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401be206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401be127`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401be19d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401be1c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401be206`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401be182`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401be182`

## string_xrefs

- `0x1401be17b`: `SymbolicLinkValue`

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
0x1401be090  push    rbp
0x1401be092  push    rbx
0x1401be093  push    rsi
0x1401be094  push    rdi
0x1401be095  push    r14
0x1401be097  mov     rbp, rsp
0x1401be09a  sub     rsp, 70h
0x1401be09e  lea     rax, [rbp+dwDisposition]
0x1401be0a2  mov     [rbp+hKey], 0
0x1401be0aa  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1401be0af  mov     esi, r9d
0x1401be0b2  lea     rax, [rbp+hKey]
0x1401be0b6  mov     [rbp+var_10], 0
0x1401be0be  mov     [rsp+70h+phkResult], rax; phkResult
0x1401be0c3  mov     r14, r8
0x1401be0c6  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401be0cf  xor     r9d, r9d; lpClass
0x1401be0d2  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x1401be0da  xor     r8d, r8d; Reserved
0x1401be0dd  mov     [rsp+70h+dwOptions], 1; dwOptions
0x1401be0e5  mov     rbx, rdx
0x1401be0e8  mov     rdi, rcx
0x1401be0eb  mov     [rbp+dwDisposition], 0
0x1401be0f2  mov     [rbp+Type], 0
0x1401be0f9  mov     [rbp+cbData], 0
0x1401be100  call    cs:__imp_RegCreateKeyExW
0x1401be107  nop     dword ptr [rax+rax+00h]
0x1401be10c  test    eax, eax
0x1401be10e  jz      short loc_1401BE123
0x1401be110  jle     loc_1401BE218
0x1401be116  movzx   eax, ax
0x1401be119  or      eax, 80070000h
0x1401be11e  jmp     loc_1401BE218
0x1401be123  mov     rcx, [rbp+hKey]; hKey
0x1401be127  call    cs:__imp_RegCloseKey
0x1401be12e  nop     dword ptr [rax+rax+00h]
0x1401be133  lea     rax, [rbp+var_10]
0x1401be137  mov     r9d, 2001Fh; samDesired
0x1401be13d  mov     r8d, 8; ulOptions
0x1401be143  mov     qword ptr [rsp+70h+dwOptions], rax; phkResult
0x1401be148  mov     rdx, rbx; lpSubKey
0x1401be14b  mov     rcx, rdi; hKey
0x1401be14e  call    cs:__imp_RegOpenKeyExW
0x1401be155  nop     dword ptr [rax+rax+00h]
0x1401be15a  test    eax, eax
0x1401be15c  jnz     short loc_1401BE110
0x1401be15e  mov     rcx, [rbp+var_10]; hKey
0x1401be162  lea     rax, [rbp+cbData]
0x1401be166  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x1401be16b  lea     r9, [rbp+Type]; lpType
0x1401be16f  xor     r8d, r8d; lpReserved
0x1401be172  mov     qword ptr [rsp+70h+dwOptions], 0; lpData
0x1401be17b  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1401be182  call    cs:__imp_RegQueryValueExW
0x1401be189  nop     dword ptr [rax+rax+00h]
0x1401be18e  mov     ebx, eax
0x1401be190  test    eax, eax
0x1401be192  jz      short loc_1401BE1BA
0x1401be194  cmp     eax, 2
0x1401be197  jz      short loc_1401BE1D7
0x1401be199  mov     rcx, [rbp+var_10]; hKey
0x1401be19d  call    cs:__imp_RegCloseKey
0x1401be1a4  nop     dword ptr [rax+rax+00h]
0x1401be1a9  test    ebx, ebx
0x1401be1ab  jle     short loc_1401BE1B6
0x1401be1ad  movzx   ebx, bx
0x1401be1b0  or      ebx, 80070000h
0x1401be1b6  mov     eax, ebx
0x1401be1b8  jmp     short loc_1401BE218
0x1401be1ba  cmp     [rbp+Type], 6
0x1401be1be  jnz     short loc_1401BE1D7
0x1401be1c0  mov     rcx, [rbp+var_10]; hKey
0x1401be1c4  call    cs:__imp_RegCloseKey
0x1401be1cb  nop     dword ptr [rax+rax+00h]
0x1401be1d0  mov     eax, 800705B8h
0x1401be1d5  jmp     short loc_1401BE218
0x1401be1d7  mov     eax, [rbp+arg_28]
0x1401be1da  mov     r9d, esi; dwType
0x1401be1dd  mov     rcx, [rbp+var_10]; hKey
0x1401be1e1  xor     r8d, r8d; Reserved
0x1401be1e4  mov     [rsp+70h+samDesired], eax; cbData
0x1401be1e8  mov     rdx, r14; lpValueName
0x1401be1eb  mov     rax, [rbp+lpData]
0x1401be1ef  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x1401be1f4  call    cs:__imp_RegSetValueExW
0x1401be1fb  nop     dword ptr [rax+rax+00h]
0x1401be200  mov     rcx, [rbp+var_10]; hKey
0x1401be204  mov     ebx, eax
0x1401be206  call    cs:__imp_RegCloseKey
0x1401be20d  nop     dword ptr [rax+rax+00h]
0x1401be212  test    ebx, ebx
0x1401be214  jnz     short loc_1401BE1AB
0x1401be216  xor     eax, eax
0x1401be218  add     rsp, 70h
0x1401be21c  pop     r14
0x1401be21e  pop     rdi
0x1401be21f  pop     rsi
0x1401be220  pop     rbx
0x1401be221  pop     rbp
0x1401be222  retn
```
