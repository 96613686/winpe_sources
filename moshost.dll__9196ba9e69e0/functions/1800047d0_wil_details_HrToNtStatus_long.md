# wil::details::HrToNtStatus(long)

- ea: `0x1800047d0`
- end: `0x18000498c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ae0`
- `0x180002b80`
- `0x180002bd0`
- `0x180002c90`
- `0x180003da8`
- `0x180004994`
- `0x180005110`
- `0x18000c96f`
- `0x18000c9da`
- `0x18000caa3`
- `0x18000cb0e`

## callees

- `0x1800047d0`

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
0x1800047d0  mov     eax, 800700EAh
0x1800047d5  cmp     ecx, eax
0x1800047d7  jg      loc_1800048AC
0x1800047dd  jz      loc_1800048A2
0x1800047e3  mov     eax, 80070057h
0x1800047e8  cmp     ecx, eax
0x1800047ea  jg      short loc_180004856
0x1800047ec  jz      short loc_18000484C
0x1800047ee  cmp     ecx, 80004005h
0x1800047f4  jz      short loc_180004842
0x1800047f6  cmp     ecx, 80070001h
0x1800047fc  jz      short loc_180004838
0x1800047fe  cmp     ecx, 80070002h
0x180004804  jz      short loc_18000482E
0x180004806  cmp     ecx, 80070003h
0x18000480c  jz      short loc_180004824
0x18000480e  cmp     ecx, 8007000Eh
0x180004814  jnz     loc_180004931
0x18000481a  mov     ecx, 0C0000017h
0x18000481f  jmp     loc_180004989
0x180004824  mov     ecx, 0C000003Ah
0x180004829  jmp     loc_180004989
0x18000482e  mov     ecx, 0C0000034h
0x180004833  jmp     loc_180004989
0x180004838  mov     ecx, 0C0000002h
0x18000483d  jmp     loc_180004989
0x180004842  mov     ecx, 0C0000001h
0x180004847  jmp     loc_180004989
0x18000484c  mov     ecx, 0C000000Dh
0x180004851  jmp     loc_180004989
0x180004856  cmp     ecx, 80070070h
0x18000485c  jz      short loc_180004898
0x18000485e  cmp     ecx, 8007007Ah
0x180004864  jz      short loc_18000488E
0x180004866  cmp     ecx, 8007007Bh
0x18000486c  jz      short loc_180004884
0x18000486e  cmp     ecx, 8007007Eh
0x180004874  jnz     loc_180004931
0x18000487a  mov     ecx, 0C0000135h
0x18000487f  jmp     loc_180004989
0x180004884  mov     ecx, 0C0000033h
0x180004889  jmp     loc_180004989
0x18000488e  mov     ecx, 0C0000023h
0x180004893  jmp     loc_180004989
0x180004898  mov     ecx, 0C000007Fh
0x18000489d  jmp     loc_180004989
0x1800048a2  mov     ecx, 80000005h
0x1800048a7  jmp     loc_180004989
0x1800048ac  mov     eax, 8007047Eh
0x1800048b1  cmp     ecx, eax
0x1800048b3  jg      short loc_180004915
0x1800048b5  jz      short loc_18000490E
0x1800048b7  cmp     ecx, 80070216h
0x1800048bd  jz      short loc_180004907
0x1800048bf  cmp     ecx, 8007023Eh
0x1800048c5  jz      short loc_1800048FD
0x1800048c7  cmp     ecx, 80070246h
0x1800048cd  jz      short loc_1800048F3
0x1800048cf  cmp     ecx, 80070247h
0x1800048d5  jz      short loc_1800048E9
0x1800048d7  cmp     ecx, 80070272h
0x1800048dd  jnz     short loc_180004931
0x1800048df  mov     ecx, 0C0000273h
0x1800048e4  jmp     loc_180004989
0x1800048e9  mov     ecx, 0C0000163h
0x1800048ee  jmp     loc_180004989
0x1800048f3  mov     ecx, 0C0000161h
0x1800048f8  jmp     loc_180004989
0x1800048fd  mov     ecx, 0C0000025h
0x180004902  jmp     loc_180004989
0x180004907  mov     ecx, 0C0000095h
0x18000490c  jmp     short loc_180004989
0x18000490e  mov     ecx, 0C0000059h
0x180004913  jmp     short loc_180004989
0x180004915  cmp     ecx, 8007050Ch
0x18000491b  jz      short loc_180004984
0x18000491d  cmp     ecx, 8007054Fh
0x180004923  jz      short loc_18000497D
0x180004925  cmp     ecx, 800705B9h
0x18000492b  jz      short loc_180004976
0x18000492d  test    ecx, ecx
0x18000492f  jz      short loc_180004972
0x180004931  bt      ecx, 1Ch
0x180004935  jnb     short loc_18000493D
0x180004937  btr     ecx, 1Ch
0x18000493b  jmp     short loc_180004989
0x18000493d  mov     eax, ecx
0x18000493f  and     eax, 1FFF0000h
0x180004944  cmp     eax, 70000h
0x180004949  jnz     short loc_18000495C
0x18000494b  movzx   ecx, cx
0x18000494e  mov     eax, ecx
0x180004950  or      eax, 0C0070000h
0x180004955  test    ecx, ecx
0x180004957  cmovnz  ecx, eax
0x18000495a  jmp     short loc_180004989
0x18000495c  cmp     eax, 90000h
0x180004961  jnz     short loc_18000497D
0x180004963  test    ecx, ecx
0x180004965  jle     short loc_180004989
0x180004967  movzx   ecx, cx
0x18000496a  or      ecx, 0C0090000h
0x180004970  jmp     short loc_180004989
0x180004972  xor     ecx, ecx
0x180004974  jmp     short loc_180004989
0x180004976  mov     ecx, 0C000A083h
0x18000497b  jmp     short loc_180004989
0x18000497d  mov     ecx, 0C00000E5h
0x180004982  jmp     short loc_180004989
0x180004984  mov     ecx, 0C000042Bh
0x180004989  mov     eax, ecx
0x18000498b  retn
```
