# wil::details::HrToNtStatus(long)

- ea: `0x14000275c`
- end: `0x140002918`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001dd4`
- `0x140001e74`
- `0x140002920`

## callees

- `0x14000275c`

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
0x14000275c  mov     eax, 800700EAh
0x140002761  cmp     ecx, eax
0x140002763  jg      loc_140002838
0x140002769  jz      loc_14000282E
0x14000276f  mov     eax, 80070057h
0x140002774  cmp     ecx, eax
0x140002776  jg      short loc_1400027E2
0x140002778  jz      short loc_1400027D8
0x14000277a  cmp     ecx, 80004005h
0x140002780  jz      short loc_1400027CE
0x140002782  cmp     ecx, 80070001h
0x140002788  jz      short loc_1400027C4
0x14000278a  cmp     ecx, 80070002h
0x140002790  jz      short loc_1400027BA
0x140002792  cmp     ecx, 80070003h
0x140002798  jz      short loc_1400027B0
0x14000279a  cmp     ecx, 8007000Eh
0x1400027a0  jnz     loc_1400028BD
0x1400027a6  mov     ecx, 0C0000017h
0x1400027ab  jmp     loc_140002915
0x1400027b0  mov     ecx, 0C000003Ah
0x1400027b5  jmp     loc_140002915
0x1400027ba  mov     ecx, 0C0000034h
0x1400027bf  jmp     loc_140002915
0x1400027c4  mov     ecx, 0C0000002h
0x1400027c9  jmp     loc_140002915
0x1400027ce  mov     ecx, 0C0000001h
0x1400027d3  jmp     loc_140002915
0x1400027d8  mov     ecx, 0C000000Dh
0x1400027dd  jmp     loc_140002915
0x1400027e2  cmp     ecx, 80070070h
0x1400027e8  jz      short loc_140002824
0x1400027ea  cmp     ecx, 8007007Ah
0x1400027f0  jz      short loc_14000281A
0x1400027f2  cmp     ecx, 8007007Bh
0x1400027f8  jz      short loc_140002810
0x1400027fa  cmp     ecx, 8007007Eh
0x140002800  jnz     loc_1400028BD
0x140002806  mov     ecx, 0C0000135h
0x14000280b  jmp     loc_140002915
0x140002810  mov     ecx, 0C0000033h
0x140002815  jmp     loc_140002915
0x14000281a  mov     ecx, 0C0000023h
0x14000281f  jmp     loc_140002915
0x140002824  mov     ecx, 0C000007Fh
0x140002829  jmp     loc_140002915
0x14000282e  mov     ecx, 80000005h
0x140002833  jmp     loc_140002915
0x140002838  mov     eax, 8007047Eh
0x14000283d  cmp     ecx, eax
0x14000283f  jg      short loc_1400028A1
0x140002841  jz      short loc_14000289A
0x140002843  cmp     ecx, 80070216h
0x140002849  jz      short loc_140002893
0x14000284b  cmp     ecx, 8007023Eh
0x140002851  jz      short loc_140002889
0x140002853  cmp     ecx, 80070246h
0x140002859  jz      short loc_14000287F
0x14000285b  cmp     ecx, 80070247h
0x140002861  jz      short loc_140002875
0x140002863  cmp     ecx, 80070272h
0x140002869  jnz     short loc_1400028BD
0x14000286b  mov     ecx, 0C0000273h
0x140002870  jmp     loc_140002915
0x140002875  mov     ecx, 0C0000163h
0x14000287a  jmp     loc_140002915
0x14000287f  mov     ecx, 0C0000161h
0x140002884  jmp     loc_140002915
0x140002889  mov     ecx, 0C0000025h
0x14000288e  jmp     loc_140002915
0x140002893  mov     ecx, 0C0000095h
0x140002898  jmp     short loc_140002915
0x14000289a  mov     ecx, 0C0000059h
0x14000289f  jmp     short loc_140002915
0x1400028a1  cmp     ecx, 8007050Ch
0x1400028a7  jz      short loc_140002910
0x1400028a9  cmp     ecx, 8007054Fh
0x1400028af  jz      short loc_140002909
0x1400028b1  cmp     ecx, 800705B9h
0x1400028b7  jz      short loc_140002902
0x1400028b9  test    ecx, ecx
0x1400028bb  jz      short loc_1400028FE
0x1400028bd  bt      ecx, 1Ch
0x1400028c1  jnb     short loc_1400028C9
0x1400028c3  btr     ecx, 1Ch
0x1400028c7  jmp     short loc_140002915
0x1400028c9  mov     eax, ecx
0x1400028cb  and     eax, 1FFF0000h
0x1400028d0  cmp     eax, 70000h
0x1400028d5  jnz     short loc_1400028E8
0x1400028d7  movzx   ecx, cx
0x1400028da  mov     eax, ecx
0x1400028dc  or      eax, 0C0070000h
0x1400028e1  test    ecx, ecx
0x1400028e3  cmovnz  ecx, eax
0x1400028e6  jmp     short loc_140002915
0x1400028e8  cmp     eax, 90000h
0x1400028ed  jnz     short loc_140002909
0x1400028ef  test    ecx, ecx
0x1400028f1  jle     short loc_140002915
0x1400028f3  movzx   ecx, cx
0x1400028f6  or      ecx, 0C0090000h
0x1400028fc  jmp     short loc_140002915
0x1400028fe  xor     ecx, ecx
0x140002900  jmp     short loc_140002915
0x140002902  mov     ecx, 0C000A083h
0x140002907  jmp     short loc_140002915
0x140002909  mov     ecx, 0C00000E5h
0x14000290e  jmp     short loc_140002915
0x140002910  mov     ecx, 0C000042Bh
0x140002915  mov     eax, ecx
0x140002917  retn
```
