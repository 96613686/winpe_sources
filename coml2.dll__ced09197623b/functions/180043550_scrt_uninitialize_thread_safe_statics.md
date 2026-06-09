# __scrt_uninitialize_thread_safe_statics

- ea: `0x180043550`
- end: `0x180043578`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180043550`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004356d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004356d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004355b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004355b`

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
0x180043550  sub     rsp, 28h
0x180043554  lea     rcx, CriticalSection; lpCriticalSection
0x18004355b  call    cs:__imp_DeleteCriticalSection
0x180043561  mov     rcx, cs:hHandle; hObject
0x180043568  test    rcx, rcx
0x18004356b  jz      short loc_180043573
0x18004356d  call    cs:__imp_CloseHandle
0x180043573  add     rsp, 28h
0x180043577  retn
```
