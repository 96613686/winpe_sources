# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001008`
- end: `0x1800010ac`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `164`
- prototype: `__int64 __fastcall(int, int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800253fc`
- `0x180025490`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000109a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000109a`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
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
  UserData->Ptr = (ULONGLONG)off_180063198;
  UserData->Size = *(unsigned __int16 *)off_180063198;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, UserData);
}

```

## disassembly

```asm
0x180001008  sub     rsp, 48h
0x18000100c  movzx   eax, byte ptr [rdx]
0x18000100f  xor     r9d, r9d; RelatedActivityId
0x180001012  mov     r8, [rsp+48h+arg_28]
0x180001017  shl     eax, 18h
0x18000101a  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000101e  movzx   eax, word ptr [rdx+1]
0x180001022  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001026  mov     rax, [rdx+3]
0x18000102a  add     rdx, 0Bh
0x18000102e  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001033  mov     rax, cs:off_180063198
0x18000103a  mov     [r8], rax
0x18000103d  mov     rax, cs:off_180063198
0x180001044  mov     [rsp+48h+UserData], r8; UserData
0x180001049  mov     [rsp+48h+UserDataCount], 4; UserDataCount
0x180001051  movzx   ecx, word ptr [rax]
0x180001054  mov     [r8+8], ecx
0x180001058  lea     rcx, _TraceLoggingMetadata
0x18000105f  mov     [r8+10h], rdx
0x180001063  mov     dword ptr [r8+0Ch], 2
0x18000106b  movzx   eax, word ptr [rdx]
0x18000106e  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001073  mov     [r8+18h], eax
0x180001077  lea     rax, _TraceLoggingMetadataEnd
0x18000107e  sub     eax, ecx
0x180001080  mov     dword ptr [r8+1Ch], 1
0x180001088  mov     [rsp+48h+arg_20], eax
0x18000108c  xor     r8d, r8d; ActivityId
0x18000108f  mov     eax, [rsp+48h+arg_20]
0x180001093  mov     rcx, cs:RegHandle; RegHandle
0x18000109a  call    cs:__imp_EventWriteTransfer
0x1800010a1  nop     dword ptr [rax+rax+00h]
0x1800010a6  add     rsp, 48h
0x1800010aa  retn
```
