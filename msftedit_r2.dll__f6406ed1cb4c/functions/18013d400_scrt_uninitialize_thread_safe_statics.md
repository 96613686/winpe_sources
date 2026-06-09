# __scrt_uninitialize_thread_safe_statics

- ea: `0x18013d400`
- end: `0x18013d428`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18013d400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18013d40b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18013d40b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013d41d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013d41d`

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
0x18013d400  sub     rsp, 28h
0x18013d404  lea     rcx, CriticalSection; lpCriticalSection
0x18013d40b  call    cs:__imp_DeleteCriticalSection
0x18013d411  mov     rcx, cs:hHandle; hObject
0x18013d418  test    rcx, rcx
0x18013d41b  jz      short loc_18013D423
0x18013d41d  call    cs:__imp_CloseHandle
0x18013d423  add     rsp, 28h
0x18013d427  retn
```
