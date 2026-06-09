# wil::details::HrToNtStatus(long)

- ea: `0x180006e8c`
- end: `0x180007048`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050d4`
- `0x18000514c`
- `0x1800051c4`
- `0x180005214`
- `0x180005278`
- `0x180007180`

## callees

- `0x180006e8c`

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
0x180006e8c  mov     eax, 800700EAh
0x180006e91  cmp     ecx, eax
0x180006e93  jg      loc_180006F68
0x180006e99  jz      loc_180006F5E
0x180006e9f  mov     eax, 80070057h
0x180006ea4  cmp     ecx, eax
0x180006ea6  jg      short loc_180006F12
0x180006ea8  jz      short loc_180006F08
0x180006eaa  cmp     ecx, 80004005h
0x180006eb0  jz      short loc_180006EFE
0x180006eb2  cmp     ecx, 80070001h
0x180006eb8  jz      short loc_180006EF4
0x180006eba  cmp     ecx, 80070002h
0x180006ec0  jz      short loc_180006EEA
0x180006ec2  cmp     ecx, 80070003h
0x180006ec8  jz      short loc_180006EE0
0x180006eca  cmp     ecx, 8007000Eh
0x180006ed0  jnz     loc_180006FED
0x180006ed6  mov     ecx, 0C0000017h
0x180006edb  jmp     loc_180007045
0x180006ee0  mov     ecx, 0C000003Ah
0x180006ee5  jmp     loc_180007045
0x180006eea  mov     ecx, 0C0000034h
0x180006eef  jmp     loc_180007045
0x180006ef4  mov     ecx, 0C0000002h
0x180006ef9  jmp     loc_180007045
0x180006efe  mov     ecx, 0C0000001h
0x180006f03  jmp     loc_180007045
0x180006f08  mov     ecx, 0C000000Dh
0x180006f0d  jmp     loc_180007045
0x180006f12  cmp     ecx, 80070070h
0x180006f18  jz      short loc_180006F54
0x180006f1a  cmp     ecx, 8007007Ah
0x180006f20  jz      short loc_180006F4A
0x180006f22  cmp     ecx, 8007007Bh
0x180006f28  jz      short loc_180006F40
0x180006f2a  cmp     ecx, 8007007Eh
0x180006f30  jnz     loc_180006FED
0x180006f36  mov     ecx, 0C0000135h
0x180006f3b  jmp     loc_180007045
0x180006f40  mov     ecx, 0C0000033h
0x180006f45  jmp     loc_180007045
0x180006f4a  mov     ecx, 0C0000023h
0x180006f4f  jmp     loc_180007045
0x180006f54  mov     ecx, 0C000007Fh
0x180006f59  jmp     loc_180007045
0x180006f5e  mov     ecx, 80000005h
0x180006f63  jmp     loc_180007045
0x180006f68  mov     eax, 8007047Eh
0x180006f6d  cmp     ecx, eax
0x180006f6f  jg      short loc_180006FD1
0x180006f71  jz      short loc_180006FCA
0x180006f73  cmp     ecx, 80070216h
0x180006f79  jz      short loc_180006FC3
0x180006f7b  cmp     ecx, 8007023Eh
0x180006f81  jz      short loc_180006FB9
0x180006f83  cmp     ecx, 80070246h
0x180006f89  jz      short loc_180006FAF
0x180006f8b  cmp     ecx, 80070247h
0x180006f91  jz      short loc_180006FA5
0x180006f93  cmp     ecx, 80070272h
0x180006f99  jnz     short loc_180006FED
0x180006f9b  mov     ecx, 0C0000273h
0x180006fa0  jmp     loc_180007045
0x180006fa5  mov     ecx, 0C0000163h
0x180006faa  jmp     loc_180007045
0x180006faf  mov     ecx, 0C0000161h
0x180006fb4  jmp     loc_180007045
0x180006fb9  mov     ecx, 0C0000025h
0x180006fbe  jmp     loc_180007045
0x180006fc3  mov     ecx, 0C0000095h
0x180006fc8  jmp     short loc_180007045
0x180006fca  mov     ecx, 0C0000059h
0x180006fcf  jmp     short loc_180007045
0x180006fd1  cmp     ecx, 8007050Ch
0x180006fd7  jz      short loc_180007040
0x180006fd9  cmp     ecx, 8007054Fh
0x180006fdf  jz      short loc_180007039
0x180006fe1  cmp     ecx, 800705B9h
0x180006fe7  jz      short loc_180007032
0x180006fe9  test    ecx, ecx
0x180006feb  jz      short loc_18000702E
0x180006fed  bt      ecx, 1Ch
0x180006ff1  jnb     short loc_180006FF9
0x180006ff3  btr     ecx, 1Ch
0x180006ff7  jmp     short loc_180007045
0x180006ff9  mov     eax, ecx
0x180006ffb  and     eax, 1FFF0000h
0x180007000  cmp     eax, 70000h
0x180007005  jnz     short loc_180007018
0x180007007  movzx   ecx, cx
0x18000700a  mov     eax, ecx
0x18000700c  or      eax, 0C0070000h
0x180007011  test    ecx, ecx
0x180007013  cmovnz  ecx, eax
0x180007016  jmp     short loc_180007045
0x180007018  cmp     eax, 90000h
0x18000701d  jnz     short loc_180007039
0x18000701f  test    ecx, ecx
0x180007021  jle     short loc_180007045
0x180007023  movzx   ecx, cx
0x180007026  or      ecx, 0C0090000h
0x18000702c  jmp     short loc_180007045
0x18000702e  xor     ecx, ecx
0x180007030  jmp     short loc_180007045
0x180007032  mov     ecx, 0C000A083h
0x180007037  jmp     short loc_180007045
0x180007039  mov     ecx, 0C00000E5h
0x18000703e  jmp     short loc_180007045
0x180007040  mov     ecx, 0C000042Bh
0x180007045  mov     eax, ecx
0x180007047  retn
```
