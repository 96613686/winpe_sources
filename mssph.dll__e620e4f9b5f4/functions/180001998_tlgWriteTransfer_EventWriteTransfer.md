# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001998`
- end: `0x180001a2f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015b4`
- `0x180001a38`
- `0x180001b30`
- `0x180001bdc`
- `0x180001eb4`
- `0x180001f88`
- `0x180002154`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a24`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a24`

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
0x180001998  sub     rsp, 48h
0x18000199c  movzx   eax, byte ptr [rdx]
0x18000199f  mov     r11, rcx
0x1800019a2  shl     eax, 18h
0x1800019a5  mov     r10, r8
0x1800019a8  mov     r8, [rsp+48h+arg_28]
0x1800019ad  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800019b1  movzx   eax, word ptr [rdx+1]
0x1800019b5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800019b9  mov     rax, [rdx+3]
0x1800019bd  add     rdx, 0Bh
0x1800019c1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800019c6  mov     rax, [rcx+8]
0x1800019ca  mov     [r8], rax
0x1800019cd  mov     rax, [rcx+8]
0x1800019d1  mov     [rsp+48h+UserData], r8; UserData
0x1800019d6  movzx   ecx, word ptr [rax]
0x1800019d9  mov     [r8+8], ecx
0x1800019dd  lea     rcx, _TraceLoggingMetadata
0x1800019e4  mov     [r8+10h], rdx
0x1800019e8  mov     dword ptr [r8+0Ch], 2
0x1800019f0  movzx   eax, word ptr [rdx]
0x1800019f3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800019f8  mov     [r8+18h], eax
0x1800019fc  lea     rax, _TraceLoggingMetadataEnd
0x180001a03  sub     eax, ecx
0x180001a05  mov     dword ptr [r8+1Ch], 1
0x180001a0d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001a11  mov     r8, r10; ActivityId
0x180001a14  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001a18  mov     eax, [rsp+48h+arg_20]
0x180001a1c  mov     rcx, [r11+20h]; RegHandle
0x180001a20  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001a24  call    cs:__imp_EventWriteTransfer
0x180001a2a  add     rsp, 48h
0x180001a2e  retn
```
