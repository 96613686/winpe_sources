# wil::details::HrToNtStatus(long)

- ea: `0x140003e3c`
- end: `0x140003ff8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001fb4`
- `0x140002054`
- `0x1400020a4`
- `0x14000215c`
- `0x14000341c`
- `0x1400040dc`

## callees

- `0x140003e3c`

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
0x140003e3c  mov     eax, 800700EAh
0x140003e41  cmp     ecx, eax
0x140003e43  jg      loc_140003F18
0x140003e49  jz      loc_140003F0E
0x140003e4f  mov     eax, 80070057h
0x140003e54  cmp     ecx, eax
0x140003e56  jg      short loc_140003EC2
0x140003e58  jz      short loc_140003EB8
0x140003e5a  cmp     ecx, 80004005h
0x140003e60  jz      short loc_140003EAE
0x140003e62  cmp     ecx, 80070001h
0x140003e68  jz      short loc_140003EA4
0x140003e6a  cmp     ecx, 80070002h
0x140003e70  jz      short loc_140003E9A
0x140003e72  cmp     ecx, 80070003h
0x140003e78  jz      short loc_140003E90
0x140003e7a  cmp     ecx, 8007000Eh
0x140003e80  jnz     loc_140003F9D
0x140003e86  mov     ecx, 0C0000017h
0x140003e8b  jmp     loc_140003FF5
0x140003e90  mov     ecx, 0C000003Ah
0x140003e95  jmp     loc_140003FF5
0x140003e9a  mov     ecx, 0C0000034h
0x140003e9f  jmp     loc_140003FF5
0x140003ea4  mov     ecx, 0C0000002h
0x140003ea9  jmp     loc_140003FF5
0x140003eae  mov     ecx, 0C0000001h
0x140003eb3  jmp     loc_140003FF5
0x140003eb8  mov     ecx, 0C000000Dh
0x140003ebd  jmp     loc_140003FF5
0x140003ec2  cmp     ecx, 80070070h
0x140003ec8  jz      short loc_140003F04
0x140003eca  cmp     ecx, 8007007Ah
0x140003ed0  jz      short loc_140003EFA
0x140003ed2  cmp     ecx, 8007007Bh
0x140003ed8  jz      short loc_140003EF0
0x140003eda  cmp     ecx, 8007007Eh
0x140003ee0  jnz     loc_140003F9D
0x140003ee6  mov     ecx, 0C0000135h
0x140003eeb  jmp     loc_140003FF5
0x140003ef0  mov     ecx, 0C0000033h
0x140003ef5  jmp     loc_140003FF5
0x140003efa  mov     ecx, 0C0000023h
0x140003eff  jmp     loc_140003FF5
0x140003f04  mov     ecx, 0C000007Fh
0x140003f09  jmp     loc_140003FF5
0x140003f0e  mov     ecx, 80000005h
0x140003f13  jmp     loc_140003FF5
0x140003f18  mov     eax, 8007047Eh
0x140003f1d  cmp     ecx, eax
0x140003f1f  jg      short loc_140003F81
0x140003f21  jz      short loc_140003F7A
0x140003f23  cmp     ecx, 80070216h
0x140003f29  jz      short loc_140003F73
0x140003f2b  cmp     ecx, 8007023Eh
0x140003f31  jz      short loc_140003F69
0x140003f33  cmp     ecx, 80070246h
0x140003f39  jz      short loc_140003F5F
0x140003f3b  cmp     ecx, 80070247h
0x140003f41  jz      short loc_140003F55
0x140003f43  cmp     ecx, 80070272h
0x140003f49  jnz     short loc_140003F9D
0x140003f4b  mov     ecx, 0C0000273h
0x140003f50  jmp     loc_140003FF5
0x140003f55  mov     ecx, 0C0000163h
0x140003f5a  jmp     loc_140003FF5
0x140003f5f  mov     ecx, 0C0000161h
0x140003f64  jmp     loc_140003FF5
0x140003f69  mov     ecx, 0C0000025h
0x140003f6e  jmp     loc_140003FF5
0x140003f73  mov     ecx, 0C0000095h
0x140003f78  jmp     short loc_140003FF5
0x140003f7a  mov     ecx, 0C0000059h
0x140003f7f  jmp     short loc_140003FF5
0x140003f81  cmp     ecx, 8007050Ch
0x140003f87  jz      short loc_140003FF0
0x140003f89  cmp     ecx, 8007054Fh
0x140003f8f  jz      short loc_140003FE9
0x140003f91  cmp     ecx, 800705B9h
0x140003f97  jz      short loc_140003FE2
0x140003f99  test    ecx, ecx
0x140003f9b  jz      short loc_140003FDE
0x140003f9d  bt      ecx, 1Ch
0x140003fa1  jnb     short loc_140003FA9
0x140003fa3  btr     ecx, 1Ch
0x140003fa7  jmp     short loc_140003FF5
0x140003fa9  mov     eax, ecx
0x140003fab  and     eax, 1FFF0000h
0x140003fb0  cmp     eax, 70000h
0x140003fb5  jnz     short loc_140003FC8
0x140003fb7  movzx   ecx, cx
0x140003fba  mov     eax, ecx
0x140003fbc  or      eax, 0C0070000h
0x140003fc1  test    ecx, ecx
0x140003fc3  cmovnz  ecx, eax
0x140003fc6  jmp     short loc_140003FF5
0x140003fc8  cmp     eax, 90000h
0x140003fcd  jnz     short loc_140003FE9
0x140003fcf  test    ecx, ecx
0x140003fd1  jle     short loc_140003FF5
0x140003fd3  movzx   ecx, cx
0x140003fd6  or      ecx, 0C0090000h
0x140003fdc  jmp     short loc_140003FF5
0x140003fde  xor     ecx, ecx
0x140003fe0  jmp     short loc_140003FF5
0x140003fe2  mov     ecx, 0C000A083h
0x140003fe7  jmp     short loc_140003FF5
0x140003fe9  mov     ecx, 0C00000E5h
0x140003fee  jmp     short loc_140003FF5
0x140003ff0  mov     ecx, 0C000042Bh
0x140003ff5  mov     eax, ecx
0x140003ff7  retn
```
