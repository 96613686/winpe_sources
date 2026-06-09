# CNlmTriggerProfileEventSink::NetworkDeleted(_GUID)

- ea: `0x18000c770`
- end: `0x18000c788`
- name: `?NetworkDeleted@CNlmTriggerProfileEventSink@@UEAAJU_GUID@@@Z`
- size: `24`
- prototype: `__int64 __fastcall(CNlmTriggerProfileEventSink *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b340`

## pseudocode

```c
__int64 __fastcall CNlmTriggerProfileEventSink::NetworkDeleted(CNlmTriggerProfileEventSink *this, struct _GUID *a2)
{
  NcaSrcLnkdTriggerSignalTriggersInList(&stru_180028CF0);
  return 0;
}

```

## disassembly

```asm
0x18000c770  sub     rsp, 28h
0x18000c774  lea     rcx, stru_180028CF0
0x18000c77b  call    NcaSrcLnkdTriggerSignalTriggersInList
0x18000c780  xor     eax, eax
0x18000c782  add     rsp, 28h
0x18000c786  retn
```
