# wil::details::HrToNtStatus(long)

- ea: `0x140006078`
- end: `0x140006234`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002eac`
- `0x140002f4c`
- `0x140002f9c`
- `0x140003054`
- `0x140004d98`
- `0x140006cd4`

## callees

- `0x140006078`

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
0x140006078  mov     eax, 800700EAh
0x14000607d  cmp     ecx, eax
0x14000607f  jg      loc_140006154
0x140006085  jz      loc_14000614A
0x14000608b  mov     eax, 80070057h
0x140006090  cmp     ecx, eax
0x140006092  jg      short loc_1400060FE
0x140006094  jz      short loc_1400060F4
0x140006096  cmp     ecx, 80004005h
0x14000609c  jz      short loc_1400060EA
0x14000609e  cmp     ecx, 80070001h
0x1400060a4  jz      short loc_1400060E0
0x1400060a6  cmp     ecx, 80070002h
0x1400060ac  jz      short loc_1400060D6
0x1400060ae  cmp     ecx, 80070003h
0x1400060b4  jz      short loc_1400060CC
0x1400060b6  cmp     ecx, 8007000Eh
0x1400060bc  jnz     loc_1400061D9
0x1400060c2  mov     ecx, 0C0000017h
0x1400060c7  jmp     loc_140006231
0x1400060cc  mov     ecx, 0C000003Ah
0x1400060d1  jmp     loc_140006231
0x1400060d6  mov     ecx, 0C0000034h
0x1400060db  jmp     loc_140006231
0x1400060e0  mov     ecx, 0C0000002h
0x1400060e5  jmp     loc_140006231
0x1400060ea  mov     ecx, 0C0000001h
0x1400060ef  jmp     loc_140006231
0x1400060f4  mov     ecx, 0C000000Dh
0x1400060f9  jmp     loc_140006231
0x1400060fe  cmp     ecx, 80070070h
0x140006104  jz      short loc_140006140
0x140006106  cmp     ecx, 8007007Ah
0x14000610c  jz      short loc_140006136
0x14000610e  cmp     ecx, 8007007Bh
0x140006114  jz      short loc_14000612C
0x140006116  cmp     ecx, 8007007Eh
0x14000611c  jnz     loc_1400061D9
0x140006122  mov     ecx, 0C0000135h
0x140006127  jmp     loc_140006231
0x14000612c  mov     ecx, 0C0000033h
0x140006131  jmp     loc_140006231
0x140006136  mov     ecx, 0C0000023h
0x14000613b  jmp     loc_140006231
0x140006140  mov     ecx, 0C000007Fh
0x140006145  jmp     loc_140006231
0x14000614a  mov     ecx, 80000005h
0x14000614f  jmp     loc_140006231
0x140006154  mov     eax, 8007047Eh
0x140006159  cmp     ecx, eax
0x14000615b  jg      short loc_1400061BD
0x14000615d  jz      short loc_1400061B6
0x14000615f  cmp     ecx, 80070216h
0x140006165  jz      short loc_1400061AF
0x140006167  cmp     ecx, 8007023Eh
0x14000616d  jz      short loc_1400061A5
0x14000616f  cmp     ecx, 80070246h
0x140006175  jz      short loc_14000619B
0x140006177  cmp     ecx, 80070247h
0x14000617d  jz      short loc_140006191
0x14000617f  cmp     ecx, 80070272h
0x140006185  jnz     short loc_1400061D9
0x140006187  mov     ecx, 0C0000273h
0x14000618c  jmp     loc_140006231
0x140006191  mov     ecx, 0C0000163h
0x140006196  jmp     loc_140006231
0x14000619b  mov     ecx, 0C0000161h
0x1400061a0  jmp     loc_140006231
0x1400061a5  mov     ecx, 0C0000025h
0x1400061aa  jmp     loc_140006231
0x1400061af  mov     ecx, 0C0000095h
0x1400061b4  jmp     short loc_140006231
0x1400061b6  mov     ecx, 0C0000059h
0x1400061bb  jmp     short loc_140006231
0x1400061bd  cmp     ecx, 8007050Ch
0x1400061c3  jz      short loc_14000622C
0x1400061c5  cmp     ecx, 8007054Fh
0x1400061cb  jz      short loc_140006225
0x1400061cd  cmp     ecx, 800705B9h
0x1400061d3  jz      short loc_14000621E
0x1400061d5  test    ecx, ecx
0x1400061d7  jz      short loc_14000621A
0x1400061d9  bt      ecx, 1Ch
0x1400061dd  jnb     short loc_1400061E5
0x1400061df  btr     ecx, 1Ch
0x1400061e3  jmp     short loc_140006231
0x1400061e5  mov     eax, ecx
0x1400061e7  and     eax, 1FFF0000h
0x1400061ec  cmp     eax, 70000h
0x1400061f1  jnz     short loc_140006204
0x1400061f3  movzx   ecx, cx
0x1400061f6  mov     eax, ecx
0x1400061f8  or      eax, 0C0070000h
0x1400061fd  test    ecx, ecx
0x1400061ff  cmovnz  ecx, eax
0x140006202  jmp     short loc_140006231
0x140006204  cmp     eax, 90000h
0x140006209  jnz     short loc_140006225
0x14000620b  test    ecx, ecx
0x14000620d  jle     short loc_140006231
0x14000620f  movzx   ecx, cx
0x140006212  or      ecx, 0C0090000h
0x140006218  jmp     short loc_140006231
0x14000621a  xor     ecx, ecx
0x14000621c  jmp     short loc_140006231
0x14000621e  mov     ecx, 0C000A083h
0x140006223  jmp     short loc_140006231
0x140006225  mov     ecx, 0C00000E5h
0x14000622a  jmp     short loc_140006231
0x14000622c  mov     ecx, 0C000042Bh
0x140006231  mov     eax, ecx
0x140006233  retn
```
