# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001070`
- end: `0x140001112`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `162`
- prototype: `NTSTATUS __fastcall(__int64, unsigned __int8 *, __int64, __int64, ULONG UserDataCount, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140001600`
- `0x140012658`
- `0x140012e9c`
- `0x140013510`
- `0x140013a60`
- `0x140013c34`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001100`
- `ntoskrnl!EtwWriteTransfer` at `0x140001100`

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
  a6->Ptr = *(_QWORD *)(a1 + 8);
  a6->Size = **(unsigned __int16 **)(a1 + 8);
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &v9, 0, 0, UserDataCount, a6);
}

```

## disassembly

```asm
0x140001070  mov     r11, rsp
0x140001073  mov     [r11+20h], r9
0x140001077  sub     rsp, 48h
0x14000107b  movzx   eax, byte ptr [rdx]
0x14000107e  mov     r10, rcx
0x140001081  mov     r8, [rsp+48h+arg_28]
0x140001086  xor     r9d, r9d; RelatedActivityId
0x140001089  shl     eax, 18h
0x14000108c  mov     [rsp+48h+var_18], eax
0x140001090  movzx   eax, word ptr [rdx+1]
0x140001094  mov     [rsp+48h+var_14], eax
0x140001098  mov     rax, [rdx+3]
0x14000109c  add     rdx, 0Bh
0x1400010a0  mov     [r11-10h], rax
0x1400010a4  mov     rax, [rcx+8]
0x1400010a8  mov     [r8], rax
0x1400010ab  mov     rax, [rcx+8]
0x1400010af  mov     [r11-20h], r8
0x1400010b3  movzx   ecx, word ptr [rax]
0x1400010b6  mov     [r8+8], ecx
0x1400010ba  lea     rcx, _TraceLoggingMetadata
0x1400010c1  mov     [r8+10h], rdx
0x1400010c5  mov     dword ptr [r8+0Ch], 2
0x1400010cd  movzx   eax, word ptr [rdx]
0x1400010d0  lea     rdx, [r11-18h]; EventDescriptor
0x1400010d4  mov     [r8+18h], eax
0x1400010d8  lea     rax, _TraceLoggingMetadataEnd
0x1400010df  sub     eax, ecx
0x1400010e1  mov     dword ptr [r8+1Ch], 1
0x1400010e9  mov     [rsp+48h+arg_18], eax
0x1400010ed  xor     r8d, r8d; ActivityId
0x1400010f0  mov     eax, [rsp+48h+arg_18]
0x1400010f4  mov     eax, [rsp+48h+arg_20]
0x1400010f8  mov     rcx, [r10+20h]; RegHandle
0x1400010fc  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001100  call    cs:__imp_EtwWriteTransfer
0x140001107  nop     dword ptr [rax+rax+00h]
0x14000110c  add     rsp, 48h
0x140001110  retn
```
