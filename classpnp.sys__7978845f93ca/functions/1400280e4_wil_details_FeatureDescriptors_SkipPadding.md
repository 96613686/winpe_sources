# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x1400280e4`
- end: `0x140028106`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14005adc0`
- `0x14005af50`
- `0x14005aff0`
- `0x14005b06c`
- `0x14005b0f0`
- `0x14006509c`
- `0x14006515c`

## callees

- `0x1400280e4`

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
0x1400280e4  xchg    ax, ax
0x1400280e6  lea     rax, wil_details_featureDescriptors_z
0x1400280ed  cmp     rcx, rax
0x1400280f0  jnb     short loc_140028103
0x1400280f2  cmp     qword ptr [rcx], 0
0x1400280f6  jnz     short loc_1400280FE
0x1400280f8  add     rcx, 8
0x1400280fc  jmp     short loc_1400280E6
0x1400280fe  mov     rax, rcx
0x140028101  retn
0x140028103  xor     eax, eax
0x140028105  retn
```
