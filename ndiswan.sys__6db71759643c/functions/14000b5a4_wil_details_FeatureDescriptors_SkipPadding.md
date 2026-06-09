# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x14000b5a4`
- end: `0x14000b5c6`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14003758c`
- `0x14003771c`
- `0x1400377b0`
- `0x14003782c`
- `0x1400378b0`
- `0x1400396e8`
- `0x140039a50`

## callees

- `0x14000b5a4`

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
0x14000b5a4  xchg    ax, ax
0x14000b5a6  lea     rax, wil_details_featureDescriptors_z
0x14000b5ad  cmp     rcx, rax
0x14000b5b0  jnb     short loc_14000B5C3
0x14000b5b2  cmp     qword ptr [rcx], 0
0x14000b5b6  jnz     short loc_14000B5BE
0x14000b5b8  add     rcx, 8
0x14000b5bc  jmp     short loc_14000B5A6
0x14000b5be  mov     rax, rcx
0x14000b5c1  retn
0x14000b5c3  xor     eax, eax
0x14000b5c5  retn
```
