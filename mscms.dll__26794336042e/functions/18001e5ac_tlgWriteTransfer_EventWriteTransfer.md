# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18001e5ac`
- end: `0x18001e643`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001164`
- `0x180001298`
- `0x1800016bc`
- `0x180001750`
- `0x180001818`
- `0x1800018dc`
- `0x18000193c`
- `0x180001a08`
- `0x180001dc4`
- `0x1800022a0`
- `0x18000242c`
- `0x180002500`
- `0x180002658`
- `0x18000271c`
- `0x1800027b0`
- `0x180002874`
- `0x1800028d8`
- `0x180002984`
- `0x180002a48`
- `0x180002b10`
- `0x180002bcc`
- `0x180044ab0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e638`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e638`

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
0x18001e5ac  sub     rsp, 48h
0x18001e5b0  movzx   eax, byte ptr [rdx]
0x18001e5b3  mov     r11, rcx
0x18001e5b6  shl     eax, 18h
0x18001e5b9  mov     r10, r8
0x18001e5bc  mov     r8, [rsp+48h+arg_28]
0x18001e5c1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18001e5c5  movzx   eax, word ptr [rdx+1]
0x18001e5c9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18001e5cd  mov     rax, [rdx+3]
0x18001e5d1  add     rdx, 0Bh
0x18001e5d5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18001e5da  mov     rax, [rcx+8]
0x18001e5de  mov     [r8], rax
0x18001e5e1  mov     rax, [rcx+8]
0x18001e5e5  mov     [rsp+48h+UserData], r8; UserData
0x18001e5ea  movzx   ecx, word ptr [rax]
0x18001e5ed  mov     [r8+8], ecx
0x18001e5f1  lea     rcx, _TraceLoggingMetadata
0x18001e5f8  mov     [r8+10h], rdx
0x18001e5fc  mov     dword ptr [r8+0Ch], 2
0x18001e604  movzx   eax, word ptr [rdx]
0x18001e607  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18001e60c  mov     [r8+18h], eax
0x18001e610  lea     rax, _TraceLoggingMetadataEnd
0x18001e617  sub     eax, ecx
0x18001e619  mov     dword ptr [r8+1Ch], 1
0x18001e621  mov     dword ptr [rsp+48h+arg_28], eax
0x18001e625  mov     r8, r10; ActivityId
0x18001e628  mov     eax, dword ptr [rsp+48h+arg_28]
0x18001e62c  mov     eax, [rsp+48h+arg_20]
0x18001e630  mov     rcx, [r11+20h]; RegHandle
0x18001e634  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18001e638  call    cs:__imp_EventWriteTransfer
0x18001e63e  add     rsp, 48h
0x18001e642  retn
```
