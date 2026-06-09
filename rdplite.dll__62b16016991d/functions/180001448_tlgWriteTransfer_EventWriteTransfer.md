# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001448`
- end: `0x1800014df`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001178`
- `0x1800014e8`
- `0x180001574`
- `0x1800016a0`
- `0x1800017dc`
- `0x180001a90`
- `0x180001d88`
- `0x180001ecc`
- `0x180001fe4`
- `0x18000208c`
- `0x180002198`
- `0x1800022b0`
- `0x1800023fc`
- `0x180002508`
- `0x18000260c`
- `0x18000275c`
- `0x1800028d4`
- `0x180002a98`
- `0x180002d44`
- `0x180002f68`
- `0x180003080`
- `0x18000b578`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014d4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014d4`

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
0x180001448  sub     rsp, 48h
0x18000144c  movzx   eax, byte ptr [rdx]
0x18000144f  mov     r11, rcx
0x180001452  shl     eax, 18h
0x180001455  mov     r10, r8
0x180001458  mov     r8, [rsp+48h+arg_28]
0x18000145d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001461  movzx   eax, word ptr [rdx+1]
0x180001465  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001469  mov     rax, [rdx+3]
0x18000146d  add     rdx, 0Bh
0x180001471  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001476  mov     rax, [rcx+8]
0x18000147a  mov     [r8], rax
0x18000147d  mov     rax, [rcx+8]
0x180001481  mov     [rsp+48h+UserData], r8; UserData
0x180001486  movzx   ecx, word ptr [rax]
0x180001489  mov     [r8+8], ecx
0x18000148d  lea     rcx, _TraceLoggingMetadata
0x180001494  mov     [r8+10h], rdx
0x180001498  mov     dword ptr [r8+0Ch], 2
0x1800014a0  movzx   eax, word ptr [rdx]
0x1800014a3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800014a8  mov     [r8+18h], eax
0x1800014ac  lea     rax, _TraceLoggingMetadataEnd
0x1800014b3  sub     eax, ecx
0x1800014b5  mov     dword ptr [r8+1Ch], 1
0x1800014bd  mov     dword ptr [rsp+48h+arg_28], eax
0x1800014c1  mov     r8, r10; ActivityId
0x1800014c4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800014c8  mov     eax, [rsp+48h+arg_20]
0x1800014cc  mov     rcx, [r11+20h]; RegHandle
0x1800014d0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800014d4  call    cs:__imp_EventWriteTransfer
0x1800014da  add     rsp, 48h
0x1800014de  retn
```
