# __scrt_uninitialize_thread_safe_statics

- ea: `0x180014830`
- end: `0x180014858`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001483b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001483b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001484d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001484d`

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
0x180014830  sub     rsp, 28h
0x180014834  lea     rcx, CriticalSection; lpCriticalSection
0x18001483b  call    cs:__imp_DeleteCriticalSection
0x180014841  mov     rcx, cs:hHandle; hObject
0x180014848  test    rcx, rcx
0x18001484b  jz      short loc_180014853
0x18001484d  call    cs:__imp_CloseHandle
0x180014853  add     rsp, 28h
0x180014857  retn
```
