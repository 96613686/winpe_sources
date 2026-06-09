# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001e10`
- end: `0x180001eae`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `28`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001098`
- `0x18000134c`
- `0x180001660`
- `0x1800016f0`
- `0x1800017ec`
- `0x180001a90`
- `0x180001eb4`
- `0x180001f4c`
- `0x18000202c`
- `0x180002148`
- `0x18000223c`
- `0x180004af4`
- `0x18000c69c`
- `0x18000cf0c`
- `0x18000fb90`
- `0x1800101ec`
- `0x18001acbc`
- `0x180020bc4`
- `0x180026588`
- `0x18002666c`
- `0x1800277a8`
- `0x1800279c4`
- `0x180027db0`
- `0x180027f20`
- `0x180028100`
- `0x18002b5ac`
- `0x18002b710`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001e9c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001e9c`

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
0x180001e10  sub     rsp, 48h
0x180001e14  movzx   eax, byte ptr [rdx]
0x180001e17  mov     r11, rcx
0x180001e1a  shl     eax, 18h
0x180001e1d  mov     r10, r8
0x180001e20  mov     r8, [rsp+48h+arg_28]
0x180001e25  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001e29  movzx   eax, word ptr [rdx+1]
0x180001e2d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001e31  mov     rax, [rdx+3]
0x180001e35  add     rdx, 0Bh
0x180001e39  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001e3e  mov     rax, [rcx+8]
0x180001e42  mov     [r8], rax
0x180001e45  mov     rax, [rcx+8]
0x180001e49  mov     [rsp+48h+UserData], r8; UserData
0x180001e4e  movzx   ecx, word ptr [rax]
0x180001e51  mov     [r8+8], ecx
0x180001e55  lea     rcx, _TraceLoggingMetadata
0x180001e5c  mov     [r8+10h], rdx
0x180001e60  mov     dword ptr [r8+0Ch], 2
0x180001e68  movzx   eax, word ptr [rdx]
0x180001e6b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001e70  mov     [r8+18h], eax
0x180001e74  lea     rax, _TraceLoggingMetadataEnd
0x180001e7b  sub     eax, ecx
0x180001e7d  mov     dword ptr [r8+1Ch], 1
0x180001e85  mov     dword ptr [rsp+48h+arg_28], eax
0x180001e89  mov     r8, r10; ActivityId
0x180001e8c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001e90  mov     eax, [rsp+48h+arg_20]
0x180001e94  mov     rcx, [r11+20h]; RegHandle
0x180001e98  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001e9c  call    cs:__imp_EventWriteTransfer
0x180001ea3  nop     dword ptr [rax+rax+00h]
0x180001ea8  add     rsp, 48h
0x180001eac  retn
```
