# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x180044010`
- end: `0x18004403e`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001a984`
- `0x18003d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044033`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044033`

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
0x180044010  mov     r11, rsp
0x180044013  mov     [r11+18h], r8d
0x180044017  sub     rsp, 38h
0x18004401b  mov     rcx, [rcx]; hKey
0x18004401e  lea     rax, [r11+18h]
0x180044022  mov     r9d, 4; dwType
0x180044028  xor     r8d, r8d; Reserved
0x18004402b  mov     [r11-10h], r9d
0x18004402f  mov     [r11-18h], rax
0x180044033  call    cs:__imp_RegSetValueExW
0x180044039  add     rsp, 38h
0x18004403d  retn
```
