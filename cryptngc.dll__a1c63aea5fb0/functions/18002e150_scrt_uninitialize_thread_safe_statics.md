# __scrt_uninitialize_thread_safe_statics

- ea: `0x18002e150`
- end: `0x18002e178`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002e150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e15b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e15b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e16d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e16d`

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
0x18002e150  sub     rsp, 28h
0x18002e154  lea     rcx, CriticalSection; lpCriticalSection
0x18002e15b  call    cs:__imp_DeleteCriticalSection
0x18002e161  mov     rcx, cs:hObject; hObject
0x18002e168  test    rcx, rcx
0x18002e16b  jz      short loc_18002E173
0x18002e16d  call    cs:__imp_CloseHandle
0x18002e173  add     rsp, 28h
0x18002e177  retn
```
