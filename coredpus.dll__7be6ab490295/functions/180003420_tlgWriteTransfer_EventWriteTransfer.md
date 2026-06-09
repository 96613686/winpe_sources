# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180003420`
- end: `0x1800034be`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001190`
- `0x1800011d4`
- `0x1800012b0`
- `0x180001390`
- `0x180001488`
- `0x180001584`
- `0x18000169c`
- `0x1800017e8`
- `0x180001878`
- `0x180001950`
- `0x180001a44`
- `0x180001ae0`
- `0x180001bd0`
- `0x180001c78`
- `0x180029240`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800034ac`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800034ac`

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
0x180003420  sub     rsp, 48h
0x180003424  movzx   eax, byte ptr [rdx]
0x180003427  mov     r11, rcx
0x18000342a  shl     eax, 18h
0x18000342d  mov     r10, r8
0x180003430  mov     r8, [rsp+48h+arg_28]
0x180003435  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180003439  movzx   eax, word ptr [rdx+1]
0x18000343d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180003441  mov     rax, [rdx+3]
0x180003445  add     rdx, 0Bh
0x180003449  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000344e  mov     rax, [rcx+8]
0x180003452  mov     [r8], rax
0x180003455  mov     rax, [rcx+8]
0x180003459  mov     [rsp+48h+UserData], r8; UserData
0x18000345e  movzx   ecx, word ptr [rax]
0x180003461  mov     [r8+8], ecx
0x180003465  lea     rcx, _TraceLoggingMetadata
0x18000346c  mov     [r8+10h], rdx
0x180003470  mov     dword ptr [r8+0Ch], 2
0x180003478  movzx   eax, word ptr [rdx]
0x18000347b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180003480  mov     [r8+18h], eax
0x180003484  lea     rax, _TraceLoggingMetadataEnd
0x18000348b  sub     eax, ecx
0x18000348d  mov     dword ptr [r8+1Ch], 1
0x180003495  mov     dword ptr [rsp+48h+arg_28], eax
0x180003499  mov     r8, r10; ActivityId
0x18000349c  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800034a0  mov     eax, [rsp+48h+arg_20]
0x1800034a4  mov     rcx, [r11+20h]; RegHandle
0x1800034a8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800034ac  call    cs:__imp_EventWriteTransfer
0x1800034b3  nop     dword ptr [rax+rax+00h]
0x1800034b8  add     rsp, 48h
0x1800034bc  retn
```
