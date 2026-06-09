# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001078`
- end: `0x180001116`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180001144`
- `0x180003d50`
- `0x1800082b0`
- `0x180012630`
- `0x180012c28`
- `0x180018564`
- `0x1800192a4`
- `0x180019520`
- `0x180019880`
- `0x180019ed8`
- `0x18001a694`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001104`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001104`

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
0x180001078  sub     rsp, 48h
0x18000107c  movzx   eax, byte ptr [rdx]
0x18000107f  mov     r11, rcx
0x180001082  shl     eax, 18h
0x180001085  mov     r10, r8
0x180001088  mov     r8, [rsp+48h+arg_28]
0x18000108d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001091  movzx   eax, word ptr [rdx+1]
0x180001095  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001099  mov     rax, [rdx+3]
0x18000109d  add     rdx, 0Bh
0x1800010a1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800010a6  mov     rax, [rcx+8]
0x1800010aa  mov     [r8], rax
0x1800010ad  mov     rax, [rcx+8]
0x1800010b1  mov     [rsp+48h+UserData], r8; UserData
0x1800010b6  movzx   ecx, word ptr [rax]
0x1800010b9  mov     [r8+8], ecx
0x1800010bd  lea     rcx, _TraceLoggingMetadata
0x1800010c4  mov     [r8+10h], rdx
0x1800010c8  mov     dword ptr [r8+0Ch], 2
0x1800010d0  movzx   eax, word ptr [rdx]
0x1800010d3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800010d8  mov     [r8+18h], eax
0x1800010dc  lea     rax, _TraceLoggingMetadataEnd
0x1800010e3  sub     eax, ecx
0x1800010e5  mov     dword ptr [r8+1Ch], 1
0x1800010ed  mov     dword ptr [rsp+48h+arg_28], eax
0x1800010f1  mov     r8, r10; ActivityId
0x1800010f4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800010f8  mov     eax, [rsp+48h+arg_20]
0x1800010fc  mov     rcx, [r11+20h]; RegHandle
0x180001100  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001104  call    cs:__imp_EventWriteTransfer
0x18000110b  nop     dword ptr [rax+rax+00h]
0x180001110  add     rsp, 48h
0x180001114  retn
```
