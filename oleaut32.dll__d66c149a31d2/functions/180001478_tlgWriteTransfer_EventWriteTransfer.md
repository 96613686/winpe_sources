# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001478`
- end: `0x18000150f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180067d88`
- `0x180067e54`
- `0x180067f0c`
- `0x180067fcc`
- `0x180068074`
- `0x180068160`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001504`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001504`

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
0x180001478  sub     rsp, 48h
0x18000147c  movzx   eax, byte ptr [rdx]
0x18000147f  mov     r11, rcx
0x180001482  shl     eax, 18h
0x180001485  mov     r10, r8
0x180001488  mov     r8, [rsp+48h+arg_28]
0x18000148d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001491  movzx   eax, word ptr [rdx+1]
0x180001495  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001499  mov     rax, [rdx+3]
0x18000149d  add     rdx, 0Bh
0x1800014a1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800014a6  mov     rax, [rcx+8]
0x1800014aa  mov     [r8], rax
0x1800014ad  mov     rax, [rcx+8]
0x1800014b1  mov     [rsp+48h+UserData], r8; UserData
0x1800014b6  movzx   ecx, word ptr [rax]
0x1800014b9  mov     [r8+8], ecx
0x1800014bd  lea     rcx, _TraceLoggingMetadata
0x1800014c4  mov     [r8+10h], rdx
0x1800014c8  mov     dword ptr [r8+0Ch], 2
0x1800014d0  movzx   eax, word ptr [rdx]
0x1800014d3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800014d8  mov     [r8+18h], eax
0x1800014dc  lea     rax, _TraceLoggingMetadataEnd
0x1800014e3  sub     eax, ecx
0x1800014e5  mov     dword ptr [r8+1Ch], 1
0x1800014ed  mov     dword ptr [rsp+48h+arg_28], eax
0x1800014f1  mov     r8, r10; ActivityId
0x1800014f4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800014f8  mov     eax, [rsp+48h+arg_20]
0x1800014fc  mov     rcx, [r11+20h]; RegHandle
0x180001500  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001504  call    cs:__imp_EventWriteTransfer
0x18000150a  add     rsp, 48h
0x18000150e  retn
```
