# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001bac`
- end: `0x140001c43`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140001590`
- `0x140001834`
- `0x1400035b8`
- `0x140004cbc`
- `0x14000d358`
- `0x14000d500`
- `0x14000d6e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c38`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c38`

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
0x140001bac  sub     rsp, 48h
0x140001bb0  movzx   eax, byte ptr [rdx]
0x140001bb3  mov     r11, rcx
0x140001bb6  shl     eax, 18h
0x140001bb9  mov     r10, r8
0x140001bbc  mov     r8, [rsp+48h+arg_28]
0x140001bc1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001bc5  movzx   eax, word ptr [rdx+1]
0x140001bc9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001bcd  mov     rax, [rdx+3]
0x140001bd1  add     rdx, 0Bh
0x140001bd5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001bda  mov     rax, [rcx+8]
0x140001bde  mov     [r8], rax
0x140001be1  mov     rax, [rcx+8]
0x140001be5  mov     [rsp+48h+UserData], r8; UserData
0x140001bea  movzx   ecx, word ptr [rax]
0x140001bed  mov     [r8+8], ecx
0x140001bf1  lea     rcx, _TraceLoggingMetadata
0x140001bf8  mov     [r8+10h], rdx
0x140001bfc  mov     dword ptr [r8+0Ch], 2
0x140001c04  movzx   eax, word ptr [rdx]
0x140001c07  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001c0c  mov     [r8+18h], eax
0x140001c10  lea     rax, _TraceLoggingMetadataEnd
0x140001c17  sub     eax, ecx
0x140001c19  mov     dword ptr [r8+1Ch], 1
0x140001c21  mov     dword ptr [rsp+48h+arg_28], eax
0x140001c25  mov     r8, r10; ActivityId
0x140001c28  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001c2c  mov     eax, [rsp+48h+arg_20]
0x140001c30  mov     rcx, [r11+20h]; RegHandle
0x140001c34  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001c38  call    cs:__imp_EventWriteTransfer
0x140001c3e  add     rsp, 48h
0x140001c42  retn
```
