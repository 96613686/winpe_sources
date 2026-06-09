# CSafeReg::SetDword(ushort const *,ulong)

- ea: `0x18001b0d0`
- end: `0x18001b115`
- name: `?SetDword@CSafeReg@@QEAAJPEBGK@Z`
- size: `69`
- prototype: `__int64 __fastcall(CSafeReg *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010f80`
- `0x180013370`

## callees

- `0x18001b0d0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001b0f4`
- `ADVAPI32!RegSetValueExW` at `0x18001b0f4`

## pseudocode

```c
__int64 __fastcall CSafeReg::SetDword(HKEY *this, const unsigned __int16 *a2, int a3)
{
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  int v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  v3 = 0;
  v4 = RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v6, 4u);
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
    else
      return (unsigned int)v4;
  }
  return v3;
}

```

## disassembly

```asm
0x18001b0d0  mov     r11, rsp
0x18001b0d3  mov     [r11+18h], r8d
0x18001b0d7  push    rbx
0x18001b0d8  sub     rsp, 30h
0x18001b0dc  mov     rcx, [rcx]; hKey
0x18001b0df  lea     rax, [r11+18h]
0x18001b0e3  xor     ebx, ebx
0x18001b0e5  xor     r8d, r8d; Reserved
0x18001b0e8  lea     r9d, [rbx+4]; dwType
0x18001b0ec  mov     [r11-10h], r9d
0x18001b0f0  mov     [r11-18h], rax
0x18001b0f4  call    cs:__imp_RegSetValueExW
0x18001b0fa  test    eax, eax
0x18001b0fc  jz      short loc_18001B10D
0x18001b0fe  jg      short loc_18001B104
0x18001b100  mov     ebx, eax
0x18001b102  jmp     short loc_18001B10D
0x18001b104  movzx   ebx, ax
0x18001b107  or      ebx, 80070000h
0x18001b10d  mov     eax, ebx
0x18001b10f  add     rsp, 30h
0x18001b113  pop     rbx
0x18001b114  retn
```
