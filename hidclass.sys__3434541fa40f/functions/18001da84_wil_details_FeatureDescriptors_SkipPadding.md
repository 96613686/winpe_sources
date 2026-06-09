# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x18001da84`
- end: `0x18001daa6`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18003923c`
- `0x180039374`
- `0x180039410`
- `0x18003948c`
- `0x180039510`
- `0x180045078`
- `0x180045138`

## callees

- `0x18001da84`

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
0x18001da84  xchg    ax, ax
0x18001da86  lea     rax, wil_details_featureDescriptors_z
0x18001da8d  cmp     rcx, rax
0x18001da90  jnb     short loc_18001DAA3
0x18001da92  cmp     qword ptr [rcx], 0
0x18001da96  jnz     short loc_18001DA9E
0x18001da98  add     rcx, 8
0x18001da9c  jmp     short loc_18001DA86
0x18001da9e  mov     rax, rcx
0x18001daa1  retn
0x18001daa3  xor     eax, eax
0x18001daa5  retn
```
