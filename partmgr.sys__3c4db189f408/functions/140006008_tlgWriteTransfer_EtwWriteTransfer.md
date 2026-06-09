# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140006008`
- end: `0x1400060a6`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400010ac`
- `0x140001160`
- `0x14000191c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140006094`
- `ntoskrnl!EtwWriteTransfer` at `0x140006094`

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
0x140006008  sub     rsp, 48h
0x14000600c  movzx   eax, byte ptr [rdx]
0x14000600f  mov     r11, rcx
0x140006012  shl     eax, 18h
0x140006015  mov     r10, r8
0x140006018  mov     r8, [rsp+48h+arg_28]
0x14000601d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140006021  movzx   eax, word ptr [rdx+1]
0x140006025  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140006029  mov     rax, [rdx+3]
0x14000602d  add     rdx, 0Bh
0x140006031  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140006036  mov     rax, [rcx+8]
0x14000603a  mov     [r8], rax
0x14000603d  mov     rax, [rcx+8]
0x140006041  mov     [rsp+48h+UserData], r8; UserData
0x140006046  movzx   ecx, word ptr [rax]
0x140006049  mov     [r8+8], ecx
0x14000604d  lea     rcx, _TraceLoggingMetadata
0x140006054  mov     [r8+10h], rdx
0x140006058  mov     dword ptr [r8+0Ch], 2
0x140006060  movzx   eax, word ptr [rdx]
0x140006063  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140006068  mov     [r8+18h], eax
0x14000606c  lea     rax, _TraceLoggingMetadataEnd
0x140006073  sub     eax, ecx
0x140006075  mov     dword ptr [r8+1Ch], 1
0x14000607d  mov     dword ptr [rsp+48h+arg_28], eax
0x140006081  mov     r8, r10; ActivityId
0x140006084  mov     eax, dword ptr [rsp+48h+arg_28]
0x140006088  mov     eax, [rsp+48h+arg_20]
0x14000608c  mov     rcx, [r11+20h]; RegHandle
0x140006090  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140006094  call    cs:__imp_EtwWriteTransfer
0x14000609b  nop     dword ptr [rax+rax+00h]
0x1400060a0  add     rsp, 48h
0x1400060a4  retn
```
