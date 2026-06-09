# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001008`
- end: `0x1800010a9`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `161`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, __int64)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180007c10`
- `0x180007de0`
- `0x180007f00`
- `0x180008010`
- `0x18000814c`
- `0x180008240`
- `0x180008410`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000109e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000109e`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
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
  a6->Ptr = (ULONGLONG)off_180012008;
  a6->Size = *(unsigned __int16 *)off_180012008;
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EventWriteTransfer(RegHandle, &v9, 0, 0, UserDataCount, a6);
}

```

## disassembly

```asm
0x180001008  mov     r11, rsp
0x18000100b  mov     [r11+20h], r9
0x18000100f  sub     rsp, 48h
0x180001013  movzx   eax, byte ptr [rdx]
0x180001016  xor     r9d, r9d; RelatedActivityId
0x180001019  mov     r8, [rsp+48h+arg_28]
0x18000101e  shl     eax, 18h
0x180001021  mov     [rsp+48h+var_18], eax
0x180001025  movzx   eax, word ptr [rdx+1]
0x180001029  mov     [rsp+48h+var_14], eax
0x18000102d  mov     rax, [rdx+3]
0x180001031  add     rdx, 0Bh
0x180001035  mov     [r11-10h], rax
0x180001039  mov     rax, cs:off_180012008
0x180001040  mov     [r8], rax
0x180001043  mov     rax, cs:off_180012008
0x18000104a  mov     [r11-20h], r8
0x18000104e  movzx   ecx, word ptr [rax]
0x180001051  mov     [r8+8], ecx
0x180001055  lea     rcx, _TraceLoggingMetadata
0x18000105c  mov     [r8+10h], rdx
0x180001060  mov     dword ptr [r8+0Ch], 2
0x180001068  movzx   eax, word ptr [rdx]
0x18000106b  lea     rdx, [r11-18h]; EventDescriptor
0x18000106f  mov     [r8+18h], eax
0x180001073  lea     rax, _TraceLoggingMetadataEnd
0x18000107a  sub     eax, ecx
0x18000107c  mov     dword ptr [r8+1Ch], 1
0x180001084  mov     [rsp+48h+arg_18], eax
0x180001088  xor     r8d, r8d; ActivityId
0x18000108b  mov     eax, [rsp+48h+arg_18]
0x18000108f  mov     eax, [rsp+48h+arg_20]
0x180001093  mov     rcx, cs:RegHandle; RegHandle
0x18000109a  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000109e  call    cs:__imp_EventWriteTransfer
0x1800010a4  add     rsp, 48h
0x1800010a8  retn
```
