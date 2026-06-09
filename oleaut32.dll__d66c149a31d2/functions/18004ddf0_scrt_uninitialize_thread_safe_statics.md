# __scrt_uninitialize_thread_safe_statics

- ea: `0x18004ddf0`
- end: `0x18004de18`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18004ddf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ddfb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ddfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004de0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004de0d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800C2C08);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x18004ddf0  sub     rsp, 28h
0x18004ddf4  lea     rcx, stru_1800C2C08; lpCriticalSection
0x18004ddfb  call    cs:__imp_DeleteCriticalSection
0x18004de01  mov     rcx, cs:hHandle; hObject
0x18004de08  test    rcx, rcx
0x18004de0b  jz      short loc_18004DE13
0x18004de0d  call    cs:__imp_CloseHandle
0x18004de13  add     rsp, 28h
0x18004de17  retn
```
