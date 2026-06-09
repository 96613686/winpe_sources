# wil::details::HrToNtStatus(long)

- ea: `0x180006e5c`
- end: `0x180007018`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045fc`
- `0x18000469c`
- `0x1800046ec`
- `0x1800047a4`
- `0x180006368`
- `0x1800070fc`

## callees

- `0x180006e5c`

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
0x180006e5c  mov     eax, 800700EAh
0x180006e61  cmp     ecx, eax
0x180006e63  jg      loc_180006F38
0x180006e69  jz      loc_180006F2E
0x180006e6f  mov     eax, 80070057h
0x180006e74  cmp     ecx, eax
0x180006e76  jg      short loc_180006EE2
0x180006e78  jz      short loc_180006ED8
0x180006e7a  cmp     ecx, 80004005h
0x180006e80  jz      short loc_180006ECE
0x180006e82  cmp     ecx, 80070001h
0x180006e88  jz      short loc_180006EC4
0x180006e8a  cmp     ecx, 80070002h
0x180006e90  jz      short loc_180006EBA
0x180006e92  cmp     ecx, 80070003h
0x180006e98  jz      short loc_180006EB0
0x180006e9a  cmp     ecx, 8007000Eh
0x180006ea0  jnz     loc_180006FBD
0x180006ea6  mov     ecx, 0C0000017h
0x180006eab  jmp     loc_180007015
0x180006eb0  mov     ecx, 0C000003Ah
0x180006eb5  jmp     loc_180007015
0x180006eba  mov     ecx, 0C0000034h
0x180006ebf  jmp     loc_180007015
0x180006ec4  mov     ecx, 0C0000002h
0x180006ec9  jmp     loc_180007015
0x180006ece  mov     ecx, 0C0000001h
0x180006ed3  jmp     loc_180007015
0x180006ed8  mov     ecx, 0C000000Dh
0x180006edd  jmp     loc_180007015
0x180006ee2  cmp     ecx, 80070070h
0x180006ee8  jz      short loc_180006F24
0x180006eea  cmp     ecx, 8007007Ah
0x180006ef0  jz      short loc_180006F1A
0x180006ef2  cmp     ecx, 8007007Bh
0x180006ef8  jz      short loc_180006F10
0x180006efa  cmp     ecx, 8007007Eh
0x180006f00  jnz     loc_180006FBD
0x180006f06  mov     ecx, 0C0000135h
0x180006f0b  jmp     loc_180007015
0x180006f10  mov     ecx, 0C0000033h
0x180006f15  jmp     loc_180007015
0x180006f1a  mov     ecx, 0C0000023h
0x180006f1f  jmp     loc_180007015
0x180006f24  mov     ecx, 0C000007Fh
0x180006f29  jmp     loc_180007015
0x180006f2e  mov     ecx, 80000005h
0x180006f33  jmp     loc_180007015
0x180006f38  mov     eax, 8007047Eh
0x180006f3d  cmp     ecx, eax
0x180006f3f  jg      short loc_180006FA1
0x180006f41  jz      short loc_180006F9A
0x180006f43  cmp     ecx, 80070216h
0x180006f49  jz      short loc_180006F93
0x180006f4b  cmp     ecx, 8007023Eh
0x180006f51  jz      short loc_180006F89
0x180006f53  cmp     ecx, 80070246h
0x180006f59  jz      short loc_180006F7F
0x180006f5b  cmp     ecx, 80070247h
0x180006f61  jz      short loc_180006F75
0x180006f63  cmp     ecx, 80070272h
0x180006f69  jnz     short loc_180006FBD
0x180006f6b  mov     ecx, 0C0000273h
0x180006f70  jmp     loc_180007015
0x180006f75  mov     ecx, 0C0000163h
0x180006f7a  jmp     loc_180007015
0x180006f7f  mov     ecx, 0C0000161h
0x180006f84  jmp     loc_180007015
0x180006f89  mov     ecx, 0C0000025h
0x180006f8e  jmp     loc_180007015
0x180006f93  mov     ecx, 0C0000095h
0x180006f98  jmp     short loc_180007015
0x180006f9a  mov     ecx, 0C0000059h
0x180006f9f  jmp     short loc_180007015
0x180006fa1  cmp     ecx, 8007050Ch
0x180006fa7  jz      short loc_180007010
0x180006fa9  cmp     ecx, 8007054Fh
0x180006faf  jz      short loc_180007009
0x180006fb1  cmp     ecx, 800705B9h
0x180006fb7  jz      short loc_180007002
0x180006fb9  test    ecx, ecx
0x180006fbb  jz      short loc_180006FFE
0x180006fbd  bt      ecx, 1Ch
0x180006fc1  jnb     short loc_180006FC9
0x180006fc3  btr     ecx, 1Ch
0x180006fc7  jmp     short loc_180007015
0x180006fc9  mov     eax, ecx
0x180006fcb  and     eax, 1FFF0000h
0x180006fd0  cmp     eax, 70000h
0x180006fd5  jnz     short loc_180006FE8
0x180006fd7  movzx   ecx, cx
0x180006fda  mov     eax, ecx
0x180006fdc  or      eax, 0C0070000h
0x180006fe1  test    ecx, ecx
0x180006fe3  cmovnz  ecx, eax
0x180006fe6  jmp     short loc_180007015
0x180006fe8  cmp     eax, 90000h
0x180006fed  jnz     short loc_180007009
0x180006fef  test    ecx, ecx
0x180006ff1  jle     short loc_180007015
0x180006ff3  movzx   ecx, cx
0x180006ff6  or      ecx, 0C0090000h
0x180006ffc  jmp     short loc_180007015
0x180006ffe  xor     ecx, ecx
0x180007000  jmp     short loc_180007015
0x180007002  mov     ecx, 0C000A083h
0x180007007  jmp     short loc_180007015
0x180007009  mov     ecx, 0C00000E5h
0x18000700e  jmp     short loc_180007015
0x180007010  mov     ecx, 0C000042Bh
0x180007015  mov     eax, ecx
0x180007017  retn
```
