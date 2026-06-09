# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x1400057a0`
- end: `0x1400057c0`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `32`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f010`
- `0x14000f780`
- `0x14000f7fc`
- `0x140011010`

## callees

- `0x1400057a0`

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
0x1400057a0  lea     rax, wil_details_featureDescriptors_z
0x1400057a7  cmp     rcx, rax
0x1400057aa  jnb     short loc_1400057BD
0x1400057ac  cmp     qword ptr [rcx], 0
0x1400057b0  jnz     short loc_1400057B8
0x1400057b2  add     rcx, 8
0x1400057b6  jmp     short loc_1400057A7
0x1400057b8  mov     rax, rcx
0x1400057bb  retn
0x1400057bd  xor     eax, eax
0x1400057bf  retn
```
