# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800014b0`
- end: `0x180001547`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001068`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000153c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000153c`

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
0x1800014b0  sub     rsp, 48h
0x1800014b4  movzx   eax, byte ptr [rdx]
0x1800014b7  mov     r11, rcx
0x1800014ba  shl     eax, 18h
0x1800014bd  mov     r10, r8
0x1800014c0  mov     r8, [rsp+48h+arg_28]
0x1800014c5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800014c9  movzx   eax, word ptr [rdx+1]
0x1800014cd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800014d1  mov     rax, [rdx+3]
0x1800014d5  add     rdx, 0Bh
0x1800014d9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800014de  mov     rax, [rcx+8]
0x1800014e2  mov     [r8], rax
0x1800014e5  mov     rax, [rcx+8]
0x1800014e9  mov     [rsp+48h+UserData], r8; UserData
0x1800014ee  movzx   ecx, word ptr [rax]
0x1800014f1  mov     [r8+8], ecx
0x1800014f5  lea     rcx, _TraceLoggingMetadata
0x1800014fc  mov     [r8+10h], rdx
0x180001500  mov     dword ptr [r8+0Ch], 2
0x180001508  movzx   eax, word ptr [rdx]
0x18000150b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001510  mov     [r8+18h], eax
0x180001514  lea     rax, _TraceLoggingMetadataEnd
0x18000151b  sub     eax, ecx
0x18000151d  mov     dword ptr [r8+1Ch], 1
0x180001525  mov     dword ptr [rsp+48h+arg_28], eax
0x180001529  mov     r8, r10; ActivityId
0x18000152c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001530  mov     eax, [rsp+48h+arg_20]
0x180001534  mov     rcx, [r11+20h]; RegHandle
0x180001538  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000153c  call    cs:__imp_EventWriteTransfer
0x180001542  add     rsp, 48h
0x180001546  retn
```
