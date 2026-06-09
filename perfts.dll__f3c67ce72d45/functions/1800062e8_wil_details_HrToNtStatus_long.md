# wil::details::HrToNtStatus(long)

- ea: `0x1800062e8`
- end: `0x1800064a4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c74`
- `0x180003dd8`
- `0x180003e3c`
- `0x1800068b0`
- `0x180008350`
- `0x180009fac`
- `0x18000a017`
- `0x18000a0e0`
- `0x18000a14b`

## callees

- `0x1800062e8`

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
0x1800062e8  mov     eax, 800700EAh
0x1800062ed  cmp     ecx, eax
0x1800062ef  jg      loc_1800063C4
0x1800062f5  jz      loc_1800063BA
0x1800062fb  mov     eax, 80070057h
0x180006300  cmp     ecx, eax
0x180006302  jg      short loc_18000636E
0x180006304  jz      short loc_180006364
0x180006306  cmp     ecx, 80004005h
0x18000630c  jz      short loc_18000635A
0x18000630e  cmp     ecx, 80070001h
0x180006314  jz      short loc_180006350
0x180006316  cmp     ecx, 80070002h
0x18000631c  jz      short loc_180006346
0x18000631e  cmp     ecx, 80070003h
0x180006324  jz      short loc_18000633C
0x180006326  cmp     ecx, 8007000Eh
0x18000632c  jnz     loc_180006449
0x180006332  mov     ecx, 0C0000017h
0x180006337  jmp     loc_1800064A1
0x18000633c  mov     ecx, 0C000003Ah
0x180006341  jmp     loc_1800064A1
0x180006346  mov     ecx, 0C0000034h
0x18000634b  jmp     loc_1800064A1
0x180006350  mov     ecx, 0C0000002h
0x180006355  jmp     loc_1800064A1
0x18000635a  mov     ecx, 0C0000001h
0x18000635f  jmp     loc_1800064A1
0x180006364  mov     ecx, 0C000000Dh
0x180006369  jmp     loc_1800064A1
0x18000636e  cmp     ecx, 80070070h
0x180006374  jz      short loc_1800063B0
0x180006376  cmp     ecx, 8007007Ah
0x18000637c  jz      short loc_1800063A6
0x18000637e  cmp     ecx, 8007007Bh
0x180006384  jz      short loc_18000639C
0x180006386  cmp     ecx, 8007007Eh
0x18000638c  jnz     loc_180006449
0x180006392  mov     ecx, 0C0000135h
0x180006397  jmp     loc_1800064A1
0x18000639c  mov     ecx, 0C0000033h
0x1800063a1  jmp     loc_1800064A1
0x1800063a6  mov     ecx, 0C0000023h
0x1800063ab  jmp     loc_1800064A1
0x1800063b0  mov     ecx, 0C000007Fh
0x1800063b5  jmp     loc_1800064A1
0x1800063ba  mov     ecx, 80000005h
0x1800063bf  jmp     loc_1800064A1
0x1800063c4  mov     eax, 8007047Eh
0x1800063c9  cmp     ecx, eax
0x1800063cb  jg      short loc_18000642D
0x1800063cd  jz      short loc_180006426
0x1800063cf  cmp     ecx, 80070216h
0x1800063d5  jz      short loc_18000641F
0x1800063d7  cmp     ecx, 8007023Eh
0x1800063dd  jz      short loc_180006415
0x1800063df  cmp     ecx, 80070246h
0x1800063e5  jz      short loc_18000640B
0x1800063e7  cmp     ecx, 80070247h
0x1800063ed  jz      short loc_180006401
0x1800063ef  cmp     ecx, 80070272h
0x1800063f5  jnz     short loc_180006449
0x1800063f7  mov     ecx, 0C0000273h
0x1800063fc  jmp     loc_1800064A1
0x180006401  mov     ecx, 0C0000163h
0x180006406  jmp     loc_1800064A1
0x18000640b  mov     ecx, 0C0000161h
0x180006410  jmp     loc_1800064A1
0x180006415  mov     ecx, 0C0000025h
0x18000641a  jmp     loc_1800064A1
0x18000641f  mov     ecx, 0C0000095h
0x180006424  jmp     short loc_1800064A1
0x180006426  mov     ecx, 0C0000059h
0x18000642b  jmp     short loc_1800064A1
0x18000642d  cmp     ecx, 8007050Ch
0x180006433  jz      short loc_18000649C
0x180006435  cmp     ecx, 8007054Fh
0x18000643b  jz      short loc_180006495
0x18000643d  cmp     ecx, 800705B9h
0x180006443  jz      short loc_18000648E
0x180006445  test    ecx, ecx
0x180006447  jz      short loc_18000648A
0x180006449  bt      ecx, 1Ch
0x18000644d  jnb     short loc_180006455
0x18000644f  btr     ecx, 1Ch
0x180006453  jmp     short loc_1800064A1
0x180006455  mov     eax, ecx
0x180006457  and     eax, 1FFF0000h
0x18000645c  cmp     eax, 70000h
0x180006461  jnz     short loc_180006474
0x180006463  movzx   ecx, cx
0x180006466  mov     eax, ecx
0x180006468  or      eax, 0C0070000h
0x18000646d  test    ecx, ecx
0x18000646f  cmovnz  ecx, eax
0x180006472  jmp     short loc_1800064A1
0x180006474  cmp     eax, 90000h
0x180006479  jnz     short loc_180006495
0x18000647b  test    ecx, ecx
0x18000647d  jle     short loc_1800064A1
0x18000647f  movzx   ecx, cx
0x180006482  or      ecx, 0C0090000h
0x180006488  jmp     short loc_1800064A1
0x18000648a  xor     ecx, ecx
0x18000648c  jmp     short loc_1800064A1
0x18000648e  mov     ecx, 0C000A083h
0x180006493  jmp     short loc_1800064A1
0x180006495  mov     ecx, 0C00000E5h
0x18000649a  jmp     short loc_1800064A1
0x18000649c  mov     ecx, 0C000042Bh
0x1800064a1  mov     eax, ecx
0x1800064a3  retn
```
