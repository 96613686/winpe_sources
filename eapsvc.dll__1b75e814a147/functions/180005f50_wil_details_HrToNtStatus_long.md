# wil::details::HrToNtStatus(long)

- ea: `0x180005f50`
- end: `0x18000610c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e74`
- `0x180002f14`
- `0x180002f64`
- `0x180003024`
- `0x180005528`
- `0x180006214`
- `0x1800080f0`
- `0x18000a4e8`
- `0x1800150e4`
- `0x18001514f`
- `0x180015218`
- `0x180015283`

## callees

- `0x180005f50`

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
0x180005f50  mov     eax, 800700EAh
0x180005f55  cmp     ecx, eax
0x180005f57  jg      loc_18000602C
0x180005f5d  jz      loc_180006022
0x180005f63  mov     eax, 80070057h
0x180005f68  cmp     ecx, eax
0x180005f6a  jg      short loc_180005FD6
0x180005f6c  jz      short loc_180005FCC
0x180005f6e  cmp     ecx, 80004005h
0x180005f74  jz      short loc_180005FC2
0x180005f76  cmp     ecx, 80070001h
0x180005f7c  jz      short loc_180005FB8
0x180005f7e  cmp     ecx, 80070002h
0x180005f84  jz      short loc_180005FAE
0x180005f86  cmp     ecx, 80070003h
0x180005f8c  jz      short loc_180005FA4
0x180005f8e  cmp     ecx, 8007000Eh
0x180005f94  jnz     loc_1800060B1
0x180005f9a  mov     ecx, 0C0000017h
0x180005f9f  jmp     loc_180006109
0x180005fa4  mov     ecx, 0C000003Ah
0x180005fa9  jmp     loc_180006109
0x180005fae  mov     ecx, 0C0000034h
0x180005fb3  jmp     loc_180006109
0x180005fb8  mov     ecx, 0C0000002h
0x180005fbd  jmp     loc_180006109
0x180005fc2  mov     ecx, 0C0000001h
0x180005fc7  jmp     loc_180006109
0x180005fcc  mov     ecx, 0C000000Dh
0x180005fd1  jmp     loc_180006109
0x180005fd6  cmp     ecx, 80070070h
0x180005fdc  jz      short loc_180006018
0x180005fde  cmp     ecx, 8007007Ah
0x180005fe4  jz      short loc_18000600E
0x180005fe6  cmp     ecx, 8007007Bh
0x180005fec  jz      short loc_180006004
0x180005fee  cmp     ecx, 8007007Eh
0x180005ff4  jnz     loc_1800060B1
0x180005ffa  mov     ecx, 0C0000135h
0x180005fff  jmp     loc_180006109
0x180006004  mov     ecx, 0C0000033h
0x180006009  jmp     loc_180006109
0x18000600e  mov     ecx, 0C0000023h
0x180006013  jmp     loc_180006109
0x180006018  mov     ecx, 0C000007Fh
0x18000601d  jmp     loc_180006109
0x180006022  mov     ecx, 80000005h
0x180006027  jmp     loc_180006109
0x18000602c  mov     eax, 8007047Eh
0x180006031  cmp     ecx, eax
0x180006033  jg      short loc_180006095
0x180006035  jz      short loc_18000608E
0x180006037  cmp     ecx, 80070216h
0x18000603d  jz      short loc_180006087
0x18000603f  cmp     ecx, 8007023Eh
0x180006045  jz      short loc_18000607D
0x180006047  cmp     ecx, 80070246h
0x18000604d  jz      short loc_180006073
0x18000604f  cmp     ecx, 80070247h
0x180006055  jz      short loc_180006069
0x180006057  cmp     ecx, 80070272h
0x18000605d  jnz     short loc_1800060B1
0x18000605f  mov     ecx, 0C0000273h
0x180006064  jmp     loc_180006109
0x180006069  mov     ecx, 0C0000163h
0x18000606e  jmp     loc_180006109
0x180006073  mov     ecx, 0C0000161h
0x180006078  jmp     loc_180006109
0x18000607d  mov     ecx, 0C0000025h
0x180006082  jmp     loc_180006109
0x180006087  mov     ecx, 0C0000095h
0x18000608c  jmp     short loc_180006109
0x18000608e  mov     ecx, 0C0000059h
0x180006093  jmp     short loc_180006109
0x180006095  cmp     ecx, 8007050Ch
0x18000609b  jz      short loc_180006104
0x18000609d  cmp     ecx, 8007054Fh
0x1800060a3  jz      short loc_1800060FD
0x1800060a5  cmp     ecx, 800705B9h
0x1800060ab  jz      short loc_1800060F6
0x1800060ad  test    ecx, ecx
0x1800060af  jz      short loc_1800060F2
0x1800060b1  bt      ecx, 1Ch
0x1800060b5  jnb     short loc_1800060BD
0x1800060b7  btr     ecx, 1Ch
0x1800060bb  jmp     short loc_180006109
0x1800060bd  mov     eax, ecx
0x1800060bf  and     eax, 1FFF0000h
0x1800060c4  cmp     eax, 70000h
0x1800060c9  jnz     short loc_1800060DC
0x1800060cb  movzx   ecx, cx
0x1800060ce  mov     eax, ecx
0x1800060d0  or      eax, 0C0070000h
0x1800060d5  test    ecx, ecx
0x1800060d7  cmovnz  ecx, eax
0x1800060da  jmp     short loc_180006109
0x1800060dc  cmp     eax, 90000h
0x1800060e1  jnz     short loc_1800060FD
0x1800060e3  test    ecx, ecx
0x1800060e5  jle     short loc_180006109
0x1800060e7  movzx   ecx, cx
0x1800060ea  or      ecx, 0C0090000h
0x1800060f0  jmp     short loc_180006109
0x1800060f2  xor     ecx, ecx
0x1800060f4  jmp     short loc_180006109
0x1800060f6  mov     ecx, 0C000A083h
0x1800060fb  jmp     short loc_180006109
0x1800060fd  mov     ecx, 0C00000E5h
0x180006102  jmp     short loc_180006109
0x180006104  mov     ecx, 0C000042Bh
0x180006109  mov     eax, ecx
0x18000610b  retn
```
