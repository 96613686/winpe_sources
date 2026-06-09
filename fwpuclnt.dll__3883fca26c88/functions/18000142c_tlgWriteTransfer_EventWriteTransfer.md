# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000142c`
- end: `0x1800014ca`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014b8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014b8`

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
0x18000142c  sub     rsp, 48h
0x180001430  movzx   eax, byte ptr [rdx]
0x180001433  mov     r11, rcx
0x180001436  shl     eax, 18h
0x180001439  mov     r10, r8
0x18000143c  mov     r8, [rsp+48h+arg_28]
0x180001441  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001445  movzx   eax, word ptr [rdx+1]
0x180001449  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000144d  mov     rax, [rdx+3]
0x180001451  add     rdx, 0Bh
0x180001455  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000145a  mov     rax, [rcx+8]
0x18000145e  mov     [r8], rax
0x180001461  mov     rax, [rcx+8]
0x180001465  mov     [rsp+48h+UserData], r8; UserData
0x18000146a  movzx   ecx, word ptr [rax]
0x18000146d  mov     [r8+8], ecx
0x180001471  lea     rcx, _TraceLoggingMetadata
0x180001478  mov     [r8+10h], rdx
0x18000147c  mov     dword ptr [r8+0Ch], 2
0x180001484  movzx   eax, word ptr [rdx]
0x180001487  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000148c  mov     [r8+18h], eax
0x180001490  lea     rax, _TraceLoggingMetadataEnd
0x180001497  sub     eax, ecx
0x180001499  mov     dword ptr [r8+1Ch], 1
0x1800014a1  mov     dword ptr [rsp+48h+arg_28], eax
0x1800014a5  mov     r8, r10; ActivityId
0x1800014a8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800014ac  mov     eax, [rsp+48h+arg_20]
0x1800014b0  mov     rcx, [r11+20h]; RegHandle
0x1800014b4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800014b8  call    cs:__imp_EventWriteTransfer
0x1800014bf  nop     dword ptr [rax+rax+00h]
0x1800014c4  add     rsp, 48h
0x1800014c8  retn
```
