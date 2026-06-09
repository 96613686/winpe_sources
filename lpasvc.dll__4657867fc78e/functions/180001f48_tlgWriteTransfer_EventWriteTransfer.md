# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001f48`
- end: `0x180001fdf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `103`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010f0`
- `0x1800011fc`
- `0x180001300`
- `0x1800013ec`
- `0x1800014d8`
- `0x1800015d4`
- `0x1800016e4`
- `0x1800017c8`
- `0x1800018b4`
- `0x18000199c`
- `0x180001a94`
- `0x180001c18`
- `0x180001d50`
- `0x180001e44`
- `0x180001fe8`
- `0x180002124`
- `0x180002290`
- `0x1800023b4`
- `0x1800024e8`
- `0x18000262c`
- `0x180002794`
- `0x1800028e0`
- `0x180002a3c`
- `0x180002bdc`
- `0x180002e1c`
- `0x180002ff0`
- `0x1800031fc`
- `0x1800034e0`
- `0x1800035a4`
- `0x1800036bc`
- `0x1800037f4`
- `0x180003908`
- `0x180003a34`
- `0x180003b24`
- `0x180003c3c`
- `0x180003d5c`
- `0x180003e68`
- `0x180003f84`
- `0x1800040c4`
- `0x1800041fc`
- `0x180004324`
- `0x18000440c`
- `0x1800045ac`
- `0x1800046b4`
- `0x180004804`
- `0x180004948`
- `0x180004a7c`
- `0x180004b78`
- `0x180004c84`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001fd4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001fd4`

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
0x180001f48  sub     rsp, 48h
0x180001f4c  movzx   eax, byte ptr [rdx]
0x180001f4f  mov     r11, rcx
0x180001f52  shl     eax, 18h
0x180001f55  mov     r10, r8
0x180001f58  mov     r8, [rsp+48h+arg_28]
0x180001f5d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001f61  movzx   eax, word ptr [rdx+1]
0x180001f65  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001f69  mov     rax, [rdx+3]
0x180001f6d  add     rdx, 0Bh
0x180001f71  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001f76  mov     rax, [rcx+8]
0x180001f7a  mov     [r8], rax
0x180001f7d  mov     rax, [rcx+8]
0x180001f81  mov     [rsp+48h+UserData], r8; UserData
0x180001f86  movzx   ecx, word ptr [rax]
0x180001f89  mov     [r8+8], ecx
0x180001f8d  lea     rcx, _TraceLoggingMetadata
0x180001f94  mov     [r8+10h], rdx
0x180001f98  mov     dword ptr [r8+0Ch], 2
0x180001fa0  movzx   eax, word ptr [rdx]
0x180001fa3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001fa8  mov     [r8+18h], eax
0x180001fac  lea     rax, _TraceLoggingMetadataEnd
0x180001fb3  sub     eax, ecx
0x180001fb5  mov     dword ptr [r8+1Ch], 1
0x180001fbd  mov     dword ptr [rsp+48h+arg_28], eax
0x180001fc1  mov     r8, r10; ActivityId
0x180001fc4  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001fc8  mov     eax, [rsp+48h+arg_20]
0x180001fcc  mov     rcx, [r11+20h]; RegHandle
0x180001fd0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001fd4  call    cs:__imp_EventWriteTransfer
0x180001fda  add     rsp, 48h
0x180001fde  retn
```
