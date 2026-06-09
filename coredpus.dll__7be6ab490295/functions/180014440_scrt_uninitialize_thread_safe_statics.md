# __scrt_uninitialize_thread_safe_statics

- ea: `0x180014440`
- end: `0x180014468`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014440`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001445d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001445d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001444b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001444b`

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
0x180014440  sub     rsp, 28h
0x180014444  lea     rcx, CriticalSection; lpCriticalSection
0x18001444b  call    cs:__imp_DeleteCriticalSection
0x180014451  mov     rcx, cs:hHandle; hObject
0x180014458  test    rcx, rcx
0x18001445b  jz      short loc_180014463
0x18001445d  call    cs:__imp_CloseHandle
0x180014463  add     rsp, 28h
0x180014467  retn
```
