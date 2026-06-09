# wil::details::HrToNtStatus(long)

- ea: `0x140014d0c`
- end: `0x140014ec8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400124b0`
- `0x140012550`
- `0x1400125a0`
- `0x140012660`
- `0x1400142e8`
- `0x140014ed0`

## callees

- `0x140014d0c`

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
0x140014d0c  mov     eax, 800700EAh
0x140014d11  cmp     ecx, eax
0x140014d13  jg      loc_140014DE8
0x140014d19  jz      loc_140014DDE
0x140014d1f  mov     eax, 80070057h
0x140014d24  cmp     ecx, eax
0x140014d26  jg      short loc_140014D92
0x140014d28  jz      short loc_140014D88
0x140014d2a  cmp     ecx, 80004005h
0x140014d30  jz      short loc_140014D7E
0x140014d32  cmp     ecx, 80070001h
0x140014d38  jz      short loc_140014D74
0x140014d3a  cmp     ecx, 80070002h
0x140014d40  jz      short loc_140014D6A
0x140014d42  cmp     ecx, 80070003h
0x140014d48  jz      short loc_140014D60
0x140014d4a  cmp     ecx, 8007000Eh
0x140014d50  jnz     loc_140014E6D
0x140014d56  mov     ecx, 0C0000017h
0x140014d5b  jmp     loc_140014EC5
0x140014d60  mov     ecx, 0C000003Ah
0x140014d65  jmp     loc_140014EC5
0x140014d6a  mov     ecx, 0C0000034h
0x140014d6f  jmp     loc_140014EC5
0x140014d74  mov     ecx, 0C0000002h
0x140014d79  jmp     loc_140014EC5
0x140014d7e  mov     ecx, 0C0000001h
0x140014d83  jmp     loc_140014EC5
0x140014d88  mov     ecx, 0C000000Dh
0x140014d8d  jmp     loc_140014EC5
0x140014d92  cmp     ecx, 80070070h
0x140014d98  jz      short loc_140014DD4
0x140014d9a  cmp     ecx, 8007007Ah
0x140014da0  jz      short loc_140014DCA
0x140014da2  cmp     ecx, 8007007Bh
0x140014da8  jz      short loc_140014DC0
0x140014daa  cmp     ecx, 8007007Eh
0x140014db0  jnz     loc_140014E6D
0x140014db6  mov     ecx, 0C0000135h
0x140014dbb  jmp     loc_140014EC5
0x140014dc0  mov     ecx, 0C0000033h
0x140014dc5  jmp     loc_140014EC5
0x140014dca  mov     ecx, 0C0000023h
0x140014dcf  jmp     loc_140014EC5
0x140014dd4  mov     ecx, 0C000007Fh
0x140014dd9  jmp     loc_140014EC5
0x140014dde  mov     ecx, 80000005h
0x140014de3  jmp     loc_140014EC5
0x140014de8  mov     eax, 8007047Eh
0x140014ded  cmp     ecx, eax
0x140014def  jg      short loc_140014E51
0x140014df1  jz      short loc_140014E4A
0x140014df3  cmp     ecx, 80070216h
0x140014df9  jz      short loc_140014E43
0x140014dfb  cmp     ecx, 8007023Eh
0x140014e01  jz      short loc_140014E39
0x140014e03  cmp     ecx, 80070246h
0x140014e09  jz      short loc_140014E2F
0x140014e0b  cmp     ecx, 80070247h
0x140014e11  jz      short loc_140014E25
0x140014e13  cmp     ecx, 80070272h
0x140014e19  jnz     short loc_140014E6D
0x140014e1b  mov     ecx, 0C0000273h
0x140014e20  jmp     loc_140014EC5
0x140014e25  mov     ecx, 0C0000163h
0x140014e2a  jmp     loc_140014EC5
0x140014e2f  mov     ecx, 0C0000161h
0x140014e34  jmp     loc_140014EC5
0x140014e39  mov     ecx, 0C0000025h
0x140014e3e  jmp     loc_140014EC5
0x140014e43  mov     ecx, 0C0000095h
0x140014e48  jmp     short loc_140014EC5
0x140014e4a  mov     ecx, 0C0000059h
0x140014e4f  jmp     short loc_140014EC5
0x140014e51  cmp     ecx, 8007050Ch
0x140014e57  jz      short loc_140014EC0
0x140014e59  cmp     ecx, 8007054Fh
0x140014e5f  jz      short loc_140014EB9
0x140014e61  cmp     ecx, 800705B9h
0x140014e67  jz      short loc_140014EB2
0x140014e69  test    ecx, ecx
0x140014e6b  jz      short loc_140014EAE
0x140014e6d  bt      ecx, 1Ch
0x140014e71  jnb     short loc_140014E79
0x140014e73  btr     ecx, 1Ch
0x140014e77  jmp     short loc_140014EC5
0x140014e79  mov     eax, ecx
0x140014e7b  and     eax, 1FFF0000h
0x140014e80  cmp     eax, 70000h
0x140014e85  jnz     short loc_140014E98
0x140014e87  movzx   ecx, cx
0x140014e8a  mov     eax, ecx
0x140014e8c  or      eax, 0C0070000h
0x140014e91  test    ecx, ecx
0x140014e93  cmovnz  ecx, eax
0x140014e96  jmp     short loc_140014EC5
0x140014e98  cmp     eax, 90000h
0x140014e9d  jnz     short loc_140014EB9
0x140014e9f  test    ecx, ecx
0x140014ea1  jle     short loc_140014EC5
0x140014ea3  movzx   ecx, cx
0x140014ea6  or      ecx, 0C0090000h
0x140014eac  jmp     short loc_140014EC5
0x140014eae  xor     ecx, ecx
0x140014eb0  jmp     short loc_140014EC5
0x140014eb2  mov     ecx, 0C000A083h
0x140014eb7  jmp     short loc_140014EC5
0x140014eb9  mov     ecx, 0C00000E5h
0x140014ebe  jmp     short loc_140014EC5
0x140014ec0  mov     ecx, 0C000042Bh
0x140014ec5  mov     eax, ecx
0x140014ec7  retn
```
