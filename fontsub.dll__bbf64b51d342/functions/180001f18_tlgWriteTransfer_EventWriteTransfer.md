# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001f18`
- end: `0x180001faf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x18000132c`
- `0x1800015e0`
- `0x180001908`
- `0x180001978`
- `0x180001a08`
- `0x180001a98`
- `0x180003698`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001fa4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001fa4`

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
0x180001f18  sub     rsp, 48h
0x180001f1c  movzx   eax, byte ptr [rdx]
0x180001f1f  mov     r11, rcx
0x180001f22  shl     eax, 18h
0x180001f25  mov     r10, r8
0x180001f28  mov     r8, [rsp+48h+arg_28]
0x180001f2d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001f31  movzx   eax, word ptr [rdx+1]
0x180001f35  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001f39  mov     rax, [rdx+3]
0x180001f3d  add     rdx, 0Bh
0x180001f41  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001f46  mov     rax, [rcx+8]
0x180001f4a  mov     [r8], rax
0x180001f4d  mov     rax, [rcx+8]
0x180001f51  mov     [rsp+48h+UserData], r8; UserData
0x180001f56  movzx   ecx, word ptr [rax]
0x180001f59  mov     [r8+8], ecx
0x180001f5d  lea     rcx, _TraceLoggingMetadata
0x180001f64  mov     [r8+10h], rdx
0x180001f68  mov     dword ptr [r8+0Ch], 2
0x180001f70  movzx   eax, word ptr [rdx]
0x180001f73  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001f78  mov     [r8+18h], eax
0x180001f7c  lea     rax, _TraceLoggingMetadataEnd
0x180001f83  sub     eax, ecx
0x180001f85  mov     dword ptr [r8+1Ch], 1
0x180001f8d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001f91  mov     r8, r10; ActivityId
0x180001f94  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001f98  mov     eax, [rsp+48h+arg_20]
0x180001f9c  mov     rcx, [r11+20h]; RegHandle
0x180001fa0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001fa4  call    cs:__imp_EventWriteTransfer
0x180001faa  add     rsp, 48h
0x180001fae  retn
```
