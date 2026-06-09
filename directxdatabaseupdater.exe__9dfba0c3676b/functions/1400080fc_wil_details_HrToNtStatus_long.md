# wil::details::HrToNtStatus(long)

- ea: `0x1400080fc`
- end: `0x1400082b8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1400042ec`
- `0x1400043e0`
- `0x140004460`
- `0x1400044e4`
- `0x14000453c`
- `0x140004bfc`
- `0x140007078`
- `0x140008600`
- `0x14000a270`
- `0x14000f5ec`
- `0x14000f760`
- `0x140014138`
- `0x140018808`
- `0x140018853`
- `0x140018916`
- `0x140018961`

## callees

- `0x1400080fc`

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
0x1400080fc  mov     eax, 800700EAh
0x140008101  cmp     ecx, eax
0x140008103  jg      loc_1400081D8
0x140008109  jz      loc_1400081CE
0x14000810f  mov     eax, 80070057h
0x140008114  cmp     ecx, eax
0x140008116  jg      short loc_140008182
0x140008118  jz      short loc_140008178
0x14000811a  cmp     ecx, 80004005h
0x140008120  jz      short loc_14000816E
0x140008122  cmp     ecx, 80070001h
0x140008128  jz      short loc_140008164
0x14000812a  cmp     ecx, 80070002h
0x140008130  jz      short loc_14000815A
0x140008132  cmp     ecx, 80070003h
0x140008138  jz      short loc_140008150
0x14000813a  cmp     ecx, 8007000Eh
0x140008140  jnz     loc_14000825D
0x140008146  mov     ecx, 0C0000017h
0x14000814b  jmp     loc_1400082B5
0x140008150  mov     ecx, 0C000003Ah
0x140008155  jmp     loc_1400082B5
0x14000815a  mov     ecx, 0C0000034h
0x14000815f  jmp     loc_1400082B5
0x140008164  mov     ecx, 0C0000002h
0x140008169  jmp     loc_1400082B5
0x14000816e  mov     ecx, 0C0000001h
0x140008173  jmp     loc_1400082B5
0x140008178  mov     ecx, 0C000000Dh
0x14000817d  jmp     loc_1400082B5
0x140008182  cmp     ecx, 80070070h
0x140008188  jz      short loc_1400081C4
0x14000818a  cmp     ecx, 8007007Ah
0x140008190  jz      short loc_1400081BA
0x140008192  cmp     ecx, 8007007Bh
0x140008198  jz      short loc_1400081B0
0x14000819a  cmp     ecx, 8007007Eh
0x1400081a0  jnz     loc_14000825D
0x1400081a6  mov     ecx, 0C0000135h
0x1400081ab  jmp     loc_1400082B5
0x1400081b0  mov     ecx, 0C0000033h
0x1400081b5  jmp     loc_1400082B5
0x1400081ba  mov     ecx, 0C0000023h
0x1400081bf  jmp     loc_1400082B5
0x1400081c4  mov     ecx, 0C000007Fh
0x1400081c9  jmp     loc_1400082B5
0x1400081ce  mov     ecx, 80000005h
0x1400081d3  jmp     loc_1400082B5
0x1400081d8  mov     eax, 8007047Eh
0x1400081dd  cmp     ecx, eax
0x1400081df  jg      short loc_140008241
0x1400081e1  jz      short loc_14000823A
0x1400081e3  cmp     ecx, 80070216h
0x1400081e9  jz      short loc_140008233
0x1400081eb  cmp     ecx, 8007023Eh
0x1400081f1  jz      short loc_140008229
0x1400081f3  cmp     ecx, 80070246h
0x1400081f9  jz      short loc_14000821F
0x1400081fb  cmp     ecx, 80070247h
0x140008201  jz      short loc_140008215
0x140008203  cmp     ecx, 80070272h
0x140008209  jnz     short loc_14000825D
0x14000820b  mov     ecx, 0C0000273h
0x140008210  jmp     loc_1400082B5
0x140008215  mov     ecx, 0C0000163h
0x14000821a  jmp     loc_1400082B5
0x14000821f  mov     ecx, 0C0000161h
0x140008224  jmp     loc_1400082B5
0x140008229  mov     ecx, 0C0000025h
0x14000822e  jmp     loc_1400082B5
0x140008233  mov     ecx, 0C0000095h
0x140008238  jmp     short loc_1400082B5
0x14000823a  mov     ecx, 0C0000059h
0x14000823f  jmp     short loc_1400082B5
0x140008241  cmp     ecx, 8007050Ch
0x140008247  jz      short loc_1400082B0
0x140008249  cmp     ecx, 8007054Fh
0x14000824f  jz      short loc_1400082A9
0x140008251  cmp     ecx, 800705B9h
0x140008257  jz      short loc_1400082A2
0x140008259  test    ecx, ecx
0x14000825b  jz      short loc_14000829E
0x14000825d  bt      ecx, 1Ch
0x140008261  jnb     short loc_140008269
0x140008263  btr     ecx, 1Ch
0x140008267  jmp     short loc_1400082B5
0x140008269  mov     eax, ecx
0x14000826b  and     eax, 1FFF0000h
0x140008270  cmp     eax, 70000h
0x140008275  jnz     short loc_140008288
0x140008277  movzx   ecx, cx
0x14000827a  mov     eax, ecx
0x14000827c  or      eax, 0C0070000h
0x140008281  test    ecx, ecx
0x140008283  cmovnz  ecx, eax
0x140008286  jmp     short loc_1400082B5
0x140008288  cmp     eax, 90000h
0x14000828d  jnz     short loc_1400082A9
0x14000828f  test    ecx, ecx
0x140008291  jle     short loc_1400082B5
0x140008293  movzx   ecx, cx
0x140008296  or      ecx, 0C0090000h
0x14000829c  jmp     short loc_1400082B5
0x14000829e  xor     ecx, ecx
0x1400082a0  jmp     short loc_1400082B5
0x1400082a2  mov     ecx, 0C000A083h
0x1400082a7  jmp     short loc_1400082B5
0x1400082a9  mov     ecx, 0C00000E5h
0x1400082ae  jmp     short loc_1400082B5
0x1400082b0  mov     ecx, 0C000042Bh
0x1400082b5  mov     eax, ecx
0x1400082b7  retn
```
