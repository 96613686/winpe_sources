# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x14001d60c`
- end: `0x14001d6aa`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000c1cc`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001d698`
- `ntoskrnl!EtwWriteTransfer` at `0x14001d698`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
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
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14001d60c  sub     rsp, 48h
0x14001d610  movzx   eax, byte ptr [rdx]
0x14001d613  mov     r11, rcx
0x14001d616  shl     eax, 18h
0x14001d619  mov     r10, r8
0x14001d61c  mov     r8, [rsp+48h+arg_28]
0x14001d621  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14001d625  movzx   eax, word ptr [rdx+1]
0x14001d629  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x14001d62d  mov     rax, [rdx+3]
0x14001d631  add     rdx, 0Bh
0x14001d635  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14001d63a  mov     rax, [rcx+8]
0x14001d63e  mov     [r8], rax
0x14001d641  mov     rax, [rcx+8]
0x14001d645  mov     [rsp+48h+UserData], r8; UserData
0x14001d64a  movzx   ecx, word ptr [rax]
0x14001d64d  mov     [r8+8], ecx
0x14001d651  lea     rcx, _TraceLoggingMetadata
0x14001d658  mov     [r8+10h], rdx
0x14001d65c  mov     dword ptr [r8+0Ch], 2
0x14001d664  movzx   eax, word ptr [rdx]
0x14001d667  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x14001d66c  mov     [r8+18h], eax
0x14001d670  lea     rax, _TraceLoggingMetadataEnd
0x14001d677  sub     eax, ecx
0x14001d679  mov     dword ptr [r8+1Ch], 1
0x14001d681  mov     dword ptr [rsp+48h+arg_28], eax
0x14001d685  mov     r8, r10; ActivityId
0x14001d688  mov     eax, dword ptr [rsp+48h+arg_28]
0x14001d68c  mov     eax, [rsp+48h+arg_20]
0x14001d690  mov     rcx, [r11+20h]; RegHandle
0x14001d694  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x14001d698  call    cs:__imp_EtwWriteTransfer
0x14001d69f  nop     dword ptr [rax+rax+00h]
0x14001d6a4  add     rsp, 48h
0x14001d6a8  retn
```
