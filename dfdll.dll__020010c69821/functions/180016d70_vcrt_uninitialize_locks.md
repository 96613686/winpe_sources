# __vcrt_uninitialize_locks

- ea: `0x180016d70`
- end: `0x180016da7`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180014aec`
- `0x180014b3c`
- `0x180016d3c`

## callees

- `0x180016d70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180016d8f`
- `KERNEL32!DeleteCriticalSection` at `0x180016d8f`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18002E0D0;
  while ( v0 )
  {
    DeleteCriticalSection(&stru_18002E0A8 + (unsigned int)--v0);
    --dword_18002E0D0;
  }
  return 1;
}

```

## disassembly

```asm
0x180016d70  push    rbx
0x180016d72  sub     rsp, 20h
0x180016d76  mov     ebx, cs:dword_18002E0D0
0x180016d7c  jmp     short loc_180016D9B
0x180016d7e  lea     rax, stru_18002E0A8
0x180016d85  dec     ebx
0x180016d87  lea     rcx, [rbx+rbx*4]
0x180016d8b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180016d8f  call    cs:__imp_DeleteCriticalSection
0x180016d95  dec     cs:dword_18002E0D0
0x180016d9b  test    ebx, ebx
0x180016d9d  jnz     short loc_180016D7E
0x180016d9f  mov     al, 1
0x180016da1  add     rsp, 20h
0x180016da5  pop     rbx
0x180016da6  retn
```
