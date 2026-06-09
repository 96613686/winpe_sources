# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x14000107c`
- end: `0x140001124`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `168`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000f290`
- `0x14000f3f0`
- `0x14000f9b8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001112`
- `ntoskrnl!EtwWriteTransfer` at `0x140001112`

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
0x14000107c  mov     r11, rsp
0x14000107f  mov     [r11+20h], r9
0x140001083  sub     rsp, 48h
0x140001087  movzx   eax, byte ptr [rdx]
0x14000108a  xor     r9d, r9d; RelatedActivityId
0x14000108d  mov     r8, [rsp+48h+arg_28]
0x140001092  shl     eax, 18h
0x140001095  mov     [rsp+48h+var_18], eax
0x140001099  movzx   eax, word ptr [rdx+1]
0x14000109d  mov     [rsp+48h+var_14], eax
0x1400010a1  mov     rax, [rdx+3]
0x1400010a5  add     rdx, 0Bh
0x1400010a9  mov     [r11-10h], rax
0x1400010ad  mov     rax, cs:EventInformation
0x1400010b4  mov     [r8], rax
0x1400010b7  mov     rax, cs:EventInformation
0x1400010be  mov     [r11-20h], r8
0x1400010c2  movzx   ecx, word ptr [rax]
0x1400010c5  mov     [r8+8], ecx
0x1400010c9  lea     rcx, _TraceLoggingMetadata
0x1400010d0  mov     [r8+10h], rdx
0x1400010d4  mov     dword ptr [r8+0Ch], 2
0x1400010dc  movzx   eax, word ptr [rdx]
0x1400010df  lea     rdx, [r11-18h]; EventDescriptor
0x1400010e3  mov     [r8+18h], eax
0x1400010e7  lea     rax, _TraceLoggingMetadataEnd
0x1400010ee  sub     eax, ecx
0x1400010f0  mov     dword ptr [r8+1Ch], 1
0x1400010f8  mov     [rsp+48h+arg_18], eax
0x1400010fc  xor     r8d, r8d; ActivityId
0x1400010ff  mov     eax, [rsp+48h+arg_18]
0x140001103  mov     eax, [rsp+48h+arg_20]
0x140001107  mov     rcx, cs:RegHandle; RegHandle
0x14000110e  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001112  call    cs:__imp_EtwWriteTransfer
0x140001119  nop     dword ptr [rax+rax+00h]
0x14000111e  add     rsp, 48h
0x140001122  retn
```
