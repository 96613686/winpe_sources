# wil::details::HrToNtStatus(long)

- ea: `0x180005050`
- end: `0x18000520c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002560`
- `0x180002600`
- `0x180002650`
- `0x180002710`
- `0x1800046e8`
- `0x180005214`

## callees

- `0x180005050`

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
0x180005050  mov     eax, 800700EAh
0x180005055  cmp     ecx, eax
0x180005057  jg      loc_18000512C
0x18000505d  jz      loc_180005122
0x180005063  mov     eax, 80070057h
0x180005068  cmp     ecx, eax
0x18000506a  jg      short loc_1800050D6
0x18000506c  jz      short loc_1800050CC
0x18000506e  cmp     ecx, 80004005h
0x180005074  jz      short loc_1800050C2
0x180005076  cmp     ecx, 80070001h
0x18000507c  jz      short loc_1800050B8
0x18000507e  cmp     ecx, 80070002h
0x180005084  jz      short loc_1800050AE
0x180005086  cmp     ecx, 80070003h
0x18000508c  jz      short loc_1800050A4
0x18000508e  cmp     ecx, 8007000Eh
0x180005094  jnz     loc_1800051B1
0x18000509a  mov     ecx, 0C0000017h
0x18000509f  jmp     loc_180005209
0x1800050a4  mov     ecx, 0C000003Ah
0x1800050a9  jmp     loc_180005209
0x1800050ae  mov     ecx, 0C0000034h
0x1800050b3  jmp     loc_180005209
0x1800050b8  mov     ecx, 0C0000002h
0x1800050bd  jmp     loc_180005209
0x1800050c2  mov     ecx, 0C0000001h
0x1800050c7  jmp     loc_180005209
0x1800050cc  mov     ecx, 0C000000Dh
0x1800050d1  jmp     loc_180005209
0x1800050d6  cmp     ecx, 80070070h
0x1800050dc  jz      short loc_180005118
0x1800050de  cmp     ecx, 8007007Ah
0x1800050e4  jz      short loc_18000510E
0x1800050e6  cmp     ecx, 8007007Bh
0x1800050ec  jz      short loc_180005104
0x1800050ee  cmp     ecx, 8007007Eh
0x1800050f4  jnz     loc_1800051B1
0x1800050fa  mov     ecx, 0C0000135h
0x1800050ff  jmp     loc_180005209
0x180005104  mov     ecx, 0C0000033h
0x180005109  jmp     loc_180005209
0x18000510e  mov     ecx, 0C0000023h
0x180005113  jmp     loc_180005209
0x180005118  mov     ecx, 0C000007Fh
0x18000511d  jmp     loc_180005209
0x180005122  mov     ecx, 80000005h
0x180005127  jmp     loc_180005209
0x18000512c  mov     eax, 8007047Eh
0x180005131  cmp     ecx, eax
0x180005133  jg      short loc_180005195
0x180005135  jz      short loc_18000518E
0x180005137  cmp     ecx, 80070216h
0x18000513d  jz      short loc_180005187
0x18000513f  cmp     ecx, 8007023Eh
0x180005145  jz      short loc_18000517D
0x180005147  cmp     ecx, 80070246h
0x18000514d  jz      short loc_180005173
0x18000514f  cmp     ecx, 80070247h
0x180005155  jz      short loc_180005169
0x180005157  cmp     ecx, 80070272h
0x18000515d  jnz     short loc_1800051B1
0x18000515f  mov     ecx, 0C0000273h
0x180005164  jmp     loc_180005209
0x180005169  mov     ecx, 0C0000163h
0x18000516e  jmp     loc_180005209
0x180005173  mov     ecx, 0C0000161h
0x180005178  jmp     loc_180005209
0x18000517d  mov     ecx, 0C0000025h
0x180005182  jmp     loc_180005209
0x180005187  mov     ecx, 0C0000095h
0x18000518c  jmp     short loc_180005209
0x18000518e  mov     ecx, 0C0000059h
0x180005193  jmp     short loc_180005209
0x180005195  cmp     ecx, 8007050Ch
0x18000519b  jz      short loc_180005204
0x18000519d  cmp     ecx, 8007054Fh
0x1800051a3  jz      short loc_1800051FD
0x1800051a5  cmp     ecx, 800705B9h
0x1800051ab  jz      short loc_1800051F6
0x1800051ad  test    ecx, ecx
0x1800051af  jz      short loc_1800051F2
0x1800051b1  bt      ecx, 1Ch
0x1800051b5  jnb     short loc_1800051BD
0x1800051b7  btr     ecx, 1Ch
0x1800051bb  jmp     short loc_180005209
0x1800051bd  mov     eax, ecx
0x1800051bf  and     eax, 1FFF0000h
0x1800051c4  cmp     eax, 70000h
0x1800051c9  jnz     short loc_1800051DC
0x1800051cb  movzx   ecx, cx
0x1800051ce  mov     eax, ecx
0x1800051d0  or      eax, 0C0070000h
0x1800051d5  test    ecx, ecx
0x1800051d7  cmovnz  ecx, eax
0x1800051da  jmp     short loc_180005209
0x1800051dc  cmp     eax, 90000h
0x1800051e1  jnz     short loc_1800051FD
0x1800051e3  test    ecx, ecx
0x1800051e5  jle     short loc_180005209
0x1800051e7  movzx   ecx, cx
0x1800051ea  or      ecx, 0C0090000h
0x1800051f0  jmp     short loc_180005209
0x1800051f2  xor     ecx, ecx
0x1800051f4  jmp     short loc_180005209
0x1800051f6  mov     ecx, 0C000A083h
0x1800051fb  jmp     short loc_180005209
0x1800051fd  mov     ecx, 0C00000E5h
0x180005202  jmp     short loc_180005209
0x180005204  mov     ecx, 0C000042Bh
0x180005209  mov     eax, ecx
0x18000520b  retn
```
