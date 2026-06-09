# _dynamic_atexit_destructor_for__TraceOutputSettings::SettingsLock__

- ea: `0x140007250`
- end: `0x140007275`
- name: `_dynamic_atexit_destructor_for__TraceOutputSettings::SettingsLock__`
- size: `37`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140007269`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140007269`

## pseudocode

```c
void dynamic_atexit_destructor_for__TraceOutputSettings::SettingsLock__()
{
  TraceOutputSettings::SettingsLock = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_140010798);
}

```

## disassembly

```asm
0x140007250  sub     rsp, 28h
0x140007254  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x14000725b  mov     cs:?SettingsLock@TraceOutputSettings@@0VCSemExclusive@@A, rax; CSemExclusive TraceOutputSettings::SettingsLock
0x140007262  lea     rcx, stru_140010798; lpCriticalSection
0x140007269  call    cs:__imp_DeleteCriticalSection
0x14000726f  nop
0x140007270  add     rsp, 28h
0x140007274  retn
```
