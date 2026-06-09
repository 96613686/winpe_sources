# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800146c0`
- end: `0x18001475e`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001038`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18001474c`
- `ADVAPI32!EventWriteTransfer` at `0x18001474c`

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
0x1800146c0  sub     rsp, 48h
0x1800146c4  movzx   eax, byte ptr [rdx]
0x1800146c7  mov     r11, rcx
0x1800146ca  shl     eax, 18h
0x1800146cd  mov     r10, r8
0x1800146d0  mov     r8, [rsp+48h+arg_28]
0x1800146d5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800146d9  movzx   eax, word ptr [rdx+1]
0x1800146dd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800146e1  mov     rax, [rdx+3]
0x1800146e5  add     rdx, 0Bh
0x1800146e9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800146ee  mov     rax, [rcx+8]
0x1800146f2  mov     [r8], rax
0x1800146f5  mov     rax, [rcx+8]
0x1800146f9  mov     [rsp+48h+UserData], r8; UserData
0x1800146fe  movzx   ecx, word ptr [rax]
0x180014701  mov     [r8+8], ecx
0x180014705  lea     rcx, _TraceLoggingMetadata
0x18001470c  mov     [r8+10h], rdx
0x180014710  mov     dword ptr [r8+0Ch], 2
0x180014718  movzx   eax, word ptr [rdx]
0x18001471b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180014720  mov     [r8+18h], eax
0x180014724  lea     rax, _TraceLoggingMetadataEnd
0x18001472b  sub     eax, ecx
0x18001472d  mov     dword ptr [r8+1Ch], 1
0x180014735  mov     dword ptr [rsp+48h+arg_28], eax
0x180014739  mov     r8, r10; ActivityId
0x18001473c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180014740  mov     eax, [rsp+48h+arg_20]
0x180014744  mov     rcx, [r11+20h]; RegHandle
0x180014748  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18001474c  call    cs:__imp_EventWriteTransfer
0x180014753  nop     dword ptr [rax+rax+00h]
0x180014758  add     rsp, 48h
0x18001475c  retn
```
