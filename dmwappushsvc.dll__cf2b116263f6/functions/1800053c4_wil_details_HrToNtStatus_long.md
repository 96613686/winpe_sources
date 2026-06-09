# wil::details::HrToNtStatus(long)

- ea: `0x1800053c4`
- end: `0x180005580`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a04`
- `0x180006a7c`
- `0x180006af8`
- `0x180006b48`
- `0x180006bac`
- `0x180006ebc`
- `0x18000941c`

## callees

- `0x1800053c4`

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
0x1800053c4  mov     eax, 800700EAh
0x1800053c9  cmp     ecx, eax
0x1800053cb  jg      loc_1800054A0
0x1800053d1  jz      loc_180005496
0x1800053d7  mov     eax, 80070057h
0x1800053dc  cmp     ecx, eax
0x1800053de  jg      short loc_18000544A
0x1800053e0  jz      short loc_180005440
0x1800053e2  cmp     ecx, 80004005h
0x1800053e8  jz      short loc_180005436
0x1800053ea  cmp     ecx, 80070001h
0x1800053f0  jz      short loc_18000542C
0x1800053f2  cmp     ecx, 80070002h
0x1800053f8  jz      short loc_180005422
0x1800053fa  cmp     ecx, 80070003h
0x180005400  jz      short loc_180005418
0x180005402  cmp     ecx, 8007000Eh
0x180005408  jnz     loc_180005525
0x18000540e  mov     ecx, 0C0000017h
0x180005413  jmp     loc_18000557D
0x180005418  mov     ecx, 0C000003Ah
0x18000541d  jmp     loc_18000557D
0x180005422  mov     ecx, 0C0000034h
0x180005427  jmp     loc_18000557D
0x18000542c  mov     ecx, 0C0000002h
0x180005431  jmp     loc_18000557D
0x180005436  mov     ecx, 0C0000001h
0x18000543b  jmp     loc_18000557D
0x180005440  mov     ecx, 0C000000Dh
0x180005445  jmp     loc_18000557D
0x18000544a  cmp     ecx, 80070070h
0x180005450  jz      short loc_18000548C
0x180005452  cmp     ecx, 8007007Ah
0x180005458  jz      short loc_180005482
0x18000545a  cmp     ecx, 8007007Bh
0x180005460  jz      short loc_180005478
0x180005462  cmp     ecx, 8007007Eh
0x180005468  jnz     loc_180005525
0x18000546e  mov     ecx, 0C0000135h
0x180005473  jmp     loc_18000557D
0x180005478  mov     ecx, 0C0000033h
0x18000547d  jmp     loc_18000557D
0x180005482  mov     ecx, 0C0000023h
0x180005487  jmp     loc_18000557D
0x18000548c  mov     ecx, 0C000007Fh
0x180005491  jmp     loc_18000557D
0x180005496  mov     ecx, 80000005h
0x18000549b  jmp     loc_18000557D
0x1800054a0  mov     eax, 8007047Eh
0x1800054a5  cmp     ecx, eax
0x1800054a7  jg      short loc_180005509
0x1800054a9  jz      short loc_180005502
0x1800054ab  cmp     ecx, 80070216h
0x1800054b1  jz      short loc_1800054FB
0x1800054b3  cmp     ecx, 8007023Eh
0x1800054b9  jz      short loc_1800054F1
0x1800054bb  cmp     ecx, 80070246h
0x1800054c1  jz      short loc_1800054E7
0x1800054c3  cmp     ecx, 80070247h
0x1800054c9  jz      short loc_1800054DD
0x1800054cb  cmp     ecx, 80070272h
0x1800054d1  jnz     short loc_180005525
0x1800054d3  mov     ecx, 0C0000273h
0x1800054d8  jmp     loc_18000557D
0x1800054dd  mov     ecx, 0C0000163h
0x1800054e2  jmp     loc_18000557D
0x1800054e7  mov     ecx, 0C0000161h
0x1800054ec  jmp     loc_18000557D
0x1800054f1  mov     ecx, 0C0000025h
0x1800054f6  jmp     loc_18000557D
0x1800054fb  mov     ecx, 0C0000095h
0x180005500  jmp     short loc_18000557D
0x180005502  mov     ecx, 0C0000059h
0x180005507  jmp     short loc_18000557D
0x180005509  cmp     ecx, 8007050Ch
0x18000550f  jz      short loc_180005578
0x180005511  cmp     ecx, 8007054Fh
0x180005517  jz      short loc_180005571
0x180005519  cmp     ecx, 800705B9h
0x18000551f  jz      short loc_18000556A
0x180005521  test    ecx, ecx
0x180005523  jz      short loc_180005566
0x180005525  bt      ecx, 1Ch
0x180005529  jnb     short loc_180005531
0x18000552b  btr     ecx, 1Ch
0x18000552f  jmp     short loc_18000557D
0x180005531  mov     eax, ecx
0x180005533  and     eax, 1FFF0000h
0x180005538  cmp     eax, 70000h
0x18000553d  jnz     short loc_180005550
0x18000553f  movzx   ecx, cx
0x180005542  mov     eax, ecx
0x180005544  or      eax, 0C0070000h
0x180005549  test    ecx, ecx
0x18000554b  cmovnz  ecx, eax
0x18000554e  jmp     short loc_18000557D
0x180005550  cmp     eax, 90000h
0x180005555  jnz     short loc_180005571
0x180005557  test    ecx, ecx
0x180005559  jle     short loc_18000557D
0x18000555b  movzx   ecx, cx
0x18000555e  or      ecx, 0C0090000h
0x180005564  jmp     short loc_18000557D
0x180005566  xor     ecx, ecx
0x180005568  jmp     short loc_18000557D
0x18000556a  mov     ecx, 0C000A083h
0x18000556f  jmp     short loc_18000557D
0x180005571  mov     ecx, 0C00000E5h
0x180005576  jmp     short loc_18000557D
0x180005578  mov     ecx, 0C000042Bh
0x18000557d  mov     eax, ecx
0x18000557f  retn
```
