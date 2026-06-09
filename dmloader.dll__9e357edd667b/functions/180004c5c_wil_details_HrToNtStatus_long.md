# wil::details::HrToNtStatus(long)

- ea: `0x180004c5c`
- end: `0x180004e18`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021e0`
- `0x180002280`
- `0x1800022d0`
- `0x180002390`
- `0x180004238`
- `0x180004e40`

## callees

- `0x180004c5c`

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
0x180004c5c  mov     eax, 800700EAh
0x180004c61  cmp     ecx, eax
0x180004c63  jg      loc_180004D38
0x180004c69  jz      loc_180004D2E
0x180004c6f  mov     eax, 80070057h
0x180004c74  cmp     ecx, eax
0x180004c76  jg      short loc_180004CE2
0x180004c78  jz      short loc_180004CD8
0x180004c7a  cmp     ecx, 80004005h
0x180004c80  jz      short loc_180004CCE
0x180004c82  cmp     ecx, 80070001h
0x180004c88  jz      short loc_180004CC4
0x180004c8a  cmp     ecx, 80070002h
0x180004c90  jz      short loc_180004CBA
0x180004c92  cmp     ecx, 80070003h
0x180004c98  jz      short loc_180004CB0
0x180004c9a  cmp     ecx, 8007000Eh
0x180004ca0  jnz     loc_180004DBD
0x180004ca6  mov     ecx, 0C0000017h
0x180004cab  jmp     loc_180004E15
0x180004cb0  mov     ecx, 0C000003Ah
0x180004cb5  jmp     loc_180004E15
0x180004cba  mov     ecx, 0C0000034h
0x180004cbf  jmp     loc_180004E15
0x180004cc4  mov     ecx, 0C0000002h
0x180004cc9  jmp     loc_180004E15
0x180004cce  mov     ecx, 0C0000001h
0x180004cd3  jmp     loc_180004E15
0x180004cd8  mov     ecx, 0C000000Dh
0x180004cdd  jmp     loc_180004E15
0x180004ce2  cmp     ecx, 80070070h
0x180004ce8  jz      short loc_180004D24
0x180004cea  cmp     ecx, 8007007Ah
0x180004cf0  jz      short loc_180004D1A
0x180004cf2  cmp     ecx, 8007007Bh
0x180004cf8  jz      short loc_180004D10
0x180004cfa  cmp     ecx, 8007007Eh
0x180004d00  jnz     loc_180004DBD
0x180004d06  mov     ecx, 0C0000135h
0x180004d0b  jmp     loc_180004E15
0x180004d10  mov     ecx, 0C0000033h
0x180004d15  jmp     loc_180004E15
0x180004d1a  mov     ecx, 0C0000023h
0x180004d1f  jmp     loc_180004E15
0x180004d24  mov     ecx, 0C000007Fh
0x180004d29  jmp     loc_180004E15
0x180004d2e  mov     ecx, 80000005h
0x180004d33  jmp     loc_180004E15
0x180004d38  mov     eax, 8007047Eh
0x180004d3d  cmp     ecx, eax
0x180004d3f  jg      short loc_180004DA1
0x180004d41  jz      short loc_180004D9A
0x180004d43  cmp     ecx, 80070216h
0x180004d49  jz      short loc_180004D93
0x180004d4b  cmp     ecx, 8007023Eh
0x180004d51  jz      short loc_180004D89
0x180004d53  cmp     ecx, 80070246h
0x180004d59  jz      short loc_180004D7F
0x180004d5b  cmp     ecx, 80070247h
0x180004d61  jz      short loc_180004D75
0x180004d63  cmp     ecx, 80070272h
0x180004d69  jnz     short loc_180004DBD
0x180004d6b  mov     ecx, 0C0000273h
0x180004d70  jmp     loc_180004E15
0x180004d75  mov     ecx, 0C0000163h
0x180004d7a  jmp     loc_180004E15
0x180004d7f  mov     ecx, 0C0000161h
0x180004d84  jmp     loc_180004E15
0x180004d89  mov     ecx, 0C0000025h
0x180004d8e  jmp     loc_180004E15
0x180004d93  mov     ecx, 0C0000095h
0x180004d98  jmp     short loc_180004E15
0x180004d9a  mov     ecx, 0C0000059h
0x180004d9f  jmp     short loc_180004E15
0x180004da1  cmp     ecx, 8007050Ch
0x180004da7  jz      short loc_180004E10
0x180004da9  cmp     ecx, 8007054Fh
0x180004daf  jz      short loc_180004E09
0x180004db1  cmp     ecx, 800705B9h
0x180004db7  jz      short loc_180004E02
0x180004db9  test    ecx, ecx
0x180004dbb  jz      short loc_180004DFE
0x180004dbd  bt      ecx, 1Ch
0x180004dc1  jnb     short loc_180004DC9
0x180004dc3  btr     ecx, 1Ch
0x180004dc7  jmp     short loc_180004E15
0x180004dc9  mov     eax, ecx
0x180004dcb  and     eax, 1FFF0000h
0x180004dd0  cmp     eax, 70000h
0x180004dd5  jnz     short loc_180004DE8
0x180004dd7  movzx   ecx, cx
0x180004dda  mov     eax, ecx
0x180004ddc  or      eax, 0C0070000h
0x180004de1  test    ecx, ecx
0x180004de3  cmovnz  ecx, eax
0x180004de6  jmp     short loc_180004E15
0x180004de8  cmp     eax, 90000h
0x180004ded  jnz     short loc_180004E09
0x180004def  test    ecx, ecx
0x180004df1  jle     short loc_180004E15
0x180004df3  movzx   ecx, cx
0x180004df6  or      ecx, 0C0090000h
0x180004dfc  jmp     short loc_180004E15
0x180004dfe  xor     ecx, ecx
0x180004e00  jmp     short loc_180004E15
0x180004e02  mov     ecx, 0C000A083h
0x180004e07  jmp     short loc_180004E15
0x180004e09  mov     ecx, 0C00000E5h
0x180004e0e  jmp     short loc_180004E15
0x180004e10  mov     ecx, 0C000042Bh
0x180004e15  mov     eax, ecx
0x180004e17  retn
```
