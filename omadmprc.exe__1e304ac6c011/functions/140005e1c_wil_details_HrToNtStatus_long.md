# wil::details::HrToNtStatus(long)

- ea: `0x140005e1c`
- end: `0x140005fd8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140002ed4`
- `0x140002f80`
- `0x140002fd0`
- `0x140003090`
- `0x1400052b4`
- `0x140006158`
- `0x140008380`
- `0x14000d7fc`
- `0x140015991`
- `0x1400159fc`
- `0x140015ac5`
- `0x140015b30`

## callees

- `0x140005e1c`

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
0x140005e1c  mov     eax, 800700EAh
0x140005e21  cmp     ecx, eax
0x140005e23  jg      loc_140005EF8
0x140005e29  jz      loc_140005EEE
0x140005e2f  mov     eax, 80070057h
0x140005e34  cmp     ecx, eax
0x140005e36  jg      short loc_140005EA2
0x140005e38  jz      short loc_140005E98
0x140005e3a  cmp     ecx, 80004005h
0x140005e40  jz      short loc_140005E8E
0x140005e42  cmp     ecx, 80070001h
0x140005e48  jz      short loc_140005E84
0x140005e4a  cmp     ecx, 80070002h
0x140005e50  jz      short loc_140005E7A
0x140005e52  cmp     ecx, 80070003h
0x140005e58  jz      short loc_140005E70
0x140005e5a  cmp     ecx, 8007000Eh
0x140005e60  jnz     loc_140005F7D
0x140005e66  mov     ecx, 0C0000017h
0x140005e6b  jmp     loc_140005FD5
0x140005e70  mov     ecx, 0C000003Ah
0x140005e75  jmp     loc_140005FD5
0x140005e7a  mov     ecx, 0C0000034h
0x140005e7f  jmp     loc_140005FD5
0x140005e84  mov     ecx, 0C0000002h
0x140005e89  jmp     loc_140005FD5
0x140005e8e  mov     ecx, 0C0000001h
0x140005e93  jmp     loc_140005FD5
0x140005e98  mov     ecx, 0C000000Dh
0x140005e9d  jmp     loc_140005FD5
0x140005ea2  cmp     ecx, 80070070h
0x140005ea8  jz      short loc_140005EE4
0x140005eaa  cmp     ecx, 8007007Ah
0x140005eb0  jz      short loc_140005EDA
0x140005eb2  cmp     ecx, 8007007Bh
0x140005eb8  jz      short loc_140005ED0
0x140005eba  cmp     ecx, 8007007Eh
0x140005ec0  jnz     loc_140005F7D
0x140005ec6  mov     ecx, 0C0000135h
0x140005ecb  jmp     loc_140005FD5
0x140005ed0  mov     ecx, 0C0000033h
0x140005ed5  jmp     loc_140005FD5
0x140005eda  mov     ecx, 0C0000023h
0x140005edf  jmp     loc_140005FD5
0x140005ee4  mov     ecx, 0C000007Fh
0x140005ee9  jmp     loc_140005FD5
0x140005eee  mov     ecx, 80000005h
0x140005ef3  jmp     loc_140005FD5
0x140005ef8  mov     eax, 8007047Eh
0x140005efd  cmp     ecx, eax
0x140005eff  jg      short loc_140005F61
0x140005f01  jz      short loc_140005F5A
0x140005f03  cmp     ecx, 80070216h
0x140005f09  jz      short loc_140005F53
0x140005f0b  cmp     ecx, 8007023Eh
0x140005f11  jz      short loc_140005F49
0x140005f13  cmp     ecx, 80070246h
0x140005f19  jz      short loc_140005F3F
0x140005f1b  cmp     ecx, 80070247h
0x140005f21  jz      short loc_140005F35
0x140005f23  cmp     ecx, 80070272h
0x140005f29  jnz     short loc_140005F7D
0x140005f2b  mov     ecx, 0C0000273h
0x140005f30  jmp     loc_140005FD5
0x140005f35  mov     ecx, 0C0000163h
0x140005f3a  jmp     loc_140005FD5
0x140005f3f  mov     ecx, 0C0000161h
0x140005f44  jmp     loc_140005FD5
0x140005f49  mov     ecx, 0C0000025h
0x140005f4e  jmp     loc_140005FD5
0x140005f53  mov     ecx, 0C0000095h
0x140005f58  jmp     short loc_140005FD5
0x140005f5a  mov     ecx, 0C0000059h
0x140005f5f  jmp     short loc_140005FD5
0x140005f61  cmp     ecx, 8007050Ch
0x140005f67  jz      short loc_140005FD0
0x140005f69  cmp     ecx, 8007054Fh
0x140005f6f  jz      short loc_140005FC9
0x140005f71  cmp     ecx, 800705B9h
0x140005f77  jz      short loc_140005FC2
0x140005f79  test    ecx, ecx
0x140005f7b  jz      short loc_140005FBE
0x140005f7d  bt      ecx, 1Ch
0x140005f81  jnb     short loc_140005F89
0x140005f83  btr     ecx, 1Ch
0x140005f87  jmp     short loc_140005FD5
0x140005f89  mov     eax, ecx
0x140005f8b  and     eax, 1FFF0000h
0x140005f90  cmp     eax, 70000h
0x140005f95  jnz     short loc_140005FA8
0x140005f97  movzx   ecx, cx
0x140005f9a  mov     eax, ecx
0x140005f9c  or      eax, 0C0070000h
0x140005fa1  test    ecx, ecx
0x140005fa3  cmovnz  ecx, eax
0x140005fa6  jmp     short loc_140005FD5
0x140005fa8  cmp     eax, 90000h
0x140005fad  jnz     short loc_140005FC9
0x140005faf  test    ecx, ecx
0x140005fb1  jle     short loc_140005FD5
0x140005fb3  movzx   ecx, cx
0x140005fb6  or      ecx, 0C0090000h
0x140005fbc  jmp     short loc_140005FD5
0x140005fbe  xor     ecx, ecx
0x140005fc0  jmp     short loc_140005FD5
0x140005fc2  mov     ecx, 0C000A083h
0x140005fc7  jmp     short loc_140005FD5
0x140005fc9  mov     ecx, 0C00000E5h
0x140005fce  jmp     short loc_140005FD5
0x140005fd0  mov     ecx, 0C000042Bh
0x140005fd5  mov     eax, ecx
0x140005fd7  retn
```
