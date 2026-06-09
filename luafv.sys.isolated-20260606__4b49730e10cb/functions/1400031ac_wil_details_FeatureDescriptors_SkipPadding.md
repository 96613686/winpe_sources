# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x1400031ac`
- end: `0x1400031ce`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14001692c`
- `0x140016abc`
- `0x140016b50`
- `0x140016bcc`
- `0x140016c50`
- `0x1400294b4`
- `0x140029574`

## callees

- `0x1400031ac`

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
0x1400031ac  xchg    ax, ax
0x1400031ae  lea     rax, wil_details_featureDescriptors_z
0x1400031b5  cmp     rcx, rax
0x1400031b8  jnb     short loc_1400031CB
0x1400031ba  cmp     qword ptr [rcx], 0
0x1400031be  jnz     short loc_1400031C6
0x1400031c0  add     rcx, 8
0x1400031c4  jmp     short loc_1400031AE
0x1400031c6  mov     rax, rcx
0x1400031c9  retn
0x1400031cb  xor     eax, eax
0x1400031cd  retn
```
