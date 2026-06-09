# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000b468`
- end: `0x18000b4ff`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001300`
- `0x180001360`
- `0x18000b13c`
- `0x18000b3f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b4f4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b4f4`

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
0x18000b468  sub     rsp, 48h
0x18000b46c  movzx   eax, byte ptr [rdx]
0x18000b46f  mov     r11, rcx
0x18000b472  shl     eax, 18h
0x18000b475  mov     r10, r8
0x18000b478  mov     r8, [rsp+48h+arg_28]
0x18000b47d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000b481  movzx   eax, word ptr [rdx+1]
0x18000b485  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000b489  mov     rax, [rdx+3]
0x18000b48d  add     rdx, 0Bh
0x18000b491  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000b496  mov     rax, [rcx+8]
0x18000b49a  mov     [r8], rax
0x18000b49d  mov     rax, [rcx+8]
0x18000b4a1  mov     [rsp+48h+UserData], r8; UserData
0x18000b4a6  movzx   ecx, word ptr [rax]
0x18000b4a9  mov     [r8+8], ecx
0x18000b4ad  lea     rcx, _TraceLoggingMetadata
0x18000b4b4  mov     [r8+10h], rdx
0x18000b4b8  mov     dword ptr [r8+0Ch], 2
0x18000b4c0  movzx   eax, word ptr [rdx]
0x18000b4c3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000b4c8  mov     [r8+18h], eax
0x18000b4cc  lea     rax, _TraceLoggingMetadataEnd
0x18000b4d3  sub     eax, ecx
0x18000b4d5  mov     dword ptr [r8+1Ch], 1
0x18000b4dd  mov     dword ptr [rsp+48h+arg_28], eax
0x18000b4e1  mov     r8, r10; ActivityId
0x18000b4e4  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000b4e8  mov     eax, [rsp+48h+arg_20]
0x18000b4ec  mov     rcx, [r11+20h]; RegHandle
0x18000b4f0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000b4f4  call    cs:__imp_EventWriteTransfer
0x18000b4fa  add     rsp, 48h
0x18000b4fe  retn
```
