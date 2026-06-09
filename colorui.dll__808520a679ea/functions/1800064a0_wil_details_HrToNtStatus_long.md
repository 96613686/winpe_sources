# wil::details::HrToNtStatus(long)

- ea: `0x1800064a0`
- end: `0x18000665c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002464`
- `0x18000250c`
- `0x18000255c`
- `0x18000261c`
- `0x1800059d8`
- `0x180006ba0`

## callees

- `0x1800064a0`

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
0x1800064a0  mov     eax, 800700EAh
0x1800064a5  cmp     ecx, eax
0x1800064a7  jg      loc_18000657C
0x1800064ad  jz      loc_180006572
0x1800064b3  mov     eax, 80070057h
0x1800064b8  cmp     ecx, eax
0x1800064ba  jg      short loc_180006526
0x1800064bc  jz      short loc_18000651C
0x1800064be  cmp     ecx, 80004005h
0x1800064c4  jz      short loc_180006512
0x1800064c6  cmp     ecx, 80070001h
0x1800064cc  jz      short loc_180006508
0x1800064ce  cmp     ecx, 80070002h
0x1800064d4  jz      short loc_1800064FE
0x1800064d6  cmp     ecx, 80070003h
0x1800064dc  jz      short loc_1800064F4
0x1800064de  cmp     ecx, 8007000Eh
0x1800064e4  jnz     loc_180006601
0x1800064ea  mov     ecx, 0C0000017h
0x1800064ef  jmp     loc_180006659
0x1800064f4  mov     ecx, 0C000003Ah
0x1800064f9  jmp     loc_180006659
0x1800064fe  mov     ecx, 0C0000034h
0x180006503  jmp     loc_180006659
0x180006508  mov     ecx, 0C0000002h
0x18000650d  jmp     loc_180006659
0x180006512  mov     ecx, 0C0000001h
0x180006517  jmp     loc_180006659
0x18000651c  mov     ecx, 0C000000Dh
0x180006521  jmp     loc_180006659
0x180006526  cmp     ecx, 80070070h
0x18000652c  jz      short loc_180006568
0x18000652e  cmp     ecx, 8007007Ah
0x180006534  jz      short loc_18000655E
0x180006536  cmp     ecx, 8007007Bh
0x18000653c  jz      short loc_180006554
0x18000653e  cmp     ecx, 8007007Eh
0x180006544  jnz     loc_180006601
0x18000654a  mov     ecx, 0C0000135h
0x18000654f  jmp     loc_180006659
0x180006554  mov     ecx, 0C0000033h
0x180006559  jmp     loc_180006659
0x18000655e  mov     ecx, 0C0000023h
0x180006563  jmp     loc_180006659
0x180006568  mov     ecx, 0C000007Fh
0x18000656d  jmp     loc_180006659
0x180006572  mov     ecx, 80000005h
0x180006577  jmp     loc_180006659
0x18000657c  mov     eax, 8007047Eh
0x180006581  cmp     ecx, eax
0x180006583  jg      short loc_1800065E5
0x180006585  jz      short loc_1800065DE
0x180006587  cmp     ecx, 80070216h
0x18000658d  jz      short loc_1800065D7
0x18000658f  cmp     ecx, 8007023Eh
0x180006595  jz      short loc_1800065CD
0x180006597  cmp     ecx, 80070246h
0x18000659d  jz      short loc_1800065C3
0x18000659f  cmp     ecx, 80070247h
0x1800065a5  jz      short loc_1800065B9
0x1800065a7  cmp     ecx, 80070272h
0x1800065ad  jnz     short loc_180006601
0x1800065af  mov     ecx, 0C0000273h
0x1800065b4  jmp     loc_180006659
0x1800065b9  mov     ecx, 0C0000163h
0x1800065be  jmp     loc_180006659
0x1800065c3  mov     ecx, 0C0000161h
0x1800065c8  jmp     loc_180006659
0x1800065cd  mov     ecx, 0C0000025h
0x1800065d2  jmp     loc_180006659
0x1800065d7  mov     ecx, 0C0000095h
0x1800065dc  jmp     short loc_180006659
0x1800065de  mov     ecx, 0C0000059h
0x1800065e3  jmp     short loc_180006659
0x1800065e5  cmp     ecx, 8007050Ch
0x1800065eb  jz      short loc_180006654
0x1800065ed  cmp     ecx, 8007054Fh
0x1800065f3  jz      short loc_18000664D
0x1800065f5  cmp     ecx, 800705B9h
0x1800065fb  jz      short loc_180006646
0x1800065fd  test    ecx, ecx
0x1800065ff  jz      short loc_180006642
0x180006601  bt      ecx, 1Ch
0x180006605  jnb     short loc_18000660D
0x180006607  btr     ecx, 1Ch
0x18000660b  jmp     short loc_180006659
0x18000660d  mov     eax, ecx
0x18000660f  and     eax, 1FFF0000h
0x180006614  cmp     eax, 70000h
0x180006619  jnz     short loc_18000662C
0x18000661b  movzx   ecx, cx
0x18000661e  mov     eax, ecx
0x180006620  or      eax, 0C0070000h
0x180006625  test    ecx, ecx
0x180006627  cmovnz  ecx, eax
0x18000662a  jmp     short loc_180006659
0x18000662c  cmp     eax, 90000h
0x180006631  jnz     short loc_18000664D
0x180006633  test    ecx, ecx
0x180006635  jle     short loc_180006659
0x180006637  movzx   ecx, cx
0x18000663a  or      ecx, 0C0090000h
0x180006640  jmp     short loc_180006659
0x180006642  xor     ecx, ecx
0x180006644  jmp     short loc_180006659
0x180006646  mov     ecx, 0C000A083h
0x18000664b  jmp     short loc_180006659
0x18000664d  mov     ecx, 0C00000E5h
0x180006652  jmp     short loc_180006659
0x180006654  mov     ecx, 0C000042Bh
0x180006659  mov     eax, ecx
0x18000665b  retn
```
