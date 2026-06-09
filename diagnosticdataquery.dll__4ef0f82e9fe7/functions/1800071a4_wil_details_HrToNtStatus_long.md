# wil::details::HrToNtStatus(long)

- ea: `0x1800071a4`
- end: `0x180007360`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000547c`
- `0x180005524`
- `0x180005574`
- `0x18000562c`
- `0x180006778`
- `0x180007368`

## callees

- `0x1800071a4`

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
0x1800071a4  mov     eax, 800700EAh
0x1800071a9  cmp     ecx, eax
0x1800071ab  jg      loc_180007280
0x1800071b1  jz      loc_180007276
0x1800071b7  mov     eax, 80070057h
0x1800071bc  cmp     ecx, eax
0x1800071be  jg      short loc_18000722A
0x1800071c0  jz      short loc_180007220
0x1800071c2  cmp     ecx, 80004005h
0x1800071c8  jz      short loc_180007216
0x1800071ca  cmp     ecx, 80070001h
0x1800071d0  jz      short loc_18000720C
0x1800071d2  cmp     ecx, 80070002h
0x1800071d8  jz      short loc_180007202
0x1800071da  cmp     ecx, 80070003h
0x1800071e0  jz      short loc_1800071F8
0x1800071e2  cmp     ecx, 8007000Eh
0x1800071e8  jnz     loc_180007305
0x1800071ee  mov     ecx, 0C0000017h
0x1800071f3  jmp     loc_18000735D
0x1800071f8  mov     ecx, 0C000003Ah
0x1800071fd  jmp     loc_18000735D
0x180007202  mov     ecx, 0C0000034h
0x180007207  jmp     loc_18000735D
0x18000720c  mov     ecx, 0C0000002h
0x180007211  jmp     loc_18000735D
0x180007216  mov     ecx, 0C0000001h
0x18000721b  jmp     loc_18000735D
0x180007220  mov     ecx, 0C000000Dh
0x180007225  jmp     loc_18000735D
0x18000722a  cmp     ecx, 80070070h
0x180007230  jz      short loc_18000726C
0x180007232  cmp     ecx, 8007007Ah
0x180007238  jz      short loc_180007262
0x18000723a  cmp     ecx, 8007007Bh
0x180007240  jz      short loc_180007258
0x180007242  cmp     ecx, 8007007Eh
0x180007248  jnz     loc_180007305
0x18000724e  mov     ecx, 0C0000135h
0x180007253  jmp     loc_18000735D
0x180007258  mov     ecx, 0C0000033h
0x18000725d  jmp     loc_18000735D
0x180007262  mov     ecx, 0C0000023h
0x180007267  jmp     loc_18000735D
0x18000726c  mov     ecx, 0C000007Fh
0x180007271  jmp     loc_18000735D
0x180007276  mov     ecx, 80000005h
0x18000727b  jmp     loc_18000735D
0x180007280  mov     eax, 8007047Eh
0x180007285  cmp     ecx, eax
0x180007287  jg      short loc_1800072E9
0x180007289  jz      short loc_1800072E2
0x18000728b  cmp     ecx, 80070216h
0x180007291  jz      short loc_1800072DB
0x180007293  cmp     ecx, 8007023Eh
0x180007299  jz      short loc_1800072D1
0x18000729b  cmp     ecx, 80070246h
0x1800072a1  jz      short loc_1800072C7
0x1800072a3  cmp     ecx, 80070247h
0x1800072a9  jz      short loc_1800072BD
0x1800072ab  cmp     ecx, 80070272h
0x1800072b1  jnz     short loc_180007305
0x1800072b3  mov     ecx, 0C0000273h
0x1800072b8  jmp     loc_18000735D
0x1800072bd  mov     ecx, 0C0000163h
0x1800072c2  jmp     loc_18000735D
0x1800072c7  mov     ecx, 0C0000161h
0x1800072cc  jmp     loc_18000735D
0x1800072d1  mov     ecx, 0C0000025h
0x1800072d6  jmp     loc_18000735D
0x1800072db  mov     ecx, 0C0000095h
0x1800072e0  jmp     short loc_18000735D
0x1800072e2  mov     ecx, 0C0000059h
0x1800072e7  jmp     short loc_18000735D
0x1800072e9  cmp     ecx, 8007050Ch
0x1800072ef  jz      short loc_180007358
0x1800072f1  cmp     ecx, 8007054Fh
0x1800072f7  jz      short loc_180007351
0x1800072f9  cmp     ecx, 800705B9h
0x1800072ff  jz      short loc_18000734A
0x180007301  test    ecx, ecx
0x180007303  jz      short loc_180007346
0x180007305  bt      ecx, 1Ch
0x180007309  jnb     short loc_180007311
0x18000730b  btr     ecx, 1Ch
0x18000730f  jmp     short loc_18000735D
0x180007311  mov     eax, ecx
0x180007313  and     eax, 1FFF0000h
0x180007318  cmp     eax, 70000h
0x18000731d  jnz     short loc_180007330
0x18000731f  movzx   ecx, cx
0x180007322  mov     eax, ecx
0x180007324  or      eax, 0C0070000h
0x180007329  test    ecx, ecx
0x18000732b  cmovnz  ecx, eax
0x18000732e  jmp     short loc_18000735D
0x180007330  cmp     eax, 90000h
0x180007335  jnz     short loc_180007351
0x180007337  test    ecx, ecx
0x180007339  jle     short loc_18000735D
0x18000733b  movzx   ecx, cx
0x18000733e  or      ecx, 0C0090000h
0x180007344  jmp     short loc_18000735D
0x180007346  xor     ecx, ecx
0x180007348  jmp     short loc_18000735D
0x18000734a  mov     ecx, 0C000A083h
0x18000734f  jmp     short loc_18000735D
0x180007351  mov     ecx, 0C00000E5h
0x180007356  jmp     short loc_18000735D
0x180007358  mov     ecx, 0C000042Bh
0x18000735d  mov     eax, ecx
0x18000735f  retn
```
