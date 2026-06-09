# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002320`
- end: `0x180002348`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000232b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000232b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000233d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000233d`

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
0x180002320  sub     rsp, 28h
0x180002324  lea     rcx, CriticalSection; lpCriticalSection
0x18000232b  call    cs:__imp_DeleteCriticalSection
0x180002331  mov     rcx, cs:hHandle; hObject
0x180002338  test    rcx, rcx
0x18000233b  jz      short loc_180002343
0x18000233d  call    cs:__imp_CloseHandle
0x180002343  add     rsp, 28h
0x180002347  retn
```
