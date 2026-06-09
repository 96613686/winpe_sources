# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800137a4`
- end: `0x18001383b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `46`
- callee_count: `0`
- tags: ``

## callers

- `0x18000102c`
- `0x1800037f4`
- `0x180003ec8`
- `0x1800047b0`
- `0x180004d80`
- `0x180004f08`
- `0x1800051bc`
- `0x1800056e8`
- `0x180005b0c`
- `0x180005ed0`
- `0x1800065a0`
- `0x180006b7c`
- `0x180006e28`
- `0x1800070e4`
- `0x18000a750`
- `0x18000b4d8`
- `0x18000defc`
- `0x18000e2cc`
- `0x18000e3d0`
- `0x180010e64`
- `0x180011074`
- `0x180011260`
- `0x180013754`
- `0x1800139d0`
- `0x180014800`
- `0x1800162b0`
- `0x180016544`
- `0x180016990`
- `0x180016d90`
- `0x180016ed0`
- `0x1800180d0`
- `0x1800184a0`
- `0x1800187c0`
- `0x180018e98`
- `0x180019100`
- `0x180019430`
- `0x180019810`
- `0x18001dc40`
- `0x18001f0a0`
- `0x18001f1b0`
- `0x1800245dc`
- `0x1800246bc`
- `0x180024c90`
- `0x1800252e0`
- `0x180025460`
- `0x1800281f8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013830`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013830`

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
0x1800137a4  sub     rsp, 48h
0x1800137a8  movzx   eax, byte ptr [rdx]
0x1800137ab  mov     r11, rcx
0x1800137ae  shl     eax, 18h
0x1800137b1  mov     r10, r8
0x1800137b4  mov     r8, [rsp+48h+arg_28]
0x1800137b9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800137bd  movzx   eax, word ptr [rdx+1]
0x1800137c1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800137c5  mov     rax, [rdx+3]
0x1800137c9  add     rdx, 0Bh
0x1800137cd  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800137d2  mov     rax, [rcx+8]
0x1800137d6  mov     [r8], rax
0x1800137d9  mov     rax, [rcx+8]
0x1800137dd  mov     [rsp+48h+UserData], r8; UserData
0x1800137e2  movzx   ecx, word ptr [rax]
0x1800137e5  mov     [r8+8], ecx
0x1800137e9  lea     rcx, _TraceLoggingMetadata
0x1800137f0  mov     [r8+10h], rdx
0x1800137f4  mov     dword ptr [r8+0Ch], 2
0x1800137fc  movzx   eax, word ptr [rdx]
0x1800137ff  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180013804  mov     [r8+18h], eax
0x180013808  lea     rax, _TraceLoggingMetadataEnd
0x18001380f  sub     eax, ecx
0x180013811  mov     dword ptr [r8+1Ch], 1
0x180013819  mov     dword ptr [rsp+48h+arg_28], eax
0x18001381d  mov     r8, r10; ActivityId
0x180013820  mov     eax, dword ptr [rsp+48h+arg_28]
0x180013824  mov     eax, [rsp+48h+arg_20]
0x180013828  mov     rcx, [r11+20h]; RegHandle
0x18001382c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180013830  call    cs:__imp_EventWriteTransfer
0x180013836  add     rsp, 48h
0x18001383a  retn
```
