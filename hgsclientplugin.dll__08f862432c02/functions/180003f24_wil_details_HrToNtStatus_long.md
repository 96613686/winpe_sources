# wil::details::HrToNtStatus(long)

- ea: `0x180003f24`
- end: `0x1800040e0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021a4`
- `0x180002254`
- `0x1800022ac`
- `0x180002374`
- `0x1800034f8`
- `0x1800040e8`
- `0x180004870`
- `0x180007080`
- `0x180007234`
- `0x180009aa4`
- `0x18000aace`
- `0x18000ab39`
- `0x18000ac02`
- `0x18000ac6d`

## callees

- `0x180003f24`

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
0x180003f24  mov     eax, 800700EAh
0x180003f29  cmp     ecx, eax
0x180003f2b  jg      loc_180004000
0x180003f31  jz      loc_180003FF6
0x180003f37  mov     eax, 80070057h
0x180003f3c  cmp     ecx, eax
0x180003f3e  jg      short loc_180003FAA
0x180003f40  jz      short loc_180003FA0
0x180003f42  cmp     ecx, 80004005h
0x180003f48  jz      short loc_180003F96
0x180003f4a  cmp     ecx, 80070001h
0x180003f50  jz      short loc_180003F8C
0x180003f52  cmp     ecx, 80070002h
0x180003f58  jz      short loc_180003F82
0x180003f5a  cmp     ecx, 80070003h
0x180003f60  jz      short loc_180003F78
0x180003f62  cmp     ecx, 8007000Eh
0x180003f68  jnz     loc_180004085
0x180003f6e  mov     ecx, 0C0000017h
0x180003f73  jmp     loc_1800040DD
0x180003f78  mov     ecx, 0C000003Ah
0x180003f7d  jmp     loc_1800040DD
0x180003f82  mov     ecx, 0C0000034h
0x180003f87  jmp     loc_1800040DD
0x180003f8c  mov     ecx, 0C0000002h
0x180003f91  jmp     loc_1800040DD
0x180003f96  mov     ecx, 0C0000001h
0x180003f9b  jmp     loc_1800040DD
0x180003fa0  mov     ecx, 0C000000Dh
0x180003fa5  jmp     loc_1800040DD
0x180003faa  cmp     ecx, 80070070h
0x180003fb0  jz      short loc_180003FEC
0x180003fb2  cmp     ecx, 8007007Ah
0x180003fb8  jz      short loc_180003FE2
0x180003fba  cmp     ecx, 8007007Bh
0x180003fc0  jz      short loc_180003FD8
0x180003fc2  cmp     ecx, 8007007Eh
0x180003fc8  jnz     loc_180004085
0x180003fce  mov     ecx, 0C0000135h
0x180003fd3  jmp     loc_1800040DD
0x180003fd8  mov     ecx, 0C0000033h
0x180003fdd  jmp     loc_1800040DD
0x180003fe2  mov     ecx, 0C0000023h
0x180003fe7  jmp     loc_1800040DD
0x180003fec  mov     ecx, 0C000007Fh
0x180003ff1  jmp     loc_1800040DD
0x180003ff6  mov     ecx, 80000005h
0x180003ffb  jmp     loc_1800040DD
0x180004000  mov     eax, 8007047Eh
0x180004005  cmp     ecx, eax
0x180004007  jg      short loc_180004069
0x180004009  jz      short loc_180004062
0x18000400b  cmp     ecx, 80070216h
0x180004011  jz      short loc_18000405B
0x180004013  cmp     ecx, 8007023Eh
0x180004019  jz      short loc_180004051
0x18000401b  cmp     ecx, 80070246h
0x180004021  jz      short loc_180004047
0x180004023  cmp     ecx, 80070247h
0x180004029  jz      short loc_18000403D
0x18000402b  cmp     ecx, 80070272h
0x180004031  jnz     short loc_180004085
0x180004033  mov     ecx, 0C0000273h
0x180004038  jmp     loc_1800040DD
0x18000403d  mov     ecx, 0C0000163h
0x180004042  jmp     loc_1800040DD
0x180004047  mov     ecx, 0C0000161h
0x18000404c  jmp     loc_1800040DD
0x180004051  mov     ecx, 0C0000025h
0x180004056  jmp     loc_1800040DD
0x18000405b  mov     ecx, 0C0000095h
0x180004060  jmp     short loc_1800040DD
0x180004062  mov     ecx, 0C0000059h
0x180004067  jmp     short loc_1800040DD
0x180004069  cmp     ecx, 8007050Ch
0x18000406f  jz      short loc_1800040D8
0x180004071  cmp     ecx, 8007054Fh
0x180004077  jz      short loc_1800040D1
0x180004079  cmp     ecx, 800705B9h
0x18000407f  jz      short loc_1800040CA
0x180004081  test    ecx, ecx
0x180004083  jz      short loc_1800040C6
0x180004085  bt      ecx, 1Ch
0x180004089  jnb     short loc_180004091
0x18000408b  btr     ecx, 1Ch
0x18000408f  jmp     short loc_1800040DD
0x180004091  mov     eax, ecx
0x180004093  and     eax, 1FFF0000h
0x180004098  cmp     eax, 70000h
0x18000409d  jnz     short loc_1800040B0
0x18000409f  movzx   ecx, cx
0x1800040a2  mov     eax, ecx
0x1800040a4  or      eax, 0C0070000h
0x1800040a9  test    ecx, ecx
0x1800040ab  cmovnz  ecx, eax
0x1800040ae  jmp     short loc_1800040DD
0x1800040b0  cmp     eax, 90000h
0x1800040b5  jnz     short loc_1800040D1
0x1800040b7  test    ecx, ecx
0x1800040b9  jle     short loc_1800040DD
0x1800040bb  movzx   ecx, cx
0x1800040be  or      ecx, 0C0090000h
0x1800040c4  jmp     short loc_1800040DD
0x1800040c6  xor     ecx, ecx
0x1800040c8  jmp     short loc_1800040DD
0x1800040ca  mov     ecx, 0C000A083h
0x1800040cf  jmp     short loc_1800040DD
0x1800040d1  mov     ecx, 0C00000E5h
0x1800040d6  jmp     short loc_1800040DD
0x1800040d8  mov     ecx, 0C000042Bh
0x1800040dd  mov     eax, ecx
0x1800040df  retn
```
