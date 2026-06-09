# wil::details::HrToNtStatus(long)

- ea: `0x180005f3c`
- end: `0x1800060f8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034b4`
- `0x1800035b0`
- `0x1800036b8`
- `0x180003738`
- `0x1800037bc`
- `0x180003814`
- `0x1800052f8`
- `0x180006218`
- `0x180006b30`
- `0x180008828`
- `0x1800088d4`
- `0x180008b24`
- `0x18001005c`
- `0x1800109de`
- `0x180010a29`
- `0x180010aec`
- `0x180010b37`

## callees

- `0x180005f3c`

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
0x180005f3c  mov     eax, 800700EAh
0x180005f41  cmp     ecx, eax
0x180005f43  jg      loc_180006018
0x180005f49  jz      loc_18000600E
0x180005f4f  mov     eax, 80070057h
0x180005f54  cmp     ecx, eax
0x180005f56  jg      short loc_180005FC2
0x180005f58  jz      short loc_180005FB8
0x180005f5a  cmp     ecx, 80004005h
0x180005f60  jz      short loc_180005FAE
0x180005f62  cmp     ecx, 80070001h
0x180005f68  jz      short loc_180005FA4
0x180005f6a  cmp     ecx, 80070002h
0x180005f70  jz      short loc_180005F9A
0x180005f72  cmp     ecx, 80070003h
0x180005f78  jz      short loc_180005F90
0x180005f7a  cmp     ecx, 8007000Eh
0x180005f80  jnz     loc_18000609D
0x180005f86  mov     ecx, 0C0000017h
0x180005f8b  jmp     loc_1800060F5
0x180005f90  mov     ecx, 0C000003Ah
0x180005f95  jmp     loc_1800060F5
0x180005f9a  mov     ecx, 0C0000034h
0x180005f9f  jmp     loc_1800060F5
0x180005fa4  mov     ecx, 0C0000002h
0x180005fa9  jmp     loc_1800060F5
0x180005fae  mov     ecx, 0C0000001h
0x180005fb3  jmp     loc_1800060F5
0x180005fb8  mov     ecx, 0C000000Dh
0x180005fbd  jmp     loc_1800060F5
0x180005fc2  cmp     ecx, 80070070h
0x180005fc8  jz      short loc_180006004
0x180005fca  cmp     ecx, 8007007Ah
0x180005fd0  jz      short loc_180005FFA
0x180005fd2  cmp     ecx, 8007007Bh
0x180005fd8  jz      short loc_180005FF0
0x180005fda  cmp     ecx, 8007007Eh
0x180005fe0  jnz     loc_18000609D
0x180005fe6  mov     ecx, 0C0000135h
0x180005feb  jmp     loc_1800060F5
0x180005ff0  mov     ecx, 0C0000033h
0x180005ff5  jmp     loc_1800060F5
0x180005ffa  mov     ecx, 0C0000023h
0x180005fff  jmp     loc_1800060F5
0x180006004  mov     ecx, 0C000007Fh
0x180006009  jmp     loc_1800060F5
0x18000600e  mov     ecx, 80000005h
0x180006013  jmp     loc_1800060F5
0x180006018  mov     eax, 8007047Eh
0x18000601d  cmp     ecx, eax
0x18000601f  jg      short loc_180006081
0x180006021  jz      short loc_18000607A
0x180006023  cmp     ecx, 80070216h
0x180006029  jz      short loc_180006073
0x18000602b  cmp     ecx, 8007023Eh
0x180006031  jz      short loc_180006069
0x180006033  cmp     ecx, 80070246h
0x180006039  jz      short loc_18000605F
0x18000603b  cmp     ecx, 80070247h
0x180006041  jz      short loc_180006055
0x180006043  cmp     ecx, 80070272h
0x180006049  jnz     short loc_18000609D
0x18000604b  mov     ecx, 0C0000273h
0x180006050  jmp     loc_1800060F5
0x180006055  mov     ecx, 0C0000163h
0x18000605a  jmp     loc_1800060F5
0x18000605f  mov     ecx, 0C0000161h
0x180006064  jmp     loc_1800060F5
0x180006069  mov     ecx, 0C0000025h
0x18000606e  jmp     loc_1800060F5
0x180006073  mov     ecx, 0C0000095h
0x180006078  jmp     short loc_1800060F5
0x18000607a  mov     ecx, 0C0000059h
0x18000607f  jmp     short loc_1800060F5
0x180006081  cmp     ecx, 8007050Ch
0x180006087  jz      short loc_1800060F0
0x180006089  cmp     ecx, 8007054Fh
0x18000608f  jz      short loc_1800060E9
0x180006091  cmp     ecx, 800705B9h
0x180006097  jz      short loc_1800060E2
0x180006099  test    ecx, ecx
0x18000609b  jz      short loc_1800060DE
0x18000609d  bt      ecx, 1Ch
0x1800060a1  jnb     short loc_1800060A9
0x1800060a3  btr     ecx, 1Ch
0x1800060a7  jmp     short loc_1800060F5
0x1800060a9  mov     eax, ecx
0x1800060ab  and     eax, 1FFF0000h
0x1800060b0  cmp     eax, 70000h
0x1800060b5  jnz     short loc_1800060C8
0x1800060b7  movzx   ecx, cx
0x1800060ba  mov     eax, ecx
0x1800060bc  or      eax, 0C0070000h
0x1800060c1  test    ecx, ecx
0x1800060c3  cmovnz  ecx, eax
0x1800060c6  jmp     short loc_1800060F5
0x1800060c8  cmp     eax, 90000h
0x1800060cd  jnz     short loc_1800060E9
0x1800060cf  test    ecx, ecx
0x1800060d1  jle     short loc_1800060F5
0x1800060d3  movzx   ecx, cx
0x1800060d6  or      ecx, 0C0090000h
0x1800060dc  jmp     short loc_1800060F5
0x1800060de  xor     ecx, ecx
0x1800060e0  jmp     short loc_1800060F5
0x1800060e2  mov     ecx, 0C000A083h
0x1800060e7  jmp     short loc_1800060F5
0x1800060e9  mov     ecx, 0C00000E5h
0x1800060ee  jmp     short loc_1800060F5
0x1800060f0  mov     ecx, 0C000042Bh
0x1800060f5  mov     eax, ecx
0x1800060f7  retn
```
