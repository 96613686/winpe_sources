# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001e74`
- end: `0x180001f12`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x180001150`
- `0x1800011f8`
- `0x180001354`
- `0x1800014a0`
- `0x1800015c8`
- `0x1800016b8`
- `0x1800017ac`
- `0x18000186c`
- `0x1800019a4`
- `0x180001a64`
- `0x180001b28`
- `0x180001c18`
- `0x180001d08`
- `0x180001dcc`
- `0x180042510`
- `0x1800426f0`
- `0x18004284c`
- `0x180042d20`
- `0x180043738`
- `0x1800438ac`
- `0x180043bd0`
- `0x180043e58`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001f00`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001f00`

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
0x180001e74  sub     rsp, 48h
0x180001e78  movzx   eax, byte ptr [rdx]
0x180001e7b  mov     r11, rcx
0x180001e7e  shl     eax, 18h
0x180001e81  mov     r10, r8
0x180001e84  mov     r8, [rsp+48h+arg_28]
0x180001e89  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001e8d  movzx   eax, word ptr [rdx+1]
0x180001e91  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001e95  mov     rax, [rdx+3]
0x180001e99  add     rdx, 0Bh
0x180001e9d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001ea2  mov     rax, [rcx+8]
0x180001ea6  mov     [r8], rax
0x180001ea9  mov     rax, [rcx+8]
0x180001ead  mov     [rsp+48h+UserData], r8; UserData
0x180001eb2  movzx   ecx, word ptr [rax]
0x180001eb5  mov     [r8+8], ecx
0x180001eb9  lea     rcx, _TraceLoggingMetadata
0x180001ec0  mov     [r8+10h], rdx
0x180001ec4  mov     dword ptr [r8+0Ch], 2
0x180001ecc  movzx   eax, word ptr [rdx]
0x180001ecf  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001ed4  mov     [r8+18h], eax
0x180001ed8  lea     rax, _TraceLoggingMetadataEnd
0x180001edf  sub     eax, ecx
0x180001ee1  mov     dword ptr [r8+1Ch], 1
0x180001ee9  mov     dword ptr [rsp+48h+arg_28], eax
0x180001eed  mov     r8, r10; ActivityId
0x180001ef0  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001ef4  mov     eax, [rsp+48h+arg_20]
0x180001ef8  mov     rcx, [r11+20h]; RegHandle
0x180001efc  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001f00  call    cs:__imp_EventWriteTransfer
0x180001f07  nop     dword ptr [rax+rax+00h]
0x180001f0c  add     rsp, 48h
0x180001f10  retn
```
