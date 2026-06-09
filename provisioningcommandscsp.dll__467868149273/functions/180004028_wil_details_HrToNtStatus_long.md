# wil::details::HrToNtStatus(long)

- ea: `0x180004028`
- end: `0x1800041e4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023d8`
- `0x180002490`
- `0x1800024e8`
- `0x1800025b0`
- `0x180003644`
- `0x180004210`
- `0x180004d60`
- `0x18000660c`
- `0x18000d279`
- `0x18000d2e4`
- `0x18000d3ad`
- `0x18000d418`

## callees

- `0x180004028`

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
0x180004028  mov     eax, 800700EAh
0x18000402d  cmp     ecx, eax
0x18000402f  jg      loc_180004104
0x180004035  jz      loc_1800040FA
0x18000403b  mov     eax, 80070057h
0x180004040  cmp     ecx, eax
0x180004042  jg      short loc_1800040AE
0x180004044  jz      short loc_1800040A4
0x180004046  cmp     ecx, 80004005h
0x18000404c  jz      short loc_18000409A
0x18000404e  cmp     ecx, 80070001h
0x180004054  jz      short loc_180004090
0x180004056  cmp     ecx, 80070002h
0x18000405c  jz      short loc_180004086
0x18000405e  cmp     ecx, 80070003h
0x180004064  jz      short loc_18000407C
0x180004066  cmp     ecx, 8007000Eh
0x18000406c  jnz     loc_180004189
0x180004072  mov     ecx, 0C0000017h
0x180004077  jmp     loc_1800041E1
0x18000407c  mov     ecx, 0C000003Ah
0x180004081  jmp     loc_1800041E1
0x180004086  mov     ecx, 0C0000034h
0x18000408b  jmp     loc_1800041E1
0x180004090  mov     ecx, 0C0000002h
0x180004095  jmp     loc_1800041E1
0x18000409a  mov     ecx, 0C0000001h
0x18000409f  jmp     loc_1800041E1
0x1800040a4  mov     ecx, 0C000000Dh
0x1800040a9  jmp     loc_1800041E1
0x1800040ae  cmp     ecx, 80070070h
0x1800040b4  jz      short loc_1800040F0
0x1800040b6  cmp     ecx, 8007007Ah
0x1800040bc  jz      short loc_1800040E6
0x1800040be  cmp     ecx, 8007007Bh
0x1800040c4  jz      short loc_1800040DC
0x1800040c6  cmp     ecx, 8007007Eh
0x1800040cc  jnz     loc_180004189
0x1800040d2  mov     ecx, 0C0000135h
0x1800040d7  jmp     loc_1800041E1
0x1800040dc  mov     ecx, 0C0000033h
0x1800040e1  jmp     loc_1800041E1
0x1800040e6  mov     ecx, 0C0000023h
0x1800040eb  jmp     loc_1800041E1
0x1800040f0  mov     ecx, 0C000007Fh
0x1800040f5  jmp     loc_1800041E1
0x1800040fa  mov     ecx, 80000005h
0x1800040ff  jmp     loc_1800041E1
0x180004104  mov     eax, 8007047Eh
0x180004109  cmp     ecx, eax
0x18000410b  jg      short loc_18000416D
0x18000410d  jz      short loc_180004166
0x18000410f  cmp     ecx, 80070216h
0x180004115  jz      short loc_18000415F
0x180004117  cmp     ecx, 8007023Eh
0x18000411d  jz      short loc_180004155
0x18000411f  cmp     ecx, 80070246h
0x180004125  jz      short loc_18000414B
0x180004127  cmp     ecx, 80070247h
0x18000412d  jz      short loc_180004141
0x18000412f  cmp     ecx, 80070272h
0x180004135  jnz     short loc_180004189
0x180004137  mov     ecx, 0C0000273h
0x18000413c  jmp     loc_1800041E1
0x180004141  mov     ecx, 0C0000163h
0x180004146  jmp     loc_1800041E1
0x18000414b  mov     ecx, 0C0000161h
0x180004150  jmp     loc_1800041E1
0x180004155  mov     ecx, 0C0000025h
0x18000415a  jmp     loc_1800041E1
0x18000415f  mov     ecx, 0C0000095h
0x180004164  jmp     short loc_1800041E1
0x180004166  mov     ecx, 0C0000059h
0x18000416b  jmp     short loc_1800041E1
0x18000416d  cmp     ecx, 8007050Ch
0x180004173  jz      short loc_1800041DC
0x180004175  cmp     ecx, 8007054Fh
0x18000417b  jz      short loc_1800041D5
0x18000417d  cmp     ecx, 800705B9h
0x180004183  jz      short loc_1800041CE
0x180004185  test    ecx, ecx
0x180004187  jz      short loc_1800041CA
0x180004189  bt      ecx, 1Ch
0x18000418d  jnb     short loc_180004195
0x18000418f  btr     ecx, 1Ch
0x180004193  jmp     short loc_1800041E1
0x180004195  mov     eax, ecx
0x180004197  and     eax, 1FFF0000h
0x18000419c  cmp     eax, 70000h
0x1800041a1  jnz     short loc_1800041B4
0x1800041a3  movzx   ecx, cx
0x1800041a6  mov     eax, ecx
0x1800041a8  or      eax, 0C0070000h
0x1800041ad  test    ecx, ecx
0x1800041af  cmovnz  ecx, eax
0x1800041b2  jmp     short loc_1800041E1
0x1800041b4  cmp     eax, 90000h
0x1800041b9  jnz     short loc_1800041D5
0x1800041bb  test    ecx, ecx
0x1800041bd  jle     short loc_1800041E1
0x1800041bf  movzx   ecx, cx
0x1800041c2  or      ecx, 0C0090000h
0x1800041c8  jmp     short loc_1800041E1
0x1800041ca  xor     ecx, ecx
0x1800041cc  jmp     short loc_1800041E1
0x1800041ce  mov     ecx, 0C000A083h
0x1800041d3  jmp     short loc_1800041E1
0x1800041d5  mov     ecx, 0C00000E5h
0x1800041da  jmp     short loc_1800041E1
0x1800041dc  mov     ecx, 0C000042Bh
0x1800041e1  mov     eax, ecx
0x1800041e3  retn
```
