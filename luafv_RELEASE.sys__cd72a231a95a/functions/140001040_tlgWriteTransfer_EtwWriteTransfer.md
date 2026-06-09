# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001040`
- end: `0x1400010e4`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `164`
- prototype: `NTSTATUS __fastcall(__int64, unsigned __int8 *, __int64, __int64, int, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140023cc4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400010d2`
- `ntoskrnl!EtwWriteTransfer` at `0x1400010d2`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
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
  UserData->Ptr = (ULONGLONG)EventInformation;
  UserData->Size = *(unsigned __int16 *)EventInformation;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, UserData);
}

```

## disassembly

```asm
0x140001040  sub     rsp, 48h
0x140001044  movzx   eax, byte ptr [rdx]
0x140001047  xor     r9d, r9d; RelatedActivityId
0x14000104a  mov     r8, [rsp+48h+arg_28]
0x14000104f  shl     eax, 18h
0x140001052  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001056  movzx   eax, word ptr [rdx+1]
0x14000105a  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x14000105e  mov     rax, [rdx+3]
0x140001062  add     rdx, 0Bh
0x140001066  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000106b  mov     rax, cs:EventInformation
0x140001072  mov     [r8], rax
0x140001075  mov     rax, cs:EventInformation
0x14000107c  mov     [rsp+48h+UserData], r8; UserData
0x140001081  mov     [rsp+48h+UserDataCount], 6; UserDataCount
0x140001089  movzx   ecx, word ptr [rax]
0x14000108c  mov     [r8+8], ecx
0x140001090  lea     rcx, _TraceLoggingMetadata
0x140001097  mov     [r8+10h], rdx
0x14000109b  mov     dword ptr [r8+0Ch], 2
0x1400010a3  movzx   eax, word ptr [rdx]
0x1400010a6  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400010ab  mov     [r8+18h], eax
0x1400010af  lea     rax, _TraceLoggingMetadataEnd
0x1400010b6  sub     eax, ecx
0x1400010b8  mov     dword ptr [r8+1Ch], 1
0x1400010c0  mov     [rsp+48h+arg_20], eax
0x1400010c4  xor     r8d, r8d; ActivityId
0x1400010c7  mov     eax, [rsp+48h+arg_20]
0x1400010cb  mov     rcx, cs:RegHandle; RegHandle
0x1400010d2  call    cs:__imp_EtwWriteTransfer
0x1400010d9  nop     dword ptr [rax+rax+00h]
0x1400010de  add     rsp, 48h
0x1400010e2  retn
```
