# __scrt_uninitialize_thread_safe_statics

- ea: `0x14000cfa0`
- end: `0x14000cfc8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000cfa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000cfab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000cfab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cfbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cfbd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1400759B8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x14000cfa0  sub     rsp, 28h
0x14000cfa4  lea     rcx, stru_1400759B8; lpCriticalSection
0x14000cfab  call    cs:__imp_DeleteCriticalSection
0x14000cfb1  mov     rcx, cs:hHandle; hObject
0x14000cfb8  test    rcx, rcx
0x14000cfbb  jz      short loc_14000CFC3
0x14000cfbd  call    cs:__imp_CloseHandle
0x14000cfc3  add     rsp, 28h
0x14000cfc7  retn
```
