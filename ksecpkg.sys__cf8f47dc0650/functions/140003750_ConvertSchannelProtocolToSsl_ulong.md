# ConvertSchannelProtocolToSsl(ulong)

- ea: `0x140003750`
- end: `0x1400037d6`
- name: `?ConvertSchannelProtocolToSsl@@YAGK@Z`
- size: `134`
- prototype: `unsigned __int16 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003530`
- `0x14000b920`

## callees

- `0x140003750`

## pseudocode

```c
unsigned __int16 __fastcall ConvertSchannelProtocolToSsl(int a1)
{
  unsigned __int16 result; // ax

  if ( (a1 & 0x3FFC) != 0 && (a1 & 0xF0000) != 0 )
    return 0;
  if ( (a1 & 0xC0000) != 0 )
    return -259;
  if ( (a1 & 0x30000) != 0 )
    return -257;
  if ( (a1 & 0x3000) != 0 )
    return 772;
  if ( (a1 & 0xC00) != 0 )
    return 771;
  result = 768;
  if ( (a1 & 0x300) != 0 )
    return 770;
  if ( (a1 & 0xC0) != 0 )
    return 769;
  if ( (a1 & 0x30) == 0 )
  {
    result = 0;
    if ( (a1 & 0xC) != 0 )
      return 2;
  }
  return result;
}

```

## disassembly

```asm
0x140003750  test    ecx, 3FFCh
0x140003756  setnz   dl
0x140003759  test    ecx, 0F0000h
0x14000375f  setnz   al
0x140003762  test    al, dl
0x140003764  jnz     short loc_140003785
0x140003766  test    ecx, 0C0000h
0x14000376c  jnz     short loc_140003789
0x14000376e  test    ecx, 30000h
0x140003774  jnz     short loc_140003790
0x140003776  test    ecx, 3000h
0x14000377c  jz      short loc_140003797
0x14000377e  mov     eax, 304h
0x140003783  retn
0x140003785  xor     eax, eax
0x140003787  retn
0x140003789  mov     eax, 0FEFDh
0x14000378e  retn
0x140003790  mov     eax, 0FEFFh
0x140003795  retn
0x140003797  test    ecx, 0C00h
0x14000379d  jz      short loc_1400037A6
0x14000379f  mov     eax, 303h
0x1400037a4  retn
0x1400037a6  mov     eax, 300h
0x1400037ab  test    eax, ecx
0x1400037ad  jz      short loc_1400037B6
0x1400037af  mov     eax, 302h
0x1400037b4  retn
0x1400037b6  test    cl, 0C0h
0x1400037b9  jz      short loc_1400037C2
0x1400037bb  mov     eax, 301h
0x1400037c0  retn
0x1400037c2  test    cl, 30h
0x1400037c5  jnz     short locret_140003783
0x1400037c7  xor     eax, eax
0x1400037c9  mov     edx, 2
0x1400037ce  test    cl, 0Ch
0x1400037d1  cmovnz  ax, dx
0x1400037d5  retn
```
