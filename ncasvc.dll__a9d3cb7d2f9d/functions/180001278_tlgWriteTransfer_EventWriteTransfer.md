# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001278`
- end: `0x180001316`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001180`
- `0x1800161c8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001304`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001304`

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
0x180001278  sub     rsp, 48h
0x18000127c  movzx   eax, byte ptr [rdx]
0x18000127f  mov     r11, rcx
0x180001282  shl     eax, 18h
0x180001285  mov     r10, r8
0x180001288  mov     r8, [rsp+48h+arg_28]
0x18000128d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001291  movzx   eax, word ptr [rdx+1]
0x180001295  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001299  mov     rax, [rdx+3]
0x18000129d  add     rdx, 0Bh
0x1800012a1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800012a6  mov     rax, [rcx+8]
0x1800012aa  mov     [r8], rax
0x1800012ad  mov     rax, [rcx+8]
0x1800012b1  mov     [rsp+48h+UserData], r8; UserData
0x1800012b6  movzx   ecx, word ptr [rax]
0x1800012b9  mov     [r8+8], ecx
0x1800012bd  lea     rcx, _TraceLoggingMetadata
0x1800012c4  mov     [r8+10h], rdx
0x1800012c8  mov     dword ptr [r8+0Ch], 2
0x1800012d0  movzx   eax, word ptr [rdx]
0x1800012d3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800012d8  mov     [r8+18h], eax
0x1800012dc  lea     rax, _TraceLoggingMetadataEnd
0x1800012e3  sub     eax, ecx
0x1800012e5  mov     dword ptr [r8+1Ch], 1
0x1800012ed  mov     dword ptr [rsp+48h+arg_28], eax
0x1800012f1  mov     r8, r10; ActivityId
0x1800012f4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800012f8  mov     eax, [rsp+48h+arg_20]
0x1800012fc  mov     rcx, [r11+20h]; RegHandle
0x180001300  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001304  call    cs:__imp_EventWriteTransfer
0x18000130b  nop     dword ptr [rax+rax+00h]
0x180001310  add     rsp, 48h
0x180001314  retn
```
