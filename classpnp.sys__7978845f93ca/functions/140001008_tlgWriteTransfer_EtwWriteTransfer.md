# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001008`
- end: `0x1400010b0`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `168`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, __int64)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x14001c9e0`
- `0x14001e86c`
- `0x14001f154`
- `0x140025340`
- `0x1400259cc`
- `0x14002b8b0`
- `0x14002ba00`
- `0x14002d800`
- `0x14002fdd8`
- `0x140035ce4`
- `0x1400360d4`
- `0x14003dbfc`
- `0x14003df08`
- `0x140056294`
- `0x140056664`
- `0x140056a40`
- `0x1400579b4`
- `0x140058d20`
- `0x14005923c`
- `0x14005fe50`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000109e`
- `ntoskrnl!EtwWriteTransfer` at `0x14000109e`

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
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR v9; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&v9.Id = *a2 << 24;
  *(_DWORD *)&v9.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  v9.Keyword = v6;
  a6->Ptr = (unsigned __int64)EventInformation;
  a6->Size = *(unsigned __int16 *)EventInformation;
  a6[1].Ptr = (unsigned __int64)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EtwWriteTransfer(RegHandle, &v9, 0, 0, UserDataCount, a6);
}

```

## disassembly

```asm
0x140001008  mov     r11, rsp
0x14000100b  mov     [r11+20h], r9
0x14000100f  sub     rsp, 48h
0x140001013  movzx   eax, byte ptr [rdx]
0x140001016  xor     r9d, r9d; RelatedActivityId
0x140001019  mov     r8, [rsp+48h+arg_28]
0x14000101e  shl     eax, 18h
0x140001021  mov     [rsp+48h+var_18], eax
0x140001025  movzx   eax, word ptr [rdx+1]
0x140001029  mov     [rsp+48h+var_14], eax
0x14000102d  mov     rax, [rdx+3]
0x140001031  add     rdx, 0Bh
0x140001035  mov     [r11-10h], rax
0x140001039  mov     rax, cs:EventInformation
0x140001040  mov     [r8], rax
0x140001043  mov     rax, cs:EventInformation
0x14000104a  mov     [r11-20h], r8
0x14000104e  movzx   ecx, word ptr [rax]
0x140001051  mov     [r8+8], ecx
0x140001055  lea     rcx, _TraceLoggingMetadata
0x14000105c  mov     [r8+10h], rdx
0x140001060  mov     dword ptr [r8+0Ch], 2
0x140001068  movzx   eax, word ptr [rdx]
0x14000106b  lea     rdx, [r11-18h]; EventDescriptor
0x14000106f  mov     [r8+18h], eax
0x140001073  lea     rax, _TraceLoggingMetadataEnd
0x14000107a  sub     eax, ecx
0x14000107c  mov     dword ptr [r8+1Ch], 1
0x140001084  mov     [rsp+48h+arg_18], eax
0x140001088  xor     r8d, r8d; ActivityId
0x14000108b  mov     eax, [rsp+48h+arg_18]
0x14000108f  mov     eax, [rsp+48h+arg_20]
0x140001093  mov     rcx, cs:RegHandle; RegHandle
0x14000109a  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x14000109e  call    cs:__imp_EtwWriteTransfer
0x1400010a5  nop     dword ptr [rax+rax+00h]
0x1400010aa  add     rsp, 48h
0x1400010ae  retn
```
