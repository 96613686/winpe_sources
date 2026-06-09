# wil::details::HrToNtStatus(long)

- ea: `0x180002b90`
- end: `0x180002d2e`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `414`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002780`
- `0x1800032b4`
- `0x180003360`
- `0x180006098`
- `0x180006108`
- `0x18000617c`
- `0x180008904`
- `0x180008988`
- `0x180008a0c`

## callees

- `0x180002b90`

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
0x180002b90  cmp     ecx, 8007054Fh
0x180002b96  jz      loc_180002D26
0x180002b9c  cmp     ecx, 80070001h
0x180002ba2  jg      short loc_180002BC6
0x180002ba4  jz      short loc_180002BBC
0x180002ba6  cmp     ecx, 80004005h
0x180002bac  jnz     def_180002C06; jumptable 0000000180002C06 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180002bb2  mov     ecx, 0C0000001h
0x180002bb7  jmp     loc_180002D2B
0x180002bbc  mov     ecx, 0C0000002h
0x180002bc1  jmp     loc_180002D2B
0x180002bc6  cmp     ecx, 80070216h
0x180002bcc  jg      loc_180002C6C
0x180002bd2  jz      loc_180002C62
0x180002bd8  lea     eax, [rcx+7FF8FFFEh]; switch 233 cases
0x180002bde  cmp     eax, 0E8h
0x180002be3  ja      def_180002C06; jumptable 0000000180002C06 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180002be9  lea     r8, __ImageBase
0x180002bf0  cdqe
0x180002bf2  movzx   eax, ds:(byte_180002D58 - 180000000h)[r8+rax]
0x180002bfb  mov     edx, ds:(jpt_180002C06 - 180000000h)[r8+rax*4]
0x180002c03  add     rdx, r8
0x180002c06  jmp     rdx; switch jump
0x180002c08  mov     ecx, 0C000000Dh; jumptable 0000000180002C06 case -2147024809
0x180002c0d  jmp     loc_180002D2B
0x180002c12  mov     ecx, 0C0000017h; jumptable 0000000180002C06 case -2147024882
0x180002c17  jmp     loc_180002D2B
0x180002c1c  mov     ecx, 0C000003Ah; jumptable 0000000180002C06 case -2147024893
0x180002c21  jmp     loc_180002D2B
0x180002c26  mov     ecx, 0C0000034h; jumptable 0000000180002C06 case -2147024894
0x180002c2b  jmp     loc_180002D2B
0x180002c30  mov     ecx, 80000005h; jumptable 0000000180002C06 case -2147024662
0x180002c35  jmp     loc_180002D2B
0x180002c3a  mov     ecx, 0C0000023h; jumptable 0000000180002C06 case -2147024774
0x180002c3f  jmp     loc_180002D2B
0x180002c44  mov     ecx, 0C000007Fh; jumptable 0000000180002C06 case -2147024784
0x180002c49  jmp     loc_180002D2B
0x180002c4e  mov     ecx, 0C0000033h; jumptable 0000000180002C06 case -2147024773
0x180002c53  jmp     loc_180002D2B
0x180002c58  mov     ecx, 0C0000135h; jumptable 0000000180002C06 case -2147024770
0x180002c5d  jmp     loc_180002D2B
0x180002c62  mov     ecx, 0C0000095h
0x180002c67  jmp     loc_180002D2B
0x180002c6c  cmp     ecx, 8007047Eh
0x180002c72  jg      short loc_180002CBF
0x180002c74  jz      short loc_180002CB8
0x180002c76  cmp     ecx, 8007023Eh
0x180002c7c  jz      short loc_180002CB1
0x180002c7e  cmp     ecx, 80070246h
0x180002c84  jz      short loc_180002CAA
0x180002c86  cmp     ecx, 80070247h
0x180002c8c  jz      short loc_180002CA0
0x180002c8e  cmp     ecx, 80070272h
0x180002c94  jnz     short def_180002C06; jumptable 0000000180002C06 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180002c96  mov     ecx, 0C0000273h
0x180002c9b  jmp     loc_180002D2B
0x180002ca0  mov     ecx, 0C0000163h
0x180002ca5  jmp     loc_180002D2B
0x180002caa  mov     ecx, 0C0000161h
0x180002caf  jmp     short loc_180002D2B
0x180002cb1  mov     ecx, 0C0000025h
0x180002cb6  jmp     short loc_180002D2B
0x180002cb8  mov     ecx, 0C0000059h
0x180002cbd  jmp     short loc_180002D2B
0x180002cbf  cmp     ecx, 8007050Ch
0x180002cc5  jz      short loc_180002D1F
0x180002cc7  cmp     ecx, 800705B9h
0x180002ccd  jz      short loc_180002D18
0x180002ccf  test    ecx, ecx
0x180002cd1  jz      short loc_180002D14
0x180002cd3  bt      ecx, 1Ch; jumptable 0000000180002C06 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180002cd7  jnb     short loc_180002CDF
0x180002cd9  btr     ecx, 1Ch
0x180002cdd  jmp     short loc_180002D2B
0x180002cdf  mov     eax, ecx
0x180002ce1  and     eax, 1FFF0000h
0x180002ce6  cmp     eax, 70000h
0x180002ceb  jnz     short loc_180002CFE
0x180002ced  movzx   ecx, cx
0x180002cf0  mov     eax, ecx
0x180002cf2  or      eax, 0C0070000h
0x180002cf7  test    ecx, ecx
0x180002cf9  cmovnz  ecx, eax
0x180002cfc  jmp     short loc_180002D2B
0x180002cfe  cmp     eax, 90000h
0x180002d03  jnz     short loc_180002D26
0x180002d05  test    ecx, ecx
0x180002d07  jle     short loc_180002D2B
0x180002d09  movzx   ecx, cx
0x180002d0c  or      ecx, 0C0090000h
0x180002d12  jmp     short loc_180002D2B
0x180002d14  xor     ecx, ecx
0x180002d16  jmp     short loc_180002D2B
0x180002d18  mov     ecx, 0C000A083h
0x180002d1d  jmp     short loc_180002D2B
0x180002d1f  mov     ecx, 0C000042Bh
0x180002d24  jmp     short loc_180002D2B
0x180002d26  mov     ecx, 0C00000E5h
0x180002d2b  mov     eax, ecx
0x180002d2d  retn
```
