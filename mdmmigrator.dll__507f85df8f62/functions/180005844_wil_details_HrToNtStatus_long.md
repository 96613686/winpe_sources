# wil::details::HrToNtStatus(long)

- ea: `0x180005844`
- end: `0x180005a00`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a00`
- `0x180003ab0`
- `0x180003b08`
- `0x180003bd0`
- `0x180004e18`
- `0x180005a08`
- `0x180006110`
- `0x18000797c`
- `0x180011a98`
- `0x18001ed22`
- `0x18001ed8d`
- `0x18001ee56`
- `0x18001eec1`

## callees

- `0x180005844`

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
0x180005844  mov     eax, 800700EAh
0x180005849  cmp     ecx, eax
0x18000584b  jg      loc_180005920
0x180005851  jz      loc_180005916
0x180005857  mov     eax, 80070057h
0x18000585c  cmp     ecx, eax
0x18000585e  jg      short loc_1800058CA
0x180005860  jz      short loc_1800058C0
0x180005862  cmp     ecx, 80004005h
0x180005868  jz      short loc_1800058B6
0x18000586a  cmp     ecx, 80070001h
0x180005870  jz      short loc_1800058AC
0x180005872  cmp     ecx, 80070002h
0x180005878  jz      short loc_1800058A2
0x18000587a  cmp     ecx, 80070003h
0x180005880  jz      short loc_180005898
0x180005882  cmp     ecx, 8007000Eh
0x180005888  jnz     loc_1800059A5
0x18000588e  mov     ecx, 0C0000017h
0x180005893  jmp     loc_1800059FD
0x180005898  mov     ecx, 0C000003Ah
0x18000589d  jmp     loc_1800059FD
0x1800058a2  mov     ecx, 0C0000034h
0x1800058a7  jmp     loc_1800059FD
0x1800058ac  mov     ecx, 0C0000002h
0x1800058b1  jmp     loc_1800059FD
0x1800058b6  mov     ecx, 0C0000001h
0x1800058bb  jmp     loc_1800059FD
0x1800058c0  mov     ecx, 0C000000Dh
0x1800058c5  jmp     loc_1800059FD
0x1800058ca  cmp     ecx, 80070070h
0x1800058d0  jz      short loc_18000590C
0x1800058d2  cmp     ecx, 8007007Ah
0x1800058d8  jz      short loc_180005902
0x1800058da  cmp     ecx, 8007007Bh
0x1800058e0  jz      short loc_1800058F8
0x1800058e2  cmp     ecx, 8007007Eh
0x1800058e8  jnz     loc_1800059A5
0x1800058ee  mov     ecx, 0C0000135h
0x1800058f3  jmp     loc_1800059FD
0x1800058f8  mov     ecx, 0C0000033h
0x1800058fd  jmp     loc_1800059FD
0x180005902  mov     ecx, 0C0000023h
0x180005907  jmp     loc_1800059FD
0x18000590c  mov     ecx, 0C000007Fh
0x180005911  jmp     loc_1800059FD
0x180005916  mov     ecx, 80000005h
0x18000591b  jmp     loc_1800059FD
0x180005920  mov     eax, 8007047Eh
0x180005925  cmp     ecx, eax
0x180005927  jg      short loc_180005989
0x180005929  jz      short loc_180005982
0x18000592b  cmp     ecx, 80070216h
0x180005931  jz      short loc_18000597B
0x180005933  cmp     ecx, 8007023Eh
0x180005939  jz      short loc_180005971
0x18000593b  cmp     ecx, 80070246h
0x180005941  jz      short loc_180005967
0x180005943  cmp     ecx, 80070247h
0x180005949  jz      short loc_18000595D
0x18000594b  cmp     ecx, 80070272h
0x180005951  jnz     short loc_1800059A5
0x180005953  mov     ecx, 0C0000273h
0x180005958  jmp     loc_1800059FD
0x18000595d  mov     ecx, 0C0000163h
0x180005962  jmp     loc_1800059FD
0x180005967  mov     ecx, 0C0000161h
0x18000596c  jmp     loc_1800059FD
0x180005971  mov     ecx, 0C0000025h
0x180005976  jmp     loc_1800059FD
0x18000597b  mov     ecx, 0C0000095h
0x180005980  jmp     short loc_1800059FD
0x180005982  mov     ecx, 0C0000059h
0x180005987  jmp     short loc_1800059FD
0x180005989  cmp     ecx, 8007050Ch
0x18000598f  jz      short loc_1800059F8
0x180005991  cmp     ecx, 8007054Fh
0x180005997  jz      short loc_1800059F1
0x180005999  cmp     ecx, 800705B9h
0x18000599f  jz      short loc_1800059EA
0x1800059a1  test    ecx, ecx
0x1800059a3  jz      short loc_1800059E6
0x1800059a5  bt      ecx, 1Ch
0x1800059a9  jnb     short loc_1800059B1
0x1800059ab  btr     ecx, 1Ch
0x1800059af  jmp     short loc_1800059FD
0x1800059b1  mov     eax, ecx
0x1800059b3  and     eax, 1FFF0000h
0x1800059b8  cmp     eax, 70000h
0x1800059bd  jnz     short loc_1800059D0
0x1800059bf  movzx   ecx, cx
0x1800059c2  mov     eax, ecx
0x1800059c4  or      eax, 0C0070000h
0x1800059c9  test    ecx, ecx
0x1800059cb  cmovnz  ecx, eax
0x1800059ce  jmp     short loc_1800059FD
0x1800059d0  cmp     eax, 90000h
0x1800059d5  jnz     short loc_1800059F1
0x1800059d7  test    ecx, ecx
0x1800059d9  jle     short loc_1800059FD
0x1800059db  movzx   ecx, cx
0x1800059de  or      ecx, 0C0090000h
0x1800059e4  jmp     short loc_1800059FD
0x1800059e6  xor     ecx, ecx
0x1800059e8  jmp     short loc_1800059FD
0x1800059ea  mov     ecx, 0C000A083h
0x1800059ef  jmp     short loc_1800059FD
0x1800059f1  mov     ecx, 0C00000E5h
0x1800059f6  jmp     short loc_1800059FD
0x1800059f8  mov     ecx, 0C000042Bh
0x1800059fd  mov     eax, ecx
0x1800059ff  retn
```
