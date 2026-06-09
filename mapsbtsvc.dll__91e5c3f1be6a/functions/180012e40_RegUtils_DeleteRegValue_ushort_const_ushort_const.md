# RegUtils::DeleteRegValue(ushort const *,ushort const *)

- ea: `0x180012e40`
- end: `0x180012e7b`
- name: `?DeleteRegValue@RegUtils@@SAJPEBG0@Z`
- size: `59`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c440`

## callees

- `0x180012e40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180012e55`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180012e55`

## pseudocode

```c
__int64 __fastcall RegUtils::DeleteRegValue(LPCWSTR lpSubKey, const unsigned __int16 *a2)
{
  LSTATUS v2; // ecx

  v2 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"ActiveRequests");
  if ( v2 == 2 )
    return 0;
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180012e40  sub     rsp, 28h
0x180012e44  mov     rdx, rcx; lpSubKey
0x180012e47  lea     r8, ValueName; "ActiveRequests"
0x180012e4e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012e55  call    cs:__imp_RegDeleteKeyValueW
0x180012e5b  mov     ecx, eax
0x180012e5d  cmp     eax, 2
0x180012e60  jnz     short loc_180012E66
0x180012e62  xor     eax, eax
0x180012e64  jmp     short loc_180012E76
0x180012e66  test    ecx, ecx
0x180012e68  jg      short loc_180012E6E
0x180012e6a  mov     eax, ecx
0x180012e6c  jmp     short loc_180012E76
0x180012e6e  movzx   eax, cx
0x180012e71  or      eax, 80070000h
0x180012e76  add     rsp, 28h
0x180012e7a  retn
```
