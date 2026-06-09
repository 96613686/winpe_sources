# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002bd0`
- end: `0x180002bf8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002bdb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002bdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002bed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002bed`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180002bd0  sub     rsp, 28h
0x180002bd4  lea     rcx, CriticalSection; lpCriticalSection
0x180002bdb  call    cs:__imp_DeleteCriticalSection
0x180002be1  mov     rcx, cs:hHandle; hObject
0x180002be8  test    rcx, rcx
0x180002beb  jz      short loc_180002BF3
0x180002bed  call    cs:__imp_CloseHandle
0x180002bf3  add     rsp, 28h
0x180002bf7  retn
```
