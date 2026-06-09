# Common::GlobalHeap::Free(void *)

- ea: `0x180002ad0`
- end: `0x180002ae9`
- name: `?Free@GlobalHeap@Common@@SAXPEAX@Z`
- size: `25`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001610`
- `0x180001ef0`
- `0x1800020d0`
- `0x1800029c0`
- `0x180009a80`
- `0x180009c20`

## callees

- `0x180002ad0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002ae1`

## pseudocode

```c
void __fastcall Common::GlobalHeap::Free(void *a1)
{
  if ( a1 )
    RtlFreeHeap(ReservedForLocalUse::g_heap, 0, a1);
}

```

## disassembly

```asm
0x180002ad0  test    rcx, rcx
0x180002ad3  jz      short locret_180002AE8
0x180002ad5  mov     r8, rcx
0x180002ad8  xor     edx, edx
0x180002ada  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; void * ReservedForLocalUse::g_heap
0x180002ae1  jmp     cs:__imp_RtlFreeHeap
0x180002ae8  retn
```
