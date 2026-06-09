# wil::details::HrToNtStatus(long)

- ea: `0x18001e1e8`
- end: `0x18001e3b1`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `457`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b638`
- `0x18001b6f0`
- `0x18001b744`
- `0x18001b800`
- `0x18001d650`
- `0x180022e50`

## callees

- `0x18001e1e8`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // edx

  v1 = (unsigned int)this;
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          return (unsigned int)-1073740757;
        case 0x8007054F:
          return (unsigned int)-1073741595;
        case 0x800705B9:
          return (unsigned int)-1073700733;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          return (unsigned int)-1073741735;
        case 0x80070216:
          return (unsigned int)-1073741675;
        case 0x8007023E:
          return (unsigned int)-1073741787;
        case 0x80070246:
          return (unsigned int)-1073741471;
        case 0x80070247:
          return (unsigned int)-1073741469;
        case 0x80070272:
          return (unsigned int)-1073741197;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
      return (unsigned int)-2147483643;
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          return (unsigned int)-1073741697;
        case 0x8007007A:
          return (unsigned int)-1073741789;
        case 0x8007007B:
          return (unsigned int)-1073741773;
        case 0x8007007E:
          return (unsigned int)-1073741515;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          return (unsigned int)-1073741811;
        case 0x80004005:
          return (unsigned int)-1073741823;
        case 0x80070001:
          return (unsigned int)-1073741822;
        case 0x80070002:
          return (unsigned int)-1073741772;
        case 0x80070003:
          return (unsigned int)-1073741766;
        case 0x8007000E:
          return (unsigned int)-1073741801;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
    return (unsigned int)this & 0xEFFFFFFF;
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    v1 = (unsigned __int16)this;
    if ( (_WORD)this )
      return (unsigned __int16)this | 0xC0070000;
    return v1;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
    return (unsigned int)-1073741595;
  if ( (int)this > 0 )
    return (unsigned __int16)this | 0xC0090000;
  return v1;
}

```

## disassembly

```asm
0x18001e1e8  mov     eax, 800700EAh
0x18001e1ed  mov     edx, ecx
0x18001e1ef  cmp     ecx, eax
0x18001e1f1  jg      loc_18001E2C6
0x18001e1f7  jz      loc_18001E2BC
0x18001e1fd  mov     eax, 80070057h
0x18001e202  cmp     ecx, eax
0x18001e204  jg      short loc_18001E270
0x18001e206  jz      short loc_18001E266
0x18001e208  cmp     ecx, 80004005h
0x18001e20e  jz      short loc_18001E25C
0x18001e210  cmp     ecx, 80070001h
0x18001e216  jz      short loc_18001E252
0x18001e218  cmp     ecx, 80070002h
0x18001e21e  jz      short loc_18001E248
0x18001e220  cmp     ecx, 80070003h
0x18001e226  jz      short loc_18001E23E
0x18001e228  cmp     ecx, 8007000Eh
0x18001e22e  jnz     loc_18001E34E
0x18001e234  mov     edx, 0C0000017h
0x18001e239  jmp     loc_18001E3AE
0x18001e23e  mov     edx, 0C000003Ah
0x18001e243  jmp     loc_18001E3AE
0x18001e248  mov     edx, 0C0000034h
0x18001e24d  jmp     loc_18001E3AE
0x18001e252  mov     edx, 0C0000002h
0x18001e257  jmp     loc_18001E3AE
0x18001e25c  mov     edx, 0C0000001h
0x18001e261  jmp     loc_18001E3AE
0x18001e266  mov     edx, 0C000000Dh
0x18001e26b  jmp     loc_18001E3AE
0x18001e270  cmp     edx, 80070070h
0x18001e276  jz      short loc_18001E2B2
0x18001e278  cmp     edx, 8007007Ah
0x18001e27e  jz      short loc_18001E2A8
0x18001e280  cmp     edx, 8007007Bh
0x18001e286  jz      short loc_18001E29E
0x18001e288  cmp     edx, 8007007Eh
0x18001e28e  jnz     loc_18001E34E
0x18001e294  mov     edx, 0C0000135h
0x18001e299  jmp     loc_18001E3AE
0x18001e29e  mov     edx, 0C0000033h
0x18001e2a3  jmp     loc_18001E3AE
0x18001e2a8  mov     edx, 0C0000023h
0x18001e2ad  jmp     loc_18001E3AE
0x18001e2b2  mov     edx, 0C000007Fh
0x18001e2b7  jmp     loc_18001E3AE
0x18001e2bc  mov     edx, 80000005h
0x18001e2c1  jmp     loc_18001E3AE
0x18001e2c6  mov     eax, 8007047Eh
0x18001e2cb  cmp     edx, eax
0x18001e2cd  jg      short loc_18001E332
0x18001e2cf  jz      short loc_18001E32B
0x18001e2d1  cmp     edx, 80070216h
0x18001e2d7  jz      short loc_18001E321
0x18001e2d9  cmp     edx, 8007023Eh
0x18001e2df  jz      short loc_18001E317
0x18001e2e1  cmp     edx, 80070246h
0x18001e2e7  jz      short loc_18001E30D
0x18001e2e9  cmp     edx, 80070247h
0x18001e2ef  jz      short loc_18001E303
0x18001e2f1  cmp     edx, 80070272h
0x18001e2f7  jnz     short loc_18001E34E
0x18001e2f9  mov     edx, 0C0000273h
0x18001e2fe  jmp     loc_18001E3AE
0x18001e303  mov     edx, 0C0000163h
0x18001e308  jmp     loc_18001E3AE
0x18001e30d  mov     edx, 0C0000161h
0x18001e312  jmp     loc_18001E3AE
0x18001e317  mov     edx, 0C0000025h
0x18001e31c  jmp     loc_18001E3AE
0x18001e321  mov     edx, 0C0000095h
0x18001e326  jmp     loc_18001E3AE
0x18001e32b  mov     edx, 0C0000059h
0x18001e330  jmp     short loc_18001E3AE
0x18001e332  cmp     edx, 8007050Ch
0x18001e338  jz      short loc_18001E3A9
0x18001e33a  cmp     edx, 8007054Fh
0x18001e340  jz      short loc_18001E3A2
0x18001e342  cmp     edx, 800705B9h
0x18001e348  jz      short loc_18001E39B
0x18001e34a  test    edx, edx
0x18001e34c  jz      short loc_18001E397
0x18001e34e  bt      edx, 1Ch
0x18001e352  jnb     short loc_18001E35A
0x18001e354  btr     edx, 1Ch
0x18001e358  jmp     short loc_18001E3AE
0x18001e35a  mov     eax, edx
0x18001e35c  mov     ecx, 1FFF0000h
0x18001e361  and     eax, ecx
0x18001e363  cmp     eax, 70000h
0x18001e368  jnz     short loc_18001E37D
0x18001e36a  movzx   ecx, dx
0x18001e36d  mov     eax, ecx
0x18001e36f  mov     edx, ecx
0x18001e371  or      eax, 0C0070000h
0x18001e376  test    ecx, ecx
0x18001e378  cmovnz  edx, eax
0x18001e37b  jmp     short loc_18001E3AE
0x18001e37d  mov     eax, edx
0x18001e37f  and     eax, ecx
0x18001e381  cmp     eax, 90000h
0x18001e386  jnz     short loc_18001E3A2
0x18001e388  test    edx, edx
0x18001e38a  jle     short loc_18001E3AE
0x18001e38c  movzx   edx, dx
0x18001e38f  or      edx, 0C0090000h
0x18001e395  jmp     short loc_18001E3AE
0x18001e397  xor     edx, edx
0x18001e399  jmp     short loc_18001E3AE
0x18001e39b  mov     edx, 0C000A083h
0x18001e3a0  jmp     short loc_18001E3AE
0x18001e3a2  mov     edx, 0C00000E5h
0x18001e3a7  jmp     short loc_18001E3AE
0x18001e3a9  mov     edx, 0C000042Bh
0x18001e3ae  mov     eax, edx
0x18001e3b0  retn
```
