# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001170`
- end: `0x140001207`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140094a40`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400011fc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400011fc`

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
0x140001170  sub     rsp, 48h
0x140001174  movzx   eax, byte ptr [rdx]
0x140001177  mov     r11, rcx
0x14000117a  shl     eax, 18h
0x14000117d  mov     r10, r8
0x140001180  mov     r8, [rsp+48h+arg_28]
0x140001185  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001189  movzx   eax, word ptr [rdx+1]
0x14000118d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001191  mov     rax, [rdx+3]
0x140001195  add     rdx, 0Bh
0x140001199  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000119e  mov     rax, [rcx+8]
0x1400011a2  mov     [r8], rax
0x1400011a5  mov     rax, [rcx+8]
0x1400011a9  mov     [rsp+48h+UserData], r8; UserData
0x1400011ae  movzx   ecx, word ptr [rax]
0x1400011b1  mov     [r8+8], ecx
0x1400011b5  lea     rcx, _TraceLoggingMetadata
0x1400011bc  mov     [r8+10h], rdx
0x1400011c0  mov     dword ptr [r8+0Ch], 2
0x1400011c8  movzx   eax, word ptr [rdx]
0x1400011cb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400011d0  mov     [r8+18h], eax
0x1400011d4  lea     rax, _TraceLoggingMetadataEnd
0x1400011db  sub     eax, ecx
0x1400011dd  mov     dword ptr [r8+1Ch], 1
0x1400011e5  mov     dword ptr [rsp+48h+arg_28], eax
0x1400011e9  mov     r8, r10; ActivityId
0x1400011ec  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400011f0  mov     eax, [rsp+48h+arg_20]
0x1400011f4  mov     rcx, [r11+20h]; RegHandle
0x1400011f8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400011fc  call    cs:__imp_EventWriteTransfer
0x140001202  add     rsp, 48h
0x140001206  retn
```
