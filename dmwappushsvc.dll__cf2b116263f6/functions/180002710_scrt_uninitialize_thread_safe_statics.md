# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002710`
- end: `0x180002738`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002710`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000272d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000272d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000271b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000271b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180002710  sub     rsp, 28h
0x180002714  lea     rcx, CriticalSection; lpCriticalSection
0x18000271b  call    cs:__imp_DeleteCriticalSection
0x180002721  mov     rcx, cs:hObject; hObject
0x180002728  test    rcx, rcx
0x18000272b  jz      short loc_180002733
0x18000272d  call    cs:__imp_CloseHandle
0x180002733  add     rsp, 28h
0x180002737  retn
```
