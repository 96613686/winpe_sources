# FltpCommonOplockCheckBreak

- ea: `0x18001df10`
- end: `0x18001e145`
- name: `FltpCommonOplockCheckBreak`
- size: `565`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64 (__fastcall *)(__int64, __int64, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)()), __int64 (__fastcall *)(__int64, __int64, _QWORD, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)()), __int64 (__fastcall *)(__int64, __int64, _QWORD, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64, __int64), __int64 (__fastcall *)(__int64, __int64, __int64, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)()), unsigned int, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001e80`
- `0x180002000`
- `0x180002060`
- `0x18001deb0`
- `0x180021cc0`
- `0x180051d10`

## callees

- `0x180007230`
- `0x180009f20`
- `0x18001df10`
- `0x180024880`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18001e0f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001e0f7`
- `ntoskrnl!ExAllocatePool2` at `0x18001df6d`
- `ntoskrnl!ExAllocatePool2` at `0x18001df6d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001dfa5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001dfa5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001e0cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001e0cf`

## pseudocode

```c

```
