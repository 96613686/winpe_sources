# ATL::CRegKey::SetDWORDValue(wchar_t const *,ulong)

- ea: `0x1800115c4`
- end: `0x1800115f2`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEB_WK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000b6ac`
- `0x18002b2e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800115e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800115e7`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetDWORDValue(HKEY *this, const wchar_t *a2, int a3)
{
  int v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  return RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v4, 4u);
}

```

## disassembly

```asm
0x1800115c4  mov     r11, rsp
0x1800115c7  mov     [r11+18h], r8d
0x1800115cb  sub     rsp, 38h
0x1800115cf  mov     rcx, [rcx]; hKey
0x1800115d2  lea     rax, [r11+18h]
0x1800115d6  mov     r9d, 4; dwType
0x1800115dc  xor     r8d, r8d; Reserved
0x1800115df  mov     [r11-10h], r9d
0x1800115e3  mov     [r11-18h], rax
0x1800115e7  call    cs:__imp_RegSetValueExW
0x1800115ed  add     rsp, 38h
0x1800115f1  retn
```
