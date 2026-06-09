# HbEvtpTransferBufferOwnershipToEtw

- ea: `0x140001f6c`
- end: `0x14000203c`
- name: `HbEvtpTransferBufferOwnershipToEtw`
- size: `208`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001bfc`

## callees

- `0x140001600`
- `0x140001f6c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140001fc8`
- `ntoskrnl!KeDelayExecutionThread` at `0x140001fc8`

## string_xrefs

- `0x140002016`: `Timeout waiting for buffer %d to become available`
- `0x140001f9d`: `Sleeping while waiting for buffer %d to become available`

## pseudocode

```c
__int64 __fastcall HbEvtpTransferBufferOwnershipToEtw(__int64 a1)
{
  unsigned int v1; // esi
  signed __int32 i; // eax
  _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  Interval.QuadPart = -500000;
  for ( i = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 88), 1, 0);
        ;
        i = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 88), 1, 0) )
  {
    if ( i != 1 )
    {
      HbpTraceEvent(
        3,
        "HbEvtpTransferBufferOwnershipToEtw",
        3726,
        "Buffer %d is now owned by ETW",
        *(_DWORD *)(a1 + 84));
      return 0;
    }
    if ( v1 >= 0xC8 )
      break;
    HbpTraceEvent(
      3,
      "HbEvtpTransferBufferOwnershipToEtw",
      3721,
      "Sleeping while waiting for buffer %d to become available",
      *(_DWORD *)(a1 + 84));
    KeDelayExecutionThread(0, 0, &Interval);
    ++v1;
  }
  HbpTraceEvent(
    0,
    "HbEvtpTransferBufferOwnershipToEtw",
    3718,
    "Timeout waiting for buffer %d to become available",
    *(_DWORD *)(a1 + 84));
  return 258;
}

```

## disassembly

```asm
0x140001f6c  push    rbx
0x140001f6e  push    rsi
0x140001f6f  push    rdi
0x140001f70  push    r14
0x140001f72  sub     rsp, 38h
0x140001f76  xor     esi, esi
0x140001f78  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFF85EE0h
0x140001f81  mov     rdi, rcx
0x140001f84  xor     eax, eax
0x140001f86  lea     r14d, [rsi+1]
0x140001f8a  lock cmpxchg [rcx+58h], r14d
0x140001f90  jmp     short loc_140001FDF
0x140001f92  mov     eax, [rdi+54h]
0x140001f95  cmp     esi, 0C8h
0x140001f9b  jnb     short loc_140002016
0x140001f9d  lea     r9, aSleepingWhileW; "Sleeping while waiting for buffer %d to"...
0x140001fa4  mov     [rsp+58h+var_38], eax
0x140001fa8  mov     r8d, 0E89h
0x140001fae  lea     rdx, aHbevtptransfer; "HbEvtpTransferBufferOwnershipToEtw"
0x140001fb5  mov     ecx, 3
0x140001fba  call    HbpTraceEvent
0x140001fbf  lea     r8, [rsp+58h+Interval]; Interval
0x140001fc4  xor     edx, edx; Alertable
0x140001fc6  xor     ecx, ecx; WaitMode
0x140001fc8  call    cs:__imp_KeDelayExecutionThread
0x140001fcf  nop     dword ptr [rax+rax+00h]
0x140001fd4  add     esi, r14d
0x140001fd7  xor     eax, eax
0x140001fd9  lock cmpxchg [rdi+58h], r14d
0x140001fdf  cmp     eax, r14d
0x140001fe2  jz      short loc_140001F92
0x140001fe4  mov     eax, [rdi+54h]
0x140001fe7  lea     r9, aBufferDIsNowOw; "Buffer %d is now owned by ETW"
0x140001fee  mov     r8d, 0E8Eh
0x140001ff4  mov     [rsp+58h+var_38], eax
0x140001ff8  lea     rdx, aHbevtptransfer; "HbEvtpTransferBufferOwnershipToEtw"
0x140001fff  mov     ecx, 3
0x140002004  call    HbpTraceEvent
0x140002009  xor     eax, eax
0x14000200b  add     rsp, 38h
0x14000200f  pop     r14
0x140002011  pop     rdi
0x140002012  pop     rsi
0x140002013  pop     rbx
0x140002014  retn
0x140002016  lea     r9, aTimeoutWaiting_0; "Timeout waiting for buffer %d to become"...
0x14000201d  mov     [rsp+58h+var_38], eax
0x140002021  mov     r8d, 0E86h
0x140002027  lea     rdx, aHbevtptransfer; "HbEvtpTransferBufferOwnershipToEtw"
0x14000202e  xor     ecx, ecx
0x140002030  call    HbpTraceEvent
0x140002035  mov     eax, 102h
0x14000203a  jmp     short loc_14000200B
```
