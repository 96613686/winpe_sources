# wil::details::HrToNtStatus(long)

- ea: `0x140007908`
- end: `0x140007ac4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140003840`
- `0x14000397c`
- `0x1400039d4`
- `0x140003af8`
- `0x140003c24`
- `0x140006e38`
- `0x140007d88`
- `0x14000e060`
- `0x140010da8`
- `0x140010e84`
- `0x140011688`

## callees

- `0x140007908`

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
0x140007908  mov     eax, 800700EAh
0x14000790d  cmp     ecx, eax
0x14000790f  jg      loc_1400079E4
0x140007915  jz      loc_1400079DA
0x14000791b  mov     eax, 80070057h
0x140007920  cmp     ecx, eax
0x140007922  jg      short loc_14000798E
0x140007924  jz      short loc_140007984
0x140007926  cmp     ecx, 80004005h
0x14000792c  jz      short loc_14000797A
0x14000792e  cmp     ecx, 80070001h
0x140007934  jz      short loc_140007970
0x140007936  cmp     ecx, 80070002h
0x14000793c  jz      short loc_140007966
0x14000793e  cmp     ecx, 80070003h
0x140007944  jz      short loc_14000795C
0x140007946  cmp     ecx, 8007000Eh
0x14000794c  jnz     loc_140007A69
0x140007952  mov     ecx, 0C0000017h
0x140007957  jmp     loc_140007AC1
0x14000795c  mov     ecx, 0C000003Ah
0x140007961  jmp     loc_140007AC1
0x140007966  mov     ecx, 0C0000034h
0x14000796b  jmp     loc_140007AC1
0x140007970  mov     ecx, 0C0000002h
0x140007975  jmp     loc_140007AC1
0x14000797a  mov     ecx, 0C0000001h
0x14000797f  jmp     loc_140007AC1
0x140007984  mov     ecx, 0C000000Dh
0x140007989  jmp     loc_140007AC1
0x14000798e  cmp     ecx, 80070070h
0x140007994  jz      short loc_1400079D0
0x140007996  cmp     ecx, 8007007Ah
0x14000799c  jz      short loc_1400079C6
0x14000799e  cmp     ecx, 8007007Bh
0x1400079a4  jz      short loc_1400079BC
0x1400079a6  cmp     ecx, 8007007Eh
0x1400079ac  jnz     loc_140007A69
0x1400079b2  mov     ecx, 0C0000135h
0x1400079b7  jmp     loc_140007AC1
0x1400079bc  mov     ecx, 0C0000033h
0x1400079c1  jmp     loc_140007AC1
0x1400079c6  mov     ecx, 0C0000023h
0x1400079cb  jmp     loc_140007AC1
0x1400079d0  mov     ecx, 0C000007Fh
0x1400079d5  jmp     loc_140007AC1
0x1400079da  mov     ecx, 80000005h
0x1400079df  jmp     loc_140007AC1
0x1400079e4  mov     eax, 8007047Eh
0x1400079e9  cmp     ecx, eax
0x1400079eb  jg      short loc_140007A4D
0x1400079ed  jz      short loc_140007A46
0x1400079ef  cmp     ecx, 80070216h
0x1400079f5  jz      short loc_140007A3F
0x1400079f7  cmp     ecx, 8007023Eh
0x1400079fd  jz      short loc_140007A35
0x1400079ff  cmp     ecx, 80070246h
0x140007a05  jz      short loc_140007A2B
0x140007a07  cmp     ecx, 80070247h
0x140007a0d  jz      short loc_140007A21
0x140007a0f  cmp     ecx, 80070272h
0x140007a15  jnz     short loc_140007A69
0x140007a17  mov     ecx, 0C0000273h
0x140007a1c  jmp     loc_140007AC1
0x140007a21  mov     ecx, 0C0000163h
0x140007a26  jmp     loc_140007AC1
0x140007a2b  mov     ecx, 0C0000161h
0x140007a30  jmp     loc_140007AC1
0x140007a35  mov     ecx, 0C0000025h
0x140007a3a  jmp     loc_140007AC1
0x140007a3f  mov     ecx, 0C0000095h
0x140007a44  jmp     short loc_140007AC1
0x140007a46  mov     ecx, 0C0000059h
0x140007a4b  jmp     short loc_140007AC1
0x140007a4d  cmp     ecx, 8007050Ch
0x140007a53  jz      short loc_140007ABC
0x140007a55  cmp     ecx, 8007054Fh
0x140007a5b  jz      short loc_140007AB5
0x140007a5d  cmp     ecx, 800705B9h
0x140007a63  jz      short loc_140007AAE
0x140007a65  test    ecx, ecx
0x140007a67  jz      short loc_140007AAA
0x140007a69  bt      ecx, 1Ch
0x140007a6d  jnb     short loc_140007A75
0x140007a6f  btr     ecx, 1Ch
0x140007a73  jmp     short loc_140007AC1
0x140007a75  mov     eax, ecx
0x140007a77  and     eax, 1FFF0000h
0x140007a7c  cmp     eax, 70000h
0x140007a81  jnz     short loc_140007A94
0x140007a83  movzx   ecx, cx
0x140007a86  mov     eax, ecx
0x140007a88  or      eax, 0C0070000h
0x140007a8d  test    ecx, ecx
0x140007a8f  cmovnz  ecx, eax
0x140007a92  jmp     short loc_140007AC1
0x140007a94  cmp     eax, 90000h
0x140007a99  jnz     short loc_140007AB5
0x140007a9b  test    ecx, ecx
0x140007a9d  jle     short loc_140007AC1
0x140007a9f  movzx   ecx, cx
0x140007aa2  or      ecx, 0C0090000h
0x140007aa8  jmp     short loc_140007AC1
0x140007aaa  xor     ecx, ecx
0x140007aac  jmp     short loc_140007AC1
0x140007aae  mov     ecx, 0C000A083h
0x140007ab3  jmp     short loc_140007AC1
0x140007ab5  mov     ecx, 0C00000E5h
0x140007aba  jmp     short loc_140007AC1
0x140007abc  mov     ecx, 0C000042Bh
0x140007ac1  mov     eax, ecx
0x140007ac3  retn
```
