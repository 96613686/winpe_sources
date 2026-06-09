# AscendingRecordIndexCompare

- ea: `0x18000d380`
- end: `0x18000d393`
- name: `AscendingRecordIndexCompare`
- size: `19`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d380`

## pseudocode

```c
__int64 __fastcall AscendingRecordIndexCompare(_WORD *a1, _WORD *a2)
{
  if ( *a1 == *a2 )
    return 0;
  else
    return *a1 < *a2 ? -1 : 1;
}

```

## disassembly

```asm
0x18000d380  movzx   eax, word ptr [rcx]
0x18000d383  cmp     ax, [rdx]
0x18000d386  jnz     short loc_18000D38B
0x18000d388  xor     eax, eax
0x18000d38a  retn
0x18000d38b  sbb     eax, eax
0x18000d38d  and     eax, 0FFFFFFFEh
0x18000d390  inc     eax
0x18000d392  retn
```
