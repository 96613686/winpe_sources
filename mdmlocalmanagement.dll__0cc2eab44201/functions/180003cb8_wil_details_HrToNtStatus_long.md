# wil::details::HrToNtStatus(long)

- ea: `0x180003cb8`
- end: `0x180003e74`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021f0`
- `0x180002298`
- `0x1800022e8`
- `0x1800023a0`
- `0x1800032e4`
- `0x180003e7c`

## callees

- `0x180003cb8`

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
0x180003cb8  mov     eax, 800700EAh
0x180003cbd  cmp     ecx, eax
0x180003cbf  jg      loc_180003D94
0x180003cc5  jz      loc_180003D8A
0x180003ccb  mov     eax, 80070057h
0x180003cd0  cmp     ecx, eax
0x180003cd2  jg      short loc_180003D3E
0x180003cd4  jz      short loc_180003D34
0x180003cd6  cmp     ecx, 80004005h
0x180003cdc  jz      short loc_180003D2A
0x180003cde  cmp     ecx, 80070001h
0x180003ce4  jz      short loc_180003D20
0x180003ce6  cmp     ecx, 80070002h
0x180003cec  jz      short loc_180003D16
0x180003cee  cmp     ecx, 80070003h
0x180003cf4  jz      short loc_180003D0C
0x180003cf6  cmp     ecx, 8007000Eh
0x180003cfc  jnz     loc_180003E19
0x180003d02  mov     ecx, 0C0000017h
0x180003d07  jmp     loc_180003E71
0x180003d0c  mov     ecx, 0C000003Ah
0x180003d11  jmp     loc_180003E71
0x180003d16  mov     ecx, 0C0000034h
0x180003d1b  jmp     loc_180003E71
0x180003d20  mov     ecx, 0C0000002h
0x180003d25  jmp     loc_180003E71
0x180003d2a  mov     ecx, 0C0000001h
0x180003d2f  jmp     loc_180003E71
0x180003d34  mov     ecx, 0C000000Dh
0x180003d39  jmp     loc_180003E71
0x180003d3e  cmp     ecx, 80070070h
0x180003d44  jz      short loc_180003D80
0x180003d46  cmp     ecx, 8007007Ah
0x180003d4c  jz      short loc_180003D76
0x180003d4e  cmp     ecx, 8007007Bh
0x180003d54  jz      short loc_180003D6C
0x180003d56  cmp     ecx, 8007007Eh
0x180003d5c  jnz     loc_180003E19
0x180003d62  mov     ecx, 0C0000135h
0x180003d67  jmp     loc_180003E71
0x180003d6c  mov     ecx, 0C0000033h
0x180003d71  jmp     loc_180003E71
0x180003d76  mov     ecx, 0C0000023h
0x180003d7b  jmp     loc_180003E71
0x180003d80  mov     ecx, 0C000007Fh
0x180003d85  jmp     loc_180003E71
0x180003d8a  mov     ecx, 80000005h
0x180003d8f  jmp     loc_180003E71
0x180003d94  mov     eax, 8007047Eh
0x180003d99  cmp     ecx, eax
0x180003d9b  jg      short loc_180003DFD
0x180003d9d  jz      short loc_180003DF6
0x180003d9f  cmp     ecx, 80070216h
0x180003da5  jz      short loc_180003DEF
0x180003da7  cmp     ecx, 8007023Eh
0x180003dad  jz      short loc_180003DE5
0x180003daf  cmp     ecx, 80070246h
0x180003db5  jz      short loc_180003DDB
0x180003db7  cmp     ecx, 80070247h
0x180003dbd  jz      short loc_180003DD1
0x180003dbf  cmp     ecx, 80070272h
0x180003dc5  jnz     short loc_180003E19
0x180003dc7  mov     ecx, 0C0000273h
0x180003dcc  jmp     loc_180003E71
0x180003dd1  mov     ecx, 0C0000163h
0x180003dd6  jmp     loc_180003E71
0x180003ddb  mov     ecx, 0C0000161h
0x180003de0  jmp     loc_180003E71
0x180003de5  mov     ecx, 0C0000025h
0x180003dea  jmp     loc_180003E71
0x180003def  mov     ecx, 0C0000095h
0x180003df4  jmp     short loc_180003E71
0x180003df6  mov     ecx, 0C0000059h
0x180003dfb  jmp     short loc_180003E71
0x180003dfd  cmp     ecx, 8007050Ch
0x180003e03  jz      short loc_180003E6C
0x180003e05  cmp     ecx, 8007054Fh
0x180003e0b  jz      short loc_180003E65
0x180003e0d  cmp     ecx, 800705B9h
0x180003e13  jz      short loc_180003E5E
0x180003e15  test    ecx, ecx
0x180003e17  jz      short loc_180003E5A
0x180003e19  bt      ecx, 1Ch
0x180003e1d  jnb     short loc_180003E25
0x180003e1f  btr     ecx, 1Ch
0x180003e23  jmp     short loc_180003E71
0x180003e25  mov     eax, ecx
0x180003e27  and     eax, 1FFF0000h
0x180003e2c  cmp     eax, 70000h
0x180003e31  jnz     short loc_180003E44
0x180003e33  movzx   ecx, cx
0x180003e36  mov     eax, ecx
0x180003e38  or      eax, 0C0070000h
0x180003e3d  test    ecx, ecx
0x180003e3f  cmovnz  ecx, eax
0x180003e42  jmp     short loc_180003E71
0x180003e44  cmp     eax, 90000h
0x180003e49  jnz     short loc_180003E65
0x180003e4b  test    ecx, ecx
0x180003e4d  jle     short loc_180003E71
0x180003e4f  movzx   ecx, cx
0x180003e52  or      ecx, 0C0090000h
0x180003e58  jmp     short loc_180003E71
0x180003e5a  xor     ecx, ecx
0x180003e5c  jmp     short loc_180003E71
0x180003e5e  mov     ecx, 0C000A083h
0x180003e63  jmp     short loc_180003E71
0x180003e65  mov     ecx, 0C00000E5h
0x180003e6a  jmp     short loc_180003E71
0x180003e6c  mov     ecx, 0C000042Bh
0x180003e71  mov     eax, ecx
0x180003e73  retn
```
