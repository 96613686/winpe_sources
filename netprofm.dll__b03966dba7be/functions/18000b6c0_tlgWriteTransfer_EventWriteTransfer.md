# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000b6c0`
- end: `0x18000b773`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x180001084`
- `0x1800011cc`
- `0x18000b624`

## callees

- `0x1800120d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b75b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b75b`

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
0x18000b6c0  sub     rsp, 58h
0x18000b6c4  mov     rax, cs:__security_cookie
0x18000b6cb  xor     rax, rsp
0x18000b6ce  mov     [rsp+58h+var_10], rax
0x18000b6d3  movzx   eax, byte ptr [rdx]
0x18000b6d6  mov     r11, rcx
0x18000b6d9  mov     r10, [rsp+58h+arg_28]
0x18000b6e1  shl     eax, 18h
0x18000b6e4  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x18000b6e8  movzx   eax, word ptr [rdx+1]
0x18000b6ec  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x18000b6f0  mov     rax, [rdx+3]
0x18000b6f4  add     rdx, 0Bh
0x18000b6f8  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x18000b6fd  mov     rax, [rcx+8]
0x18000b701  mov     [r10], rax
0x18000b704  mov     rax, [rcx+8]
0x18000b708  mov     [rsp+58h+UserData], r10; UserData
0x18000b70d  movzx   ecx, word ptr [rax]
0x18000b710  mov     [r10+8], ecx
0x18000b714  lea     rcx, _TraceLoggingMetadata
0x18000b71b  mov     [r10+10h], rdx
0x18000b71f  mov     dword ptr [r10+0Ch], 2
0x18000b727  movzx   eax, word ptr [rdx]
0x18000b72a  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x18000b72f  mov     [r10+18h], eax
0x18000b733  lea     rax, _TraceLoggingMetadataEnd
0x18000b73a  sub     eax, ecx
0x18000b73c  mov     dword ptr [r10+1Ch], 1
0x18000b744  mov     [rsp+58h+var_28], eax
0x18000b748  mov     eax, [rsp+58h+var_28]
0x18000b74c  mov     eax, [rsp+58h+arg_20]
0x18000b753  mov     rcx, [r11+20h]; RegHandle
0x18000b757  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x18000b75b  call    cs:__imp_EventWriteTransfer
0x18000b761  mov     rcx, [rsp+58h+var_10]
0x18000b766  xor     rcx, rsp; StackCookie
0x18000b769  call    __security_check_cookie
0x18000b76e  add     rsp, 58h
0x18000b772  retn
```
