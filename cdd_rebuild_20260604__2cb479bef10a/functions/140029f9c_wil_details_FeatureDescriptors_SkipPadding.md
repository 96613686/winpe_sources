# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140029f9c`
- end: `0x140029fbe`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140043168`
- `0x140043370`
- `0x1400433fc`
- `0x140043480`
- `0x1400472ec`
- `0x1400473ac`

## callees

- `0x140029f9c`

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
0x140029f9c  xchg    ax, ax
0x140029f9e  lea     rax, wil_details_featureDescriptors_z
0x140029fa5  cmp     rcx, rax
0x140029fa8  jnb     short loc_140029FBB
0x140029faa  cmp     qword ptr [rcx], 0
0x140029fae  jnz     short loc_140029FB6
0x140029fb0  add     rcx, 8
0x140029fb4  jmp     short loc_140029F9E
0x140029fb6  mov     rax, rcx
0x140029fb9  retn
0x140029fbb  xor     eax, eax
0x140029fbd  retn
```
