# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001040`
- end: `0x1400010e8`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `168`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, __int64)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x140009a30`
- `0x140009aac`
- `0x140009b28`
- `0x140009ba4`
- `0x140009c64`
- `0x140009f9c`
- `0x14000a018`
- `0x14000a394`
- `0x14000a410`
- `0x14000a48c`
- `0x14000a508`
- `0x14000a584`
- `0x14000a600`
- `0x14000b23c`
- `0x14000b2b8`
- `0x14000bb7c`
- `0x14000bbf8`
- `0x14000bc74`
- `0x14000bcf0`
- `0x14000cbe0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400010d6`
- `ntoskrnl!EtwWriteTransfer` at `0x1400010d6`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        ULONG UserDataCount,
        struct _EVENT_DATA_DESCRIPTOR *a6)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR v9; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&v9.Id = *a2 << 24;
  *(_DWORD *)&v9.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  v9.Keyword = v6;
  a6->Ptr = (ULONGLONG)EventInformation;
  a6->Size = *(unsigned __int16 *)EventInformation;
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EtwWriteTransfer(RegHandle, &v9, 0, 0, UserDataCount, a6);
}

```

## disassembly

```asm
0x140001040  mov     r11, rsp
0x140001043  mov     [r11+20h], r9
0x140001047  sub     rsp, 48h
0x14000104b  movzx   eax, byte ptr [rdx]
0x14000104e  xor     r9d, r9d; RelatedActivityId
0x140001051  mov     r8, [rsp+48h+arg_28]
0x140001056  shl     eax, 18h
0x140001059  mov     [rsp+48h+var_18], eax
0x14000105d  movzx   eax, word ptr [rdx+1]
0x140001061  mov     [rsp+48h+var_14], eax
0x140001065  mov     rax, [rdx+3]
0x140001069  add     rdx, 0Bh
0x14000106d  mov     [r11-10h], rax
0x140001071  mov     rax, cs:EventInformation
0x140001078  mov     [r8], rax
0x14000107b  mov     rax, cs:EventInformation
0x140001082  mov     [r11-20h], r8
0x140001086  movzx   ecx, word ptr [rax]
0x140001089  mov     [r8+8], ecx
0x14000108d  lea     rcx, _TraceLoggingMetadata
0x140001094  mov     [r8+10h], rdx
0x140001098  mov     dword ptr [r8+0Ch], 2
0x1400010a0  movzx   eax, word ptr [rdx]
0x1400010a3  lea     rdx, [r11-18h]; EventDescriptor
0x1400010a7  mov     [r8+18h], eax
0x1400010ab  lea     rax, _TraceLoggingMetadataEnd
0x1400010b2  sub     eax, ecx
0x1400010b4  mov     dword ptr [r8+1Ch], 1
0x1400010bc  mov     [rsp+48h+arg_18], eax
0x1400010c0  xor     r8d, r8d; ActivityId
0x1400010c3  mov     eax, [rsp+48h+arg_18]
0x1400010c7  mov     eax, [rsp+48h+arg_20]
0x1400010cb  mov     rcx, cs:RegHandle; RegHandle
0x1400010d2  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400010d6  call    cs:__imp_EtwWriteTransfer
0x1400010dd  nop     dword ptr [rax+rax+00h]
0x1400010e2  add     rsp, 48h
0x1400010e6  retn
```
