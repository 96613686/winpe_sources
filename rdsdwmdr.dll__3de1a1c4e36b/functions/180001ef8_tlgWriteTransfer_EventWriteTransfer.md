# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001ef8`
- end: `0x180001f8f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010f8`
- `0x180001188`
- `0x180001290`
- `0x180001368`
- `0x180001474`
- `0x180001564`
- `0x18000160c`
- `0x180001724`
- `0x180001868`
- `0x18000192c`
- `0x1800019fc`
- `0x180001b3c`
- `0x180001bfc`
- `0x180001ca4`
- `0x180001f98`
- `0x1800020bc`
- `0x1800021f0`
- `0x1800022b0`
- `0x180002374`
- `0x180002444`
- `0x18000251c`
- `0x180002630`
- `0x180002720`
- `0x180002844`
- `0x180002914`
- `0x180002a04`
- `0x180002b04`
- `0x180002cbc`
- `0x180002dfc`
- `0x180002e4c`
- `0x180002f18`
- `0x180002fc8`
- `0x18000304c`
- `0x180019b70`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001f84`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001f84`

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
0x180001ef8  sub     rsp, 48h
0x180001efc  movzx   eax, byte ptr [rdx]
0x180001eff  mov     r11, rcx
0x180001f02  shl     eax, 18h
0x180001f05  mov     r10, r8
0x180001f08  mov     r8, [rsp+48h+arg_28]
0x180001f0d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001f11  movzx   eax, word ptr [rdx+1]
0x180001f15  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001f19  mov     rax, [rdx+3]
0x180001f1d  add     rdx, 0Bh
0x180001f21  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001f26  mov     rax, [rcx+8]
0x180001f2a  mov     [r8], rax
0x180001f2d  mov     rax, [rcx+8]
0x180001f31  mov     [rsp+48h+UserData], r8; UserData
0x180001f36  movzx   ecx, word ptr [rax]
0x180001f39  mov     [r8+8], ecx
0x180001f3d  lea     rcx, _TraceLoggingMetadata
0x180001f44  mov     [r8+10h], rdx
0x180001f48  mov     dword ptr [r8+0Ch], 2
0x180001f50  movzx   eax, word ptr [rdx]
0x180001f53  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001f58  mov     [r8+18h], eax
0x180001f5c  lea     rax, _TraceLoggingMetadataEnd
0x180001f63  sub     eax, ecx
0x180001f65  mov     dword ptr [r8+1Ch], 1
0x180001f6d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001f71  mov     r8, r10; ActivityId
0x180001f74  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001f78  mov     eax, [rsp+48h+arg_20]
0x180001f7c  mov     rcx, [r11+20h]; RegHandle
0x180001f80  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001f84  call    cs:__imp_EventWriteTransfer
0x180001f8a  add     rsp, 48h
0x180001f8e  retn
```
