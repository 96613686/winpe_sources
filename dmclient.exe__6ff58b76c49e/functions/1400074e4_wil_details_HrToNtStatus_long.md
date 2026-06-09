# wil::details::HrToNtStatus(long)

- ea: `0x1400074e4`
- end: `0x1400076a0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400033b8`
- `0x140003460`
- `0x1400034b0`
- `0x1400035c0`
- `0x140006ac8`
- `0x140007b00`

## callees

- `0x1400074e4`

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
0x1400074e4  mov     eax, 800700EAh
0x1400074e9  cmp     ecx, eax
0x1400074eb  jg      loc_1400075C0
0x1400074f1  jz      loc_1400075B6
0x1400074f7  mov     eax, 80070057h
0x1400074fc  cmp     ecx, eax
0x1400074fe  jg      short loc_14000756A
0x140007500  jz      short loc_140007560
0x140007502  cmp     ecx, 80004005h
0x140007508  jz      short loc_140007556
0x14000750a  cmp     ecx, 80070001h
0x140007510  jz      short loc_14000754C
0x140007512  cmp     ecx, 80070002h
0x140007518  jz      short loc_140007542
0x14000751a  cmp     ecx, 80070003h
0x140007520  jz      short loc_140007538
0x140007522  cmp     ecx, 8007000Eh
0x140007528  jnz     loc_140007645
0x14000752e  mov     ecx, 0C0000017h
0x140007533  jmp     loc_14000769D
0x140007538  mov     ecx, 0C000003Ah
0x14000753d  jmp     loc_14000769D
0x140007542  mov     ecx, 0C0000034h
0x140007547  jmp     loc_14000769D
0x14000754c  mov     ecx, 0C0000002h
0x140007551  jmp     loc_14000769D
0x140007556  mov     ecx, 0C0000001h
0x14000755b  jmp     loc_14000769D
0x140007560  mov     ecx, 0C000000Dh
0x140007565  jmp     loc_14000769D
0x14000756a  cmp     ecx, 80070070h
0x140007570  jz      short loc_1400075AC
0x140007572  cmp     ecx, 8007007Ah
0x140007578  jz      short loc_1400075A2
0x14000757a  cmp     ecx, 8007007Bh
0x140007580  jz      short loc_140007598
0x140007582  cmp     ecx, 8007007Eh
0x140007588  jnz     loc_140007645
0x14000758e  mov     ecx, 0C0000135h
0x140007593  jmp     loc_14000769D
0x140007598  mov     ecx, 0C0000033h
0x14000759d  jmp     loc_14000769D
0x1400075a2  mov     ecx, 0C0000023h
0x1400075a7  jmp     loc_14000769D
0x1400075ac  mov     ecx, 0C000007Fh
0x1400075b1  jmp     loc_14000769D
0x1400075b6  mov     ecx, 80000005h
0x1400075bb  jmp     loc_14000769D
0x1400075c0  mov     eax, 8007047Eh
0x1400075c5  cmp     ecx, eax
0x1400075c7  jg      short loc_140007629
0x1400075c9  jz      short loc_140007622
0x1400075cb  cmp     ecx, 80070216h
0x1400075d1  jz      short loc_14000761B
0x1400075d3  cmp     ecx, 8007023Eh
0x1400075d9  jz      short loc_140007611
0x1400075db  cmp     ecx, 80070246h
0x1400075e1  jz      short loc_140007607
0x1400075e3  cmp     ecx, 80070247h
0x1400075e9  jz      short loc_1400075FD
0x1400075eb  cmp     ecx, 80070272h
0x1400075f1  jnz     short loc_140007645
0x1400075f3  mov     ecx, 0C0000273h
0x1400075f8  jmp     loc_14000769D
0x1400075fd  mov     ecx, 0C0000163h
0x140007602  jmp     loc_14000769D
0x140007607  mov     ecx, 0C0000161h
0x14000760c  jmp     loc_14000769D
0x140007611  mov     ecx, 0C0000025h
0x140007616  jmp     loc_14000769D
0x14000761b  mov     ecx, 0C0000095h
0x140007620  jmp     short loc_14000769D
0x140007622  mov     ecx, 0C0000059h
0x140007627  jmp     short loc_14000769D
0x140007629  cmp     ecx, 8007050Ch
0x14000762f  jz      short loc_140007698
0x140007631  cmp     ecx, 8007054Fh
0x140007637  jz      short loc_140007691
0x140007639  cmp     ecx, 800705B9h
0x14000763f  jz      short loc_14000768A
0x140007641  test    ecx, ecx
0x140007643  jz      short loc_140007686
0x140007645  bt      ecx, 1Ch
0x140007649  jnb     short loc_140007651
0x14000764b  btr     ecx, 1Ch
0x14000764f  jmp     short loc_14000769D
0x140007651  mov     eax, ecx
0x140007653  and     eax, 1FFF0000h
0x140007658  cmp     eax, 70000h
0x14000765d  jnz     short loc_140007670
0x14000765f  movzx   ecx, cx
0x140007662  mov     eax, ecx
0x140007664  or      eax, 0C0070000h
0x140007669  test    ecx, ecx
0x14000766b  cmovnz  ecx, eax
0x14000766e  jmp     short loc_14000769D
0x140007670  cmp     eax, 90000h
0x140007675  jnz     short loc_140007691
0x140007677  test    ecx, ecx
0x140007679  jle     short loc_14000769D
0x14000767b  movzx   ecx, cx
0x14000767e  or      ecx, 0C0090000h
0x140007684  jmp     short loc_14000769D
0x140007686  xor     ecx, ecx
0x140007688  jmp     short loc_14000769D
0x14000768a  mov     ecx, 0C000A083h
0x14000768f  jmp     short loc_14000769D
0x140007691  mov     ecx, 0C00000E5h
0x140007696  jmp     short loc_14000769D
0x140007698  mov     ecx, 0C000042Bh
0x14000769d  mov     eax, ecx
0x14000769f  retn
```
