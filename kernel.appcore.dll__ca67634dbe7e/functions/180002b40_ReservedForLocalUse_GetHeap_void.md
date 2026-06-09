# ReservedForLocalUse::GetHeap(void)

- ea: `0x180002b40`
- end: `0x180002b61`
- name: `?GetHeap@ReservedForLocalUse@@YAPEAXXZ`
- size: `33`
- prototype: `void *__fastcall(ReservedForLocalUse *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002af0`
- `0x180009c4c`

## callees

- `0x180002b40`

## pseudocode

```c
PVOID __fastcall ReservedForLocalUse::GetHeap(ReservedForLocalUse *this)
{
  PVOID result; // rax

  result = ReservedForLocalUse::g_heap;
  if ( !ReservedForLocalUse::g_heap )
  {
    result = NtCurrentPeb()->ProcessHeap;
    ReservedForLocalUse::g_heap = result;
  }
  return result;
}

```

## disassembly

```asm
0x180002b40  mov     rax, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; void * ReservedForLocalUse::g_heap
0x180002b47  test    rax, rax
0x180002b4a  jnz     short locret_180002B60
0x180002b4c  mov     rax, gs:60h
0x180002b55  mov     rax, [rax+30h]
0x180002b59  mov     cs:?g_heap@ReservedForLocalUse@@3PEAXEA, rax; void * ReservedForLocalUse::g_heap
0x180002b60  retn
```
