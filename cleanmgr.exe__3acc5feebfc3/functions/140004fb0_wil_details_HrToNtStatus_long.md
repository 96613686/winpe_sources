# wil::details::HrToNtStatus(long)

- ea: `0x140004fb0`
- end: `0x14000516c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400035c4`
- `0x140003630`
- `0x1400036a8`
- `0x1400036f8`
- `0x1400045e8`
- `0x140005174`

## callees

- `0x140004fb0`

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
0x140004fb0  mov     eax, 800700EAh
0x140004fb5  cmp     ecx, eax
0x140004fb7  jg      loc_14000508C
0x140004fbd  jz      loc_140005082
0x140004fc3  mov     eax, 80070057h
0x140004fc8  cmp     ecx, eax
0x140004fca  jg      short loc_140005036
0x140004fcc  jz      short loc_14000502C
0x140004fce  cmp     ecx, 80004005h
0x140004fd4  jz      short loc_140005022
0x140004fd6  cmp     ecx, 80070001h
0x140004fdc  jz      short loc_140005018
0x140004fde  cmp     ecx, 80070002h
0x140004fe4  jz      short loc_14000500E
0x140004fe6  cmp     ecx, 80070003h
0x140004fec  jz      short loc_140005004
0x140004fee  cmp     ecx, 8007000Eh
0x140004ff4  jnz     loc_140005111
0x140004ffa  mov     ecx, 0C0000017h
0x140004fff  jmp     loc_140005169
0x140005004  mov     ecx, 0C000003Ah
0x140005009  jmp     loc_140005169
0x14000500e  mov     ecx, 0C0000034h
0x140005013  jmp     loc_140005169
0x140005018  mov     ecx, 0C0000002h
0x14000501d  jmp     loc_140005169
0x140005022  mov     ecx, 0C0000001h
0x140005027  jmp     loc_140005169
0x14000502c  mov     ecx, 0C000000Dh
0x140005031  jmp     loc_140005169
0x140005036  cmp     ecx, 80070070h
0x14000503c  jz      short loc_140005078
0x14000503e  cmp     ecx, 8007007Ah
0x140005044  jz      short loc_14000506E
0x140005046  cmp     ecx, 8007007Bh
0x14000504c  jz      short loc_140005064
0x14000504e  cmp     ecx, 8007007Eh
0x140005054  jnz     loc_140005111
0x14000505a  mov     ecx, 0C0000135h
0x14000505f  jmp     loc_140005169
0x140005064  mov     ecx, 0C0000033h
0x140005069  jmp     loc_140005169
0x14000506e  mov     ecx, 0C0000023h
0x140005073  jmp     loc_140005169
0x140005078  mov     ecx, 0C000007Fh
0x14000507d  jmp     loc_140005169
0x140005082  mov     ecx, 80000005h
0x140005087  jmp     loc_140005169
0x14000508c  mov     eax, 8007047Eh
0x140005091  cmp     ecx, eax
0x140005093  jg      short loc_1400050F5
0x140005095  jz      short loc_1400050EE
0x140005097  cmp     ecx, 80070216h
0x14000509d  jz      short loc_1400050E7
0x14000509f  cmp     ecx, 8007023Eh
0x1400050a5  jz      short loc_1400050DD
0x1400050a7  cmp     ecx, 80070246h
0x1400050ad  jz      short loc_1400050D3
0x1400050af  cmp     ecx, 80070247h
0x1400050b5  jz      short loc_1400050C9
0x1400050b7  cmp     ecx, 80070272h
0x1400050bd  jnz     short loc_140005111
0x1400050bf  mov     ecx, 0C0000273h
0x1400050c4  jmp     loc_140005169
0x1400050c9  mov     ecx, 0C0000163h
0x1400050ce  jmp     loc_140005169
0x1400050d3  mov     ecx, 0C0000161h
0x1400050d8  jmp     loc_140005169
0x1400050dd  mov     ecx, 0C0000025h
0x1400050e2  jmp     loc_140005169
0x1400050e7  mov     ecx, 0C0000095h
0x1400050ec  jmp     short loc_140005169
0x1400050ee  mov     ecx, 0C0000059h
0x1400050f3  jmp     short loc_140005169
0x1400050f5  cmp     ecx, 8007050Ch
0x1400050fb  jz      short loc_140005164
0x1400050fd  cmp     ecx, 8007054Fh
0x140005103  jz      short loc_14000515D
0x140005105  cmp     ecx, 800705B9h
0x14000510b  jz      short loc_140005156
0x14000510d  test    ecx, ecx
0x14000510f  jz      short loc_140005152
0x140005111  bt      ecx, 1Ch
0x140005115  jnb     short loc_14000511D
0x140005117  btr     ecx, 1Ch
0x14000511b  jmp     short loc_140005169
0x14000511d  mov     eax, ecx
0x14000511f  and     eax, 1FFF0000h
0x140005124  cmp     eax, 70000h
0x140005129  jnz     short loc_14000513C
0x14000512b  movzx   ecx, cx
0x14000512e  mov     eax, ecx
0x140005130  or      eax, 0C0070000h
0x140005135  test    ecx, ecx
0x140005137  cmovnz  ecx, eax
0x14000513a  jmp     short loc_140005169
0x14000513c  cmp     eax, 90000h
0x140005141  jnz     short loc_14000515D
0x140005143  test    ecx, ecx
0x140005145  jle     short loc_140005169
0x140005147  movzx   ecx, cx
0x14000514a  or      ecx, 0C0090000h
0x140005150  jmp     short loc_140005169
0x140005152  xor     ecx, ecx
0x140005154  jmp     short loc_140005169
0x140005156  mov     ecx, 0C000A083h
0x14000515b  jmp     short loc_140005169
0x14000515d  mov     ecx, 0C00000E5h
0x140005162  jmp     short loc_140005169
0x140005164  mov     ecx, 0C000042Bh
0x140005169  mov     eax, ecx
0x14000516b  retn
```
