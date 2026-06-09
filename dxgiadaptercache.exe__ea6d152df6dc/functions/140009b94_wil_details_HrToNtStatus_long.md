# wil::details::HrToNtStatus(long)

- ea: `0x140009b94`
- end: `0x140009d50`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x14000377c`
- `0x1400038d0`
- `0x140003aac`
- `0x140003b5c`
- `0x140003bb4`
- `0x140003cd4`
- `0x1400046c0`
- `0x1400088d8`
- `0x140009ee4`
- `0x14000c730`
- `0x140011800`
- `0x14001186b`
- `0x140011934`
- `0x14001199f`

## callees

- `0x140009b94`

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
0x140009b94  mov     eax, 800700EAh
0x140009b99  cmp     ecx, eax
0x140009b9b  jg      loc_140009C70
0x140009ba1  jz      loc_140009C66
0x140009ba7  mov     eax, 80070057h
0x140009bac  cmp     ecx, eax
0x140009bae  jg      short loc_140009C1A
0x140009bb0  jz      short loc_140009C10
0x140009bb2  cmp     ecx, 80004005h
0x140009bb8  jz      short loc_140009C06
0x140009bba  cmp     ecx, 80070001h
0x140009bc0  jz      short loc_140009BFC
0x140009bc2  cmp     ecx, 80070002h
0x140009bc8  jz      short loc_140009BF2
0x140009bca  cmp     ecx, 80070003h
0x140009bd0  jz      short loc_140009BE8
0x140009bd2  cmp     ecx, 8007000Eh
0x140009bd8  jnz     loc_140009CF5
0x140009bde  mov     ecx, 0C0000017h
0x140009be3  jmp     loc_140009D4D
0x140009be8  mov     ecx, 0C000003Ah
0x140009bed  jmp     loc_140009D4D
0x140009bf2  mov     ecx, 0C0000034h
0x140009bf7  jmp     loc_140009D4D
0x140009bfc  mov     ecx, 0C0000002h
0x140009c01  jmp     loc_140009D4D
0x140009c06  mov     ecx, 0C0000001h
0x140009c0b  jmp     loc_140009D4D
0x140009c10  mov     ecx, 0C000000Dh
0x140009c15  jmp     loc_140009D4D
0x140009c1a  cmp     ecx, 80070070h
0x140009c20  jz      short loc_140009C5C
0x140009c22  cmp     ecx, 8007007Ah
0x140009c28  jz      short loc_140009C52
0x140009c2a  cmp     ecx, 8007007Bh
0x140009c30  jz      short loc_140009C48
0x140009c32  cmp     ecx, 8007007Eh
0x140009c38  jnz     loc_140009CF5
0x140009c3e  mov     ecx, 0C0000135h
0x140009c43  jmp     loc_140009D4D
0x140009c48  mov     ecx, 0C0000033h
0x140009c4d  jmp     loc_140009D4D
0x140009c52  mov     ecx, 0C0000023h
0x140009c57  jmp     loc_140009D4D
0x140009c5c  mov     ecx, 0C000007Fh
0x140009c61  jmp     loc_140009D4D
0x140009c66  mov     ecx, 80000005h
0x140009c6b  jmp     loc_140009D4D
0x140009c70  mov     eax, 8007047Eh
0x140009c75  cmp     ecx, eax
0x140009c77  jg      short loc_140009CD9
0x140009c79  jz      short loc_140009CD2
0x140009c7b  cmp     ecx, 80070216h
0x140009c81  jz      short loc_140009CCB
0x140009c83  cmp     ecx, 8007023Eh
0x140009c89  jz      short loc_140009CC1
0x140009c8b  cmp     ecx, 80070246h
0x140009c91  jz      short loc_140009CB7
0x140009c93  cmp     ecx, 80070247h
0x140009c99  jz      short loc_140009CAD
0x140009c9b  cmp     ecx, 80070272h
0x140009ca1  jnz     short loc_140009CF5
0x140009ca3  mov     ecx, 0C0000273h
0x140009ca8  jmp     loc_140009D4D
0x140009cad  mov     ecx, 0C0000163h
0x140009cb2  jmp     loc_140009D4D
0x140009cb7  mov     ecx, 0C0000161h
0x140009cbc  jmp     loc_140009D4D
0x140009cc1  mov     ecx, 0C0000025h
0x140009cc6  jmp     loc_140009D4D
0x140009ccb  mov     ecx, 0C0000095h
0x140009cd0  jmp     short loc_140009D4D
0x140009cd2  mov     ecx, 0C0000059h
0x140009cd7  jmp     short loc_140009D4D
0x140009cd9  cmp     ecx, 8007050Ch
0x140009cdf  jz      short loc_140009D48
0x140009ce1  cmp     ecx, 8007054Fh
0x140009ce7  jz      short loc_140009D41
0x140009ce9  cmp     ecx, 800705B9h
0x140009cef  jz      short loc_140009D3A
0x140009cf1  test    ecx, ecx
0x140009cf3  jz      short loc_140009D36
0x140009cf5  bt      ecx, 1Ch
0x140009cf9  jnb     short loc_140009D01
0x140009cfb  btr     ecx, 1Ch
0x140009cff  jmp     short loc_140009D4D
0x140009d01  mov     eax, ecx
0x140009d03  and     eax, 1FFF0000h
0x140009d08  cmp     eax, 70000h
0x140009d0d  jnz     short loc_140009D20
0x140009d0f  movzx   ecx, cx
0x140009d12  mov     eax, ecx
0x140009d14  or      eax, 0C0070000h
0x140009d19  test    ecx, ecx
0x140009d1b  cmovnz  ecx, eax
0x140009d1e  jmp     short loc_140009D4D
0x140009d20  cmp     eax, 90000h
0x140009d25  jnz     short loc_140009D41
0x140009d27  test    ecx, ecx
0x140009d29  jle     short loc_140009D4D
0x140009d2b  movzx   ecx, cx
0x140009d2e  or      ecx, 0C0090000h
0x140009d34  jmp     short loc_140009D4D
0x140009d36  xor     ecx, ecx
0x140009d38  jmp     short loc_140009D4D
0x140009d3a  mov     ecx, 0C000A083h
0x140009d3f  jmp     short loc_140009D4D
0x140009d41  mov     ecx, 0C00000E5h
0x140009d46  jmp     short loc_140009D4D
0x140009d48  mov     ecx, 0C000042Bh
0x140009d4d  mov     eax, ecx
0x140009d4f  retn
```
