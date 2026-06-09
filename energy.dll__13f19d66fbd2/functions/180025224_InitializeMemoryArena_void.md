# InitializeMemoryArena(void)

- ea: `0x180025224`
- end: `0x180025272`
- name: `?InitializeMemoryArena@@YAHXZ`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007920`
- `0x180008da0`
- `0x1800250cc`
- `0x180025170`
- `0x1800251c0`

## callees

- `0x180025224`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18002524d`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18002524d`

## pseudocode

```c
_BOOL8 InitializeMemoryArena(void)
{
  _BOOL8 result; // rax
  HANDLE v1; // rax

  result = 1;
  if ( !NewOperatorMemoryArena )
  {
    if ( _InterlockedIncrement(&MemoryArenaInUse) > 1 )
    {
      v1 = NewOperatorMemoryArena;
    }
    else
    {
      v1 = HeapCreate(0, 0, 0);
      NewOperatorMemoryArena = v1;
    }
    return v1 != 0;
  }
  return result;
}

```

## disassembly

```asm
0x180025224  sub     rsp, 28h
0x180025228  cmp     cs:?NewOperatorMemoryArena@@3U__MemoryArena@@A, 0; __MemoryArena NewOperatorMemoryArena
0x180025230  mov     eax, 1
0x180025235  jnz     short loc_18002526D
0x180025237  lock xadd cs:?MemoryArenaInUse@@3JC, eax; long volatile MemoryArenaInUse
0x18002523f  inc     eax
0x180025241  cmp     eax, 1
0x180025244  jg      short loc_18002525C
0x180025246  xor     r8d, r8d; dwMaximumSize
0x180025249  xor     edx, edx; dwInitialSize
0x18002524b  xor     ecx, ecx; flOptions
0x18002524d  call    cs:__imp_HeapCreate
0x180025253  mov     cs:?NewOperatorMemoryArena@@3U__MemoryArena@@A, rax; __MemoryArena NewOperatorMemoryArena
0x18002525a  jmp     short loc_180025263
0x18002525c  mov     rax, cs:?NewOperatorMemoryArena@@3U__MemoryArena@@A; __MemoryArena NewOperatorMemoryArena
0x180025263  xor     ecx, ecx
0x180025265  test    rax, rax
0x180025268  setnz   cl
0x18002526b  mov     eax, ecx
0x18002526d  add     rsp, 28h
0x180025271  retn
```
