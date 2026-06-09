# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001010`
- end: `0x1400010ae`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x140001124`
- `0x14004d2a8`
- `0x14004d454`
- `0x1400501d0`
- `0x1400510ac`
- `0x14005202c`
- `0x1400566c4`
- `0x14005693c`
- `0x1400578ac`
- `0x140058934`
- `0x140058a00`
- `0x140058b0c`
- `0x140058ba4`
- `0x140058ce4`
- `0x1400592f0`
- `0x140059940`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000109c`
- `ntoskrnl!EtwWriteTransfer` at `0x14000109c`

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
0x140001010  sub     rsp, 48h
0x140001014  movzx   eax, byte ptr [rdx]
0x140001017  mov     r11, rcx
0x14000101a  shl     eax, 18h
0x14000101d  mov     r10, r8
0x140001020  mov     r8, [rsp+48h+arg_28]
0x140001025  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001029  movzx   eax, word ptr [rdx+1]
0x14000102d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001031  mov     rax, [rdx+3]
0x140001035  add     rdx, 0Bh
0x140001039  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000103e  mov     rax, [rcx+8]
0x140001042  mov     [r8], rax
0x140001045  mov     rax, [rcx+8]
0x140001049  mov     [rsp+48h+UserData], r8; UserData
0x14000104e  movzx   ecx, word ptr [rax]
0x140001051  mov     [r8+8], ecx
0x140001055  lea     rcx, _TraceLoggingMetadata
0x14000105c  mov     [r8+10h], rdx
0x140001060  mov     dword ptr [r8+0Ch], 2
0x140001068  movzx   eax, word ptr [rdx]
0x14000106b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001070  mov     [r8+18h], eax
0x140001074  lea     rax, _TraceLoggingMetadataEnd
0x14000107b  sub     eax, ecx
0x14000107d  mov     dword ptr [r8+1Ch], 1
0x140001085  mov     dword ptr [rsp+48h+arg_28], eax
0x140001089  mov     r8, r10; ActivityId
0x14000108c  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001090  mov     eax, [rsp+48h+arg_20]
0x140001094  mov     rcx, [r11+20h]; RegHandle
0x140001098  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x14000109c  call    cs:__imp_EtwWriteTransfer
0x1400010a3  nop     dword ptr [rax+rax+00h]
0x1400010a8  add     rsp, 48h
0x1400010ac  retn
```
