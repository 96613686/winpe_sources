# ImageCompareSectionNames

- ea: `0x1400023b8`
- end: `0x1400023e0`
- name: `ImageCompareSectionNames`
- size: `40`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011178`

## callees

- `0x1400023b8`

## pseudocode

```c
char __fastcall ImageCompareSectionNames(__int64 a1)
{
  __int64 i; // rdx
  char v2; // r8

  for ( i = 0; (unsigned int)i < 9; i = (unsigned int)(i + 1) )
  {
    v2 = *(_BYTE *)(i + a1);
    if ( v2 != aRdata[i] )
      break;
    if ( !v2 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1400023b8  xor     edx, edx
0x1400023ba  cmp     edx, 9
0x1400023bd  jnb     short loc_1400023DD
0x1400023bf  mov     r8b, [rdx+rcx]
0x1400023c3  lea     r9, aRdata; ".rdata"
0x1400023ca  cmp     r8b, [rdx+r9]
0x1400023ce  jnz     short loc_1400023DD
0x1400023d0  test    r8b, r8b
0x1400023d3  jz      short loc_1400023D9
0x1400023d5  inc     edx
0x1400023d7  jmp     short loc_1400023BA
0x1400023d9  mov     al, 1
0x1400023db  retn
0x1400023dd  xor     al, al
0x1400023df  retn
```
