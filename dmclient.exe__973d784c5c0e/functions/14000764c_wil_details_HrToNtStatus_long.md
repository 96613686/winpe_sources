# wil::details::HrToNtStatus(long)

- ea: `0x14000764c`
- end: `0x140007808`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400033f8`
- `0x1400034a8`
- `0x1400034f8`
- `0x140003608`
- `0x140006bb4`
- `0x140007c9c`

## callees

- `0x14000764c`

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
0x14000764c  mov     eax, 800700EAh
0x140007651  cmp     ecx, eax
0x140007653  jg      loc_140007728
0x140007659  jz      loc_14000771E
0x14000765f  mov     eax, 80070057h
0x140007664  cmp     ecx, eax
0x140007666  jg      short loc_1400076D2
0x140007668  jz      short loc_1400076C8
0x14000766a  cmp     ecx, 80004005h
0x140007670  jz      short loc_1400076BE
0x140007672  cmp     ecx, 80070001h
0x140007678  jz      short loc_1400076B4
0x14000767a  cmp     ecx, 80070002h
0x140007680  jz      short loc_1400076AA
0x140007682  cmp     ecx, 80070003h
0x140007688  jz      short loc_1400076A0
0x14000768a  cmp     ecx, 8007000Eh
0x140007690  jnz     loc_1400077AD
0x140007696  mov     ecx, 0C0000017h
0x14000769b  jmp     loc_140007805
0x1400076a0  mov     ecx, 0C000003Ah
0x1400076a5  jmp     loc_140007805
0x1400076aa  mov     ecx, 0C0000034h
0x1400076af  jmp     loc_140007805
0x1400076b4  mov     ecx, 0C0000002h
0x1400076b9  jmp     loc_140007805
0x1400076be  mov     ecx, 0C0000001h
0x1400076c3  jmp     loc_140007805
0x1400076c8  mov     ecx, 0C000000Dh
0x1400076cd  jmp     loc_140007805
0x1400076d2  cmp     ecx, 80070070h
0x1400076d8  jz      short loc_140007714
0x1400076da  cmp     ecx, 8007007Ah
0x1400076e0  jz      short loc_14000770A
0x1400076e2  cmp     ecx, 8007007Bh
0x1400076e8  jz      short loc_140007700
0x1400076ea  cmp     ecx, 8007007Eh
0x1400076f0  jnz     loc_1400077AD
0x1400076f6  mov     ecx, 0C0000135h
0x1400076fb  jmp     loc_140007805
0x140007700  mov     ecx, 0C0000033h
0x140007705  jmp     loc_140007805
0x14000770a  mov     ecx, 0C0000023h
0x14000770f  jmp     loc_140007805
0x140007714  mov     ecx, 0C000007Fh
0x140007719  jmp     loc_140007805
0x14000771e  mov     ecx, 80000005h
0x140007723  jmp     loc_140007805
0x140007728  mov     eax, 8007047Eh
0x14000772d  cmp     ecx, eax
0x14000772f  jg      short loc_140007791
0x140007731  jz      short loc_14000778A
0x140007733  cmp     ecx, 80070216h
0x140007739  jz      short loc_140007783
0x14000773b  cmp     ecx, 8007023Eh
0x140007741  jz      short loc_140007779
0x140007743  cmp     ecx, 80070246h
0x140007749  jz      short loc_14000776F
0x14000774b  cmp     ecx, 80070247h
0x140007751  jz      short loc_140007765
0x140007753  cmp     ecx, 80070272h
0x140007759  jnz     short loc_1400077AD
0x14000775b  mov     ecx, 0C0000273h
0x140007760  jmp     loc_140007805
0x140007765  mov     ecx, 0C0000163h
0x14000776a  jmp     loc_140007805
0x14000776f  mov     ecx, 0C0000161h
0x140007774  jmp     loc_140007805
0x140007779  mov     ecx, 0C0000025h
0x14000777e  jmp     loc_140007805
0x140007783  mov     ecx, 0C0000095h
0x140007788  jmp     short loc_140007805
0x14000778a  mov     ecx, 0C0000059h
0x14000778f  jmp     short loc_140007805
0x140007791  cmp     ecx, 8007050Ch
0x140007797  jz      short loc_140007800
0x140007799  cmp     ecx, 8007054Fh
0x14000779f  jz      short loc_1400077F9
0x1400077a1  cmp     ecx, 800705B9h
0x1400077a7  jz      short loc_1400077F2
0x1400077a9  test    ecx, ecx
0x1400077ab  jz      short loc_1400077EE
0x1400077ad  bt      ecx, 1Ch
0x1400077b1  jnb     short loc_1400077B9
0x1400077b3  btr     ecx, 1Ch
0x1400077b7  jmp     short loc_140007805
0x1400077b9  mov     eax, ecx
0x1400077bb  and     eax, 1FFF0000h
0x1400077c0  cmp     eax, 70000h
0x1400077c5  jnz     short loc_1400077D8
0x1400077c7  movzx   ecx, cx
0x1400077ca  mov     eax, ecx
0x1400077cc  or      eax, 0C0070000h
0x1400077d1  test    ecx, ecx
0x1400077d3  cmovnz  ecx, eax
0x1400077d6  jmp     short loc_140007805
0x1400077d8  cmp     eax, 90000h
0x1400077dd  jnz     short loc_1400077F9
0x1400077df  test    ecx, ecx
0x1400077e1  jle     short loc_140007805
0x1400077e3  movzx   ecx, cx
0x1400077e6  or      ecx, 0C0090000h
0x1400077ec  jmp     short loc_140007805
0x1400077ee  xor     ecx, ecx
0x1400077f0  jmp     short loc_140007805
0x1400077f2  mov     ecx, 0C000A083h
0x1400077f7  jmp     short loc_140007805
0x1400077f9  mov     ecx, 0C00000E5h
0x1400077fe  jmp     short loc_140007805
0x140007800  mov     ecx, 0C000042Bh
0x140007805  mov     eax, ecx
0x140007807  retn
```
