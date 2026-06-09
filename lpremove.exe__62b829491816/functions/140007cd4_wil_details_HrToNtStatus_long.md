# wil::details::HrToNtStatus(long)

- ea: `0x140007cd4`
- end: `0x140007e90`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1400036d8`
- `0x14000381c`
- `0x140003a08`
- `0x140003ab8`
- `0x140003b10`
- `0x140003bd8`
- `0x1400070d8`
- `0x1400086ac`
- `0x14000a770`
- `0x14000e024`
- `0x14000e098`
- `0x14001012b`
- `0x140010196`
- `0x14001025f`
- `0x1400102ca`

## callees

- `0x140007cd4`

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
0x140007cd4  mov     eax, 800700EAh
0x140007cd9  cmp     ecx, eax
0x140007cdb  jg      loc_140007DB0
0x140007ce1  jz      loc_140007DA6
0x140007ce7  mov     eax, 80070057h
0x140007cec  cmp     ecx, eax
0x140007cee  jg      short loc_140007D5A
0x140007cf0  jz      short loc_140007D50
0x140007cf2  cmp     ecx, 80004005h
0x140007cf8  jz      short loc_140007D46
0x140007cfa  cmp     ecx, 80070001h
0x140007d00  jz      short loc_140007D3C
0x140007d02  cmp     ecx, 80070002h
0x140007d08  jz      short loc_140007D32
0x140007d0a  cmp     ecx, 80070003h
0x140007d10  jz      short loc_140007D28
0x140007d12  cmp     ecx, 8007000Eh
0x140007d18  jnz     loc_140007E35
0x140007d1e  mov     ecx, 0C0000017h
0x140007d23  jmp     loc_140007E8D
0x140007d28  mov     ecx, 0C000003Ah
0x140007d2d  jmp     loc_140007E8D
0x140007d32  mov     ecx, 0C0000034h
0x140007d37  jmp     loc_140007E8D
0x140007d3c  mov     ecx, 0C0000002h
0x140007d41  jmp     loc_140007E8D
0x140007d46  mov     ecx, 0C0000001h
0x140007d4b  jmp     loc_140007E8D
0x140007d50  mov     ecx, 0C000000Dh
0x140007d55  jmp     loc_140007E8D
0x140007d5a  cmp     ecx, 80070070h
0x140007d60  jz      short loc_140007D9C
0x140007d62  cmp     ecx, 8007007Ah
0x140007d68  jz      short loc_140007D92
0x140007d6a  cmp     ecx, 8007007Bh
0x140007d70  jz      short loc_140007D88
0x140007d72  cmp     ecx, 8007007Eh
0x140007d78  jnz     loc_140007E35
0x140007d7e  mov     ecx, 0C0000135h
0x140007d83  jmp     loc_140007E8D
0x140007d88  mov     ecx, 0C0000033h
0x140007d8d  jmp     loc_140007E8D
0x140007d92  mov     ecx, 0C0000023h
0x140007d97  jmp     loc_140007E8D
0x140007d9c  mov     ecx, 0C000007Fh
0x140007da1  jmp     loc_140007E8D
0x140007da6  mov     ecx, 80000005h
0x140007dab  jmp     loc_140007E8D
0x140007db0  mov     eax, 8007047Eh
0x140007db5  cmp     ecx, eax
0x140007db7  jg      short loc_140007E19
0x140007db9  jz      short loc_140007E12
0x140007dbb  cmp     ecx, 80070216h
0x140007dc1  jz      short loc_140007E0B
0x140007dc3  cmp     ecx, 8007023Eh
0x140007dc9  jz      short loc_140007E01
0x140007dcb  cmp     ecx, 80070246h
0x140007dd1  jz      short loc_140007DF7
0x140007dd3  cmp     ecx, 80070247h
0x140007dd9  jz      short loc_140007DED
0x140007ddb  cmp     ecx, 80070272h
0x140007de1  jnz     short loc_140007E35
0x140007de3  mov     ecx, 0C0000273h
0x140007de8  jmp     loc_140007E8D
0x140007ded  mov     ecx, 0C0000163h
0x140007df2  jmp     loc_140007E8D
0x140007df7  mov     ecx, 0C0000161h
0x140007dfc  jmp     loc_140007E8D
0x140007e01  mov     ecx, 0C0000025h
0x140007e06  jmp     loc_140007E8D
0x140007e0b  mov     ecx, 0C0000095h
0x140007e10  jmp     short loc_140007E8D
0x140007e12  mov     ecx, 0C0000059h
0x140007e17  jmp     short loc_140007E8D
0x140007e19  cmp     ecx, 8007050Ch
0x140007e1f  jz      short loc_140007E88
0x140007e21  cmp     ecx, 8007054Fh
0x140007e27  jz      short loc_140007E81
0x140007e29  cmp     ecx, 800705B9h
0x140007e2f  jz      short loc_140007E7A
0x140007e31  test    ecx, ecx
0x140007e33  jz      short loc_140007E76
0x140007e35  bt      ecx, 1Ch
0x140007e39  jnb     short loc_140007E41
0x140007e3b  btr     ecx, 1Ch
0x140007e3f  jmp     short loc_140007E8D
0x140007e41  mov     eax, ecx
0x140007e43  and     eax, 1FFF0000h
0x140007e48  cmp     eax, 70000h
0x140007e4d  jnz     short loc_140007E60
0x140007e4f  movzx   ecx, cx
0x140007e52  mov     eax, ecx
0x140007e54  or      eax, 0C0070000h
0x140007e59  test    ecx, ecx
0x140007e5b  cmovnz  ecx, eax
0x140007e5e  jmp     short loc_140007E8D
0x140007e60  cmp     eax, 90000h
0x140007e65  jnz     short loc_140007E81
0x140007e67  test    ecx, ecx
0x140007e69  jle     short loc_140007E8D
0x140007e6b  movzx   ecx, cx
0x140007e6e  or      ecx, 0C0090000h
0x140007e74  jmp     short loc_140007E8D
0x140007e76  xor     ecx, ecx
0x140007e78  jmp     short loc_140007E8D
0x140007e7a  mov     ecx, 0C000A083h
0x140007e7f  jmp     short loc_140007E8D
0x140007e81  mov     ecx, 0C00000E5h
0x140007e86  jmp     short loc_140007E8D
0x140007e88  mov     ecx, 0C000042Bh
0x140007e8d  mov     eax, ecx
0x140007e8f  retn
```
