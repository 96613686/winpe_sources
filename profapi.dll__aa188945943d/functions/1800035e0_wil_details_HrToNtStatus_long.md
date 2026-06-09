# wil::details::HrToNtStatus(long)

- ea: `0x1800035e0`
- end: `0x1800037cc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `492`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001514`
- `0x180002548`
- `0x180003564`
- `0x1800037d4`
- `0x18000c308`
- `0x18000c4e8`
- `0x18000c648`
- `0x1800108a4`
- `0x18001091c`
- `0x180011e6c`
- `0x18001676c`

## callees

- `0x1800035e0`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (int)this > -2147024662 )
  {
    if ( (int)this <= -2147023746 )
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
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x8007054F:
          goto LABEL_26;
        case 0x800705B9:
          LODWORD(this) = -1073700733;
          return (unsigned int)this;
        case 0:
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
    if ( (_DWORD)this == -2147024809 )
    {
      LODWORD(this) = -1073741811;
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
        case 0x80070002:
          LODWORD(this) = -1073741772;
          return (unsigned int)this;
        case 0x80004005:
          LODWORD(this) = -1073741823;
          return (unsigned int)this;
        case 0x80070001:
          LODWORD(this) = -1073741822;
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
LABEL_26:
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
0x1800035e0  mov     eax, 800700EAh
0x1800035e5  cmp     ecx, eax
0x1800035e7  jg      short loc_180003666
0x1800035e9  jz      loc_18000372E
0x1800035ef  mov     eax, 80070057h
0x1800035f4  cmp     ecx, eax
0x1800035f6  jz      short loc_18000360D
0x1800035f8  jg      loc_1800036E2
0x1800035fe  cmp     ecx, 80070002h
0x180003604  jnz     short loc_180003615
0x180003606  mov     ecx, 0C0000034h
0x18000360b  jmp     short loc_180003612
0x18000360d  mov     ecx, 0C000000Dh
0x180003612  mov     eax, ecx
0x180003614  retn
0x180003615  cmp     ecx, 80004005h
0x18000361b  jz      loc_1800036D8
0x180003621  cmp     ecx, 80070001h
0x180003627  jz      loc_1800036CE
0x18000362d  cmp     ecx, 80070003h
0x180003633  jz      loc_1800036C4
0x180003639  cmp     ecx, 8007000Eh
0x18000363f  jz      short loc_1800036BA
0x180003641  bt      ecx, 1Ch
0x180003645  jb      short loc_18000369C
0x180003647  mov     eax, ecx
0x180003649  and     eax, 1FFF0000h
0x18000364e  cmp     eax, 70000h
0x180003653  jnz     short loc_1800036A5
0x180003655  movzx   ecx, cx
0x180003658  mov     eax, ecx
0x18000365a  or      eax, 0C0070000h
0x18000365f  test    ecx, ecx
0x180003661  cmovnz  ecx, eax
0x180003664  jmp     short loc_180003612
0x180003666  mov     eax, 8007047Eh
0x18000366b  cmp     ecx, eax
0x18000366d  jle     loc_180003738
0x180003673  cmp     ecx, 8007050Ch
0x180003679  jz      loc_1800037C2
0x18000367f  cmp     ecx, 8007054Fh
0x180003685  jz      short loc_1800036B0
0x180003687  cmp     ecx, 800705B9h
0x18000368d  jz      loc_1800037B8
0x180003693  test    ecx, ecx
0x180003695  jnz     short loc_180003641
0x180003697  jmp     loc_180003612
0x18000369c  btr     ecx, 1Ch
0x1800036a0  jmp     loc_180003612
0x1800036a5  cmp     eax, 90000h
0x1800036aa  jz      loc_1800037A2
0x1800036b0  mov     ecx, 0C00000E5h
0x1800036b5  jmp     loc_180003612
0x1800036ba  mov     ecx, 0C0000017h
0x1800036bf  jmp     loc_180003612
0x1800036c4  mov     ecx, 0C000003Ah
0x1800036c9  jmp     loc_180003612
0x1800036ce  mov     ecx, 0C0000002h
0x1800036d3  jmp     loc_180003612
0x1800036d8  mov     ecx, 0C0000001h
0x1800036dd  jmp     loc_180003612
0x1800036e2  cmp     ecx, 80070070h
0x1800036e8  jz      short loc_180003724
0x1800036ea  cmp     ecx, 8007007Ah
0x1800036f0  jz      short loc_18000371A
0x1800036f2  cmp     ecx, 8007007Bh
0x1800036f8  jz      short loc_180003710
0x1800036fa  cmp     ecx, 8007007Eh
0x180003700  jnz     loc_180003641
0x180003706  mov     ecx, 0C0000135h
0x18000370b  jmp     loc_180003612
0x180003710  mov     ecx, 0C0000033h
0x180003715  jmp     loc_180003612
0x18000371a  mov     ecx, 0C0000023h
0x18000371f  jmp     loc_180003612
0x180003724  mov     ecx, 0C000007Fh
0x180003729  jmp     loc_180003612
0x18000372e  mov     ecx, 80000005h
0x180003733  jmp     loc_180003612
0x180003738  jz      short loc_180003798
0x18000373a  cmp     ecx, 80070216h
0x180003740  jz      short loc_18000378E
0x180003742  cmp     ecx, 8007023Eh
0x180003748  jz      short loc_180003784
0x18000374a  cmp     ecx, 80070246h
0x180003750  jz      short loc_18000377A
0x180003752  cmp     ecx, 80070247h
0x180003758  jz      short loc_180003770
0x18000375a  cmp     ecx, 80070272h
0x180003760  jnz     loc_180003641
0x180003766  mov     ecx, 0C0000273h
0x18000376b  jmp     loc_180003612
0x180003770  mov     ecx, 0C0000163h
0x180003775  jmp     loc_180003612
0x18000377a  mov     ecx, 0C0000161h
0x18000377f  jmp     loc_180003612
0x180003784  mov     ecx, 0C0000025h
0x180003789  jmp     loc_180003612
0x18000378e  mov     ecx, 0C0000095h
0x180003793  jmp     loc_180003612
0x180003798  mov     ecx, 0C0000059h
0x18000379d  jmp     loc_180003612
0x1800037a2  test    ecx, ecx
0x1800037a4  jle     loc_180003612
0x1800037aa  movzx   ecx, cx
0x1800037ad  or      ecx, 0C0090000h
0x1800037b3  jmp     loc_180003612
0x1800037b8  mov     ecx, 0C000A083h
0x1800037bd  jmp     loc_180003612
0x1800037c2  mov     ecx, 0C000042Bh
0x1800037c7  jmp     loc_180003612
```
