# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800013c8`
- end: `0x18000145f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x18000113c`
- `0x18000125c`
- `0x180001468`
- `0x180001514`
- `0x180001628`
- `0x18000174c`
- `0x180001824`
- `0x1800018cc`
- `0x1800019e4`
- `0x180001b0c`
- `0x180001bd0`
- `0x18000a2a4`
- `0x18000da88`
- `0x18001e264`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001454`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001454`

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
0x1800013c8  sub     rsp, 48h
0x1800013cc  movzx   eax, byte ptr [rdx]
0x1800013cf  mov     r11, rcx
0x1800013d2  shl     eax, 18h
0x1800013d5  mov     r10, r8
0x1800013d8  mov     r8, [rsp+48h+arg_28]
0x1800013dd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800013e1  movzx   eax, word ptr [rdx+1]
0x1800013e5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800013e9  mov     rax, [rdx+3]
0x1800013ed  add     rdx, 0Bh
0x1800013f1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800013f6  mov     rax, [rcx+8]
0x1800013fa  mov     [r8], rax
0x1800013fd  mov     rax, [rcx+8]
0x180001401  mov     [rsp+48h+UserData], r8; UserData
0x180001406  movzx   ecx, word ptr [rax]
0x180001409  mov     [r8+8], ecx
0x18000140d  lea     rcx, _TraceLoggingMetadata
0x180001414  mov     [r8+10h], rdx
0x180001418  mov     dword ptr [r8+0Ch], 2
0x180001420  movzx   eax, word ptr [rdx]
0x180001423  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001428  mov     [r8+18h], eax
0x18000142c  lea     rax, _TraceLoggingMetadataEnd
0x180001433  sub     eax, ecx
0x180001435  mov     dword ptr [r8+1Ch], 1
0x18000143d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001441  mov     r8, r10; ActivityId
0x180001444  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001448  mov     eax, [rsp+48h+arg_20]
0x18000144c  mov     rcx, [r11+20h]; RegHandle
0x180001450  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001454  call    cs:__imp_EventWriteTransfer
0x18000145a  add     rsp, 48h
0x18000145e  retn
```
