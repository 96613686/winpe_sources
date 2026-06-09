# wil::details::HrToNtStatus(long)

- ea: `0x140004e3c`
- end: `0x140004ff8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140002324`
- `0x140002580`
- `0x140002630`
- `0x140002690`
- `0x1400027b4`
- `0x1400043c8`
- `0x140005000`
- `0x140005820`
- `0x140007a96`
- `0x140007b01`
- `0x140007bca`
- `0x140007c35`

## callees

- `0x140004e3c`

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
0x140004e3c  mov     eax, 800700EAh
0x140004e41  cmp     ecx, eax
0x140004e43  jg      loc_140004F18
0x140004e49  jz      loc_140004F0E
0x140004e4f  mov     eax, 80070057h
0x140004e54  cmp     ecx, eax
0x140004e56  jg      short loc_140004EC2
0x140004e58  jz      short loc_140004EB8
0x140004e5a  cmp     ecx, 80004005h
0x140004e60  jz      short loc_140004EAE
0x140004e62  cmp     ecx, 80070001h
0x140004e68  jz      short loc_140004EA4
0x140004e6a  cmp     ecx, 80070002h
0x140004e70  jz      short loc_140004E9A
0x140004e72  cmp     ecx, 80070003h
0x140004e78  jz      short loc_140004E90
0x140004e7a  cmp     ecx, 8007000Eh
0x140004e80  jnz     loc_140004F9D
0x140004e86  mov     ecx, 0C0000017h
0x140004e8b  jmp     loc_140004FF5
0x140004e90  mov     ecx, 0C000003Ah
0x140004e95  jmp     loc_140004FF5
0x140004e9a  mov     ecx, 0C0000034h
0x140004e9f  jmp     loc_140004FF5
0x140004ea4  mov     ecx, 0C0000002h
0x140004ea9  jmp     loc_140004FF5
0x140004eae  mov     ecx, 0C0000001h
0x140004eb3  jmp     loc_140004FF5
0x140004eb8  mov     ecx, 0C000000Dh
0x140004ebd  jmp     loc_140004FF5
0x140004ec2  cmp     ecx, 80070070h
0x140004ec8  jz      short loc_140004F04
0x140004eca  cmp     ecx, 8007007Ah
0x140004ed0  jz      short loc_140004EFA
0x140004ed2  cmp     ecx, 8007007Bh
0x140004ed8  jz      short loc_140004EF0
0x140004eda  cmp     ecx, 8007007Eh
0x140004ee0  jnz     loc_140004F9D
0x140004ee6  mov     ecx, 0C0000135h
0x140004eeb  jmp     loc_140004FF5
0x140004ef0  mov     ecx, 0C0000033h
0x140004ef5  jmp     loc_140004FF5
0x140004efa  mov     ecx, 0C0000023h
0x140004eff  jmp     loc_140004FF5
0x140004f04  mov     ecx, 0C000007Fh
0x140004f09  jmp     loc_140004FF5
0x140004f0e  mov     ecx, 80000005h
0x140004f13  jmp     loc_140004FF5
0x140004f18  mov     eax, 8007047Eh
0x140004f1d  cmp     ecx, eax
0x140004f1f  jg      short loc_140004F81
0x140004f21  jz      short loc_140004F7A
0x140004f23  cmp     ecx, 80070216h
0x140004f29  jz      short loc_140004F73
0x140004f2b  cmp     ecx, 8007023Eh
0x140004f31  jz      short loc_140004F69
0x140004f33  cmp     ecx, 80070246h
0x140004f39  jz      short loc_140004F5F
0x140004f3b  cmp     ecx, 80070247h
0x140004f41  jz      short loc_140004F55
0x140004f43  cmp     ecx, 80070272h
0x140004f49  jnz     short loc_140004F9D
0x140004f4b  mov     ecx, 0C0000273h
0x140004f50  jmp     loc_140004FF5
0x140004f55  mov     ecx, 0C0000163h
0x140004f5a  jmp     loc_140004FF5
0x140004f5f  mov     ecx, 0C0000161h
0x140004f64  jmp     loc_140004FF5
0x140004f69  mov     ecx, 0C0000025h
0x140004f6e  jmp     loc_140004FF5
0x140004f73  mov     ecx, 0C0000095h
0x140004f78  jmp     short loc_140004FF5
0x140004f7a  mov     ecx, 0C0000059h
0x140004f7f  jmp     short loc_140004FF5
0x140004f81  cmp     ecx, 8007050Ch
0x140004f87  jz      short loc_140004FF0
0x140004f89  cmp     ecx, 8007054Fh
0x140004f8f  jz      short loc_140004FE9
0x140004f91  cmp     ecx, 800705B9h
0x140004f97  jz      short loc_140004FE2
0x140004f99  test    ecx, ecx
0x140004f9b  jz      short loc_140004FDE
0x140004f9d  bt      ecx, 1Ch
0x140004fa1  jnb     short loc_140004FA9
0x140004fa3  btr     ecx, 1Ch
0x140004fa7  jmp     short loc_140004FF5
0x140004fa9  mov     eax, ecx
0x140004fab  and     eax, 1FFF0000h
0x140004fb0  cmp     eax, 70000h
0x140004fb5  jnz     short loc_140004FC8
0x140004fb7  movzx   ecx, cx
0x140004fba  mov     eax, ecx
0x140004fbc  or      eax, 0C0070000h
0x140004fc1  test    ecx, ecx
0x140004fc3  cmovnz  ecx, eax
0x140004fc6  jmp     short loc_140004FF5
0x140004fc8  cmp     eax, 90000h
0x140004fcd  jnz     short loc_140004FE9
0x140004fcf  test    ecx, ecx
0x140004fd1  jle     short loc_140004FF5
0x140004fd3  movzx   ecx, cx
0x140004fd6  or      ecx, 0C0090000h
0x140004fdc  jmp     short loc_140004FF5
0x140004fde  xor     ecx, ecx
0x140004fe0  jmp     short loc_140004FF5
0x140004fe2  mov     ecx, 0C000A083h
0x140004fe7  jmp     short loc_140004FF5
0x140004fe9  mov     ecx, 0C00000E5h
0x140004fee  jmp     short loc_140004FF5
0x140004ff0  mov     ecx, 0C000042Bh
0x140004ff5  mov     eax, ecx
0x140004ff7  retn
```
