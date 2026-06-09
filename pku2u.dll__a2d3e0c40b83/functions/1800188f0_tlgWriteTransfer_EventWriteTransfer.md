# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800188f0`
- end: `0x180018987`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000115c`
- `0x180001410`
- `0x18002de2c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001897c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001897c`

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
0x1800188f0  sub     rsp, 48h
0x1800188f4  movzx   eax, byte ptr [rdx]
0x1800188f7  mov     r11, rcx
0x1800188fa  shl     eax, 18h
0x1800188fd  mov     r10, r8
0x180018900  mov     r8, [rsp+48h+arg_28]
0x180018905  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180018909  movzx   eax, word ptr [rdx+1]
0x18001890d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180018911  mov     rax, [rdx+3]
0x180018915  add     rdx, 0Bh
0x180018919  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18001891e  mov     rax, [rcx+8]
0x180018922  mov     [r8], rax
0x180018925  mov     rax, [rcx+8]
0x180018929  mov     [rsp+48h+UserData], r8; UserData
0x18001892e  movzx   ecx, word ptr [rax]
0x180018931  mov     [r8+8], ecx
0x180018935  lea     rcx, _TraceLoggingMetadata
0x18001893c  mov     [r8+10h], rdx
0x180018940  mov     dword ptr [r8+0Ch], 2
0x180018948  movzx   eax, word ptr [rdx]
0x18001894b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180018950  mov     [r8+18h], eax
0x180018954  lea     rax, _TraceLoggingMetadataEnd
0x18001895b  sub     eax, ecx
0x18001895d  mov     dword ptr [r8+1Ch], 1
0x180018965  mov     dword ptr [rsp+48h+arg_28], eax
0x180018969  mov     r8, r10; ActivityId
0x18001896c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180018970  mov     eax, [rsp+48h+arg_20]
0x180018974  mov     rcx, [r11+20h]; RegHandle
0x180018978  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18001897c  call    cs:__imp_EventWriteTransfer
0x180018982  add     rsp, 48h
0x180018986  retn
```
