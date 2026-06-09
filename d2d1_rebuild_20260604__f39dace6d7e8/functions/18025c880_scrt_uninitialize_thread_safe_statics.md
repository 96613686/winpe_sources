# __scrt_uninitialize_thread_safe_statics

- ea: `0x18025c880`
- end: `0x18025c8a8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18025c880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18025c88b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18025c88b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18025c89d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18025c89d`

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
0x18025c880  sub     rsp, 28h
0x18025c884  lea     rcx, CriticalSection; lpCriticalSection
0x18025c88b  call    cs:__imp_DeleteCriticalSection
0x18025c891  mov     rcx, cs:hObject; hObject
0x18025c898  test    rcx, rcx
0x18025c89b  jz      short loc_18025C8A3
0x18025c89d  call    cs:__imp_CloseHandle
0x18025c8a3  add     rsp, 28h
0x18025c8a7  retn
```
