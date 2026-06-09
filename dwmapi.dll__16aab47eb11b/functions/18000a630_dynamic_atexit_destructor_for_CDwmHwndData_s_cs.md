# _dynamic_atexit_destructor_for__CDwmHwndData::s_cs__

- ea: `0x18000a630`
- end: `0x18000a63e`
- name: `_dynamic_atexit_destructor_for__CDwmHwndData::s_cs__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a637`

## pseudocode

```c
void dynamic_atexit_destructor_for__CDwmHwndData::s_cs__()
{
  DeleteCriticalSection(&CDwmHwndData::s_cs);
}

```

## disassembly

```asm
0x18000a630  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; CDwmCS CDwmHwndData::s_cs
0x18000a637  jmp     cs:__imp_DeleteCriticalSection
```
