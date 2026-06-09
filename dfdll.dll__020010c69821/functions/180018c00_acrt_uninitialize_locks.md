# __acrt_uninitialize_locks

- ea: `0x180018c00`
- end: `0x180018c37`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018b90`

## callees

- `0x180018c00`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180018c1f`
- `KERNEL32!DeleteCriticalSection` at `0x180018c1f`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18002E508;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18002E300[5 * (unsigned int)--v0]);
    --dword_18002E508;
  }
  return 1;
}

```

## disassembly

```asm
0x180018c00  push    rbx
0x180018c02  sub     rsp, 20h
0x180018c06  mov     ebx, cs:dword_18002E508
0x180018c0c  jmp     short loc_180018C2B
0x180018c0e  lea     rax, qword_18002E300
0x180018c15  dec     ebx
0x180018c17  lea     rcx, [rbx+rbx*4]
0x180018c1b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180018c1f  call    cs:__imp_DeleteCriticalSection
0x180018c25  dec     cs:dword_18002E508
0x180018c2b  test    ebx, ebx
0x180018c2d  jnz     short loc_180018C0E
0x180018c2f  mov     al, 1
0x180018c31  add     rsp, 20h
0x180018c35  pop     rbx
0x180018c36  retn
```
