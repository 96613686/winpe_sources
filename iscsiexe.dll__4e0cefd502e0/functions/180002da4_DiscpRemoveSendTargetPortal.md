# DiscpRemoveSendTargetPortal

- ea: `0x180002da4`
- end: `0x180002e99`
- name: `DiscpRemoveSendTargetPortal`
- size: `245`
- prototype: `__int64 __fastcall(int *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004980`

## callees

- `0x180002da4`
- `0x180016de8`

## import_xrefs

- `ISCSIUM!DiscpOpenRegistryKey` at `0x180002de0`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x180002de0`
- `ISCSIUM!DiscpFreeMemory` at `0x180002e6f`
- `ISCSIUM!DiscpFreeMemory` at `0x180002e7a`
- `ISCSIUM!DiscpFreeMemory` at `0x180002e6f`
- `ISCSIUM!DiscpFreeMemory` at `0x180002e7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002e1e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002e58`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002e1e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002e58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e88`

## pseudocode

```c
__int64 __fastcall DiscpRemoveSendTargetPortal(int *a1, unsigned int a2, __int64 a3)
{
  unsigned int PortalName; // ebx
  LPCWSTR v8; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpValueName; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  lpValueName = 0;
  v8 = 0;
  hKey = 0;
  PortalName = DiscpOpenRegistryKey(
                 &hKey,
                 L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Send Targets",
                 131103);
  if ( !PortalName )
  {
    PortalName = DiscpCreatePortalName(a3, a1, a2, 0, (wchar_t **)&lpValueName);
    if ( !PortalName )
    {
      PortalName = RegDeleteValueW(hKey, lpValueName);
      if ( PortalName )
      {
        PortalName = DiscpCreatePortalName(a3, a1, a2, 1, (wchar_t **)&v8);
        if ( !PortalName )
        {
          PortalName = RegDeleteValueW(hKey, v8);
          if ( PortalName )
            PortalName = -268500925;
          DiscpFreeMemory(v8);
        }
      }
      DiscpFreeMemory(lpValueName);
    }
    RegCloseKey(hKey);
  }
  return PortalName;
}

```

## disassembly

```asm
0x180002da4  mov     rax, rsp
0x180002da7  push    rbx
0x180002da8  push    rbp
0x180002da9  push    rsi
0x180002daa  push    rdi
0x180002dab  sub     rsp, 48h
0x180002daf  mov     rdi, r8
0x180002db2  mov     qword ptr [rax-30h], 0
0x180002dba  mov     esi, edx
0x180002dbc  mov     qword ptr [rax-38h], 0
0x180002dc4  mov     rbp, rcx
0x180002dc7  mov     qword ptr [rax+20h], 0
0x180002dcf  mov     r8d, 2001Fh
0x180002dd5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180002ddc  lea     rcx, [rax+20h]
0x180002de0  call    cs:__imp_DiscpOpenRegistryKey
0x180002de6  mov     ebx, eax
0x180002de8  test    eax, eax
0x180002dea  jnz     loc_180002E8E
0x180002df0  lea     rax, [rsp+68h+lpValueName]
0x180002df5  xor     r9d, r9d
0x180002df8  mov     r8d, esi
0x180002dfb  mov     [rsp+68h+var_48], rax
0x180002e00  mov     rdx, rbp
0x180002e03  mov     rcx, rdi
0x180002e06  call    DiscpCreatePortalName
0x180002e0b  mov     ebx, eax
0x180002e0d  test    eax, eax
0x180002e0f  jnz     short loc_180002E80
0x180002e11  mov     rdx, [rsp+68h+lpValueName]; lpValueName
0x180002e16  mov     rcx, [rsp+68h+hKey]; hKey
0x180002e1e  call    cs:__imp_RegDeleteValueW
0x180002e24  mov     ebx, eax
0x180002e26  test    eax, eax
0x180002e28  jz      short loc_180002E75
0x180002e2a  lea     rax, [rsp+68h+var_38]
0x180002e2f  mov     r9b, 1
0x180002e32  mov     r8d, esi
0x180002e35  mov     [rsp+68h+var_48], rax
0x180002e3a  mov     rdx, rbp
0x180002e3d  mov     rcx, rdi
0x180002e40  call    DiscpCreatePortalName
0x180002e45  mov     ebx, eax
0x180002e47  test    eax, eax
0x180002e49  jnz     short loc_180002E75
0x180002e4b  mov     rdx, [rsp+68h+var_38]; lpValueName
0x180002e50  mov     rcx, [rsp+68h+hKey]; hKey
0x180002e58  call    cs:__imp_RegDeleteValueW
0x180002e5e  mov     rcx, [rsp+68h+var_38]
0x180002e63  mov     ebx, eax
0x180002e65  test    ebx, ebx
0x180002e67  mov     eax, 0EFFF0043h
0x180002e6c  cmovnz  ebx, eax
0x180002e6f  call    cs:__imp_DiscpFreeMemory
0x180002e75  mov     rcx, [rsp+68h+lpValueName]
0x180002e7a  call    cs:__imp_DiscpFreeMemory
0x180002e80  mov     rcx, [rsp+68h+hKey]; hKey
0x180002e88  call    cs:__imp_RegCloseKey
0x180002e8e  mov     eax, ebx
0x180002e90  add     rsp, 48h
0x180002e94  pop     rdi
0x180002e95  pop     rsi
0x180002e96  pop     rbp
0x180002e97  pop     rbx
0x180002e98  retn
```
