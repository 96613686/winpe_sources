# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x140009938`
- end: `0x140009966`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14000e16c`
- `0x14001b51c`
- `0x14001ed8c`
- `0x140020938`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000995b`
- `ADVAPI32!RegSetValueExW` at `0x14000995b`

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
0x140009938  mov     r11, rsp
0x14000993b  mov     [r11+18h], r8d
0x14000993f  sub     rsp, 38h
0x140009943  mov     rcx, [rcx]; hKey
0x140009946  lea     rax, [r11+18h]
0x14000994a  mov     r9d, 4; dwType
0x140009950  xor     r8d, r8d; Reserved
0x140009953  mov     [r11-10h], r9d
0x140009957  mov     [r11-18h], rax
0x14000995b  call    cs:__imp_RegSetValueExW
0x140009961  add     rsp, 38h
0x140009965  retn
```
