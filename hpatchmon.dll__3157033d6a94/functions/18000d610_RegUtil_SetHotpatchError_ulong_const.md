# RegUtil::SetHotpatchError(ulong const &)

- ea: `0x18000d610`
- end: `0x18000d6af`
- name: `?SetHotpatchError@RegUtil@@SAJAEBK@Z`
- size: `159`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180009a80`
- `0x18000df40`
- `0x180010710`

## callees

- `0x18000d610`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d69c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d69c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d67e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d67e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d646`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d646`

## pseudocode

```c
__int64 __fastcall RegUtil::SetHotpatchError(BYTE *lpData)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegUtil::HOTPATCH_ENVIRONMENT_KEY, 0, 0x20006u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    v3 = 0;
    v4 = RegSetValueExW(hKey, RegUtil::HOTPATCH_ERROR_CTAC_KEY_NAME, 0, 4u, lpData, 4u);
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      else
        v3 = v4;
    }
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d610  mov     r11, rsp
0x18000d613  mov     [r11+8], rbx
0x18000d617  push    rdi
0x18000d618  sub     rsp, 30h
0x18000d61c  mov     rdx, cs:?HOTPATCH_ENVIRONMENT_KEY@RegUtil@@0QEBGEB; lpSubKey
0x18000d623  lea     rax, [r11+10h]
0x18000d627  mov     rdi, rcx
0x18000d62a  mov     [r11-18h], rax
0x18000d62e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d635  mov     qword ptr [r11+10h], 0
0x18000d63d  mov     r9d, 20006h; samDesired
0x18000d643  xor     r8d, r8d; ulOptions
0x18000d646  call    cs:__imp_RegOpenKeyExW
0x18000d64c  mov     ebx, eax
0x18000d64e  test    eax, eax
0x18000d650  jz      short loc_18000D65F
0x18000d652  jle     short loc_18000D6A2
0x18000d654  movzx   ebx, ax
0x18000d657  or      ebx, 80070000h
0x18000d65d  jmp     short loc_18000D6A2
0x18000d65f  mov     rdx, cs:?HOTPATCH_ERROR_CTAC_KEY_NAME@RegUtil@@0QEBGEB; lpValueName
0x18000d666  xor     ebx, ebx
0x18000d668  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d66d  xor     r8d, r8d; Reserved
0x18000d670  lea     r9d, [rbx+4]; dwType
0x18000d674  mov     [rsp+38h+cbData], r9d; cbData
0x18000d679  mov     [rsp+38h+lpData], rdi; lpData
0x18000d67e  call    cs:__imp_RegSetValueExW
0x18000d684  test    eax, eax
0x18000d686  jz      short loc_18000D697
0x18000d688  jg      short loc_18000D68E
0x18000d68a  mov     ebx, eax
0x18000d68c  jmp     short loc_18000D697
0x18000d68e  movzx   ebx, ax
0x18000d691  or      ebx, 80070000h
0x18000d697  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d69c  call    cs:__imp_RegCloseKey
0x18000d6a2  mov     eax, ebx
0x18000d6a4  mov     rbx, [rsp+38h+arg_0]
0x18000d6a9  add     rsp, 30h
0x18000d6ad  pop     rdi
0x18000d6ae  retn
```
