# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001ed0`
- end: `0x180001f8a`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `186`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x18000109c`
- `0x180001350`
- `0x180001664`
- `0x1800016f4`
- `0x1800017f0`
- `0x180001a94`
- `0x1800083d8`
- `0x18000f118`
- `0x18000f248`
- `0x18000f378`
- `0x18000f4a8`
- `0x18000f5d8`
- `0x18000f708`
- `0x18000f838`
- `0x18000f968`
- `0x18000fa98`
- `0x18000fbc8`
- `0x18000fcf8`
- `0x18000fe28`
- `0x18001a9c8`
- `0x18001b48c`
- `0x180029118`
- `0x18002a118`

## callees

- `0x180002690`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001f6b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001f6b`

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
0x180001ed0  sub     rsp, 58h
0x180001ed4  mov     rax, cs:__security_cookie
0x180001edb  xor     rax, rsp
0x180001ede  mov     [rsp+58h+var_10], rax
0x180001ee3  movzx   eax, byte ptr [rdx]
0x180001ee6  mov     r11, rcx
0x180001ee9  mov     r10, [rsp+58h+arg_28]
0x180001ef1  shl     eax, 18h
0x180001ef4  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001ef8  movzx   eax, word ptr [rdx+1]
0x180001efc  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001f00  mov     rax, [rdx+3]
0x180001f04  add     rdx, 0Bh
0x180001f08  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001f0d  mov     rax, [rcx+8]
0x180001f11  mov     [r10], rax
0x180001f14  mov     rax, [rcx+8]
0x180001f18  mov     [rsp+58h+UserData], r10; UserData
0x180001f1d  movzx   ecx, word ptr [rax]
0x180001f20  mov     [r10+8], ecx
0x180001f24  lea     rcx, _TraceLoggingMetadata
0x180001f2b  mov     [r10+10h], rdx
0x180001f2f  mov     dword ptr [r10+0Ch], 2
0x180001f37  movzx   eax, word ptr [rdx]
0x180001f3a  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001f3f  mov     [r10+18h], eax
0x180001f43  lea     rax, _TraceLoggingMetadataEnd
0x180001f4a  sub     eax, ecx
0x180001f4c  mov     dword ptr [r10+1Ch], 1
0x180001f54  mov     [rsp+58h+var_28], eax
0x180001f58  mov     eax, [rsp+58h+var_28]
0x180001f5c  mov     eax, [rsp+58h+arg_20]
0x180001f63  mov     rcx, [r11+20h]; RegHandle
0x180001f67  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180001f6b  call    cs:__imp_EventWriteTransfer
0x180001f72  nop     dword ptr [rax+rax+00h]
0x180001f77  mov     rcx, [rsp+58h+var_10]
0x180001f7c  xor     rcx, rsp; StackCookie
0x180001f7f  call    __security_check_cookie
0x180001f84  add     rsp, 58h
0x180001f88  retn
```
