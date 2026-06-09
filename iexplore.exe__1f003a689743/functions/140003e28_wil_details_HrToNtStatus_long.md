# wil::details::HrToNtStatus(long)

- ea: `0x140003e28`
- end: `0x140003fe4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002658`
- `0x1400026d0`
- `0x140002748`
- `0x140002798`
- `0x140003368`
- `0x14000422c`

## callees

- `0x140003e28`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x8007054F:
          goto LABEL_53;
        case 0x800705B9:
          LODWORD(this) = -1073700733;
          return (unsigned int)this;
        case 0:
          LODWORD(this) = 0;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          LODWORD(this) = -1073741735;
          return (unsigned int)this;
        case 0x80070216:
          LODWORD(this) = -1073741675;
          return (unsigned int)this;
        case 0x8007023E:
          LODWORD(this) = -1073741787;
          return (unsigned int)this;
        case 0x80070246:
          LODWORD(this) = -1073741471;
          return (unsigned int)this;
        case 0x80070247:
          LODWORD(this) = -1073741469;
          return (unsigned int)this;
        case 0x80070272:
          LODWORD(this) = -1073741197;
          return (unsigned int)this;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
    {
      LODWORD(this) = -2147483643;
      return (unsigned int)this;
    }
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          LODWORD(this) = -1073741697;
          return (unsigned int)this;
        case 0x8007007A:
          LODWORD(this) = -1073741789;
          return (unsigned int)this;
        case 0x8007007B:
          LODWORD(this) = -1073741773;
          return (unsigned int)this;
        case 0x8007007E:
          LODWORD(this) = -1073741515;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          LODWORD(this) = -1073741811;
          return (unsigned int)this;
        case 0x80004005:
          LODWORD(this) = -1073741823;
          return (unsigned int)this;
        case 0x80070001:
          LODWORD(this) = -1073741822;
          return (unsigned int)this;
        case 0x80070002:
          LODWORD(this) = -1073741772;
          return (unsigned int)this;
        case 0x80070003:
          LODWORD(this) = -1073741766;
          return (unsigned int)this;
        case 0x8007000E:
          LODWORD(this) = -1073741801;
          return (unsigned int)this;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
  {
    LODWORD(this) = (unsigned int)this & 0xEFFFFFFF;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    LODWORD(this) = (unsigned __int16)this;
    if ( (_WORD)this )
      LODWORD(this) = (unsigned __int16)this | 0xC0070000;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
  {
LABEL_53:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (int)this > 0 )
    LODWORD(this) = (unsigned __int16)this | 0xC0090000;
  return (unsigned int)this;
}

```

## disassembly

```asm
0x140003e28  mov     eax, 800700EAh
0x140003e2d  cmp     ecx, eax
0x140003e2f  jg      loc_140003F04
0x140003e35  jz      loc_140003EFA
0x140003e3b  mov     eax, 80070057h
0x140003e40  cmp     ecx, eax
0x140003e42  jg      short loc_140003EAE
0x140003e44  jz      short loc_140003EA4
0x140003e46  cmp     ecx, 80004005h
0x140003e4c  jz      short loc_140003E9A
0x140003e4e  cmp     ecx, 80070001h
0x140003e54  jz      short loc_140003E90
0x140003e56  cmp     ecx, 80070002h
0x140003e5c  jz      short loc_140003E86
0x140003e5e  cmp     ecx, 80070003h
0x140003e64  jz      short loc_140003E7C
0x140003e66  cmp     ecx, 8007000Eh
0x140003e6c  jnz     loc_140003F89
0x140003e72  mov     ecx, 0C0000017h
0x140003e77  jmp     loc_140003FE1
0x140003e7c  mov     ecx, 0C000003Ah
0x140003e81  jmp     loc_140003FE1
0x140003e86  mov     ecx, 0C0000034h
0x140003e8b  jmp     loc_140003FE1
0x140003e90  mov     ecx, 0C0000002h
0x140003e95  jmp     loc_140003FE1
0x140003e9a  mov     ecx, 0C0000001h
0x140003e9f  jmp     loc_140003FE1
0x140003ea4  mov     ecx, 0C000000Dh
0x140003ea9  jmp     loc_140003FE1
0x140003eae  cmp     ecx, 80070070h
0x140003eb4  jz      short loc_140003EF0
0x140003eb6  cmp     ecx, 8007007Ah
0x140003ebc  jz      short loc_140003EE6
0x140003ebe  cmp     ecx, 8007007Bh
0x140003ec4  jz      short loc_140003EDC
0x140003ec6  cmp     ecx, 8007007Eh
0x140003ecc  jnz     loc_140003F89
0x140003ed2  mov     ecx, 0C0000135h
0x140003ed7  jmp     loc_140003FE1
0x140003edc  mov     ecx, 0C0000033h
0x140003ee1  jmp     loc_140003FE1
0x140003ee6  mov     ecx, 0C0000023h
0x140003eeb  jmp     loc_140003FE1
0x140003ef0  mov     ecx, 0C000007Fh
0x140003ef5  jmp     loc_140003FE1
0x140003efa  mov     ecx, 80000005h
0x140003eff  jmp     loc_140003FE1
0x140003f04  mov     eax, 8007047Eh
0x140003f09  cmp     ecx, eax
0x140003f0b  jg      short loc_140003F6D
0x140003f0d  jz      short loc_140003F66
0x140003f0f  cmp     ecx, 80070216h
0x140003f15  jz      short loc_140003F5F
0x140003f17  cmp     ecx, 8007023Eh
0x140003f1d  jz      short loc_140003F55
0x140003f1f  cmp     ecx, 80070246h
0x140003f25  jz      short loc_140003F4B
0x140003f27  cmp     ecx, 80070247h
0x140003f2d  jz      short loc_140003F41
0x140003f2f  cmp     ecx, 80070272h
0x140003f35  jnz     short loc_140003F89
0x140003f37  mov     ecx, 0C0000273h
0x140003f3c  jmp     loc_140003FE1
0x140003f41  mov     ecx, 0C0000163h
0x140003f46  jmp     loc_140003FE1
0x140003f4b  mov     ecx, 0C0000161h
0x140003f50  jmp     loc_140003FE1
0x140003f55  mov     ecx, 0C0000025h
0x140003f5a  jmp     loc_140003FE1
0x140003f5f  mov     ecx, 0C0000095h
0x140003f64  jmp     short loc_140003FE1
0x140003f66  mov     ecx, 0C0000059h
0x140003f6b  jmp     short loc_140003FE1
0x140003f6d  cmp     ecx, 8007050Ch
0x140003f73  jz      short loc_140003FDC
0x140003f75  cmp     ecx, 8007054Fh
0x140003f7b  jz      short loc_140003FD5
0x140003f7d  cmp     ecx, 800705B9h
0x140003f83  jz      short loc_140003FCE
0x140003f85  test    ecx, ecx
0x140003f87  jz      short loc_140003FCA
0x140003f89  bt      ecx, 1Ch
0x140003f8d  jnb     short loc_140003F95
0x140003f8f  btr     ecx, 1Ch
0x140003f93  jmp     short loc_140003FE1
0x140003f95  mov     eax, ecx
0x140003f97  and     eax, 1FFF0000h
0x140003f9c  cmp     eax, 70000h
0x140003fa1  jnz     short loc_140003FB4
0x140003fa3  movzx   ecx, cx
0x140003fa6  mov     eax, ecx
0x140003fa8  or      eax, 0C0070000h
0x140003fad  test    ecx, ecx
0x140003faf  cmovnz  ecx, eax
0x140003fb2  jmp     short loc_140003FE1
0x140003fb4  cmp     eax, 90000h
0x140003fb9  jnz     short loc_140003FD5
0x140003fbb  test    ecx, ecx
0x140003fbd  jle     short loc_140003FE1
0x140003fbf  movzx   ecx, cx
0x140003fc2  or      ecx, 0C0090000h
0x140003fc8  jmp     short loc_140003FE1
0x140003fca  xor     ecx, ecx
0x140003fcc  jmp     short loc_140003FE1
0x140003fce  mov     ecx, 0C000A083h
0x140003fd3  jmp     short loc_140003FE1
0x140003fd5  mov     ecx, 0C00000E5h
0x140003fda  jmp     short loc_140003FE1
0x140003fdc  mov     ecx, 0C000042Bh
0x140003fe1  mov     eax, ecx
0x140003fe3  retn
```
