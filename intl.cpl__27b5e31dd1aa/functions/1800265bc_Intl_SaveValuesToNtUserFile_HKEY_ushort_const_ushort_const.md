# Intl_SaveValuesToNtUserFile(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800265bc`
- end: `0x180026654`
- name: `?Intl_SaveValuesToNtUserFile@@YAXPEAUHKEY__@@PEBG1@Z`
- size: `152`
- prototype: `void __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800261f0`

## callees

- `0x180024da4`
- `0x180024fdc`
- `0x180025078`
- `0x180025d38`
- `0x1800265bc`
- `0x180026df0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800265ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800265ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026633`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026633`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026648`

## pseudocode

```c
void __fastcall Intl_SaveValuesToNtUserFile(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rcx
  HKEY NtUserHive; // rax
  HKEY v5; // rbx
  const unsigned __int16 *v6; // rcx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  const unsigned __int16 *v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = a3;
  hKey = 0;
  if ( !RegOpenKeyExW(a1, L"Control Panel\\International", 0, 0x20019u, &hKey) )
  {
    LOBYTE(v8) = 0;
    NtUserHive = Intl_LoadNtUserHive(v3, L"Control Panel\\International", (char *)&v8);
    v5 = NtUserHive;
    if ( NtUserHive )
    {
      Intl_DeleteRegKeyValues(NtUserHive);
      Intl_DeleteRegSubKeys(v5);
      Intl_CreateRegTree(hKey, v5);
      RegCloseKey(v5);
      Intl_UnloadNtUserHive(v6, (unsigned __int8 *)&v8);
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x1800265bc  mov     r11, rsp
0x1800265bf  mov     [r11+18h], r8
0x1800265c3  mov     [r11+10h], rdx
0x1800265c7  push    rbx
0x1800265c8  sub     rsp, 30h
0x1800265cc  lea     rax, [r11+10h]
0x1800265d0  mov     qword ptr [r11+10h], 0
0x1800265d8  mov     r9d, 20019h; samDesired
0x1800265de  mov     [r11-18h], rax
0x1800265e2  xor     r8d, r8d; ulOptions
0x1800265e5  lea     rdx, ?c_szCPanelIntl@@3QBGB; "Control Panel\\International"
0x1800265ec  call    cs:__imp_RegOpenKeyExW
0x1800265f2  test    eax, eax
0x1800265f4  jnz     short loc_18002664E
0x1800265f6  lea     r8, [rsp+38h+arg_10]; unsigned __int8 *
0x1800265fb  mov     byte ptr [rsp+38h+arg_10], al
0x1800265ff  lea     rdx, ?c_szCPanelIntl@@3QBGB; "Control Panel\\International"
0x180026606  call    ?Intl_LoadNtUserHive@@YAPEAUHKEY__@@PEBG0PEAE@Z; Intl_LoadNtUserHive(ushort const *,ushort const *,uchar *)
0x18002660b  mov     rbx, rax
0x18002660e  test    rax, rax
0x180026611  jz      short loc_180026643
0x180026613  mov     rcx, rax; hKey
0x180026616  call    ?Intl_DeleteRegKeyValues@@YAXPEAUHKEY__@@@Z; Intl_DeleteRegKeyValues(HKEY__ *)
0x18002661b  mov     rcx, rbx; hKey
0x18002661e  call    ?Intl_DeleteRegSubKeys@@YAXPEAUHKEY__@@@Z; Intl_DeleteRegSubKeys(HKEY__ *)
0x180026623  mov     rcx, [rsp+38h+hKey]; HKEY
0x180026628  mov     rdx, rbx; HKEY
0x18002662b  call    ?Intl_CreateRegTree@@YAKPEAUHKEY__@@0@Z; Intl_CreateRegTree(HKEY__ *,HKEY__ *)
0x180026630  mov     rcx, rbx; hKey
0x180026633  call    cs:__imp_RegCloseKey
0x180026639  lea     rdx, [rsp+38h+arg_10]; unsigned __int8 *
0x18002663e  call    ?Intl_UnloadNtUserHive@@YAXPEBGPEAE@Z; Intl_UnloadNtUserHive(ushort const *,uchar *)
0x180026643  mov     rcx, [rsp+38h+hKey]; hKey
0x180026648  call    cs:__imp_RegCloseKey
0x18002664e  add     rsp, 30h
0x180026652  pop     rbx
0x180026653  retn
```
