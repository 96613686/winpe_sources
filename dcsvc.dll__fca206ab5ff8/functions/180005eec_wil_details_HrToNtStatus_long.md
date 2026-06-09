# wil::details::HrToNtStatus(long)

- ea: `0x180005eec`
- end: `0x1800060a8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003004`
- `0x1800030ac`
- `0x1800030fc`
- `0x1800031bc`
- `0x1800054b8`
- `0x1800062f8`
- `0x18000ea70`

## callees

- `0x180005eec`

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
0x180005eec  mov     eax, 800700EAh
0x180005ef1  cmp     ecx, eax
0x180005ef3  jg      loc_180005FC8
0x180005ef9  jz      loc_180005FBE
0x180005eff  mov     eax, 80070057h
0x180005f04  cmp     ecx, eax
0x180005f06  jg      short loc_180005F72
0x180005f08  jz      short loc_180005F68
0x180005f0a  cmp     ecx, 80004005h
0x180005f10  jz      short loc_180005F5E
0x180005f12  cmp     ecx, 80070001h
0x180005f18  jz      short loc_180005F54
0x180005f1a  cmp     ecx, 80070002h
0x180005f20  jz      short loc_180005F4A
0x180005f22  cmp     ecx, 80070003h
0x180005f28  jz      short loc_180005F40
0x180005f2a  cmp     ecx, 8007000Eh
0x180005f30  jnz     loc_18000604D
0x180005f36  mov     ecx, 0C0000017h
0x180005f3b  jmp     loc_1800060A5
0x180005f40  mov     ecx, 0C000003Ah
0x180005f45  jmp     loc_1800060A5
0x180005f4a  mov     ecx, 0C0000034h
0x180005f4f  jmp     loc_1800060A5
0x180005f54  mov     ecx, 0C0000002h
0x180005f59  jmp     loc_1800060A5
0x180005f5e  mov     ecx, 0C0000001h
0x180005f63  jmp     loc_1800060A5
0x180005f68  mov     ecx, 0C000000Dh
0x180005f6d  jmp     loc_1800060A5
0x180005f72  cmp     ecx, 80070070h
0x180005f78  jz      short loc_180005FB4
0x180005f7a  cmp     ecx, 8007007Ah
0x180005f80  jz      short loc_180005FAA
0x180005f82  cmp     ecx, 8007007Bh
0x180005f88  jz      short loc_180005FA0
0x180005f8a  cmp     ecx, 8007007Eh
0x180005f90  jnz     loc_18000604D
0x180005f96  mov     ecx, 0C0000135h
0x180005f9b  jmp     loc_1800060A5
0x180005fa0  mov     ecx, 0C0000033h
0x180005fa5  jmp     loc_1800060A5
0x180005faa  mov     ecx, 0C0000023h
0x180005faf  jmp     loc_1800060A5
0x180005fb4  mov     ecx, 0C000007Fh
0x180005fb9  jmp     loc_1800060A5
0x180005fbe  mov     ecx, 80000005h
0x180005fc3  jmp     loc_1800060A5
0x180005fc8  mov     eax, 8007047Eh
0x180005fcd  cmp     ecx, eax
0x180005fcf  jg      short loc_180006031
0x180005fd1  jz      short loc_18000602A
0x180005fd3  cmp     ecx, 80070216h
0x180005fd9  jz      short loc_180006023
0x180005fdb  cmp     ecx, 8007023Eh
0x180005fe1  jz      short loc_180006019
0x180005fe3  cmp     ecx, 80070246h
0x180005fe9  jz      short loc_18000600F
0x180005feb  cmp     ecx, 80070247h
0x180005ff1  jz      short loc_180006005
0x180005ff3  cmp     ecx, 80070272h
0x180005ff9  jnz     short loc_18000604D
0x180005ffb  mov     ecx, 0C0000273h
0x180006000  jmp     loc_1800060A5
0x180006005  mov     ecx, 0C0000163h
0x18000600a  jmp     loc_1800060A5
0x18000600f  mov     ecx, 0C0000161h
0x180006014  jmp     loc_1800060A5
0x180006019  mov     ecx, 0C0000025h
0x18000601e  jmp     loc_1800060A5
0x180006023  mov     ecx, 0C0000095h
0x180006028  jmp     short loc_1800060A5
0x18000602a  mov     ecx, 0C0000059h
0x18000602f  jmp     short loc_1800060A5
0x180006031  cmp     ecx, 8007050Ch
0x180006037  jz      short loc_1800060A0
0x180006039  cmp     ecx, 8007054Fh
0x18000603f  jz      short loc_180006099
0x180006041  cmp     ecx, 800705B9h
0x180006047  jz      short loc_180006092
0x180006049  test    ecx, ecx
0x18000604b  jz      short loc_18000608E
0x18000604d  bt      ecx, 1Ch
0x180006051  jnb     short loc_180006059
0x180006053  btr     ecx, 1Ch
0x180006057  jmp     short loc_1800060A5
0x180006059  mov     eax, ecx
0x18000605b  and     eax, 1FFF0000h
0x180006060  cmp     eax, 70000h
0x180006065  jnz     short loc_180006078
0x180006067  movzx   ecx, cx
0x18000606a  mov     eax, ecx
0x18000606c  or      eax, 0C0070000h
0x180006071  test    ecx, ecx
0x180006073  cmovnz  ecx, eax
0x180006076  jmp     short loc_1800060A5
0x180006078  cmp     eax, 90000h
0x18000607d  jnz     short loc_180006099
0x18000607f  test    ecx, ecx
0x180006081  jle     short loc_1800060A5
0x180006083  movzx   ecx, cx
0x180006086  or      ecx, 0C0090000h
0x18000608c  jmp     short loc_1800060A5
0x18000608e  xor     ecx, ecx
0x180006090  jmp     short loc_1800060A5
0x180006092  mov     ecx, 0C000A083h
0x180006097  jmp     short loc_1800060A5
0x180006099  mov     ecx, 0C00000E5h
0x18000609e  jmp     short loc_1800060A5
0x1800060a0  mov     ecx, 0C000042Bh
0x1800060a5  mov     eax, ecx
0x1800060a7  retn
```
