# wil::details::HrToNtStatus(long)

- ea: `0x180009f38`
- end: `0x18000a0f4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000863c`
- `0x1800086dc`
- `0x18000872c`
- `0x1800087e4`
- `0x180009688`
- `0x18000a0fc`

## callees

- `0x180009f38`

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
0x180009f38  mov     eax, 800700EAh
0x180009f3d  cmp     ecx, eax
0x180009f3f  jg      loc_18000A014
0x180009f45  jz      loc_18000A00A
0x180009f4b  mov     eax, 80070057h
0x180009f50  cmp     ecx, eax
0x180009f52  jg      short loc_180009FBE
0x180009f54  jz      short loc_180009FB4
0x180009f56  cmp     ecx, 80004005h
0x180009f5c  jz      short loc_180009FAA
0x180009f5e  cmp     ecx, 80070001h
0x180009f64  jz      short loc_180009FA0
0x180009f66  cmp     ecx, 80070002h
0x180009f6c  jz      short loc_180009F96
0x180009f6e  cmp     ecx, 80070003h
0x180009f74  jz      short loc_180009F8C
0x180009f76  cmp     ecx, 8007000Eh
0x180009f7c  jnz     loc_18000A099
0x180009f82  mov     ecx, 0C0000017h
0x180009f87  jmp     loc_18000A0F1
0x180009f8c  mov     ecx, 0C000003Ah
0x180009f91  jmp     loc_18000A0F1
0x180009f96  mov     ecx, 0C0000034h
0x180009f9b  jmp     loc_18000A0F1
0x180009fa0  mov     ecx, 0C0000002h
0x180009fa5  jmp     loc_18000A0F1
0x180009faa  mov     ecx, 0C0000001h
0x180009faf  jmp     loc_18000A0F1
0x180009fb4  mov     ecx, 0C000000Dh
0x180009fb9  jmp     loc_18000A0F1
0x180009fbe  cmp     ecx, 80070070h
0x180009fc4  jz      short loc_18000A000
0x180009fc6  cmp     ecx, 8007007Ah
0x180009fcc  jz      short loc_180009FF6
0x180009fce  cmp     ecx, 8007007Bh
0x180009fd4  jz      short loc_180009FEC
0x180009fd6  cmp     ecx, 8007007Eh
0x180009fdc  jnz     loc_18000A099
0x180009fe2  mov     ecx, 0C0000135h
0x180009fe7  jmp     loc_18000A0F1
0x180009fec  mov     ecx, 0C0000033h
0x180009ff1  jmp     loc_18000A0F1
0x180009ff6  mov     ecx, 0C0000023h
0x180009ffb  jmp     loc_18000A0F1
0x18000a000  mov     ecx, 0C000007Fh
0x18000a005  jmp     loc_18000A0F1
0x18000a00a  mov     ecx, 80000005h
0x18000a00f  jmp     loc_18000A0F1
0x18000a014  mov     eax, 8007047Eh
0x18000a019  cmp     ecx, eax
0x18000a01b  jg      short loc_18000A07D
0x18000a01d  jz      short loc_18000A076
0x18000a01f  cmp     ecx, 80070216h
0x18000a025  jz      short loc_18000A06F
0x18000a027  cmp     ecx, 8007023Eh
0x18000a02d  jz      short loc_18000A065
0x18000a02f  cmp     ecx, 80070246h
0x18000a035  jz      short loc_18000A05B
0x18000a037  cmp     ecx, 80070247h
0x18000a03d  jz      short loc_18000A051
0x18000a03f  cmp     ecx, 80070272h
0x18000a045  jnz     short loc_18000A099
0x18000a047  mov     ecx, 0C0000273h
0x18000a04c  jmp     loc_18000A0F1
0x18000a051  mov     ecx, 0C0000163h
0x18000a056  jmp     loc_18000A0F1
0x18000a05b  mov     ecx, 0C0000161h
0x18000a060  jmp     loc_18000A0F1
0x18000a065  mov     ecx, 0C0000025h
0x18000a06a  jmp     loc_18000A0F1
0x18000a06f  mov     ecx, 0C0000095h
0x18000a074  jmp     short loc_18000A0F1
0x18000a076  mov     ecx, 0C0000059h
0x18000a07b  jmp     short loc_18000A0F1
0x18000a07d  cmp     ecx, 8007050Ch
0x18000a083  jz      short loc_18000A0EC
0x18000a085  cmp     ecx, 8007054Fh
0x18000a08b  jz      short loc_18000A0E5
0x18000a08d  cmp     ecx, 800705B9h
0x18000a093  jz      short loc_18000A0DE
0x18000a095  test    ecx, ecx
0x18000a097  jz      short loc_18000A0DA
0x18000a099  bt      ecx, 1Ch
0x18000a09d  jnb     short loc_18000A0A5
0x18000a09f  btr     ecx, 1Ch
0x18000a0a3  jmp     short loc_18000A0F1
0x18000a0a5  mov     eax, ecx
0x18000a0a7  and     eax, 1FFF0000h
0x18000a0ac  cmp     eax, 70000h
0x18000a0b1  jnz     short loc_18000A0C4
0x18000a0b3  movzx   ecx, cx
0x18000a0b6  mov     eax, ecx
0x18000a0b8  or      eax, 0C0070000h
0x18000a0bd  test    ecx, ecx
0x18000a0bf  cmovnz  ecx, eax
0x18000a0c2  jmp     short loc_18000A0F1
0x18000a0c4  cmp     eax, 90000h
0x18000a0c9  jnz     short loc_18000A0E5
0x18000a0cb  test    ecx, ecx
0x18000a0cd  jle     short loc_18000A0F1
0x18000a0cf  movzx   ecx, cx
0x18000a0d2  or      ecx, 0C0090000h
0x18000a0d8  jmp     short loc_18000A0F1
0x18000a0da  xor     ecx, ecx
0x18000a0dc  jmp     short loc_18000A0F1
0x18000a0de  mov     ecx, 0C000A083h
0x18000a0e3  jmp     short loc_18000A0F1
0x18000a0e5  mov     ecx, 0C00000E5h
0x18000a0ea  jmp     short loc_18000A0F1
0x18000a0ec  mov     ecx, 0C000042Bh
0x18000a0f1  mov     eax, ecx
0x18000a0f3  retn
```
