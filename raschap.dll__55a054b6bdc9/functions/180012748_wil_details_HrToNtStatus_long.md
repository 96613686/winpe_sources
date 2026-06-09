# wil::details::HrToNtStatus(long)

- ea: `0x180012748`
- end: `0x180012904`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800126c4`
- `0x18001e7b8`
- `0x18001e830`
- `0x18001e880`
- `0x18001e8e4`
- `0x180020944`

## callees

- `0x180012748`

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
0x180012748  mov     eax, 800700EAh
0x18001274d  cmp     ecx, eax
0x18001274f  jg      loc_180012824
0x180012755  jz      loc_18001281A
0x18001275b  mov     eax, 80070057h
0x180012760  cmp     ecx, eax
0x180012762  jg      short loc_1800127CE
0x180012764  jz      short loc_1800127C4
0x180012766  cmp     ecx, 80004005h
0x18001276c  jz      short loc_1800127BA
0x18001276e  cmp     ecx, 80070001h
0x180012774  jz      short loc_1800127B0
0x180012776  cmp     ecx, 80070002h
0x18001277c  jz      short loc_1800127A6
0x18001277e  cmp     ecx, 80070003h
0x180012784  jz      short loc_18001279C
0x180012786  cmp     ecx, 8007000Eh
0x18001278c  jnz     loc_1800128A9
0x180012792  mov     ecx, 0C0000017h
0x180012797  jmp     loc_180012901
0x18001279c  mov     ecx, 0C000003Ah
0x1800127a1  jmp     loc_180012901
0x1800127a6  mov     ecx, 0C0000034h
0x1800127ab  jmp     loc_180012901
0x1800127b0  mov     ecx, 0C0000002h
0x1800127b5  jmp     loc_180012901
0x1800127ba  mov     ecx, 0C0000001h
0x1800127bf  jmp     loc_180012901
0x1800127c4  mov     ecx, 0C000000Dh
0x1800127c9  jmp     loc_180012901
0x1800127ce  cmp     ecx, 80070070h
0x1800127d4  jz      short loc_180012810
0x1800127d6  cmp     ecx, 8007007Ah
0x1800127dc  jz      short loc_180012806
0x1800127de  cmp     ecx, 8007007Bh
0x1800127e4  jz      short loc_1800127FC
0x1800127e6  cmp     ecx, 8007007Eh
0x1800127ec  jnz     loc_1800128A9
0x1800127f2  mov     ecx, 0C0000135h
0x1800127f7  jmp     loc_180012901
0x1800127fc  mov     ecx, 0C0000033h
0x180012801  jmp     loc_180012901
0x180012806  mov     ecx, 0C0000023h
0x18001280b  jmp     loc_180012901
0x180012810  mov     ecx, 0C000007Fh
0x180012815  jmp     loc_180012901
0x18001281a  mov     ecx, 80000005h
0x18001281f  jmp     loc_180012901
0x180012824  mov     eax, 8007047Eh
0x180012829  cmp     ecx, eax
0x18001282b  jg      short loc_18001288D
0x18001282d  jz      short loc_180012886
0x18001282f  cmp     ecx, 80070216h
0x180012835  jz      short loc_18001287F
0x180012837  cmp     ecx, 8007023Eh
0x18001283d  jz      short loc_180012875
0x18001283f  cmp     ecx, 80070246h
0x180012845  jz      short loc_18001286B
0x180012847  cmp     ecx, 80070247h
0x18001284d  jz      short loc_180012861
0x18001284f  cmp     ecx, 80070272h
0x180012855  jnz     short loc_1800128A9
0x180012857  mov     ecx, 0C0000273h
0x18001285c  jmp     loc_180012901
0x180012861  mov     ecx, 0C0000163h
0x180012866  jmp     loc_180012901
0x18001286b  mov     ecx, 0C0000161h
0x180012870  jmp     loc_180012901
0x180012875  mov     ecx, 0C0000025h
0x18001287a  jmp     loc_180012901
0x18001287f  mov     ecx, 0C0000095h
0x180012884  jmp     short loc_180012901
0x180012886  mov     ecx, 0C0000059h
0x18001288b  jmp     short loc_180012901
0x18001288d  cmp     ecx, 8007050Ch
0x180012893  jz      short loc_1800128FC
0x180012895  cmp     ecx, 8007054Fh
0x18001289b  jz      short loc_1800128F5
0x18001289d  cmp     ecx, 800705B9h
0x1800128a3  jz      short loc_1800128EE
0x1800128a5  test    ecx, ecx
0x1800128a7  jz      short loc_1800128EA
0x1800128a9  bt      ecx, 1Ch
0x1800128ad  jnb     short loc_1800128B5
0x1800128af  btr     ecx, 1Ch
0x1800128b3  jmp     short loc_180012901
0x1800128b5  mov     eax, ecx
0x1800128b7  and     eax, 1FFF0000h
0x1800128bc  cmp     eax, 70000h
0x1800128c1  jnz     short loc_1800128D4
0x1800128c3  movzx   ecx, cx
0x1800128c6  mov     eax, ecx
0x1800128c8  or      eax, 0C0070000h
0x1800128cd  test    ecx, ecx
0x1800128cf  cmovnz  ecx, eax
0x1800128d2  jmp     short loc_180012901
0x1800128d4  cmp     eax, 90000h
0x1800128d9  jnz     short loc_1800128F5
0x1800128db  test    ecx, ecx
0x1800128dd  jle     short loc_180012901
0x1800128df  movzx   ecx, cx
0x1800128e2  or      ecx, 0C0090000h
0x1800128e8  jmp     short loc_180012901
0x1800128ea  xor     ecx, ecx
0x1800128ec  jmp     short loc_180012901
0x1800128ee  mov     ecx, 0C000A083h
0x1800128f3  jmp     short loc_180012901
0x1800128f5  mov     ecx, 0C00000E5h
0x1800128fa  jmp     short loc_180012901
0x1800128fc  mov     ecx, 0C000042Bh
0x180012901  mov     eax, ecx
0x180012903  retn
```
