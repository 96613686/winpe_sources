# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001464`
- end: `0x1800014fb`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x18000113c`
- `0x180001258`
- `0x180001370`
- `0x180001504`
- `0x180001694`
- `0x1800017f0`
- `0x1800018f0`
- `0x1800019e0`
- `0x180001aa4`
- `0x180001b68`
- `0x180001c10`
- `0x180001cb4`
- `0x180001d44`
- `0x180001ff8`
- `0x18000230c`
- `0x180002408`
- `0x1800026ac`
- `0x1800138e8`
- `0x180015500`
- `0x180016110`
- `0x180016f50`
- `0x180018a98`
- `0x180018d14`
- `0x18001b0f8`
- `0x18001bd24`
- `0x18001beb4`
- `0x180024b94`
- `0x180026d2c`
- `0x18002dc14`
- `0x18002dd58`
- `0x18002de9c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014f0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014f0`

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
0x180001464  sub     rsp, 48h
0x180001468  movzx   eax, byte ptr [rdx]
0x18000146b  mov     r11, rcx
0x18000146e  shl     eax, 18h
0x180001471  mov     r10, r8
0x180001474  mov     r8, [rsp+48h+arg_28]
0x180001479  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000147d  movzx   eax, word ptr [rdx+1]
0x180001481  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001485  mov     rax, [rdx+3]
0x180001489  add     rdx, 0Bh
0x18000148d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001492  mov     rax, [rcx+8]
0x180001496  mov     [r8], rax
0x180001499  mov     rax, [rcx+8]
0x18000149d  mov     [rsp+48h+UserData], r8; UserData
0x1800014a2  movzx   ecx, word ptr [rax]
0x1800014a5  mov     [r8+8], ecx
0x1800014a9  lea     rcx, _TraceLoggingMetadata
0x1800014b0  mov     [r8+10h], rdx
0x1800014b4  mov     dword ptr [r8+0Ch], 2
0x1800014bc  movzx   eax, word ptr [rdx]
0x1800014bf  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800014c4  mov     [r8+18h], eax
0x1800014c8  lea     rax, _TraceLoggingMetadataEnd
0x1800014cf  sub     eax, ecx
0x1800014d1  mov     dword ptr [r8+1Ch], 1
0x1800014d9  mov     dword ptr [rsp+48h+arg_28], eax
0x1800014dd  mov     r8, r10; ActivityId
0x1800014e0  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800014e4  mov     eax, [rsp+48h+arg_20]
0x1800014e8  mov     rcx, [r11+20h]; RegHandle
0x1800014ec  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800014f0  call    cs:__imp_EventWriteTransfer
0x1800014f6  add     rsp, 48h
0x1800014fa  retn
```
