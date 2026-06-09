# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x1400024fc`
- end: `0x1400025a4`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `168`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, __int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002668`
- `0x140005044`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140002592`
- `ntoskrnl!EtwWriteTransfer` at `0x140002592`

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
0x1400024fc  mov     r11, rsp
0x1400024ff  mov     [r11+20h], r9
0x140002503  sub     rsp, 48h
0x140002507  movzx   eax, byte ptr [rdx]
0x14000250a  xor     r9d, r9d; RelatedActivityId
0x14000250d  mov     r8, [rsp+48h+arg_28]
0x140002512  shl     eax, 18h
0x140002515  mov     [rsp+48h+var_18], eax
0x140002519  movzx   eax, word ptr [rdx+1]
0x14000251d  mov     [rsp+48h+var_14], eax
0x140002521  mov     rax, [rdx+3]
0x140002525  add     rdx, 0Bh
0x140002529  mov     [r11-10h], rax
0x14000252d  mov     rax, cs:EventInformation
0x140002534  mov     [r8], rax
0x140002537  mov     rax, cs:EventInformation
0x14000253e  mov     [r11-20h], r8
0x140002542  movzx   ecx, word ptr [rax]
0x140002545  mov     [r8+8], ecx
0x140002549  lea     rcx, _TraceLoggingMetadata
0x140002550  mov     [r8+10h], rdx
0x140002554  mov     dword ptr [r8+0Ch], 2
0x14000255c  movzx   eax, word ptr [rdx]
0x14000255f  lea     rdx, [r11-18h]; EventDescriptor
0x140002563  mov     [r8+18h], eax
0x140002567  lea     rax, _TraceLoggingMetadataEnd
0x14000256e  sub     eax, ecx
0x140002570  mov     dword ptr [r8+1Ch], 1
0x140002578  mov     [rsp+48h+arg_18], eax
0x14000257c  xor     r8d, r8d; ActivityId
0x14000257f  mov     eax, [rsp+48h+arg_18]
0x140002583  mov     eax, [rsp+48h+arg_20]
0x140002587  mov     rcx, cs:RegHandle; RegHandle
0x14000258e  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140002592  call    cs:__imp_EtwWriteTransfer
0x140002599  nop     dword ptr [rax+rax+00h]
0x14000259e  add     rsp, 48h
0x1400025a2  retn
```
