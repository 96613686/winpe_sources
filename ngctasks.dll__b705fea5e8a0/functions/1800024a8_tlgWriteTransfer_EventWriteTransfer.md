# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800024a8`
- end: `0x18000253f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800012cc`
- `0x180001310`
- `0x1800013bc`
- `0x1800016a8`
- `0x1800019bc`
- `0x180001a4c`
- `0x180001b0c`
- `0x180001bec`
- `0x180001e90`
- `0x180002188`
- `0x18000224c`
- `0x180002548`
- `0x180002a08`
- `0x180002e70`
- `0x180002ec8`
- `0x1800180d4`
- `0x18001c324`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002534`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002534`

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
0x1800024a8  sub     rsp, 48h
0x1800024ac  movzx   eax, byte ptr [rdx]
0x1800024af  mov     r11, rcx
0x1800024b2  shl     eax, 18h
0x1800024b5  mov     r10, r8
0x1800024b8  mov     r8, [rsp+48h+arg_28]
0x1800024bd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800024c1  movzx   eax, word ptr [rdx+1]
0x1800024c5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800024c9  mov     rax, [rdx+3]
0x1800024cd  add     rdx, 0Bh
0x1800024d1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800024d6  mov     rax, [rcx+8]
0x1800024da  mov     [r8], rax
0x1800024dd  mov     rax, [rcx+8]
0x1800024e1  mov     [rsp+48h+UserData], r8; UserData
0x1800024e6  movzx   ecx, word ptr [rax]
0x1800024e9  mov     [r8+8], ecx
0x1800024ed  lea     rcx, _TraceLoggingMetadata
0x1800024f4  mov     [r8+10h], rdx
0x1800024f8  mov     dword ptr [r8+0Ch], 2
0x180002500  movzx   eax, word ptr [rdx]
0x180002503  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180002508  mov     [r8+18h], eax
0x18000250c  lea     rax, _TraceLoggingMetadataEnd
0x180002513  sub     eax, ecx
0x180002515  mov     dword ptr [r8+1Ch], 1
0x18000251d  mov     dword ptr [rsp+48h+arg_28], eax
0x180002521  mov     r8, r10; ActivityId
0x180002524  mov     eax, dword ptr [rsp+48h+arg_28]
0x180002528  mov     eax, [rsp+48h+arg_20]
0x18000252c  mov     rcx, [r11+20h]; RegHandle
0x180002530  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180002534  call    cs:__imp_EventWriteTransfer
0x18000253a  add     rsp, 48h
0x18000253e  retn
```
