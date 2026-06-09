# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001f68`
- end: `0x18000201b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800012cc`
- `0x1800015a4`
- `0x180001678`
- `0x18000173c`
- `0x1800017ac`
- `0x18000183c`
- `0x180001ae0`
- `0x18000f838`

## callees

- `0x180002620`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002003`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002003`

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
0x180001f68  sub     rsp, 58h
0x180001f6c  mov     rax, cs:__security_cookie
0x180001f73  xor     rax, rsp
0x180001f76  mov     [rsp+58h+var_10], rax
0x180001f7b  movzx   eax, byte ptr [rdx]
0x180001f7e  mov     r11, rcx
0x180001f81  mov     r10, [rsp+58h+arg_28]
0x180001f89  shl     eax, 18h
0x180001f8c  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001f90  movzx   eax, word ptr [rdx+1]
0x180001f94  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001f98  mov     rax, [rdx+3]
0x180001f9c  add     rdx, 0Bh
0x180001fa0  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001fa5  mov     rax, [rcx+8]
0x180001fa9  mov     [r10], rax
0x180001fac  mov     rax, [rcx+8]
0x180001fb0  mov     [rsp+58h+UserData], r10; UserData
0x180001fb5  movzx   ecx, word ptr [rax]
0x180001fb8  mov     [r10+8], ecx
0x180001fbc  lea     rcx, _TraceLoggingMetadata
0x180001fc3  mov     [r10+10h], rdx
0x180001fc7  mov     dword ptr [r10+0Ch], 2
0x180001fcf  movzx   eax, word ptr [rdx]
0x180001fd2  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001fd7  mov     [r10+18h], eax
0x180001fdb  lea     rax, _TraceLoggingMetadataEnd
0x180001fe2  sub     eax, ecx
0x180001fe4  mov     dword ptr [r10+1Ch], 1
0x180001fec  mov     [rsp+58h+var_28], eax
0x180001ff0  mov     eax, [rsp+58h+var_28]
0x180001ff4  mov     eax, [rsp+58h+arg_20]
0x180001ffb  mov     rcx, [r11+20h]; RegHandle
0x180001fff  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180002003  call    cs:__imp_EventWriteTransfer
0x180002009  mov     rcx, [rsp+58h+var_10]
0x18000200e  xor     rcx, rsp; StackCookie
0x180002011  call    __security_check_cookie
0x180002016  add     rsp, 58h
0x18000201a  retn
```
