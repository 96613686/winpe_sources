# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001640`
- end: `0x1800016de`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016e4`
- `0x180001774`
- `0x180001a18`
- `0x180001d90`
- `0x1800020c0`
- `0x180002394`
- `0x180002698`
- `0x1800027a4`
- `0x18000c3dc`
- `0x18000e008`
- `0x18000e920`
- `0x180018224`
- `0x18001838c`
- `0x1800184f4`
- `0x18001865c`
- `0x1800187c4`
- `0x18001892c`
- `0x180018d3c`
- `0x1800195cc`
- `0x180019cfc`
- `0x18001a34c`
- `0x18001a93c`
- `0x1800349f0`
- `0x180050c3c`
- `0x180050da4`
- `0x18005144c`
- `0x180053970`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800016cc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800016cc`

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
0x180001640  sub     rsp, 48h
0x180001644  movzx   eax, byte ptr [rdx]
0x180001647  mov     r11, rcx
0x18000164a  shl     eax, 18h
0x18000164d  mov     r10, r8
0x180001650  mov     r8, [rsp+48h+arg_28]
0x180001655  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001659  movzx   eax, word ptr [rdx+1]
0x18000165d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001661  mov     rax, [rdx+3]
0x180001665  add     rdx, 0Bh
0x180001669  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000166e  mov     rax, [rcx+8]
0x180001672  mov     [r8], rax
0x180001675  mov     rax, [rcx+8]
0x180001679  mov     [rsp+48h+UserData], r8; UserData
0x18000167e  movzx   ecx, word ptr [rax]
0x180001681  mov     [r8+8], ecx
0x180001685  lea     rcx, _TraceLoggingMetadata
0x18000168c  mov     [r8+10h], rdx
0x180001690  mov     dword ptr [r8+0Ch], 2
0x180001698  movzx   eax, word ptr [rdx]
0x18000169b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800016a0  mov     [r8+18h], eax
0x1800016a4  lea     rax, _TraceLoggingMetadataEnd
0x1800016ab  sub     eax, ecx
0x1800016ad  mov     dword ptr [r8+1Ch], 1
0x1800016b5  mov     dword ptr [rsp+48h+arg_28], eax
0x1800016b9  mov     r8, r10; ActivityId
0x1800016bc  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800016c0  mov     eax, [rsp+48h+arg_20]
0x1800016c4  mov     rcx, [r11+20h]; RegHandle
0x1800016c8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800016cc  call    cs:__imp_EventWriteTransfer
0x1800016d3  nop     dword ptr [rax+rax+00h]
0x1800016d8  add     rsp, 48h
0x1800016dc  retn
```
