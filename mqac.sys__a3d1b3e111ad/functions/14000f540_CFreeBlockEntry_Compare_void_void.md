# CFreeBlockEntry::Compare(void *,void *)

- ea: `0x14000f540`
- end: `0x14000f545`
- name: `?Compare@CFreeBlockEntry@@SAHPEAX0@Z`
- size: `5`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CFreeBlockEntry::Compare(_DWORD *a1, _DWORD *a2)
{
  return (unsigned int)(*a1 - *a2);
}

```

## disassembly

```asm
0x14000f540  mov     eax, [rcx]
0x14000f542  sub     eax, [rdx]
0x14000f544  retn
```
