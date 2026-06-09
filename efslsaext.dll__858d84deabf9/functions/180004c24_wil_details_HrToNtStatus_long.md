# wil::details::HrToNtStatus(long)

- ea: `0x180004c24`
- end: `0x180004de0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003124`
- `0x1800031c4`
- `0x180003214`
- `0x1800032d4`
- `0x180004358`
- `0x180004dfc`
- `0x180008a1c`

## callees

- `0x180004c24`

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
0x180004c24  mov     eax, 800700EAh
0x180004c29  cmp     ecx, eax
0x180004c2b  jg      loc_180004D00
0x180004c31  jz      loc_180004CF6
0x180004c37  mov     eax, 80070057h
0x180004c3c  cmp     ecx, eax
0x180004c3e  jg      short loc_180004CAA
0x180004c40  jz      short loc_180004CA0
0x180004c42  cmp     ecx, 80004005h
0x180004c48  jz      short loc_180004C96
0x180004c4a  cmp     ecx, 80070001h
0x180004c50  jz      short loc_180004C8C
0x180004c52  cmp     ecx, 80070002h
0x180004c58  jz      short loc_180004C82
0x180004c5a  cmp     ecx, 80070003h
0x180004c60  jz      short loc_180004C78
0x180004c62  cmp     ecx, 8007000Eh
0x180004c68  jnz     loc_180004D85
0x180004c6e  mov     ecx, 0C0000017h
0x180004c73  jmp     loc_180004DDD
0x180004c78  mov     ecx, 0C000003Ah
0x180004c7d  jmp     loc_180004DDD
0x180004c82  mov     ecx, 0C0000034h
0x180004c87  jmp     loc_180004DDD
0x180004c8c  mov     ecx, 0C0000002h
0x180004c91  jmp     loc_180004DDD
0x180004c96  mov     ecx, 0C0000001h
0x180004c9b  jmp     loc_180004DDD
0x180004ca0  mov     ecx, 0C000000Dh
0x180004ca5  jmp     loc_180004DDD
0x180004caa  cmp     ecx, 80070070h
0x180004cb0  jz      short loc_180004CEC
0x180004cb2  cmp     ecx, 8007007Ah
0x180004cb8  jz      short loc_180004CE2
0x180004cba  cmp     ecx, 8007007Bh
0x180004cc0  jz      short loc_180004CD8
0x180004cc2  cmp     ecx, 8007007Eh
0x180004cc8  jnz     loc_180004D85
0x180004cce  mov     ecx, 0C0000135h
0x180004cd3  jmp     loc_180004DDD
0x180004cd8  mov     ecx, 0C0000033h
0x180004cdd  jmp     loc_180004DDD
0x180004ce2  mov     ecx, 0C0000023h
0x180004ce7  jmp     loc_180004DDD
0x180004cec  mov     ecx, 0C000007Fh
0x180004cf1  jmp     loc_180004DDD
0x180004cf6  mov     ecx, 80000005h
0x180004cfb  jmp     loc_180004DDD
0x180004d00  mov     eax, 8007047Eh
0x180004d05  cmp     ecx, eax
0x180004d07  jg      short loc_180004D69
0x180004d09  jz      short loc_180004D62
0x180004d0b  cmp     ecx, 80070216h
0x180004d11  jz      short loc_180004D5B
0x180004d13  cmp     ecx, 8007023Eh
0x180004d19  jz      short loc_180004D51
0x180004d1b  cmp     ecx, 80070246h
0x180004d21  jz      short loc_180004D47
0x180004d23  cmp     ecx, 80070247h
0x180004d29  jz      short loc_180004D3D
0x180004d2b  cmp     ecx, 80070272h
0x180004d31  jnz     short loc_180004D85
0x180004d33  mov     ecx, 0C0000273h
0x180004d38  jmp     loc_180004DDD
0x180004d3d  mov     ecx, 0C0000163h
0x180004d42  jmp     loc_180004DDD
0x180004d47  mov     ecx, 0C0000161h
0x180004d4c  jmp     loc_180004DDD
0x180004d51  mov     ecx, 0C0000025h
0x180004d56  jmp     loc_180004DDD
0x180004d5b  mov     ecx, 0C0000095h
0x180004d60  jmp     short loc_180004DDD
0x180004d62  mov     ecx, 0C0000059h
0x180004d67  jmp     short loc_180004DDD
0x180004d69  cmp     ecx, 8007050Ch
0x180004d6f  jz      short loc_180004DD8
0x180004d71  cmp     ecx, 8007054Fh
0x180004d77  jz      short loc_180004DD1
0x180004d79  cmp     ecx, 800705B9h
0x180004d7f  jz      short loc_180004DCA
0x180004d81  test    ecx, ecx
0x180004d83  jz      short loc_180004DC6
0x180004d85  bt      ecx, 1Ch
0x180004d89  jnb     short loc_180004D91
0x180004d8b  btr     ecx, 1Ch
0x180004d8f  jmp     short loc_180004DDD
0x180004d91  mov     eax, ecx
0x180004d93  and     eax, 1FFF0000h
0x180004d98  cmp     eax, 70000h
0x180004d9d  jnz     short loc_180004DB0
0x180004d9f  movzx   ecx, cx
0x180004da2  mov     eax, ecx
0x180004da4  or      eax, 0C0070000h
0x180004da9  test    ecx, ecx
0x180004dab  cmovnz  ecx, eax
0x180004dae  jmp     short loc_180004DDD
0x180004db0  cmp     eax, 90000h
0x180004db5  jnz     short loc_180004DD1
0x180004db7  test    ecx, ecx
0x180004db9  jle     short loc_180004DDD
0x180004dbb  movzx   ecx, cx
0x180004dbe  or      ecx, 0C0090000h
0x180004dc4  jmp     short loc_180004DDD
0x180004dc6  xor     ecx, ecx
0x180004dc8  jmp     short loc_180004DDD
0x180004dca  mov     ecx, 0C000A083h
0x180004dcf  jmp     short loc_180004DDD
0x180004dd1  mov     ecx, 0C00000E5h
0x180004dd6  jmp     short loc_180004DDD
0x180004dd8  mov     ecx, 0C000042Bh
0x180004ddd  mov     eax, ecx
0x180004ddf  retn
```
