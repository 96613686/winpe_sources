# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400011ac`
- end: `0x140001243`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x14000124c`
- `0x14000132c`
- `0x140001424`
- `0x140001518`
- `0x1400015a8`
- `0x140008f54`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001238`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001238`

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
0x1400011ac  sub     rsp, 48h
0x1400011b0  movzx   eax, byte ptr [rdx]
0x1400011b3  mov     r11, rcx
0x1400011b6  shl     eax, 18h
0x1400011b9  mov     r10, r8
0x1400011bc  mov     r8, [rsp+48h+arg_28]
0x1400011c1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400011c5  movzx   eax, word ptr [rdx+1]
0x1400011c9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400011cd  mov     rax, [rdx+3]
0x1400011d1  add     rdx, 0Bh
0x1400011d5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400011da  mov     rax, [rcx+8]
0x1400011de  mov     [r8], rax
0x1400011e1  mov     rax, [rcx+8]
0x1400011e5  mov     [rsp+48h+UserData], r8; UserData
0x1400011ea  movzx   ecx, word ptr [rax]
0x1400011ed  mov     [r8+8], ecx
0x1400011f1  lea     rcx, _TraceLoggingMetadata
0x1400011f8  mov     [r8+10h], rdx
0x1400011fc  mov     dword ptr [r8+0Ch], 2
0x140001204  movzx   eax, word ptr [rdx]
0x140001207  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x14000120c  mov     [r8+18h], eax
0x140001210  lea     rax, _TraceLoggingMetadataEnd
0x140001217  sub     eax, ecx
0x140001219  mov     dword ptr [r8+1Ch], 1
0x140001221  mov     dword ptr [rsp+48h+arg_28], eax
0x140001225  mov     r8, r10; ActivityId
0x140001228  mov     eax, dword ptr [rsp+48h+arg_28]
0x14000122c  mov     eax, [rsp+48h+arg_20]
0x140001230  mov     rcx, [r11+20h]; RegHandle
0x140001234  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001238  call    cs:__imp_EventWriteTransfer
0x14000123e  add     rsp, 48h
0x140001242  retn
```
