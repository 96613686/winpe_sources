# wil::details::HrToNtStatus(long)

- ea: `0x180004b64`
- end: `0x180004d20`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002330`
- `0x1800023d8`
- `0x180002428`
- `0x1800024e0`
- `0x180004088`
- `0x180004d90`

## callees

- `0x180004b64`

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
0x180004b64  mov     eax, 800700EAh
0x180004b69  cmp     ecx, eax
0x180004b6b  jg      loc_180004C40
0x180004b71  jz      loc_180004C36
0x180004b77  mov     eax, 80070057h
0x180004b7c  cmp     ecx, eax
0x180004b7e  jg      short loc_180004BEA
0x180004b80  jz      short loc_180004BE0
0x180004b82  cmp     ecx, 80004005h
0x180004b88  jz      short loc_180004BD6
0x180004b8a  cmp     ecx, 80070001h
0x180004b90  jz      short loc_180004BCC
0x180004b92  cmp     ecx, 80070002h
0x180004b98  jz      short loc_180004BC2
0x180004b9a  cmp     ecx, 80070003h
0x180004ba0  jz      short loc_180004BB8
0x180004ba2  cmp     ecx, 8007000Eh
0x180004ba8  jnz     loc_180004CC5
0x180004bae  mov     ecx, 0C0000017h
0x180004bb3  jmp     loc_180004D1D
0x180004bb8  mov     ecx, 0C000003Ah
0x180004bbd  jmp     loc_180004D1D
0x180004bc2  mov     ecx, 0C0000034h
0x180004bc7  jmp     loc_180004D1D
0x180004bcc  mov     ecx, 0C0000002h
0x180004bd1  jmp     loc_180004D1D
0x180004bd6  mov     ecx, 0C0000001h
0x180004bdb  jmp     loc_180004D1D
0x180004be0  mov     ecx, 0C000000Dh
0x180004be5  jmp     loc_180004D1D
0x180004bea  cmp     ecx, 80070070h
0x180004bf0  jz      short loc_180004C2C
0x180004bf2  cmp     ecx, 8007007Ah
0x180004bf8  jz      short loc_180004C22
0x180004bfa  cmp     ecx, 8007007Bh
0x180004c00  jz      short loc_180004C18
0x180004c02  cmp     ecx, 8007007Eh
0x180004c08  jnz     loc_180004CC5
0x180004c0e  mov     ecx, 0C0000135h
0x180004c13  jmp     loc_180004D1D
0x180004c18  mov     ecx, 0C0000033h
0x180004c1d  jmp     loc_180004D1D
0x180004c22  mov     ecx, 0C0000023h
0x180004c27  jmp     loc_180004D1D
0x180004c2c  mov     ecx, 0C000007Fh
0x180004c31  jmp     loc_180004D1D
0x180004c36  mov     ecx, 80000005h
0x180004c3b  jmp     loc_180004D1D
0x180004c40  mov     eax, 8007047Eh
0x180004c45  cmp     ecx, eax
0x180004c47  jg      short loc_180004CA9
0x180004c49  jz      short loc_180004CA2
0x180004c4b  cmp     ecx, 80070216h
0x180004c51  jz      short loc_180004C9B
0x180004c53  cmp     ecx, 8007023Eh
0x180004c59  jz      short loc_180004C91
0x180004c5b  cmp     ecx, 80070246h
0x180004c61  jz      short loc_180004C87
0x180004c63  cmp     ecx, 80070247h
0x180004c69  jz      short loc_180004C7D
0x180004c6b  cmp     ecx, 80070272h
0x180004c71  jnz     short loc_180004CC5
0x180004c73  mov     ecx, 0C0000273h
0x180004c78  jmp     loc_180004D1D
0x180004c7d  mov     ecx, 0C0000163h
0x180004c82  jmp     loc_180004D1D
0x180004c87  mov     ecx, 0C0000161h
0x180004c8c  jmp     loc_180004D1D
0x180004c91  mov     ecx, 0C0000025h
0x180004c96  jmp     loc_180004D1D
0x180004c9b  mov     ecx, 0C0000095h
0x180004ca0  jmp     short loc_180004D1D
0x180004ca2  mov     ecx, 0C0000059h
0x180004ca7  jmp     short loc_180004D1D
0x180004ca9  cmp     ecx, 8007050Ch
0x180004caf  jz      short loc_180004D18
0x180004cb1  cmp     ecx, 8007054Fh
0x180004cb7  jz      short loc_180004D11
0x180004cb9  cmp     ecx, 800705B9h
0x180004cbf  jz      short loc_180004D0A
0x180004cc1  test    ecx, ecx
0x180004cc3  jz      short loc_180004D06
0x180004cc5  bt      ecx, 1Ch
0x180004cc9  jnb     short loc_180004CD1
0x180004ccb  btr     ecx, 1Ch
0x180004ccf  jmp     short loc_180004D1D
0x180004cd1  mov     eax, ecx
0x180004cd3  and     eax, 1FFF0000h
0x180004cd8  cmp     eax, 70000h
0x180004cdd  jnz     short loc_180004CF0
0x180004cdf  movzx   ecx, cx
0x180004ce2  mov     eax, ecx
0x180004ce4  or      eax, 0C0070000h
0x180004ce9  test    ecx, ecx
0x180004ceb  cmovnz  ecx, eax
0x180004cee  jmp     short loc_180004D1D
0x180004cf0  cmp     eax, 90000h
0x180004cf5  jnz     short loc_180004D11
0x180004cf7  test    ecx, ecx
0x180004cf9  jle     short loc_180004D1D
0x180004cfb  movzx   ecx, cx
0x180004cfe  or      ecx, 0C0090000h
0x180004d04  jmp     short loc_180004D1D
0x180004d06  xor     ecx, ecx
0x180004d08  jmp     short loc_180004D1D
0x180004d0a  mov     ecx, 0C000A083h
0x180004d0f  jmp     short loc_180004D1D
0x180004d11  mov     ecx, 0C00000E5h
0x180004d16  jmp     short loc_180004D1D
0x180004d18  mov     ecx, 0C000042Bh
0x180004d1d  mov     eax, ecx
0x180004d1f  retn
```
