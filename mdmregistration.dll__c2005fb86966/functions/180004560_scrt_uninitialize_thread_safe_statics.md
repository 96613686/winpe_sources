# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004560`
- end: `0x180004588`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000456b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000456b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000457d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000457d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180070A58);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180004560  sub     rsp, 28h
0x180004564  lea     rcx, stru_180070A58; lpCriticalSection
0x18000456b  call    cs:__imp_DeleteCriticalSection
0x180004571  mov     rcx, cs:hHandle; hObject
0x180004578  test    rcx, rcx
0x18000457b  jz      short loc_180004583
0x18000457d  call    cs:__imp_CloseHandle
0x180004583  add     rsp, 28h
0x180004587  retn
```
