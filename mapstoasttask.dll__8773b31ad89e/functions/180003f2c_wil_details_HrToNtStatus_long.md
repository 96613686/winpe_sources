# wil::details::HrToNtStatus(long)

- ea: `0x180003f2c`
- end: `0x1800040e8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038b8`
- `0x180004be0`
- `0x180006fe4`
- `0x1800070a4`
- `0x1800075f0`
- `0x180007b34`
- `0x180007bd4`
- `0x18000993e`
- `0x1800099a9`
- `0x180009a72`
- `0x180009add`

## callees

- `0x180003f2c`

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
0x180003f2c  mov     eax, 800700EAh
0x180003f31  cmp     ecx, eax
0x180003f33  jg      loc_180004008
0x180003f39  jz      loc_180003FFE
0x180003f3f  mov     eax, 80070057h
0x180003f44  cmp     ecx, eax
0x180003f46  jg      short loc_180003FB2
0x180003f48  jz      short loc_180003FA8
0x180003f4a  cmp     ecx, 80004005h
0x180003f50  jz      short loc_180003F9E
0x180003f52  cmp     ecx, 80070001h
0x180003f58  jz      short loc_180003F94
0x180003f5a  cmp     ecx, 80070002h
0x180003f60  jz      short loc_180003F8A
0x180003f62  cmp     ecx, 80070003h
0x180003f68  jz      short loc_180003F80
0x180003f6a  cmp     ecx, 8007000Eh
0x180003f70  jnz     loc_18000408D
0x180003f76  mov     ecx, 0C0000017h
0x180003f7b  jmp     loc_1800040E5
0x180003f80  mov     ecx, 0C000003Ah
0x180003f85  jmp     loc_1800040E5
0x180003f8a  mov     ecx, 0C0000034h
0x180003f8f  jmp     loc_1800040E5
0x180003f94  mov     ecx, 0C0000002h
0x180003f99  jmp     loc_1800040E5
0x180003f9e  mov     ecx, 0C0000001h
0x180003fa3  jmp     loc_1800040E5
0x180003fa8  mov     ecx, 0C000000Dh
0x180003fad  jmp     loc_1800040E5
0x180003fb2  cmp     ecx, 80070070h
0x180003fb8  jz      short loc_180003FF4
0x180003fba  cmp     ecx, 8007007Ah
0x180003fc0  jz      short loc_180003FEA
0x180003fc2  cmp     ecx, 8007007Bh
0x180003fc8  jz      short loc_180003FE0
0x180003fca  cmp     ecx, 8007007Eh
0x180003fd0  jnz     loc_18000408D
0x180003fd6  mov     ecx, 0C0000135h
0x180003fdb  jmp     loc_1800040E5
0x180003fe0  mov     ecx, 0C0000033h
0x180003fe5  jmp     loc_1800040E5
0x180003fea  mov     ecx, 0C0000023h
0x180003fef  jmp     loc_1800040E5
0x180003ff4  mov     ecx, 0C000007Fh
0x180003ff9  jmp     loc_1800040E5
0x180003ffe  mov     ecx, 80000005h
0x180004003  jmp     loc_1800040E5
0x180004008  mov     eax, 8007047Eh
0x18000400d  cmp     ecx, eax
0x18000400f  jg      short loc_180004071
0x180004011  jz      short loc_18000406A
0x180004013  cmp     ecx, 80070216h
0x180004019  jz      short loc_180004063
0x18000401b  cmp     ecx, 8007023Eh
0x180004021  jz      short loc_180004059
0x180004023  cmp     ecx, 80070246h
0x180004029  jz      short loc_18000404F
0x18000402b  cmp     ecx, 80070247h
0x180004031  jz      short loc_180004045
0x180004033  cmp     ecx, 80070272h
0x180004039  jnz     short loc_18000408D
0x18000403b  mov     ecx, 0C0000273h
0x180004040  jmp     loc_1800040E5
0x180004045  mov     ecx, 0C0000163h
0x18000404a  jmp     loc_1800040E5
0x18000404f  mov     ecx, 0C0000161h
0x180004054  jmp     loc_1800040E5
0x180004059  mov     ecx, 0C0000025h
0x18000405e  jmp     loc_1800040E5
0x180004063  mov     ecx, 0C0000095h
0x180004068  jmp     short loc_1800040E5
0x18000406a  mov     ecx, 0C0000059h
0x18000406f  jmp     short loc_1800040E5
0x180004071  cmp     ecx, 8007050Ch
0x180004077  jz      short loc_1800040E0
0x180004079  cmp     ecx, 8007054Fh
0x18000407f  jz      short loc_1800040D9
0x180004081  cmp     ecx, 800705B9h
0x180004087  jz      short loc_1800040D2
0x180004089  test    ecx, ecx
0x18000408b  jz      short loc_1800040CE
0x18000408d  bt      ecx, 1Ch
0x180004091  jnb     short loc_180004099
0x180004093  btr     ecx, 1Ch
0x180004097  jmp     short loc_1800040E5
0x180004099  mov     eax, ecx
0x18000409b  and     eax, 1FFF0000h
0x1800040a0  cmp     eax, 70000h
0x1800040a5  jnz     short loc_1800040B8
0x1800040a7  movzx   ecx, cx
0x1800040aa  mov     eax, ecx
0x1800040ac  or      eax, 0C0070000h
0x1800040b1  test    ecx, ecx
0x1800040b3  cmovnz  ecx, eax
0x1800040b6  jmp     short loc_1800040E5
0x1800040b8  cmp     eax, 90000h
0x1800040bd  jnz     short loc_1800040D9
0x1800040bf  test    ecx, ecx
0x1800040c1  jle     short loc_1800040E5
0x1800040c3  movzx   ecx, cx
0x1800040c6  or      ecx, 0C0090000h
0x1800040cc  jmp     short loc_1800040E5
0x1800040ce  xor     ecx, ecx
0x1800040d0  jmp     short loc_1800040E5
0x1800040d2  mov     ecx, 0C000A083h
0x1800040d7  jmp     short loc_1800040E5
0x1800040d9  mov     ecx, 0C00000E5h
0x1800040de  jmp     short loc_1800040E5
0x1800040e0  mov     ecx, 0C000042Bh
0x1800040e5  mov     eax, ecx
0x1800040e7  retn
```
