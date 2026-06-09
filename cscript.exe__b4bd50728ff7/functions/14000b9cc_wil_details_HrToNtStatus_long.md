# wil::details::HrToNtStatus(long)

- ea: `0x14000b9cc`
- end: `0x14000bb88`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a5ac`
- `0x14000a624`
- `0x14000a674`
- `0x14000a734`
- `0x14000b470`
- `0x14000bb90`

## callees

- `0x14000b9cc`

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
0x14000b9cc  mov     eax, 800700EAh
0x14000b9d1  cmp     ecx, eax
0x14000b9d3  jg      loc_14000BAA8
0x14000b9d9  jz      loc_14000BA9E
0x14000b9df  mov     eax, 80070057h
0x14000b9e4  cmp     ecx, eax
0x14000b9e6  jg      short loc_14000BA52
0x14000b9e8  jz      short loc_14000BA48
0x14000b9ea  cmp     ecx, 80004005h
0x14000b9f0  jz      short loc_14000BA3E
0x14000b9f2  cmp     ecx, 80070001h
0x14000b9f8  jz      short loc_14000BA34
0x14000b9fa  cmp     ecx, 80070002h
0x14000ba00  jz      short loc_14000BA2A
0x14000ba02  cmp     ecx, 80070003h
0x14000ba08  jz      short loc_14000BA20
0x14000ba0a  cmp     ecx, 8007000Eh
0x14000ba10  jnz     loc_14000BB2D
0x14000ba16  mov     ecx, 0C0000017h
0x14000ba1b  jmp     loc_14000BB85
0x14000ba20  mov     ecx, 0C000003Ah
0x14000ba25  jmp     loc_14000BB85
0x14000ba2a  mov     ecx, 0C0000034h
0x14000ba2f  jmp     loc_14000BB85
0x14000ba34  mov     ecx, 0C0000002h
0x14000ba39  jmp     loc_14000BB85
0x14000ba3e  mov     ecx, 0C0000001h
0x14000ba43  jmp     loc_14000BB85
0x14000ba48  mov     ecx, 0C000000Dh
0x14000ba4d  jmp     loc_14000BB85
0x14000ba52  cmp     ecx, 80070070h
0x14000ba58  jz      short loc_14000BA94
0x14000ba5a  cmp     ecx, 8007007Ah
0x14000ba60  jz      short loc_14000BA8A
0x14000ba62  cmp     ecx, 8007007Bh
0x14000ba68  jz      short loc_14000BA80
0x14000ba6a  cmp     ecx, 8007007Eh
0x14000ba70  jnz     loc_14000BB2D
0x14000ba76  mov     ecx, 0C0000135h
0x14000ba7b  jmp     loc_14000BB85
0x14000ba80  mov     ecx, 0C0000033h
0x14000ba85  jmp     loc_14000BB85
0x14000ba8a  mov     ecx, 0C0000023h
0x14000ba8f  jmp     loc_14000BB85
0x14000ba94  mov     ecx, 0C000007Fh
0x14000ba99  jmp     loc_14000BB85
0x14000ba9e  mov     ecx, 80000005h
0x14000baa3  jmp     loc_14000BB85
0x14000baa8  mov     eax, 8007047Eh
0x14000baad  cmp     ecx, eax
0x14000baaf  jg      short loc_14000BB11
0x14000bab1  jz      short loc_14000BB0A
0x14000bab3  cmp     ecx, 80070216h
0x14000bab9  jz      short loc_14000BB03
0x14000babb  cmp     ecx, 8007023Eh
0x14000bac1  jz      short loc_14000BAF9
0x14000bac3  cmp     ecx, 80070246h
0x14000bac9  jz      short loc_14000BAEF
0x14000bacb  cmp     ecx, 80070247h
0x14000bad1  jz      short loc_14000BAE5
0x14000bad3  cmp     ecx, 80070272h
0x14000bad9  jnz     short loc_14000BB2D
0x14000badb  mov     ecx, 0C0000273h
0x14000bae0  jmp     loc_14000BB85
0x14000bae5  mov     ecx, 0C0000163h
0x14000baea  jmp     loc_14000BB85
0x14000baef  mov     ecx, 0C0000161h
0x14000baf4  jmp     loc_14000BB85
0x14000baf9  mov     ecx, 0C0000025h
0x14000bafe  jmp     loc_14000BB85
0x14000bb03  mov     ecx, 0C0000095h
0x14000bb08  jmp     short loc_14000BB85
0x14000bb0a  mov     ecx, 0C0000059h
0x14000bb0f  jmp     short loc_14000BB85
0x14000bb11  cmp     ecx, 8007050Ch
0x14000bb17  jz      short loc_14000BB80
0x14000bb19  cmp     ecx, 8007054Fh
0x14000bb1f  jz      short loc_14000BB79
0x14000bb21  cmp     ecx, 800705B9h
0x14000bb27  jz      short loc_14000BB72
0x14000bb29  test    ecx, ecx
0x14000bb2b  jz      short loc_14000BB6E
0x14000bb2d  bt      ecx, 1Ch
0x14000bb31  jnb     short loc_14000BB39
0x14000bb33  btr     ecx, 1Ch
0x14000bb37  jmp     short loc_14000BB85
0x14000bb39  mov     eax, ecx
0x14000bb3b  and     eax, 1FFF0000h
0x14000bb40  cmp     eax, 70000h
0x14000bb45  jnz     short loc_14000BB58
0x14000bb47  movzx   ecx, cx
0x14000bb4a  mov     eax, ecx
0x14000bb4c  or      eax, 0C0070000h
0x14000bb51  test    ecx, ecx
0x14000bb53  cmovnz  ecx, eax
0x14000bb56  jmp     short loc_14000BB85
0x14000bb58  cmp     eax, 90000h
0x14000bb5d  jnz     short loc_14000BB79
0x14000bb5f  test    ecx, ecx
0x14000bb61  jle     short loc_14000BB85
0x14000bb63  movzx   ecx, cx
0x14000bb66  or      ecx, 0C0090000h
0x14000bb6c  jmp     short loc_14000BB85
0x14000bb6e  xor     ecx, ecx
0x14000bb70  jmp     short loc_14000BB85
0x14000bb72  mov     ecx, 0C000A083h
0x14000bb77  jmp     short loc_14000BB85
0x14000bb79  mov     ecx, 0C00000E5h
0x14000bb7e  jmp     short loc_14000BB85
0x14000bb80  mov     ecx, 0C000042Bh
0x14000bb85  mov     eax, ecx
0x14000bb87  retn
```
