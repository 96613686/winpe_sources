# wil::details::HrToNtStatus(long)

- ea: `0x18000a180`
- end: `0x18000a33c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800075e0`
- `0x180007680`
- `0x1800076d0`
- `0x180007790`
- `0x180009818`
- `0x18000a344`

## callees

- `0x18000a180`

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
0x18000a180  mov     eax, 800700EAh
0x18000a185  cmp     ecx, eax
0x18000a187  jg      loc_18000A25C
0x18000a18d  jz      loc_18000A252
0x18000a193  mov     eax, 80070057h
0x18000a198  cmp     ecx, eax
0x18000a19a  jg      short loc_18000A206
0x18000a19c  jz      short loc_18000A1FC
0x18000a19e  cmp     ecx, 80004005h
0x18000a1a4  jz      short loc_18000A1F2
0x18000a1a6  cmp     ecx, 80070001h
0x18000a1ac  jz      short loc_18000A1E8
0x18000a1ae  cmp     ecx, 80070002h
0x18000a1b4  jz      short loc_18000A1DE
0x18000a1b6  cmp     ecx, 80070003h
0x18000a1bc  jz      short loc_18000A1D4
0x18000a1be  cmp     ecx, 8007000Eh
0x18000a1c4  jnz     loc_18000A2E1
0x18000a1ca  mov     ecx, 0C0000017h
0x18000a1cf  jmp     loc_18000A339
0x18000a1d4  mov     ecx, 0C000003Ah
0x18000a1d9  jmp     loc_18000A339
0x18000a1de  mov     ecx, 0C0000034h
0x18000a1e3  jmp     loc_18000A339
0x18000a1e8  mov     ecx, 0C0000002h
0x18000a1ed  jmp     loc_18000A339
0x18000a1f2  mov     ecx, 0C0000001h
0x18000a1f7  jmp     loc_18000A339
0x18000a1fc  mov     ecx, 0C000000Dh
0x18000a201  jmp     loc_18000A339
0x18000a206  cmp     ecx, 80070070h
0x18000a20c  jz      short loc_18000A248
0x18000a20e  cmp     ecx, 8007007Ah
0x18000a214  jz      short loc_18000A23E
0x18000a216  cmp     ecx, 8007007Bh
0x18000a21c  jz      short loc_18000A234
0x18000a21e  cmp     ecx, 8007007Eh
0x18000a224  jnz     loc_18000A2E1
0x18000a22a  mov     ecx, 0C0000135h
0x18000a22f  jmp     loc_18000A339
0x18000a234  mov     ecx, 0C0000033h
0x18000a239  jmp     loc_18000A339
0x18000a23e  mov     ecx, 0C0000023h
0x18000a243  jmp     loc_18000A339
0x18000a248  mov     ecx, 0C000007Fh
0x18000a24d  jmp     loc_18000A339
0x18000a252  mov     ecx, 80000005h
0x18000a257  jmp     loc_18000A339
0x18000a25c  mov     eax, 8007047Eh
0x18000a261  cmp     ecx, eax
0x18000a263  jg      short loc_18000A2C5
0x18000a265  jz      short loc_18000A2BE
0x18000a267  cmp     ecx, 80070216h
0x18000a26d  jz      short loc_18000A2B7
0x18000a26f  cmp     ecx, 8007023Eh
0x18000a275  jz      short loc_18000A2AD
0x18000a277  cmp     ecx, 80070246h
0x18000a27d  jz      short loc_18000A2A3
0x18000a27f  cmp     ecx, 80070247h
0x18000a285  jz      short loc_18000A299
0x18000a287  cmp     ecx, 80070272h
0x18000a28d  jnz     short loc_18000A2E1
0x18000a28f  mov     ecx, 0C0000273h
0x18000a294  jmp     loc_18000A339
0x18000a299  mov     ecx, 0C0000163h
0x18000a29e  jmp     loc_18000A339
0x18000a2a3  mov     ecx, 0C0000161h
0x18000a2a8  jmp     loc_18000A339
0x18000a2ad  mov     ecx, 0C0000025h
0x18000a2b2  jmp     loc_18000A339
0x18000a2b7  mov     ecx, 0C0000095h
0x18000a2bc  jmp     short loc_18000A339
0x18000a2be  mov     ecx, 0C0000059h
0x18000a2c3  jmp     short loc_18000A339
0x18000a2c5  cmp     ecx, 8007050Ch
0x18000a2cb  jz      short loc_18000A334
0x18000a2cd  cmp     ecx, 8007054Fh
0x18000a2d3  jz      short loc_18000A32D
0x18000a2d5  cmp     ecx, 800705B9h
0x18000a2db  jz      short loc_18000A326
0x18000a2dd  test    ecx, ecx
0x18000a2df  jz      short loc_18000A322
0x18000a2e1  bt      ecx, 1Ch
0x18000a2e5  jnb     short loc_18000A2ED
0x18000a2e7  btr     ecx, 1Ch
0x18000a2eb  jmp     short loc_18000A339
0x18000a2ed  mov     eax, ecx
0x18000a2ef  and     eax, 1FFF0000h
0x18000a2f4  cmp     eax, 70000h
0x18000a2f9  jnz     short loc_18000A30C
0x18000a2fb  movzx   ecx, cx
0x18000a2fe  mov     eax, ecx
0x18000a300  or      eax, 0C0070000h
0x18000a305  test    ecx, ecx
0x18000a307  cmovnz  ecx, eax
0x18000a30a  jmp     short loc_18000A339
0x18000a30c  cmp     eax, 90000h
0x18000a311  jnz     short loc_18000A32D
0x18000a313  test    ecx, ecx
0x18000a315  jle     short loc_18000A339
0x18000a317  movzx   ecx, cx
0x18000a31a  or      ecx, 0C0090000h
0x18000a320  jmp     short loc_18000A339
0x18000a322  xor     ecx, ecx
0x18000a324  jmp     short loc_18000A339
0x18000a326  mov     ecx, 0C000A083h
0x18000a32b  jmp     short loc_18000A339
0x18000a32d  mov     ecx, 0C00000E5h
0x18000a332  jmp     short loc_18000A339
0x18000a334  mov     ecx, 0C000042Bh
0x18000a339  mov     eax, ecx
0x18000a33b  retn
```
