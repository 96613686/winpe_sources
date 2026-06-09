# wil::details::HrToNtStatus(long)

- ea: `0x18000ddd0`
- end: `0x18000df8c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b83c`
- `0x18000b8dc`
- `0x18000b92c`
- `0x18000b9e4`
- `0x18000cf68`
- `0x18000e034`

## callees

- `0x18000ddd0`

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
0x18000ddd0  mov     eax, 800700EAh
0x18000ddd5  cmp     ecx, eax
0x18000ddd7  jg      loc_18000DEAC
0x18000dddd  jz      loc_18000DEA2
0x18000dde3  mov     eax, 80070057h
0x18000dde8  cmp     ecx, eax
0x18000ddea  jg      short loc_18000DE56
0x18000ddec  jz      short loc_18000DE4C
0x18000ddee  cmp     ecx, 80004005h
0x18000ddf4  jz      short loc_18000DE42
0x18000ddf6  cmp     ecx, 80070001h
0x18000ddfc  jz      short loc_18000DE38
0x18000ddfe  cmp     ecx, 80070002h
0x18000de04  jz      short loc_18000DE2E
0x18000de06  cmp     ecx, 80070003h
0x18000de0c  jz      short loc_18000DE24
0x18000de0e  cmp     ecx, 8007000Eh
0x18000de14  jnz     loc_18000DF31
0x18000de1a  mov     ecx, 0C0000017h
0x18000de1f  jmp     loc_18000DF89
0x18000de24  mov     ecx, 0C000003Ah
0x18000de29  jmp     loc_18000DF89
0x18000de2e  mov     ecx, 0C0000034h
0x18000de33  jmp     loc_18000DF89
0x18000de38  mov     ecx, 0C0000002h
0x18000de3d  jmp     loc_18000DF89
0x18000de42  mov     ecx, 0C0000001h
0x18000de47  jmp     loc_18000DF89
0x18000de4c  mov     ecx, 0C000000Dh
0x18000de51  jmp     loc_18000DF89
0x18000de56  cmp     ecx, 80070070h
0x18000de5c  jz      short loc_18000DE98
0x18000de5e  cmp     ecx, 8007007Ah
0x18000de64  jz      short loc_18000DE8E
0x18000de66  cmp     ecx, 8007007Bh
0x18000de6c  jz      short loc_18000DE84
0x18000de6e  cmp     ecx, 8007007Eh
0x18000de74  jnz     loc_18000DF31
0x18000de7a  mov     ecx, 0C0000135h
0x18000de7f  jmp     loc_18000DF89
0x18000de84  mov     ecx, 0C0000033h
0x18000de89  jmp     loc_18000DF89
0x18000de8e  mov     ecx, 0C0000023h
0x18000de93  jmp     loc_18000DF89
0x18000de98  mov     ecx, 0C000007Fh
0x18000de9d  jmp     loc_18000DF89
0x18000dea2  mov     ecx, 80000005h
0x18000dea7  jmp     loc_18000DF89
0x18000deac  mov     eax, 8007047Eh
0x18000deb1  cmp     ecx, eax
0x18000deb3  jg      short loc_18000DF15
0x18000deb5  jz      short loc_18000DF0E
0x18000deb7  cmp     ecx, 80070216h
0x18000debd  jz      short loc_18000DF07
0x18000debf  cmp     ecx, 8007023Eh
0x18000dec5  jz      short loc_18000DEFD
0x18000dec7  cmp     ecx, 80070246h
0x18000decd  jz      short loc_18000DEF3
0x18000decf  cmp     ecx, 80070247h
0x18000ded5  jz      short loc_18000DEE9
0x18000ded7  cmp     ecx, 80070272h
0x18000dedd  jnz     short loc_18000DF31
0x18000dedf  mov     ecx, 0C0000273h
0x18000dee4  jmp     loc_18000DF89
0x18000dee9  mov     ecx, 0C0000163h
0x18000deee  jmp     loc_18000DF89
0x18000def3  mov     ecx, 0C0000161h
0x18000def8  jmp     loc_18000DF89
0x18000defd  mov     ecx, 0C0000025h
0x18000df02  jmp     loc_18000DF89
0x18000df07  mov     ecx, 0C0000095h
0x18000df0c  jmp     short loc_18000DF89
0x18000df0e  mov     ecx, 0C0000059h
0x18000df13  jmp     short loc_18000DF89
0x18000df15  cmp     ecx, 8007050Ch
0x18000df1b  jz      short loc_18000DF84
0x18000df1d  cmp     ecx, 8007054Fh
0x18000df23  jz      short loc_18000DF7D
0x18000df25  cmp     ecx, 800705B9h
0x18000df2b  jz      short loc_18000DF76
0x18000df2d  test    ecx, ecx
0x18000df2f  jz      short loc_18000DF72
0x18000df31  bt      ecx, 1Ch
0x18000df35  jnb     short loc_18000DF3D
0x18000df37  btr     ecx, 1Ch
0x18000df3b  jmp     short loc_18000DF89
0x18000df3d  mov     eax, ecx
0x18000df3f  and     eax, 1FFF0000h
0x18000df44  cmp     eax, 70000h
0x18000df49  jnz     short loc_18000DF5C
0x18000df4b  movzx   ecx, cx
0x18000df4e  mov     eax, ecx
0x18000df50  or      eax, 0C0070000h
0x18000df55  test    ecx, ecx
0x18000df57  cmovnz  ecx, eax
0x18000df5a  jmp     short loc_18000DF89
0x18000df5c  cmp     eax, 90000h
0x18000df61  jnz     short loc_18000DF7D
0x18000df63  test    ecx, ecx
0x18000df65  jle     short loc_18000DF89
0x18000df67  movzx   ecx, cx
0x18000df6a  or      ecx, 0C0090000h
0x18000df70  jmp     short loc_18000DF89
0x18000df72  xor     ecx, ecx
0x18000df74  jmp     short loc_18000DF89
0x18000df76  mov     ecx, 0C000A083h
0x18000df7b  jmp     short loc_18000DF89
0x18000df7d  mov     ecx, 0C00000E5h
0x18000df82  jmp     short loc_18000DF89
0x18000df84  mov     ecx, 0C000042Bh
0x18000df89  mov     eax, ecx
0x18000df8b  retn
```
