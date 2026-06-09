# __scrt_uninitialize_thread_safe_statics

- ea: `0x180003860`
- end: `0x180003888`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000386b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000386b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000387d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000387d`

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
0x180003860  sub     rsp, 28h
0x180003864  lea     rcx, CriticalSection; lpCriticalSection
0x18000386b  call    cs:__imp_DeleteCriticalSection
0x180003871  mov     rcx, cs:hHandle; hObject
0x180003878  test    rcx, rcx
0x18000387b  jz      short loc_180003883
0x18000387d  call    cs:__imp_CloseHandle
0x180003883  add     rsp, 28h
0x180003887  retn
```
