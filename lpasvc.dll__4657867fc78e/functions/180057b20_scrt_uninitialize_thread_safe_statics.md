# __scrt_uninitialize_thread_safe_statics

- ea: `0x180057b20`
- end: `0x180057b48`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180057b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057b2b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057b2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057b3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057b3d`

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
0x180057b20  sub     rsp, 28h
0x180057b24  lea     rcx, CriticalSection; lpCriticalSection
0x180057b2b  call    cs:__imp_DeleteCriticalSection
0x180057b31  mov     rcx, cs:hHandle; hObject
0x180057b38  test    rcx, rcx
0x180057b3b  jz      short loc_180057B43
0x180057b3d  call    cs:__imp_CloseHandle
0x180057b43  add     rsp, 28h
0x180057b47  retn
```
