# Dhcpv6CompareMode

- ea: `0x18000f3a4`
- end: `0x18000f3e6`
- name: `Dhcpv6CompareMode`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010088`
- `0x180011e04`

## callees

- `0x18000f3a4`
- `0x1800190a4`
- `0x1800191fc`

## pseudocode

```c
_BOOL8 __fastcall Dhcpv6CompareMode(__int64 a1)
{
  unsigned int v1; // edx
  unsigned int v3; // edx

  if ( (unsigned int)IsModeStateful(a1) )
  {
    if ( (unsigned int)IsModeStateful(v1) )
      return 1;
  }
  else if ( (unsigned int)((__int64 (*)(void))IsModeStateLess)() )
  {
    return (unsigned int)IsModeStateLess(v3) != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f3a4  sub     rsp, 28h
0x18000f3a8  call    IsModeStateful
0x18000f3ad  test    eax, eax
0x18000f3af  jz      short loc_18000F3C3
0x18000f3b1  mov     ecx, edx
0x18000f3b3  call    IsModeStateful
0x18000f3b8  test    eax, eax
0x18000f3ba  jz      short loc_18000F3DE
0x18000f3bc  mov     eax, 1
0x18000f3c1  jmp     short loc_18000F3E0
0x18000f3c3  call    IsModeStateLess
0x18000f3c8  test    eax, eax
0x18000f3ca  jz      short loc_18000F3DE
0x18000f3cc  mov     ecx, edx
0x18000f3ce  call    IsModeStateLess
0x18000f3d3  xor     ecx, ecx
0x18000f3d5  test    eax, eax
0x18000f3d7  setnz   cl
0x18000f3da  mov     eax, ecx
0x18000f3dc  jmp     short loc_18000F3E0
0x18000f3de  xor     eax, eax
0x18000f3e0  add     rsp, 28h
0x18000f3e4  retn
```
