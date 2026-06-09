# wil::details::HrToNtStatus(long)

- ea: `0x180003fd8`
- end: `0x180004194`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023ec`
- `0x180002494`
- `0x1800024e4`
- `0x18000259c`
- `0x180003604`
- `0x18000420c`

## callees

- `0x180003fd8`

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
0x180003fd8  mov     eax, 800700EAh
0x180003fdd  cmp     ecx, eax
0x180003fdf  jg      loc_1800040B4
0x180003fe5  jz      loc_1800040AA
0x180003feb  mov     eax, 80070057h
0x180003ff0  cmp     ecx, eax
0x180003ff2  jg      short loc_18000405E
0x180003ff4  jz      short loc_180004054
0x180003ff6  cmp     ecx, 80004005h
0x180003ffc  jz      short loc_18000404A
0x180003ffe  cmp     ecx, 80070001h
0x180004004  jz      short loc_180004040
0x180004006  cmp     ecx, 80070002h
0x18000400c  jz      short loc_180004036
0x18000400e  cmp     ecx, 80070003h
0x180004014  jz      short loc_18000402C
0x180004016  cmp     ecx, 8007000Eh
0x18000401c  jnz     loc_180004139
0x180004022  mov     ecx, 0C0000017h
0x180004027  jmp     loc_180004191
0x18000402c  mov     ecx, 0C000003Ah
0x180004031  jmp     loc_180004191
0x180004036  mov     ecx, 0C0000034h
0x18000403b  jmp     loc_180004191
0x180004040  mov     ecx, 0C0000002h
0x180004045  jmp     loc_180004191
0x18000404a  mov     ecx, 0C0000001h
0x18000404f  jmp     loc_180004191
0x180004054  mov     ecx, 0C000000Dh
0x180004059  jmp     loc_180004191
0x18000405e  cmp     ecx, 80070070h
0x180004064  jz      short loc_1800040A0
0x180004066  cmp     ecx, 8007007Ah
0x18000406c  jz      short loc_180004096
0x18000406e  cmp     ecx, 8007007Bh
0x180004074  jz      short loc_18000408C
0x180004076  cmp     ecx, 8007007Eh
0x18000407c  jnz     loc_180004139
0x180004082  mov     ecx, 0C0000135h
0x180004087  jmp     loc_180004191
0x18000408c  mov     ecx, 0C0000033h
0x180004091  jmp     loc_180004191
0x180004096  mov     ecx, 0C0000023h
0x18000409b  jmp     loc_180004191
0x1800040a0  mov     ecx, 0C000007Fh
0x1800040a5  jmp     loc_180004191
0x1800040aa  mov     ecx, 80000005h
0x1800040af  jmp     loc_180004191
0x1800040b4  mov     eax, 8007047Eh
0x1800040b9  cmp     ecx, eax
0x1800040bb  jg      short loc_18000411D
0x1800040bd  jz      short loc_180004116
0x1800040bf  cmp     ecx, 80070216h
0x1800040c5  jz      short loc_18000410F
0x1800040c7  cmp     ecx, 8007023Eh
0x1800040cd  jz      short loc_180004105
0x1800040cf  cmp     ecx, 80070246h
0x1800040d5  jz      short loc_1800040FB
0x1800040d7  cmp     ecx, 80070247h
0x1800040dd  jz      short loc_1800040F1
0x1800040df  cmp     ecx, 80070272h
0x1800040e5  jnz     short loc_180004139
0x1800040e7  mov     ecx, 0C0000273h
0x1800040ec  jmp     loc_180004191
0x1800040f1  mov     ecx, 0C0000163h
0x1800040f6  jmp     loc_180004191
0x1800040fb  mov     ecx, 0C0000161h
0x180004100  jmp     loc_180004191
0x180004105  mov     ecx, 0C0000025h
0x18000410a  jmp     loc_180004191
0x18000410f  mov     ecx, 0C0000095h
0x180004114  jmp     short loc_180004191
0x180004116  mov     ecx, 0C0000059h
0x18000411b  jmp     short loc_180004191
0x18000411d  cmp     ecx, 8007050Ch
0x180004123  jz      short loc_18000418C
0x180004125  cmp     ecx, 8007054Fh
0x18000412b  jz      short loc_180004185
0x18000412d  cmp     ecx, 800705B9h
0x180004133  jz      short loc_18000417E
0x180004135  test    ecx, ecx
0x180004137  jz      short loc_18000417A
0x180004139  bt      ecx, 1Ch
0x18000413d  jnb     short loc_180004145
0x18000413f  btr     ecx, 1Ch
0x180004143  jmp     short loc_180004191
0x180004145  mov     eax, ecx
0x180004147  and     eax, 1FFF0000h
0x18000414c  cmp     eax, 70000h
0x180004151  jnz     short loc_180004164
0x180004153  movzx   ecx, cx
0x180004156  mov     eax, ecx
0x180004158  or      eax, 0C0070000h
0x18000415d  test    ecx, ecx
0x18000415f  cmovnz  ecx, eax
0x180004162  jmp     short loc_180004191
0x180004164  cmp     eax, 90000h
0x180004169  jnz     short loc_180004185
0x18000416b  test    ecx, ecx
0x18000416d  jle     short loc_180004191
0x18000416f  movzx   ecx, cx
0x180004172  or      ecx, 0C0090000h
0x180004178  jmp     short loc_180004191
0x18000417a  xor     ecx, ecx
0x18000417c  jmp     short loc_180004191
0x18000417e  mov     ecx, 0C000A083h
0x180004183  jmp     short loc_180004191
0x180004185  mov     ecx, 0C00000E5h
0x18000418a  jmp     short loc_180004191
0x18000418c  mov     ecx, 0C000042Bh
0x180004191  mov     eax, ecx
0x180004193  retn
```
