# __scrt_uninitialize_thread_safe_statics

- ea: `0x180001cf0`
- end: `0x180001d18`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001cfb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001cfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d0d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800465A8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180001cf0  sub     rsp, 28h
0x180001cf4  lea     rcx, stru_1800465A8; lpCriticalSection
0x180001cfb  call    cs:__imp_DeleteCriticalSection
0x180001d01  mov     rcx, cs:hHandle; hObject
0x180001d08  test    rcx, rcx
0x180001d0b  jz      short loc_180001D13
0x180001d0d  call    cs:__imp_CloseHandle
0x180001d13  add     rsp, 28h
0x180001d17  retn
```
