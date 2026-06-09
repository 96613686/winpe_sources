# wil::details::HrToNtStatus(long)

- ea: `0x180004aa0`
- end: `0x180004c5c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f48`
- `0x180002fb8`
- `0x180003030`
- `0x180003080`
- `0x1800040d8`
- `0x180004d34`

## callees

- `0x180004aa0`

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
0x180004aa0  mov     eax, 800700EAh
0x180004aa5  cmp     ecx, eax
0x180004aa7  jg      loc_180004B7C
0x180004aad  jz      loc_180004B72
0x180004ab3  mov     eax, 80070057h
0x180004ab8  cmp     ecx, eax
0x180004aba  jg      short loc_180004B26
0x180004abc  jz      short loc_180004B1C
0x180004abe  cmp     ecx, 80004005h
0x180004ac4  jz      short loc_180004B12
0x180004ac6  cmp     ecx, 80070001h
0x180004acc  jz      short loc_180004B08
0x180004ace  cmp     ecx, 80070002h
0x180004ad4  jz      short loc_180004AFE
0x180004ad6  cmp     ecx, 80070003h
0x180004adc  jz      short loc_180004AF4
0x180004ade  cmp     ecx, 8007000Eh
0x180004ae4  jnz     loc_180004C01
0x180004aea  mov     ecx, 0C0000017h
0x180004aef  jmp     loc_180004C59
0x180004af4  mov     ecx, 0C000003Ah
0x180004af9  jmp     loc_180004C59
0x180004afe  mov     ecx, 0C0000034h
0x180004b03  jmp     loc_180004C59
0x180004b08  mov     ecx, 0C0000002h
0x180004b0d  jmp     loc_180004C59
0x180004b12  mov     ecx, 0C0000001h
0x180004b17  jmp     loc_180004C59
0x180004b1c  mov     ecx, 0C000000Dh
0x180004b21  jmp     loc_180004C59
0x180004b26  cmp     ecx, 80070070h
0x180004b2c  jz      short loc_180004B68
0x180004b2e  cmp     ecx, 8007007Ah
0x180004b34  jz      short loc_180004B5E
0x180004b36  cmp     ecx, 8007007Bh
0x180004b3c  jz      short loc_180004B54
0x180004b3e  cmp     ecx, 8007007Eh
0x180004b44  jnz     loc_180004C01
0x180004b4a  mov     ecx, 0C0000135h
0x180004b4f  jmp     loc_180004C59
0x180004b54  mov     ecx, 0C0000033h
0x180004b59  jmp     loc_180004C59
0x180004b5e  mov     ecx, 0C0000023h
0x180004b63  jmp     loc_180004C59
0x180004b68  mov     ecx, 0C000007Fh
0x180004b6d  jmp     loc_180004C59
0x180004b72  mov     ecx, 80000005h
0x180004b77  jmp     loc_180004C59
0x180004b7c  mov     eax, 8007047Eh
0x180004b81  cmp     ecx, eax
0x180004b83  jg      short loc_180004BE5
0x180004b85  jz      short loc_180004BDE
0x180004b87  cmp     ecx, 80070216h
0x180004b8d  jz      short loc_180004BD7
0x180004b8f  cmp     ecx, 8007023Eh
0x180004b95  jz      short loc_180004BCD
0x180004b97  cmp     ecx, 80070246h
0x180004b9d  jz      short loc_180004BC3
0x180004b9f  cmp     ecx, 80070247h
0x180004ba5  jz      short loc_180004BB9
0x180004ba7  cmp     ecx, 80070272h
0x180004bad  jnz     short loc_180004C01
0x180004baf  mov     ecx, 0C0000273h
0x180004bb4  jmp     loc_180004C59
0x180004bb9  mov     ecx, 0C0000163h
0x180004bbe  jmp     loc_180004C59
0x180004bc3  mov     ecx, 0C0000161h
0x180004bc8  jmp     loc_180004C59
0x180004bcd  mov     ecx, 0C0000025h
0x180004bd2  jmp     loc_180004C59
0x180004bd7  mov     ecx, 0C0000095h
0x180004bdc  jmp     short loc_180004C59
0x180004bde  mov     ecx, 0C0000059h
0x180004be3  jmp     short loc_180004C59
0x180004be5  cmp     ecx, 8007050Ch
0x180004beb  jz      short loc_180004C54
0x180004bed  cmp     ecx, 8007054Fh
0x180004bf3  jz      short loc_180004C4D
0x180004bf5  cmp     ecx, 800705B9h
0x180004bfb  jz      short loc_180004C46
0x180004bfd  test    ecx, ecx
0x180004bff  jz      short loc_180004C42
0x180004c01  bt      ecx, 1Ch
0x180004c05  jnb     short loc_180004C0D
0x180004c07  btr     ecx, 1Ch
0x180004c0b  jmp     short loc_180004C59
0x180004c0d  mov     eax, ecx
0x180004c0f  and     eax, 1FFF0000h
0x180004c14  cmp     eax, 70000h
0x180004c19  jnz     short loc_180004C2C
0x180004c1b  movzx   ecx, cx
0x180004c1e  mov     eax, ecx
0x180004c20  or      eax, 0C0070000h
0x180004c25  test    ecx, ecx
0x180004c27  cmovnz  ecx, eax
0x180004c2a  jmp     short loc_180004C59
0x180004c2c  cmp     eax, 90000h
0x180004c31  jnz     short loc_180004C4D
0x180004c33  test    ecx, ecx
0x180004c35  jle     short loc_180004C59
0x180004c37  movzx   ecx, cx
0x180004c3a  or      ecx, 0C0090000h
0x180004c40  jmp     short loc_180004C59
0x180004c42  xor     ecx, ecx
0x180004c44  jmp     short loc_180004C59
0x180004c46  mov     ecx, 0C000A083h
0x180004c4b  jmp     short loc_180004C59
0x180004c4d  mov     ecx, 0C00000E5h
0x180004c52  jmp     short loc_180004C59
0x180004c54  mov     ecx, 0C000042Bh
0x180004c59  mov     eax, ecx
0x180004c5b  retn
```
