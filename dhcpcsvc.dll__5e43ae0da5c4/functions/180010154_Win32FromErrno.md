# Win32FromErrno

- ea: `0x180010154`
- end: `0x180010192`
- name: `Win32FromErrno`
- size: `62`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007dd0`
- `0x180009d40`
- `0x18000a4d0`
- `0x18000c540`
- `0x18000fdc4`

## callees

- `0x180010154`

## pseudocode

```c
__int64 __fastcall Win32FromErrno(int a1)
{
  __int64 result; // rax

  switch ( a1 )
  {
    case 0:
      return 0;
    case 7:
      return 160;
    case 11:
      return 1450;
    case 13:
      return 5;
    case 22:
      return 160;
  }
  result = 474;
  if ( a1 != 34 )
    return 31;
  return result;
}

```

## disassembly

```asm
0x180010154  test    ecx, ecx
0x180010156  jz      short loc_18001018F
0x180010158  cmp     ecx, 7
0x18001015b  jz      short loc_180010189
0x18001015d  cmp     ecx, 0Bh
0x180010160  jz      short loc_180010183
0x180010162  cmp     ecx, 0Dh
0x180010165  jz      short loc_18001017D
0x180010167  cmp     ecx, 16h
0x18001016a  jz      short loc_180010189
0x18001016c  cmp     ecx, 22h ; '"'
0x18001016f  mov     eax, 1DAh
0x180010174  mov     edx, 1Fh
0x180010179  cmovnz  eax, edx
0x18001017c  retn
0x18001017d  mov     eax, 5
0x180010182  retn
0x180010183  mov     eax, 5AAh
0x180010188  retn
0x180010189  mov     eax, 0A0h
0x18001018e  retn
0x18001018f  xor     eax, eax
0x180010191  retn
```
