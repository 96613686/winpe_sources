# wil::details::HrToNtStatus(long)

- ea: `0x18000a70c`
- end: `0x18000a8c8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000902c`
- `0x1800090d4`
- `0x180009124`
- `0x1800091dc`
- `0x180009df4`
- `0x18000a8d0`

## callees

- `0x18000a70c`

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
0x18000a70c  mov     eax, 800700EAh
0x18000a711  cmp     ecx, eax
0x18000a713  jg      loc_18000A7E8
0x18000a719  jz      loc_18000A7DE
0x18000a71f  mov     eax, 80070057h
0x18000a724  cmp     ecx, eax
0x18000a726  jg      short loc_18000A792
0x18000a728  jz      short loc_18000A788
0x18000a72a  cmp     ecx, 80004005h
0x18000a730  jz      short loc_18000A77E
0x18000a732  cmp     ecx, 80070001h
0x18000a738  jz      short loc_18000A774
0x18000a73a  cmp     ecx, 80070002h
0x18000a740  jz      short loc_18000A76A
0x18000a742  cmp     ecx, 80070003h
0x18000a748  jz      short loc_18000A760
0x18000a74a  cmp     ecx, 8007000Eh
0x18000a750  jnz     loc_18000A86D
0x18000a756  mov     ecx, 0C0000017h
0x18000a75b  jmp     loc_18000A8C5
0x18000a760  mov     ecx, 0C000003Ah
0x18000a765  jmp     loc_18000A8C5
0x18000a76a  mov     ecx, 0C0000034h
0x18000a76f  jmp     loc_18000A8C5
0x18000a774  mov     ecx, 0C0000002h
0x18000a779  jmp     loc_18000A8C5
0x18000a77e  mov     ecx, 0C0000001h
0x18000a783  jmp     loc_18000A8C5
0x18000a788  mov     ecx, 0C000000Dh
0x18000a78d  jmp     loc_18000A8C5
0x18000a792  cmp     ecx, 80070070h
0x18000a798  jz      short loc_18000A7D4
0x18000a79a  cmp     ecx, 8007007Ah
0x18000a7a0  jz      short loc_18000A7CA
0x18000a7a2  cmp     ecx, 8007007Bh
0x18000a7a8  jz      short loc_18000A7C0
0x18000a7aa  cmp     ecx, 8007007Eh
0x18000a7b0  jnz     loc_18000A86D
0x18000a7b6  mov     ecx, 0C0000135h
0x18000a7bb  jmp     loc_18000A8C5
0x18000a7c0  mov     ecx, 0C0000033h
0x18000a7c5  jmp     loc_18000A8C5
0x18000a7ca  mov     ecx, 0C0000023h
0x18000a7cf  jmp     loc_18000A8C5
0x18000a7d4  mov     ecx, 0C000007Fh
0x18000a7d9  jmp     loc_18000A8C5
0x18000a7de  mov     ecx, 80000005h
0x18000a7e3  jmp     loc_18000A8C5
0x18000a7e8  mov     eax, 8007047Eh
0x18000a7ed  cmp     ecx, eax
0x18000a7ef  jg      short loc_18000A851
0x18000a7f1  jz      short loc_18000A84A
0x18000a7f3  cmp     ecx, 80070216h
0x18000a7f9  jz      short loc_18000A843
0x18000a7fb  cmp     ecx, 8007023Eh
0x18000a801  jz      short loc_18000A839
0x18000a803  cmp     ecx, 80070246h
0x18000a809  jz      short loc_18000A82F
0x18000a80b  cmp     ecx, 80070247h
0x18000a811  jz      short loc_18000A825
0x18000a813  cmp     ecx, 80070272h
0x18000a819  jnz     short loc_18000A86D
0x18000a81b  mov     ecx, 0C0000273h
0x18000a820  jmp     loc_18000A8C5
0x18000a825  mov     ecx, 0C0000163h
0x18000a82a  jmp     loc_18000A8C5
0x18000a82f  mov     ecx, 0C0000161h
0x18000a834  jmp     loc_18000A8C5
0x18000a839  mov     ecx, 0C0000025h
0x18000a83e  jmp     loc_18000A8C5
0x18000a843  mov     ecx, 0C0000095h
0x18000a848  jmp     short loc_18000A8C5
0x18000a84a  mov     ecx, 0C0000059h
0x18000a84f  jmp     short loc_18000A8C5
0x18000a851  cmp     ecx, 8007050Ch
0x18000a857  jz      short loc_18000A8C0
0x18000a859  cmp     ecx, 8007054Fh
0x18000a85f  jz      short loc_18000A8B9
0x18000a861  cmp     ecx, 800705B9h
0x18000a867  jz      short loc_18000A8B2
0x18000a869  test    ecx, ecx
0x18000a86b  jz      short loc_18000A8AE
0x18000a86d  bt      ecx, 1Ch
0x18000a871  jnb     short loc_18000A879
0x18000a873  btr     ecx, 1Ch
0x18000a877  jmp     short loc_18000A8C5
0x18000a879  mov     eax, ecx
0x18000a87b  and     eax, 1FFF0000h
0x18000a880  cmp     eax, 70000h
0x18000a885  jnz     short loc_18000A898
0x18000a887  movzx   ecx, cx
0x18000a88a  mov     eax, ecx
0x18000a88c  or      eax, 0C0070000h
0x18000a891  test    ecx, ecx
0x18000a893  cmovnz  ecx, eax
0x18000a896  jmp     short loc_18000A8C5
0x18000a898  cmp     eax, 90000h
0x18000a89d  jnz     short loc_18000A8B9
0x18000a89f  test    ecx, ecx
0x18000a8a1  jle     short loc_18000A8C5
0x18000a8a3  movzx   ecx, cx
0x18000a8a6  or      ecx, 0C0090000h
0x18000a8ac  jmp     short loc_18000A8C5
0x18000a8ae  xor     ecx, ecx
0x18000a8b0  jmp     short loc_18000A8C5
0x18000a8b2  mov     ecx, 0C000A083h
0x18000a8b7  jmp     short loc_18000A8C5
0x18000a8b9  mov     ecx, 0C00000E5h
0x18000a8be  jmp     short loc_18000A8C5
0x18000a8c0  mov     ecx, 0C000042Bh
0x18000a8c5  mov     eax, ecx
0x18000a8c7  retn
```
