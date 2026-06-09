# wil::details::HrToNtStatus(long)

- ea: `0x180005f2c`
- end: `0x1800060e8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030e4`
- `0x1800032bc`
- `0x18000336c`
- `0x1800033c4`
- `0x1800034f0`
- `0x180004bb8`
- `0x1800060f0`
- `0x1800068b0`
- `0x180009e58`
- `0x18000d5f7`
- `0x18000d662`
- `0x18000d72b`
- `0x18000d796`

## callees

- `0x180005f2c`

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
0x180005f2c  mov     eax, 800700EAh
0x180005f31  cmp     ecx, eax
0x180005f33  jg      loc_180006008
0x180005f39  jz      loc_180005FFE
0x180005f3f  mov     eax, 80070057h
0x180005f44  cmp     ecx, eax
0x180005f46  jg      short loc_180005FB2
0x180005f48  jz      short loc_180005FA8
0x180005f4a  cmp     ecx, 80004005h
0x180005f50  jz      short loc_180005F9E
0x180005f52  cmp     ecx, 80070001h
0x180005f58  jz      short loc_180005F94
0x180005f5a  cmp     ecx, 80070002h
0x180005f60  jz      short loc_180005F8A
0x180005f62  cmp     ecx, 80070003h
0x180005f68  jz      short loc_180005F80
0x180005f6a  cmp     ecx, 8007000Eh
0x180005f70  jnz     loc_18000608D
0x180005f76  mov     ecx, 0C0000017h
0x180005f7b  jmp     loc_1800060E5
0x180005f80  mov     ecx, 0C000003Ah
0x180005f85  jmp     loc_1800060E5
0x180005f8a  mov     ecx, 0C0000034h
0x180005f8f  jmp     loc_1800060E5
0x180005f94  mov     ecx, 0C0000002h
0x180005f99  jmp     loc_1800060E5
0x180005f9e  mov     ecx, 0C0000001h
0x180005fa3  jmp     loc_1800060E5
0x180005fa8  mov     ecx, 0C000000Dh
0x180005fad  jmp     loc_1800060E5
0x180005fb2  cmp     ecx, 80070070h
0x180005fb8  jz      short loc_180005FF4
0x180005fba  cmp     ecx, 8007007Ah
0x180005fc0  jz      short loc_180005FEA
0x180005fc2  cmp     ecx, 8007007Bh
0x180005fc8  jz      short loc_180005FE0
0x180005fca  cmp     ecx, 8007007Eh
0x180005fd0  jnz     loc_18000608D
0x180005fd6  mov     ecx, 0C0000135h
0x180005fdb  jmp     loc_1800060E5
0x180005fe0  mov     ecx, 0C0000033h
0x180005fe5  jmp     loc_1800060E5
0x180005fea  mov     ecx, 0C0000023h
0x180005fef  jmp     loc_1800060E5
0x180005ff4  mov     ecx, 0C000007Fh
0x180005ff9  jmp     loc_1800060E5
0x180005ffe  mov     ecx, 80000005h
0x180006003  jmp     loc_1800060E5
0x180006008  mov     eax, 8007047Eh
0x18000600d  cmp     ecx, eax
0x18000600f  jg      short loc_180006071
0x180006011  jz      short loc_18000606A
0x180006013  cmp     ecx, 80070216h
0x180006019  jz      short loc_180006063
0x18000601b  cmp     ecx, 8007023Eh
0x180006021  jz      short loc_180006059
0x180006023  cmp     ecx, 80070246h
0x180006029  jz      short loc_18000604F
0x18000602b  cmp     ecx, 80070247h
0x180006031  jz      short loc_180006045
0x180006033  cmp     ecx, 80070272h
0x180006039  jnz     short loc_18000608D
0x18000603b  mov     ecx, 0C0000273h
0x180006040  jmp     loc_1800060E5
0x180006045  mov     ecx, 0C0000163h
0x18000604a  jmp     loc_1800060E5
0x18000604f  mov     ecx, 0C0000161h
0x180006054  jmp     loc_1800060E5
0x180006059  mov     ecx, 0C0000025h
0x18000605e  jmp     loc_1800060E5
0x180006063  mov     ecx, 0C0000095h
0x180006068  jmp     short loc_1800060E5
0x18000606a  mov     ecx, 0C0000059h
0x18000606f  jmp     short loc_1800060E5
0x180006071  cmp     ecx, 8007050Ch
0x180006077  jz      short loc_1800060E0
0x180006079  cmp     ecx, 8007054Fh
0x18000607f  jz      short loc_1800060D9
0x180006081  cmp     ecx, 800705B9h
0x180006087  jz      short loc_1800060D2
0x180006089  test    ecx, ecx
0x18000608b  jz      short loc_1800060CE
0x18000608d  bt      ecx, 1Ch
0x180006091  jnb     short loc_180006099
0x180006093  btr     ecx, 1Ch
0x180006097  jmp     short loc_1800060E5
0x180006099  mov     eax, ecx
0x18000609b  and     eax, 1FFF0000h
0x1800060a0  cmp     eax, 70000h
0x1800060a5  jnz     short loc_1800060B8
0x1800060a7  movzx   ecx, cx
0x1800060aa  mov     eax, ecx
0x1800060ac  or      eax, 0C0070000h
0x1800060b1  test    ecx, ecx
0x1800060b3  cmovnz  ecx, eax
0x1800060b6  jmp     short loc_1800060E5
0x1800060b8  cmp     eax, 90000h
0x1800060bd  jnz     short loc_1800060D9
0x1800060bf  test    ecx, ecx
0x1800060c1  jle     short loc_1800060E5
0x1800060c3  movzx   ecx, cx
0x1800060c6  or      ecx, 0C0090000h
0x1800060cc  jmp     short loc_1800060E5
0x1800060ce  xor     ecx, ecx
0x1800060d0  jmp     short loc_1800060E5
0x1800060d2  mov     ecx, 0C000A083h
0x1800060d7  jmp     short loc_1800060E5
0x1800060d9  mov     ecx, 0C00000E5h
0x1800060de  jmp     short loc_1800060E5
0x1800060e0  mov     ecx, 0C000042Bh
0x1800060e5  mov     eax, ecx
0x1800060e7  retn
```
