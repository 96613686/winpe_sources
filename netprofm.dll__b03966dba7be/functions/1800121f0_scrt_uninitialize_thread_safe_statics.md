# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800121f0`
- end: `0x180012218`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800121f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800121fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800121fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001220d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001220d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18005FD68);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800121f0  sub     rsp, 28h
0x1800121f4  lea     rcx, stru_18005FD68; lpCriticalSection
0x1800121fb  call    cs:__imp_DeleteCriticalSection
0x180012201  mov     rcx, cs:hHandle; hObject
0x180012208  test    rcx, rcx
0x18001220b  jz      short loc_180012213
0x18001220d  call    cs:__imp_CloseHandle
0x180012213  add     rsp, 28h
0x180012217  retn
```
