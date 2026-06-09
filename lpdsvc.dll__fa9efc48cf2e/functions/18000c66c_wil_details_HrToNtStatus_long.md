# wil::details::HrToNtStatus(long)

- ea: `0x18000c66c`
- end: `0x18000c828`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac70`
- `0x18000ad10`
- `0x18000ad60`
- `0x18000ae18`
- `0x18000bc48`
- `0x18000c830`

## callees

- `0x18000c66c`

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
0x18000c66c  mov     eax, 800700EAh
0x18000c671  cmp     ecx, eax
0x18000c673  jg      loc_18000C748
0x18000c679  jz      loc_18000C73E
0x18000c67f  mov     eax, 80070057h
0x18000c684  cmp     ecx, eax
0x18000c686  jg      short loc_18000C6F2
0x18000c688  jz      short loc_18000C6E8
0x18000c68a  cmp     ecx, 80004005h
0x18000c690  jz      short loc_18000C6DE
0x18000c692  cmp     ecx, 80070001h
0x18000c698  jz      short loc_18000C6D4
0x18000c69a  cmp     ecx, 80070002h
0x18000c6a0  jz      short loc_18000C6CA
0x18000c6a2  cmp     ecx, 80070003h
0x18000c6a8  jz      short loc_18000C6C0
0x18000c6aa  cmp     ecx, 8007000Eh
0x18000c6b0  jnz     loc_18000C7CD
0x18000c6b6  mov     ecx, 0C0000017h
0x18000c6bb  jmp     loc_18000C825
0x18000c6c0  mov     ecx, 0C000003Ah
0x18000c6c5  jmp     loc_18000C825
0x18000c6ca  mov     ecx, 0C0000034h
0x18000c6cf  jmp     loc_18000C825
0x18000c6d4  mov     ecx, 0C0000002h
0x18000c6d9  jmp     loc_18000C825
0x18000c6de  mov     ecx, 0C0000001h
0x18000c6e3  jmp     loc_18000C825
0x18000c6e8  mov     ecx, 0C000000Dh
0x18000c6ed  jmp     loc_18000C825
0x18000c6f2  cmp     ecx, 80070070h
0x18000c6f8  jz      short loc_18000C734
0x18000c6fa  cmp     ecx, 8007007Ah
0x18000c700  jz      short loc_18000C72A
0x18000c702  cmp     ecx, 8007007Bh
0x18000c708  jz      short loc_18000C720
0x18000c70a  cmp     ecx, 8007007Eh
0x18000c710  jnz     loc_18000C7CD
0x18000c716  mov     ecx, 0C0000135h
0x18000c71b  jmp     loc_18000C825
0x18000c720  mov     ecx, 0C0000033h
0x18000c725  jmp     loc_18000C825
0x18000c72a  mov     ecx, 0C0000023h
0x18000c72f  jmp     loc_18000C825
0x18000c734  mov     ecx, 0C000007Fh
0x18000c739  jmp     loc_18000C825
0x18000c73e  mov     ecx, 80000005h
0x18000c743  jmp     loc_18000C825
0x18000c748  mov     eax, 8007047Eh
0x18000c74d  cmp     ecx, eax
0x18000c74f  jg      short loc_18000C7B1
0x18000c751  jz      short loc_18000C7AA
0x18000c753  cmp     ecx, 80070216h
0x18000c759  jz      short loc_18000C7A3
0x18000c75b  cmp     ecx, 8007023Eh
0x18000c761  jz      short loc_18000C799
0x18000c763  cmp     ecx, 80070246h
0x18000c769  jz      short loc_18000C78F
0x18000c76b  cmp     ecx, 80070247h
0x18000c771  jz      short loc_18000C785
0x18000c773  cmp     ecx, 80070272h
0x18000c779  jnz     short loc_18000C7CD
0x18000c77b  mov     ecx, 0C0000273h
0x18000c780  jmp     loc_18000C825
0x18000c785  mov     ecx, 0C0000163h
0x18000c78a  jmp     loc_18000C825
0x18000c78f  mov     ecx, 0C0000161h
0x18000c794  jmp     loc_18000C825
0x18000c799  mov     ecx, 0C0000025h
0x18000c79e  jmp     loc_18000C825
0x18000c7a3  mov     ecx, 0C0000095h
0x18000c7a8  jmp     short loc_18000C825
0x18000c7aa  mov     ecx, 0C0000059h
0x18000c7af  jmp     short loc_18000C825
0x18000c7b1  cmp     ecx, 8007050Ch
0x18000c7b7  jz      short loc_18000C820
0x18000c7b9  cmp     ecx, 8007054Fh
0x18000c7bf  jz      short loc_18000C819
0x18000c7c1  cmp     ecx, 800705B9h
0x18000c7c7  jz      short loc_18000C812
0x18000c7c9  test    ecx, ecx
0x18000c7cb  jz      short loc_18000C80E
0x18000c7cd  bt      ecx, 1Ch
0x18000c7d1  jnb     short loc_18000C7D9
0x18000c7d3  btr     ecx, 1Ch
0x18000c7d7  jmp     short loc_18000C825
0x18000c7d9  mov     eax, ecx
0x18000c7db  and     eax, 1FFF0000h
0x18000c7e0  cmp     eax, 70000h
0x18000c7e5  jnz     short loc_18000C7F8
0x18000c7e7  movzx   ecx, cx
0x18000c7ea  mov     eax, ecx
0x18000c7ec  or      eax, 0C0070000h
0x18000c7f1  test    ecx, ecx
0x18000c7f3  cmovnz  ecx, eax
0x18000c7f6  jmp     short loc_18000C825
0x18000c7f8  cmp     eax, 90000h
0x18000c7fd  jnz     short loc_18000C819
0x18000c7ff  test    ecx, ecx
0x18000c801  jle     short loc_18000C825
0x18000c803  movzx   ecx, cx
0x18000c806  or      ecx, 0C0090000h
0x18000c80c  jmp     short loc_18000C825
0x18000c80e  xor     ecx, ecx
0x18000c810  jmp     short loc_18000C825
0x18000c812  mov     ecx, 0C000A083h
0x18000c817  jmp     short loc_18000C825
0x18000c819  mov     ecx, 0C00000E5h
0x18000c81e  jmp     short loc_18000C825
0x18000c820  mov     ecx, 0C000042Bh
0x18000c825  mov     eax, ecx
0x18000c827  retn
```
