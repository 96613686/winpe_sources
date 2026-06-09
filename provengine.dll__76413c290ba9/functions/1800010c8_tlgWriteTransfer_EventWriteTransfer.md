# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800010c8`
- end: `0x18000115f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `70`
- callee_count: `0`
- tags: ``

## callers

- `0x180001168`
- `0x1800011ac`
- `0x180001238`
- `0x180001300`
- `0x180001358`
- `0x1800015a0`
- `0x1800017f4`
- `0x1800018ec`
- `0x180001994`
- `0x180001a14`
- `0x180001af4`
- `0x180004070`
- `0x180007cc0`
- `0x180008900`
- `0x180008a84`
- `0x18000915c`
- `0x180009348`
- `0x1800097d0`
- `0x180009924`
- `0x18000a4e4`
- `0x18000a7f4`
- `0x18000f230`
- `0x18000f288`
- `0x180011920`
- `0x1800119b8`
- `0x180011ae4`
- `0x180011bb0`
- `0x180011c68`
- `0x18001240c`
- `0x1800141f0`
- `0x180014810`
- `0x180014cf8`
- `0x180015740`
- `0x1800162f0`
- `0x1800165e0`
- `0x180016cc8`
- `0x180016f5c`
- `0x1800172e8`
- `0x18001772c`
- `0x180018068`
- `0x180018438`
- `0x180018e20`
- `0x18001a6fc`
- `0x18001b700`
- `0x18001d028`
- `0x18001d25c`
- `0x18001d924`
- `0x18001def0`
- `0x18001eeec`
- `0x18001f95c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001154`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001154`

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
0x1800010c8  sub     rsp, 48h
0x1800010cc  movzx   eax, byte ptr [rdx]
0x1800010cf  mov     r11, rcx
0x1800010d2  shl     eax, 18h
0x1800010d5  mov     r10, r8
0x1800010d8  mov     r8, [rsp+48h+arg_28]
0x1800010dd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800010e1  movzx   eax, word ptr [rdx+1]
0x1800010e5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800010e9  mov     rax, [rdx+3]
0x1800010ed  add     rdx, 0Bh
0x1800010f1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800010f6  mov     rax, [rcx+8]
0x1800010fa  mov     [r8], rax
0x1800010fd  mov     rax, [rcx+8]
0x180001101  mov     [rsp+48h+UserData], r8; UserData
0x180001106  movzx   ecx, word ptr [rax]
0x180001109  mov     [r8+8], ecx
0x18000110d  lea     rcx, _TraceLoggingMetadata
0x180001114  mov     [r8+10h], rdx
0x180001118  mov     dword ptr [r8+0Ch], 2
0x180001120  movzx   eax, word ptr [rdx]
0x180001123  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001128  mov     [r8+18h], eax
0x18000112c  lea     rax, _TraceLoggingMetadataEnd
0x180001133  sub     eax, ecx
0x180001135  mov     dword ptr [r8+1Ch], 1
0x18000113d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001141  mov     r8, r10; ActivityId
0x180001144  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001148  mov     eax, [rsp+48h+arg_20]
0x18000114c  mov     rcx, [r11+20h]; RegHandle
0x180001150  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001154  call    cs:__imp_EventWriteTransfer
0x18000115a  add     rsp, 48h
0x18000115e  retn
```
