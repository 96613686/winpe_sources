# AscendingTagCompare

- ea: `0x18000d3a0`
- end: `0x18000d3b1`
- name: `AscendingTagCompare`
- size: `17`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d3a0`

## pseudocode

```c
__int64 __fastcall AscendingTagCompare(_DWORD *a1, _DWORD *a2)
{
  if ( *a1 == *a2 )
    return 0;
  else
    return *a1 < *a2 ? -1 : 1;
}

```

## disassembly

```asm
0x18000d3a0  mov     eax, [rcx]
0x18000d3a2  cmp     eax, [rdx]
0x18000d3a4  jnz     short loc_18000D3A9
0x18000d3a6  xor     eax, eax
0x18000d3a8  retn
0x18000d3a9  sbb     eax, eax
0x18000d3ab  and     eax, 0FFFFFFFEh
0x18000d3ae  inc     eax
0x18000d3b0  retn
```
