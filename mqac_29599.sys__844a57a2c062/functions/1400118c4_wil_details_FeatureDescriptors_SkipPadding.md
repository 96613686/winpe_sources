# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x1400118c4`
- end: `0x1400118e4`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `32`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14002f5cc`
- `0x14002f7e0`
- `0x14002f86c`
- `0x14002f8f0`
- `0x140030078`
- `0x140030138`

## callees

- `0x1400118c4`

## pseudocode

```c
_QWORD *__fastcall wil_details_FeatureDescriptors_SkipPadding(_QWORD *a1)
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
0x1400118c4  lea     rax, wil_details_featureDescriptors_a
0x1400118cb  jmp     short loc_1400118D7
0x1400118cd  cmp     qword ptr [rcx], 0
0x1400118d1  jnz     short loc_1400118E0
0x1400118d3  add     rcx, 8
0x1400118d7  cmp     rcx, rax
0x1400118da  jb      short loc_1400118CD
0x1400118dc  xor     eax, eax
0x1400118de  retn
0x1400118e0  mov     rax, rcx
0x1400118e3  retn
```
