# __scrt_uninitialize_thread_safe_statics

- ea: `0x180054620`
- end: `0x180054648`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180054620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005462b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005462b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005463d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005463d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180152FB8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180054620  sub     rsp, 28h
0x180054624  lea     rcx, stru_180152FB8; lpCriticalSection
0x18005462b  call    cs:__imp_DeleteCriticalSection
0x180054631  mov     rcx, cs:hHandle; hObject
0x180054638  test    rcx, rcx
0x18005463b  jz      short loc_180054643
0x18005463d  call    cs:__imp_CloseHandle
0x180054643  add     rsp, 28h
0x180054647  retn
```
