# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x180029b74`
- end: `0x180029ba2`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180028cdc`
- `0x180028f00`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180029b97`
- `ADVAPI32!RegSetValueExW` at `0x180029b97`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetDWORDValue(HKEY *this, const unsigned __int16 *a2, int a3)
{
  int v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  return RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v4, 4u);
}

```

## disassembly

```asm
0x180029b74  mov     r11, rsp
0x180029b77  mov     [r11+18h], r8d
0x180029b7b  sub     rsp, 38h
0x180029b7f  mov     rcx, [rcx]; hKey
0x180029b82  lea     rax, [r11+18h]
0x180029b86  mov     r9d, 4; dwType
0x180029b8c  xor     r8d, r8d; Reserved
0x180029b8f  mov     [r11-10h], r9d
0x180029b93  mov     [r11-18h], rax
0x180029b97  call    cs:__imp_RegSetValueExW
0x180029b9d  add     rsp, 38h
0x180029ba1  retn
```
