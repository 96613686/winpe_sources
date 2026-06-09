# wil::details::HrToNtStatus(long)

- ea: `0x1800044ac`
- end: `0x180004668`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ae0`
- `0x180002b80`
- `0x180002bd0`
- `0x180002c88`
- `0x180003b38`
- `0x18000468c`

## callees

- `0x1800044ac`

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
0x1800044ac  mov     eax, 800700EAh
0x1800044b1  cmp     ecx, eax
0x1800044b3  jg      loc_180004588
0x1800044b9  jz      loc_18000457E
0x1800044bf  mov     eax, 80070057h
0x1800044c4  cmp     ecx, eax
0x1800044c6  jg      short loc_180004532
0x1800044c8  jz      short loc_180004528
0x1800044ca  cmp     ecx, 80004005h
0x1800044d0  jz      short loc_18000451E
0x1800044d2  cmp     ecx, 80070001h
0x1800044d8  jz      short loc_180004514
0x1800044da  cmp     ecx, 80070002h
0x1800044e0  jz      short loc_18000450A
0x1800044e2  cmp     ecx, 80070003h
0x1800044e8  jz      short loc_180004500
0x1800044ea  cmp     ecx, 8007000Eh
0x1800044f0  jnz     loc_18000460D
0x1800044f6  mov     ecx, 0C0000017h
0x1800044fb  jmp     loc_180004665
0x180004500  mov     ecx, 0C000003Ah
0x180004505  jmp     loc_180004665
0x18000450a  mov     ecx, 0C0000034h
0x18000450f  jmp     loc_180004665
0x180004514  mov     ecx, 0C0000002h
0x180004519  jmp     loc_180004665
0x18000451e  mov     ecx, 0C0000001h
0x180004523  jmp     loc_180004665
0x180004528  mov     ecx, 0C000000Dh
0x18000452d  jmp     loc_180004665
0x180004532  cmp     ecx, 80070070h
0x180004538  jz      short loc_180004574
0x18000453a  cmp     ecx, 8007007Ah
0x180004540  jz      short loc_18000456A
0x180004542  cmp     ecx, 8007007Bh
0x180004548  jz      short loc_180004560
0x18000454a  cmp     ecx, 8007007Eh
0x180004550  jnz     loc_18000460D
0x180004556  mov     ecx, 0C0000135h
0x18000455b  jmp     loc_180004665
0x180004560  mov     ecx, 0C0000033h
0x180004565  jmp     loc_180004665
0x18000456a  mov     ecx, 0C0000023h
0x18000456f  jmp     loc_180004665
0x180004574  mov     ecx, 0C000007Fh
0x180004579  jmp     loc_180004665
0x18000457e  mov     ecx, 80000005h
0x180004583  jmp     loc_180004665
0x180004588  mov     eax, 8007047Eh
0x18000458d  cmp     ecx, eax
0x18000458f  jg      short loc_1800045F1
0x180004591  jz      short loc_1800045EA
0x180004593  cmp     ecx, 80070216h
0x180004599  jz      short loc_1800045E3
0x18000459b  cmp     ecx, 8007023Eh
0x1800045a1  jz      short loc_1800045D9
0x1800045a3  cmp     ecx, 80070246h
0x1800045a9  jz      short loc_1800045CF
0x1800045ab  cmp     ecx, 80070247h
0x1800045b1  jz      short loc_1800045C5
0x1800045b3  cmp     ecx, 80070272h
0x1800045b9  jnz     short loc_18000460D
0x1800045bb  mov     ecx, 0C0000273h
0x1800045c0  jmp     loc_180004665
0x1800045c5  mov     ecx, 0C0000163h
0x1800045ca  jmp     loc_180004665
0x1800045cf  mov     ecx, 0C0000161h
0x1800045d4  jmp     loc_180004665
0x1800045d9  mov     ecx, 0C0000025h
0x1800045de  jmp     loc_180004665
0x1800045e3  mov     ecx, 0C0000095h
0x1800045e8  jmp     short loc_180004665
0x1800045ea  mov     ecx, 0C0000059h
0x1800045ef  jmp     short loc_180004665
0x1800045f1  cmp     ecx, 8007050Ch
0x1800045f7  jz      short loc_180004660
0x1800045f9  cmp     ecx, 8007054Fh
0x1800045ff  jz      short loc_180004659
0x180004601  cmp     ecx, 800705B9h
0x180004607  jz      short loc_180004652
0x180004609  test    ecx, ecx
0x18000460b  jz      short loc_18000464E
0x18000460d  bt      ecx, 1Ch
0x180004611  jnb     short loc_180004619
0x180004613  btr     ecx, 1Ch
0x180004617  jmp     short loc_180004665
0x180004619  mov     eax, ecx
0x18000461b  and     eax, 1FFF0000h
0x180004620  cmp     eax, 70000h
0x180004625  jnz     short loc_180004638
0x180004627  movzx   ecx, cx
0x18000462a  mov     eax, ecx
0x18000462c  or      eax, 0C0070000h
0x180004631  test    ecx, ecx
0x180004633  cmovnz  ecx, eax
0x180004636  jmp     short loc_180004665
0x180004638  cmp     eax, 90000h
0x18000463d  jnz     short loc_180004659
0x18000463f  test    ecx, ecx
0x180004641  jle     short loc_180004665
0x180004643  movzx   ecx, cx
0x180004646  or      ecx, 0C0090000h
0x18000464c  jmp     short loc_180004665
0x18000464e  xor     ecx, ecx
0x180004650  jmp     short loc_180004665
0x180004652  mov     ecx, 0C000A083h
0x180004657  jmp     short loc_180004665
0x180004659  mov     ecx, 0C00000E5h
0x18000465e  jmp     short loc_180004665
0x180004660  mov     ecx, 0C000042Bh
0x180004665  mov     eax, ecx
0x180004667  retn
```
