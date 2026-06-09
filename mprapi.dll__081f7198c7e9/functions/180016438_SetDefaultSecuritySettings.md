# SetDefaultSecuritySettings

- ea: `0x180016438`
- end: `0x18001650c`
- name: `SetDefaultSecuritySettings`
- size: `212`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026b90`

## callees

- `0x180016438`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800164ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800164ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016478`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016478`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800164ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800164ab`

## string_xrefs

- `0x180016463`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 SetDefaultSecuritySettings()
{
  unsigned int v0; // ebx
  int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 4;
  cbData = 4;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
         0,
         0xF003Fu,
         &hKey);
  if ( !v0 )
  {
    Data = 0;
    if ( RegQueryValueExW(hKey, L"ServerFlags", 0, &Type, (LPBYTE)&Data, &cbData) || Type == 4 )
    {
      Data |= 0x602u;
      v0 = RegSetValueExW(hKey, L"ServerFlags", 0, 4u, (const BYTE *)&Data, 4u);
    }
    else
    {
      v0 = 87;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180016438  push    rbp
0x18001643a  push    rbx
0x18001643b  mov     rbp, rsp
0x18001643e  sub     rsp, 38h
0x180016442  lea     rax, [rbp+hKey]
0x180016446  mov     [rbp+hKey], 0
0x18001644e  mov     r9d, 0F003Fh; samDesired
0x180016454  mov     [rsp+38h+phkResult], rax; phkResult
0x180016459  xor     r8d, r8d; ulOptions
0x18001645c  mov     [rbp+Type], 4
0x180016463  lea     rdx, c_szRegKeyRemoteAccessParameters; "System\\CurrentControlSet\\Services\\Re"...
0x18001646a  mov     [rbp+cbData], 4
0x180016471  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016478  call    cs:__imp_RegOpenKeyExW
0x18001647e  mov     ebx, eax
0x180016480  test    eax, eax
0x180016482  jnz     short loc_1800164F4
0x180016484  mov     rcx, [rbp+hKey]; hKey
0x180016488  lea     r9, [rbp+Type]; lpType
0x18001648c  mov     [rbp+Data], eax
0x18001648f  lea     rdx, c_szServerFlags; "ServerFlags"
0x180016496  lea     rax, [rbp+cbData]
0x18001649a  xor     r8d, r8d; lpReserved
0x18001649d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800164a2  lea     rax, [rbp+Data]
0x1800164a6  mov     [rsp+38h+phkResult], rax; lpData
0x1800164ab  call    cs:__imp_RegQueryValueExW
0x1800164b1  test    eax, eax
0x1800164b3  jnz     short loc_1800164C0
0x1800164b5  cmp     [rbp+Type], 4
0x1800164b9  jz      short loc_1800164C0
0x1800164bb  lea     ebx, [rax+57h]
0x1800164be  jmp     short loc_1800164F4
0x1800164c0  or      [rbp+Data], 602h
0x1800164c7  lea     rax, [rbp+Data]
0x1800164cb  mov     rcx, [rbp+hKey]; hKey
0x1800164cf  lea     rdx, c_szServerFlags; "ServerFlags"
0x1800164d6  mov     dword ptr [rsp+38h+lpcbData], 4; cbData
0x1800164de  mov     r9d, 4; dwType
0x1800164e4  xor     r8d, r8d; Reserved
0x1800164e7  mov     [rsp+38h+phkResult], rax; lpData
0x1800164ec  call    cs:__imp_RegSetValueExW
0x1800164f2  mov     ebx, eax
0x1800164f4  mov     rcx, [rbp+hKey]; hKey
0x1800164f8  test    rcx, rcx
0x1800164fb  jz      short loc_180016503
0x1800164fd  call    cs:__imp_RegCloseKey
0x180016503  mov     eax, ebx
0x180016505  add     rsp, 38h
0x180016509  pop     rbx
0x18001650a  pop     rbp
0x18001650b  retn
```
