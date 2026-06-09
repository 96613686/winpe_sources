# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140002318`
- end: `0x1400023af`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`
- `0x1400012cc`
- `0x140001590`
- `0x14000187c`
- `0x1400018ec`
- `0x14000197c`
- `0x140001a3c`
- `0x140001ce0`
- `0x140001fd8`
- `0x14000209c`
- `0x1400050c8`
- `0x14000bb94`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400023a4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400023a4`

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
0x140002318  sub     rsp, 48h
0x14000231c  movzx   eax, byte ptr [rdx]
0x14000231f  mov     r11, rcx
0x140002322  shl     eax, 18h
0x140002325  mov     r10, r8
0x140002328  mov     r8, [rsp+48h+arg_28]
0x14000232d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140002331  movzx   eax, word ptr [rdx+1]
0x140002335  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140002339  mov     rax, [rdx+3]
0x14000233d  add     rdx, 0Bh
0x140002341  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140002346  mov     rax, [rcx+8]
0x14000234a  mov     [r8], rax
0x14000234d  mov     rax, [rcx+8]
0x140002351  mov     [rsp+48h+UserData], r8; UserData
0x140002356  movzx   ecx, word ptr [rax]
0x140002359  mov     [r8+8], ecx
0x14000235d  lea     rcx, _TraceLoggingMetadata
0x140002364  mov     [r8+10h], rdx
0x140002368  mov     dword ptr [r8+0Ch], 2
0x140002370  movzx   eax, word ptr [rdx]
0x140002373  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140002378  mov     [r8+18h], eax
0x14000237c  lea     rax, _TraceLoggingMetadataEnd
0x140002383  sub     eax, ecx
0x140002385  mov     dword ptr [r8+1Ch], 1
0x14000238d  mov     dword ptr [rsp+48h+arg_28], eax
0x140002391  mov     r8, r10; ActivityId
0x140002394  mov     eax, dword ptr [rsp+48h+arg_28]
0x140002398  mov     eax, [rsp+48h+arg_20]
0x14000239c  mov     rcx, [r11+20h]; RegHandle
0x1400023a0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400023a4  call    cs:__imp_EventWriteTransfer
0x1400023aa  add     rsp, 48h
0x1400023ae  retn
```
