# wil::details::HrToNtStatus(long)

- ea: `0x180004d88`
- end: `0x180004f44`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d04`
- `0x180005d48`
- `0x180005db8`
- `0x180005e08`
- `0x180006b18`
- `0x180007474`

## callees

- `0x180004d88`

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
0x180004d88  mov     eax, 800700EAh
0x180004d8d  cmp     ecx, eax
0x180004d8f  jg      loc_180004E64
0x180004d95  jz      loc_180004E5A
0x180004d9b  mov     eax, 80070057h
0x180004da0  cmp     ecx, eax
0x180004da2  jg      short loc_180004E0E
0x180004da4  jz      short loc_180004E04
0x180004da6  cmp     ecx, 80004005h
0x180004dac  jz      short loc_180004DFA
0x180004dae  cmp     ecx, 80070001h
0x180004db4  jz      short loc_180004DF0
0x180004db6  cmp     ecx, 80070002h
0x180004dbc  jz      short loc_180004DE6
0x180004dbe  cmp     ecx, 80070003h
0x180004dc4  jz      short loc_180004DDC
0x180004dc6  cmp     ecx, 8007000Eh
0x180004dcc  jnz     loc_180004EE9
0x180004dd2  mov     ecx, 0C0000017h
0x180004dd7  jmp     loc_180004F41
0x180004ddc  mov     ecx, 0C000003Ah
0x180004de1  jmp     loc_180004F41
0x180004de6  mov     ecx, 0C0000034h
0x180004deb  jmp     loc_180004F41
0x180004df0  mov     ecx, 0C0000002h
0x180004df5  jmp     loc_180004F41
0x180004dfa  mov     ecx, 0C0000001h
0x180004dff  jmp     loc_180004F41
0x180004e04  mov     ecx, 0C000000Dh
0x180004e09  jmp     loc_180004F41
0x180004e0e  cmp     ecx, 80070070h
0x180004e14  jz      short loc_180004E50
0x180004e16  cmp     ecx, 8007007Ah
0x180004e1c  jz      short loc_180004E46
0x180004e1e  cmp     ecx, 8007007Bh
0x180004e24  jz      short loc_180004E3C
0x180004e26  cmp     ecx, 8007007Eh
0x180004e2c  jnz     loc_180004EE9
0x180004e32  mov     ecx, 0C0000135h
0x180004e37  jmp     loc_180004F41
0x180004e3c  mov     ecx, 0C0000033h
0x180004e41  jmp     loc_180004F41
0x180004e46  mov     ecx, 0C0000023h
0x180004e4b  jmp     loc_180004F41
0x180004e50  mov     ecx, 0C000007Fh
0x180004e55  jmp     loc_180004F41
0x180004e5a  mov     ecx, 80000005h
0x180004e5f  jmp     loc_180004F41
0x180004e64  mov     eax, 8007047Eh
0x180004e69  cmp     ecx, eax
0x180004e6b  jg      short loc_180004ECD
0x180004e6d  jz      short loc_180004EC6
0x180004e6f  cmp     ecx, 80070216h
0x180004e75  jz      short loc_180004EBF
0x180004e77  cmp     ecx, 8007023Eh
0x180004e7d  jz      short loc_180004EB5
0x180004e7f  cmp     ecx, 80070246h
0x180004e85  jz      short loc_180004EAB
0x180004e87  cmp     ecx, 80070247h
0x180004e8d  jz      short loc_180004EA1
0x180004e8f  cmp     ecx, 80070272h
0x180004e95  jnz     short loc_180004EE9
0x180004e97  mov     ecx, 0C0000273h
0x180004e9c  jmp     loc_180004F41
0x180004ea1  mov     ecx, 0C0000163h
0x180004ea6  jmp     loc_180004F41
0x180004eab  mov     ecx, 0C0000161h
0x180004eb0  jmp     loc_180004F41
0x180004eb5  mov     ecx, 0C0000025h
0x180004eba  jmp     loc_180004F41
0x180004ebf  mov     ecx, 0C0000095h
0x180004ec4  jmp     short loc_180004F41
0x180004ec6  mov     ecx, 0C0000059h
0x180004ecb  jmp     short loc_180004F41
0x180004ecd  cmp     ecx, 8007050Ch
0x180004ed3  jz      short loc_180004F3C
0x180004ed5  cmp     ecx, 8007054Fh
0x180004edb  jz      short loc_180004F35
0x180004edd  cmp     ecx, 800705B9h
0x180004ee3  jz      short loc_180004F2E
0x180004ee5  test    ecx, ecx
0x180004ee7  jz      short loc_180004F2A
0x180004ee9  bt      ecx, 1Ch
0x180004eed  jnb     short loc_180004EF5
0x180004eef  btr     ecx, 1Ch
0x180004ef3  jmp     short loc_180004F41
0x180004ef5  mov     eax, ecx
0x180004ef7  and     eax, 1FFF0000h
0x180004efc  cmp     eax, 70000h
0x180004f01  jnz     short loc_180004F14
0x180004f03  movzx   ecx, cx
0x180004f06  mov     eax, ecx
0x180004f08  or      eax, 0C0070000h
0x180004f0d  test    ecx, ecx
0x180004f0f  cmovnz  ecx, eax
0x180004f12  jmp     short loc_180004F41
0x180004f14  cmp     eax, 90000h
0x180004f19  jnz     short loc_180004F35
0x180004f1b  test    ecx, ecx
0x180004f1d  jle     short loc_180004F41
0x180004f1f  movzx   ecx, cx
0x180004f22  or      ecx, 0C0090000h
0x180004f28  jmp     short loc_180004F41
0x180004f2a  xor     ecx, ecx
0x180004f2c  jmp     short loc_180004F41
0x180004f2e  mov     ecx, 0C000A083h
0x180004f33  jmp     short loc_180004F41
0x180004f35  mov     ecx, 0C00000E5h
0x180004f3a  jmp     short loc_180004F41
0x180004f3c  mov     ecx, 0C000042Bh
0x180004f41  mov     eax, ecx
0x180004f43  retn
```
