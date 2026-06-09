# wil::details::HrToNtStatus(long)

- ea: `0x18000355c`
- end: `0x180003718`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ba8`
- `0x180001c48`
- `0x180001c98`
- `0x180001d50`
- `0x180002b38`
- `0x180003720`

## callees

- `0x18000355c`

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
0x18000355c  mov     eax, 800700EAh
0x180003561  cmp     ecx, eax
0x180003563  jg      loc_180003638
0x180003569  jz      loc_18000362E
0x18000356f  mov     eax, 80070057h
0x180003574  cmp     ecx, eax
0x180003576  jg      short loc_1800035E2
0x180003578  jz      short loc_1800035D8
0x18000357a  cmp     ecx, 80004005h
0x180003580  jz      short loc_1800035CE
0x180003582  cmp     ecx, 80070001h
0x180003588  jz      short loc_1800035C4
0x18000358a  cmp     ecx, 80070002h
0x180003590  jz      short loc_1800035BA
0x180003592  cmp     ecx, 80070003h
0x180003598  jz      short loc_1800035B0
0x18000359a  cmp     ecx, 8007000Eh
0x1800035a0  jnz     loc_1800036BD
0x1800035a6  mov     ecx, 0C0000017h
0x1800035ab  jmp     loc_180003715
0x1800035b0  mov     ecx, 0C000003Ah
0x1800035b5  jmp     loc_180003715
0x1800035ba  mov     ecx, 0C0000034h
0x1800035bf  jmp     loc_180003715
0x1800035c4  mov     ecx, 0C0000002h
0x1800035c9  jmp     loc_180003715
0x1800035ce  mov     ecx, 0C0000001h
0x1800035d3  jmp     loc_180003715
0x1800035d8  mov     ecx, 0C000000Dh
0x1800035dd  jmp     loc_180003715
0x1800035e2  cmp     ecx, 80070070h
0x1800035e8  jz      short loc_180003624
0x1800035ea  cmp     ecx, 8007007Ah
0x1800035f0  jz      short loc_18000361A
0x1800035f2  cmp     ecx, 8007007Bh
0x1800035f8  jz      short loc_180003610
0x1800035fa  cmp     ecx, 8007007Eh
0x180003600  jnz     loc_1800036BD
0x180003606  mov     ecx, 0C0000135h
0x18000360b  jmp     loc_180003715
0x180003610  mov     ecx, 0C0000033h
0x180003615  jmp     loc_180003715
0x18000361a  mov     ecx, 0C0000023h
0x18000361f  jmp     loc_180003715
0x180003624  mov     ecx, 0C000007Fh
0x180003629  jmp     loc_180003715
0x18000362e  mov     ecx, 80000005h
0x180003633  jmp     loc_180003715
0x180003638  mov     eax, 8007047Eh
0x18000363d  cmp     ecx, eax
0x18000363f  jg      short loc_1800036A1
0x180003641  jz      short loc_18000369A
0x180003643  cmp     ecx, 80070216h
0x180003649  jz      short loc_180003693
0x18000364b  cmp     ecx, 8007023Eh
0x180003651  jz      short loc_180003689
0x180003653  cmp     ecx, 80070246h
0x180003659  jz      short loc_18000367F
0x18000365b  cmp     ecx, 80070247h
0x180003661  jz      short loc_180003675
0x180003663  cmp     ecx, 80070272h
0x180003669  jnz     short loc_1800036BD
0x18000366b  mov     ecx, 0C0000273h
0x180003670  jmp     loc_180003715
0x180003675  mov     ecx, 0C0000163h
0x18000367a  jmp     loc_180003715
0x18000367f  mov     ecx, 0C0000161h
0x180003684  jmp     loc_180003715
0x180003689  mov     ecx, 0C0000025h
0x18000368e  jmp     loc_180003715
0x180003693  mov     ecx, 0C0000095h
0x180003698  jmp     short loc_180003715
0x18000369a  mov     ecx, 0C0000059h
0x18000369f  jmp     short loc_180003715
0x1800036a1  cmp     ecx, 8007050Ch
0x1800036a7  jz      short loc_180003710
0x1800036a9  cmp     ecx, 8007054Fh
0x1800036af  jz      short loc_180003709
0x1800036b1  cmp     ecx, 800705B9h
0x1800036b7  jz      short loc_180003702
0x1800036b9  test    ecx, ecx
0x1800036bb  jz      short loc_1800036FE
0x1800036bd  bt      ecx, 1Ch
0x1800036c1  jnb     short loc_1800036C9
0x1800036c3  btr     ecx, 1Ch
0x1800036c7  jmp     short loc_180003715
0x1800036c9  mov     eax, ecx
0x1800036cb  and     eax, 1FFF0000h
0x1800036d0  cmp     eax, 70000h
0x1800036d5  jnz     short loc_1800036E8
0x1800036d7  movzx   ecx, cx
0x1800036da  mov     eax, ecx
0x1800036dc  or      eax, 0C0070000h
0x1800036e1  test    ecx, ecx
0x1800036e3  cmovnz  ecx, eax
0x1800036e6  jmp     short loc_180003715
0x1800036e8  cmp     eax, 90000h
0x1800036ed  jnz     short loc_180003709
0x1800036ef  test    ecx, ecx
0x1800036f1  jle     short loc_180003715
0x1800036f3  movzx   ecx, cx
0x1800036f6  or      ecx, 0C0090000h
0x1800036fc  jmp     short loc_180003715
0x1800036fe  xor     ecx, ecx
0x180003700  jmp     short loc_180003715
0x180003702  mov     ecx, 0C000A083h
0x180003707  jmp     short loc_180003715
0x180003709  mov     ecx, 0C00000E5h
0x18000370e  jmp     short loc_180003715
0x180003710  mov     ecx, 0C000042Bh
0x180003715  mov     eax, ecx
0x180003717  retn
```
