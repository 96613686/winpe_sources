# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x14002d2b0`
- end: `0x14002d2d0`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `32`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140044d40`
- `0x140044ed0`
- `0x140044f70`
- `0x140044fec`
- `0x140045070`
- `0x1400531f8`
- `0x1400532b8`

## callees

- `0x14002d2b0`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( 1 )
  {
    if ( a1 >= wil_details_featureDescriptors_z )
      return 0;
    if ( *a1 )
      break;
    ++a1;
  }
  return a1;
}

```

## disassembly

```asm
0x14002d2b0  lea     rax, wil_details_featureDescriptors_z
0x14002d2b7  jmp     short loc_14002D2C3
0x14002d2b9  cmp     qword ptr [rcx], 0
0x14002d2bd  jnz     short loc_14002D2CC
0x14002d2bf  add     rcx, 8
0x14002d2c3  cmp     rcx, rax
0x14002d2c6  jb      short loc_14002D2B9
0x14002d2c8  xor     eax, eax
0x14002d2ca  retn
0x14002d2cc  mov     rax, rcx
0x14002d2cf  retn
```
