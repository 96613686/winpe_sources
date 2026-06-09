# _heapmin

- ea: `0x18001cf40`
- end: `0x18001cf85`
- name: `_heapmin`
- size: `69`
- prototype: `int __cdecl()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007e80`
- `0x180007f00`
- `0x18001cf40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf58`
- `api-ms-win-core-heap-l1-1-0!HeapCompact` at `0x18001cf4d`
- `api-ms-win-core-heap-l1-1-0!HeapCompact` at `0x18001cf4d`

## pseudocode

```c
int __cdecl heapmin()
{
  if ( HeapCompact(crtheap, 0) )
    return 0;
  if ( GetLastError() == 120 )
  {
    *_doserrno() = 120;
    *errno() = 40;
  }
  return -1;
}

```

## disassembly

```asm
0x18001cf40  sub     rsp, 28h
0x18001cf44  mov     rcx, cs:_crtheap; hHeap
0x18001cf4b  xor     edx, edx; dwFlags
0x18001cf4d  call    cs:__imp_HeapCompact
0x18001cf53  test    rax, rax
0x18001cf56  jnz     short loc_18001CF7E
0x18001cf58  call    cs:__imp_GetLastError
0x18001cf5e  cmp     eax, 78h ; 'x'
0x18001cf61  jnz     short loc_18001CF79
0x18001cf63  call    __doserrno
0x18001cf68  mov     dword ptr [rax], 78h ; 'x'
0x18001cf6e  call    _errno
0x18001cf73  mov     dword ptr [rax], 28h ; '('
0x18001cf79  or      eax, 0FFFFFFFFh
0x18001cf7c  jmp     short loc_18001CF80
0x18001cf7e  xor     eax, eax
0x18001cf80  add     rsp, 28h
0x18001cf84  retn
```
