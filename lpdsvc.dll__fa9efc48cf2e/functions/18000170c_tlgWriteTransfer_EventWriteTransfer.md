# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000170c`
- end: `0x1800017a3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800010e0`
- `0x180001394`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001798`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001798`

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
0x18000170c  sub     rsp, 48h
0x180001710  movzx   eax, byte ptr [rdx]
0x180001713  mov     r11, rcx
0x180001716  shl     eax, 18h
0x180001719  mov     r10, r8
0x18000171c  mov     r8, [rsp+48h+arg_28]
0x180001721  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001725  movzx   eax, word ptr [rdx+1]
0x180001729  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000172d  mov     rax, [rdx+3]
0x180001731  add     rdx, 0Bh
0x180001735  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000173a  mov     rax, [rcx+8]
0x18000173e  mov     [r8], rax
0x180001741  mov     rax, [rcx+8]
0x180001745  mov     [rsp+48h+UserData], r8; UserData
0x18000174a  movzx   ecx, word ptr [rax]
0x18000174d  mov     [r8+8], ecx
0x180001751  lea     rcx, _TraceLoggingMetadata
0x180001758  mov     [r8+10h], rdx
0x18000175c  mov     dword ptr [r8+0Ch], 2
0x180001764  movzx   eax, word ptr [rdx]
0x180001767  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000176c  mov     [r8+18h], eax
0x180001770  lea     rax, _TraceLoggingMetadataEnd
0x180001777  sub     eax, ecx
0x180001779  mov     dword ptr [r8+1Ch], 1
0x180001781  mov     dword ptr [rsp+48h+arg_28], eax
0x180001785  mov     r8, r10; ActivityId
0x180001788  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000178c  mov     eax, [rsp+48h+arg_20]
0x180001790  mov     rcx, [r11+20h]; RegHandle
0x180001794  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001798  call    cs:__imp_EventWriteTransfer
0x18000179e  add     rsp, 48h
0x1800017a2  retn
```
