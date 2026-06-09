# wil::details::HrToNtStatus(long)

- ea: `0x180006518`
- end: `0x1800066d4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003354`
- `0x1800033cc`
- `0x18000344c`
- `0x18000349c`
- `0x180005ae8`
- `0x180006a0c`

## callees

- `0x180006518`

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
0x180006518  mov     eax, 800700EAh
0x18000651d  cmp     ecx, eax
0x18000651f  jg      loc_1800065F4
0x180006525  jz      loc_1800065EA
0x18000652b  mov     eax, 80070057h
0x180006530  cmp     ecx, eax
0x180006532  jg      short loc_18000659E
0x180006534  jz      short loc_180006594
0x180006536  cmp     ecx, 80004005h
0x18000653c  jz      short loc_18000658A
0x18000653e  cmp     ecx, 80070001h
0x180006544  jz      short loc_180006580
0x180006546  cmp     ecx, 80070002h
0x18000654c  jz      short loc_180006576
0x18000654e  cmp     ecx, 80070003h
0x180006554  jz      short loc_18000656C
0x180006556  cmp     ecx, 8007000Eh
0x18000655c  jnz     loc_180006679
0x180006562  mov     ecx, 0C0000017h
0x180006567  jmp     loc_1800066D1
0x18000656c  mov     ecx, 0C000003Ah
0x180006571  jmp     loc_1800066D1
0x180006576  mov     ecx, 0C0000034h
0x18000657b  jmp     loc_1800066D1
0x180006580  mov     ecx, 0C0000002h
0x180006585  jmp     loc_1800066D1
0x18000658a  mov     ecx, 0C0000001h
0x18000658f  jmp     loc_1800066D1
0x180006594  mov     ecx, 0C000000Dh
0x180006599  jmp     loc_1800066D1
0x18000659e  cmp     ecx, 80070070h
0x1800065a4  jz      short loc_1800065E0
0x1800065a6  cmp     ecx, 8007007Ah
0x1800065ac  jz      short loc_1800065D6
0x1800065ae  cmp     ecx, 8007007Bh
0x1800065b4  jz      short loc_1800065CC
0x1800065b6  cmp     ecx, 8007007Eh
0x1800065bc  jnz     loc_180006679
0x1800065c2  mov     ecx, 0C0000135h
0x1800065c7  jmp     loc_1800066D1
0x1800065cc  mov     ecx, 0C0000033h
0x1800065d1  jmp     loc_1800066D1
0x1800065d6  mov     ecx, 0C0000023h
0x1800065db  jmp     loc_1800066D1
0x1800065e0  mov     ecx, 0C000007Fh
0x1800065e5  jmp     loc_1800066D1
0x1800065ea  mov     ecx, 80000005h
0x1800065ef  jmp     loc_1800066D1
0x1800065f4  mov     eax, 8007047Eh
0x1800065f9  cmp     ecx, eax
0x1800065fb  jg      short loc_18000665D
0x1800065fd  jz      short loc_180006656
0x1800065ff  cmp     ecx, 80070216h
0x180006605  jz      short loc_18000664F
0x180006607  cmp     ecx, 8007023Eh
0x18000660d  jz      short loc_180006645
0x18000660f  cmp     ecx, 80070246h
0x180006615  jz      short loc_18000663B
0x180006617  cmp     ecx, 80070247h
0x18000661d  jz      short loc_180006631
0x18000661f  cmp     ecx, 80070272h
0x180006625  jnz     short loc_180006679
0x180006627  mov     ecx, 0C0000273h
0x18000662c  jmp     loc_1800066D1
0x180006631  mov     ecx, 0C0000163h
0x180006636  jmp     loc_1800066D1
0x18000663b  mov     ecx, 0C0000161h
0x180006640  jmp     loc_1800066D1
0x180006645  mov     ecx, 0C0000025h
0x18000664a  jmp     loc_1800066D1
0x18000664f  mov     ecx, 0C0000095h
0x180006654  jmp     short loc_1800066D1
0x180006656  mov     ecx, 0C0000059h
0x18000665b  jmp     short loc_1800066D1
0x18000665d  cmp     ecx, 8007050Ch
0x180006663  jz      short loc_1800066CC
0x180006665  cmp     ecx, 8007054Fh
0x18000666b  jz      short loc_1800066C5
0x18000666d  cmp     ecx, 800705B9h
0x180006673  jz      short loc_1800066BE
0x180006675  test    ecx, ecx
0x180006677  jz      short loc_1800066BA
0x180006679  bt      ecx, 1Ch
0x18000667d  jnb     short loc_180006685
0x18000667f  btr     ecx, 1Ch
0x180006683  jmp     short loc_1800066D1
0x180006685  mov     eax, ecx
0x180006687  and     eax, 1FFF0000h
0x18000668c  cmp     eax, 70000h
0x180006691  jnz     short loc_1800066A4
0x180006693  movzx   ecx, cx
0x180006696  mov     eax, ecx
0x180006698  or      eax, 0C0070000h
0x18000669d  test    ecx, ecx
0x18000669f  cmovnz  ecx, eax
0x1800066a2  jmp     short loc_1800066D1
0x1800066a4  cmp     eax, 90000h
0x1800066a9  jnz     short loc_1800066C5
0x1800066ab  test    ecx, ecx
0x1800066ad  jle     short loc_1800066D1
0x1800066af  movzx   ecx, cx
0x1800066b2  or      ecx, 0C0090000h
0x1800066b8  jmp     short loc_1800066D1
0x1800066ba  xor     ecx, ecx
0x1800066bc  jmp     short loc_1800066D1
0x1800066be  mov     ecx, 0C000A083h
0x1800066c3  jmp     short loc_1800066D1
0x1800066c5  mov     ecx, 0C00000E5h
0x1800066ca  jmp     short loc_1800066D1
0x1800066cc  mov     ecx, 0C000042Bh
0x1800066d1  mov     eax, ecx
0x1800066d3  retn
```
