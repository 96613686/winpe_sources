# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140004c24`
- end: `0x140004c44`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `32`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e7a0`
- `0x14000e930`
- `0x14000e9d0`
- `0x14000ea4c`
- `0x14000ead0`
- `0x1400134c8`
- `0x140013588`

## callees

- `0x140004c24`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( 1 )
  {
    if ( a1 >= wil_details_featureDescriptors_a )
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
0x140004c24  lea     rax, wil_details_featureDescriptors_a
0x140004c2b  jmp     short loc_140004C37
0x140004c2d  cmp     qword ptr [rcx], 0
0x140004c31  jnz     short loc_140004C40
0x140004c33  add     rcx, 8
0x140004c37  cmp     rcx, rax
0x140004c3a  jb      short loc_140004C2D
0x140004c3c  xor     eax, eax
0x140004c3e  retn
0x140004c40  mov     rax, rcx
0x140004c43  retn
```
