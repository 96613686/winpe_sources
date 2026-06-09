# wil::details::HrToNtStatus(long)

- ea: `0x180004e9c`
- end: `0x180005058`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180003118`
- `0x1800031c8`
- `0x180003220`
- `0x1800032e8`
- `0x180004468`
- `0x180005060`
- `0x1800057e0`
- `0x18000bf1c`
- `0x18000d7ff`
- `0x18000d86a`
- `0x18000d933`
- `0x18000d99e`

## callees

- `0x180004e9c`

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
0x180004e9c  mov     eax, 800700EAh
0x180004ea1  cmp     ecx, eax
0x180004ea3  jg      loc_180004F78
0x180004ea9  jz      loc_180004F6E
0x180004eaf  mov     eax, 80070057h
0x180004eb4  cmp     ecx, eax
0x180004eb6  jg      short loc_180004F22
0x180004eb8  jz      short loc_180004F18
0x180004eba  cmp     ecx, 80004005h
0x180004ec0  jz      short loc_180004F0E
0x180004ec2  cmp     ecx, 80070001h
0x180004ec8  jz      short loc_180004F04
0x180004eca  cmp     ecx, 80070002h
0x180004ed0  jz      short loc_180004EFA
0x180004ed2  cmp     ecx, 80070003h
0x180004ed8  jz      short loc_180004EF0
0x180004eda  cmp     ecx, 8007000Eh
0x180004ee0  jnz     loc_180004FFD
0x180004ee6  mov     ecx, 0C0000017h
0x180004eeb  jmp     loc_180005055
0x180004ef0  mov     ecx, 0C000003Ah
0x180004ef5  jmp     loc_180005055
0x180004efa  mov     ecx, 0C0000034h
0x180004eff  jmp     loc_180005055
0x180004f04  mov     ecx, 0C0000002h
0x180004f09  jmp     loc_180005055
0x180004f0e  mov     ecx, 0C0000001h
0x180004f13  jmp     loc_180005055
0x180004f18  mov     ecx, 0C000000Dh
0x180004f1d  jmp     loc_180005055
0x180004f22  cmp     ecx, 80070070h
0x180004f28  jz      short loc_180004F64
0x180004f2a  cmp     ecx, 8007007Ah
0x180004f30  jz      short loc_180004F5A
0x180004f32  cmp     ecx, 8007007Bh
0x180004f38  jz      short loc_180004F50
0x180004f3a  cmp     ecx, 8007007Eh
0x180004f40  jnz     loc_180004FFD
0x180004f46  mov     ecx, 0C0000135h
0x180004f4b  jmp     loc_180005055
0x180004f50  mov     ecx, 0C0000033h
0x180004f55  jmp     loc_180005055
0x180004f5a  mov     ecx, 0C0000023h
0x180004f5f  jmp     loc_180005055
0x180004f64  mov     ecx, 0C000007Fh
0x180004f69  jmp     loc_180005055
0x180004f6e  mov     ecx, 80000005h
0x180004f73  jmp     loc_180005055
0x180004f78  mov     eax, 8007047Eh
0x180004f7d  cmp     ecx, eax
0x180004f7f  jg      short loc_180004FE1
0x180004f81  jz      short loc_180004FDA
0x180004f83  cmp     ecx, 80070216h
0x180004f89  jz      short loc_180004FD3
0x180004f8b  cmp     ecx, 8007023Eh
0x180004f91  jz      short loc_180004FC9
0x180004f93  cmp     ecx, 80070246h
0x180004f99  jz      short loc_180004FBF
0x180004f9b  cmp     ecx, 80070247h
0x180004fa1  jz      short loc_180004FB5
0x180004fa3  cmp     ecx, 80070272h
0x180004fa9  jnz     short loc_180004FFD
0x180004fab  mov     ecx, 0C0000273h
0x180004fb0  jmp     loc_180005055
0x180004fb5  mov     ecx, 0C0000163h
0x180004fba  jmp     loc_180005055
0x180004fbf  mov     ecx, 0C0000161h
0x180004fc4  jmp     loc_180005055
0x180004fc9  mov     ecx, 0C0000025h
0x180004fce  jmp     loc_180005055
0x180004fd3  mov     ecx, 0C0000095h
0x180004fd8  jmp     short loc_180005055
0x180004fda  mov     ecx, 0C0000059h
0x180004fdf  jmp     short loc_180005055
0x180004fe1  cmp     ecx, 8007050Ch
0x180004fe7  jz      short loc_180005050
0x180004fe9  cmp     ecx, 8007054Fh
0x180004fef  jz      short loc_180005049
0x180004ff1  cmp     ecx, 800705B9h
0x180004ff7  jz      short loc_180005042
0x180004ff9  test    ecx, ecx
0x180004ffb  jz      short loc_18000503E
0x180004ffd  bt      ecx, 1Ch
0x180005001  jnb     short loc_180005009
0x180005003  btr     ecx, 1Ch
0x180005007  jmp     short loc_180005055
0x180005009  mov     eax, ecx
0x18000500b  and     eax, 1FFF0000h
0x180005010  cmp     eax, 70000h
0x180005015  jnz     short loc_180005028
0x180005017  movzx   ecx, cx
0x18000501a  mov     eax, ecx
0x18000501c  or      eax, 0C0070000h
0x180005021  test    ecx, ecx
0x180005023  cmovnz  ecx, eax
0x180005026  jmp     short loc_180005055
0x180005028  cmp     eax, 90000h
0x18000502d  jnz     short loc_180005049
0x18000502f  test    ecx, ecx
0x180005031  jle     short loc_180005055
0x180005033  movzx   ecx, cx
0x180005036  or      ecx, 0C0090000h
0x18000503c  jmp     short loc_180005055
0x18000503e  xor     ecx, ecx
0x180005040  jmp     short loc_180005055
0x180005042  mov     ecx, 0C000A083h
0x180005047  jmp     short loc_180005055
0x180005049  mov     ecx, 0C00000E5h
0x18000504e  jmp     short loc_180005055
0x180005050  mov     ecx, 0C000042Bh
0x180005055  mov     eax, ecx
0x180005057  retn
```
