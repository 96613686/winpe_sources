# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002800`
- end: `0x180002828`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000280b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000280b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000281d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000281d`

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
0x180002800  sub     rsp, 28h
0x180002804  lea     rcx, CriticalSection; lpCriticalSection
0x18000280b  call    cs:__imp_DeleteCriticalSection
0x180002811  mov     rcx, cs:hHandle; hObject
0x180002818  test    rcx, rcx
0x18000281b  jz      short loc_180002823
0x18000281d  call    cs:__imp_CloseHandle
0x180002823  add     rsp, 28h
0x180002827  retn
```
