# wil::details::HrToNtStatus(long)

- ea: `0x180006eb8`
- end: `0x180007074`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ce4`
- `0x180003d84`
- `0x180003dd4`
- `0x180003e94`
- `0x180005fa8`
- `0x180007a74`

## callees

- `0x180006eb8`

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
0x180006eb8  mov     eax, 800700EAh
0x180006ebd  cmp     ecx, eax
0x180006ebf  jg      loc_180006F94
0x180006ec5  jz      loc_180006F8A
0x180006ecb  mov     eax, 80070057h
0x180006ed0  cmp     ecx, eax
0x180006ed2  jg      short loc_180006F3E
0x180006ed4  jz      short loc_180006F34
0x180006ed6  cmp     ecx, 80004005h
0x180006edc  jz      short loc_180006F2A
0x180006ede  cmp     ecx, 80070001h
0x180006ee4  jz      short loc_180006F20
0x180006ee6  cmp     ecx, 80070002h
0x180006eec  jz      short loc_180006F16
0x180006eee  cmp     ecx, 80070003h
0x180006ef4  jz      short loc_180006F0C
0x180006ef6  cmp     ecx, 8007000Eh
0x180006efc  jnz     loc_180007019
0x180006f02  mov     ecx, 0C0000017h
0x180006f07  jmp     loc_180007071
0x180006f0c  mov     ecx, 0C000003Ah
0x180006f11  jmp     loc_180007071
0x180006f16  mov     ecx, 0C0000034h
0x180006f1b  jmp     loc_180007071
0x180006f20  mov     ecx, 0C0000002h
0x180006f25  jmp     loc_180007071
0x180006f2a  mov     ecx, 0C0000001h
0x180006f2f  jmp     loc_180007071
0x180006f34  mov     ecx, 0C000000Dh
0x180006f39  jmp     loc_180007071
0x180006f3e  cmp     ecx, 80070070h
0x180006f44  jz      short loc_180006F80
0x180006f46  cmp     ecx, 8007007Ah
0x180006f4c  jz      short loc_180006F76
0x180006f4e  cmp     ecx, 8007007Bh
0x180006f54  jz      short loc_180006F6C
0x180006f56  cmp     ecx, 8007007Eh
0x180006f5c  jnz     loc_180007019
0x180006f62  mov     ecx, 0C0000135h
0x180006f67  jmp     loc_180007071
0x180006f6c  mov     ecx, 0C0000033h
0x180006f71  jmp     loc_180007071
0x180006f76  mov     ecx, 0C0000023h
0x180006f7b  jmp     loc_180007071
0x180006f80  mov     ecx, 0C000007Fh
0x180006f85  jmp     loc_180007071
0x180006f8a  mov     ecx, 80000005h
0x180006f8f  jmp     loc_180007071
0x180006f94  mov     eax, 8007047Eh
0x180006f99  cmp     ecx, eax
0x180006f9b  jg      short loc_180006FFD
0x180006f9d  jz      short loc_180006FF6
0x180006f9f  cmp     ecx, 80070216h
0x180006fa5  jz      short loc_180006FEF
0x180006fa7  cmp     ecx, 8007023Eh
0x180006fad  jz      short loc_180006FE5
0x180006faf  cmp     ecx, 80070246h
0x180006fb5  jz      short loc_180006FDB
0x180006fb7  cmp     ecx, 80070247h
0x180006fbd  jz      short loc_180006FD1
0x180006fbf  cmp     ecx, 80070272h
0x180006fc5  jnz     short loc_180007019
0x180006fc7  mov     ecx, 0C0000273h
0x180006fcc  jmp     loc_180007071
0x180006fd1  mov     ecx, 0C0000163h
0x180006fd6  jmp     loc_180007071
0x180006fdb  mov     ecx, 0C0000161h
0x180006fe0  jmp     loc_180007071
0x180006fe5  mov     ecx, 0C0000025h
0x180006fea  jmp     loc_180007071
0x180006fef  mov     ecx, 0C0000095h
0x180006ff4  jmp     short loc_180007071
0x180006ff6  mov     ecx, 0C0000059h
0x180006ffb  jmp     short loc_180007071
0x180006ffd  cmp     ecx, 8007050Ch
0x180007003  jz      short loc_18000706C
0x180007005  cmp     ecx, 8007054Fh
0x18000700b  jz      short loc_180007065
0x18000700d  cmp     ecx, 800705B9h
0x180007013  jz      short loc_18000705E
0x180007015  test    ecx, ecx
0x180007017  jz      short loc_18000705A
0x180007019  bt      ecx, 1Ch
0x18000701d  jnb     short loc_180007025
0x18000701f  btr     ecx, 1Ch
0x180007023  jmp     short loc_180007071
0x180007025  mov     eax, ecx
0x180007027  and     eax, 1FFF0000h
0x18000702c  cmp     eax, 70000h
0x180007031  jnz     short loc_180007044
0x180007033  movzx   ecx, cx
0x180007036  mov     eax, ecx
0x180007038  or      eax, 0C0070000h
0x18000703d  test    ecx, ecx
0x18000703f  cmovnz  ecx, eax
0x180007042  jmp     short loc_180007071
0x180007044  cmp     eax, 90000h
0x180007049  jnz     short loc_180007065
0x18000704b  test    ecx, ecx
0x18000704d  jle     short loc_180007071
0x18000704f  movzx   ecx, cx
0x180007052  or      ecx, 0C0090000h
0x180007058  jmp     short loc_180007071
0x18000705a  xor     ecx, ecx
0x18000705c  jmp     short loc_180007071
0x18000705e  mov     ecx, 0C000A083h
0x180007063  jmp     short loc_180007071
0x180007065  mov     ecx, 0C00000E5h
0x18000706a  jmp     short loc_180007071
0x18000706c  mov     ecx, 0C000042Bh
0x180007071  mov     eax, ecx
0x180007073  retn
```
