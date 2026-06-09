# wil::details::HrToNtStatus(long)

- ea: `0x180005a7c`
- end: `0x180005c38`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003220`
- `0x1800032c0`
- `0x180003310`
- `0x1800033d0`
- `0x180005058`
- `0x180005c40`

## callees

- `0x180005a7c`

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
0x180005a7c  mov     eax, 800700EAh
0x180005a81  cmp     ecx, eax
0x180005a83  jg      loc_180005B58
0x180005a89  jz      loc_180005B4E
0x180005a8f  mov     eax, 80070057h
0x180005a94  cmp     ecx, eax
0x180005a96  jg      short loc_180005B02
0x180005a98  jz      short loc_180005AF8
0x180005a9a  cmp     ecx, 80004005h
0x180005aa0  jz      short loc_180005AEE
0x180005aa2  cmp     ecx, 80070001h
0x180005aa8  jz      short loc_180005AE4
0x180005aaa  cmp     ecx, 80070002h
0x180005ab0  jz      short loc_180005ADA
0x180005ab2  cmp     ecx, 80070003h
0x180005ab8  jz      short loc_180005AD0
0x180005aba  cmp     ecx, 8007000Eh
0x180005ac0  jnz     loc_180005BDD
0x180005ac6  mov     ecx, 0C0000017h
0x180005acb  jmp     loc_180005C35
0x180005ad0  mov     ecx, 0C000003Ah
0x180005ad5  jmp     loc_180005C35
0x180005ada  mov     ecx, 0C0000034h
0x180005adf  jmp     loc_180005C35
0x180005ae4  mov     ecx, 0C0000002h
0x180005ae9  jmp     loc_180005C35
0x180005aee  mov     ecx, 0C0000001h
0x180005af3  jmp     loc_180005C35
0x180005af8  mov     ecx, 0C000000Dh
0x180005afd  jmp     loc_180005C35
0x180005b02  cmp     ecx, 80070070h
0x180005b08  jz      short loc_180005B44
0x180005b0a  cmp     ecx, 8007007Ah
0x180005b10  jz      short loc_180005B3A
0x180005b12  cmp     ecx, 8007007Bh
0x180005b18  jz      short loc_180005B30
0x180005b1a  cmp     ecx, 8007007Eh
0x180005b20  jnz     loc_180005BDD
0x180005b26  mov     ecx, 0C0000135h
0x180005b2b  jmp     loc_180005C35
0x180005b30  mov     ecx, 0C0000033h
0x180005b35  jmp     loc_180005C35
0x180005b3a  mov     ecx, 0C0000023h
0x180005b3f  jmp     loc_180005C35
0x180005b44  mov     ecx, 0C000007Fh
0x180005b49  jmp     loc_180005C35
0x180005b4e  mov     ecx, 80000005h
0x180005b53  jmp     loc_180005C35
0x180005b58  mov     eax, 8007047Eh
0x180005b5d  cmp     ecx, eax
0x180005b5f  jg      short loc_180005BC1
0x180005b61  jz      short loc_180005BBA
0x180005b63  cmp     ecx, 80070216h
0x180005b69  jz      short loc_180005BB3
0x180005b6b  cmp     ecx, 8007023Eh
0x180005b71  jz      short loc_180005BA9
0x180005b73  cmp     ecx, 80070246h
0x180005b79  jz      short loc_180005B9F
0x180005b7b  cmp     ecx, 80070247h
0x180005b81  jz      short loc_180005B95
0x180005b83  cmp     ecx, 80070272h
0x180005b89  jnz     short loc_180005BDD
0x180005b8b  mov     ecx, 0C0000273h
0x180005b90  jmp     loc_180005C35
0x180005b95  mov     ecx, 0C0000163h
0x180005b9a  jmp     loc_180005C35
0x180005b9f  mov     ecx, 0C0000161h
0x180005ba4  jmp     loc_180005C35
0x180005ba9  mov     ecx, 0C0000025h
0x180005bae  jmp     loc_180005C35
0x180005bb3  mov     ecx, 0C0000095h
0x180005bb8  jmp     short loc_180005C35
0x180005bba  mov     ecx, 0C0000059h
0x180005bbf  jmp     short loc_180005C35
0x180005bc1  cmp     ecx, 8007050Ch
0x180005bc7  jz      short loc_180005C30
0x180005bc9  cmp     ecx, 8007054Fh
0x180005bcf  jz      short loc_180005C29
0x180005bd1  cmp     ecx, 800705B9h
0x180005bd7  jz      short loc_180005C22
0x180005bd9  test    ecx, ecx
0x180005bdb  jz      short loc_180005C1E
0x180005bdd  bt      ecx, 1Ch
0x180005be1  jnb     short loc_180005BE9
0x180005be3  btr     ecx, 1Ch
0x180005be7  jmp     short loc_180005C35
0x180005be9  mov     eax, ecx
0x180005beb  and     eax, 1FFF0000h
0x180005bf0  cmp     eax, 70000h
0x180005bf5  jnz     short loc_180005C08
0x180005bf7  movzx   ecx, cx
0x180005bfa  mov     eax, ecx
0x180005bfc  or      eax, 0C0070000h
0x180005c01  test    ecx, ecx
0x180005c03  cmovnz  ecx, eax
0x180005c06  jmp     short loc_180005C35
0x180005c08  cmp     eax, 90000h
0x180005c0d  jnz     short loc_180005C29
0x180005c0f  test    ecx, ecx
0x180005c11  jle     short loc_180005C35
0x180005c13  movzx   ecx, cx
0x180005c16  or      ecx, 0C0090000h
0x180005c1c  jmp     short loc_180005C35
0x180005c1e  xor     ecx, ecx
0x180005c20  jmp     short loc_180005C35
0x180005c22  mov     ecx, 0C000A083h
0x180005c27  jmp     short loc_180005C35
0x180005c29  mov     ecx, 0C00000E5h
0x180005c2e  jmp     short loc_180005C35
0x180005c30  mov     ecx, 0C000042Bh
0x180005c35  mov     eax, ecx
0x180005c37  retn
```
