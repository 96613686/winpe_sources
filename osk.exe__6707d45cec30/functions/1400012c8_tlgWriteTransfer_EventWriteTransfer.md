# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400012c8`
- end: `0x14000135f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010c0`
- `0x140001368`
- `0x140001640`
- `0x140001714`
- `0x1400017d8`
- `0x140001a8c`
- `0x14002219c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x140001354`
- `ADVAPI32!EventWriteTransfer` at `0x140001354`

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
0x1400012c8  sub     rsp, 48h
0x1400012cc  movzx   eax, byte ptr [rdx]
0x1400012cf  mov     r11, rcx
0x1400012d2  shl     eax, 18h
0x1400012d5  mov     r10, r8
0x1400012d8  mov     r8, [rsp+48h+arg_28]
0x1400012dd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400012e1  movzx   eax, word ptr [rdx+1]
0x1400012e5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400012e9  mov     rax, [rdx+3]
0x1400012ed  add     rdx, 0Bh
0x1400012f1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400012f6  mov     rax, [rcx+8]
0x1400012fa  mov     [r8], rax
0x1400012fd  mov     rax, [rcx+8]
0x140001301  mov     [rsp+48h+UserData], r8; UserData
0x140001306  movzx   ecx, word ptr [rax]
0x140001309  mov     [r8+8], ecx
0x14000130d  lea     rcx, _TraceLoggingMetadata
0x140001314  mov     [r8+10h], rdx
0x140001318  mov     dword ptr [r8+0Ch], 2
0x140001320  movzx   eax, word ptr [rdx]
0x140001323  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001328  mov     [r8+18h], eax
0x14000132c  lea     rax, _TraceLoggingMetadataEnd
0x140001333  sub     eax, ecx
0x140001335  mov     dword ptr [r8+1Ch], 1
0x14000133d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001341  mov     r8, r10; ActivityId
0x140001344  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001348  mov     eax, [rsp+48h+arg_20]
0x14000134c  mov     rcx, [r11+20h]; RegHandle
0x140001350  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001354  call    cs:__imp_EventWriteTransfer
0x14000135a  add     rsp, 48h
0x14000135e  retn
```
