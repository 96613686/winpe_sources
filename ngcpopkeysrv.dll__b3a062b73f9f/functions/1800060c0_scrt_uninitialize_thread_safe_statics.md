# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800060c0`
- end: `0x1800060e8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800060c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800060cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800060cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060dd`

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
0x1800060c0  sub     rsp, 28h
0x1800060c4  lea     rcx, CriticalSection; lpCriticalSection
0x1800060cb  call    cs:__imp_DeleteCriticalSection
0x1800060d1  mov     rcx, cs:hHandle; hObject
0x1800060d8  test    rcx, rcx
0x1800060db  jz      short loc_1800060E3
0x1800060dd  call    cs:__imp_CloseHandle
0x1800060e3  add     rsp, 28h
0x1800060e7  retn
```
