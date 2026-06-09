# wil::details::HrToNtStatus(long)

- ea: `0x14000abcc`
- end: `0x14000ad88`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x14000df74`
- `0x14000fa04`
- `0x14000fb6c`
- `0x140011070`
- `0x1400110e8`
- `0x140012400`
- `0x140012e40`
- `0x14001e5e8`
- `0x14001e633`
- `0x14001e6f6`
- `0x14001e741`

## callees

- `0x14000abcc`

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
        case 0x8007054F:
          goto LABEL_53;
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
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
0x14000abcc  mov     eax, 800700EAh
0x14000abd1  cmp     ecx, eax
0x14000abd3  jg      loc_14000ACA8
0x14000abd9  jz      loc_14000AC9E
0x14000abdf  mov     eax, 80070057h
0x14000abe4  cmp     ecx, eax
0x14000abe6  jg      short loc_14000AC52
0x14000abe8  jz      short loc_14000AC48
0x14000abea  cmp     ecx, 80004005h
0x14000abf0  jz      short loc_14000AC3E
0x14000abf2  cmp     ecx, 80070001h
0x14000abf8  jz      short loc_14000AC34
0x14000abfa  cmp     ecx, 80070002h
0x14000ac00  jz      short loc_14000AC2A
0x14000ac02  cmp     ecx, 80070003h
0x14000ac08  jz      short loc_14000AC20
0x14000ac0a  cmp     ecx, 8007000Eh
0x14000ac10  jnz     loc_14000AD2D
0x14000ac16  mov     ecx, 0C0000017h
0x14000ac1b  jmp     loc_14000AD85
0x14000ac20  mov     ecx, 0C000003Ah
0x14000ac25  jmp     loc_14000AD85
0x14000ac2a  mov     ecx, 0C0000034h
0x14000ac2f  jmp     loc_14000AD85
0x14000ac34  mov     ecx, 0C0000002h
0x14000ac39  jmp     loc_14000AD85
0x14000ac3e  mov     ecx, 0C0000001h
0x14000ac43  jmp     loc_14000AD85
0x14000ac48  mov     ecx, 0C000000Dh
0x14000ac4d  jmp     loc_14000AD85
0x14000ac52  cmp     ecx, 80070070h
0x14000ac58  jz      short loc_14000AC94
0x14000ac5a  cmp     ecx, 8007007Ah
0x14000ac60  jz      short loc_14000AC8A
0x14000ac62  cmp     ecx, 8007007Bh
0x14000ac68  jz      short loc_14000AC80
0x14000ac6a  cmp     ecx, 8007007Eh
0x14000ac70  jnz     loc_14000AD2D
0x14000ac76  mov     ecx, 0C0000135h
0x14000ac7b  jmp     loc_14000AD85
0x14000ac80  mov     ecx, 0C0000033h
0x14000ac85  jmp     loc_14000AD85
0x14000ac8a  mov     ecx, 0C0000023h
0x14000ac8f  jmp     loc_14000AD85
0x14000ac94  mov     ecx, 0C000007Fh
0x14000ac99  jmp     loc_14000AD85
0x14000ac9e  mov     ecx, 80000005h
0x14000aca3  jmp     loc_14000AD85
0x14000aca8  mov     eax, 8007047Eh
0x14000acad  cmp     ecx, eax
0x14000acaf  jg      short loc_14000AD11
0x14000acb1  jz      short loc_14000AD0A
0x14000acb3  cmp     ecx, 80070216h
0x14000acb9  jz      short loc_14000AD03
0x14000acbb  cmp     ecx, 8007023Eh
0x14000acc1  jz      short loc_14000ACF9
0x14000acc3  cmp     ecx, 80070246h
0x14000acc9  jz      short loc_14000ACEF
0x14000accb  cmp     ecx, 80070247h
0x14000acd1  jz      short loc_14000ACE5
0x14000acd3  cmp     ecx, 80070272h
0x14000acd9  jnz     short loc_14000AD2D
0x14000acdb  mov     ecx, 0C0000273h
0x14000ace0  jmp     loc_14000AD85
0x14000ace5  mov     ecx, 0C0000163h
0x14000acea  jmp     loc_14000AD85
0x14000acef  mov     ecx, 0C0000161h
0x14000acf4  jmp     loc_14000AD85
0x14000acf9  mov     ecx, 0C0000025h
0x14000acfe  jmp     loc_14000AD85
0x14000ad03  mov     ecx, 0C0000095h
0x14000ad08  jmp     short loc_14000AD85
0x14000ad0a  mov     ecx, 0C0000059h
0x14000ad0f  jmp     short loc_14000AD85
0x14000ad11  cmp     ecx, 8007054Fh
0x14000ad17  jz      short loc_14000AD79
0x14000ad19  cmp     ecx, 8007050Ch
0x14000ad1f  jz      short loc_14000AD80
0x14000ad21  cmp     ecx, 800705B9h
0x14000ad27  jz      short loc_14000AD72
0x14000ad29  test    ecx, ecx
0x14000ad2b  jz      short loc_14000AD6E
0x14000ad2d  bt      ecx, 1Ch
0x14000ad31  jnb     short loc_14000AD39
0x14000ad33  btr     ecx, 1Ch
0x14000ad37  jmp     short loc_14000AD85
0x14000ad39  mov     eax, ecx
0x14000ad3b  and     eax, 1FFF0000h
0x14000ad40  cmp     eax, 70000h
0x14000ad45  jnz     short loc_14000AD58
0x14000ad47  movzx   ecx, cx
0x14000ad4a  mov     eax, ecx
0x14000ad4c  or      eax, 0C0070000h
0x14000ad51  test    ecx, ecx
0x14000ad53  cmovnz  ecx, eax
0x14000ad56  jmp     short loc_14000AD85
0x14000ad58  cmp     eax, 90000h
0x14000ad5d  jnz     short loc_14000AD79
0x14000ad5f  test    ecx, ecx
0x14000ad61  jle     short loc_14000AD85
0x14000ad63  movzx   ecx, cx
0x14000ad66  or      ecx, 0C0090000h
0x14000ad6c  jmp     short loc_14000AD85
0x14000ad6e  xor     ecx, ecx
0x14000ad70  jmp     short loc_14000AD85
0x14000ad72  mov     ecx, 0C000A083h
0x14000ad77  jmp     short loc_14000AD85
0x14000ad79  mov     ecx, 0C00000E5h
0x14000ad7e  jmp     short loc_14000AD85
0x14000ad80  mov     ecx, 0C000042Bh
0x14000ad85  mov     eax, ecx
0x14000ad87  retn
```
