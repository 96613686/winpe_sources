# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004b90`
- end: `0x180004bb8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004b90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004b9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004b9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bad`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180032A78);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180004b90  sub     rsp, 28h
0x180004b94  lea     rcx, stru_180032A78; lpCriticalSection
0x180004b9b  call    cs:__imp_DeleteCriticalSection
0x180004ba1  mov     rcx, cs:hHandle; hObject
0x180004ba8  test    rcx, rcx
0x180004bab  jz      short loc_180004BB3
0x180004bad  call    cs:__imp_CloseHandle
0x180004bb3  add     rsp, 28h
0x180004bb7  retn
```
