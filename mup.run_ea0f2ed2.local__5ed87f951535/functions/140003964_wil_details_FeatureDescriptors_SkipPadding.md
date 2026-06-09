# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140003964`
- end: `0x140003986`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140011d1c`
- `0x140011e54`
- `0x140011ef0`
- `0x140011f6c`
- `0x140011ff0`
- `0x1400210f4`
- `0x1400211b4`

## callees

- `0x140003964`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( a1 < wil_details_featureDescriptors_a )
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
0x140003964  xchg    ax, ax
0x140003966  lea     rax, wil_details_featureDescriptors_a
0x14000396d  cmp     rcx, rax
0x140003970  jnb     short loc_140003983
0x140003972  cmp     qword ptr [rcx], 0
0x140003976  jnz     short loc_14000397E
0x140003978  add     rcx, 8
0x14000397c  jmp     short loc_140003966
0x14000397e  mov     rax, rcx
0x140003981  retn
0x140003983  xor     eax, eax
0x140003985  retn
```
