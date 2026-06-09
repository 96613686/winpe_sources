# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800012f0`
- end: `0x1800013a3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800013ac`

## callees

- `0x180004310`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000138b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000138b`

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
0x1800012f0  sub     rsp, 58h
0x1800012f4  mov     rax, cs:__security_cookie
0x1800012fb  xor     rax, rsp
0x1800012fe  mov     [rsp+58h+var_10], rax
0x180001303  movzx   eax, byte ptr [rdx]
0x180001306  mov     r11, rcx
0x180001309  mov     r10, [rsp+58h+arg_28]
0x180001311  shl     eax, 18h
0x180001314  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001318  movzx   eax, word ptr [rdx+1]
0x18000131c  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001320  mov     rax, [rdx+3]
0x180001324  add     rdx, 0Bh
0x180001328  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x18000132d  mov     rax, [rcx+8]
0x180001331  mov     [r10], rax
0x180001334  mov     rax, [rcx+8]
0x180001338  mov     [rsp+58h+UserData], r10; UserData
0x18000133d  movzx   ecx, word ptr [rax]
0x180001340  mov     [r10+8], ecx
0x180001344  lea     rcx, _TraceLoggingMetadata
0x18000134b  mov     [r10+10h], rdx
0x18000134f  mov     dword ptr [r10+0Ch], 2
0x180001357  movzx   eax, word ptr [rdx]
0x18000135a  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x18000135f  mov     [r10+18h], eax
0x180001363  lea     rax, _TraceLoggingMetadataEnd
0x18000136a  sub     eax, ecx
0x18000136c  mov     dword ptr [r10+1Ch], 1
0x180001374  mov     [rsp+58h+var_28], eax
0x180001378  mov     eax, [rsp+58h+var_28]
0x18000137c  mov     eax, [rsp+58h+arg_20]
0x180001383  mov     rcx, [r11+20h]; RegHandle
0x180001387  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x18000138b  call    cs:__imp_EventWriteTransfer
0x180001391  mov     rcx, [rsp+58h+var_10]
0x180001396  xor     rcx, rsp; StackCookie
0x180001399  call    __security_check_cookie
0x18000139e  add     rsp, 58h
0x1800013a2  retn
```
