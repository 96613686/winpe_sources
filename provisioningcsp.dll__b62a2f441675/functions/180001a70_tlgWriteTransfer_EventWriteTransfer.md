# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001a70`
- end: `0x180001b0e`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180001150`
- `0x180001404`
- `0x180001494`
- `0x180001738`
- `0x180001b14`
- `0x180001ba8`
- `0x180001c10`
- `0x180001cf0`
- `0x180001d9c`
- `0x18000b330`
- `0x18000c8f4`
- `0x18000ca5c`
- `0x18000cbc4`
- `0x1800118a0`
- `0x180011e80`
- `0x180014f14`
- `0x180023680`
- `0x180031968`
- `0x1800319ec`
- `0x1800322c0`
- `0x180032c84`
- `0x180034150`
- `0x180034630`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001afc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001afc`

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
0x180001a70  sub     rsp, 48h
0x180001a74  movzx   eax, byte ptr [rdx]
0x180001a77  mov     r11, rcx
0x180001a7a  shl     eax, 18h
0x180001a7d  mov     r10, r8
0x180001a80  mov     r8, [rsp+48h+arg_28]
0x180001a85  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001a89  movzx   eax, word ptr [rdx+1]
0x180001a8d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001a91  mov     rax, [rdx+3]
0x180001a95  add     rdx, 0Bh
0x180001a99  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001a9e  mov     rax, [rcx+8]
0x180001aa2  mov     [r8], rax
0x180001aa5  mov     rax, [rcx+8]
0x180001aa9  mov     [rsp+48h+UserData], r8; UserData
0x180001aae  movzx   ecx, word ptr [rax]
0x180001ab1  mov     [r8+8], ecx
0x180001ab5  lea     rcx, _TraceLoggingMetadata
0x180001abc  mov     [r8+10h], rdx
0x180001ac0  mov     dword ptr [r8+0Ch], 2
0x180001ac8  movzx   eax, word ptr [rdx]
0x180001acb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001ad0  mov     [r8+18h], eax
0x180001ad4  lea     rax, _TraceLoggingMetadataEnd
0x180001adb  sub     eax, ecx
0x180001add  mov     dword ptr [r8+1Ch], 1
0x180001ae5  mov     dword ptr [rsp+48h+arg_28], eax
0x180001ae9  mov     r8, r10; ActivityId
0x180001aec  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001af0  mov     eax, [rsp+48h+arg_20]
0x180001af4  mov     rcx, [r11+20h]; RegHandle
0x180001af8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001afc  call    cs:__imp_EventWriteTransfer
0x180001b03  nop     dword ptr [rax+rax+00h]
0x180001b08  add     rsp, 48h
0x180001b0c  retn
```
