# __scrt_uninitialize_thread_safe_statics

- ea: `0x140003120`
- end: `0x140003148`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000312b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000312b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000313d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000313d`

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
0x140003120  sub     rsp, 28h
0x140003124  lea     rcx, CriticalSection; lpCriticalSection
0x14000312b  call    cs:__imp_DeleteCriticalSection
0x140003131  mov     rcx, cs:hHandle; hObject
0x140003138  test    rcx, rcx
0x14000313b  jz      short loc_140003143
0x14000313d  call    cs:__imp_CloseHandle
0x140003143  add     rsp, 28h
0x140003147  retn
```
