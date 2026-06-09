# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002aa0`
- end: `0x180002ac8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002aab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002aab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002abd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002abd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180021DA8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180002aa0  sub     rsp, 28h
0x180002aa4  lea     rcx, stru_180021DA8; lpCriticalSection
0x180002aab  call    cs:__imp_DeleteCriticalSection
0x180002ab1  mov     rcx, cs:hHandle; hObject
0x180002ab8  test    rcx, rcx
0x180002abb  jz      short loc_180002AC3
0x180002abd  call    cs:__imp_CloseHandle
0x180002ac3  add     rsp, 28h
0x180002ac7  retn
```
