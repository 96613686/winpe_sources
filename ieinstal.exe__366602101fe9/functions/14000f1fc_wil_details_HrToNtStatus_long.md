# wil::details::HrToNtStatus(long)

- ea: `0x14000f1fc`
- end: `0x14000f3b8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dc80`
- `0x14000dd28`
- `0x14000dd78`
- `0x14000de30`
- `0x14000e8e0`
- `0x14000f3d0`

## callees

- `0x14000f1fc`

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
0x14000f1fc  mov     eax, 800700EAh
0x14000f201  cmp     ecx, eax
0x14000f203  jg      loc_14000F2D8
0x14000f209  jz      loc_14000F2CE
0x14000f20f  mov     eax, 80070057h
0x14000f214  cmp     ecx, eax
0x14000f216  jg      short loc_14000F282
0x14000f218  jz      short loc_14000F278
0x14000f21a  cmp     ecx, 80004005h
0x14000f220  jz      short loc_14000F26E
0x14000f222  cmp     ecx, 80070001h
0x14000f228  jz      short loc_14000F264
0x14000f22a  cmp     ecx, 80070002h
0x14000f230  jz      short loc_14000F25A
0x14000f232  cmp     ecx, 80070003h
0x14000f238  jz      short loc_14000F250
0x14000f23a  cmp     ecx, 8007000Eh
0x14000f240  jnz     loc_14000F35D
0x14000f246  mov     ecx, 0C0000017h
0x14000f24b  jmp     loc_14000F3B5
0x14000f250  mov     ecx, 0C000003Ah
0x14000f255  jmp     loc_14000F3B5
0x14000f25a  mov     ecx, 0C0000034h
0x14000f25f  jmp     loc_14000F3B5
0x14000f264  mov     ecx, 0C0000002h
0x14000f269  jmp     loc_14000F3B5
0x14000f26e  mov     ecx, 0C0000001h
0x14000f273  jmp     loc_14000F3B5
0x14000f278  mov     ecx, 0C000000Dh
0x14000f27d  jmp     loc_14000F3B5
0x14000f282  cmp     ecx, 80070070h
0x14000f288  jz      short loc_14000F2C4
0x14000f28a  cmp     ecx, 8007007Ah
0x14000f290  jz      short loc_14000F2BA
0x14000f292  cmp     ecx, 8007007Bh
0x14000f298  jz      short loc_14000F2B0
0x14000f29a  cmp     ecx, 8007007Eh
0x14000f2a0  jnz     loc_14000F35D
0x14000f2a6  mov     ecx, 0C0000135h
0x14000f2ab  jmp     loc_14000F3B5
0x14000f2b0  mov     ecx, 0C0000033h
0x14000f2b5  jmp     loc_14000F3B5
0x14000f2ba  mov     ecx, 0C0000023h
0x14000f2bf  jmp     loc_14000F3B5
0x14000f2c4  mov     ecx, 0C000007Fh
0x14000f2c9  jmp     loc_14000F3B5
0x14000f2ce  mov     ecx, 80000005h
0x14000f2d3  jmp     loc_14000F3B5
0x14000f2d8  mov     eax, 8007047Eh
0x14000f2dd  cmp     ecx, eax
0x14000f2df  jg      short loc_14000F341
0x14000f2e1  jz      short loc_14000F33A
0x14000f2e3  cmp     ecx, 80070216h
0x14000f2e9  jz      short loc_14000F333
0x14000f2eb  cmp     ecx, 8007023Eh
0x14000f2f1  jz      short loc_14000F329
0x14000f2f3  cmp     ecx, 80070246h
0x14000f2f9  jz      short loc_14000F31F
0x14000f2fb  cmp     ecx, 80070247h
0x14000f301  jz      short loc_14000F315
0x14000f303  cmp     ecx, 80070272h
0x14000f309  jnz     short loc_14000F35D
0x14000f30b  mov     ecx, 0C0000273h
0x14000f310  jmp     loc_14000F3B5
0x14000f315  mov     ecx, 0C0000163h
0x14000f31a  jmp     loc_14000F3B5
0x14000f31f  mov     ecx, 0C0000161h
0x14000f324  jmp     loc_14000F3B5
0x14000f329  mov     ecx, 0C0000025h
0x14000f32e  jmp     loc_14000F3B5
0x14000f333  mov     ecx, 0C0000095h
0x14000f338  jmp     short loc_14000F3B5
0x14000f33a  mov     ecx, 0C0000059h
0x14000f33f  jmp     short loc_14000F3B5
0x14000f341  cmp     ecx, 8007050Ch
0x14000f347  jz      short loc_14000F3B0
0x14000f349  cmp     ecx, 8007054Fh
0x14000f34f  jz      short loc_14000F3A9
0x14000f351  cmp     ecx, 800705B9h
0x14000f357  jz      short loc_14000F3A2
0x14000f359  test    ecx, ecx
0x14000f35b  jz      short loc_14000F39E
0x14000f35d  bt      ecx, 1Ch
0x14000f361  jnb     short loc_14000F369
0x14000f363  btr     ecx, 1Ch
0x14000f367  jmp     short loc_14000F3B5
0x14000f369  mov     eax, ecx
0x14000f36b  and     eax, 1FFF0000h
0x14000f370  cmp     eax, 70000h
0x14000f375  jnz     short loc_14000F388
0x14000f377  movzx   ecx, cx
0x14000f37a  mov     eax, ecx
0x14000f37c  or      eax, 0C0070000h
0x14000f381  test    ecx, ecx
0x14000f383  cmovnz  ecx, eax
0x14000f386  jmp     short loc_14000F3B5
0x14000f388  cmp     eax, 90000h
0x14000f38d  jnz     short loc_14000F3A9
0x14000f38f  test    ecx, ecx
0x14000f391  jle     short loc_14000F3B5
0x14000f393  movzx   ecx, cx
0x14000f396  or      ecx, 0C0090000h
0x14000f39c  jmp     short loc_14000F3B5
0x14000f39e  xor     ecx, ecx
0x14000f3a0  jmp     short loc_14000F3B5
0x14000f3a2  mov     ecx, 0C000A083h
0x14000f3a7  jmp     short loc_14000F3B5
0x14000f3a9  mov     ecx, 0C00000E5h
0x14000f3ae  jmp     short loc_14000F3B5
0x14000f3b0  mov     ecx, 0C000042Bh
0x14000f3b5  mov     eax, ecx
0x14000f3b7  retn
```
