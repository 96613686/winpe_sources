# wil_details_RecordFeatureUsageCallback

- ea: `0x14000ab40`
- end: `0x14000ab56`
- name: `wil_details_RecordFeatureUsageCallback`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001990`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000ab44`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000ab44`

## pseudocode

```c
__int64 wil_details_RecordFeatureUsageCallback()
{
  return RtlRecordFeatureUsage();
}

```

## disassembly

```asm
0x14000ab40  sub     rsp, 28h
0x14000ab44  call    cs:__imp_RtlRecordFeatureUsage
0x14000ab4b  nop     dword ptr [rax+rax+00h]
0x14000ab50  add     rsp, 28h
0x14000ab54  retn
```
