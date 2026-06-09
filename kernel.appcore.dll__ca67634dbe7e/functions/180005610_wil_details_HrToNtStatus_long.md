# wil::details::HrToNtStatus(long)

- ea: `0x180005610`
- end: `0x1800057ae`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `414`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005560`
- `0x1800058f4`
- `0x180005a4c`
- `0x1800091f4`
- `0x180009268`
- `0x180009488`

## callees

- `0x180005610`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (_DWORD)this == -2147023537 )
    goto LABEL_46;
  if ( (int)this <= -2147024895 )
  {
    if ( (_DWORD)this == -2147024895 )
    {
      LODWORD(this) = -1073741822;
      return (unsigned int)this;
    }
    if ( (_DWORD)this == -2147467259 )
    {
      LODWORD(this) = -1073741823;
      return (unsigned int)this;
    }
LABEL_34:
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
    if ( ((unsigned int)this & 0x1FFF0000) == 0x90000 )
    {
      if ( (int)this > 0 )
        LODWORD(this) = (unsigned __int16)this | 0xC0090000;
      return (unsigned int)this;
    }
LABEL_46:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (int)this > -2147024362 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
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
    goto LABEL_34;
  }
  if ( (_DWORD)this == -2147024362 )
  {
    LODWORD(this) = -1073741675;
  }
  else
  {
    switch ( (unsigned int)this )
    {
      case 0x80070002:
        LODWORD(this) = -1073741772;
        break;
      case 0x80070003:
        LODWORD(this) = -1073741766;
        break;
      case 0x8007000E:
        LODWORD(this) = -1073741801;
        break;
      case 0x80070057:
        LODWORD(this) = -1073741811;
        break;
      case 0x80070070:
        LODWORD(this) = -1073741697;
        break;
      case 0x8007007A:
        LODWORD(this) = -1073741789;
        break;
      case 0x8007007B:
        LODWORD(this) = -1073741773;
        break;
      case 0x8007007E:
        LODWORD(this) = -1073741515;
        break;
      case 0x800700EA:
        LODWORD(this) = -2147483643;
        break;
      default:
        goto LABEL_34;
    }
  }
  return (unsigned int)this;
}

```

## disassembly

```asm
0x180005610  cmp     ecx, 8007054Fh
0x180005616  jz      loc_1800057A6
0x18000561c  cmp     ecx, 80070001h
0x180005622  jg      short loc_180005646
0x180005624  jz      short loc_18000563C
0x180005626  cmp     ecx, 80004005h
0x18000562c  jnz     def_180005686; jumptable 0000000180005686 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180005632  mov     ecx, 0C0000001h
0x180005637  jmp     loc_1800057AB
0x18000563c  mov     ecx, 0C0000002h
0x180005641  jmp     loc_1800057AB
0x180005646  cmp     ecx, 80070216h
0x18000564c  jg      loc_1800056EC
0x180005652  jz      loc_1800056E2
0x180005658  lea     eax, [rcx+7FF8FFFEh]; switch 233 cases
0x18000565e  cmp     eax, 0E8h
0x180005663  ja      def_180005686; jumptable 0000000180005686 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180005669  lea     r8, __ImageBase
0x180005670  cdqe
0x180005672  movzx   eax, ds:(byte_1800057D8 - 180000000h)[r8+rax]
0x18000567b  mov     edx, ds:(jpt_180005686 - 180000000h)[r8+rax*4]
0x180005683  add     rdx, r8
0x180005686  jmp     rdx; switch jump
0x180005688  mov     ecx, 0C000000Dh; jumptable 0000000180005686 case -2147024809
0x18000568d  jmp     loc_1800057AB
0x180005692  mov     ecx, 0C0000017h; jumptable 0000000180005686 case -2147024882
0x180005697  jmp     loc_1800057AB
0x18000569c  mov     ecx, 0C000003Ah; jumptable 0000000180005686 case -2147024893
0x1800056a1  jmp     loc_1800057AB
0x1800056a6  mov     ecx, 0C0000034h; jumptable 0000000180005686 case -2147024894
0x1800056ab  jmp     loc_1800057AB
0x1800056b0  mov     ecx, 80000005h; jumptable 0000000180005686 case -2147024662
0x1800056b5  jmp     loc_1800057AB
0x1800056ba  mov     ecx, 0C0000023h; jumptable 0000000180005686 case -2147024774
0x1800056bf  jmp     loc_1800057AB
0x1800056c4  mov     ecx, 0C000007Fh; jumptable 0000000180005686 case -2147024784
0x1800056c9  jmp     loc_1800057AB
0x1800056ce  mov     ecx, 0C0000033h; jumptable 0000000180005686 case -2147024773
0x1800056d3  jmp     loc_1800057AB
0x1800056d8  mov     ecx, 0C0000135h; jumptable 0000000180005686 case -2147024770
0x1800056dd  jmp     loc_1800057AB
0x1800056e2  mov     ecx, 0C0000095h
0x1800056e7  jmp     loc_1800057AB
0x1800056ec  cmp     ecx, 8007047Eh
0x1800056f2  jg      short loc_18000573F
0x1800056f4  jz      short loc_180005738
0x1800056f6  cmp     ecx, 8007023Eh
0x1800056fc  jz      short loc_180005731
0x1800056fe  cmp     ecx, 80070246h
0x180005704  jz      short loc_18000572A
0x180005706  cmp     ecx, 80070247h
0x18000570c  jz      short loc_180005720
0x18000570e  cmp     ecx, 80070272h
0x180005714  jnz     short def_180005686; jumptable 0000000180005686 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180005716  mov     ecx, 0C0000273h
0x18000571b  jmp     loc_1800057AB
0x180005720  mov     ecx, 0C0000163h
0x180005725  jmp     loc_1800057AB
0x18000572a  mov     ecx, 0C0000161h
0x18000572f  jmp     short loc_1800057AB
0x180005731  mov     ecx, 0C0000025h
0x180005736  jmp     short loc_1800057AB
0x180005738  mov     ecx, 0C0000059h
0x18000573d  jmp     short loc_1800057AB
0x18000573f  cmp     ecx, 8007050Ch
0x180005745  jz      short loc_18000579F
0x180005747  cmp     ecx, 800705B9h
0x18000574d  jz      short loc_180005798
0x18000574f  test    ecx, ecx
0x180005751  jz      short loc_180005794
0x180005753  bt      ecx, 1Ch; jumptable 0000000180005686 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180005757  jnb     short loc_18000575F
0x180005759  btr     ecx, 1Ch
0x18000575d  jmp     short loc_1800057AB
0x18000575f  mov     eax, ecx
0x180005761  and     eax, 1FFF0000h
0x180005766  cmp     eax, 70000h
0x18000576b  jnz     short loc_18000577E
0x18000576d  movzx   ecx, cx
0x180005770  mov     eax, ecx
0x180005772  or      eax, 0C0070000h
0x180005777  test    ecx, ecx
0x180005779  cmovnz  ecx, eax
0x18000577c  jmp     short loc_1800057AB
0x18000577e  cmp     eax, 90000h
0x180005783  jnz     short loc_1800057A6
0x180005785  test    ecx, ecx
0x180005787  jle     short loc_1800057AB
0x180005789  movzx   ecx, cx
0x18000578c  or      ecx, 0C0090000h
0x180005792  jmp     short loc_1800057AB
0x180005794  xor     ecx, ecx
0x180005796  jmp     short loc_1800057AB
0x180005798  mov     ecx, 0C000A083h
0x18000579d  jmp     short loc_1800057AB
0x18000579f  mov     ecx, 0C000042Bh
0x1800057a4  jmp     short loc_1800057AB
0x1800057a6  mov     ecx, 0C00000E5h
0x1800057ab  mov     eax, ecx
0x1800057ad  retn
```
