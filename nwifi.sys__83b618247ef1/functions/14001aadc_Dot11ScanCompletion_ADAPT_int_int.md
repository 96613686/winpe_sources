# Dot11ScanCompletion(_ADAPT *,int,int)

- ea: `0x14001aadc`
- end: `0x14001ac75`
- name: `?Dot11ScanCompletion@@YAXPEAU_ADAPT@@HH@Z`
- size: `409`
- prototype: `void __fastcall(struct _ADAPT *, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003dc90`
- `0x140053ed0`
- `0x1400540d0`

## callees

- `0x14001aadc`
- `0x140020f20`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ac0d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ac0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac1e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001abc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001abc1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ab4f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ab4f`

## pseudocode

```c
void __fastcall Dot11ScanCompletion(struct _ADAPT *a1, unsigned int a2)
{
  KIRQL v4; // al
  struct DOT11_WIFI_SCAN_REQUEST *pOutstandingInNic; // rbx
  _LIST_ENTRY *p_QueuedScanRequestList; // r8
  struct _ADAPT *Flink; // rcx
  __int64 v8; // rax
  __int128 v9; // [rsp+30h] [rbp-10h] BYREF

  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, 1, a2);
  }
  *((_QWORD *)&v9 + 1) = &v9;
  *(_QWORD *)&v9 = &v9;
  v4 = KeAcquireSpinLockRaiseToDpc(&a1->ScanModule.Lock.SpinLock);
  pOutstandingInNic = a1->ScanModule.pOutstandingInNic;
  p_QueuedScanRequestList = &a1->ScanModule.QueuedScanRequestList;
  a1->ScanModule.Lock.OldIrql = v4;
  a1->ScanModule.pOutstandingInNic = 0;
  a1->ScanModule.uNumQueuedScanRequests = 0;
  Flink = (struct _ADAPT *)a1->ScanModule.QueuedScanRequestList.Flink;
  if ( Flink != (struct _ADAPT *)&a1->ScanModule.QueuedScanRequestList )
  {
    **((_QWORD **)&v9 + 1) = Flink;
    p_QueuedScanRequestList->Flink->Blink = (_LIST_ENTRY *)*((_QWORD *)&v9 + 1);
    a1->ScanModule.QueuedScanRequestList.Blink->Flink = (_LIST_ENTRY *)&v9;
    *((_QWORD *)&v9 + 1) = a1->ScanModule.QueuedScanRequestList.Blink;
    p_QueuedScanRequestList->Flink = p_QueuedScanRequestList;
    a1->ScanModule.QueuedScanRequestList.Blink = &a1->ScanModule.QueuedScanRequestList;
  }
  KeReleaseSpinLock(&a1->ScanModule.Lock.SpinLock, a1->ScanModule.Lock.OldIrql);
  if ( pOutstandingInNic )
  {
    while ( 1 )
    {
      if ( pOutstandingInNic )
      {
        (*((void (__fastcall **)(struct _ADAPT *, _QWORD, _QWORD, _QWORD, _QWORD))pOutstandingInNic + 3))(
          a1,
          a2,
          *((_QWORD *)pOutstandingInNic + 4),
          *((_QWORD *)pOutstandingInNic + 5),
          *((_QWORD *)pOutstandingInNic + 6));
        if ( *((_QWORD *)pOutstandingInNic - 2) )
          ExFreeToNPagedLookasideList(
            *((PNPAGED_LOOKASIDE_LIST *)pOutstandingInNic - 2),
            (char *)pOutstandingInNic - 16);
        else
          ExFreePoolWithTag((char *)pOutstandingInNic - 16, *((_DWORD *)pOutstandingInNic - 2));
      }
      pOutstandingInNic = (struct DOT11_WIFI_SCAN_REQUEST *)v9;
      if ( (__int128 *)v9 == &v9 )
        break;
      if ( *(__int128 **)(v9 + 8) != &v9 || (v8 = *(_QWORD *)v9, *(_QWORD *)(*(_QWORD *)v9 + 8LL) != (_QWORD)v9) )
        __fastfail(3u);
      *(_QWORD *)&v9 = *(_QWORD *)v9;
      *(_QWORD *)(v8 + 8) = &v9;
    }
    _InterlockedDecrement((volatile signed __int32 *)&a1->ScanModule.uNumOutstandingScannings);
  }
}

```

## disassembly

```asm
0x14001aadc  push    rbp
0x14001aade  push    rbx
0x14001aadf  push    rsi
0x14001aae0  push    rdi
0x14001aae1  push    r14
0x14001aae3  mov     rbp, rsp
0x14001aae6  sub     rsp, 40h
0x14001aaea  xorps   xmm0, xmm0
0x14001aaed  mov     r14d, edx
0x14001aaf0  movups  [rbp+var_10], xmm0
0x14001aaf4  mov     rdi, rcx
0x14001aaf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aafe  lea     rax, WPP_GLOBAL_Control
0x14001ab05  cmp     rcx, rax
0x14001ab08  jz      short loc_14001AB35
0x14001ab0a  cmp     byte ptr [rcx+29h], 3
0x14001ab0e  jb      short loc_14001AB35
0x14001ab10  mov     eax, [rcx+2Ch]
0x14001ab13  test    al, 10h
0x14001ab15  jz      short loc_14001AB35
0x14001ab17  mov     rcx, [rcx+18h]
0x14001ab1b  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14001ab22  mov     edx, 0Dh
0x14001ab27  mov     dword ptr [rsp+40h+var_20], r14d
0x14001ab2c  lea     r9d, [rdx-0Ch]
0x14001ab30  call    WPP_SF_Dd
0x14001ab35  lea     rax, [rbp+var_10]
0x14001ab39  mov     qword ptr [rbp+var_10+8], rax
0x14001ab3d  lea     rsi, [rdi+90h]
0x14001ab44  lea     rax, [rbp+var_10]
0x14001ab48  mov     rcx, rsi; SpinLock
0x14001ab4b  mov     qword ptr [rbp+var_10], rax
0x14001ab4f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ab56  nop     dword ptr [rax+rax+00h]
0x14001ab5b  mov     rbx, [rdi+0A8h]
0x14001ab62  lea     r8, [rdi+0B8h]
0x14001ab69  mov     [rdi+98h], al
0x14001ab6f  mov     qword ptr [rdi+0A8h], 0
0x14001ab7a  mov     dword ptr [rdi+0B0h], 0
0x14001ab84  mov     rcx, [r8]
0x14001ab87  cmp     rcx, r8
0x14001ab8a  jz      short loc_14001ABB8
0x14001ab8c  mov     rax, qword ptr [rbp+var_10+8]
0x14001ab90  mov     [rax], rcx
0x14001ab93  lea     rcx, [rbp+var_10]
0x14001ab97  mov     rax, qword ptr [rbp+var_10+8]
0x14001ab9b  mov     rdx, [r8]
0x14001ab9e  mov     [rdx+8], rax
0x14001aba2  mov     rax, [r8+8]
0x14001aba6  mov     [rax], rcx
0x14001aba9  mov     rax, [r8+8]
0x14001abad  mov     qword ptr [rbp+var_10+8], rax
0x14001abb1  mov     [r8], r8
0x14001abb4  mov     [r8+8], r8
0x14001abb8  mov     dl, [rdi+98h]; NewIrql
0x14001abbe  mov     rcx, rsi; SpinLock
0x14001abc1  call    cs:__imp_KeReleaseSpinLock
0x14001abc8  nop     dword ptr [rax+rax+00h]
0x14001abcd  test    rbx, rbx
0x14001abd0  jz      loc_14001AC69
0x14001abd6  test    rbx, rbx
0x14001abd9  jz      short loc_14001AC2A
0x14001abdb  mov     rcx, [rbx+30h]
0x14001abdf  mov     edx, r14d
0x14001abe2  mov     rax, [rbx+18h]
0x14001abe6  mov     r9, [rbx+28h]
0x14001abea  mov     r8, [rbx+20h]
0x14001abee  mov     [rsp+40h+var_20], rcx
0x14001abf3  mov     rcx, rdi
0x14001abf6  call    _guard_dispatch_icall
0x14001abfb  lea     rcx, [rbx-10h]; P
0x14001abff  mov     rax, [rcx]
0x14001ac02  test    rax, rax
0x14001ac05  jz      short loc_14001AC1B
0x14001ac07  mov     rdx, rcx; Entry
0x14001ac0a  mov     rcx, rax; Lookaside
0x14001ac0d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001ac14  nop     dword ptr [rax+rax+00h]
0x14001ac19  jmp     short loc_14001AC2A
0x14001ac1b  mov     edx, [rcx+8]; Tag
0x14001ac1e  call    cs:__imp_ExFreePoolWithTag
0x14001ac25  nop     dword ptr [rax+rax+00h]
0x14001ac2a  mov     rbx, qword ptr [rbp+var_10]
0x14001ac2e  lea     rax, [rbp+var_10]
0x14001ac32  cmp     rbx, rax
0x14001ac35  jz      short loc_14001AC62
0x14001ac37  lea     rax, [rbp+var_10]
0x14001ac3b  cmp     [rbx+8], rax
0x14001ac3f  jnz     short loc_14001AC5B
0x14001ac41  mov     rax, [rbx]
0x14001ac44  cmp     [rax+8], rbx
0x14001ac48  jnz     short loc_14001AC5B
0x14001ac4a  lea     rcx, [rbp+var_10]
0x14001ac4e  mov     qword ptr [rbp+var_10], rax
0x14001ac52  mov     [rax+8], rcx
0x14001ac56  jmp     loc_14001ABD6
0x14001ac5b  mov     ecx, 3
0x14001ac60  int     29h; Win8: RtlFailFast(ecx)
0x14001ac62  lock dec dword ptr [rdi+0A0h]
0x14001ac69  add     rsp, 40h
0x14001ac6d  pop     r14
0x14001ac6f  pop     rdi
0x14001ac70  pop     rsi
0x14001ac71  pop     rbx
0x14001ac72  pop     rbp
0x14001ac73  retn
```
