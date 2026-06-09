# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000129c`
- end: `0x180001333`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001178`
- `0x18000133c`
- `0x1800014e4`
- `0x180024090`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001328`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001328`

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
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000129c  sub     rsp, 48h
0x1800012a0  movzx   eax, byte ptr [rdx]
0x1800012a3  mov     r11, rcx
0x1800012a6  shl     eax, 18h
0x1800012a9  mov     r10, r8
0x1800012ac  mov     r8, [rsp+48h+arg_28]
0x1800012b1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800012b5  movzx   eax, word ptr [rdx+1]
0x1800012b9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800012bd  mov     rax, [rdx+3]
0x1800012c1  add     rdx, 0Bh
0x1800012c5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800012ca  mov     rax, [rcx+8]
0x1800012ce  mov     [r8], rax
0x1800012d1  mov     rax, [rcx+8]
0x1800012d5  mov     [rsp+48h+UserData], r8; UserData
0x1800012da  movzx   ecx, word ptr [rax]
0x1800012dd  mov     [r8+8], ecx
0x1800012e1  lea     rcx, _TraceLoggingMetadata
0x1800012e8  mov     [r8+10h], rdx
0x1800012ec  mov     dword ptr [r8+0Ch], 2
0x1800012f4  movzx   eax, word ptr [rdx]
0x1800012f7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800012fc  mov     [r8+18h], eax
0x180001300  lea     rax, _TraceLoggingMetadataEnd
0x180001307  sub     eax, ecx
0x180001309  mov     dword ptr [r8+1Ch], 1
0x180001311  mov     dword ptr [rsp+48h+arg_28], eax
0x180001315  mov     r8, r10; ActivityId
0x180001318  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000131c  mov     eax, [rsp+48h+arg_20]
0x180001320  mov     rcx, [r11+20h]; RegHandle
0x180001324  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001328  call    cs:__imp_EventWriteTransfer
0x18000132e  add     rsp, 48h
0x180001332  retn
```
