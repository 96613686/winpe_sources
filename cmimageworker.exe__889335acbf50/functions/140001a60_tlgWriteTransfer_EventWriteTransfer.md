# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001a60`
- end: `0x140001afe`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400012bc`
- `0x14000134c`
- `0x1400015f0`
- `0x1400018e8`
- `0x140003840`
- `0x1400078e4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001aec`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001aec`

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
0x140001a60  sub     rsp, 48h
0x140001a64  movzx   eax, byte ptr [rdx]
0x140001a67  mov     r11, rcx
0x140001a6a  shl     eax, 18h
0x140001a6d  mov     r10, r8
0x140001a70  mov     r8, [rsp+48h+arg_28]
0x140001a75  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001a79  movzx   eax, word ptr [rdx+1]
0x140001a7d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001a81  mov     rax, [rdx+3]
0x140001a85  add     rdx, 0Bh
0x140001a89  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001a8e  mov     rax, [rcx+8]
0x140001a92  mov     [r8], rax
0x140001a95  mov     rax, [rcx+8]
0x140001a99  mov     [rsp+48h+UserData], r8; UserData
0x140001a9e  movzx   ecx, word ptr [rax]
0x140001aa1  mov     [r8+8], ecx
0x140001aa5  lea     rcx, _TraceLoggingMetadata
0x140001aac  mov     [r8+10h], rdx
0x140001ab0  mov     dword ptr [r8+0Ch], 2
0x140001ab8  movzx   eax, word ptr [rdx]
0x140001abb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001ac0  mov     [r8+18h], eax
0x140001ac4  lea     rax, _TraceLoggingMetadataEnd
0x140001acb  sub     eax, ecx
0x140001acd  mov     dword ptr [r8+1Ch], 1
0x140001ad5  mov     dword ptr [rsp+48h+arg_28], eax
0x140001ad9  mov     r8, r10; ActivityId
0x140001adc  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001ae0  mov     eax, [rsp+48h+arg_20]
0x140001ae4  mov     rcx, [r11+20h]; RegHandle
0x140001ae8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001aec  call    cs:__imp_EventWriteTransfer
0x140001af3  nop     dword ptr [rax+rax+00h]
0x140001af8  add     rsp, 48h
0x140001afc  retn
```
