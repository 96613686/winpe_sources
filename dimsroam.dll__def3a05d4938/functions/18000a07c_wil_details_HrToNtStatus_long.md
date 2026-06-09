# wil::details::HrToNtStatus(long)

- ea: `0x18000a07c`
- end: `0x18000a238`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180007820`
- `0x1800078c0`
- `0x180007910`
- `0x1800079d0`
- `0x180009658`
- `0x18000a240`

## callees

- `0x18000a07c`

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
0x18000a07c  mov     eax, 800700EAh
0x18000a081  cmp     ecx, eax
0x18000a083  jg      loc_18000A158
0x18000a089  jz      loc_18000A14E
0x18000a08f  mov     eax, 80070057h
0x18000a094  cmp     ecx, eax
0x18000a096  jg      short loc_18000A102
0x18000a098  jz      short loc_18000A0F8
0x18000a09a  cmp     ecx, 80004005h
0x18000a0a0  jz      short loc_18000A0EE
0x18000a0a2  cmp     ecx, 80070001h
0x18000a0a8  jz      short loc_18000A0E4
0x18000a0aa  cmp     ecx, 80070002h
0x18000a0b0  jz      short loc_18000A0DA
0x18000a0b2  cmp     ecx, 80070003h
0x18000a0b8  jz      short loc_18000A0D0
0x18000a0ba  cmp     ecx, 8007000Eh
0x18000a0c0  jnz     loc_18000A1DD
0x18000a0c6  mov     ecx, 0C0000017h
0x18000a0cb  jmp     loc_18000A235
0x18000a0d0  mov     ecx, 0C000003Ah
0x18000a0d5  jmp     loc_18000A235
0x18000a0da  mov     ecx, 0C0000034h
0x18000a0df  jmp     loc_18000A235
0x18000a0e4  mov     ecx, 0C0000002h
0x18000a0e9  jmp     loc_18000A235
0x18000a0ee  mov     ecx, 0C0000001h
0x18000a0f3  jmp     loc_18000A235
0x18000a0f8  mov     ecx, 0C000000Dh
0x18000a0fd  jmp     loc_18000A235
0x18000a102  cmp     ecx, 80070070h
0x18000a108  jz      short loc_18000A144
0x18000a10a  cmp     ecx, 8007007Ah
0x18000a110  jz      short loc_18000A13A
0x18000a112  cmp     ecx, 8007007Bh
0x18000a118  jz      short loc_18000A130
0x18000a11a  cmp     ecx, 8007007Eh
0x18000a120  jnz     loc_18000A1DD
0x18000a126  mov     ecx, 0C0000135h
0x18000a12b  jmp     loc_18000A235
0x18000a130  mov     ecx, 0C0000033h
0x18000a135  jmp     loc_18000A235
0x18000a13a  mov     ecx, 0C0000023h
0x18000a13f  jmp     loc_18000A235
0x18000a144  mov     ecx, 0C000007Fh
0x18000a149  jmp     loc_18000A235
0x18000a14e  mov     ecx, 80000005h
0x18000a153  jmp     loc_18000A235
0x18000a158  mov     eax, 8007047Eh
0x18000a15d  cmp     ecx, eax
0x18000a15f  jg      short loc_18000A1C1
0x18000a161  jz      short loc_18000A1BA
0x18000a163  cmp     ecx, 80070216h
0x18000a169  jz      short loc_18000A1B3
0x18000a16b  cmp     ecx, 8007023Eh
0x18000a171  jz      short loc_18000A1A9
0x18000a173  cmp     ecx, 80070246h
0x18000a179  jz      short loc_18000A19F
0x18000a17b  cmp     ecx, 80070247h
0x18000a181  jz      short loc_18000A195
0x18000a183  cmp     ecx, 80070272h
0x18000a189  jnz     short loc_18000A1DD
0x18000a18b  mov     ecx, 0C0000273h
0x18000a190  jmp     loc_18000A235
0x18000a195  mov     ecx, 0C0000163h
0x18000a19a  jmp     loc_18000A235
0x18000a19f  mov     ecx, 0C0000161h
0x18000a1a4  jmp     loc_18000A235
0x18000a1a9  mov     ecx, 0C0000025h
0x18000a1ae  jmp     loc_18000A235
0x18000a1b3  mov     ecx, 0C0000095h
0x18000a1b8  jmp     short loc_18000A235
0x18000a1ba  mov     ecx, 0C0000059h
0x18000a1bf  jmp     short loc_18000A235
0x18000a1c1  cmp     ecx, 8007050Ch
0x18000a1c7  jz      short loc_18000A230
0x18000a1c9  cmp     ecx, 8007054Fh
0x18000a1cf  jz      short loc_18000A229
0x18000a1d1  cmp     ecx, 800705B9h
0x18000a1d7  jz      short loc_18000A222
0x18000a1d9  test    ecx, ecx
0x18000a1db  jz      short loc_18000A21E
0x18000a1dd  bt      ecx, 1Ch
0x18000a1e1  jnb     short loc_18000A1E9
0x18000a1e3  btr     ecx, 1Ch
0x18000a1e7  jmp     short loc_18000A235
0x18000a1e9  mov     eax, ecx
0x18000a1eb  and     eax, 1FFF0000h
0x18000a1f0  cmp     eax, 70000h
0x18000a1f5  jnz     short loc_18000A208
0x18000a1f7  movzx   ecx, cx
0x18000a1fa  mov     eax, ecx
0x18000a1fc  or      eax, 0C0070000h
0x18000a201  test    ecx, ecx
0x18000a203  cmovnz  ecx, eax
0x18000a206  jmp     short loc_18000A235
0x18000a208  cmp     eax, 90000h
0x18000a20d  jnz     short loc_18000A229
0x18000a20f  test    ecx, ecx
0x18000a211  jle     short loc_18000A235
0x18000a213  movzx   ecx, cx
0x18000a216  or      ecx, 0C0090000h
0x18000a21c  jmp     short loc_18000A235
0x18000a21e  xor     ecx, ecx
0x18000a220  jmp     short loc_18000A235
0x18000a222  mov     ecx, 0C000A083h
0x18000a227  jmp     short loc_18000A235
0x18000a229  mov     ecx, 0C00000E5h
0x18000a22e  jmp     short loc_18000A235
0x18000a230  mov     ecx, 0C000042Bh
0x18000a235  mov     eax, ecx
0x18000a237  retn
```
