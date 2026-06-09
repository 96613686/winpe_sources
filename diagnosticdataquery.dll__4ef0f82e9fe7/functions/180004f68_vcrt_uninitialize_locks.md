# __vcrt_uninitialize_locks

- ea: `0x180004f68`
- end: `0x180004f9f`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bf0`
- `0x180002c54`
- `0x180004f18`

## callees

- `0x180004f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f87`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180014358;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_180014330[5 * (unsigned int)--v0]);
    --dword_180014358;
  }
  return 1;
}

```

## disassembly

```asm
0x180004f68  push    rbx
0x180004f6a  sub     rsp, 20h
0x180004f6e  mov     ebx, cs:dword_180014358
0x180004f74  jmp     short loc_180004F93
0x180004f76  lea     rax, qword_180014330
0x180004f7d  dec     ebx
0x180004f7f  lea     rcx, [rbx+rbx*4]
0x180004f83  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180004f87  call    cs:__imp_DeleteCriticalSection
0x180004f8d  dec     cs:dword_180014358
0x180004f93  test    ebx, ebx
0x180004f95  jnz     short loc_180004F76
0x180004f97  mov     al, 1
0x180004f99  add     rsp, 20h
0x180004f9d  pop     rbx
0x180004f9e  retn
```
