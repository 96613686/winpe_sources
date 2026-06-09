# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180002128`
- end: `0x1800021db`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `96`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800010a8`
- `0x1800011bc`
- `0x180001234`
- `0x180001294`
- `0x180001308`
- `0x1800015e0`
- `0x1800016b4`
- `0x180001778`
- `0x180001874`
- `0x18000196c`
- `0x180001c20`
- `0x180001c98`
- `0x1800021e4`
- `0x18000222c`
- `0x180002318`
- `0x18000245c`
- `0x1800025c0`
- `0x1800026b4`
- `0x180002870`
- `0x1800029f4`
- `0x180002ae8`
- `0x180002bec`
- `0x180002d14`
- `0x180002dec`
- `0x180002f1c`
- `0x180002fb0`
- `0x180003044`
- `0x18000310c`
- `0x1800031b4`
- `0x18000327c`
- `0x180003354`
- `0x180003440`
- `0x1800035f8`
- `0x180003724`
- `0x180003844`
- `0x1800039cc`
- `0x180003ae8`
- `0x180003c68`
- `0x180003e08`
- `0x180003f44`
- `0x1800040e4`
- `0x180004298`
- `0x18000438c`
- `0x1800043ec`
- `0x1800044e0`
- `0x180004590`
- `0x1800046f4`
- `0x180004820`
- `0x180004914`

## callees

- `0x180007c90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800021c3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800021c3`

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
0x180002128  sub     rsp, 58h
0x18000212c  mov     rax, cs:__security_cookie
0x180002133  xor     rax, rsp
0x180002136  mov     [rsp+58h+var_10], rax
0x18000213b  movzx   eax, byte ptr [rdx]
0x18000213e  mov     r11, rcx
0x180002141  mov     r10, [rsp+58h+arg_28]
0x180002149  shl     eax, 18h
0x18000214c  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180002150  movzx   eax, word ptr [rdx+1]
0x180002154  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180002158  mov     rax, [rdx+3]
0x18000215c  add     rdx, 0Bh
0x180002160  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180002165  mov     rax, [rcx+8]
0x180002169  mov     [r10], rax
0x18000216c  mov     rax, [rcx+8]
0x180002170  mov     [rsp+58h+UserData], r10; UserData
0x180002175  movzx   ecx, word ptr [rax]
0x180002178  mov     [r10+8], ecx
0x18000217c  lea     rcx, _TraceLoggingMetadata
0x180002183  mov     [r10+10h], rdx
0x180002187  mov     dword ptr [r10+0Ch], 2
0x18000218f  movzx   eax, word ptr [rdx]
0x180002192  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180002197  mov     [r10+18h], eax
0x18000219b  lea     rax, _TraceLoggingMetadataEnd
0x1800021a2  sub     eax, ecx
0x1800021a4  mov     dword ptr [r10+1Ch], 1
0x1800021ac  mov     [rsp+58h+var_28], eax
0x1800021b0  mov     eax, [rsp+58h+var_28]
0x1800021b4  mov     eax, [rsp+58h+arg_20]
0x1800021bb  mov     rcx, [r11+20h]; RegHandle
0x1800021bf  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1800021c3  call    cs:__imp_EventWriteTransfer
0x1800021c9  mov     rcx, [rsp+58h+var_10]
0x1800021ce  xor     rcx, rsp; StackCookie
0x1800021d1  call    __security_check_cookie
0x1800021d6  add     rsp, 58h
0x1800021da  retn
```
