# __scrt_uninitialize_thread_safe_statics

- ea: `0x180007290`
- end: `0x1800072b8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000729b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000729b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072ad`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180054188);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180007290  sub     rsp, 28h
0x180007294  lea     rcx, stru_180054188; lpCriticalSection
0x18000729b  call    cs:__imp_DeleteCriticalSection
0x1800072a1  mov     rcx, cs:hObject; hObject
0x1800072a8  test    rcx, rcx
0x1800072ab  jz      short loc_1800072B3
0x1800072ad  call    cs:__imp_CloseHandle
0x1800072b3  add     rsp, 28h
0x1800072b7  retn
```
