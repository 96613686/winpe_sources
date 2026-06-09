# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800020e0`
- end: `0x180002108`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800020e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800020eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800020eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020fd`

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
0x1800020e0  sub     rsp, 28h
0x1800020e4  lea     rcx, CriticalSection; lpCriticalSection
0x1800020eb  call    cs:__imp_DeleteCriticalSection
0x1800020f1  mov     rcx, cs:hHandle; hObject
0x1800020f8  test    rcx, rcx
0x1800020fb  jz      short loc_180002103
0x1800020fd  call    cs:__imp_CloseHandle
0x180002103  add     rsp, 28h
0x180002107  retn
```
