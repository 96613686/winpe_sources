# GetCustomCofigurationKey

- ea: `0x1800816c0`
- end: `0x18008175e`
- name: `GetCustomCofigurationKey`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180080ab4`
- `0x180081764`

## callees

- `0x1800816c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180081751`
- `ADVAPI32!RegCloseKey` at `0x180081751`
- `ADVAPI32!RegOpenKeyExA` at `0x1800816fd`
- `ADVAPI32!RegOpenKeyExA` at `0x1800816fd`
- `ADVAPI32!RegQueryValueExA` at `0x180081735`
- `ADVAPI32!RegQueryValueExA` at `0x180081735`

## string_xrefs

- `0x1800816ea`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
HKEY GetCustomCofigurationKey()
{
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "CustomParams", 0, 0, (LPBYTE)&Data, &cbData) && Data )
      return hKey;
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x1800816c0  mov     rax, rsp
0x1800816c3  sub     rsp, 38h
0x1800816c7  mov     qword ptr [rax+18h], 0
0x1800816cf  mov     r9d, 1; samDesired
0x1800816d5  mov     dword ptr [rax+10h], 0
0x1800816dc  xor     r8d, r8d; ulOptions
0x1800816df  mov     dword ptr [rax+8], 0
0x1800816e6  lea     rax, [rax+18h]
0x1800816ea  lea     rdx, aSystemCurrentc_28; "System\\CurrentControlSet\\Services\\ra"...
0x1800816f1  mov     [rsp+38h+phkResult], rax; phkResult
0x1800816f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800816fd  call    cs:__imp_RegOpenKeyExA
0x180081703  test    eax, eax
0x180081705  jnz     short loc_180081757
0x180081707  mov     rcx, [rsp+38h+hKey]; hKey
0x18008170c  lea     rax, [rsp+38h+cbData]
0x180081711  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180081716  lea     rdx, aCustomparams; "CustomParams"
0x18008171d  lea     rax, [rsp+38h+Data]
0x180081722  mov     [rsp+38h+cbData], 4
0x18008172a  xor     r9d, r9d; lpType
0x18008172d  mov     [rsp+38h+phkResult], rax; lpData
0x180081732  xor     r8d, r8d; lpReserved
0x180081735  call    cs:__imp_RegQueryValueExA
0x18008173b  test    eax, eax
0x18008173d  jnz     short loc_18008174C
0x18008173f  cmp     [rsp+38h+Data], eax
0x180081743  jz      short loc_18008174C
0x180081745  mov     rax, [rsp+38h+hKey]
0x18008174a  jmp     short loc_180081759
0x18008174c  mov     rcx, [rsp+38h+hKey]; hKey
0x180081751  call    cs:__imp_RegCloseKey
0x180081757  xor     eax, eax
0x180081759  add     rsp, 38h
0x18008175d  retn
```
