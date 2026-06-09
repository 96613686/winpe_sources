# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400011d8`
- end: `0x14000126f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `27`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400010e0`
- `0x140001278`
- `0x140001308`
- `0x1400013ac`
- `0x140001454`
- `0x140001518`
- `0x1400015c4`
- `0x14000168c`
- `0x140001728`
- `0x140001824`
- `0x140001ad8`
- `0x140001bd4`
- `0x140001d38`
- `0x140001e94`
- `0x14000218c`
- `0x1400022b4`
- `0x140002368`
- `0x140024900`
- `0x140027364`
- `0x14002776c`
- `0x140027a4c`
- `0x140028a80`
- `0x14002a4b8`
- `0x14002cb80`
- `0x14002cfb4`
- `0x140033a3c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001264`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001264`

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
0x1400011d8  sub     rsp, 48h
0x1400011dc  movzx   eax, byte ptr [rdx]
0x1400011df  mov     r11, rcx
0x1400011e2  shl     eax, 18h
0x1400011e5  mov     r10, r8
0x1400011e8  mov     r8, [rsp+48h+arg_28]
0x1400011ed  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400011f1  movzx   eax, word ptr [rdx+1]
0x1400011f5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400011f9  mov     rax, [rdx+3]
0x1400011fd  add     rdx, 0Bh
0x140001201  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001206  mov     rax, [rcx+8]
0x14000120a  mov     [r8], rax
0x14000120d  mov     rax, [rcx+8]
0x140001211  mov     [rsp+48h+UserData], r8; UserData
0x140001216  movzx   ecx, word ptr [rax]
0x140001219  mov     [r8+8], ecx
0x14000121d  lea     rcx, _TraceLoggingMetadata
0x140001224  mov     [r8+10h], rdx
0x140001228  mov     dword ptr [r8+0Ch], 2
0x140001230  movzx   eax, word ptr [rdx]
0x140001233  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001238  mov     [r8+18h], eax
0x14000123c  lea     rax, _TraceLoggingMetadataEnd
0x140001243  sub     eax, ecx
0x140001245  mov     dword ptr [r8+1Ch], 1
0x14000124d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001251  mov     r8, r10; ActivityId
0x140001254  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001258  mov     eax, [rsp+48h+arg_20]
0x14000125c  mov     rcx, [r11+20h]; RegHandle
0x140001260  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001264  call    cs:__imp_EventWriteTransfer
0x14000126a  add     rsp, 48h
0x14000126e  retn
```
