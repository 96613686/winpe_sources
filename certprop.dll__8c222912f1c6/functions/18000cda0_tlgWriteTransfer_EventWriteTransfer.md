# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000cda0`
- end: `0x18000ce42`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `162`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b09c`
- `0x1800180f4`
- `0x1800185d8`
- `0x18001e4bc`
- `0x18001e910`
- `0x1800205c4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ce37`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ce37`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
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
  UserData->Ptr = (ULONGLONG)off_180031010;
  UserData->Size = *(unsigned __int16 *)off_180031010;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000cda0  mov     [rsp+arg_0], rcx
0x18000cda5  sub     rsp, 48h
0x18000cda9  movzx   eax, byte ptr [rdx]
0x18000cdac  mov     r10, r9
0x18000cdaf  mov     r9, [rsp+48h+arg_28]
0x18000cdb4  shl     eax, 18h
0x18000cdb7  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000cdbb  movzx   eax, word ptr [rdx+1]
0x18000cdbf  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000cdc3  mov     rax, [rdx+3]
0x18000cdc7  add     rdx, 0Bh
0x18000cdcb  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000cdd0  mov     rax, cs:off_180031010
0x18000cdd7  mov     [r9], rax
0x18000cdda  mov     rax, cs:off_180031010
0x18000cde1  mov     [rsp+48h+UserData], r9; UserData
0x18000cde6  movzx   ecx, word ptr [rax]
0x18000cde9  mov     [r9+8], ecx
0x18000cded  lea     rcx, _TraceLoggingMetadata
0x18000cdf4  mov     [r9+10h], rdx
0x18000cdf8  mov     dword ptr [r9+0Ch], 2
0x18000ce00  movzx   eax, word ptr [rdx]
0x18000ce03  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000ce08  mov     [r9+18h], eax
0x18000ce0c  lea     rax, _TraceLoggingMetadataEnd
0x18000ce13  sub     eax, ecx
0x18000ce15  mov     dword ptr [r9+1Ch], 1
0x18000ce1d  mov     dword ptr [rsp+48h+arg_0], eax
0x18000ce21  mov     r9, r10; RelatedActivityId
0x18000ce24  mov     eax, dword ptr [rsp+48h+arg_0]
0x18000ce28  mov     eax, [rsp+48h+arg_20]
0x18000ce2c  mov     rcx, cs:RegHandle; RegHandle
0x18000ce33  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000ce37  call    cs:__imp_EventWriteTransfer
0x18000ce3d  add     rsp, 48h
0x18000ce41  retn
```
