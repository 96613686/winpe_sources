# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800011e4`
- end: `0x18000127b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000113c`
- `0x180001284`
- `0x18000132c`
- `0x18000fff8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001270`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001270`

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
0x1800011e4  sub     rsp, 48h
0x1800011e8  movzx   eax, byte ptr [rdx]
0x1800011eb  mov     r11, rcx
0x1800011ee  shl     eax, 18h
0x1800011f1  mov     r10, r8
0x1800011f4  mov     r8, [rsp+48h+arg_28]
0x1800011f9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800011fd  movzx   eax, word ptr [rdx+1]
0x180001201  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001205  mov     rax, [rdx+3]
0x180001209  add     rdx, 0Bh
0x18000120d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001212  mov     rax, [rcx+8]
0x180001216  mov     [r8], rax
0x180001219  mov     rax, [rcx+8]
0x18000121d  mov     [rsp+48h+UserData], r8; UserData
0x180001222  movzx   ecx, word ptr [rax]
0x180001225  mov     [r8+8], ecx
0x180001229  lea     rcx, _TraceLoggingMetadata
0x180001230  mov     [r8+10h], rdx
0x180001234  mov     dword ptr [r8+0Ch], 2
0x18000123c  movzx   eax, word ptr [rdx]
0x18000123f  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001244  mov     [r8+18h], eax
0x180001248  lea     rax, _TraceLoggingMetadataEnd
0x18000124f  sub     eax, ecx
0x180001251  mov     dword ptr [r8+1Ch], 1
0x180001259  mov     dword ptr [rsp+48h+arg_28], eax
0x18000125d  mov     r8, r10; ActivityId
0x180001260  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001264  mov     eax, [rsp+48h+arg_20]
0x180001268  mov     rcx, [r11+20h]; RegHandle
0x18000126c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001270  call    cs:__imp_EventWriteTransfer
0x180001276  add     rsp, 48h
0x18000127a  retn
```
