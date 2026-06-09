# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140007124`
- end: `0x140007146`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14002031c`
- `0x140020530`
- `0x1400205bc`
- `0x140020640`
- `0x140032184`
- `0x140032244`

## callees

- `0x140007124`

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
0x140007124  xchg    ax, ax
0x140007126  lea     rax, wil_details_featureDescriptors_z
0x14000712d  cmp     rcx, rax
0x140007130  jnb     short loc_140007143
0x140007132  cmp     qword ptr [rcx], 0
0x140007136  jnz     short loc_14000713E
0x140007138  add     rcx, 8
0x14000713c  jmp     short loc_140007126
0x14000713e  mov     rax, rcx
0x140007141  retn
0x140007143  xor     eax, eax
0x140007145  retn
```
