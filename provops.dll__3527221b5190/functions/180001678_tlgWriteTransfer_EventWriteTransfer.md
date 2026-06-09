# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001678`
- end: `0x18000170f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `55`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001718`
- `0x180001760`
- `0x1800017ec`
- `0x180001878`
- `0x180001920`
- `0x18000197c`
- `0x180001a88`
- `0x180001b4c`
- `0x180001bf4`
- `0x180001f08`
- `0x180001f98`
- `0x18000223c`
- `0x180002300`
- `0x1800023dc`
- `0x1800024fc`
- `0x180002614`
- `0x18000270c`
- `0x180006b24`
- `0x18000a61c`
- `0x18000a7d0`
- `0x18000a954`
- `0x18000ad74`
- `0x18000ae0c`
- `0x18000c2a4`
- `0x18000c2fc`
- `0x18000c354`
- `0x18000f8d0`
- `0x180010b40`
- `0x180013e9c`
- `0x180014434`
- `0x180016840`
- `0x180017f68`
- `0x1800180ac`
- `0x1800181f4`
- `0x18001833c`
- `0x1800184b4`
- `0x18001862c`
- `0x1800187a4`
- `0x180018944`
- `0x180018cc4`
- `0x180023558`
- `0x180023d4c`
- `0x180025660`
- `0x180028df4`
- `0x180028e74`
- `0x1800296a0`
- `0x18002a170`
- `0x18002ac38`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001704`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001704`

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
0x180001678  sub     rsp, 48h
0x18000167c  movzx   eax, byte ptr [rdx]
0x18000167f  mov     r11, rcx
0x180001682  shl     eax, 18h
0x180001685  mov     r10, r8
0x180001688  mov     r8, [rsp+48h+arg_28]
0x18000168d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001691  movzx   eax, word ptr [rdx+1]
0x180001695  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001699  mov     rax, [rdx+3]
0x18000169d  add     rdx, 0Bh
0x1800016a1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800016a6  mov     rax, [rcx+8]
0x1800016aa  mov     [r8], rax
0x1800016ad  mov     rax, [rcx+8]
0x1800016b1  mov     [rsp+48h+UserData], r8; UserData
0x1800016b6  movzx   ecx, word ptr [rax]
0x1800016b9  mov     [r8+8], ecx
0x1800016bd  lea     rcx, _TraceLoggingMetadata
0x1800016c4  mov     [r8+10h], rdx
0x1800016c8  mov     dword ptr [r8+0Ch], 2
0x1800016d0  movzx   eax, word ptr [rdx]
0x1800016d3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800016d8  mov     [r8+18h], eax
0x1800016dc  lea     rax, _TraceLoggingMetadataEnd
0x1800016e3  sub     eax, ecx
0x1800016e5  mov     dword ptr [r8+1Ch], 1
0x1800016ed  mov     dword ptr [rsp+48h+arg_28], eax
0x1800016f1  mov     r8, r10; ActivityId
0x1800016f4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800016f8  mov     eax, [rsp+48h+arg_20]
0x1800016fc  mov     rcx, [r11+20h]; RegHandle
0x180001700  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001704  call    cs:__imp_EventWriteTransfer
0x18000170a  add     rsp, 48h
0x18000170e  retn
```
