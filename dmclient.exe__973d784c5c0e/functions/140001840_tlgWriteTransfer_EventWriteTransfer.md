# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001840`
- end: `0x1400018de`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x140001098`
- `0x140001418`
- `0x14000153c`
- `0x140001604`
- `0x1400018e4`
- `0x1400019a8`
- `0x140001a9c`
- `0x140001bb4`
- `0x140001c5c`
- `0x140001d80`
- `0x14000784c`
- `0x140011580`
- `0x140011cd0`
- `0x140012928`
- `0x140018700`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400018cc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400018cc`

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
0x140001840  sub     rsp, 48h
0x140001844  movzx   eax, byte ptr [rdx]
0x140001847  mov     r11, rcx
0x14000184a  shl     eax, 18h
0x14000184d  mov     r10, r8
0x140001850  mov     r8, [rsp+48h+arg_28]
0x140001855  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001859  movzx   eax, word ptr [rdx+1]
0x14000185d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001861  mov     rax, [rdx+3]
0x140001865  add     rdx, 0Bh
0x140001869  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000186e  mov     rax, [rcx+8]
0x140001872  mov     [r8], rax
0x140001875  mov     rax, [rcx+8]
0x140001879  mov     [rsp+48h+UserData], r8; UserData
0x14000187e  movzx   ecx, word ptr [rax]
0x140001881  mov     [r8+8], ecx
0x140001885  lea     rcx, _TraceLoggingMetadata
0x14000188c  mov     [r8+10h], rdx
0x140001890  mov     dword ptr [r8+0Ch], 2
0x140001898  movzx   eax, word ptr [rdx]
0x14000189b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400018a0  mov     [r8+18h], eax
0x1400018a4  lea     rax, _TraceLoggingMetadataEnd
0x1400018ab  sub     eax, ecx
0x1400018ad  mov     dword ptr [r8+1Ch], 1
0x1400018b5  mov     dword ptr [rsp+48h+arg_28], eax
0x1400018b9  mov     r8, r10; ActivityId
0x1400018bc  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400018c0  mov     eax, [rsp+48h+arg_20]
0x1400018c4  mov     rcx, [r11+20h]; RegHandle
0x1400018c8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400018cc  call    cs:__imp_EventWriteTransfer
0x1400018d3  nop     dword ptr [rax+rax+00h]
0x1400018d8  add     rsp, 48h
0x1400018dc  retn
```
