# RtlStringCbLengthW

- ea: `0x140001190`
- end: `0x1400011e0`
- name: `RtlStringCbLengthW`
- size: `80`
- prototype: `NTSTATUS __stdcall(STRSAFE_PCNZWCH psz, size_t cbMax, size_t *pcbLength)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d9a8`
- `0x14000e340`
- `0x140010890`

## callees

- `0x140001190`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbLengthW(STRSAFE_PCNZWCH psz, size_t cbMax, size_t *pcbLength)
{
  __int64 v3; // rax
  NTSTATUS v4; // edx
  __int64 v5; // r9
  NTSTATUS result; // eax

  if ( psz )
  {
    v3 = 0x7FFFFFFF;
    do
    {
      if ( !*psz )
        break;
      ++psz;
      --v3;
    }
    while ( v3 );
    psz = 0;
    v4 = -1073741811;
    if ( v3 )
    {
      v4 = 0;
      v5 = 0x7FFFFFFF - v3;
      goto LABEL_7;
    }
  }
  else
  {
    v4 = -1073741811;
  }
  v5 = 0;
LABEL_7:
  result = v4;
  if ( pcbLength )
  {
    if ( v4 >= 0 )
      psz = (STRSAFE_PCNZWCH)(2 * v5);
    *pcbLength = (size_t)psz;
  }
  return result;
}

```

## disassembly

```asm
0x140001190  test    rcx, rcx
0x140001193  jz      short loc_1400011D6
0x140001195  mov     r9d, 7FFFFFFFh
0x14000119b  mov     eax, r9d
0x14000119e  xchg    ax, ax
0x1400011a0  cmp     word ptr [rcx], 0
0x1400011a4  jz      short loc_1400011B0
0x1400011a6  add     rcx, 2
0x1400011aa  sub     rax, 1
0x1400011ae  jnz     short loc_1400011A0
0x1400011b0  xor     ecx, ecx
0x1400011b2  mov     edx, 0C000000Dh
0x1400011b7  test    rax, rax
0x1400011ba  cmovnz  edx, ecx
0x1400011bd  jz      short loc_1400011DB
0x1400011bf  sub     r9, rax
0x1400011c2  mov     eax, edx
0x1400011c4  test    r8, r8
0x1400011c7  jz      short locret_1400011D4
0x1400011c9  test    edx, edx
0x1400011cb  js      short loc_1400011D1
0x1400011cd  lea     rcx, [r9+r9]
0x1400011d1  mov     [r8], rcx
0x1400011d4  retn
0x1400011d6  mov     edx, 0C000000Dh
0x1400011db  mov     r9, rcx
0x1400011de  jmp     short loc_1400011C2
```
