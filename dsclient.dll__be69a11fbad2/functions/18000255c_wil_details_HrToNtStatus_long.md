# wil::details::HrToNtStatus(long)

- ea: `0x18000255c`
- end: `0x180002718`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024d8`
- `0x180003ec0`
- `0x180003f38`
- `0x180003f88`
- `0x180005668`
- `0x1800061c8`

## callees

- `0x18000255c`

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
0x18000255c  mov     eax, 800700EAh
0x180002561  cmp     ecx, eax
0x180002563  jg      loc_180002638
0x180002569  jz      loc_18000262E
0x18000256f  mov     eax, 80070057h
0x180002574  cmp     ecx, eax
0x180002576  jg      short loc_1800025E2
0x180002578  jz      short loc_1800025D8
0x18000257a  cmp     ecx, 80004005h
0x180002580  jz      short loc_1800025CE
0x180002582  cmp     ecx, 80070001h
0x180002588  jz      short loc_1800025C4
0x18000258a  cmp     ecx, 80070002h
0x180002590  jz      short loc_1800025BA
0x180002592  cmp     ecx, 80070003h
0x180002598  jz      short loc_1800025B0
0x18000259a  cmp     ecx, 8007000Eh
0x1800025a0  jnz     loc_1800026BD
0x1800025a6  mov     ecx, 0C0000017h
0x1800025ab  jmp     loc_180002715
0x1800025b0  mov     ecx, 0C000003Ah
0x1800025b5  jmp     loc_180002715
0x1800025ba  mov     ecx, 0C0000034h
0x1800025bf  jmp     loc_180002715
0x1800025c4  mov     ecx, 0C0000002h
0x1800025c9  jmp     loc_180002715
0x1800025ce  mov     ecx, 0C0000001h
0x1800025d3  jmp     loc_180002715
0x1800025d8  mov     ecx, 0C000000Dh
0x1800025dd  jmp     loc_180002715
0x1800025e2  cmp     ecx, 80070070h
0x1800025e8  jz      short loc_180002624
0x1800025ea  cmp     ecx, 8007007Ah
0x1800025f0  jz      short loc_18000261A
0x1800025f2  cmp     ecx, 8007007Bh
0x1800025f8  jz      short loc_180002610
0x1800025fa  cmp     ecx, 8007007Eh
0x180002600  jnz     loc_1800026BD
0x180002606  mov     ecx, 0C0000135h
0x18000260b  jmp     loc_180002715
0x180002610  mov     ecx, 0C0000033h
0x180002615  jmp     loc_180002715
0x18000261a  mov     ecx, 0C0000023h
0x18000261f  jmp     loc_180002715
0x180002624  mov     ecx, 0C000007Fh
0x180002629  jmp     loc_180002715
0x18000262e  mov     ecx, 80000005h
0x180002633  jmp     loc_180002715
0x180002638  mov     eax, 8007047Eh
0x18000263d  cmp     ecx, eax
0x18000263f  jg      short loc_1800026A1
0x180002641  jz      short loc_18000269A
0x180002643  cmp     ecx, 80070216h
0x180002649  jz      short loc_180002693
0x18000264b  cmp     ecx, 8007023Eh
0x180002651  jz      short loc_180002689
0x180002653  cmp     ecx, 80070246h
0x180002659  jz      short loc_18000267F
0x18000265b  cmp     ecx, 80070247h
0x180002661  jz      short loc_180002675
0x180002663  cmp     ecx, 80070272h
0x180002669  jnz     short loc_1800026BD
0x18000266b  mov     ecx, 0C0000273h
0x180002670  jmp     loc_180002715
0x180002675  mov     ecx, 0C0000163h
0x18000267a  jmp     loc_180002715
0x18000267f  mov     ecx, 0C0000161h
0x180002684  jmp     loc_180002715
0x180002689  mov     ecx, 0C0000025h
0x18000268e  jmp     loc_180002715
0x180002693  mov     ecx, 0C0000095h
0x180002698  jmp     short loc_180002715
0x18000269a  mov     ecx, 0C0000059h
0x18000269f  jmp     short loc_180002715
0x1800026a1  cmp     ecx, 8007050Ch
0x1800026a7  jz      short loc_180002710
0x1800026a9  cmp     ecx, 8007054Fh
0x1800026af  jz      short loc_180002709
0x1800026b1  cmp     ecx, 800705B9h
0x1800026b7  jz      short loc_180002702
0x1800026b9  test    ecx, ecx
0x1800026bb  jz      short loc_1800026FE
0x1800026bd  bt      ecx, 1Ch
0x1800026c1  jnb     short loc_1800026C9
0x1800026c3  btr     ecx, 1Ch
0x1800026c7  jmp     short loc_180002715
0x1800026c9  mov     eax, ecx
0x1800026cb  and     eax, 1FFF0000h
0x1800026d0  cmp     eax, 70000h
0x1800026d5  jnz     short loc_1800026E8
0x1800026d7  movzx   ecx, cx
0x1800026da  mov     eax, ecx
0x1800026dc  or      eax, 0C0070000h
0x1800026e1  test    ecx, ecx
0x1800026e3  cmovnz  ecx, eax
0x1800026e6  jmp     short loc_180002715
0x1800026e8  cmp     eax, 90000h
0x1800026ed  jnz     short loc_180002709
0x1800026ef  test    ecx, ecx
0x1800026f1  jle     short loc_180002715
0x1800026f3  movzx   ecx, cx
0x1800026f6  or      ecx, 0C0090000h
0x1800026fc  jmp     short loc_180002715
0x1800026fe  xor     ecx, ecx
0x180002700  jmp     short loc_180002715
0x180002702  mov     ecx, 0C000A083h
0x180002707  jmp     short loc_180002715
0x180002709  mov     ecx, 0C00000E5h
0x18000270e  jmp     short loc_180002715
0x180002710  mov     ecx, 0C000042Bh
0x180002715  mov     eax, ecx
0x180002717  retn
```
