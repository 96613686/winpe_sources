# CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)

- ea: `0x18001b11c`
- end: `0x18001b15c`
- name: `?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z`
- size: `64`
- prototype: `int(CSafeReg *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800181f0`
- `0x18001828c`
- `0x180018580`

## callees

- `0x18001b11c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001b13b`
- `ADVAPI32!RegSetValueExW` at `0x18001b13b`

## pseudocode

```c
__int64 __fastcall CSafeReg::SetValue(
        HKEY *this,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int8 *lpData,
        DWORD cbData)
{
  unsigned int v5; // ebx
  LSTATUS v6; // eax

  v5 = 0;
  v6 = RegSetValueExW(*this, a2, 0, 1u, lpData, cbData);
  if ( v6 )
  {
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
    else
      return (unsigned int)v6;
  }
  return v5;
}

```

## disassembly

```asm
0x18001b11c  push    rbx
0x18001b11e  sub     rsp, 30h
0x18001b122  mov     eax, [rsp+38h+arg_20]
0x18001b126  xor     ebx, ebx
0x18001b128  mov     rcx, [rcx]; hKey
0x18001b12b  xor     r8d, r8d; Reserved
0x18001b12e  mov     [rsp+38h+cbData], eax; cbData
0x18001b132  mov     [rsp+38h+lpData], r9; lpData
0x18001b137  lea     r9d, [rbx+1]; dwType
0x18001b13b  call    cs:__imp_RegSetValueExW
0x18001b141  test    eax, eax
0x18001b143  jz      short loc_18001B154
0x18001b145  jg      short loc_18001B14B
0x18001b147  mov     ebx, eax
0x18001b149  jmp     short loc_18001B154
0x18001b14b  movzx   ebx, ax
0x18001b14e  or      ebx, 80070000h
0x18001b154  mov     eax, ebx
0x18001b156  add     rsp, 30h
0x18001b15a  pop     rbx
0x18001b15b  retn
```
