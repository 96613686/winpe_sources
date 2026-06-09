# CompressGetSize

- ea: `0x180002070`
- end: `0x18000207b`
- name: `CompressGetSize`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## pseudocode

```c
__int64 __fastcall CompressGetSize(__int64 a1)
{
  return (unsigned int)(3 * *(_DWORD *)(a1 + 4) * *(_DWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180002070  mov     eax, [rcx+8]
0x180002073  imul    eax, [rcx+4]
0x180002077  lea     eax, [rax+rax*2]
0x18000207a  retn
```
