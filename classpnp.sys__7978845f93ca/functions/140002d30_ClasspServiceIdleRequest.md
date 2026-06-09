# ClasspServiceIdleRequest

- ea: `0x140002d30`
- end: `0x140002fa3`
- name: `ClasspServiceIdleRequest`
- size: `627`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140001e70`
- `0x1400024b0`
- `0x14001e2f0`

## callees

- `0x140002d30`
- `0x140002fb0`
- `0x14001feac`
- `0x140029ff4`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002d6a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002d6a`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002e02`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002f05`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002e02`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002f05`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140002e41`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140002e41`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f38`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f38`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f92`
- `ntoskrnl!IoRecordIoAttribution` at `0x140002f20`
- `ntoskrnl!IoRecordIoAttribution` at `0x140002f20`
- `ntoskrnl!KeCancelTimer` at `0x140002de9`
- `ntoskrnl!KeCancelTimer` at `0x140002de9`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140002e8c`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140002e8c`

## pseudocode

```c
void __fastcall ClasspServiceIdleRequest(__int64 a1, char a2)
{
  __int64 v2; // rbx
  KSPIN_LOCK *v5; // rbp
  KIRQL v6; // al
  _QWORD *v7; // rcx
  KIRQL v8; // r15
  _QWORD *v9; // rdi
  __int64 v10; // rax
  int v11; // edx
  int v12; // ecx
  unsigned __int8 *v13; // rax
  unsigned __int64 QpcTimeStamp[2]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v15; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v16[2]; // [rsp+60h] [rbp-48h] BYREF

  v2 = *(_QWORD *)(a1 + 1144);
  v5 = (KSPIN_LOCK *)(v2 + 3672);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 3672));
  v7 = (_QWORD *)(v2 + 3680);
  v8 = v6;
  v9 = *(_QWORD **)(v2 + 3680);
  if ( v9 == (_QWORD *)(v2 + 3680) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 3672), v6);
    return;
  }
  if ( (_QWORD *)v9[1] != v7 || (v10 = *v9, *(_QWORD **)(*v9 + 8LL) != v9) )
    __fastfail(3u);
  *v7 = v10;
  *(_QWORD *)(v10 + 8) = v7;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 3864), 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_dee7c8ca8cd5355db7ab7a1f63361bba_Traceguids);
    }
    KeCancelTimer((PKTIMER)(v2 + 3728));
  }
  QpcTimeStamp[0] = 0;
  *(_QWORD *)(v2 + 3712) = KeQueryUnbiasedInterruptTimePrecise(QpcTimeStamp);
  v9[1] = v9;
  *v9 = v9;
  if ( v9 != (_QWORD *)168
    && ClassPnPETWEnabled
    && (*(_OWORD *)QpcTimeStamp = 0,
        IoGetActivityIdIrp(v9 - 21, QpcTimeStamp),
        (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) != 0) )
  {
    McTemplateK0qdud_EtwWriteTransfer(v12, v11, (unsigned int)QpcTimeStamp, *(_DWORD *)(a1 + 588), 1, 5);
    KeReleaseSpinLock(v5, v8);
  }
  else
  {
    KeReleaseSpinLock(v5, v8);
    if ( v9 == (_QWORD *)168 )
      return;
  }
  QpcTimeStamp[0] = 0;
  v15 = 0;
  *(_OWORD *)v16 = 0;
  if ( (int)IoGetIoAttributionHandle(v9 - 21, QpcTimeStamp) >= 0 )
  {
    v13 = (unsigned __int8 *)v9[2];
    v15 = 0;
    LODWORD(v15) = 1;
    *(_OWORD *)v16 = 0;
    DWORD1(v15) = *v13 | 0x200;
    v16[1] = KeQueryUnbiasedInterruptTimePrecise(&v16[1]);
    IoRecordIoAttribution(QpcTimeStamp[0], &v15);
  }
  ServiceTransferRequest(*(_QWORD *)(a1 + 8), (__int64)(v9 - 21), a2);
}

```

## disassembly

```asm
0x140002d30  mov     [rsp+arg_18], rbx
0x140002d35  push    rbp
0x140002d36  push    rsi
0x140002d37  push    rdi
0x140002d38  push    r14
0x140002d3a  push    r15
0x140002d3c  sub     rsp, 80h
0x140002d43  mov     rax, cs:__security_cookie
0x140002d4a  xor     rax, rsp
0x140002d4d  mov     [rsp+0A8h+var_38], rax
0x140002d52  mov     rbx, [rcx+478h]
0x140002d59  mov     rsi, rcx
0x140002d5c  movzx   r14d, dl
0x140002d60  lea     rbp, [rbx+0E58h]
0x140002d67  mov     rcx, rbp; SpinLock
0x140002d6a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002d71  nop     dword ptr [rax+rax+00h]
0x140002d76  lea     rcx, [rbx+0E60h]
0x140002d7d  movzx   r15d, al
0x140002d81  mov     rdi, [rcx]
0x140002d84  cmp     rdi, rcx
0x140002d87  jz      loc_140002F31
0x140002d8d  cmp     [rdi+8], rcx
0x140002d91  jz      short loc_140002D9A
0x140002d93  mov     ecx, 3
0x140002d98  int     29h; Win8: RtlFailFast(ecx)
0x140002d9a  mov     rax, [rdi]
0x140002d9d  cmp     [rax+8], rdi
0x140002da1  jnz     short loc_140002D93
0x140002da3  mov     [rcx], rax
0x140002da6  mov     [rax+8], rcx
0x140002daa  mov     eax, 0FFFFFFFFh
0x140002daf  mov     [rsp+0A8h+arg_10], r12
0x140002db7  lock xadd [rbx+0F18h], eax
0x140002dbf  cmp     eax, 1
0x140002dc2  jnz     short loc_140002DF5
0x140002dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140002dcb  lea     rax, WPP_GLOBAL_Control
0x140002dd2  cmp     rcx, rax
0x140002dd5  jz      short loc_140002DE2
0x140002dd7  mov     eax, [rcx+2Ch]
0x140002dda  test    al, al
0x140002ddc  js      loc_140002F49
0x140002de2  lea     rcx, [rbx+0E90h]; PKTIMER
0x140002de9  call    cs:__imp_KeCancelTimer
0x140002df0  nop     dword ptr [rax+rax+00h]
0x140002df5  xor     r12d, r12d
0x140002df8  lea     rcx, [rsp+0A8h+QpcTimeStamp]; QpcTimeStamp
0x140002dfd  mov     [rsp+0A8h+QpcTimeStamp], r12
0x140002e02  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140002e09  nop     dword ptr [rax+rax+00h]
0x140002e0e  mov     [rbx+0E80h], rax
0x140002e15  lea     rbx, [rdi-0A8h]
0x140002e1c  mov     [rdi+8], rdi
0x140002e20  mov     [rdi], rdi
0x140002e23  test    rbx, rbx
0x140002e26  jz      short loc_140002E5A
0x140002e28  cmp     cs:ClassPnPETWEnabled, r12b
0x140002e2f  jz      short loc_140002E5A
0x140002e31  xorps   xmm0, xmm0
0x140002e34  lea     rdx, [rsp+0A8h+QpcTimeStamp]
0x140002e39  mov     rcx, rbx
0x140002e3c  movups  xmmword ptr [rsp+0A8h+QpcTimeStamp], xmm0
0x140002e41  call    cs:__imp_IoGetActivityIdIrp
0x140002e48  nop     dword ptr [rax+rax+00h]
0x140002e4d  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 40h
0x140002e54  jnz     loc_140002F6D
0x140002e5a  movzx   edx, r15b; NewIrql
0x140002e5e  mov     rcx, rbp; SpinLock
0x140002e61  call    cs:__imp_KeReleaseSpinLock
0x140002e68  nop     dword ptr [rax+rax+00h]
0x140002e6d  test    rbx, rbx
0x140002e70  jz      short loc_140002EAC
0x140002e72  xorps   xmm0, xmm0
0x140002e75  mov     [rsp+0A8h+QpcTimeStamp], r12
0x140002e7a  lea     rdx, [rsp+0A8h+QpcTimeStamp]
0x140002e7f  mov     rcx, rbx
0x140002e82  movups  [rsp+0A8h+var_58], xmm0
0x140002e87  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x140002e8c  call    cs:__imp_IoGetIoAttributionHandle
0x140002e93  nop     dword ptr [rax+rax+00h]
0x140002e98  test    eax, eax
0x140002e9a  jns     short loc_140002ED9
0x140002e9c  mov     rcx, [rsi+8]
0x140002ea0  movzx   r8d, r14b
0x140002ea4  mov     rdx, rbx
0x140002ea7  call    ServiceTransferRequest
0x140002eac  mov     r12, [rsp+0A8h+arg_10]
0x140002eb4  mov     rcx, [rsp+0A8h+var_38]
0x140002eb9  xor     rcx, rsp; StackCookie
0x140002ebc  call    __security_check_cookie
0x140002ec1  mov     rbx, [rsp+0A8h+arg_18]
0x140002ec9  add     rsp, 80h
0x140002ed0  pop     r15
0x140002ed2  pop     r14
0x140002ed4  pop     rdi
0x140002ed5  pop     rsi
0x140002ed6  pop     rbp
0x140002ed7  retn
0x140002ed9  mov     rax, [rbx+0B8h]
0x140002ee0  lea     rcx, [rsp+0A8h+var_48+8]; QpcTimeStamp
0x140002ee5  xorps   xmm0, xmm0
0x140002ee8  movups  [rsp+0A8h+var_58], xmm0
0x140002eed  mov     dword ptr [rsp+0A8h+var_58], 1
0x140002ef5  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x140002efa  movzx   edx, byte ptr [rax]
0x140002efd  bts     edx, 9
0x140002f01  mov     dword ptr [rsp+0A8h+var_58+4], edx
0x140002f05  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140002f0c  nop     dword ptr [rax+rax+00h]
0x140002f11  mov     rcx, [rsp+0A8h+QpcTimeStamp]
0x140002f16  lea     rdx, [rsp+0A8h+var_58]
0x140002f1b  mov     [rsp+0A8h+var_48+8], rax
0x140002f20  call    cs:__imp_IoRecordIoAttribution
0x140002f27  nop     dword ptr [rax+rax+00h]
0x140002f2c  jmp     loc_140002E9C
0x140002f31  movzx   edx, r15b; NewIrql
0x140002f35  mov     rcx, rbp; SpinLock
0x140002f38  call    cs:__imp_KeReleaseSpinLock
0x140002f3f  nop     dword ptr [rax+rax+00h]
0x140002f44  jmp     loc_140002EB4
0x140002f49  cmp     byte ptr [rcx+29h], 4
0x140002f4d  jb      loc_140002DE2
0x140002f53  mov     rcx, [rcx+18h]
0x140002f57  lea     r8, WPP_dee7c8ca8cd5355db7ab7a1f63361bba_Traceguids
0x140002f5e  mov     edx, 0Ch
0x140002f63  call    WPP_SF_
0x140002f68  jmp     loc_140002DE2
0x140002f6d  mov     r9d, [rsi+24Ch]
0x140002f74  lea     r8, [rsp+0A8h+QpcTimeStamp]
0x140002f79  mov     [rsp+0A8h+var_80], 5
0x140002f7e  mov     [rsp+0A8h+var_88], 1
0x140002f86  call    McTemplateK0qdud_EtwWriteTransfer
0x140002f8b  movzx   edx, r15b; NewIrql
0x140002f8f  mov     rcx, rbp; SpinLock
0x140002f92  call    cs:__imp_KeReleaseSpinLock
0x140002f99  nop     dword ptr [rax+rax+00h]
0x140002f9e  jmp     loc_140002E72
```
