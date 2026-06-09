# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18003049c`
- end: `0x180030533`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800015dc`
- `0x1800019d8`
- `0x180001c78`
- `0x180001e48`
- `0x180001ec0`
- `0x180001fb4`
- `0x180002064`
- `0x18000216c`
- `0x1800021e8`
- `0x180002280`
- `0x180002398`
- `0x1800024b8`
- `0x180002cd4`
- `0x180002dac`
- `0x180002f50`
- `0x18000301c`
- `0x1800031f0`
- `0x180003650`
- `0x180003738`
- `0x18002fd3c`
- `0x18002fe5c`
- `0x18003020c`
- `0x180030354`
- `0x180040f1c`
- `0x180060760`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180030528`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180030528`

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
0x18003049c  sub     rsp, 48h
0x1800304a0  movzx   eax, byte ptr [rdx]
0x1800304a3  mov     r11, rcx
0x1800304a6  shl     eax, 18h
0x1800304a9  mov     r10, r8
0x1800304ac  mov     r8, [rsp+48h+arg_28]
0x1800304b1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800304b5  movzx   eax, word ptr [rdx+1]
0x1800304b9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800304bd  mov     rax, [rdx+3]
0x1800304c1  add     rdx, 0Bh
0x1800304c5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800304ca  mov     rax, [rcx+8]
0x1800304ce  mov     [r8], rax
0x1800304d1  mov     rax, [rcx+8]
0x1800304d5  mov     [rsp+48h+UserData], r8; UserData
0x1800304da  movzx   ecx, word ptr [rax]
0x1800304dd  mov     [r8+8], ecx
0x1800304e1  lea     rcx, _TraceLoggingMetadata
0x1800304e8  mov     [r8+10h], rdx
0x1800304ec  mov     dword ptr [r8+0Ch], 2
0x1800304f4  movzx   eax, word ptr [rdx]
0x1800304f7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800304fc  mov     [r8+18h], eax
0x180030500  lea     rax, _TraceLoggingMetadataEnd
0x180030507  sub     eax, ecx
0x180030509  mov     dword ptr [r8+1Ch], 1
0x180030511  mov     dword ptr [rsp+48h+arg_28], eax
0x180030515  mov     r8, r10; ActivityId
0x180030518  mov     eax, dword ptr [rsp+48h+arg_28]
0x18003051c  mov     eax, [rsp+48h+arg_20]
0x180030520  mov     rcx, [r11+20h]; RegHandle
0x180030524  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180030528  call    cs:__imp_EventWriteTransfer
0x18003052e  add     rsp, 48h
0x180030532  retn
```
