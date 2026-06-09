# __scrt_uninitialize_thread_safe_statics

- ea: `0x140001c70`
- end: `0x140001c98`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001c70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001c8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001c7b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001c7b`

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
0x140001c70  sub     rsp, 28h
0x140001c74  lea     rcx, CriticalSection; lpCriticalSection
0x140001c7b  call    cs:__imp_DeleteCriticalSection
0x140001c81  mov     rcx, cs:hHandle; hObject
0x140001c88  test    rcx, rcx
0x140001c8b  jz      short loc_140001C93
0x140001c8d  call    cs:__imp_CloseHandle
0x140001c93  add     rsp, 28h
0x140001c97  retn
```
