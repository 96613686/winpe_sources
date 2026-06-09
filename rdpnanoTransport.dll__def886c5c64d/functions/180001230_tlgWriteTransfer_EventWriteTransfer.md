# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001230`
- end: `0x1800012ec`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `188`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `176`
- callee_count: `2`
- tags: ``

## callers

- `0x180001000`
- `0x1800012ec`
- `0x180001404`
- `0x180001494`
- `0x180001574`
- `0x180001604`
- `0x180001694`
- `0x180001724`
- `0x1800017b4`
- `0x180001854`
- `0x1800018dc`
- `0x18000196c`
- `0x1800019fc`
- `0x180001a9c`
- `0x180001b5c`
- `0x180001c90`
- `0x180001d50`
- `0x180001df0`
- `0x180001eb0`
- `0x180001f80`
- `0x180002010`
- `0x1800020f4`
- `0x1800021d8`
- `0x180002268`
- `0x180002338`
- `0x1800023d8`
- `0x180002468`
- `0x180002578`
- `0x180002608`
- `0x1800026c8`
- `0x180002768`
- `0x180002808`
- `0x1800028ac`
- `0x1800029a8`
- `0x180002a38`
- `0x180002ad8`
- `0x180002b98`
- `0x180002c48`
- `0x180002cd8`
- `0x180002d68`
- `0x180002e18`
- `0x180002ee8`
- `0x180002f94`
- `0x180003064`
- `0x180003104`
- `0x1800031e8`
- `0x1800032a8`
- `0x180003338`
- `0x1800033c8`
- `0x180003488`

## callees

- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800012d4`
- `ADVAPI32!EventWriteTransfer` at `0x1800012d4`

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
0x180001230  mov     eax, 58h
0x180001235  call    _alloca_probe
0x18000123a  sub     rsp, rax
0x18000123d  mov     rax, cs:__security_cookie
0x180001244  xor     rax, rsp
0x180001247  mov     [rsp+58h+var_10], rax
0x18000124c  movzx   eax, byte ptr [rdx]
0x18000124f  mov     r11, rcx
0x180001252  mov     r10, [rsp+58h+arg_28]
0x18000125a  shl     eax, 18h
0x18000125d  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001261  movzx   eax, word ptr [rdx+1]
0x180001265  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001269  mov     rax, [rdx+3]
0x18000126d  add     rdx, 0Bh
0x180001271  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001276  mov     rax, [rcx+8]
0x18000127a  mov     [r10], rax
0x18000127d  mov     rax, [rcx+8]
0x180001281  mov     [rsp+58h+UserData], r10; UserData
0x180001286  movzx   ecx, word ptr [rax]
0x180001289  mov     [r10+8], ecx
0x18000128d  lea     rcx, _TraceLoggingMetadata
0x180001294  mov     [r10+10h], rdx
0x180001298  mov     dword ptr [r10+0Ch], 2
0x1800012a0  movzx   eax, word ptr [rdx]
0x1800012a3  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x1800012a8  mov     [r10+18h], eax
0x1800012ac  lea     rax, _TraceLoggingMetadataEnd
0x1800012b3  sub     eax, ecx
0x1800012b5  mov     dword ptr [r10+1Ch], 1
0x1800012bd  mov     [rsp+58h+var_28], eax
0x1800012c1  mov     eax, [rsp+58h+var_28]
0x1800012c5  mov     eax, [rsp+58h+arg_20]
0x1800012cc  mov     rcx, [r11+20h]; RegHandle
0x1800012d0  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1800012d4  call    cs:__imp_EventWriteTransfer
0x1800012da  mov     rcx, [rsp+58h+var_10]
0x1800012df  xor     rcx, rsp; StackCookie
0x1800012e2  call    __security_check_cookie
0x1800012e7  add     rsp, 58h
0x1800012eb  retn
```
