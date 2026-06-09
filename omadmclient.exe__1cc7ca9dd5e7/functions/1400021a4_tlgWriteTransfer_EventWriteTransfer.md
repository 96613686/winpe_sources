# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400021a4`
- end: `0x140002242`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x140001150`
- `0x140001250`
- `0x140001314`
- `0x1400013e0`
- `0x1400014a4`
- `0x14000154c`
- `0x140001684`
- `0x1400017ac`
- `0x1400018a0`
- `0x1400019a0`
- `0x140001a90`
- `0x140001b60`
- `0x140001c20`
- `0x140001ec8`
- `0x140001f8c`
- `0x1400020b4`
- `0x140002248`
- `0x140002360`
- `0x140002484`
- `0x140002574`
- `0x140002668`
- `0x140002758`
- `0x14000e7ac`
- `0x14000e928`
- `0x14000ed54`
- `0x14000f074`
- `0x14000f590`
- `0x14000fc70`
- `0x14000ff64`
- `0x14001021c`
- `0x140065790`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002230`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002230`

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
0x1400021a4  sub     rsp, 48h
0x1400021a8  movzx   eax, byte ptr [rdx]
0x1400021ab  mov     r11, rcx
0x1400021ae  shl     eax, 18h
0x1400021b1  mov     r10, r8
0x1400021b4  mov     r8, [rsp+48h+arg_28]
0x1400021b9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400021bd  movzx   eax, word ptr [rdx+1]
0x1400021c1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400021c5  mov     rax, [rdx+3]
0x1400021c9  add     rdx, 0Bh
0x1400021cd  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400021d2  mov     rax, [rcx+8]
0x1400021d6  mov     [r8], rax
0x1400021d9  mov     rax, [rcx+8]
0x1400021dd  mov     [rsp+48h+UserData], r8; UserData
0x1400021e2  movzx   ecx, word ptr [rax]
0x1400021e5  mov     [r8+8], ecx
0x1400021e9  lea     rcx, _TraceLoggingMetadata
0x1400021f0  mov     [r8+10h], rdx
0x1400021f4  mov     dword ptr [r8+0Ch], 2
0x1400021fc  movzx   eax, word ptr [rdx]
0x1400021ff  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140002204  mov     [r8+18h], eax
0x140002208  lea     rax, _TraceLoggingMetadataEnd
0x14000220f  sub     eax, ecx
0x140002211  mov     dword ptr [r8+1Ch], 1
0x140002219  mov     dword ptr [rsp+48h+arg_28], eax
0x14000221d  mov     r8, r10; ActivityId
0x140002220  mov     eax, dword ptr [rsp+48h+arg_28]
0x140002224  mov     eax, [rsp+48h+arg_20]
0x140002228  mov     rcx, [r11+20h]; RegHandle
0x14000222c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140002230  call    cs:__imp_EventWriteTransfer
0x140002237  nop     dword ptr [rax+rax+00h]
0x14000223c  add     rsp, 48h
0x140002240  retn
```
