# wil::details::HrToNtStatus(long)

- ea: `0x180007234`
- end: `0x1800073f0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003444`
- `0x1800034e4`
- `0x180003534`
- `0x1800035f4`
- `0x180005e18`
- `0x1800078c4`

## callees

- `0x180007234`

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
0x180007234  mov     eax, 800700EAh
0x180007239  cmp     ecx, eax
0x18000723b  jg      loc_180007310
0x180007241  jz      loc_180007306
0x180007247  mov     eax, 80070057h
0x18000724c  cmp     ecx, eax
0x18000724e  jg      short loc_1800072BA
0x180007250  jz      short loc_1800072B0
0x180007252  cmp     ecx, 80004005h
0x180007258  jz      short loc_1800072A6
0x18000725a  cmp     ecx, 80070001h
0x180007260  jz      short loc_18000729C
0x180007262  cmp     ecx, 80070002h
0x180007268  jz      short loc_180007292
0x18000726a  cmp     ecx, 80070003h
0x180007270  jz      short loc_180007288
0x180007272  cmp     ecx, 8007000Eh
0x180007278  jnz     loc_180007395
0x18000727e  mov     ecx, 0C0000017h
0x180007283  jmp     loc_1800073ED
0x180007288  mov     ecx, 0C000003Ah
0x18000728d  jmp     loc_1800073ED
0x180007292  mov     ecx, 0C0000034h
0x180007297  jmp     loc_1800073ED
0x18000729c  mov     ecx, 0C0000002h
0x1800072a1  jmp     loc_1800073ED
0x1800072a6  mov     ecx, 0C0000001h
0x1800072ab  jmp     loc_1800073ED
0x1800072b0  mov     ecx, 0C000000Dh
0x1800072b5  jmp     loc_1800073ED
0x1800072ba  cmp     ecx, 80070070h
0x1800072c0  jz      short loc_1800072FC
0x1800072c2  cmp     ecx, 8007007Ah
0x1800072c8  jz      short loc_1800072F2
0x1800072ca  cmp     ecx, 8007007Bh
0x1800072d0  jz      short loc_1800072E8
0x1800072d2  cmp     ecx, 8007007Eh
0x1800072d8  jnz     loc_180007395
0x1800072de  mov     ecx, 0C0000135h
0x1800072e3  jmp     loc_1800073ED
0x1800072e8  mov     ecx, 0C0000033h
0x1800072ed  jmp     loc_1800073ED
0x1800072f2  mov     ecx, 0C0000023h
0x1800072f7  jmp     loc_1800073ED
0x1800072fc  mov     ecx, 0C000007Fh
0x180007301  jmp     loc_1800073ED
0x180007306  mov     ecx, 80000005h
0x18000730b  jmp     loc_1800073ED
0x180007310  mov     eax, 8007047Eh
0x180007315  cmp     ecx, eax
0x180007317  jg      short loc_180007379
0x180007319  jz      short loc_180007372
0x18000731b  cmp     ecx, 80070216h
0x180007321  jz      short loc_18000736B
0x180007323  cmp     ecx, 8007023Eh
0x180007329  jz      short loc_180007361
0x18000732b  cmp     ecx, 80070246h
0x180007331  jz      short loc_180007357
0x180007333  cmp     ecx, 80070247h
0x180007339  jz      short loc_18000734D
0x18000733b  cmp     ecx, 80070272h
0x180007341  jnz     short loc_180007395
0x180007343  mov     ecx, 0C0000273h
0x180007348  jmp     loc_1800073ED
0x18000734d  mov     ecx, 0C0000163h
0x180007352  jmp     loc_1800073ED
0x180007357  mov     ecx, 0C0000161h
0x18000735c  jmp     loc_1800073ED
0x180007361  mov     ecx, 0C0000025h
0x180007366  jmp     loc_1800073ED
0x18000736b  mov     ecx, 0C0000095h
0x180007370  jmp     short loc_1800073ED
0x180007372  mov     ecx, 0C0000059h
0x180007377  jmp     short loc_1800073ED
0x180007379  cmp     ecx, 8007050Ch
0x18000737f  jz      short loc_1800073E8
0x180007381  cmp     ecx, 8007054Fh
0x180007387  jz      short loc_1800073E1
0x180007389  cmp     ecx, 800705B9h
0x18000738f  jz      short loc_1800073DA
0x180007391  test    ecx, ecx
0x180007393  jz      short loc_1800073D6
0x180007395  bt      ecx, 1Ch
0x180007399  jnb     short loc_1800073A1
0x18000739b  btr     ecx, 1Ch
0x18000739f  jmp     short loc_1800073ED
0x1800073a1  mov     eax, ecx
0x1800073a3  and     eax, 1FFF0000h
0x1800073a8  cmp     eax, 70000h
0x1800073ad  jnz     short loc_1800073C0
0x1800073af  movzx   ecx, cx
0x1800073b2  mov     eax, ecx
0x1800073b4  or      eax, 0C0070000h
0x1800073b9  test    ecx, ecx
0x1800073bb  cmovnz  ecx, eax
0x1800073be  jmp     short loc_1800073ED
0x1800073c0  cmp     eax, 90000h
0x1800073c5  jnz     short loc_1800073E1
0x1800073c7  test    ecx, ecx
0x1800073c9  jle     short loc_1800073ED
0x1800073cb  movzx   ecx, cx
0x1800073ce  or      ecx, 0C0090000h
0x1800073d4  jmp     short loc_1800073ED
0x1800073d6  xor     ecx, ecx
0x1800073d8  jmp     short loc_1800073ED
0x1800073da  mov     ecx, 0C000A083h
0x1800073df  jmp     short loc_1800073ED
0x1800073e1  mov     ecx, 0C00000E5h
0x1800073e6  jmp     short loc_1800073ED
0x1800073e8  mov     ecx, 0C000042Bh
0x1800073ed  mov     eax, ecx
0x1800073ef  retn
```
