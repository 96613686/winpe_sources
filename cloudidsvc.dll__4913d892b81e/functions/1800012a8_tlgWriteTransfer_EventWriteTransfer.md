# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800012a8`
- end: `0x18000133f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001348`
- `0x18000ba60`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001334`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001334`

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
0x1800012a8  sub     rsp, 48h
0x1800012ac  movzx   eax, byte ptr [rdx]
0x1800012af  mov     r11, rcx
0x1800012b2  shl     eax, 18h
0x1800012b5  mov     r10, r8
0x1800012b8  mov     r8, [rsp+48h+arg_28]
0x1800012bd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800012c1  movzx   eax, word ptr [rdx+1]
0x1800012c5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800012c9  mov     rax, [rdx+3]
0x1800012cd  add     rdx, 0Bh
0x1800012d1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800012d6  mov     rax, [rcx+8]
0x1800012da  mov     [r8], rax
0x1800012dd  mov     rax, [rcx+8]
0x1800012e1  mov     [rsp+48h+UserData], r8; UserData
0x1800012e6  movzx   ecx, word ptr [rax]
0x1800012e9  mov     [r8+8], ecx
0x1800012ed  lea     rcx, _TraceLoggingMetadata
0x1800012f4  mov     [r8+10h], rdx
0x1800012f8  mov     dword ptr [r8+0Ch], 2
0x180001300  movzx   eax, word ptr [rdx]
0x180001303  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001308  mov     [r8+18h], eax
0x18000130c  lea     rax, _TraceLoggingMetadataEnd
0x180001313  sub     eax, ecx
0x180001315  mov     dword ptr [r8+1Ch], 1
0x18000131d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001321  mov     r8, r10; ActivityId
0x180001324  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001328  mov     eax, [rsp+48h+arg_20]
0x18000132c  mov     rcx, [r11+20h]; RegHandle
0x180001330  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001334  call    cs:__imp_EventWriteTransfer
0x18000133a  add     rsp, 48h
0x18000133e  retn
```
