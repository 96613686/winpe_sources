# __scrt_uninitialize_thread_safe_statics

- ea: `0x180020110`
- end: `0x180020138`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180020110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002011b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002011b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002012d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002012d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800898C0);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180020110  sub     rsp, 28h
0x180020114  lea     rcx, stru_1800898C0; lpCriticalSection
0x18002011b  call    cs:__imp_DeleteCriticalSection
0x180020121  mov     rcx, cs:hHandle; hObject
0x180020128  test    rcx, rcx
0x18002012b  jz      short loc_180020133
0x18002012d  call    cs:__imp_CloseHandle
0x180020133  add     rsp, 28h
0x180020137  retn
```
