# AllTracksUnblocked

- ea: `0x180005808`
- end: `0x180005836`
- name: `AllTracksUnblocked`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000484c`
- `0x1800048fc`
- `0x180005a1c`
- `0x180005d4c`

## callees

- `0x180005808`

## pseudocode

```c
__int64 __fastcall AllTracksUnblocked(__int64 a1)
{
  unsigned int v1; // r8d
  __int64 v2; // rdx

  v1 = *(_DWORD *)(a1 + 984);
  if ( !v1 )
    return 1;
  v2 = 0;
  while ( !**(_DWORD **)(*(_QWORD *)(a1 + 976) + 8 * v2) )
  {
    v2 = (unsigned int)(v2 + 1);
    if ( (unsigned int)v2 >= v1 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180005808  mov     r8d, [rcx+3D8h]
0x18000580f  test    r8d, r8d
0x180005812  jz      short loc_18000582D
0x180005814  mov     r9, [rcx+3D0h]
0x18000581b  xor     edx, edx
0x18000581d  mov     rcx, [r9+rdx*8]
0x180005821  cmp     dword ptr [rcx], 0
0x180005824  jnz     short loc_180005833
0x180005826  inc     edx
0x180005828  cmp     edx, r8d
0x18000582b  jb      short loc_18000581D
0x18000582d  mov     eax, 1
0x180005832  retn
0x180005833  xor     eax, eax
0x180005835  retn
```
