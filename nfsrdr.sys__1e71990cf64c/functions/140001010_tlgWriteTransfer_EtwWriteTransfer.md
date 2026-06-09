# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001010`
- end: `0x1400010b9`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `169`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14002246c`
- `0x140023000`
- `0x140023dd0`
- `0x140024720`
- `0x140024c60`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400010a7`
- `ntoskrnl!EtwWriteTransfer` at `0x1400010a7`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
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
  UserData->Ptr = (ULONGLONG)EventInformation;
  UserData->Size = *(unsigned __int16 *)EventInformation;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140001010  mov     [rsp+arg_18], r9
0x140001015  sub     rsp, 48h
0x140001019  movzx   eax, byte ptr [rdx]
0x14000101c  xor     r9d, r9d; RelatedActivityId
0x14000101f  mov     r8, [rsp+48h+arg_28]
0x140001024  shl     eax, 18h
0x140001027  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14000102b  movzx   eax, word ptr [rdx+1]
0x14000102f  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001033  mov     rax, [rdx+3]
0x140001037  add     rdx, 0Bh
0x14000103b  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001040  mov     rax, cs:EventInformation
0x140001047  mov     [r8], rax
0x14000104a  mov     rax, cs:EventInformation
0x140001051  mov     [rsp+48h+UserData], r8; UserData
0x140001056  movzx   ecx, word ptr [rax]
0x140001059  mov     [r8+8], ecx
0x14000105d  lea     rcx, _TraceLoggingMetadata
0x140001064  mov     [r8+10h], rdx
0x140001068  mov     dword ptr [r8+0Ch], 2
0x140001070  movzx   eax, word ptr [rdx]
0x140001073  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001078  mov     [r8+18h], eax
0x14000107c  lea     rax, _TraceLoggingMetadataEnd
0x140001083  sub     eax, ecx
0x140001085  mov     dword ptr [r8+1Ch], 1
0x14000108d  mov     dword ptr [rsp+48h+arg_18], eax
0x140001091  xor     r8d, r8d; ActivityId
0x140001094  mov     eax, dword ptr [rsp+48h+arg_18]
0x140001098  mov     eax, [rsp+48h+arg_20]
0x14000109c  mov     rcx, cs:RegHandle; RegHandle
0x1400010a3  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400010a7  call    cs:__imp_EtwWriteTransfer
0x1400010ae  nop     dword ptr [rax+rax+00h]
0x1400010b3  add     rsp, 48h
0x1400010b7  retn
```
