# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x18000f3cc`
- end: `0x18000f46a`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x180001048`
- `0x18001d238`
- `0x18005dd74`
- `0x180064e4c`
- `0x180065344`
- `0x180065494`
- `0x1800655f4`
- `0x1800657c0`
- `0x1800658e4`
- `0x180065e10`
- `0x180066218`
- `0x1800664d8`
- `0x1800666ac`
- `0x1800669d4`
- `0x180066ad8`
- `0x180066d94`
- `0x18006c344`
- `0x18006c3d8`
- `0x18006c568`
- `0x18006c62c`
- `0x18006c790`
- `0x1800e7910`
- `0x1800e79c8`
- `0x1800e7bb0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x18000f458`
- `ntoskrnl!EtwWriteTransfer` at `0x18000f458`

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
0x18000f3cc  sub     rsp, 48h
0x18000f3d0  movzx   eax, byte ptr [rdx]
0x18000f3d3  mov     r11, rcx
0x18000f3d6  shl     eax, 18h
0x18000f3d9  mov     r10, r8
0x18000f3dc  mov     r8, [rsp+48h+arg_28]
0x18000f3e1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000f3e5  movzx   eax, word ptr [rdx+1]
0x18000f3e9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000f3ed  mov     rax, [rdx+3]
0x18000f3f1  add     rdx, 0Bh
0x18000f3f5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000f3fa  mov     rax, [rcx+8]
0x18000f3fe  mov     [r8], rax
0x18000f401  mov     rax, [rcx+8]
0x18000f405  mov     [rsp+48h+UserData], r8; UserData
0x18000f40a  movzx   ecx, word ptr [rax]
0x18000f40d  mov     [r8+8], ecx
0x18000f411  lea     rcx, _TraceLoggingMetadata
0x18000f418  mov     [r8+10h], rdx
0x18000f41c  mov     dword ptr [r8+0Ch], 2
0x18000f424  movzx   eax, word ptr [rdx]
0x18000f427  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000f42c  mov     [r8+18h], eax
0x18000f430  lea     rax, _TraceLoggingMetadataEnd
0x18000f437  sub     eax, ecx
0x18000f439  mov     dword ptr [r8+1Ch], 1
0x18000f441  mov     dword ptr [rsp+48h+arg_28], eax
0x18000f445  mov     r8, r10; ActivityId
0x18000f448  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000f44c  mov     eax, [rsp+48h+arg_20]
0x18000f450  mov     rcx, [r11+20h]; RegHandle
0x18000f454  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000f458  call    cs:__imp_EtwWriteTransfer
0x18000f45f  nop     dword ptr [rax+rax+00h]
0x18000f464  add     rsp, 48h
0x18000f468  retn
```
