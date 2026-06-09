# wil::details::HrToNtStatus(long)

- ea: `0x180004764`
- end: `0x180004920`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ec8`
- `0x180002f40`
- `0x180002fbc`
- `0x18000300c`
- `0x180003e08`
- `0x180004afc`
- `0x180005360`
- `0x180006608`
- `0x1800066e0`
- `0x18000691c`
- `0x180006984`
- `0x1800080ec`
- `0x1800093a6`
- `0x1800093f1`
- `0x1800094b4`
- `0x1800094ff`

## callees

- `0x180004764`

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
0x180004764  mov     eax, 800700EAh
0x180004769  cmp     ecx, eax
0x18000476b  jg      loc_180004840
0x180004771  jz      loc_180004836
0x180004777  mov     eax, 80070057h
0x18000477c  cmp     ecx, eax
0x18000477e  jg      short loc_1800047EA
0x180004780  jz      short loc_1800047E0
0x180004782  cmp     ecx, 80004005h
0x180004788  jz      short loc_1800047D6
0x18000478a  cmp     ecx, 80070001h
0x180004790  jz      short loc_1800047CC
0x180004792  cmp     ecx, 80070002h
0x180004798  jz      short loc_1800047C2
0x18000479a  cmp     ecx, 80070003h
0x1800047a0  jz      short loc_1800047B8
0x1800047a2  cmp     ecx, 8007000Eh
0x1800047a8  jnz     loc_1800048C5
0x1800047ae  mov     ecx, 0C0000017h
0x1800047b3  jmp     loc_18000491D
0x1800047b8  mov     ecx, 0C000003Ah
0x1800047bd  jmp     loc_18000491D
0x1800047c2  mov     ecx, 0C0000034h
0x1800047c7  jmp     loc_18000491D
0x1800047cc  mov     ecx, 0C0000002h
0x1800047d1  jmp     loc_18000491D
0x1800047d6  mov     ecx, 0C0000001h
0x1800047db  jmp     loc_18000491D
0x1800047e0  mov     ecx, 0C000000Dh
0x1800047e5  jmp     loc_18000491D
0x1800047ea  cmp     ecx, 80070070h
0x1800047f0  jz      short loc_18000482C
0x1800047f2  cmp     ecx, 8007007Ah
0x1800047f8  jz      short loc_180004822
0x1800047fa  cmp     ecx, 8007007Bh
0x180004800  jz      short loc_180004818
0x180004802  cmp     ecx, 8007007Eh
0x180004808  jnz     loc_1800048C5
0x18000480e  mov     ecx, 0C0000135h
0x180004813  jmp     loc_18000491D
0x180004818  mov     ecx, 0C0000033h
0x18000481d  jmp     loc_18000491D
0x180004822  mov     ecx, 0C0000023h
0x180004827  jmp     loc_18000491D
0x18000482c  mov     ecx, 0C000007Fh
0x180004831  jmp     loc_18000491D
0x180004836  mov     ecx, 80000005h
0x18000483b  jmp     loc_18000491D
0x180004840  mov     eax, 8007047Eh
0x180004845  cmp     ecx, eax
0x180004847  jg      short loc_1800048A9
0x180004849  jz      short loc_1800048A2
0x18000484b  cmp     ecx, 80070216h
0x180004851  jz      short loc_18000489B
0x180004853  cmp     ecx, 8007023Eh
0x180004859  jz      short loc_180004891
0x18000485b  cmp     ecx, 80070246h
0x180004861  jz      short loc_180004887
0x180004863  cmp     ecx, 80070247h
0x180004869  jz      short loc_18000487D
0x18000486b  cmp     ecx, 80070272h
0x180004871  jnz     short loc_1800048C5
0x180004873  mov     ecx, 0C0000273h
0x180004878  jmp     loc_18000491D
0x18000487d  mov     ecx, 0C0000163h
0x180004882  jmp     loc_18000491D
0x180004887  mov     ecx, 0C0000161h
0x18000488c  jmp     loc_18000491D
0x180004891  mov     ecx, 0C0000025h
0x180004896  jmp     loc_18000491D
0x18000489b  mov     ecx, 0C0000095h
0x1800048a0  jmp     short loc_18000491D
0x1800048a2  mov     ecx, 0C0000059h
0x1800048a7  jmp     short loc_18000491D
0x1800048a9  cmp     ecx, 8007050Ch
0x1800048af  jz      short loc_180004918
0x1800048b1  cmp     ecx, 8007054Fh
0x1800048b7  jz      short loc_180004911
0x1800048b9  cmp     ecx, 800705B9h
0x1800048bf  jz      short loc_18000490A
0x1800048c1  test    ecx, ecx
0x1800048c3  jz      short loc_180004906
0x1800048c5  bt      ecx, 1Ch
0x1800048c9  jnb     short loc_1800048D1
0x1800048cb  btr     ecx, 1Ch
0x1800048cf  jmp     short loc_18000491D
0x1800048d1  mov     eax, ecx
0x1800048d3  and     eax, 1FFF0000h
0x1800048d8  cmp     eax, 70000h
0x1800048dd  jnz     short loc_1800048F0
0x1800048df  movzx   ecx, cx
0x1800048e2  mov     eax, ecx
0x1800048e4  or      eax, 0C0070000h
0x1800048e9  test    ecx, ecx
0x1800048eb  cmovnz  ecx, eax
0x1800048ee  jmp     short loc_18000491D
0x1800048f0  cmp     eax, 90000h
0x1800048f5  jnz     short loc_180004911
0x1800048f7  test    ecx, ecx
0x1800048f9  jle     short loc_18000491D
0x1800048fb  movzx   ecx, cx
0x1800048fe  or      ecx, 0C0090000h
0x180004904  jmp     short loc_18000491D
0x180004906  xor     ecx, ecx
0x180004908  jmp     short loc_18000491D
0x18000490a  mov     ecx, 0C000A083h
0x18000490f  jmp     short loc_18000491D
0x180004911  mov     ecx, 0C00000E5h
0x180004916  jmp     short loc_18000491D
0x180004918  mov     ecx, 0C000042Bh
0x18000491d  mov     eax, ecx
0x18000491f  retn
```
