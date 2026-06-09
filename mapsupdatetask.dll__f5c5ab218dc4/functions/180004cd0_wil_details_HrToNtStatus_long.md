# wil::details::HrToNtStatus(long)

- ea: `0x180004cd0`
- end: `0x180004e8c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000290c`
- `0x1800029ac`
- `0x1800029fc`
- `0x180002ab4`
- `0x1800042a8`
- `0x180004fe0`

## callees

- `0x180004cd0`

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
0x180004cd0  mov     eax, 800700EAh
0x180004cd5  cmp     ecx, eax
0x180004cd7  jg      loc_180004DAC
0x180004cdd  jz      loc_180004DA2
0x180004ce3  mov     eax, 80070057h
0x180004ce8  cmp     ecx, eax
0x180004cea  jg      short loc_180004D56
0x180004cec  jz      short loc_180004D4C
0x180004cee  cmp     ecx, 80004005h
0x180004cf4  jz      short loc_180004D42
0x180004cf6  cmp     ecx, 80070001h
0x180004cfc  jz      short loc_180004D38
0x180004cfe  cmp     ecx, 80070002h
0x180004d04  jz      short loc_180004D2E
0x180004d06  cmp     ecx, 80070003h
0x180004d0c  jz      short loc_180004D24
0x180004d0e  cmp     ecx, 8007000Eh
0x180004d14  jnz     loc_180004E31
0x180004d1a  mov     ecx, 0C0000017h
0x180004d1f  jmp     loc_180004E89
0x180004d24  mov     ecx, 0C000003Ah
0x180004d29  jmp     loc_180004E89
0x180004d2e  mov     ecx, 0C0000034h
0x180004d33  jmp     loc_180004E89
0x180004d38  mov     ecx, 0C0000002h
0x180004d3d  jmp     loc_180004E89
0x180004d42  mov     ecx, 0C0000001h
0x180004d47  jmp     loc_180004E89
0x180004d4c  mov     ecx, 0C000000Dh
0x180004d51  jmp     loc_180004E89
0x180004d56  cmp     ecx, 80070070h
0x180004d5c  jz      short loc_180004D98
0x180004d5e  cmp     ecx, 8007007Ah
0x180004d64  jz      short loc_180004D8E
0x180004d66  cmp     ecx, 8007007Bh
0x180004d6c  jz      short loc_180004D84
0x180004d6e  cmp     ecx, 8007007Eh
0x180004d74  jnz     loc_180004E31
0x180004d7a  mov     ecx, 0C0000135h
0x180004d7f  jmp     loc_180004E89
0x180004d84  mov     ecx, 0C0000033h
0x180004d89  jmp     loc_180004E89
0x180004d8e  mov     ecx, 0C0000023h
0x180004d93  jmp     loc_180004E89
0x180004d98  mov     ecx, 0C000007Fh
0x180004d9d  jmp     loc_180004E89
0x180004da2  mov     ecx, 80000005h
0x180004da7  jmp     loc_180004E89
0x180004dac  mov     eax, 8007047Eh
0x180004db1  cmp     ecx, eax
0x180004db3  jg      short loc_180004E15
0x180004db5  jz      short loc_180004E0E
0x180004db7  cmp     ecx, 80070216h
0x180004dbd  jz      short loc_180004E07
0x180004dbf  cmp     ecx, 8007023Eh
0x180004dc5  jz      short loc_180004DFD
0x180004dc7  cmp     ecx, 80070246h
0x180004dcd  jz      short loc_180004DF3
0x180004dcf  cmp     ecx, 80070247h
0x180004dd5  jz      short loc_180004DE9
0x180004dd7  cmp     ecx, 80070272h
0x180004ddd  jnz     short loc_180004E31
0x180004ddf  mov     ecx, 0C0000273h
0x180004de4  jmp     loc_180004E89
0x180004de9  mov     ecx, 0C0000163h
0x180004dee  jmp     loc_180004E89
0x180004df3  mov     ecx, 0C0000161h
0x180004df8  jmp     loc_180004E89
0x180004dfd  mov     ecx, 0C0000025h
0x180004e02  jmp     loc_180004E89
0x180004e07  mov     ecx, 0C0000095h
0x180004e0c  jmp     short loc_180004E89
0x180004e0e  mov     ecx, 0C0000059h
0x180004e13  jmp     short loc_180004E89
0x180004e15  cmp     ecx, 8007050Ch
0x180004e1b  jz      short loc_180004E84
0x180004e1d  cmp     ecx, 8007054Fh
0x180004e23  jz      short loc_180004E7D
0x180004e25  cmp     ecx, 800705B9h
0x180004e2b  jz      short loc_180004E76
0x180004e2d  test    ecx, ecx
0x180004e2f  jz      short loc_180004E72
0x180004e31  bt      ecx, 1Ch
0x180004e35  jnb     short loc_180004E3D
0x180004e37  btr     ecx, 1Ch
0x180004e3b  jmp     short loc_180004E89
0x180004e3d  mov     eax, ecx
0x180004e3f  and     eax, 1FFF0000h
0x180004e44  cmp     eax, 70000h
0x180004e49  jnz     short loc_180004E5C
0x180004e4b  movzx   ecx, cx
0x180004e4e  mov     eax, ecx
0x180004e50  or      eax, 0C0070000h
0x180004e55  test    ecx, ecx
0x180004e57  cmovnz  ecx, eax
0x180004e5a  jmp     short loc_180004E89
0x180004e5c  cmp     eax, 90000h
0x180004e61  jnz     short loc_180004E7D
0x180004e63  test    ecx, ecx
0x180004e65  jle     short loc_180004E89
0x180004e67  movzx   ecx, cx
0x180004e6a  or      ecx, 0C0090000h
0x180004e70  jmp     short loc_180004E89
0x180004e72  xor     ecx, ecx
0x180004e74  jmp     short loc_180004E89
0x180004e76  mov     ecx, 0C000A083h
0x180004e7b  jmp     short loc_180004E89
0x180004e7d  mov     ecx, 0C00000E5h
0x180004e82  jmp     short loc_180004E89
0x180004e84  mov     ecx, 0C000042Bh
0x180004e89  mov     eax, ecx
0x180004e8b  retn
```
