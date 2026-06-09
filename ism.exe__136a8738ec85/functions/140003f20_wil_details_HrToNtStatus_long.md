# wil::details::HrToNtStatus(long)

- ea: `0x140003f20`
- end: `0x1400040dc`
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
- `0x140002280`
- `0x1400034f8`
- `0x1400040e4`

## callees

- `0x140003f20`

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
0x140003f20  mov     eax, 800700EAh
0x140003f25  cmp     ecx, eax
0x140003f27  jg      loc_140003FFC
0x140003f2d  jz      loc_140003FF2
0x140003f33  mov     eax, 80070057h
0x140003f38  cmp     ecx, eax
0x140003f3a  jg      short loc_140003FA6
0x140003f3c  jz      short loc_140003F9C
0x140003f3e  cmp     ecx, 80004005h
0x140003f44  jz      short loc_140003F92
0x140003f46  cmp     ecx, 80070001h
0x140003f4c  jz      short loc_140003F88
0x140003f4e  cmp     ecx, 80070002h
0x140003f54  jz      short loc_140003F7E
0x140003f56  cmp     ecx, 80070003h
0x140003f5c  jz      short loc_140003F74
0x140003f5e  cmp     ecx, 8007000Eh
0x140003f64  jnz     loc_140004081
0x140003f6a  mov     ecx, 0C0000017h
0x140003f6f  jmp     loc_1400040D9
0x140003f74  mov     ecx, 0C000003Ah
0x140003f79  jmp     loc_1400040D9
0x140003f7e  mov     ecx, 0C0000034h
0x140003f83  jmp     loc_1400040D9
0x140003f88  mov     ecx, 0C0000002h
0x140003f8d  jmp     loc_1400040D9
0x140003f92  mov     ecx, 0C0000001h
0x140003f97  jmp     loc_1400040D9
0x140003f9c  mov     ecx, 0C000000Dh
0x140003fa1  jmp     loc_1400040D9
0x140003fa6  cmp     ecx, 80070070h
0x140003fac  jz      short loc_140003FE8
0x140003fae  cmp     ecx, 8007007Ah
0x140003fb4  jz      short loc_140003FDE
0x140003fb6  cmp     ecx, 8007007Bh
0x140003fbc  jz      short loc_140003FD4
0x140003fbe  cmp     ecx, 8007007Eh
0x140003fc4  jnz     loc_140004081
0x140003fca  mov     ecx, 0C0000135h
0x140003fcf  jmp     loc_1400040D9
0x140003fd4  mov     ecx, 0C0000033h
0x140003fd9  jmp     loc_1400040D9
0x140003fde  mov     ecx, 0C0000023h
0x140003fe3  jmp     loc_1400040D9
0x140003fe8  mov     ecx, 0C000007Fh
0x140003fed  jmp     loc_1400040D9
0x140003ff2  mov     ecx, 80000005h
0x140003ff7  jmp     loc_1400040D9
0x140003ffc  mov     eax, 8007047Eh
0x140004001  cmp     ecx, eax
0x140004003  jg      short loc_140004065
0x140004005  jz      short loc_14000405E
0x140004007  cmp     ecx, 80070216h
0x14000400d  jz      short loc_140004057
0x14000400f  cmp     ecx, 8007023Eh
0x140004015  jz      short loc_14000404D
0x140004017  cmp     ecx, 80070246h
0x14000401d  jz      short loc_140004043
0x14000401f  cmp     ecx, 80070247h
0x140004025  jz      short loc_140004039
0x140004027  cmp     ecx, 80070272h
0x14000402d  jnz     short loc_140004081
0x14000402f  mov     ecx, 0C0000273h
0x140004034  jmp     loc_1400040D9
0x140004039  mov     ecx, 0C0000163h
0x14000403e  jmp     loc_1400040D9
0x140004043  mov     ecx, 0C0000161h
0x140004048  jmp     loc_1400040D9
0x14000404d  mov     ecx, 0C0000025h
0x140004052  jmp     loc_1400040D9
0x140004057  mov     ecx, 0C0000095h
0x14000405c  jmp     short loc_1400040D9
0x14000405e  mov     ecx, 0C0000059h
0x140004063  jmp     short loc_1400040D9
0x140004065  cmp     ecx, 8007050Ch
0x14000406b  jz      short loc_1400040D4
0x14000406d  cmp     ecx, 8007054Fh
0x140004073  jz      short loc_1400040CD
0x140004075  cmp     ecx, 800705B9h
0x14000407b  jz      short loc_1400040C6
0x14000407d  test    ecx, ecx
0x14000407f  jz      short loc_1400040C2
0x140004081  bt      ecx, 1Ch
0x140004085  jnb     short loc_14000408D
0x140004087  btr     ecx, 1Ch
0x14000408b  jmp     short loc_1400040D9
0x14000408d  mov     eax, ecx
0x14000408f  and     eax, 1FFF0000h
0x140004094  cmp     eax, 70000h
0x140004099  jnz     short loc_1400040AC
0x14000409b  movzx   ecx, cx
0x14000409e  mov     eax, ecx
0x1400040a0  or      eax, 0C0070000h
0x1400040a5  test    ecx, ecx
0x1400040a7  cmovnz  ecx, eax
0x1400040aa  jmp     short loc_1400040D9
0x1400040ac  cmp     eax, 90000h
0x1400040b1  jnz     short loc_1400040CD
0x1400040b3  test    ecx, ecx
0x1400040b5  jle     short loc_1400040D9
0x1400040b7  movzx   ecx, cx
0x1400040ba  or      ecx, 0C0090000h
0x1400040c0  jmp     short loc_1400040D9
0x1400040c2  xor     ecx, ecx
0x1400040c4  jmp     short loc_1400040D9
0x1400040c6  mov     ecx, 0C000A083h
0x1400040cb  jmp     short loc_1400040D9
0x1400040cd  mov     ecx, 0C00000E5h
0x1400040d2  jmp     short loc_1400040D9
0x1400040d4  mov     ecx, 0C000042Bh
0x1400040d9  mov     eax, ecx
0x1400040db  retn
```
