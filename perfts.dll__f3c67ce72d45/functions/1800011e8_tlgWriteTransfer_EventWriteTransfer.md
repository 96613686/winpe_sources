# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800011e8`
- end: `0x18000127f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001098`
- `0x180001140`
- `0x180005378`
- `0x180006598`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001274`
- `ADVAPI32!EventWriteTransfer` at `0x180001274`

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
0x1800011e8  sub     rsp, 48h
0x1800011ec  movzx   eax, byte ptr [rdx]
0x1800011ef  mov     r11, rcx
0x1800011f2  shl     eax, 18h
0x1800011f5  mov     r10, r8
0x1800011f8  mov     r8, [rsp+48h+arg_28]
0x1800011fd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001201  movzx   eax, word ptr [rdx+1]
0x180001205  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001209  mov     rax, [rdx+3]
0x18000120d  add     rdx, 0Bh
0x180001211  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001216  mov     rax, [rcx+8]
0x18000121a  mov     [r8], rax
0x18000121d  mov     rax, [rcx+8]
0x180001221  mov     [rsp+48h+UserData], r8; UserData
0x180001226  movzx   ecx, word ptr [rax]
0x180001229  mov     [r8+8], ecx
0x18000122d  lea     rcx, _TraceLoggingMetadata
0x180001234  mov     [r8+10h], rdx
0x180001238  mov     dword ptr [r8+0Ch], 2
0x180001240  movzx   eax, word ptr [rdx]
0x180001243  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001248  mov     [r8+18h], eax
0x18000124c  lea     rax, _TraceLoggingMetadataEnd
0x180001253  sub     eax, ecx
0x180001255  mov     dword ptr [r8+1Ch], 1
0x18000125d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001261  mov     r8, r10; ActivityId
0x180001264  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001268  mov     eax, [rsp+48h+arg_20]
0x18000126c  mov     rcx, [r11+20h]; RegHandle
0x180001270  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001274  call    cs:__imp_EventWriteTransfer
0x18000127a  add     rsp, 48h
0x18000127e  retn
```
