# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001a88`
- end: `0x180001b1f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800012cc`
- `0x18000135c`
- `0x180001600`
- `0x180007a90`
- `0x180011acc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001b14`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001b14`

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
0x180001a88  sub     rsp, 48h
0x180001a8c  movzx   eax, byte ptr [rdx]
0x180001a8f  mov     r11, rcx
0x180001a92  shl     eax, 18h
0x180001a95  mov     r10, r8
0x180001a98  mov     r8, [rsp+48h+arg_28]
0x180001a9d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001aa1  movzx   eax, word ptr [rdx+1]
0x180001aa5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001aa9  mov     rax, [rdx+3]
0x180001aad  add     rdx, 0Bh
0x180001ab1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001ab6  mov     rax, [rcx+8]
0x180001aba  mov     [r8], rax
0x180001abd  mov     rax, [rcx+8]
0x180001ac1  mov     [rsp+48h+UserData], r8; UserData
0x180001ac6  movzx   ecx, word ptr [rax]
0x180001ac9  mov     [r8+8], ecx
0x180001acd  lea     rcx, _TraceLoggingMetadata
0x180001ad4  mov     [r8+10h], rdx
0x180001ad8  mov     dword ptr [r8+0Ch], 2
0x180001ae0  movzx   eax, word ptr [rdx]
0x180001ae3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001ae8  mov     [r8+18h], eax
0x180001aec  lea     rax, _TraceLoggingMetadataEnd
0x180001af3  sub     eax, ecx
0x180001af5  mov     dword ptr [r8+1Ch], 1
0x180001afd  mov     dword ptr [rsp+48h+arg_28], eax
0x180001b01  mov     r8, r10; ActivityId
0x180001b04  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001b08  mov     eax, [rsp+48h+arg_20]
0x180001b0c  mov     rcx, [r11+20h]; RegHandle
0x180001b10  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001b14  call    cs:__imp_EventWriteTransfer
0x180001b1a  add     rsp, 48h
0x180001b1e  retn
```
