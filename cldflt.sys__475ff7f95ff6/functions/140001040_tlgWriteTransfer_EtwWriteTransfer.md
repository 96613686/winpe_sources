# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001040`
- end: `0x1400010de`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: `NTSTATUS __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010e4`
- `0x14000a22c`
- `0x14000ad88`
- `0x14000b7e8`
- `0x14000da00`
- `0x140015660`
- `0x1400158e8`
- `0x140015a30`
- `0x140015ca8`
- `0x140015ec0`
- `0x14001615c`
- `0x1400164ac`
- `0x1400166bc`
- `0x14001694c`
- `0x140016cd0`
- `0x140016dc4`
- `0x140016e98`
- `0x140017350`
- `0x1400176f0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400010cc`
- `ntoskrnl!EtwWriteTransfer` at `0x1400010cc`

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
0x140001040  sub     rsp, 48h
0x140001044  movzx   eax, byte ptr [rdx]
0x140001047  mov     r11, rcx
0x14000104a  shl     eax, 18h
0x14000104d  mov     r10, r8
0x140001050  mov     r8, [rsp+48h+arg_28]
0x140001055  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001059  movzx   eax, word ptr [rdx+1]
0x14000105d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001061  mov     rax, [rdx+3]
0x140001065  add     rdx, 0Bh
0x140001069  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000106e  mov     rax, [rcx+8]
0x140001072  mov     [r8], rax
0x140001075  mov     rax, [rcx+8]
0x140001079  mov     [rsp+48h+UserData], r8; UserData
0x14000107e  movzx   ecx, word ptr [rax]
0x140001081  mov     [r8+8], ecx
0x140001085  lea     rcx, _TraceLoggingMetadata
0x14000108c  mov     [r8+10h], rdx
0x140001090  mov     dword ptr [r8+0Ch], 2
0x140001098  movzx   eax, word ptr [rdx]
0x14000109b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400010a0  mov     [r8+18h], eax
0x1400010a4  lea     rax, _TraceLoggingMetadataEnd
0x1400010ab  sub     eax, ecx
0x1400010ad  mov     dword ptr [r8+1Ch], 1
0x1400010b5  mov     dword ptr [rsp+48h+arg_28], eax
0x1400010b9  mov     r8, r10; ActivityId
0x1400010bc  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400010c0  mov     eax, [rsp+48h+arg_20]
0x1400010c4  mov     rcx, [r11+20h]; RegHandle
0x1400010c8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400010cc  call    cs:__imp_EtwWriteTransfer
0x1400010d3  nop     dword ptr [rax+rax+00h]
0x1400010d8  add     rsp, 48h
0x1400010dc  retn
```
