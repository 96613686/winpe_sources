# CheckRegistryKeyForWarningCheckBox(int *)

- ea: `0x18002e54c`
- end: `0x18002e629`
- name: `?CheckRegistryKeyForWarningCheckBox@@YAJPEAH@Z`
- size: `221`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002eea4`

## callees

- `0x18002e54c`
- `0x18002ec84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e61a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e61a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e5d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e5d8`

## string_xrefs

- `0x18002e5c1`: `DisableLegacyPointAndPrintAdminSecurityWarning`

## pseudocode

```c
__int64 __fastcall CheckRegistryKeyForWarningCheckBox(int *a1)
{
  signed int v2; // ebx
  int v3; // eax
  LSTATUS v4; // eax
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  if ( a1 )
  {
    *a1 = 0;
    v3 = CreateRegistryKeyWithSecurity(1, &hKey);
    v2 = v3;
    if ( !v3 )
      goto LABEL_7;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_7:
      Data = 0;
      Type = 0;
      cbData = 4;
      v4 = RegQueryValueExW(hKey, L"DisableLegacyPointAndPrintAdminSecurityWarning", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( v4 )
      {
        if ( v4 > 0 )
          v2 = (unsigned __int16)v4 | 0x80070000;
        else
          v2 = v4;
        if ( v4 == 2 )
          v2 = 0;
      }
      else
      {
        v2 = 0;
        *a1 = Data != 0;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002e54c  push    rbx
0x18002e54e  push    rdi
0x18002e54f  sub     rsp, 38h
0x18002e553  mov     [rsp+48h+hKey], 0
0x18002e55c  mov     rdi, rcx
0x18002e55f  test    rcx, rcx
0x18002e562  jnz     short loc_18002E56E
0x18002e564  mov     ebx, 80070057h
0x18002e569  jmp     loc_18002E620
0x18002e56e  mov     dword ptr [rcx], 0
0x18002e574  lea     rdx, [rsp+48h+hKey]; HKEY *
0x18002e579  mov     ecx, 1; int
0x18002e57e  call    ?CreateRegistryKeyWithSecurity@@YAKHPEAPEAUHKEY__@@@Z; CreateRegistryKeyWithSecurity(int,HKEY__ * *)
0x18002e583  mov     ebx, eax
0x18002e585  test    eax, eax
0x18002e587  jz      short loc_18002E598
0x18002e589  jle     short loc_18002E594
0x18002e58b  movzx   ebx, ax
0x18002e58e  or      ebx, 80070000h
0x18002e594  test    ebx, ebx
0x18002e596  js      short loc_18002E60D
0x18002e598  mov     rcx, [rsp+48h+hKey]; hKey
0x18002e59d  lea     rax, [rsp+48h+cbData]
0x18002e5a2  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002e5a7  lea     r9, [rsp+48h+Type]; lpType
0x18002e5ac  lea     rax, [rsp+48h+Data]
0x18002e5b1  mov     [rsp+48h+Data], 0
0x18002e5b9  xor     r8d, r8d; lpReserved
0x18002e5bc  mov     [rsp+48h+lpData], rax; lpData
0x18002e5c1  lea     rdx, ValueName; "DisableLegacyPointAndPrintAdminSecurity"...
0x18002e5c8  mov     [rsp+48h+Type], 0
0x18002e5d0  mov     [rsp+48h+cbData], 4
0x18002e5d8  call    cs:__imp_RegQueryValueExW
0x18002e5de  test    eax, eax
0x18002e5e0  jnz     short loc_18002E5E6
0x18002e5e2  xor     ebx, ebx
0x18002e5e4  jmp     short loc_18002E5F9
0x18002e5e6  jg      short loc_18002E5EC
0x18002e5e8  mov     ebx, eax
0x18002e5ea  jmp     short loc_18002E5F5
0x18002e5ec  movzx   ebx, ax
0x18002e5ef  or      ebx, 80070000h
0x18002e5f5  test    ebx, ebx
0x18002e5f7  js      short loc_18002E606
0x18002e5f9  xor     eax, eax
0x18002e5fb  cmp     [rsp+48h+Data], eax
0x18002e5ff  setnz   al
0x18002e602  mov     [rdi], eax
0x18002e604  jmp     short loc_18002E60D
0x18002e606  cmp     eax, 2
0x18002e609  jnz     short loc_18002E60D
0x18002e60b  xor     ebx, ebx
0x18002e60d  cmp     [rsp+48h+hKey], 0
0x18002e613  jz      short loc_18002E620
0x18002e615  mov     rcx, [rsp+48h+hKey]; hKey
0x18002e61a  call    cs:__imp_RegCloseKey
0x18002e620  mov     eax, ebx
0x18002e622  add     rsp, 38h
0x18002e626  pop     rdi
0x18002e627  pop     rbx
0x18002e628  retn
```
