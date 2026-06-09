# _IsFaxInstalled

- ea: `0x1800054f0`
- end: `0x180005598`
- name: `_IsFaxInstalled`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005200`

## callees

- `0x1800054f0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000553b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000553b`
- `ADVAPI32!RegCloseKey` at `0x180005578`
- `ADVAPI32!RegCloseKey` at `0x180005578`
- `ADVAPI32!RegQueryValueExW` at `0x18000556b`
- `ADVAPI32!RegQueryValueExW` at `0x18000556b`

## string_xrefs

- `0x180005554`: `Installed`

## pseudocode

```c
LSTATUS __fastcall IsFaxInstalled(LSTATUS *a1)
{
  LSTATUS result; // eax
  LSTATUS v3; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = 0;
  cbData = 4;
  hKey = 0;
  *a1 = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Setup", 0, 0x20119u, &hKey);
  if ( !result )
  {
    v3 = RegQueryValueExW(hKey, L"Installed", 0, 0, (LPBYTE)&Data, &cbData);
    result = RegCloseKey(hKey);
    if ( !v3 )
    {
      result = Data != 0;
      *a1 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800054f0  mov     rax, rsp
0x1800054f3  mov     [rax+20h], rbx
0x1800054f7  push    rdi
0x1800054f8  sub     rsp, 30h
0x1800054fc  mov     dword ptr [rax+8], 0
0x180005503  mov     rdi, rcx
0x180005506  mov     dword ptr [rax+10h], 4
0x18000550d  mov     r9d, 20119h; samDesired
0x180005513  mov     qword ptr [rax+18h], 0
0x18000551b  lea     rax, [rax+18h]
0x18000551f  mov     dword ptr [rcx], 0
0x180005525  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Setup"
0x18000552c  xor     r8d, r8d; ulOptions
0x18000552f  mov     [rsp+38h+phkResult], rax; phkResult
0x180005534  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000553b  call    cs:__imp_RegOpenKeyExW
0x180005541  test    eax, eax
0x180005543  jnz     short loc_18000558D
0x180005545  mov     rcx, [rsp+38h+hKey]; hKey
0x18000554a  lea     rax, [rsp+38h+cbData]
0x18000554f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180005554  lea     rdx, ValueName; "Installed"
0x18000555b  lea     rax, [rsp+38h+Data]
0x180005560  xor     r9d, r9d; lpType
0x180005563  xor     r8d, r8d; lpReserved
0x180005566  mov     [rsp+38h+phkResult], rax; lpData
0x18000556b  call    cs:__imp_RegQueryValueExW
0x180005571  mov     rcx, [rsp+38h+hKey]; hKey
0x180005576  mov     ebx, eax
0x180005578  call    cs:__imp_RegCloseKey
0x18000557e  test    ebx, ebx
0x180005580  jnz     short loc_18000558D
0x180005582  xor     eax, eax
0x180005584  cmp     [rsp+38h+Data], eax
0x180005588  setnz   al
0x18000558b  mov     [rdi], eax
0x18000558d  mov     rbx, [rsp+38h+arg_18]
0x180005592  add     rsp, 30h
0x180005596  pop     rdi
0x180005597  retn
```
