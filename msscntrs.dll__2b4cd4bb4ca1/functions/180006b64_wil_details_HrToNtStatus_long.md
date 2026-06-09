# wil::details::HrToNtStatus(long)

- ea: `0x180006b64`
- end: `0x180006d20`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180003898`
- `0x180003948`
- `0x1800039a0`
- `0x180003a68`
- `0x180006138`
- `0x180006e10`
- `0x1800089a0`
- `0x180013ad8`
- `0x180013bf4`
- `0x1800159e9`
- `0x180015a54`
- `0x180015b1d`
- `0x180015b88`

## callees

- `0x180006b64`

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
0x180006b64  mov     eax, 800700EAh
0x180006b69  cmp     ecx, eax
0x180006b6b  jg      loc_180006C40
0x180006b71  jz      loc_180006C36
0x180006b77  mov     eax, 80070057h
0x180006b7c  cmp     ecx, eax
0x180006b7e  jg      short loc_180006BEA
0x180006b80  jz      short loc_180006BE0
0x180006b82  cmp     ecx, 80004005h
0x180006b88  jz      short loc_180006BD6
0x180006b8a  cmp     ecx, 80070001h
0x180006b90  jz      short loc_180006BCC
0x180006b92  cmp     ecx, 80070002h
0x180006b98  jz      short loc_180006BC2
0x180006b9a  cmp     ecx, 80070003h
0x180006ba0  jz      short loc_180006BB8
0x180006ba2  cmp     ecx, 8007000Eh
0x180006ba8  jnz     loc_180006CC5
0x180006bae  mov     ecx, 0C0000017h
0x180006bb3  jmp     loc_180006D1D
0x180006bb8  mov     ecx, 0C000003Ah
0x180006bbd  jmp     loc_180006D1D
0x180006bc2  mov     ecx, 0C0000034h
0x180006bc7  jmp     loc_180006D1D
0x180006bcc  mov     ecx, 0C0000002h
0x180006bd1  jmp     loc_180006D1D
0x180006bd6  mov     ecx, 0C0000001h
0x180006bdb  jmp     loc_180006D1D
0x180006be0  mov     ecx, 0C000000Dh
0x180006be5  jmp     loc_180006D1D
0x180006bea  cmp     ecx, 80070070h
0x180006bf0  jz      short loc_180006C2C
0x180006bf2  cmp     ecx, 8007007Ah
0x180006bf8  jz      short loc_180006C22
0x180006bfa  cmp     ecx, 8007007Bh
0x180006c00  jz      short loc_180006C18
0x180006c02  cmp     ecx, 8007007Eh
0x180006c08  jnz     loc_180006CC5
0x180006c0e  mov     ecx, 0C0000135h
0x180006c13  jmp     loc_180006D1D
0x180006c18  mov     ecx, 0C0000033h
0x180006c1d  jmp     loc_180006D1D
0x180006c22  mov     ecx, 0C0000023h
0x180006c27  jmp     loc_180006D1D
0x180006c2c  mov     ecx, 0C000007Fh
0x180006c31  jmp     loc_180006D1D
0x180006c36  mov     ecx, 80000005h
0x180006c3b  jmp     loc_180006D1D
0x180006c40  mov     eax, 8007047Eh
0x180006c45  cmp     ecx, eax
0x180006c47  jg      short loc_180006CA9
0x180006c49  jz      short loc_180006CA2
0x180006c4b  cmp     ecx, 80070216h
0x180006c51  jz      short loc_180006C9B
0x180006c53  cmp     ecx, 8007023Eh
0x180006c59  jz      short loc_180006C91
0x180006c5b  cmp     ecx, 80070246h
0x180006c61  jz      short loc_180006C87
0x180006c63  cmp     ecx, 80070247h
0x180006c69  jz      short loc_180006C7D
0x180006c6b  cmp     ecx, 80070272h
0x180006c71  jnz     short loc_180006CC5
0x180006c73  mov     ecx, 0C0000273h
0x180006c78  jmp     loc_180006D1D
0x180006c7d  mov     ecx, 0C0000163h
0x180006c82  jmp     loc_180006D1D
0x180006c87  mov     ecx, 0C0000161h
0x180006c8c  jmp     loc_180006D1D
0x180006c91  mov     ecx, 0C0000025h
0x180006c96  jmp     loc_180006D1D
0x180006c9b  mov     ecx, 0C0000095h
0x180006ca0  jmp     short loc_180006D1D
0x180006ca2  mov     ecx, 0C0000059h
0x180006ca7  jmp     short loc_180006D1D
0x180006ca9  cmp     ecx, 8007050Ch
0x180006caf  jz      short loc_180006D18
0x180006cb1  cmp     ecx, 8007054Fh
0x180006cb7  jz      short loc_180006D11
0x180006cb9  cmp     ecx, 800705B9h
0x180006cbf  jz      short loc_180006D0A
0x180006cc1  test    ecx, ecx
0x180006cc3  jz      short loc_180006D06
0x180006cc5  bt      ecx, 1Ch
0x180006cc9  jnb     short loc_180006CD1
0x180006ccb  btr     ecx, 1Ch
0x180006ccf  jmp     short loc_180006D1D
0x180006cd1  mov     eax, ecx
0x180006cd3  and     eax, 1FFF0000h
0x180006cd8  cmp     eax, 70000h
0x180006cdd  jnz     short loc_180006CF0
0x180006cdf  movzx   ecx, cx
0x180006ce2  mov     eax, ecx
0x180006ce4  or      eax, 0C0070000h
0x180006ce9  test    ecx, ecx
0x180006ceb  cmovnz  ecx, eax
0x180006cee  jmp     short loc_180006D1D
0x180006cf0  cmp     eax, 90000h
0x180006cf5  jnz     short loc_180006D11
0x180006cf7  test    ecx, ecx
0x180006cf9  jle     short loc_180006D1D
0x180006cfb  movzx   ecx, cx
0x180006cfe  or      ecx, 0C0090000h
0x180006d04  jmp     short loc_180006D1D
0x180006d06  xor     ecx, ecx
0x180006d08  jmp     short loc_180006D1D
0x180006d0a  mov     ecx, 0C000A083h
0x180006d0f  jmp     short loc_180006D1D
0x180006d11  mov     ecx, 0C00000E5h
0x180006d16  jmp     short loc_180006D1D
0x180006d18  mov     ecx, 0C000042Bh
0x180006d1d  mov     eax, ecx
0x180006d1f  retn
```
