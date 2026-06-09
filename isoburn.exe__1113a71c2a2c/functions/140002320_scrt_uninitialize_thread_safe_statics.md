# __scrt_uninitialize_thread_safe_statics

- ea: `0x140002320`
- end: `0x140002348`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002320`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000233d`
- `KERNEL32!CloseHandle` at `0x14000233d`
- `KERNEL32!DeleteCriticalSection` at `0x14000232b`
- `KERNEL32!DeleteCriticalSection` at `0x14000232b`

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
0x140002320  sub     rsp, 28h
0x140002324  lea     rcx, CriticalSection; lpCriticalSection
0x14000232b  call    cs:__imp_DeleteCriticalSection
0x140002331  mov     rcx, cs:hHandle; hObject
0x140002338  test    rcx, rcx
0x14000233b  jz      short loc_140002343
0x14000233d  call    cs:__imp_CloseHandle
0x140002343  add     rsp, 28h
0x140002347  retn
```
