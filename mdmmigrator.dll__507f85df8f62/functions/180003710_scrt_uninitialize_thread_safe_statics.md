# __scrt_uninitialize_thread_safe_statics

- ea: `0x180003710`
- end: `0x180003738`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000371b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000371b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000372d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000372d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18002B5C8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180003710  sub     rsp, 28h
0x180003714  lea     rcx, stru_18002B5C8; lpCriticalSection
0x18000371b  call    cs:__imp_DeleteCriticalSection
0x180003721  mov     rcx, cs:hHandle; hObject
0x180003728  test    rcx, rcx
0x18000372b  jz      short loc_180003733
0x18000372d  call    cs:__imp_CloseHandle
0x180003733  add     rsp, 28h
0x180003737  retn
```
