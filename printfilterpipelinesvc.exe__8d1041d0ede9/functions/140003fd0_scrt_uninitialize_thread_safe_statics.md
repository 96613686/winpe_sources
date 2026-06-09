# __scrt_uninitialize_thread_safe_statics

- ea: `0x140003fd0`
- end: `0x140003ff8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003fd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140003fed`
- `KERNEL32!CloseHandle` at `0x140003fed`
- `KERNEL32!DeleteCriticalSection` at `0x140003fdb`
- `KERNEL32!DeleteCriticalSection` at `0x140003fdb`

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
0x140003fd0  sub     rsp, 28h
0x140003fd4  lea     rcx, CriticalSection; lpCriticalSection
0x140003fdb  call    cs:__imp_DeleteCriticalSection
0x140003fe1  mov     rcx, cs:hHandle; hObject
0x140003fe8  test    rcx, rcx
0x140003feb  jz      short loc_140003FF3
0x140003fed  call    cs:__imp_CloseHandle
0x140003ff3  add     rsp, 28h
0x140003ff7  retn
```
