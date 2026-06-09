# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001c88`
- end: `0x140001d3b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x140001304`
- `0x1400013d8`
- `0x14000149c`
- `0x140001750`

## callees

- `0x140002360`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001d23`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001d23`

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
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-20h] BYREF

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
0x140001c88  sub     rsp, 58h
0x140001c8c  mov     rax, cs:__security_cookie
0x140001c93  xor     rax, rsp
0x140001c96  mov     [rsp+58h+var_10], rax
0x140001c9b  movzx   eax, byte ptr [rdx]
0x140001c9e  mov     r11, rcx
0x140001ca1  mov     r10, [rsp+58h+arg_28]
0x140001ca9  shl     eax, 18h
0x140001cac  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x140001cb0  movzx   eax, word ptr [rdx+1]
0x140001cb4  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x140001cb8  mov     rax, [rdx+3]
0x140001cbc  add     rdx, 0Bh
0x140001cc0  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x140001cc5  mov     rax, [rcx+8]
0x140001cc9  mov     [r10], rax
0x140001ccc  mov     rax, [rcx+8]
0x140001cd0  mov     [rsp+58h+UserData], r10; UserData
0x140001cd5  movzx   ecx, word ptr [rax]
0x140001cd8  mov     [r10+8], ecx
0x140001cdc  lea     rcx, _TraceLoggingMetadata
0x140001ce3  mov     [r10+10h], rdx
0x140001ce7  mov     dword ptr [r10+0Ch], 2
0x140001cef  movzx   eax, word ptr [rdx]
0x140001cf2  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x140001cf7  mov     [r10+18h], eax
0x140001cfb  lea     rax, _TraceLoggingMetadataEnd
0x140001d02  sub     eax, ecx
0x140001d04  mov     dword ptr [r10+1Ch], 1
0x140001d0c  mov     [rsp+58h+var_28], eax
0x140001d10  mov     eax, [rsp+58h+var_28]
0x140001d14  mov     eax, [rsp+58h+arg_20]
0x140001d1b  mov     rcx, [r11+20h]; RegHandle
0x140001d1f  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x140001d23  call    cs:__imp_EventWriteTransfer
0x140001d29  mov     rcx, [rsp+58h+var_10]
0x140001d2e  xor     rcx, rsp; StackCookie
0x140001d31  call    __security_check_cookie
0x140001d36  add     rsp, 58h
0x140001d3a  retn
```
