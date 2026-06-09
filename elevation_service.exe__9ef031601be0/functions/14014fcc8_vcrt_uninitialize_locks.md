# __vcrt_uninitialize_locks

- ea: `0x14014fcc8`
- end: `0x14014fcff`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140131304`
- `0x14013132c`
- `0x14014fc80`

## callees

- `0x14014fcc8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14014fce7`
- `KERNEL32!DeleteCriticalSection` at `0x14014fce7`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_14038C298;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14038C270[5 * (unsigned int)--v0]);
    --dword_14038C298;
  }
  return 1;
}

```

## disassembly

```asm
0x14014fcc8  push    rbx
0x14014fcca  sub     rsp, 20h
0x14014fcce  mov     ebx, cs:dword_14038C298
0x14014fcd4  jmp     short loc_14014FCF3
0x14014fcd6  lea     rax, qword_14038C270
0x14014fcdd  dec     ebx
0x14014fcdf  lea     rcx, [rbx+rbx*4]
0x14014fce3  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14014fce7  call    cs:DeleteCriticalSection
0x14014fced  dec     cs:dword_14038C298
0x14014fcf3  test    ebx, ebx
0x14014fcf5  jnz     short loc_14014FCD6
0x14014fcf7  mov     al, 1
0x14014fcf9  add     rsp, 20h
0x14014fcfd  pop     rbx
0x14014fcfe  retn
```
