# _dynamic_atexit_destructor_for__s_csMapName2Handle__

- ea: `0x180030b60`
- end: `0x180030b77`
- name: `_dynamic_atexit_destructor_for__s_csMapName2Handle__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030b6b`
- `KERNEL32!DeleteCriticalSection` at `0x180030b6b`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_csMapName2Handle__()
{
  DeleteCriticalSection(&stru_180042568);
}

```

## disassembly

```asm
0x180030b60  sub     rsp, 28h
0x180030b64  lea     rcx, stru_180042568; lpCriticalSection
0x180030b6b  call    cs:__imp_DeleteCriticalSection
0x180030b71  nop
0x180030b72  add     rsp, 28h
0x180030b76  retn
```
