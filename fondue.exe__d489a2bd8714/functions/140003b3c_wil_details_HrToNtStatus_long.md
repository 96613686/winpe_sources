# wil::details::HrToNtStatus(long)

- ea: `0x140003b3c`
- end: `0x140003cf8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000218c`
- `0x14000222c`
- `0x14000227c`
- `0x140002334`
- `0x140003118`
- `0x140003d00`

## callees

- `0x140003b3c`

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
0x140003b3c  mov     eax, 800700EAh
0x140003b41  cmp     ecx, eax
0x140003b43  jg      loc_140003C18
0x140003b49  jz      loc_140003C0E
0x140003b4f  mov     eax, 80070057h
0x140003b54  cmp     ecx, eax
0x140003b56  jg      short loc_140003BC2
0x140003b58  jz      short loc_140003BB8
0x140003b5a  cmp     ecx, 80004005h
0x140003b60  jz      short loc_140003BAE
0x140003b62  cmp     ecx, 80070001h
0x140003b68  jz      short loc_140003BA4
0x140003b6a  cmp     ecx, 80070002h
0x140003b70  jz      short loc_140003B9A
0x140003b72  cmp     ecx, 80070003h
0x140003b78  jz      short loc_140003B90
0x140003b7a  cmp     ecx, 8007000Eh
0x140003b80  jnz     loc_140003C9D
0x140003b86  mov     ecx, 0C0000017h
0x140003b8b  jmp     loc_140003CF5
0x140003b90  mov     ecx, 0C000003Ah
0x140003b95  jmp     loc_140003CF5
0x140003b9a  mov     ecx, 0C0000034h
0x140003b9f  jmp     loc_140003CF5
0x140003ba4  mov     ecx, 0C0000002h
0x140003ba9  jmp     loc_140003CF5
0x140003bae  mov     ecx, 0C0000001h
0x140003bb3  jmp     loc_140003CF5
0x140003bb8  mov     ecx, 0C000000Dh
0x140003bbd  jmp     loc_140003CF5
0x140003bc2  cmp     ecx, 80070070h
0x140003bc8  jz      short loc_140003C04
0x140003bca  cmp     ecx, 8007007Ah
0x140003bd0  jz      short loc_140003BFA
0x140003bd2  cmp     ecx, 8007007Bh
0x140003bd8  jz      short loc_140003BF0
0x140003bda  cmp     ecx, 8007007Eh
0x140003be0  jnz     loc_140003C9D
0x140003be6  mov     ecx, 0C0000135h
0x140003beb  jmp     loc_140003CF5
0x140003bf0  mov     ecx, 0C0000033h
0x140003bf5  jmp     loc_140003CF5
0x140003bfa  mov     ecx, 0C0000023h
0x140003bff  jmp     loc_140003CF5
0x140003c04  mov     ecx, 0C000007Fh
0x140003c09  jmp     loc_140003CF5
0x140003c0e  mov     ecx, 80000005h
0x140003c13  jmp     loc_140003CF5
0x140003c18  mov     eax, 8007047Eh
0x140003c1d  cmp     ecx, eax
0x140003c1f  jg      short loc_140003C81
0x140003c21  jz      short loc_140003C7A
0x140003c23  cmp     ecx, 80070216h
0x140003c29  jz      short loc_140003C73
0x140003c2b  cmp     ecx, 8007023Eh
0x140003c31  jz      short loc_140003C69
0x140003c33  cmp     ecx, 80070246h
0x140003c39  jz      short loc_140003C5F
0x140003c3b  cmp     ecx, 80070247h
0x140003c41  jz      short loc_140003C55
0x140003c43  cmp     ecx, 80070272h
0x140003c49  jnz     short loc_140003C9D
0x140003c4b  mov     ecx, 0C0000273h
0x140003c50  jmp     loc_140003CF5
0x140003c55  mov     ecx, 0C0000163h
0x140003c5a  jmp     loc_140003CF5
0x140003c5f  mov     ecx, 0C0000161h
0x140003c64  jmp     loc_140003CF5
0x140003c69  mov     ecx, 0C0000025h
0x140003c6e  jmp     loc_140003CF5
0x140003c73  mov     ecx, 0C0000095h
0x140003c78  jmp     short loc_140003CF5
0x140003c7a  mov     ecx, 0C0000059h
0x140003c7f  jmp     short loc_140003CF5
0x140003c81  cmp     ecx, 8007050Ch
0x140003c87  jz      short loc_140003CF0
0x140003c89  cmp     ecx, 8007054Fh
0x140003c8f  jz      short loc_140003CE9
0x140003c91  cmp     ecx, 800705B9h
0x140003c97  jz      short loc_140003CE2
0x140003c99  test    ecx, ecx
0x140003c9b  jz      short loc_140003CDE
0x140003c9d  bt      ecx, 1Ch
0x140003ca1  jnb     short loc_140003CA9
0x140003ca3  btr     ecx, 1Ch
0x140003ca7  jmp     short loc_140003CF5
0x140003ca9  mov     eax, ecx
0x140003cab  and     eax, 1FFF0000h
0x140003cb0  cmp     eax, 70000h
0x140003cb5  jnz     short loc_140003CC8
0x140003cb7  movzx   ecx, cx
0x140003cba  mov     eax, ecx
0x140003cbc  or      eax, 0C0070000h
0x140003cc1  test    ecx, ecx
0x140003cc3  cmovnz  ecx, eax
0x140003cc6  jmp     short loc_140003CF5
0x140003cc8  cmp     eax, 90000h
0x140003ccd  jnz     short loc_140003CE9
0x140003ccf  test    ecx, ecx
0x140003cd1  jle     short loc_140003CF5
0x140003cd3  movzx   ecx, cx
0x140003cd6  or      ecx, 0C0090000h
0x140003cdc  jmp     short loc_140003CF5
0x140003cde  xor     ecx, ecx
0x140003ce0  jmp     short loc_140003CF5
0x140003ce2  mov     ecx, 0C000A083h
0x140003ce7  jmp     short loc_140003CF5
0x140003ce9  mov     ecx, 0C00000E5h
0x140003cee  jmp     short loc_140003CF5
0x140003cf0  mov     ecx, 0C000042Bh
0x140003cf5  mov     eax, ecx
0x140003cf7  retn
```
