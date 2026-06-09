# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x14000a128`
- end: `0x14000a14a`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140017c0c`
- `0x140017d44`
- `0x140017de0`
- `0x140017e5c`
- `0x140017ee0`
- `0x1400219d8`
- `0x140021a98`

## callees

- `0x14000a128`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( a1 < wil_details_featureDescriptors_z )
  {
    if ( *a1 )
      return a1;
    ++a1;
  }
  return 0;
}

```

## disassembly

```asm
0x14000a128  xchg    ax, ax
0x14000a12a  lea     rax, wil_details_featureDescriptors_z
0x14000a131  cmp     rcx, rax
0x14000a134  jnb     short loc_14000A147
0x14000a136  cmp     qword ptr [rcx], 0
0x14000a13a  jnz     short loc_14000A142
0x14000a13c  add     rcx, 8
0x14000a140  jmp     short loc_14000A12A
0x14000a142  mov     rax, rcx
0x14000a145  retn
0x14000a147  xor     eax, eax
0x14000a149  retn
```
