# ExtRawDllMain

- ea: `0x1800251c0`
- end: `0x18002521b`
- name: `ExtRawDllMain`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800251c0`
- `0x180025224`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800251d0`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800251d0`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800251fe`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800251fe`

## pseudocode

```c
__int64 __fastcall ExtRawDllMain(HMODULE a1, int a2, __int64 a3)
{
  if ( a2 == 1 )
  {
    InstanceHandle = a1;
    DisableThreadLibraryCalls(a1);
    return InitializeMemoryArena();
  }
  else
  {
    if ( !a2 && !a3 )
    {
      if ( NewOperatorMemoryArena )
      {
        HeapDestroy(NewOperatorMemoryArena);
        NewOperatorMemoryArena = 0;
        MemoryArenaInUse = 0;
      }
    }
    return 1;
  }
}

```

## disassembly

```asm
0x1800251c0  sub     rsp, 28h
0x1800251c4  cmp     edx, 1
0x1800251c7  jnz     short loc_1800251DF
0x1800251c9  mov     cs:?InstanceHandle@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * InstanceHandle
0x1800251d0  call    cs:__imp_DisableThreadLibraryCalls
0x1800251d6  add     rsp, 28h
0x1800251da  jmp     ?InitializeMemoryArena@@YAHXZ; InitializeMemoryArena(void)
0x1800251df  test    edx, edx
0x1800251e1  jz      short loc_1800251ED
0x1800251e3  mov     eax, 1
0x1800251e8  add     rsp, 28h
0x1800251ec  retn
0x1800251ed  test    r8, r8
0x1800251f0  jnz     short loc_1800251E3
0x1800251f2  mov     rcx, cs:?NewOperatorMemoryArena@@3U__MemoryArena@@A; hHeap
0x1800251f9  test    rcx, rcx
0x1800251fc  jz      short loc_1800251E3
0x1800251fe  call    cs:__imp_HeapDestroy
0x180025204  mov     cs:?NewOperatorMemoryArena@@3U__MemoryArena@@A, 0; __MemoryArena NewOperatorMemoryArena
0x18002520f  mov     cs:?MemoryArenaInUse@@3JC, 0; long volatile MemoryArenaInUse
0x180025219  jmp     short loc_1800251E3
```
