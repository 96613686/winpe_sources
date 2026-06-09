# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x18000f3bc`
- end: `0x18000f45a`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x180001048`
- `0x18001d240`
- `0x18005d774`
- `0x1800643c4`
- `0x1800648e0`
- `0x180064a30`
- `0x180064b90`
- `0x180064d5c`
- `0x180064e80`
- `0x1800653ac`
- `0x1800657b4`
- `0x180065a74`
- `0x180065c48`
- `0x180065f70`
- `0x180066074`
- `0x180066330`
- `0x18006af54`
- `0x18006afe8`
- `0x18006b178`
- `0x18006b23c`
- `0x18006b3a0`
- `0x18006b4c8`
- `0x1800e69d4`
- `0x1800e6a8c`
- `0x1800e6c74`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x18000f448`
- `ntoskrnl!EtwWriteTransfer` at `0x18000f448`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
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
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000f3bc  sub     rsp, 48h
0x18000f3c0  movzx   eax, byte ptr [rdx]
0x18000f3c3  mov     r11, rcx
0x18000f3c6  shl     eax, 18h
0x18000f3c9  mov     r10, r8
0x18000f3cc  mov     r8, [rsp+48h+arg_28]
0x18000f3d1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000f3d5  movzx   eax, word ptr [rdx+1]
0x18000f3d9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000f3dd  mov     rax, [rdx+3]
0x18000f3e1  add     rdx, 0Bh
0x18000f3e5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000f3ea  mov     rax, [rcx+8]
0x18000f3ee  mov     [r8], rax
0x18000f3f1  mov     rax, [rcx+8]
0x18000f3f5  mov     [rsp+48h+UserData], r8; UserData
0x18000f3fa  movzx   ecx, word ptr [rax]
0x18000f3fd  mov     [r8+8], ecx
0x18000f401  lea     rcx, _TraceLoggingMetadata
0x18000f408  mov     [r8+10h], rdx
0x18000f40c  mov     dword ptr [r8+0Ch], 2
0x18000f414  movzx   eax, word ptr [rdx]
0x18000f417  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000f41c  mov     [r8+18h], eax
0x18000f420  lea     rax, _TraceLoggingMetadataEnd
0x18000f427  sub     eax, ecx
0x18000f429  mov     dword ptr [r8+1Ch], 1
0x18000f431  mov     dword ptr [rsp+48h+arg_28], eax
0x18000f435  mov     r8, r10; ActivityId
0x18000f438  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000f43c  mov     eax, [rsp+48h+arg_20]
0x18000f440  mov     rcx, [r11+20h]; RegHandle
0x18000f444  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000f448  call    cs:__imp_EtwWriteTransfer
0x18000f44f  nop     dword ptr [rax+rax+00h]
0x18000f454  add     rsp, 48h
0x18000f458  retn
```
