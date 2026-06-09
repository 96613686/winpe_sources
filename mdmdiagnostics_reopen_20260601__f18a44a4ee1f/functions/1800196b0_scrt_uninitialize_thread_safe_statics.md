# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800196b0`
- end: `0x1800196d8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800196b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800196bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800196bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196cd`

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
0x1800196b0  sub     rsp, 28h
0x1800196b4  lea     rcx, CriticalSection; lpCriticalSection
0x1800196bb  call    cs:__imp_DeleteCriticalSection
0x1800196c1  mov     rcx, cs:hHandle; hObject
0x1800196c8  test    rcx, rcx
0x1800196cb  jz      short loc_1800196D3
0x1800196cd  call    cs:__imp_CloseHandle
0x1800196d3  add     rsp, 28h
0x1800196d7  retn
```
