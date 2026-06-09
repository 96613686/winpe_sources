# __scrt_uninitialize_thread_safe_statics

- ea: `0x140005610`
- end: `0x140005638`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000561b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000561b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000562d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000562d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_140084CD0);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x140005610  sub     rsp, 28h
0x140005614  lea     rcx, stru_140084CD0; lpCriticalSection
0x14000561b  call    cs:__imp_DeleteCriticalSection
0x140005621  mov     rcx, cs:hHandle; hObject
0x140005628  test    rcx, rcx
0x14000562b  jz      short loc_140005633
0x14000562d  call    cs:__imp_CloseHandle
0x140005633  add     rsp, 28h
0x140005637  retn
```
