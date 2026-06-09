# wil::details::HrToNtStatus(long)

- ea: `0x18000558c`
- end: `0x180005748`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026b4`
- `0x18000275c`
- `0x1800027ac`
- `0x18000286c`
- `0x180004b58`
- `0x180005918`

## callees

- `0x18000558c`

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
0x18000558c  mov     eax, 800700EAh
0x180005591  cmp     ecx, eax
0x180005593  jg      loc_180005668
0x180005599  jz      loc_18000565E
0x18000559f  mov     eax, 80070057h
0x1800055a4  cmp     ecx, eax
0x1800055a6  jg      short loc_180005612
0x1800055a8  jz      short loc_180005608
0x1800055aa  cmp     ecx, 80004005h
0x1800055b0  jz      short loc_1800055FE
0x1800055b2  cmp     ecx, 80070001h
0x1800055b8  jz      short loc_1800055F4
0x1800055ba  cmp     ecx, 80070002h
0x1800055c0  jz      short loc_1800055EA
0x1800055c2  cmp     ecx, 80070003h
0x1800055c8  jz      short loc_1800055E0
0x1800055ca  cmp     ecx, 8007000Eh
0x1800055d0  jnz     loc_1800056ED
0x1800055d6  mov     ecx, 0C0000017h
0x1800055db  jmp     loc_180005745
0x1800055e0  mov     ecx, 0C000003Ah
0x1800055e5  jmp     loc_180005745
0x1800055ea  mov     ecx, 0C0000034h
0x1800055ef  jmp     loc_180005745
0x1800055f4  mov     ecx, 0C0000002h
0x1800055f9  jmp     loc_180005745
0x1800055fe  mov     ecx, 0C0000001h
0x180005603  jmp     loc_180005745
0x180005608  mov     ecx, 0C000000Dh
0x18000560d  jmp     loc_180005745
0x180005612  cmp     ecx, 80070070h
0x180005618  jz      short loc_180005654
0x18000561a  cmp     ecx, 8007007Ah
0x180005620  jz      short loc_18000564A
0x180005622  cmp     ecx, 8007007Bh
0x180005628  jz      short loc_180005640
0x18000562a  cmp     ecx, 8007007Eh
0x180005630  jnz     loc_1800056ED
0x180005636  mov     ecx, 0C0000135h
0x18000563b  jmp     loc_180005745
0x180005640  mov     ecx, 0C0000033h
0x180005645  jmp     loc_180005745
0x18000564a  mov     ecx, 0C0000023h
0x18000564f  jmp     loc_180005745
0x180005654  mov     ecx, 0C000007Fh
0x180005659  jmp     loc_180005745
0x18000565e  mov     ecx, 80000005h
0x180005663  jmp     loc_180005745
0x180005668  mov     eax, 8007047Eh
0x18000566d  cmp     ecx, eax
0x18000566f  jg      short loc_1800056D1
0x180005671  jz      short loc_1800056CA
0x180005673  cmp     ecx, 80070216h
0x180005679  jz      short loc_1800056C3
0x18000567b  cmp     ecx, 8007023Eh
0x180005681  jz      short loc_1800056B9
0x180005683  cmp     ecx, 80070246h
0x180005689  jz      short loc_1800056AF
0x18000568b  cmp     ecx, 80070247h
0x180005691  jz      short loc_1800056A5
0x180005693  cmp     ecx, 80070272h
0x180005699  jnz     short loc_1800056ED
0x18000569b  mov     ecx, 0C0000273h
0x1800056a0  jmp     loc_180005745
0x1800056a5  mov     ecx, 0C0000163h
0x1800056aa  jmp     loc_180005745
0x1800056af  mov     ecx, 0C0000161h
0x1800056b4  jmp     loc_180005745
0x1800056b9  mov     ecx, 0C0000025h
0x1800056be  jmp     loc_180005745
0x1800056c3  mov     ecx, 0C0000095h
0x1800056c8  jmp     short loc_180005745
0x1800056ca  mov     ecx, 0C0000059h
0x1800056cf  jmp     short loc_180005745
0x1800056d1  cmp     ecx, 8007050Ch
0x1800056d7  jz      short loc_180005740
0x1800056d9  cmp     ecx, 8007054Fh
0x1800056df  jz      short loc_180005739
0x1800056e1  cmp     ecx, 800705B9h
0x1800056e7  jz      short loc_180005732
0x1800056e9  test    ecx, ecx
0x1800056eb  jz      short loc_18000572E
0x1800056ed  bt      ecx, 1Ch
0x1800056f1  jnb     short loc_1800056F9
0x1800056f3  btr     ecx, 1Ch
0x1800056f7  jmp     short loc_180005745
0x1800056f9  mov     eax, ecx
0x1800056fb  and     eax, 1FFF0000h
0x180005700  cmp     eax, 70000h
0x180005705  jnz     short loc_180005718
0x180005707  movzx   ecx, cx
0x18000570a  mov     eax, ecx
0x18000570c  or      eax, 0C0070000h
0x180005711  test    ecx, ecx
0x180005713  cmovnz  ecx, eax
0x180005716  jmp     short loc_180005745
0x180005718  cmp     eax, 90000h
0x18000571d  jnz     short loc_180005739
0x18000571f  test    ecx, ecx
0x180005721  jle     short loc_180005745
0x180005723  movzx   ecx, cx
0x180005726  or      ecx, 0C0090000h
0x18000572c  jmp     short loc_180005745
0x18000572e  xor     ecx, ecx
0x180005730  jmp     short loc_180005745
0x180005732  mov     ecx, 0C000A083h
0x180005737  jmp     short loc_180005745
0x180005739  mov     ecx, 0C00000E5h
0x18000573e  jmp     short loc_180005745
0x180005740  mov     ecx, 0C000042Bh
0x180005745  mov     eax, ecx
0x180005747  retn
```
