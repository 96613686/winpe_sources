# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002870`
- end: `0x180002898`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000287b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000287b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000288d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000288d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18001B688);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180002870  sub     rsp, 28h
0x180002874  lea     rcx, stru_18001B688; lpCriticalSection
0x18000287b  call    cs:__imp_DeleteCriticalSection
0x180002881  mov     rcx, cs:hHandle; hObject
0x180002888  test    rcx, rcx
0x18000288b  jz      short loc_180002893
0x18000288d  call    cs:__imp_CloseHandle
0x180002893  add     rsp, 28h
0x180002897  retn
```
