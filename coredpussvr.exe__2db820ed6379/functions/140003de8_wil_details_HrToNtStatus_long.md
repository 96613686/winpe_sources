# wil::details::HrToNtStatus(long)

- ea: `0x140003de8`
- end: `0x140003fa4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002354`
- `0x1400023fc`
- `0x14000244c`
- `0x140002504`
- `0x140003414`
- `0x140003fac`

## callees

- `0x140003de8`

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
0x140003de8  mov     eax, 800700EAh
0x140003ded  cmp     ecx, eax
0x140003def  jg      loc_140003EC4
0x140003df5  jz      loc_140003EBA
0x140003dfb  mov     eax, 80070057h
0x140003e00  cmp     ecx, eax
0x140003e02  jg      short loc_140003E6E
0x140003e04  jz      short loc_140003E64
0x140003e06  cmp     ecx, 80004005h
0x140003e0c  jz      short loc_140003E5A
0x140003e0e  cmp     ecx, 80070001h
0x140003e14  jz      short loc_140003E50
0x140003e16  cmp     ecx, 80070002h
0x140003e1c  jz      short loc_140003E46
0x140003e1e  cmp     ecx, 80070003h
0x140003e24  jz      short loc_140003E3C
0x140003e26  cmp     ecx, 8007000Eh
0x140003e2c  jnz     loc_140003F49
0x140003e32  mov     ecx, 0C0000017h
0x140003e37  jmp     loc_140003FA1
0x140003e3c  mov     ecx, 0C000003Ah
0x140003e41  jmp     loc_140003FA1
0x140003e46  mov     ecx, 0C0000034h
0x140003e4b  jmp     loc_140003FA1
0x140003e50  mov     ecx, 0C0000002h
0x140003e55  jmp     loc_140003FA1
0x140003e5a  mov     ecx, 0C0000001h
0x140003e5f  jmp     loc_140003FA1
0x140003e64  mov     ecx, 0C000000Dh
0x140003e69  jmp     loc_140003FA1
0x140003e6e  cmp     ecx, 80070070h
0x140003e74  jz      short loc_140003EB0
0x140003e76  cmp     ecx, 8007007Ah
0x140003e7c  jz      short loc_140003EA6
0x140003e7e  cmp     ecx, 8007007Bh
0x140003e84  jz      short loc_140003E9C
0x140003e86  cmp     ecx, 8007007Eh
0x140003e8c  jnz     loc_140003F49
0x140003e92  mov     ecx, 0C0000135h
0x140003e97  jmp     loc_140003FA1
0x140003e9c  mov     ecx, 0C0000033h
0x140003ea1  jmp     loc_140003FA1
0x140003ea6  mov     ecx, 0C0000023h
0x140003eab  jmp     loc_140003FA1
0x140003eb0  mov     ecx, 0C000007Fh
0x140003eb5  jmp     loc_140003FA1
0x140003eba  mov     ecx, 80000005h
0x140003ebf  jmp     loc_140003FA1
0x140003ec4  mov     eax, 8007047Eh
0x140003ec9  cmp     ecx, eax
0x140003ecb  jg      short loc_140003F2D
0x140003ecd  jz      short loc_140003F26
0x140003ecf  cmp     ecx, 80070216h
0x140003ed5  jz      short loc_140003F1F
0x140003ed7  cmp     ecx, 8007023Eh
0x140003edd  jz      short loc_140003F15
0x140003edf  cmp     ecx, 80070246h
0x140003ee5  jz      short loc_140003F0B
0x140003ee7  cmp     ecx, 80070247h
0x140003eed  jz      short loc_140003F01
0x140003eef  cmp     ecx, 80070272h
0x140003ef5  jnz     short loc_140003F49
0x140003ef7  mov     ecx, 0C0000273h
0x140003efc  jmp     loc_140003FA1
0x140003f01  mov     ecx, 0C0000163h
0x140003f06  jmp     loc_140003FA1
0x140003f0b  mov     ecx, 0C0000161h
0x140003f10  jmp     loc_140003FA1
0x140003f15  mov     ecx, 0C0000025h
0x140003f1a  jmp     loc_140003FA1
0x140003f1f  mov     ecx, 0C0000095h
0x140003f24  jmp     short loc_140003FA1
0x140003f26  mov     ecx, 0C0000059h
0x140003f2b  jmp     short loc_140003FA1
0x140003f2d  cmp     ecx, 8007050Ch
0x140003f33  jz      short loc_140003F9C
0x140003f35  cmp     ecx, 8007054Fh
0x140003f3b  jz      short loc_140003F95
0x140003f3d  cmp     ecx, 800705B9h
0x140003f43  jz      short loc_140003F8E
0x140003f45  test    ecx, ecx
0x140003f47  jz      short loc_140003F8A
0x140003f49  bt      ecx, 1Ch
0x140003f4d  jnb     short loc_140003F55
0x140003f4f  btr     ecx, 1Ch
0x140003f53  jmp     short loc_140003FA1
0x140003f55  mov     eax, ecx
0x140003f57  and     eax, 1FFF0000h
0x140003f5c  cmp     eax, 70000h
0x140003f61  jnz     short loc_140003F74
0x140003f63  movzx   ecx, cx
0x140003f66  mov     eax, ecx
0x140003f68  or      eax, 0C0070000h
0x140003f6d  test    ecx, ecx
0x140003f6f  cmovnz  ecx, eax
0x140003f72  jmp     short loc_140003FA1
0x140003f74  cmp     eax, 90000h
0x140003f79  jnz     short loc_140003F95
0x140003f7b  test    ecx, ecx
0x140003f7d  jle     short loc_140003FA1
0x140003f7f  movzx   ecx, cx
0x140003f82  or      ecx, 0C0090000h
0x140003f88  jmp     short loc_140003FA1
0x140003f8a  xor     ecx, ecx
0x140003f8c  jmp     short loc_140003FA1
0x140003f8e  mov     ecx, 0C000A083h
0x140003f93  jmp     short loc_140003FA1
0x140003f95  mov     ecx, 0C00000E5h
0x140003f9a  jmp     short loc_140003FA1
0x140003f9c  mov     ecx, 0C000042Bh
0x140003fa1  mov     eax, ecx
0x140003fa3  retn
```
