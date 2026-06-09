# PcpCleanupFlow

- ea: `0x14000aca4`
- end: `0x14000adf0`
- name: `PcpCleanupFlow`
- size: `332`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140005578`
- `0x140009100`
- `0x14000a7f0`

## callees

- `0x14000aca4`
- `0x14000b09c`
- `0x14000bb5c`
- `0x14000bd90`
- `0x14000f874`
- `0x1400116ec`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000ad12`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000ad12`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000acd3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000acd3`

## pseudocode

```c
__int64 __fastcall PcpCleanupFlow(_QWORD *P)
{
  _QWORD *v2; // rax
  PVOID *v3; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+90h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.SystemArgument1, &LockHandle);
  while ( LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) )
    ;
  v2 = (_QWORD *)*P;
  if ( *(_QWORD **)(*P + 8LL) != P || (v3 = (PVOID *)P[1], *v3 != P) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = v3;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (P[77] & 1) != 0 )
    PcpDecrementHold();
  if ( PcgEventTraceEnabled )
    PcpEtwWriteFlowEvent((const EVENT_DESCRIPTOR *)QOS_EVENT_PACER_CLEANUP_FLOW, (__int64)P, 7u);
  PcpUninitializeFlow(P);
  PcpTraceActivityIdStop(P);
  return PcpFreeFlow(P);
}

```

## disassembly

```asm
0x14000aca4  mov     r11, rsp
0x14000aca7  mov     [r11+8], rbx
0x14000acab  mov     [r11+10h], rsi
0x14000acaf  push    rdi
0x14000acb0  sub     rsp, 0B0h
0x14000acb7  mov     rbx, rcx
0x14000acba  lea     rdx, [r11-28h]; LockHandle
0x14000acbe  xorps   xmm0, xmm0
0x14000acc1  lea     rcx, WPP_MAIN_CB.Dpc.SystemArgument1; SpinLock
0x14000acc8  xor     eax, eax
0x14000acca  movups  xmmword ptr [r11-28h], xmm0
0x14000accf  mov     [r11-18h], rax
0x14000acd3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000acda  nop     dword ptr [rax+rax+00h]
0x14000acdf  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2
0x14000ace5  test    eax, eax
0x14000ace7  jnz     short loc_14000ACDF
0x14000ace9  mov     rax, [rbx]
0x14000acec  cmp     [rax+8], rbx
0x14000acf0  jnz     loc_14000ADE9
0x14000acf6  mov     rcx, [rbx+8]
0x14000acfa  cmp     [rcx], rbx
0x14000acfd  jnz     loc_14000ADE9
0x14000ad03  mov     [rcx], rax
0x14000ad06  mov     [rax+8], rcx
0x14000ad0a  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14000ad12  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000ad19  nop     dword ptr [rax+rax+00h]
0x14000ad1e  mov     eax, [rbx+268h]
0x14000ad24  test    al, 1
0x14000ad26  jz      short loc_14000AD2D
0x14000ad28  call    PcpDecrementHold
0x14000ad2d  mov     eax, cs:PcgEventTraceEnabled
0x14000ad33  test    eax, eax
0x14000ad35  jz      loc_14000ADBB
0x14000ad3b  lea     r9, [rbx+8Ch]
0x14000ad42  mov     esi, 7
0x14000ad47  lea     rax, [r9+20h]
0x14000ad4b  lea     rcx, [r9+1Ch]
0x14000ad4f  lea     rdx, [r9+14h]
0x14000ad53  lea     edi, [rsi-3]
0x14000ad56  mov     [rsp+0B8h+var_38], rdi
0x14000ad5e  lea     r8, [r9+0Ch]
0x14000ad62  mov     [rsp+0B8h+var_40], rax
0x14000ad67  lea     r10, [r9+8]
0x14000ad6b  mov     [rsp+0B8h+var_48], rdi
0x14000ad70  lea     eax, [rsi+1]
0x14000ad73  mov     [rsp+0B8h+var_50], rcx
0x14000ad78  lea     r11, [r9+4]
0x14000ad7c  mov     [rsp+0B8h+var_58], rax
0x14000ad81  lea     rcx, QOS_EVENT_PACER_CLEANUP_FLOW
0x14000ad88  mov     [rsp+0B8h+var_60], rdx
0x14000ad8d  mov     rdx, rbx
0x14000ad90  mov     [rsp+0B8h+var_68], rax
0x14000ad95  mov     [rsp+0B8h+var_70], r8
0x14000ad9a  mov     r8d, esi
0x14000ad9d  mov     [rsp+0B8h+var_78], rdi
0x14000ada2  mov     [rsp+0B8h+var_80], r10
0x14000ada7  mov     [rsp+0B8h+var_88], rdi
0x14000adac  mov     [rsp+0B8h+var_90], r11
0x14000adb1  mov     [rsp+0B8h+var_98], rdi
0x14000adb6  call    PcpEtwWriteFlowEvent
0x14000adbb  mov     rcx, rbx
0x14000adbe  call    PcpUninitializeFlow
0x14000adc3  mov     rcx, rbx
0x14000adc6  call    PcpTraceActivityIdStop
0x14000adcb  mov     rcx, rbx; P
0x14000adce  call    PcpFreeFlow
0x14000add3  lea     r11, [rsp+0B8h+var_8]
0x14000addb  mov     rbx, [r11+10h]
0x14000addf  mov     rsi, [r11+18h]
0x14000ade3  mov     rsp, r11
0x14000ade6  pop     rdi
0x14000ade7  retn
0x14000ade9  mov     ecx, 3
0x14000adee  int     29h; Win8: RtlFailFast(ecx)
```
