# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140003c24`
- end: `0x140003c46`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400185dc`
- `0x1400187f0`
- `0x14001887c`
- `0x140018900`
- `0x14002e8a0`
- `0x14002e960`

## callees

- `0x140003c24`

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
0x140003c24  xchg    ax, ax
0x140003c26  lea     rax, wil_details_featureDescriptors_a
0x140003c2d  cmp     rcx, rax
0x140003c30  jnb     short loc_140003C43
0x140003c32  cmp     qword ptr [rcx], 0
0x140003c36  jnz     short loc_140003C3E
0x140003c38  add     rcx, 8
0x140003c3c  jmp     short loc_140003C26
0x140003c3e  mov     rax, rcx
0x140003c41  retn
0x140003c43  xor     eax, eax
0x140003c45  retn
```
