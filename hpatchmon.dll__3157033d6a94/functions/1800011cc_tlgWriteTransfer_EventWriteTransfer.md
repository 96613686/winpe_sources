# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800011cc`
- end: `0x180001263`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `28`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18000126c`
- `0x18000132c`
- `0x180001408`
- `0x1800014d8`
- `0x180001580`
- `0x180001624`
- `0x1800016d8`
- `0x1800017d4`
- `0x180002fb0`
- `0x180005070`
- `0x1800051d8`
- `0x180006f90`
- `0x180007400`
- `0x1800075a0`
- `0x180009a80`
- `0x18000b294`
- `0x18000baf0`
- `0x18000df40`
- `0x18000eca0`
- `0x18000ed44`
- `0x18000fa50`
- `0x18000ffe0`
- `0x180010710`
- `0x180011414`
- `0x1800114a4`
- `0x1800115c0`
- `0x180011770`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001258`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001258`

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
0x1800011cc  sub     rsp, 48h
0x1800011d0  movzx   eax, byte ptr [rdx]
0x1800011d3  mov     r11, rcx
0x1800011d6  shl     eax, 18h
0x1800011d9  mov     r10, r8
0x1800011dc  mov     r8, [rsp+48h+arg_28]
0x1800011e1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800011e5  movzx   eax, word ptr [rdx+1]
0x1800011e9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800011ed  mov     rax, [rdx+3]
0x1800011f1  add     rdx, 0Bh
0x1800011f5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800011fa  mov     rax, [rcx+8]
0x1800011fe  mov     [r8], rax
0x180001201  mov     rax, [rcx+8]
0x180001205  mov     [rsp+48h+UserData], r8; UserData
0x18000120a  movzx   ecx, word ptr [rax]
0x18000120d  mov     [r8+8], ecx
0x180001211  lea     rcx, _TraceLoggingMetadata
0x180001218  mov     [r8+10h], rdx
0x18000121c  mov     dword ptr [r8+0Ch], 2
0x180001224  movzx   eax, word ptr [rdx]
0x180001227  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000122c  mov     [r8+18h], eax
0x180001230  lea     rax, _TraceLoggingMetadataEnd
0x180001237  sub     eax, ecx
0x180001239  mov     dword ptr [r8+1Ch], 1
0x180001241  mov     dword ptr [rsp+48h+arg_28], eax
0x180001245  mov     r8, r10; ActivityId
0x180001248  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000124c  mov     eax, [rsp+48h+arg_20]
0x180001250  mov     rcx, [r11+20h]; RegHandle
0x180001254  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001258  call    cs:__imp_EventWriteTransfer
0x18000125e  add     rsp, 48h
0x180001262  retn
```
