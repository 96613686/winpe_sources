# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140009bc0`
- end: `0x140009c57`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400012bc`
- `0x1400015b4`
- `0x14000188c`
- `0x140001b48`
- `0x140001e44`
- `0x140002124`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140009c4c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140009c4c`

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
0x140009bc0  sub     rsp, 48h
0x140009bc4  movzx   eax, byte ptr [rdx]
0x140009bc7  mov     r11, rcx
0x140009bca  shl     eax, 18h
0x140009bcd  mov     r10, r8
0x140009bd0  mov     r8, [rsp+48h+arg_28]
0x140009bd5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140009bd9  movzx   eax, word ptr [rdx+1]
0x140009bdd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140009be1  mov     rax, [rdx+3]
0x140009be5  add     rdx, 0Bh
0x140009be9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140009bee  mov     rax, [rcx+8]
0x140009bf2  mov     [r8], rax
0x140009bf5  mov     rax, [rcx+8]
0x140009bf9  mov     [rsp+48h+UserData], r8; UserData
0x140009bfe  movzx   ecx, word ptr [rax]
0x140009c01  mov     [r8+8], ecx
0x140009c05  lea     rcx, _TraceLoggingMetadata
0x140009c0c  mov     [r8+10h], rdx
0x140009c10  mov     dword ptr [r8+0Ch], 2
0x140009c18  movzx   eax, word ptr [rdx]
0x140009c1b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140009c20  mov     [r8+18h], eax
0x140009c24  lea     rax, _TraceLoggingMetadataEnd
0x140009c2b  sub     eax, ecx
0x140009c2d  mov     dword ptr [r8+1Ch], 1
0x140009c35  mov     dword ptr [rsp+48h+arg_28], eax
0x140009c39  mov     r8, r10; ActivityId
0x140009c3c  mov     eax, dword ptr [rsp+48h+arg_28]
0x140009c40  mov     eax, [rsp+48h+arg_20]
0x140009c44  mov     rcx, [r11+20h]; RegHandle
0x140009c48  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140009c4c  call    cs:__imp_EventWriteTransfer
0x140009c52  add     rsp, 48h
0x140009c56  retn
```
