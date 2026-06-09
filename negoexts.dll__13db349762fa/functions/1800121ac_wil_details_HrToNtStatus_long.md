# wil::details::HrToNtStatus(long)

- ea: `0x1800121ac`
- end: `0x180012368`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800101e4`
- `0x18001025c`
- `0x1800102d4`
- `0x180010324`
- `0x180010388`
- `0x18001258c`

## callees

- `0x1800121ac`

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
0x1800121ac  mov     eax, 800700EAh
0x1800121b1  cmp     ecx, eax
0x1800121b3  jg      loc_180012288
0x1800121b9  jz      loc_18001227E
0x1800121bf  mov     eax, 80070057h
0x1800121c4  cmp     ecx, eax
0x1800121c6  jg      short loc_180012232
0x1800121c8  jz      short loc_180012228
0x1800121ca  cmp     ecx, 80004005h
0x1800121d0  jz      short loc_18001221E
0x1800121d2  cmp     ecx, 80070001h
0x1800121d8  jz      short loc_180012214
0x1800121da  cmp     ecx, 80070002h
0x1800121e0  jz      short loc_18001220A
0x1800121e2  cmp     ecx, 80070003h
0x1800121e8  jz      short loc_180012200
0x1800121ea  cmp     ecx, 8007000Eh
0x1800121f0  jnz     loc_18001230D
0x1800121f6  mov     ecx, 0C0000017h
0x1800121fb  jmp     loc_180012365
0x180012200  mov     ecx, 0C000003Ah
0x180012205  jmp     loc_180012365
0x18001220a  mov     ecx, 0C0000034h
0x18001220f  jmp     loc_180012365
0x180012214  mov     ecx, 0C0000002h
0x180012219  jmp     loc_180012365
0x18001221e  mov     ecx, 0C0000001h
0x180012223  jmp     loc_180012365
0x180012228  mov     ecx, 0C000000Dh
0x18001222d  jmp     loc_180012365
0x180012232  cmp     ecx, 80070070h
0x180012238  jz      short loc_180012274
0x18001223a  cmp     ecx, 8007007Ah
0x180012240  jz      short loc_18001226A
0x180012242  cmp     ecx, 8007007Bh
0x180012248  jz      short loc_180012260
0x18001224a  cmp     ecx, 8007007Eh
0x180012250  jnz     loc_18001230D
0x180012256  mov     ecx, 0C0000135h
0x18001225b  jmp     loc_180012365
0x180012260  mov     ecx, 0C0000033h
0x180012265  jmp     loc_180012365
0x18001226a  mov     ecx, 0C0000023h
0x18001226f  jmp     loc_180012365
0x180012274  mov     ecx, 0C000007Fh
0x180012279  jmp     loc_180012365
0x18001227e  mov     ecx, 80000005h
0x180012283  jmp     loc_180012365
0x180012288  mov     eax, 8007047Eh
0x18001228d  cmp     ecx, eax
0x18001228f  jg      short loc_1800122F1
0x180012291  jz      short loc_1800122EA
0x180012293  cmp     ecx, 80070216h
0x180012299  jz      short loc_1800122E3
0x18001229b  cmp     ecx, 8007023Eh
0x1800122a1  jz      short loc_1800122D9
0x1800122a3  cmp     ecx, 80070246h
0x1800122a9  jz      short loc_1800122CF
0x1800122ab  cmp     ecx, 80070247h
0x1800122b1  jz      short loc_1800122C5
0x1800122b3  cmp     ecx, 80070272h
0x1800122b9  jnz     short loc_18001230D
0x1800122bb  mov     ecx, 0C0000273h
0x1800122c0  jmp     loc_180012365
0x1800122c5  mov     ecx, 0C0000163h
0x1800122ca  jmp     loc_180012365
0x1800122cf  mov     ecx, 0C0000161h
0x1800122d4  jmp     loc_180012365
0x1800122d9  mov     ecx, 0C0000025h
0x1800122de  jmp     loc_180012365
0x1800122e3  mov     ecx, 0C0000095h
0x1800122e8  jmp     short loc_180012365
0x1800122ea  mov     ecx, 0C0000059h
0x1800122ef  jmp     short loc_180012365
0x1800122f1  cmp     ecx, 8007050Ch
0x1800122f7  jz      short loc_180012360
0x1800122f9  cmp     ecx, 8007054Fh
0x1800122ff  jz      short loc_180012359
0x180012301  cmp     ecx, 800705B9h
0x180012307  jz      short loc_180012352
0x180012309  test    ecx, ecx
0x18001230b  jz      short loc_18001234E
0x18001230d  bt      ecx, 1Ch
0x180012311  jnb     short loc_180012319
0x180012313  btr     ecx, 1Ch
0x180012317  jmp     short loc_180012365
0x180012319  mov     eax, ecx
0x18001231b  and     eax, 1FFF0000h
0x180012320  cmp     eax, 70000h
0x180012325  jnz     short loc_180012338
0x180012327  movzx   ecx, cx
0x18001232a  mov     eax, ecx
0x18001232c  or      eax, 0C0070000h
0x180012331  test    ecx, ecx
0x180012333  cmovnz  ecx, eax
0x180012336  jmp     short loc_180012365
0x180012338  cmp     eax, 90000h
0x18001233d  jnz     short loc_180012359
0x18001233f  test    ecx, ecx
0x180012341  jle     short loc_180012365
0x180012343  movzx   ecx, cx
0x180012346  or      ecx, 0C0090000h
0x18001234c  jmp     short loc_180012365
0x18001234e  xor     ecx, ecx
0x180012350  jmp     short loc_180012365
0x180012352  mov     ecx, 0C000A083h
0x180012357  jmp     short loc_180012365
0x180012359  mov     ecx, 0C00000E5h
0x18001235e  jmp     short loc_180012365
0x180012360  mov     ecx, 0C000042Bh
0x180012365  mov     eax, ecx
0x180012367  retn
```
