# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000108c`
- end: `0x180001123`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180010cb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001118`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001118`

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
0x18000108c  sub     rsp, 48h
0x180001090  movzx   eax, byte ptr [rdx]
0x180001093  mov     r11, rcx
0x180001096  shl     eax, 18h
0x180001099  mov     r10, r8
0x18000109c  mov     r8, [rsp+48h+arg_28]
0x1800010a1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800010a5  movzx   eax, word ptr [rdx+1]
0x1800010a9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800010ad  mov     rax, [rdx+3]
0x1800010b1  add     rdx, 0Bh
0x1800010b5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800010ba  mov     rax, [rcx+8]
0x1800010be  mov     [r8], rax
0x1800010c1  mov     rax, [rcx+8]
0x1800010c5  mov     [rsp+48h+UserData], r8; UserData
0x1800010ca  movzx   ecx, word ptr [rax]
0x1800010cd  mov     [r8+8], ecx
0x1800010d1  lea     rcx, _TraceLoggingMetadata
0x1800010d8  mov     [r8+10h], rdx
0x1800010dc  mov     dword ptr [r8+0Ch], 2
0x1800010e4  movzx   eax, word ptr [rdx]
0x1800010e7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800010ec  mov     [r8+18h], eax
0x1800010f0  lea     rax, _TraceLoggingMetadataEnd
0x1800010f7  sub     eax, ecx
0x1800010f9  mov     dword ptr [r8+1Ch], 1
0x180001101  mov     dword ptr [rsp+48h+arg_28], eax
0x180001105  mov     r8, r10; ActivityId
0x180001108  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000110c  mov     eax, [rsp+48h+arg_20]
0x180001110  mov     rcx, [r11+20h]; RegHandle
0x180001114  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001118  call    cs:__imp_EventWriteTransfer
0x18000111e  add     rsp, 48h
0x180001122  retn
```
