# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000fe70`
- end: `0x18000fe98`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000fe70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000fe7b`
- `KERNEL32!DeleteCriticalSection` at `0x18000fe7b`
- `KERNEL32!CloseHandle` at `0x18000fe8d`
- `KERNEL32!CloseHandle` at `0x18000fe8d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x18000fe70  sub     rsp, 28h
0x18000fe74  lea     rcx, CriticalSection; lpCriticalSection
0x18000fe7b  call    cs:__imp_DeleteCriticalSection
0x18000fe81  mov     rcx, cs:hObject; hObject
0x18000fe88  test    rcx, rcx
0x18000fe8b  jz      short loc_18000FE93
0x18000fe8d  call    cs:__imp_CloseHandle
0x18000fe93  add     rsp, 28h
0x18000fe97  retn
```
