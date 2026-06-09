# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001068`
- end: `0x1800010ff`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180003ad0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010f4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010f4`

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
0x180001068  sub     rsp, 48h
0x18000106c  movzx   eax, byte ptr [rdx]
0x18000106f  mov     r11, rcx
0x180001072  shl     eax, 18h
0x180001075  mov     r10, r8
0x180001078  mov     r8, [rsp+48h+arg_28]
0x18000107d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001081  movzx   eax, word ptr [rdx+1]
0x180001085  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001089  mov     rax, [rdx+3]
0x18000108d  add     rdx, 0Bh
0x180001091  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001096  mov     rax, [rcx+8]
0x18000109a  mov     [r8], rax
0x18000109d  mov     rax, [rcx+8]
0x1800010a1  mov     [rsp+48h+UserData], r8; UserData
0x1800010a6  movzx   ecx, word ptr [rax]
0x1800010a9  mov     [r8+8], ecx
0x1800010ad  lea     rcx, _TraceLoggingMetadata
0x1800010b4  mov     [r8+10h], rdx
0x1800010b8  mov     dword ptr [r8+0Ch], 2
0x1800010c0  movzx   eax, word ptr [rdx]
0x1800010c3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800010c8  mov     [r8+18h], eax
0x1800010cc  lea     rax, _TraceLoggingMetadataEnd
0x1800010d3  sub     eax, ecx
0x1800010d5  mov     dword ptr [r8+1Ch], 1
0x1800010dd  mov     dword ptr [rsp+48h+arg_28], eax
0x1800010e1  mov     r8, r10; ActivityId
0x1800010e4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800010e8  mov     eax, [rsp+48h+arg_20]
0x1800010ec  mov     rcx, [r11+20h]; RegHandle
0x1800010f0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800010f4  call    cs:__imp_EventWriteTransfer
0x1800010fa  add     rsp, 48h
0x1800010fe  retn
```
