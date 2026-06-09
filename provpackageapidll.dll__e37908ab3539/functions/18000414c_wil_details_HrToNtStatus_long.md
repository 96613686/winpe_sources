# wil::details::HrToNtStatus(long)

- ea: `0x18000414c`
- end: `0x180004308`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000241c`
- `0x1800024c4`
- `0x180002514`
- `0x1800025cc`
- `0x180003718`
- `0x180004310`

## callees

- `0x18000414c`

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
0x18000414c  mov     eax, 800700EAh
0x180004151  cmp     ecx, eax
0x180004153  jg      loc_180004228
0x180004159  jz      loc_18000421E
0x18000415f  mov     eax, 80070057h
0x180004164  cmp     ecx, eax
0x180004166  jg      short loc_1800041D2
0x180004168  jz      short loc_1800041C8
0x18000416a  cmp     ecx, 80004005h
0x180004170  jz      short loc_1800041BE
0x180004172  cmp     ecx, 80070001h
0x180004178  jz      short loc_1800041B4
0x18000417a  cmp     ecx, 80070002h
0x180004180  jz      short loc_1800041AA
0x180004182  cmp     ecx, 80070003h
0x180004188  jz      short loc_1800041A0
0x18000418a  cmp     ecx, 8007000Eh
0x180004190  jnz     loc_1800042AD
0x180004196  mov     ecx, 0C0000017h
0x18000419b  jmp     loc_180004305
0x1800041a0  mov     ecx, 0C000003Ah
0x1800041a5  jmp     loc_180004305
0x1800041aa  mov     ecx, 0C0000034h
0x1800041af  jmp     loc_180004305
0x1800041b4  mov     ecx, 0C0000002h
0x1800041b9  jmp     loc_180004305
0x1800041be  mov     ecx, 0C0000001h
0x1800041c3  jmp     loc_180004305
0x1800041c8  mov     ecx, 0C000000Dh
0x1800041cd  jmp     loc_180004305
0x1800041d2  cmp     ecx, 80070070h
0x1800041d8  jz      short loc_180004214
0x1800041da  cmp     ecx, 8007007Ah
0x1800041e0  jz      short loc_18000420A
0x1800041e2  cmp     ecx, 8007007Bh
0x1800041e8  jz      short loc_180004200
0x1800041ea  cmp     ecx, 8007007Eh
0x1800041f0  jnz     loc_1800042AD
0x1800041f6  mov     ecx, 0C0000135h
0x1800041fb  jmp     loc_180004305
0x180004200  mov     ecx, 0C0000033h
0x180004205  jmp     loc_180004305
0x18000420a  mov     ecx, 0C0000023h
0x18000420f  jmp     loc_180004305
0x180004214  mov     ecx, 0C000007Fh
0x180004219  jmp     loc_180004305
0x18000421e  mov     ecx, 80000005h
0x180004223  jmp     loc_180004305
0x180004228  mov     eax, 8007047Eh
0x18000422d  cmp     ecx, eax
0x18000422f  jg      short loc_180004291
0x180004231  jz      short loc_18000428A
0x180004233  cmp     ecx, 80070216h
0x180004239  jz      short loc_180004283
0x18000423b  cmp     ecx, 8007023Eh
0x180004241  jz      short loc_180004279
0x180004243  cmp     ecx, 80070246h
0x180004249  jz      short loc_18000426F
0x18000424b  cmp     ecx, 80070247h
0x180004251  jz      short loc_180004265
0x180004253  cmp     ecx, 80070272h
0x180004259  jnz     short loc_1800042AD
0x18000425b  mov     ecx, 0C0000273h
0x180004260  jmp     loc_180004305
0x180004265  mov     ecx, 0C0000163h
0x18000426a  jmp     loc_180004305
0x18000426f  mov     ecx, 0C0000161h
0x180004274  jmp     loc_180004305
0x180004279  mov     ecx, 0C0000025h
0x18000427e  jmp     loc_180004305
0x180004283  mov     ecx, 0C0000095h
0x180004288  jmp     short loc_180004305
0x18000428a  mov     ecx, 0C0000059h
0x18000428f  jmp     short loc_180004305
0x180004291  cmp     ecx, 8007050Ch
0x180004297  jz      short loc_180004300
0x180004299  cmp     ecx, 8007054Fh
0x18000429f  jz      short loc_1800042F9
0x1800042a1  cmp     ecx, 800705B9h
0x1800042a7  jz      short loc_1800042F2
0x1800042a9  test    ecx, ecx
0x1800042ab  jz      short loc_1800042EE
0x1800042ad  bt      ecx, 1Ch
0x1800042b1  jnb     short loc_1800042B9
0x1800042b3  btr     ecx, 1Ch
0x1800042b7  jmp     short loc_180004305
0x1800042b9  mov     eax, ecx
0x1800042bb  and     eax, 1FFF0000h
0x1800042c0  cmp     eax, 70000h
0x1800042c5  jnz     short loc_1800042D8
0x1800042c7  movzx   ecx, cx
0x1800042ca  mov     eax, ecx
0x1800042cc  or      eax, 0C0070000h
0x1800042d1  test    ecx, ecx
0x1800042d3  cmovnz  ecx, eax
0x1800042d6  jmp     short loc_180004305
0x1800042d8  cmp     eax, 90000h
0x1800042dd  jnz     short loc_1800042F9
0x1800042df  test    ecx, ecx
0x1800042e1  jle     short loc_180004305
0x1800042e3  movzx   ecx, cx
0x1800042e6  or      ecx, 0C0090000h
0x1800042ec  jmp     short loc_180004305
0x1800042ee  xor     ecx, ecx
0x1800042f0  jmp     short loc_180004305
0x1800042f2  mov     ecx, 0C000A083h
0x1800042f7  jmp     short loc_180004305
0x1800042f9  mov     ecx, 0C00000E5h
0x1800042fe  jmp     short loc_180004305
0x180004300  mov     ecx, 0C000042Bh
0x180004305  mov     eax, ecx
0x180004307  retn
```
