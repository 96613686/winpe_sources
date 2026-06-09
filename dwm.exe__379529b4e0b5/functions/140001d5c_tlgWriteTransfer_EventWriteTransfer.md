# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001d5c`
- end: `0x140001df3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001c28`
- `0x14000e1f4`
- `0x14000ed0c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001de8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001de8`

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
0x140001d5c  sub     rsp, 48h
0x140001d60  movzx   eax, byte ptr [rdx]
0x140001d63  mov     r11, rcx
0x140001d66  shl     eax, 18h
0x140001d69  mov     r10, r8
0x140001d6c  mov     r8, [rsp+48h+arg_28]
0x140001d71  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001d75  movzx   eax, word ptr [rdx+1]
0x140001d79  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001d7d  mov     rax, [rdx+3]
0x140001d81  add     rdx, 0Bh
0x140001d85  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001d8a  mov     rax, [rcx+8]
0x140001d8e  mov     [r8], rax
0x140001d91  mov     rax, [rcx+8]
0x140001d95  mov     [rsp+48h+UserData], r8; UserData
0x140001d9a  movzx   ecx, word ptr [rax]
0x140001d9d  mov     [r8+8], ecx
0x140001da1  lea     rcx, _TraceLoggingMetadata
0x140001da8  mov     [r8+10h], rdx
0x140001dac  mov     dword ptr [r8+0Ch], 2
0x140001db4  movzx   eax, word ptr [rdx]
0x140001db7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001dbc  mov     [r8+18h], eax
0x140001dc0  lea     rax, _TraceLoggingMetadataEnd
0x140001dc7  sub     eax, ecx
0x140001dc9  mov     dword ptr [r8+1Ch], 1
0x140001dd1  mov     dword ptr [rsp+48h+arg_28], eax
0x140001dd5  mov     r8, r10; ActivityId
0x140001dd8  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001ddc  mov     eax, [rsp+48h+arg_20]
0x140001de0  mov     rcx, [r11+20h]; RegHandle
0x140001de4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001de8  call    cs:__imp_EventWriteTransfer
0x140001dee  add     rsp, 48h
0x140001df2  retn
```
