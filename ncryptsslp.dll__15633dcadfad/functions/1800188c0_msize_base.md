# _msize_base

- ea: `0x1800188c0`
- end: `0x1800188f9`
- name: `_msize_base`
- size: `57`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180018620`
- `0x180018900`

## callees

- `0x180014f34`
- `0x1800150d0`
- `0x1800188c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800188f2`

## pseudocode

```c
size_t __cdecl msize_base(void *Block)
{
  if ( Block )
    return HeapSize(_acrt_heap, 0, Block);
  *errno() = 22;
  invalid_parameter_noinfo();
  return -1;
}

```

## disassembly

```asm
0x1800188c0  sub     rsp, 28h
0x1800188c4  test    rcx, rcx
0x1800188c7  jnz     short loc_1800188E2
0x1800188c9  call    _errno
0x1800188ce  mov     dword ptr [rax], 16h
0x1800188d4  call    _invalid_parameter_noinfo
0x1800188d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800188dd  add     rsp, 28h
0x1800188e1  retn
0x1800188e2  mov     r8, rcx
0x1800188e5  xor     edx, edx
0x1800188e7  mov     rcx, cs:__acrt_heap
0x1800188ee  add     rsp, 28h
0x1800188f2  jmp     cs:__imp_HeapSize
```
