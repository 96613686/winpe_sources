# wil::details::HrToNtStatus(long)

- ea: `0x18000dd50`
- end: `0x18000df19`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `457`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x18000487c`
- `0x1800049c4`
- `0x180004b14`
- `0x180004cf8`
- `0x180004dc4`
- `0x180004e1c`
- `0x180004ee0`
- `0x180005058`
- `0x180005870`
- `0x18000ccf0`
- `0x180011250`
- `0x18001fa5c`
- `0x1800227ec`
- `0x18002285f`
- `0x180022920`
- `0x180022993`

## callees

- `0x18000dd50`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // edx

  v1 = (unsigned int)this;
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          return (unsigned int)-1073740757;
        case 0x8007054F:
          return (unsigned int)-1073741595;
        case 0x800705B9:
          return (unsigned int)-1073700733;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          return (unsigned int)-1073741735;
        case 0x80070216:
          return (unsigned int)-1073741675;
        case 0x8007023E:
          return (unsigned int)-1073741787;
        case 0x80070246:
          return (unsigned int)-1073741471;
        case 0x80070247:
          return (unsigned int)-1073741469;
        case 0x80070272:
          return (unsigned int)-1073741197;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
      return (unsigned int)-2147483643;
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          return (unsigned int)-1073741697;
        case 0x8007007A:
          return (unsigned int)-1073741789;
        case 0x8007007B:
          return (unsigned int)-1073741773;
        case 0x8007007E:
          return (unsigned int)-1073741515;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          return (unsigned int)-1073741811;
        case 0x80004005:
          return (unsigned int)-1073741823;
        case 0x80070001:
          return (unsigned int)-1073741822;
        case 0x80070002:
          return (unsigned int)-1073741772;
        case 0x80070003:
          return (unsigned int)-1073741766;
        case 0x8007000E:
          return (unsigned int)-1073741801;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
    return (unsigned int)this & 0xEFFFFFFF;
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    v1 = (unsigned __int16)this;
    if ( (_WORD)this )
      return (unsigned __int16)this | 0xC0070000;
    return v1;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
    return (unsigned int)-1073741595;
  if ( (int)this > 0 )
    return (unsigned __int16)this | 0xC0090000;
  return v1;
}

```

## disassembly

```asm
0x18000dd50  mov     eax, 800700EAh
0x18000dd55  mov     edx, ecx
0x18000dd57  cmp     ecx, eax
0x18000dd59  jg      loc_18000DE2E
0x18000dd5f  jz      loc_18000DE24
0x18000dd65  mov     eax, 80070057h
0x18000dd6a  cmp     ecx, eax
0x18000dd6c  jg      short loc_18000DDD8
0x18000dd6e  jz      short loc_18000DDCE
0x18000dd70  cmp     ecx, 80004005h
0x18000dd76  jz      short loc_18000DDC4
0x18000dd78  cmp     ecx, 80070001h
0x18000dd7e  jz      short loc_18000DDBA
0x18000dd80  cmp     ecx, 80070002h
0x18000dd86  jz      short loc_18000DDB0
0x18000dd88  cmp     ecx, 80070003h
0x18000dd8e  jz      short loc_18000DDA6
0x18000dd90  cmp     ecx, 8007000Eh
0x18000dd96  jnz     loc_18000DEB6
0x18000dd9c  mov     edx, 0C0000017h
0x18000dda1  jmp     loc_18000DF16
0x18000dda6  mov     edx, 0C000003Ah
0x18000ddab  jmp     loc_18000DF16
0x18000ddb0  mov     edx, 0C0000034h
0x18000ddb5  jmp     loc_18000DF16
0x18000ddba  mov     edx, 0C0000002h
0x18000ddbf  jmp     loc_18000DF16
0x18000ddc4  mov     edx, 0C0000001h
0x18000ddc9  jmp     loc_18000DF16
0x18000ddce  mov     edx, 0C000000Dh
0x18000ddd3  jmp     loc_18000DF16
0x18000ddd8  cmp     edx, 80070070h
0x18000ddde  jz      short loc_18000DE1A
0x18000dde0  cmp     edx, 8007007Ah
0x18000dde6  jz      short loc_18000DE10
0x18000dde8  cmp     edx, 8007007Bh
0x18000ddee  jz      short loc_18000DE06
0x18000ddf0  cmp     edx, 8007007Eh
0x18000ddf6  jnz     loc_18000DEB6
0x18000ddfc  mov     edx, 0C0000135h
0x18000de01  jmp     loc_18000DF16
0x18000de06  mov     edx, 0C0000033h
0x18000de0b  jmp     loc_18000DF16
0x18000de10  mov     edx, 0C0000023h
0x18000de15  jmp     loc_18000DF16
0x18000de1a  mov     edx, 0C000007Fh
0x18000de1f  jmp     loc_18000DF16
0x18000de24  mov     edx, 80000005h
0x18000de29  jmp     loc_18000DF16
0x18000de2e  mov     eax, 8007047Eh
0x18000de33  cmp     edx, eax
0x18000de35  jg      short loc_18000DE9A
0x18000de37  jz      short loc_18000DE93
0x18000de39  cmp     edx, 80070216h
0x18000de3f  jz      short loc_18000DE89
0x18000de41  cmp     edx, 8007023Eh
0x18000de47  jz      short loc_18000DE7F
0x18000de49  cmp     edx, 80070246h
0x18000de4f  jz      short loc_18000DE75
0x18000de51  cmp     edx, 80070247h
0x18000de57  jz      short loc_18000DE6B
0x18000de59  cmp     edx, 80070272h
0x18000de5f  jnz     short loc_18000DEB6
0x18000de61  mov     edx, 0C0000273h
0x18000de66  jmp     loc_18000DF16
0x18000de6b  mov     edx, 0C0000163h
0x18000de70  jmp     loc_18000DF16
0x18000de75  mov     edx, 0C0000161h
0x18000de7a  jmp     loc_18000DF16
0x18000de7f  mov     edx, 0C0000025h
0x18000de84  jmp     loc_18000DF16
0x18000de89  mov     edx, 0C0000095h
0x18000de8e  jmp     loc_18000DF16
0x18000de93  mov     edx, 0C0000059h
0x18000de98  jmp     short loc_18000DF16
0x18000de9a  cmp     edx, 8007050Ch
0x18000dea0  jz      short loc_18000DF11
0x18000dea2  cmp     edx, 8007054Fh
0x18000dea8  jz      short loc_18000DF0A
0x18000deaa  cmp     edx, 800705B9h
0x18000deb0  jz      short loc_18000DF03
0x18000deb2  test    edx, edx
0x18000deb4  jz      short loc_18000DEFF
0x18000deb6  bt      edx, 1Ch
0x18000deba  jnb     short loc_18000DEC2
0x18000debc  btr     edx, 1Ch
0x18000dec0  jmp     short loc_18000DF16
0x18000dec2  mov     eax, edx
0x18000dec4  mov     ecx, 1FFF0000h
0x18000dec9  and     eax, ecx
0x18000decb  cmp     eax, 70000h
0x18000ded0  jnz     short loc_18000DEE5
0x18000ded2  movzx   ecx, dx
0x18000ded5  mov     eax, ecx
0x18000ded7  mov     edx, ecx
0x18000ded9  or      eax, 0C0070000h
0x18000dede  test    ecx, ecx
0x18000dee0  cmovnz  edx, eax
0x18000dee3  jmp     short loc_18000DF16
0x18000dee5  mov     eax, edx
0x18000dee7  and     eax, ecx
0x18000dee9  cmp     eax, 90000h
0x18000deee  jnz     short loc_18000DF0A
0x18000def0  test    edx, edx
0x18000def2  jle     short loc_18000DF16
0x18000def4  movzx   edx, dx
0x18000def7  or      edx, 0C0090000h
0x18000defd  jmp     short loc_18000DF16
0x18000deff  xor     edx, edx
0x18000df01  jmp     short loc_18000DF16
0x18000df03  mov     edx, 0C000A083h
0x18000df08  jmp     short loc_18000DF16
0x18000df0a  mov     edx, 0C00000E5h
0x18000df0f  jmp     short loc_18000DF16
0x18000df11  mov     edx, 0C000042Bh
0x18000df16  mov     eax, edx
0x18000df18  retn
```
