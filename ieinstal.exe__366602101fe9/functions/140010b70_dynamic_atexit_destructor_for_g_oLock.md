# _dynamic_atexit_destructor_for__g_oLock__

- ea: `0x140010b70`
- end: `0x140010b96`
- name: `_dynamic_atexit_destructor_for__g_oLock__`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010b70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140010b84`
- `KERNEL32!DeleteCriticalSection` at `0x140010b84`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_oLock__()
{
  if ( g_oLock )
    DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x140010b70  sub     rsp, 28h
0x140010b74  cmp     cs:?g_oLock@@3VCLock@@A, 0; CLock g_oLock
0x140010b7b  jz      short loc_140010B90
0x140010b7d  lea     rcx, CriticalSection; lpCriticalSection
0x140010b84  call    cs:__imp_DeleteCriticalSection
0x140010b8b  nop     dword ptr [rax+rax+00h]
0x140010b90  add     rsp, 28h
0x140010b94  retn
```
