# wil::details::HrToNtStatus(long)

- ea: `0x180004c08`
- end: `0x180004dc4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031dc`
- `0x18000325c`
- `0x1800032e4`
- `0x18000333c`
- `0x180004208`
- `0x180004dfc`
- `0x1800056d0`
- `0x18000d71c`
- `0x180014490`
- `0x180018f4a`
- `0x180018f95`
- `0x180019058`
- `0x1800190a3`

## callees

- `0x180004c08`

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
0x180004c08  mov     eax, 800700EAh
0x180004c0d  cmp     ecx, eax
0x180004c0f  jg      loc_180004CE4
0x180004c15  jz      loc_180004CDA
0x180004c1b  mov     eax, 80070057h
0x180004c20  cmp     ecx, eax
0x180004c22  jg      short loc_180004C8E
0x180004c24  jz      short loc_180004C84
0x180004c26  cmp     ecx, 80004005h
0x180004c2c  jz      short loc_180004C7A
0x180004c2e  cmp     ecx, 80070001h
0x180004c34  jz      short loc_180004C70
0x180004c36  cmp     ecx, 80070002h
0x180004c3c  jz      short loc_180004C66
0x180004c3e  cmp     ecx, 80070003h
0x180004c44  jz      short loc_180004C5C
0x180004c46  cmp     ecx, 8007000Eh
0x180004c4c  jnz     loc_180004D69
0x180004c52  mov     ecx, 0C0000017h
0x180004c57  jmp     loc_180004DC1
0x180004c5c  mov     ecx, 0C000003Ah
0x180004c61  jmp     loc_180004DC1
0x180004c66  mov     ecx, 0C0000034h
0x180004c6b  jmp     loc_180004DC1
0x180004c70  mov     ecx, 0C0000002h
0x180004c75  jmp     loc_180004DC1
0x180004c7a  mov     ecx, 0C0000001h
0x180004c7f  jmp     loc_180004DC1
0x180004c84  mov     ecx, 0C000000Dh
0x180004c89  jmp     loc_180004DC1
0x180004c8e  cmp     ecx, 80070070h
0x180004c94  jz      short loc_180004CD0
0x180004c96  cmp     ecx, 8007007Ah
0x180004c9c  jz      short loc_180004CC6
0x180004c9e  cmp     ecx, 8007007Bh
0x180004ca4  jz      short loc_180004CBC
0x180004ca6  cmp     ecx, 8007007Eh
0x180004cac  jnz     loc_180004D69
0x180004cb2  mov     ecx, 0C0000135h
0x180004cb7  jmp     loc_180004DC1
0x180004cbc  mov     ecx, 0C0000033h
0x180004cc1  jmp     loc_180004DC1
0x180004cc6  mov     ecx, 0C0000023h
0x180004ccb  jmp     loc_180004DC1
0x180004cd0  mov     ecx, 0C000007Fh
0x180004cd5  jmp     loc_180004DC1
0x180004cda  mov     ecx, 80000005h
0x180004cdf  jmp     loc_180004DC1
0x180004ce4  mov     eax, 8007047Eh
0x180004ce9  cmp     ecx, eax
0x180004ceb  jg      short loc_180004D4D
0x180004ced  jz      short loc_180004D46
0x180004cef  cmp     ecx, 80070216h
0x180004cf5  jz      short loc_180004D3F
0x180004cf7  cmp     ecx, 8007023Eh
0x180004cfd  jz      short loc_180004D35
0x180004cff  cmp     ecx, 80070246h
0x180004d05  jz      short loc_180004D2B
0x180004d07  cmp     ecx, 80070247h
0x180004d0d  jz      short loc_180004D21
0x180004d0f  cmp     ecx, 80070272h
0x180004d15  jnz     short loc_180004D69
0x180004d17  mov     ecx, 0C0000273h
0x180004d1c  jmp     loc_180004DC1
0x180004d21  mov     ecx, 0C0000163h
0x180004d26  jmp     loc_180004DC1
0x180004d2b  mov     ecx, 0C0000161h
0x180004d30  jmp     loc_180004DC1
0x180004d35  mov     ecx, 0C0000025h
0x180004d3a  jmp     loc_180004DC1
0x180004d3f  mov     ecx, 0C0000095h
0x180004d44  jmp     short loc_180004DC1
0x180004d46  mov     ecx, 0C0000059h
0x180004d4b  jmp     short loc_180004DC1
0x180004d4d  cmp     ecx, 8007050Ch
0x180004d53  jz      short loc_180004DBC
0x180004d55  cmp     ecx, 8007054Fh
0x180004d5b  jz      short loc_180004DB5
0x180004d5d  cmp     ecx, 800705B9h
0x180004d63  jz      short loc_180004DAE
0x180004d65  test    ecx, ecx
0x180004d67  jz      short loc_180004DAA
0x180004d69  bt      ecx, 1Ch
0x180004d6d  jnb     short loc_180004D75
0x180004d6f  btr     ecx, 1Ch
0x180004d73  jmp     short loc_180004DC1
0x180004d75  mov     eax, ecx
0x180004d77  and     eax, 1FFF0000h
0x180004d7c  cmp     eax, 70000h
0x180004d81  jnz     short loc_180004D94
0x180004d83  movzx   ecx, cx
0x180004d86  mov     eax, ecx
0x180004d88  or      eax, 0C0070000h
0x180004d8d  test    ecx, ecx
0x180004d8f  cmovnz  ecx, eax
0x180004d92  jmp     short loc_180004DC1
0x180004d94  cmp     eax, 90000h
0x180004d99  jnz     short loc_180004DB5
0x180004d9b  test    ecx, ecx
0x180004d9d  jle     short loc_180004DC1
0x180004d9f  movzx   ecx, cx
0x180004da2  or      ecx, 0C0090000h
0x180004da8  jmp     short loc_180004DC1
0x180004daa  xor     ecx, ecx
0x180004dac  jmp     short loc_180004DC1
0x180004dae  mov     ecx, 0C000A083h
0x180004db3  jmp     short loc_180004DC1
0x180004db5  mov     ecx, 0C00000E5h
0x180004dba  jmp     short loc_180004DC1
0x180004dbc  mov     ecx, 0C000042Bh
0x180004dc1  mov     eax, ecx
0x180004dc3  retn
```
