# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x18000b834`
- end: `0x18000b856`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180021424`
- `0x180021630`
- `0x1800216bc`
- `0x180021740`
- `0x18002b6ec`
- `0x18002b7ac`

## callees

- `0x18000b834`

## pseudocode

```c
_QWORD *__fastcall wil_details_FeatureDescriptors_SkipPadding(_QWORD *a1)
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
0x18000b834  xchg    ax, ax
0x18000b836  lea     rax, wil_details_featureDescriptors_z
0x18000b83d  cmp     rcx, rax
0x18000b840  jnb     short loc_18000B853
0x18000b842  cmp     qword ptr [rcx], 0
0x18000b846  jnz     short loc_18000B84E
0x18000b848  add     rcx, 8
0x18000b84c  jmp     short loc_18000B836
0x18000b84e  mov     rax, rcx
0x18000b851  retn
0x18000b853  xor     eax, eax
0x18000b855  retn
```
