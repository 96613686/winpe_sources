# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800148a0`
- end: `0x180014937`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x18001472c`
- `0x180014940`
- `0x180014990`
- `0x180014a38`
- `0x180014a9c`
- `0x180014b14`
- `0x180014bac`
- `0x180014c80`
- `0x180014d2c`
- `0x180014eec`
- `0x180014f4c`
- `0x180014fc4`
- `0x180015058`
- `0x1800150fc`
- `0x1800151b0`
- `0x18001fcb0`
- `0x180020fe0`
- `0x18003f408`
- `0x180040290`
- `0x180041ad0`
- `0x180041cc0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001492c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001492c`

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
0x1800148a0  sub     rsp, 48h
0x1800148a4  movzx   eax, byte ptr [rdx]
0x1800148a7  mov     r11, rcx
0x1800148aa  shl     eax, 18h
0x1800148ad  mov     r10, r8
0x1800148b0  mov     r8, [rsp+48h+arg_28]
0x1800148b5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800148b9  movzx   eax, word ptr [rdx+1]
0x1800148bd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800148c1  mov     rax, [rdx+3]
0x1800148c5  add     rdx, 0Bh
0x1800148c9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800148ce  mov     rax, [rcx+8]
0x1800148d2  mov     [r8], rax
0x1800148d5  mov     rax, [rcx+8]
0x1800148d9  mov     [rsp+48h+UserData], r8; UserData
0x1800148de  movzx   ecx, word ptr [rax]
0x1800148e1  mov     [r8+8], ecx
0x1800148e5  lea     rcx, _TraceLoggingMetadata
0x1800148ec  mov     [r8+10h], rdx
0x1800148f0  mov     dword ptr [r8+0Ch], 2
0x1800148f8  movzx   eax, word ptr [rdx]
0x1800148fb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180014900  mov     [r8+18h], eax
0x180014904  lea     rax, _TraceLoggingMetadataEnd
0x18001490b  sub     eax, ecx
0x18001490d  mov     dword ptr [r8+1Ch], 1
0x180014915  mov     dword ptr [rsp+48h+arg_28], eax
0x180014919  mov     r8, r10; ActivityId
0x18001491c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180014920  mov     eax, [rsp+48h+arg_20]
0x180014924  mov     rcx, [r11+20h]; RegHandle
0x180014928  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18001492c  call    cs:__imp_EventWriteTransfer
0x180014932  add     rsp, 48h
0x180014936  retn
```
