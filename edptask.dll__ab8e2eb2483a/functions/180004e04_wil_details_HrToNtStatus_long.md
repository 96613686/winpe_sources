# wil::details::HrToNtStatus(long)

- ea: `0x180004e04`
- end: `0x180004fc0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030d0`
- `0x180003178`
- `0x1800031c8`
- `0x180003288`
- `0x180004498`
- `0x180004fc8`

## callees

- `0x180004e04`

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
0x180004e04  mov     eax, 800700EAh
0x180004e09  cmp     ecx, eax
0x180004e0b  jg      loc_180004EE0
0x180004e11  jz      loc_180004ED6
0x180004e17  mov     eax, 80070057h
0x180004e1c  cmp     ecx, eax
0x180004e1e  jg      short loc_180004E8A
0x180004e20  jz      short loc_180004E80
0x180004e22  cmp     ecx, 80004005h
0x180004e28  jz      short loc_180004E76
0x180004e2a  cmp     ecx, 80070001h
0x180004e30  jz      short loc_180004E6C
0x180004e32  cmp     ecx, 80070002h
0x180004e38  jz      short loc_180004E62
0x180004e3a  cmp     ecx, 80070003h
0x180004e40  jz      short loc_180004E58
0x180004e42  cmp     ecx, 8007000Eh
0x180004e48  jnz     loc_180004F65
0x180004e4e  mov     ecx, 0C0000017h
0x180004e53  jmp     loc_180004FBD
0x180004e58  mov     ecx, 0C000003Ah
0x180004e5d  jmp     loc_180004FBD
0x180004e62  mov     ecx, 0C0000034h
0x180004e67  jmp     loc_180004FBD
0x180004e6c  mov     ecx, 0C0000002h
0x180004e71  jmp     loc_180004FBD
0x180004e76  mov     ecx, 0C0000001h
0x180004e7b  jmp     loc_180004FBD
0x180004e80  mov     ecx, 0C000000Dh
0x180004e85  jmp     loc_180004FBD
0x180004e8a  cmp     ecx, 80070070h
0x180004e90  jz      short loc_180004ECC
0x180004e92  cmp     ecx, 8007007Ah
0x180004e98  jz      short loc_180004EC2
0x180004e9a  cmp     ecx, 8007007Bh
0x180004ea0  jz      short loc_180004EB8
0x180004ea2  cmp     ecx, 8007007Eh
0x180004ea8  jnz     loc_180004F65
0x180004eae  mov     ecx, 0C0000135h
0x180004eb3  jmp     loc_180004FBD
0x180004eb8  mov     ecx, 0C0000033h
0x180004ebd  jmp     loc_180004FBD
0x180004ec2  mov     ecx, 0C0000023h
0x180004ec7  jmp     loc_180004FBD
0x180004ecc  mov     ecx, 0C000007Fh
0x180004ed1  jmp     loc_180004FBD
0x180004ed6  mov     ecx, 80000005h
0x180004edb  jmp     loc_180004FBD
0x180004ee0  mov     eax, 8007047Eh
0x180004ee5  cmp     ecx, eax
0x180004ee7  jg      short loc_180004F49
0x180004ee9  jz      short loc_180004F42
0x180004eeb  cmp     ecx, 80070216h
0x180004ef1  jz      short loc_180004F3B
0x180004ef3  cmp     ecx, 8007023Eh
0x180004ef9  jz      short loc_180004F31
0x180004efb  cmp     ecx, 80070246h
0x180004f01  jz      short loc_180004F27
0x180004f03  cmp     ecx, 80070247h
0x180004f09  jz      short loc_180004F1D
0x180004f0b  cmp     ecx, 80070272h
0x180004f11  jnz     short loc_180004F65
0x180004f13  mov     ecx, 0C0000273h
0x180004f18  jmp     loc_180004FBD
0x180004f1d  mov     ecx, 0C0000163h
0x180004f22  jmp     loc_180004FBD
0x180004f27  mov     ecx, 0C0000161h
0x180004f2c  jmp     loc_180004FBD
0x180004f31  mov     ecx, 0C0000025h
0x180004f36  jmp     loc_180004FBD
0x180004f3b  mov     ecx, 0C0000095h
0x180004f40  jmp     short loc_180004FBD
0x180004f42  mov     ecx, 0C0000059h
0x180004f47  jmp     short loc_180004FBD
0x180004f49  cmp     ecx, 8007050Ch
0x180004f4f  jz      short loc_180004FB8
0x180004f51  cmp     ecx, 8007054Fh
0x180004f57  jz      short loc_180004FB1
0x180004f59  cmp     ecx, 800705B9h
0x180004f5f  jz      short loc_180004FAA
0x180004f61  test    ecx, ecx
0x180004f63  jz      short loc_180004FA6
0x180004f65  bt      ecx, 1Ch
0x180004f69  jnb     short loc_180004F71
0x180004f6b  btr     ecx, 1Ch
0x180004f6f  jmp     short loc_180004FBD
0x180004f71  mov     eax, ecx
0x180004f73  and     eax, 1FFF0000h
0x180004f78  cmp     eax, 70000h
0x180004f7d  jnz     short loc_180004F90
0x180004f7f  movzx   ecx, cx
0x180004f82  mov     eax, ecx
0x180004f84  or      eax, 0C0070000h
0x180004f89  test    ecx, ecx
0x180004f8b  cmovnz  ecx, eax
0x180004f8e  jmp     short loc_180004FBD
0x180004f90  cmp     eax, 90000h
0x180004f95  jnz     short loc_180004FB1
0x180004f97  test    ecx, ecx
0x180004f99  jle     short loc_180004FBD
0x180004f9b  movzx   ecx, cx
0x180004f9e  or      ecx, 0C0090000h
0x180004fa4  jmp     short loc_180004FBD
0x180004fa6  xor     ecx, ecx
0x180004fa8  jmp     short loc_180004FBD
0x180004faa  mov     ecx, 0C000A083h
0x180004faf  jmp     short loc_180004FBD
0x180004fb1  mov     ecx, 0C00000E5h
0x180004fb6  jmp     short loc_180004FBD
0x180004fb8  mov     ecx, 0C000042Bh
0x180004fbd  mov     eax, ecx
0x180004fbf  retn
```
