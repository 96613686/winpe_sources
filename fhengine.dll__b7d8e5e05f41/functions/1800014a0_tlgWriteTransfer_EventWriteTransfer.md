# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800014a0`
- end: `0x180001537`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180025db0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18000152c`
- `ADVAPI32!EventWriteTransfer` at `0x18000152c`

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
0x1800014a0  sub     rsp, 48h
0x1800014a4  movzx   eax, byte ptr [rdx]
0x1800014a7  mov     r11, rcx
0x1800014aa  shl     eax, 18h
0x1800014ad  mov     r10, r8
0x1800014b0  mov     r8, [rsp+48h+arg_28]
0x1800014b5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800014b9  movzx   eax, word ptr [rdx+1]
0x1800014bd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800014c1  mov     rax, [rdx+3]
0x1800014c5  add     rdx, 0Bh
0x1800014c9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800014ce  mov     rax, [rcx+8]
0x1800014d2  mov     [r8], rax
0x1800014d5  mov     rax, [rcx+8]
0x1800014d9  mov     [rsp+48h+UserData], r8; UserData
0x1800014de  movzx   ecx, word ptr [rax]
0x1800014e1  mov     [r8+8], ecx
0x1800014e5  lea     rcx, _TraceLoggingMetadata
0x1800014ec  mov     [r8+10h], rdx
0x1800014f0  mov     dword ptr [r8+0Ch], 2
0x1800014f8  movzx   eax, word ptr [rdx]
0x1800014fb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001500  mov     [r8+18h], eax
0x180001504  lea     rax, _TraceLoggingMetadataEnd
0x18000150b  sub     eax, ecx
0x18000150d  mov     dword ptr [r8+1Ch], 1
0x180001515  mov     dword ptr [rsp+48h+arg_28], eax
0x180001519  mov     r8, r10; ActivityId
0x18000151c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001520  mov     eax, [rsp+48h+arg_20]
0x180001524  mov     rcx, [r11+20h]; RegHandle
0x180001528  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000152c  call    cs:__imp_EventWriteTransfer
0x180001532  add     rsp, 48h
0x180001536  retn
```
