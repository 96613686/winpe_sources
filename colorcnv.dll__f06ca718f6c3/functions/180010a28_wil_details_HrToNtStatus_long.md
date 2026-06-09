# wil::details::HrToNtStatus(long)

- ea: `0x180010a28`
- end: `0x180010be4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f28c`
- `0x18000f2fc`
- `0x18000f374`
- `0x18000f3c4`
- `0x1800100a8`
- `0x180011184`

## callees

- `0x180010a28`

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
0x180010a28  mov     eax, 800700EAh
0x180010a2d  cmp     ecx, eax
0x180010a2f  jg      loc_180010B04
0x180010a35  jz      loc_180010AFA
0x180010a3b  mov     eax, 80070057h
0x180010a40  cmp     ecx, eax
0x180010a42  jg      short loc_180010AAE
0x180010a44  jz      short loc_180010AA4
0x180010a46  cmp     ecx, 80004005h
0x180010a4c  jz      short loc_180010A9A
0x180010a4e  cmp     ecx, 80070001h
0x180010a54  jz      short loc_180010A90
0x180010a56  cmp     ecx, 80070002h
0x180010a5c  jz      short loc_180010A86
0x180010a5e  cmp     ecx, 80070003h
0x180010a64  jz      short loc_180010A7C
0x180010a66  cmp     ecx, 8007000Eh
0x180010a6c  jnz     loc_180010B89
0x180010a72  mov     ecx, 0C0000017h
0x180010a77  jmp     loc_180010BE1
0x180010a7c  mov     ecx, 0C000003Ah
0x180010a81  jmp     loc_180010BE1
0x180010a86  mov     ecx, 0C0000034h
0x180010a8b  jmp     loc_180010BE1
0x180010a90  mov     ecx, 0C0000002h
0x180010a95  jmp     loc_180010BE1
0x180010a9a  mov     ecx, 0C0000001h
0x180010a9f  jmp     loc_180010BE1
0x180010aa4  mov     ecx, 0C000000Dh
0x180010aa9  jmp     loc_180010BE1
0x180010aae  cmp     ecx, 80070070h
0x180010ab4  jz      short loc_180010AF0
0x180010ab6  cmp     ecx, 8007007Ah
0x180010abc  jz      short loc_180010AE6
0x180010abe  cmp     ecx, 8007007Bh
0x180010ac4  jz      short loc_180010ADC
0x180010ac6  cmp     ecx, 8007007Eh
0x180010acc  jnz     loc_180010B89
0x180010ad2  mov     ecx, 0C0000135h
0x180010ad7  jmp     loc_180010BE1
0x180010adc  mov     ecx, 0C0000033h
0x180010ae1  jmp     loc_180010BE1
0x180010ae6  mov     ecx, 0C0000023h
0x180010aeb  jmp     loc_180010BE1
0x180010af0  mov     ecx, 0C000007Fh
0x180010af5  jmp     loc_180010BE1
0x180010afa  mov     ecx, 80000005h
0x180010aff  jmp     loc_180010BE1
0x180010b04  mov     eax, 8007047Eh
0x180010b09  cmp     ecx, eax
0x180010b0b  jg      short loc_180010B6D
0x180010b0d  jz      short loc_180010B66
0x180010b0f  cmp     ecx, 80070216h
0x180010b15  jz      short loc_180010B5F
0x180010b17  cmp     ecx, 8007023Eh
0x180010b1d  jz      short loc_180010B55
0x180010b1f  cmp     ecx, 80070246h
0x180010b25  jz      short loc_180010B4B
0x180010b27  cmp     ecx, 80070247h
0x180010b2d  jz      short loc_180010B41
0x180010b2f  cmp     ecx, 80070272h
0x180010b35  jnz     short loc_180010B89
0x180010b37  mov     ecx, 0C0000273h
0x180010b3c  jmp     loc_180010BE1
0x180010b41  mov     ecx, 0C0000163h
0x180010b46  jmp     loc_180010BE1
0x180010b4b  mov     ecx, 0C0000161h
0x180010b50  jmp     loc_180010BE1
0x180010b55  mov     ecx, 0C0000025h
0x180010b5a  jmp     loc_180010BE1
0x180010b5f  mov     ecx, 0C0000095h
0x180010b64  jmp     short loc_180010BE1
0x180010b66  mov     ecx, 0C0000059h
0x180010b6b  jmp     short loc_180010BE1
0x180010b6d  cmp     ecx, 8007050Ch
0x180010b73  jz      short loc_180010BDC
0x180010b75  cmp     ecx, 8007054Fh
0x180010b7b  jz      short loc_180010BD5
0x180010b7d  cmp     ecx, 800705B9h
0x180010b83  jz      short loc_180010BCE
0x180010b85  test    ecx, ecx
0x180010b87  jz      short loc_180010BCA
0x180010b89  bt      ecx, 1Ch
0x180010b8d  jnb     short loc_180010B95
0x180010b8f  btr     ecx, 1Ch
0x180010b93  jmp     short loc_180010BE1
0x180010b95  mov     eax, ecx
0x180010b97  and     eax, 1FFF0000h
0x180010b9c  cmp     eax, 70000h
0x180010ba1  jnz     short loc_180010BB4
0x180010ba3  movzx   ecx, cx
0x180010ba6  mov     eax, ecx
0x180010ba8  or      eax, 0C0070000h
0x180010bad  test    ecx, ecx
0x180010baf  cmovnz  ecx, eax
0x180010bb2  jmp     short loc_180010BE1
0x180010bb4  cmp     eax, 90000h
0x180010bb9  jnz     short loc_180010BD5
0x180010bbb  test    ecx, ecx
0x180010bbd  jle     short loc_180010BE1
0x180010bbf  movzx   ecx, cx
0x180010bc2  or      ecx, 0C0090000h
0x180010bc8  jmp     short loc_180010BE1
0x180010bca  xor     ecx, ecx
0x180010bcc  jmp     short loc_180010BE1
0x180010bce  mov     ecx, 0C000A083h
0x180010bd3  jmp     short loc_180010BE1
0x180010bd5  mov     ecx, 0C00000E5h
0x180010bda  jmp     short loc_180010BE1
0x180010bdc  mov     ecx, 0C000042Bh
0x180010be1  mov     eax, ecx
0x180010be3  retn
```
