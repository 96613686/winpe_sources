# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800021a0`
- end: `0x1800021c8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800021a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800021ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800021ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021bd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180012470);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800021a0  sub     rsp, 28h
0x1800021a4  lea     rcx, stru_180012470; lpCriticalSection
0x1800021ab  call    cs:__imp_DeleteCriticalSection
0x1800021b1  mov     rcx, cs:hHandle; hObject
0x1800021b8  test    rcx, rcx
0x1800021bb  jz      short loc_1800021C3
0x1800021bd  call    cs:__imp_CloseHandle
0x1800021c3  add     rsp, 28h
0x1800021c7  retn
```
