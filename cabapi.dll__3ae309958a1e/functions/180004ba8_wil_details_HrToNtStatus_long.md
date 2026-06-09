# wil::details::HrToNtStatus(long)

- ea: `0x180004ba8`
- end: `0x180004d64`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025e4`
- `0x180002694`
- `0x1800026e4`
- `0x1800027a4`
- `0x180004128`
- `0x180004d6c`
- `0x18000a8a0`

## callees

- `0x180004ba8`

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
0x180004ba8  mov     eax, 800700EAh
0x180004bad  cmp     ecx, eax
0x180004baf  jg      loc_180004C84
0x180004bb5  jz      loc_180004C7A
0x180004bbb  mov     eax, 80070057h
0x180004bc0  cmp     ecx, eax
0x180004bc2  jg      short loc_180004C2E
0x180004bc4  jz      short loc_180004C24
0x180004bc6  cmp     ecx, 80004005h
0x180004bcc  jz      short loc_180004C1A
0x180004bce  cmp     ecx, 80070001h
0x180004bd4  jz      short loc_180004C10
0x180004bd6  cmp     ecx, 80070002h
0x180004bdc  jz      short loc_180004C06
0x180004bde  cmp     ecx, 80070003h
0x180004be4  jz      short loc_180004BFC
0x180004be6  cmp     ecx, 8007000Eh
0x180004bec  jnz     loc_180004D09
0x180004bf2  mov     ecx, 0C0000017h
0x180004bf7  jmp     loc_180004D61
0x180004bfc  mov     ecx, 0C000003Ah
0x180004c01  jmp     loc_180004D61
0x180004c06  mov     ecx, 0C0000034h
0x180004c0b  jmp     loc_180004D61
0x180004c10  mov     ecx, 0C0000002h
0x180004c15  jmp     loc_180004D61
0x180004c1a  mov     ecx, 0C0000001h
0x180004c1f  jmp     loc_180004D61
0x180004c24  mov     ecx, 0C000000Dh
0x180004c29  jmp     loc_180004D61
0x180004c2e  cmp     ecx, 80070070h
0x180004c34  jz      short loc_180004C70
0x180004c36  cmp     ecx, 8007007Ah
0x180004c3c  jz      short loc_180004C66
0x180004c3e  cmp     ecx, 8007007Bh
0x180004c44  jz      short loc_180004C5C
0x180004c46  cmp     ecx, 8007007Eh
0x180004c4c  jnz     loc_180004D09
0x180004c52  mov     ecx, 0C0000135h
0x180004c57  jmp     loc_180004D61
0x180004c5c  mov     ecx, 0C0000033h
0x180004c61  jmp     loc_180004D61
0x180004c66  mov     ecx, 0C0000023h
0x180004c6b  jmp     loc_180004D61
0x180004c70  mov     ecx, 0C000007Fh
0x180004c75  jmp     loc_180004D61
0x180004c7a  mov     ecx, 80000005h
0x180004c7f  jmp     loc_180004D61
0x180004c84  mov     eax, 8007047Eh
0x180004c89  cmp     ecx, eax
0x180004c8b  jg      short loc_180004CED
0x180004c8d  jz      short loc_180004CE6
0x180004c8f  cmp     ecx, 80070216h
0x180004c95  jz      short loc_180004CDF
0x180004c97  cmp     ecx, 8007023Eh
0x180004c9d  jz      short loc_180004CD5
0x180004c9f  cmp     ecx, 80070246h
0x180004ca5  jz      short loc_180004CCB
0x180004ca7  cmp     ecx, 80070247h
0x180004cad  jz      short loc_180004CC1
0x180004caf  cmp     ecx, 80070272h
0x180004cb5  jnz     short loc_180004D09
0x180004cb7  mov     ecx, 0C0000273h
0x180004cbc  jmp     loc_180004D61
0x180004cc1  mov     ecx, 0C0000163h
0x180004cc6  jmp     loc_180004D61
0x180004ccb  mov     ecx, 0C0000161h
0x180004cd0  jmp     loc_180004D61
0x180004cd5  mov     ecx, 0C0000025h
0x180004cda  jmp     loc_180004D61
0x180004cdf  mov     ecx, 0C0000095h
0x180004ce4  jmp     short loc_180004D61
0x180004ce6  mov     ecx, 0C0000059h
0x180004ceb  jmp     short loc_180004D61
0x180004ced  cmp     ecx, 8007050Ch
0x180004cf3  jz      short loc_180004D5C
0x180004cf5  cmp     ecx, 8007054Fh
0x180004cfb  jz      short loc_180004D55
0x180004cfd  cmp     ecx, 800705B9h
0x180004d03  jz      short loc_180004D4E
0x180004d05  test    ecx, ecx
0x180004d07  jz      short loc_180004D4A
0x180004d09  bt      ecx, 1Ch
0x180004d0d  jnb     short loc_180004D15
0x180004d0f  btr     ecx, 1Ch
0x180004d13  jmp     short loc_180004D61
0x180004d15  mov     eax, ecx
0x180004d17  and     eax, 1FFF0000h
0x180004d1c  cmp     eax, 70000h
0x180004d21  jnz     short loc_180004D34
0x180004d23  movzx   ecx, cx
0x180004d26  mov     eax, ecx
0x180004d28  or      eax, 0C0070000h
0x180004d2d  test    ecx, ecx
0x180004d2f  cmovnz  ecx, eax
0x180004d32  jmp     short loc_180004D61
0x180004d34  cmp     eax, 90000h
0x180004d39  jnz     short loc_180004D55
0x180004d3b  test    ecx, ecx
0x180004d3d  jle     short loc_180004D61
0x180004d3f  movzx   ecx, cx
0x180004d42  or      ecx, 0C0090000h
0x180004d48  jmp     short loc_180004D61
0x180004d4a  xor     ecx, ecx
0x180004d4c  jmp     short loc_180004D61
0x180004d4e  mov     ecx, 0C000A083h
0x180004d53  jmp     short loc_180004D61
0x180004d55  mov     ecx, 0C00000E5h
0x180004d5a  jmp     short loc_180004D61
0x180004d5c  mov     ecx, 0C000042Bh
0x180004d61  mov     eax, ecx
0x180004d63  retn
```
