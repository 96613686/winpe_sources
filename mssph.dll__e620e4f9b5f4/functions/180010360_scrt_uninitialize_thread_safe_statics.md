# __scrt_uninitialize_thread_safe_statics

- ea: `0x180010360`
- end: `0x180010388`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001036b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001036b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001037d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001037d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180035EA8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180010360  sub     rsp, 28h
0x180010364  lea     rcx, stru_180035EA8; lpCriticalSection
0x18001036b  call    cs:__imp_DeleteCriticalSection
0x180010371  mov     rcx, cs:hHandle; hObject
0x180010378  test    rcx, rcx
0x18001037b  jz      short loc_180010383
0x18001037d  call    cs:__imp_CloseHandle
0x180010383  add     rsp, 28h
0x180010387  retn
```
