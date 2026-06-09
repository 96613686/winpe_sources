# wil::details::HrToNtStatus(long)

- ea: `0x180004734`
- end: `0x1800048f0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000258c`
- `0x180002768`
- `0x180002818`
- `0x180002870`
- `0x180002938`
- `0x180003d08`
- `0x1800048f8`
- `0x180005080`
- `0x180006e12`
- `0x180006e7d`
- `0x180006f46`
- `0x180006fb1`

## callees

- `0x180004734`

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
0x180004734  mov     eax, 800700EAh
0x180004739  cmp     ecx, eax
0x18000473b  jg      loc_180004810
0x180004741  jz      loc_180004806
0x180004747  mov     eax, 80070057h
0x18000474c  cmp     ecx, eax
0x18000474e  jg      short loc_1800047BA
0x180004750  jz      short loc_1800047B0
0x180004752  cmp     ecx, 80004005h
0x180004758  jz      short loc_1800047A6
0x18000475a  cmp     ecx, 80070001h
0x180004760  jz      short loc_18000479C
0x180004762  cmp     ecx, 80070002h
0x180004768  jz      short loc_180004792
0x18000476a  cmp     ecx, 80070003h
0x180004770  jz      short loc_180004788
0x180004772  cmp     ecx, 8007000Eh
0x180004778  jnz     loc_180004895
0x18000477e  mov     ecx, 0C0000017h
0x180004783  jmp     loc_1800048ED
0x180004788  mov     ecx, 0C000003Ah
0x18000478d  jmp     loc_1800048ED
0x180004792  mov     ecx, 0C0000034h
0x180004797  jmp     loc_1800048ED
0x18000479c  mov     ecx, 0C0000002h
0x1800047a1  jmp     loc_1800048ED
0x1800047a6  mov     ecx, 0C0000001h
0x1800047ab  jmp     loc_1800048ED
0x1800047b0  mov     ecx, 0C000000Dh
0x1800047b5  jmp     loc_1800048ED
0x1800047ba  cmp     ecx, 80070070h
0x1800047c0  jz      short loc_1800047FC
0x1800047c2  cmp     ecx, 8007007Ah
0x1800047c8  jz      short loc_1800047F2
0x1800047ca  cmp     ecx, 8007007Bh
0x1800047d0  jz      short loc_1800047E8
0x1800047d2  cmp     ecx, 8007007Eh
0x1800047d8  jnz     loc_180004895
0x1800047de  mov     ecx, 0C0000135h
0x1800047e3  jmp     loc_1800048ED
0x1800047e8  mov     ecx, 0C0000033h
0x1800047ed  jmp     loc_1800048ED
0x1800047f2  mov     ecx, 0C0000023h
0x1800047f7  jmp     loc_1800048ED
0x1800047fc  mov     ecx, 0C000007Fh
0x180004801  jmp     loc_1800048ED
0x180004806  mov     ecx, 80000005h
0x18000480b  jmp     loc_1800048ED
0x180004810  mov     eax, 8007047Eh
0x180004815  cmp     ecx, eax
0x180004817  jg      short loc_180004879
0x180004819  jz      short loc_180004872
0x18000481b  cmp     ecx, 80070216h
0x180004821  jz      short loc_18000486B
0x180004823  cmp     ecx, 8007023Eh
0x180004829  jz      short loc_180004861
0x18000482b  cmp     ecx, 80070246h
0x180004831  jz      short loc_180004857
0x180004833  cmp     ecx, 80070247h
0x180004839  jz      short loc_18000484D
0x18000483b  cmp     ecx, 80070272h
0x180004841  jnz     short loc_180004895
0x180004843  mov     ecx, 0C0000273h
0x180004848  jmp     loc_1800048ED
0x18000484d  mov     ecx, 0C0000163h
0x180004852  jmp     loc_1800048ED
0x180004857  mov     ecx, 0C0000161h
0x18000485c  jmp     loc_1800048ED
0x180004861  mov     ecx, 0C0000025h
0x180004866  jmp     loc_1800048ED
0x18000486b  mov     ecx, 0C0000095h
0x180004870  jmp     short loc_1800048ED
0x180004872  mov     ecx, 0C0000059h
0x180004877  jmp     short loc_1800048ED
0x180004879  cmp     ecx, 8007050Ch
0x18000487f  jz      short loc_1800048E8
0x180004881  cmp     ecx, 8007054Fh
0x180004887  jz      short loc_1800048E1
0x180004889  cmp     ecx, 800705B9h
0x18000488f  jz      short loc_1800048DA
0x180004891  test    ecx, ecx
0x180004893  jz      short loc_1800048D6
0x180004895  bt      ecx, 1Ch
0x180004899  jnb     short loc_1800048A1
0x18000489b  btr     ecx, 1Ch
0x18000489f  jmp     short loc_1800048ED
0x1800048a1  mov     eax, ecx
0x1800048a3  and     eax, 1FFF0000h
0x1800048a8  cmp     eax, 70000h
0x1800048ad  jnz     short loc_1800048C0
0x1800048af  movzx   ecx, cx
0x1800048b2  mov     eax, ecx
0x1800048b4  or      eax, 0C0070000h
0x1800048b9  test    ecx, ecx
0x1800048bb  cmovnz  ecx, eax
0x1800048be  jmp     short loc_1800048ED
0x1800048c0  cmp     eax, 90000h
0x1800048c5  jnz     short loc_1800048E1
0x1800048c7  test    ecx, ecx
0x1800048c9  jle     short loc_1800048ED
0x1800048cb  movzx   ecx, cx
0x1800048ce  or      ecx, 0C0090000h
0x1800048d4  jmp     short loc_1800048ED
0x1800048d6  xor     ecx, ecx
0x1800048d8  jmp     short loc_1800048ED
0x1800048da  mov     ecx, 0C000A083h
0x1800048df  jmp     short loc_1800048ED
0x1800048e1  mov     ecx, 0C00000E5h
0x1800048e6  jmp     short loc_1800048ED
0x1800048e8  mov     ecx, 0C000042Bh
0x1800048ed  mov     eax, ecx
0x1800048ef  retn
```
