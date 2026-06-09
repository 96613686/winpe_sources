# __scrt_uninitialize_thread_safe_statics

- ea: `0x180003960`
- end: `0x180003988`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000396b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000396b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000397d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000397d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18005F938);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180003960  sub     rsp, 28h
0x180003964  lea     rcx, stru_18005F938; lpCriticalSection
0x18000396b  call    cs:__imp_DeleteCriticalSection
0x180003971  mov     rcx, cs:hHandle; hObject
0x180003978  test    rcx, rcx
0x18000397b  jz      short loc_180003983
0x18000397d  call    cs:__imp_CloseHandle
0x180003983  add     rsp, 28h
0x180003987  retn
```
