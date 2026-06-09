# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400019e8`
- end: `0x140001a7f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`
- `0x1400012b8`
- `0x14000156c`
- `0x140001a88`
- `0x140001ad0`
- `0x140001b94`
- `0x140001cb8`
- `0x140001fb4`
- `0x1400020ec`
- `0x1400022a0`
- `0x140002330`
- `0x14000bae4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001a74`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001a74`

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
0x1400019e8  sub     rsp, 48h
0x1400019ec  movzx   eax, byte ptr [rdx]
0x1400019ef  mov     r11, rcx
0x1400019f2  shl     eax, 18h
0x1400019f5  mov     r10, r8
0x1400019f8  mov     r8, [rsp+48h+arg_28]
0x1400019fd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001a01  movzx   eax, word ptr [rdx+1]
0x140001a05  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001a09  mov     rax, [rdx+3]
0x140001a0d  add     rdx, 0Bh
0x140001a11  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001a16  mov     rax, [rcx+8]
0x140001a1a  mov     [r8], rax
0x140001a1d  mov     rax, [rcx+8]
0x140001a21  mov     [rsp+48h+UserData], r8; UserData
0x140001a26  movzx   ecx, word ptr [rax]
0x140001a29  mov     [r8+8], ecx
0x140001a2d  lea     rcx, _TraceLoggingMetadata
0x140001a34  mov     [r8+10h], rdx
0x140001a38  mov     dword ptr [r8+0Ch], 2
0x140001a40  movzx   eax, word ptr [rdx]
0x140001a43  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001a48  mov     [r8+18h], eax
0x140001a4c  lea     rax, _TraceLoggingMetadataEnd
0x140001a53  sub     eax, ecx
0x140001a55  mov     dword ptr [r8+1Ch], 1
0x140001a5d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001a61  mov     r8, r10; ActivityId
0x140001a64  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001a68  mov     eax, [rsp+48h+arg_20]
0x140001a6c  mov     rcx, [r11+20h]; RegHandle
0x140001a70  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001a74  call    cs:__imp_EventWriteTransfer
0x140001a7a  add     rsp, 48h
0x140001a7e  retn
```
