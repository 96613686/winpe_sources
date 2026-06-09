# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800300d0`
- end: `0x1800300f8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800300d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800300db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800300db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300ed`

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
0x1800300d0  sub     rsp, 28h
0x1800300d4  lea     rcx, CriticalSection; lpCriticalSection
0x1800300db  call    cs:__imp_DeleteCriticalSection
0x1800300e1  mov     rcx, cs:hObject; hObject
0x1800300e8  test    rcx, rcx
0x1800300eb  jz      short loc_1800300F3
0x1800300ed  call    cs:__imp_CloseHandle
0x1800300f3  add     rsp, 28h
0x1800300f7  retn
```
