# MupiGetFirstUncHardeningConfigurationEntry

- ea: `0x14001e9f0`
- end: `0x14001ea01`
- name: `MupiGetFirstUncHardeningConfigurationEntry`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400157e8`
- `0x1400158a4`

## callees

- `0x14001e9f0`

## pseudocode

```c
__int64 __fastcall MupiGetFirstUncHardeningConfigurationEntry(_QWORD *a1)
{
  if ( (_QWORD *)*a1 == a1 )
    return 0;
  else
    return *a1 - 8LL;
}

```

## disassembly

```asm
0x14001e9f0  mov     rax, [rcx]
0x14001e9f3  cmp     rax, rcx
0x14001e9f6  jz      short loc_14001E9FE
0x14001e9f8  add     rax, 0FFFFFFFFFFFFFFF8h
0x14001e9fc  retn
0x14001e9fe  xor     eax, eax
0x14001ea00  retn
```
