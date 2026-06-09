# wil::details::HrToNtStatus(long)

- ea: `0x1400053bc`
- end: `0x140005578`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x1400024b8`
- `0x140002568`
- `0x1400025c0`
- `0x14000268c`
- `0x140002bb8`
- `0x140004988`
- `0x140006b60`
- `0x140010dfc`
- `0x140010f4c`
- `0x140011008`
- `0x140011080`
- `0x140011148`
- `0x140015a90`
- `0x14001ab12`
- `0x14001ab7d`
- `0x14001ac46`
- `0x14001acb1`

## callees

- `0x1400053bc`

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
0x1400053bc  mov     eax, 800700EAh
0x1400053c1  cmp     ecx, eax
0x1400053c3  jg      loc_140005498
0x1400053c9  jz      loc_14000548E
0x1400053cf  mov     eax, 80070057h
0x1400053d4  cmp     ecx, eax
0x1400053d6  jg      short loc_140005442
0x1400053d8  jz      short loc_140005438
0x1400053da  cmp     ecx, 80004005h
0x1400053e0  jz      short loc_14000542E
0x1400053e2  cmp     ecx, 80070001h
0x1400053e8  jz      short loc_140005424
0x1400053ea  cmp     ecx, 80070002h
0x1400053f0  jz      short loc_14000541A
0x1400053f2  cmp     ecx, 80070003h
0x1400053f8  jz      short loc_140005410
0x1400053fa  cmp     ecx, 8007000Eh
0x140005400  jnz     loc_14000551D
0x140005406  mov     ecx, 0C0000017h
0x14000540b  jmp     loc_140005575
0x140005410  mov     ecx, 0C000003Ah
0x140005415  jmp     loc_140005575
0x14000541a  mov     ecx, 0C0000034h
0x14000541f  jmp     loc_140005575
0x140005424  mov     ecx, 0C0000002h
0x140005429  jmp     loc_140005575
0x14000542e  mov     ecx, 0C0000001h
0x140005433  jmp     loc_140005575
0x140005438  mov     ecx, 0C000000Dh
0x14000543d  jmp     loc_140005575
0x140005442  cmp     ecx, 80070070h
0x140005448  jz      short loc_140005484
0x14000544a  cmp     ecx, 8007007Ah
0x140005450  jz      short loc_14000547A
0x140005452  cmp     ecx, 8007007Bh
0x140005458  jz      short loc_140005470
0x14000545a  cmp     ecx, 8007007Eh
0x140005460  jnz     loc_14000551D
0x140005466  mov     ecx, 0C0000135h
0x14000546b  jmp     loc_140005575
0x140005470  mov     ecx, 0C0000033h
0x140005475  jmp     loc_140005575
0x14000547a  mov     ecx, 0C0000023h
0x14000547f  jmp     loc_140005575
0x140005484  mov     ecx, 0C000007Fh
0x140005489  jmp     loc_140005575
0x14000548e  mov     ecx, 80000005h
0x140005493  jmp     loc_140005575
0x140005498  mov     eax, 8007047Eh
0x14000549d  cmp     ecx, eax
0x14000549f  jg      short loc_140005501
0x1400054a1  jz      short loc_1400054FA
0x1400054a3  cmp     ecx, 80070216h
0x1400054a9  jz      short loc_1400054F3
0x1400054ab  cmp     ecx, 8007023Eh
0x1400054b1  jz      short loc_1400054E9
0x1400054b3  cmp     ecx, 80070246h
0x1400054b9  jz      short loc_1400054DF
0x1400054bb  cmp     ecx, 80070247h
0x1400054c1  jz      short loc_1400054D5
0x1400054c3  cmp     ecx, 80070272h
0x1400054c9  jnz     short loc_14000551D
0x1400054cb  mov     ecx, 0C0000273h
0x1400054d0  jmp     loc_140005575
0x1400054d5  mov     ecx, 0C0000163h
0x1400054da  jmp     loc_140005575
0x1400054df  mov     ecx, 0C0000161h
0x1400054e4  jmp     loc_140005575
0x1400054e9  mov     ecx, 0C0000025h
0x1400054ee  jmp     loc_140005575
0x1400054f3  mov     ecx, 0C0000095h
0x1400054f8  jmp     short loc_140005575
0x1400054fa  mov     ecx, 0C0000059h
0x1400054ff  jmp     short loc_140005575
0x140005501  cmp     ecx, 8007050Ch
0x140005507  jz      short loc_140005570
0x140005509  cmp     ecx, 8007054Fh
0x14000550f  jz      short loc_140005569
0x140005511  cmp     ecx, 800705B9h
0x140005517  jz      short loc_140005562
0x140005519  test    ecx, ecx
0x14000551b  jz      short loc_14000555E
0x14000551d  bt      ecx, 1Ch
0x140005521  jnb     short loc_140005529
0x140005523  btr     ecx, 1Ch
0x140005527  jmp     short loc_140005575
0x140005529  mov     eax, ecx
0x14000552b  and     eax, 1FFF0000h
0x140005530  cmp     eax, 70000h
0x140005535  jnz     short loc_140005548
0x140005537  movzx   ecx, cx
0x14000553a  mov     eax, ecx
0x14000553c  or      eax, 0C0070000h
0x140005541  test    ecx, ecx
0x140005543  cmovnz  ecx, eax
0x140005546  jmp     short loc_140005575
0x140005548  cmp     eax, 90000h
0x14000554d  jnz     short loc_140005569
0x14000554f  test    ecx, ecx
0x140005551  jle     short loc_140005575
0x140005553  movzx   ecx, cx
0x140005556  or      ecx, 0C0090000h
0x14000555c  jmp     short loc_140005575
0x14000555e  xor     ecx, ecx
0x140005560  jmp     short loc_140005575
0x140005562  mov     ecx, 0C000A083h
0x140005567  jmp     short loc_140005575
0x140005569  mov     ecx, 0C00000E5h
0x14000556e  jmp     short loc_140005575
0x140005570  mov     ecx, 0C000042Bh
0x140005575  mov     eax, ecx
0x140005577  retn
```
