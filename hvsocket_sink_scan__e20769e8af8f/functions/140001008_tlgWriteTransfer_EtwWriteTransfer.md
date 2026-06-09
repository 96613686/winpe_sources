# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001008`
- end: `0x1400010aa`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `162`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, __int64)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x1400023b0`
- `0x1400049a0`
- `0x140005280`
- `0x14000975c`
- `0x140009834`
- `0x1400098f4`
- `0x1400099dc`
- `0x140009a94`
- `0x140009b84`
- `0x140009c38`
- `0x140009cf8`
- `0x140009df0`
- `0x140009ec0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000a154`
- `0x14000a234`
- `0x14000a2c8`
- `0x14000b8a0`
- `0x140019110`
- `0x14001b98c`
- `0x14001bd20`
- `0x14001e5ac`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001098`
- `ntoskrnl!EtwWriteTransfer` at `0x140001098`

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
0x140001008  mov     r11, rsp
0x14000100b  mov     [r11+20h], r9
0x14000100f  sub     rsp, 48h
0x140001013  movzx   eax, byte ptr [rdx]
0x140001016  mov     r10, rcx
0x140001019  mov     r8, [rsp+48h+arg_28]
0x14000101e  xor     r9d, r9d; RelatedActivityId
0x140001021  shl     eax, 18h
0x140001024  mov     [rsp+48h+var_18], eax
0x140001028  movzx   eax, word ptr [rdx+1]
0x14000102c  mov     [rsp+48h+var_14], eax
0x140001030  mov     rax, [rdx+3]
0x140001034  add     rdx, 0Bh
0x140001038  mov     [r11-10h], rax
0x14000103c  mov     rax, [rcx+8]
0x140001040  mov     [r8], rax
0x140001043  mov     rax, [rcx+8]
0x140001047  mov     [r11-20h], r8
0x14000104b  movzx   ecx, word ptr [rax]
0x14000104e  mov     [r8+8], ecx
0x140001052  lea     rcx, _TraceLoggingMetadata
0x140001059  mov     [r8+10h], rdx
0x14000105d  mov     dword ptr [r8+0Ch], 2
0x140001065  movzx   eax, word ptr [rdx]
0x140001068  lea     rdx, [r11-18h]; EventDescriptor
0x14000106c  mov     [r8+18h], eax
0x140001070  lea     rax, _TraceLoggingMetadataEnd
0x140001077  sub     eax, ecx
0x140001079  mov     dword ptr [r8+1Ch], 1
0x140001081  mov     [rsp+48h+arg_18], eax
0x140001085  xor     r8d, r8d; ActivityId
0x140001088  mov     eax, [rsp+48h+arg_18]
0x14000108c  mov     eax, [rsp+48h+arg_20]
0x140001090  mov     rcx, [r10+20h]; RegHandle
0x140001094  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001098  call    cs:__imp_EtwWriteTransfer
0x14000109f  nop     dword ptr [rax+rax+00h]
0x1400010a4  add     rsp, 48h
0x1400010a8  retn
```
