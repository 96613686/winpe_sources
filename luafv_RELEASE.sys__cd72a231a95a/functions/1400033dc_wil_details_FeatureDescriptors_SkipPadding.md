# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x1400033dc`
- end: `0x1400033fe`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14001692c`
- `0x140016a64`
- `0x140016b00`
- `0x140016b7c`
- `0x140016c00`
- `0x1400294b4`
- `0x140029574`

## callees

- `0x1400033dc`

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
0x1400033dc  xchg    ax, ax
0x1400033de  lea     rax, wil_details_featureDescriptors_z
0x1400033e5  cmp     rcx, rax
0x1400033e8  jnb     short loc_1400033FB
0x1400033ea  cmp     qword ptr [rcx], 0
0x1400033ee  jnz     short loc_1400033F6
0x1400033f0  add     rcx, 8
0x1400033f4  jmp     short loc_1400033DE
0x1400033f6  mov     rax, rcx
0x1400033f9  retn
0x1400033fb  xor     eax, eax
0x1400033fd  retn
```
