# Intl_UnloadNtUserHive(ushort const *,uchar *)

- ea: `0x180026df0`
- end: `0x180026e39`
- name: `?Intl_UnloadNtUserHive@@YAXPEBGPEAE@Z`
- size: `73`
- prototype: `void(const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008184`
- `0x180025d38`
- `0x180026304`
- `0x1800265bc`

## callees

- `0x180026874`
- `0x180026df0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180026e1c`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180026e1c`

## string_xrefs

- `0x180026e0e`: `TempKey`
- `0x180026df9`: `SeRestorePrivilege`
- `0x180026e24`: `SeRestorePrivilege`

## pseudocode

```c
void __fastcall Intl_UnloadNtUserHive(const unsigned __int16 *a1, char *a2)
{
  if ( (int)Intl_SetPrivilegeAccessToken(L"SeRestorePrivilege", 1, (bool *)a2) >= 0 )
  {
    RegUnLoadKeyW(HKEY_USERS, L"TempKey");
    Intl_SetPrivilegeAccessToken(L"SeRestorePrivilege", *a2, (bool *)a2);
  }
}

```

## disassembly

```asm
0x180026df0  push    rbx
0x180026df2  sub     rsp, 20h
0x180026df6  mov     rbx, rdx
0x180026df9  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180026e00  mov     r8, rdx; unsigned __int8 *
0x180026e03  mov     dl, 1; unsigned __int8
0x180026e05  call    ?Intl_SetPrivilegeAccessToken@@YAKPEBGEPEAE@Z; Intl_SetPrivilegeAccessToken(ushort const *,uchar,uchar *)
0x180026e0a  test    eax, eax
0x180026e0c  js      short loc_180026E33
0x180026e0e  lea     rdx, aTempkey; "TempKey"
0x180026e15  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180026e1c  call    cs:__imp_RegUnLoadKeyW
0x180026e22  mov     dl, [rbx]; unsigned __int8
0x180026e24  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180026e2b  mov     r8, rbx; unsigned __int8 *
0x180026e2e  call    ?Intl_SetPrivilegeAccessToken@@YAKPEBGEPEAE@Z; Intl_SetPrivilegeAccessToken(ushort const *,uchar,uchar *)
0x180026e33  add     rsp, 20h
0x180026e37  pop     rbx
0x180026e38  retn
```
