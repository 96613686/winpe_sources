# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000fc20`
- end: `0x18000fcb7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x18000102c`
- `0x180001074`
- `0x1800011d0`
- `0x180001318`
- `0x180001384`
- `0x180001424`
- `0x1800014f4`
- `0x180001570`
- `0x18000166c`
- `0x180001818`
- `0x1800018a4`
- `0x180021a80`
- `0x1800384e0`
- `0x180041cf0`
- `0x1800436d8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fcac`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fcac`

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
0x18000fc20  sub     rsp, 48h
0x18000fc24  movzx   eax, byte ptr [rdx]
0x18000fc27  mov     r11, rcx
0x18000fc2a  shl     eax, 18h
0x18000fc2d  mov     r10, r8
0x18000fc30  mov     r8, [rsp+48h+arg_28]
0x18000fc35  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000fc39  movzx   eax, word ptr [rdx+1]
0x18000fc3d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000fc41  mov     rax, [rdx+3]
0x18000fc45  add     rdx, 0Bh
0x18000fc49  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000fc4e  mov     rax, [rcx+8]
0x18000fc52  mov     [r8], rax
0x18000fc55  mov     rax, [rcx+8]
0x18000fc59  mov     [rsp+48h+UserData], r8; UserData
0x18000fc5e  movzx   ecx, word ptr [rax]
0x18000fc61  mov     [r8+8], ecx
0x18000fc65  lea     rcx, _TraceLoggingMetadata
0x18000fc6c  mov     [r8+10h], rdx
0x18000fc70  mov     dword ptr [r8+0Ch], 2
0x18000fc78  movzx   eax, word ptr [rdx]
0x18000fc7b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000fc80  mov     [r8+18h], eax
0x18000fc84  lea     rax, _TraceLoggingMetadataEnd
0x18000fc8b  sub     eax, ecx
0x18000fc8d  mov     dword ptr [r8+1Ch], 1
0x18000fc95  mov     dword ptr [rsp+48h+arg_28], eax
0x18000fc99  mov     r8, r10; ActivityId
0x18000fc9c  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000fca0  mov     eax, [rsp+48h+arg_20]
0x18000fca4  mov     rcx, [r11+20h]; RegHandle
0x18000fca8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000fcac  call    cs:__imp_EventWriteTransfer
0x18000fcb2  add     rsp, 48h
0x18000fcb6  retn
```
