# CSafeReg::DeleteValue(ushort const *)

- ea: `0x18001adc0`
- end: `0x18001adec`
- name: `?DeleteValue@CSafeReg@@QEAAJPEBG@Z`
- size: `44`
- prototype: `__int64 __fastcall(CSafeReg *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180018dd0`

## callees

- `0x18001adc0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x18001adcb`
- `ADVAPI32!RegDeleteValueW` at `0x18001adcb`

## pseudocode

```c
__int64 __fastcall CSafeReg::DeleteValue(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax

  v2 = 0;
  v3 = RegDeleteValueW(*this, a2);
  if ( v3 )
  {
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
    else
      return (unsigned int)v3;
  }
  return v2;
}

```

## disassembly

```asm
0x18001adc0  push    rbx
0x18001adc2  sub     rsp, 20h
0x18001adc6  mov     rcx, [rcx]; hKey
0x18001adc9  xor     ebx, ebx
0x18001adcb  call    cs:__imp_RegDeleteValueW
0x18001add1  test    eax, eax
0x18001add3  jz      short loc_18001ADE4
0x18001add5  jg      short loc_18001ADDB
0x18001add7  mov     ebx, eax
0x18001add9  jmp     short loc_18001ADE4
0x18001addb  movzx   ebx, ax
0x18001adde  or      ebx, 80070000h
0x18001ade4  mov     eax, ebx
0x18001ade6  add     rsp, 20h
0x18001adea  pop     rbx
0x18001adeb  retn
```
