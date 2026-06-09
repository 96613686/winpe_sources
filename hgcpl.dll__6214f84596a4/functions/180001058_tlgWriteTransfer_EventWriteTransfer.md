# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001058`
- end: `0x1800010ef`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010f8`
- `0x1800013ac`
- `0x18000141c`
- `0x1800014ac`
- `0x180001750`
- `0x180001bd8`
- `0x180001eb0`
- `0x180001f84`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010e4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010e4`

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
0x180001058  sub     rsp, 48h
0x18000105c  movzx   eax, byte ptr [rdx]
0x18000105f  mov     r11, rcx
0x180001062  shl     eax, 18h
0x180001065  mov     r10, r8
0x180001068  mov     r8, [rsp+48h+arg_28]
0x18000106d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001071  movzx   eax, word ptr [rdx+1]
0x180001075  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001079  mov     rax, [rdx+3]
0x18000107d  add     rdx, 0Bh
0x180001081  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001086  mov     rax, [rcx+8]
0x18000108a  mov     [r8], rax
0x18000108d  mov     rax, [rcx+8]
0x180001091  mov     [rsp+48h+UserData], r8; UserData
0x180001096  movzx   ecx, word ptr [rax]
0x180001099  mov     [r8+8], ecx
0x18000109d  lea     rcx, _TraceLoggingMetadata
0x1800010a4  mov     [r8+10h], rdx
0x1800010a8  mov     dword ptr [r8+0Ch], 2
0x1800010b0  movzx   eax, word ptr [rdx]
0x1800010b3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800010b8  mov     [r8+18h], eax
0x1800010bc  lea     rax, _TraceLoggingMetadataEnd
0x1800010c3  sub     eax, ecx
0x1800010c5  mov     dword ptr [r8+1Ch], 1
0x1800010cd  mov     dword ptr [rsp+48h+arg_28], eax
0x1800010d1  mov     r8, r10; ActivityId
0x1800010d4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800010d8  mov     eax, [rsp+48h+arg_20]
0x1800010dc  mov     rcx, [r11+20h]; RegHandle
0x1800010e0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800010e4  call    cs:__imp_EventWriteTransfer
0x1800010ea  add     rsp, 48h
0x1800010ee  retn
```
