# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001a7c`
- end: `0x180001b13`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001098`
- `0x180001174`
- `0x180001220`
- `0x1800012cc`
- `0x180001394`
- `0x180001648`
- `0x180001b1c`
- `0x18000425c`
- `0x18000e168`
- `0x18001cd88`
- `0x18001d7a0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001b08`
- `ADVAPI32!EventWriteTransfer` at `0x180001b08`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v6;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180001a7c  sub     rsp, 48h
0x180001a80  movzx   eax, byte ptr [rdx]
0x180001a83  mov     r11, rcx
0x180001a86  shl     eax, 18h
0x180001a89  mov     r10, r8
0x180001a8c  mov     r8, [rsp+48h+arg_28]
0x180001a91  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001a95  movzx   eax, word ptr [rdx+1]
0x180001a99  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001a9d  mov     rax, [rdx+3]
0x180001aa1  add     rdx, 0Bh
0x180001aa5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001aaa  mov     rax, [rcx+8]
0x180001aae  mov     [r8], rax
0x180001ab1  mov     rax, [rcx+8]
0x180001ab5  mov     [rsp+48h+UserData], r8; UserData
0x180001aba  movzx   ecx, word ptr [rax]
0x180001abd  mov     [r8+8], ecx
0x180001ac1  lea     rcx, _TraceLoggingMetadata
0x180001ac8  mov     [r8+10h], rdx
0x180001acc  mov     dword ptr [r8+0Ch], 2
0x180001ad4  movzx   eax, word ptr [rdx]
0x180001ad7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001adc  mov     [r8+18h], eax
0x180001ae0  lea     rax, _TraceLoggingMetadataEnd
0x180001ae7  sub     eax, ecx
0x180001ae9  mov     dword ptr [r8+1Ch], 1
0x180001af1  mov     dword ptr [rsp+48h+arg_28], eax
0x180001af5  mov     r8, r10; ActivityId
0x180001af8  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001afc  mov     eax, [rsp+48h+arg_20]
0x180001b00  mov     rcx, [r11+20h]; RegHandle
0x180001b04  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001b08  call    cs:__imp_EventWriteTransfer
0x180001b0e  add     rsp, 48h
0x180001b12  retn
```
