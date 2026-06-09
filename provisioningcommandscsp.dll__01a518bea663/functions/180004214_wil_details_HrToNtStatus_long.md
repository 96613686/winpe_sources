# wil::details::HrToNtStatus(long)

- ea: `0x180004214`
- end: `0x1800043d0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023c8`
- `0x180002478`
- `0x1800024d0`
- `0x180002598`
- `0x1800038a8`
- `0x180004400`
- `0x180004c20`
- `0x18000630c`
- `0x18000cbb9`
- `0x18000cc24`
- `0x18000cced`
- `0x18000cd58`

## callees

- `0x180004214`

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
0x180004214  mov     eax, 800700EAh
0x180004219  cmp     ecx, eax
0x18000421b  jg      loc_1800042F0
0x180004221  jz      loc_1800042E6
0x180004227  mov     eax, 80070057h
0x18000422c  cmp     ecx, eax
0x18000422e  jg      short loc_18000429A
0x180004230  jz      short loc_180004290
0x180004232  cmp     ecx, 80004005h
0x180004238  jz      short loc_180004286
0x18000423a  cmp     ecx, 80070001h
0x180004240  jz      short loc_18000427C
0x180004242  cmp     ecx, 80070002h
0x180004248  jz      short loc_180004272
0x18000424a  cmp     ecx, 80070003h
0x180004250  jz      short loc_180004268
0x180004252  cmp     ecx, 8007000Eh
0x180004258  jnz     loc_180004375
0x18000425e  mov     ecx, 0C0000017h
0x180004263  jmp     loc_1800043CD
0x180004268  mov     ecx, 0C000003Ah
0x18000426d  jmp     loc_1800043CD
0x180004272  mov     ecx, 0C0000034h
0x180004277  jmp     loc_1800043CD
0x18000427c  mov     ecx, 0C0000002h
0x180004281  jmp     loc_1800043CD
0x180004286  mov     ecx, 0C0000001h
0x18000428b  jmp     loc_1800043CD
0x180004290  mov     ecx, 0C000000Dh
0x180004295  jmp     loc_1800043CD
0x18000429a  cmp     ecx, 80070070h
0x1800042a0  jz      short loc_1800042DC
0x1800042a2  cmp     ecx, 8007007Ah
0x1800042a8  jz      short loc_1800042D2
0x1800042aa  cmp     ecx, 8007007Bh
0x1800042b0  jz      short loc_1800042C8
0x1800042b2  cmp     ecx, 8007007Eh
0x1800042b8  jnz     loc_180004375
0x1800042be  mov     ecx, 0C0000135h
0x1800042c3  jmp     loc_1800043CD
0x1800042c8  mov     ecx, 0C0000033h
0x1800042cd  jmp     loc_1800043CD
0x1800042d2  mov     ecx, 0C0000023h
0x1800042d7  jmp     loc_1800043CD
0x1800042dc  mov     ecx, 0C000007Fh
0x1800042e1  jmp     loc_1800043CD
0x1800042e6  mov     ecx, 80000005h
0x1800042eb  jmp     loc_1800043CD
0x1800042f0  mov     eax, 8007047Eh
0x1800042f5  cmp     ecx, eax
0x1800042f7  jg      short loc_180004359
0x1800042f9  jz      short loc_180004352
0x1800042fb  cmp     ecx, 80070216h
0x180004301  jz      short loc_18000434B
0x180004303  cmp     ecx, 8007023Eh
0x180004309  jz      short loc_180004341
0x18000430b  cmp     ecx, 80070246h
0x180004311  jz      short loc_180004337
0x180004313  cmp     ecx, 80070247h
0x180004319  jz      short loc_18000432D
0x18000431b  cmp     ecx, 80070272h
0x180004321  jnz     short loc_180004375
0x180004323  mov     ecx, 0C0000273h
0x180004328  jmp     loc_1800043CD
0x18000432d  mov     ecx, 0C0000163h
0x180004332  jmp     loc_1800043CD
0x180004337  mov     ecx, 0C0000161h
0x18000433c  jmp     loc_1800043CD
0x180004341  mov     ecx, 0C0000025h
0x180004346  jmp     loc_1800043CD
0x18000434b  mov     ecx, 0C0000095h
0x180004350  jmp     short loc_1800043CD
0x180004352  mov     ecx, 0C0000059h
0x180004357  jmp     short loc_1800043CD
0x180004359  cmp     ecx, 8007050Ch
0x18000435f  jz      short loc_1800043C8
0x180004361  cmp     ecx, 8007054Fh
0x180004367  jz      short loc_1800043C1
0x180004369  cmp     ecx, 800705B9h
0x18000436f  jz      short loc_1800043BA
0x180004371  test    ecx, ecx
0x180004373  jz      short loc_1800043B6
0x180004375  bt      ecx, 1Ch
0x180004379  jnb     short loc_180004381
0x18000437b  btr     ecx, 1Ch
0x18000437f  jmp     short loc_1800043CD
0x180004381  mov     eax, ecx
0x180004383  and     eax, 1FFF0000h
0x180004388  cmp     eax, 70000h
0x18000438d  jnz     short loc_1800043A0
0x18000438f  movzx   ecx, cx
0x180004392  mov     eax, ecx
0x180004394  or      eax, 0C0070000h
0x180004399  test    ecx, ecx
0x18000439b  cmovnz  ecx, eax
0x18000439e  jmp     short loc_1800043CD
0x1800043a0  cmp     eax, 90000h
0x1800043a5  jnz     short loc_1800043C1
0x1800043a7  test    ecx, ecx
0x1800043a9  jle     short loc_1800043CD
0x1800043ab  movzx   ecx, cx
0x1800043ae  or      ecx, 0C0090000h
0x1800043b4  jmp     short loc_1800043CD
0x1800043b6  xor     ecx, ecx
0x1800043b8  jmp     short loc_1800043CD
0x1800043ba  mov     ecx, 0C000A083h
0x1800043bf  jmp     short loc_1800043CD
0x1800043c1  mov     ecx, 0C00000E5h
0x1800043c6  jmp     short loc_1800043CD
0x1800043c8  mov     ecx, 0C000042Bh
0x1800043cd  mov     eax, ecx
0x1800043cf  retn
```
