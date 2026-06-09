# __scrt_uninitialize_thread_safe_statics

- ea: `0x180001850`
- end: `0x180001878`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001850`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000186d`
- `KERNEL32!CloseHandle` at `0x18000186d`
- `KERNEL32!DeleteCriticalSection` at `0x18000185b`
- `KERNEL32!DeleteCriticalSection` at `0x18000185b`

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
0x180001850  sub     rsp, 28h
0x180001854  lea     rcx, CriticalSection; lpCriticalSection
0x18000185b  call    cs:__imp_DeleteCriticalSection
0x180001861  mov     rcx, cs:hHandle; hObject
0x180001868  test    rcx, rcx
0x18000186b  jz      short loc_180001873
0x18000186d  call    cs:__imp_CloseHandle
0x180001873  add     rsp, 28h
0x180001877  retn
```
