# wil::details::HrToNtStatus(long)

- ea: `0x18000513c`
- end: `0x1800052f8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000299c`
- `0x180002a44`
- `0x180002a94`
- `0x180002b54`
- `0x1800046a4`
- `0x180005300`

## callees

- `0x18000513c`

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
0x18000513c  mov     eax, 800700EAh
0x180005141  cmp     ecx, eax
0x180005143  jg      loc_180005218
0x180005149  jz      loc_18000520E
0x18000514f  mov     eax, 80070057h
0x180005154  cmp     ecx, eax
0x180005156  jg      short loc_1800051C2
0x180005158  jz      short loc_1800051B8
0x18000515a  cmp     ecx, 80004005h
0x180005160  jz      short loc_1800051AE
0x180005162  cmp     ecx, 80070001h
0x180005168  jz      short loc_1800051A4
0x18000516a  cmp     ecx, 80070002h
0x180005170  jz      short loc_18000519A
0x180005172  cmp     ecx, 80070003h
0x180005178  jz      short loc_180005190
0x18000517a  cmp     ecx, 8007000Eh
0x180005180  jnz     loc_18000529D
0x180005186  mov     ecx, 0C0000017h
0x18000518b  jmp     loc_1800052F5
0x180005190  mov     ecx, 0C000003Ah
0x180005195  jmp     loc_1800052F5
0x18000519a  mov     ecx, 0C0000034h
0x18000519f  jmp     loc_1800052F5
0x1800051a4  mov     ecx, 0C0000002h
0x1800051a9  jmp     loc_1800052F5
0x1800051ae  mov     ecx, 0C0000001h
0x1800051b3  jmp     loc_1800052F5
0x1800051b8  mov     ecx, 0C000000Dh
0x1800051bd  jmp     loc_1800052F5
0x1800051c2  cmp     ecx, 80070070h
0x1800051c8  jz      short loc_180005204
0x1800051ca  cmp     ecx, 8007007Ah
0x1800051d0  jz      short loc_1800051FA
0x1800051d2  cmp     ecx, 8007007Bh
0x1800051d8  jz      short loc_1800051F0
0x1800051da  cmp     ecx, 8007007Eh
0x1800051e0  jnz     loc_18000529D
0x1800051e6  mov     ecx, 0C0000135h
0x1800051eb  jmp     loc_1800052F5
0x1800051f0  mov     ecx, 0C0000033h
0x1800051f5  jmp     loc_1800052F5
0x1800051fa  mov     ecx, 0C0000023h
0x1800051ff  jmp     loc_1800052F5
0x180005204  mov     ecx, 0C000007Fh
0x180005209  jmp     loc_1800052F5
0x18000520e  mov     ecx, 80000005h
0x180005213  jmp     loc_1800052F5
0x180005218  mov     eax, 8007047Eh
0x18000521d  cmp     ecx, eax
0x18000521f  jg      short loc_180005281
0x180005221  jz      short loc_18000527A
0x180005223  cmp     ecx, 80070216h
0x180005229  jz      short loc_180005273
0x18000522b  cmp     ecx, 8007023Eh
0x180005231  jz      short loc_180005269
0x180005233  cmp     ecx, 80070246h
0x180005239  jz      short loc_18000525F
0x18000523b  cmp     ecx, 80070247h
0x180005241  jz      short loc_180005255
0x180005243  cmp     ecx, 80070272h
0x180005249  jnz     short loc_18000529D
0x18000524b  mov     ecx, 0C0000273h
0x180005250  jmp     loc_1800052F5
0x180005255  mov     ecx, 0C0000163h
0x18000525a  jmp     loc_1800052F5
0x18000525f  mov     ecx, 0C0000161h
0x180005264  jmp     loc_1800052F5
0x180005269  mov     ecx, 0C0000025h
0x18000526e  jmp     loc_1800052F5
0x180005273  mov     ecx, 0C0000095h
0x180005278  jmp     short loc_1800052F5
0x18000527a  mov     ecx, 0C0000059h
0x18000527f  jmp     short loc_1800052F5
0x180005281  cmp     ecx, 8007050Ch
0x180005287  jz      short loc_1800052F0
0x180005289  cmp     ecx, 8007054Fh
0x18000528f  jz      short loc_1800052E9
0x180005291  cmp     ecx, 800705B9h
0x180005297  jz      short loc_1800052E2
0x180005299  test    ecx, ecx
0x18000529b  jz      short loc_1800052DE
0x18000529d  bt      ecx, 1Ch
0x1800052a1  jnb     short loc_1800052A9
0x1800052a3  btr     ecx, 1Ch
0x1800052a7  jmp     short loc_1800052F5
0x1800052a9  mov     eax, ecx
0x1800052ab  and     eax, 1FFF0000h
0x1800052b0  cmp     eax, 70000h
0x1800052b5  jnz     short loc_1800052C8
0x1800052b7  movzx   ecx, cx
0x1800052ba  mov     eax, ecx
0x1800052bc  or      eax, 0C0070000h
0x1800052c1  test    ecx, ecx
0x1800052c3  cmovnz  ecx, eax
0x1800052c6  jmp     short loc_1800052F5
0x1800052c8  cmp     eax, 90000h
0x1800052cd  jnz     short loc_1800052E9
0x1800052cf  test    ecx, ecx
0x1800052d1  jle     short loc_1800052F5
0x1800052d3  movzx   ecx, cx
0x1800052d6  or      ecx, 0C0090000h
0x1800052dc  jmp     short loc_1800052F5
0x1800052de  xor     ecx, ecx
0x1800052e0  jmp     short loc_1800052F5
0x1800052e2  mov     ecx, 0C000A083h
0x1800052e7  jmp     short loc_1800052F5
0x1800052e9  mov     ecx, 0C00000E5h
0x1800052ee  jmp     short loc_1800052F5
0x1800052f0  mov     ecx, 0C000042Bh
0x1800052f5  mov     eax, ecx
0x1800052f7  retn
```
