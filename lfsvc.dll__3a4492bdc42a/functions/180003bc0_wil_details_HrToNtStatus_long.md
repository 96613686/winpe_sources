# wil::details::HrToNtStatus(long)

- ea: `0x180003bc0`
- end: `0x180003d7c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b1c`
- `0x180004fb0`
- `0x18000503c`
- `0x180005098`
- `0x180005164`
- `0x180006ba8`
- `0x180007688`

## callees

- `0x180003bc0`

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
0x180003bc0  mov     eax, 800700EAh
0x180003bc5  cmp     ecx, eax
0x180003bc7  jg      loc_180003C9C
0x180003bcd  jz      loc_180003C92
0x180003bd3  mov     eax, 80070057h
0x180003bd8  cmp     ecx, eax
0x180003bda  jg      short loc_180003C46
0x180003bdc  jz      short loc_180003C3C
0x180003bde  cmp     ecx, 80004005h
0x180003be4  jz      short loc_180003C32
0x180003be6  cmp     ecx, 80070001h
0x180003bec  jz      short loc_180003C28
0x180003bee  cmp     ecx, 80070002h
0x180003bf4  jz      short loc_180003C1E
0x180003bf6  cmp     ecx, 80070003h
0x180003bfc  jz      short loc_180003C14
0x180003bfe  cmp     ecx, 8007000Eh
0x180003c04  jnz     loc_180003D21
0x180003c0a  mov     ecx, 0C0000017h
0x180003c0f  jmp     loc_180003D79
0x180003c14  mov     ecx, 0C000003Ah
0x180003c19  jmp     loc_180003D79
0x180003c1e  mov     ecx, 0C0000034h
0x180003c23  jmp     loc_180003D79
0x180003c28  mov     ecx, 0C0000002h
0x180003c2d  jmp     loc_180003D79
0x180003c32  mov     ecx, 0C0000001h
0x180003c37  jmp     loc_180003D79
0x180003c3c  mov     ecx, 0C000000Dh
0x180003c41  jmp     loc_180003D79
0x180003c46  cmp     ecx, 80070070h
0x180003c4c  jz      short loc_180003C88
0x180003c4e  cmp     ecx, 8007007Ah
0x180003c54  jz      short loc_180003C7E
0x180003c56  cmp     ecx, 8007007Bh
0x180003c5c  jz      short loc_180003C74
0x180003c5e  cmp     ecx, 8007007Eh
0x180003c64  jnz     loc_180003D21
0x180003c6a  mov     ecx, 0C0000135h
0x180003c6f  jmp     loc_180003D79
0x180003c74  mov     ecx, 0C0000033h
0x180003c79  jmp     loc_180003D79
0x180003c7e  mov     ecx, 0C0000023h
0x180003c83  jmp     loc_180003D79
0x180003c88  mov     ecx, 0C000007Fh
0x180003c8d  jmp     loc_180003D79
0x180003c92  mov     ecx, 80000005h
0x180003c97  jmp     loc_180003D79
0x180003c9c  mov     eax, 8007047Eh
0x180003ca1  cmp     ecx, eax
0x180003ca3  jg      short loc_180003D05
0x180003ca5  jz      short loc_180003CFE
0x180003ca7  cmp     ecx, 80070216h
0x180003cad  jz      short loc_180003CF7
0x180003caf  cmp     ecx, 8007023Eh
0x180003cb5  jz      short loc_180003CED
0x180003cb7  cmp     ecx, 80070246h
0x180003cbd  jz      short loc_180003CE3
0x180003cbf  cmp     ecx, 80070247h
0x180003cc5  jz      short loc_180003CD9
0x180003cc7  cmp     ecx, 80070272h
0x180003ccd  jnz     short loc_180003D21
0x180003ccf  mov     ecx, 0C0000273h
0x180003cd4  jmp     loc_180003D79
0x180003cd9  mov     ecx, 0C0000163h
0x180003cde  jmp     loc_180003D79
0x180003ce3  mov     ecx, 0C0000161h
0x180003ce8  jmp     loc_180003D79
0x180003ced  mov     ecx, 0C0000025h
0x180003cf2  jmp     loc_180003D79
0x180003cf7  mov     ecx, 0C0000095h
0x180003cfc  jmp     short loc_180003D79
0x180003cfe  mov     ecx, 0C0000059h
0x180003d03  jmp     short loc_180003D79
0x180003d05  cmp     ecx, 8007050Ch
0x180003d0b  jz      short loc_180003D74
0x180003d0d  cmp     ecx, 8007054Fh
0x180003d13  jz      short loc_180003D6D
0x180003d15  cmp     ecx, 800705B9h
0x180003d1b  jz      short loc_180003D66
0x180003d1d  test    ecx, ecx
0x180003d1f  jz      short loc_180003D62
0x180003d21  bt      ecx, 1Ch
0x180003d25  jnb     short loc_180003D2D
0x180003d27  btr     ecx, 1Ch
0x180003d2b  jmp     short loc_180003D79
0x180003d2d  mov     eax, ecx
0x180003d2f  and     eax, 1FFF0000h
0x180003d34  cmp     eax, 70000h
0x180003d39  jnz     short loc_180003D4C
0x180003d3b  movzx   ecx, cx
0x180003d3e  mov     eax, ecx
0x180003d40  or      eax, 0C0070000h
0x180003d45  test    ecx, ecx
0x180003d47  cmovnz  ecx, eax
0x180003d4a  jmp     short loc_180003D79
0x180003d4c  cmp     eax, 90000h
0x180003d51  jnz     short loc_180003D6D
0x180003d53  test    ecx, ecx
0x180003d55  jle     short loc_180003D79
0x180003d57  movzx   ecx, cx
0x180003d5a  or      ecx, 0C0090000h
0x180003d60  jmp     short loc_180003D79
0x180003d62  xor     ecx, ecx
0x180003d64  jmp     short loc_180003D79
0x180003d66  mov     ecx, 0C000A083h
0x180003d6b  jmp     short loc_180003D79
0x180003d6d  mov     ecx, 0C00000E5h
0x180003d72  jmp     short loc_180003D79
0x180003d74  mov     ecx, 0C000042Bh
0x180003d79  mov     eax, ecx
0x180003d7b  retn
```
