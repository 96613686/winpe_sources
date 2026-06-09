# wil::details::HrToNtStatus(long)

- ea: `0x18000d5a0`
- end: `0x18000d75c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180004db0`
- `0x180004ef4`
- `0x180005058`
- `0x18000521c`
- `0x1800052cc`
- `0x180005324`
- `0x1800053ec`
- `0x180005570`
- `0x18000c358`
- `0x18000de68`
- `0x180010830`
- `0x18001e6c8`
- `0x180020ec6`
- `0x180020f31`
- `0x180020ffa`
- `0x180021065`

## callees

- `0x18000d5a0`

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
0x18000d5a0  mov     eax, 800700EAh
0x18000d5a5  cmp     ecx, eax
0x18000d5a7  jg      loc_18000D67C
0x18000d5ad  jz      loc_18000D672
0x18000d5b3  mov     eax, 80070057h
0x18000d5b8  cmp     ecx, eax
0x18000d5ba  jg      short loc_18000D626
0x18000d5bc  jz      short loc_18000D61C
0x18000d5be  cmp     ecx, 80004005h
0x18000d5c4  jz      short loc_18000D612
0x18000d5c6  cmp     ecx, 80070001h
0x18000d5cc  jz      short loc_18000D608
0x18000d5ce  cmp     ecx, 80070002h
0x18000d5d4  jz      short loc_18000D5FE
0x18000d5d6  cmp     ecx, 80070003h
0x18000d5dc  jz      short loc_18000D5F4
0x18000d5de  cmp     ecx, 8007000Eh
0x18000d5e4  jnz     loc_18000D701
0x18000d5ea  mov     ecx, 0C0000017h
0x18000d5ef  jmp     loc_18000D759
0x18000d5f4  mov     ecx, 0C000003Ah
0x18000d5f9  jmp     loc_18000D759
0x18000d5fe  mov     ecx, 0C0000034h
0x18000d603  jmp     loc_18000D759
0x18000d608  mov     ecx, 0C0000002h
0x18000d60d  jmp     loc_18000D759
0x18000d612  mov     ecx, 0C0000001h
0x18000d617  jmp     loc_18000D759
0x18000d61c  mov     ecx, 0C000000Dh
0x18000d621  jmp     loc_18000D759
0x18000d626  cmp     ecx, 80070070h
0x18000d62c  jz      short loc_18000D668
0x18000d62e  cmp     ecx, 8007007Ah
0x18000d634  jz      short loc_18000D65E
0x18000d636  cmp     ecx, 8007007Bh
0x18000d63c  jz      short loc_18000D654
0x18000d63e  cmp     ecx, 8007007Eh
0x18000d644  jnz     loc_18000D701
0x18000d64a  mov     ecx, 0C0000135h
0x18000d64f  jmp     loc_18000D759
0x18000d654  mov     ecx, 0C0000033h
0x18000d659  jmp     loc_18000D759
0x18000d65e  mov     ecx, 0C0000023h
0x18000d663  jmp     loc_18000D759
0x18000d668  mov     ecx, 0C000007Fh
0x18000d66d  jmp     loc_18000D759
0x18000d672  mov     ecx, 80000005h
0x18000d677  jmp     loc_18000D759
0x18000d67c  mov     eax, 8007047Eh
0x18000d681  cmp     ecx, eax
0x18000d683  jg      short loc_18000D6E5
0x18000d685  jz      short loc_18000D6DE
0x18000d687  cmp     ecx, 80070216h
0x18000d68d  jz      short loc_18000D6D7
0x18000d68f  cmp     ecx, 8007023Eh
0x18000d695  jz      short loc_18000D6CD
0x18000d697  cmp     ecx, 80070246h
0x18000d69d  jz      short loc_18000D6C3
0x18000d69f  cmp     ecx, 80070247h
0x18000d6a5  jz      short loc_18000D6B9
0x18000d6a7  cmp     ecx, 80070272h
0x18000d6ad  jnz     short loc_18000D701
0x18000d6af  mov     ecx, 0C0000273h
0x18000d6b4  jmp     loc_18000D759
0x18000d6b9  mov     ecx, 0C0000163h
0x18000d6be  jmp     loc_18000D759
0x18000d6c3  mov     ecx, 0C0000161h
0x18000d6c8  jmp     loc_18000D759
0x18000d6cd  mov     ecx, 0C0000025h
0x18000d6d2  jmp     loc_18000D759
0x18000d6d7  mov     ecx, 0C0000095h
0x18000d6dc  jmp     short loc_18000D759
0x18000d6de  mov     ecx, 0C0000059h
0x18000d6e3  jmp     short loc_18000D759
0x18000d6e5  cmp     ecx, 8007050Ch
0x18000d6eb  jz      short loc_18000D754
0x18000d6ed  cmp     ecx, 8007054Fh
0x18000d6f3  jz      short loc_18000D74D
0x18000d6f5  cmp     ecx, 800705B9h
0x18000d6fb  jz      short loc_18000D746
0x18000d6fd  test    ecx, ecx
0x18000d6ff  jz      short loc_18000D742
0x18000d701  bt      ecx, 1Ch
0x18000d705  jnb     short loc_18000D70D
0x18000d707  btr     ecx, 1Ch
0x18000d70b  jmp     short loc_18000D759
0x18000d70d  mov     eax, ecx
0x18000d70f  and     eax, 1FFF0000h
0x18000d714  cmp     eax, 70000h
0x18000d719  jnz     short loc_18000D72C
0x18000d71b  movzx   ecx, cx
0x18000d71e  mov     eax, ecx
0x18000d720  or      eax, 0C0070000h
0x18000d725  test    ecx, ecx
0x18000d727  cmovnz  ecx, eax
0x18000d72a  jmp     short loc_18000D759
0x18000d72c  cmp     eax, 90000h
0x18000d731  jnz     short loc_18000D74D
0x18000d733  test    ecx, ecx
0x18000d735  jle     short loc_18000D759
0x18000d737  movzx   ecx, cx
0x18000d73a  or      ecx, 0C0090000h
0x18000d740  jmp     short loc_18000D759
0x18000d742  xor     ecx, ecx
0x18000d744  jmp     short loc_18000D759
0x18000d746  mov     ecx, 0C000A083h
0x18000d74b  jmp     short loc_18000D759
0x18000d74d  mov     ecx, 0C00000E5h
0x18000d752  jmp     short loc_18000D759
0x18000d754  mov     ecx, 0C000042Bh
0x18000d759  mov     eax, ecx
0x18000d75b  retn
```
