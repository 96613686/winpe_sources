# SmbCeResumeSuspendedExchangesLite

- ea: `0x140005740`
- end: `0x140005b17`
- name: `SmbCeResumeSuspendedExchangesLite`
- size: `983`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140004990`
- `0x140004b90`
- `0x140004f30`
- `0x1400050b0`
- `0x140005320`
- `0x14003d124`

## callees

- `0x140004360`
- `0x140005740`
- `0x1400093a0`
- `0x14000b110`
- `0x140037fa4`
- `0x140038068`
- `0x1400383d0`
- `0x140039fd8`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005899`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005902`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400059f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005899`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005902`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400059f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005978`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005a2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005a55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005978`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005a2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005a55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a40`
- `rdbss!RxPostToWorkerThread` at `0x140005ac1`
- `rdbss!RxPostToWorkerThread` at `0x140005ac1`

## pseudocode

```c
bool __fastcall SmbCeResumeSuspendedExchangesLite(__int128 *a1, int a2, int a3, int a4, __int64 a5, __int64 a6)
{
  int v7; // r15d
  void (__fastcall *v8)(unsigned __int64, __int64 *, __int64 *); // r12
  int v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rax
  __int128 *v12; // rbx
  unsigned __int64 pContext; // rbx
  char *v14; // rdi
  struct _RDBSS_DEVICE_OBJECT *v15; // r13
  int v16; // eax
  __int64 v17; // rsi
  __int64 v18; // r14
  KSPIN_LOCK *v19; // rbp
  signed __int32 v20; // r8d
  ULONG_PTR v21; // rcx
  KIRQL v22; // al
  char **v23; // r8
  void **v24; // rdx
  __int128 v26; // [rsp+30h] [rbp-58h] BYREF

  v7 = 0;
  v8 = 0;
  v9 = a2;
  v26 = 0;
  if ( a6 )
  {
    v10 = *(unsigned __int16 *)(a6 + 2);
    if ( (_WORD)v10 )
      v11 = a6 + v10;
    else
      v11 = 0;
    v8 = *(void (__fastcall **)(unsigned __int64, __int64 *, __int64 *))(v11 + 272);
    *(_QWORD *)(v11 + 272) = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
      (unsigned int)a5,
      a2);
    v9 = a2;
  }
  if ( *(__int128 **)a1 == a1 )
  {
    v12 = &v26;
    *((_QWORD *)&v26 + 1) = &v26;
    *(_QWORD *)&v26 = &v26;
  }
  else
  {
    v26 = *a1;
    *(_QWORD *)(v26 + 8) = &v26;
    **((_QWORD **)&v26 + 1) = &v26;
    *((_QWORD *)a1 + 1) = a1;
    *(_QWORD *)a1 = a1;
    v12 = (__int128 *)v26;
  }
  while ( v12 != &v26 )
  {
    pContext = (unsigned __int64)(v12 - 8);
    LODWORD(a6) = v9;
    v14 = *(char **)(pContext + 56);
    v15 = *(struct _RDBSS_DEVICE_OBJECT **)(*(_QWORD *)(pContext + 72) + 24LL);
    v16 = v7 + 1;
    if ( (*(_DWORD *)(pContext + 68) & 0x20) == 0 )
      v16 = v7;
    v7 = v16;
    if ( v14 )
    {
      v17 = (__int64)(v14 + 4);
      _InterlockedIncrement((volatile signed __int32 *)v14 + 1);
      v18 = (__int64)(v14 + 8);
      v14[16] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v14 + 1);
      v19 = (KSPIN_LOCK *)(pContext + 24);
    }
    else
    {
      v20 = _InterlockedIncrement((volatile signed __int32 *)(pContext + 4));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
          pContext,
          v20 - 1,
          v20);
      }
      v19 = (KSPIN_LOCK *)(pContext + 24);
      *(_BYTE *)(pContext + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(pContext + 24));
      v17 = 4;
      v18 = 8;
    }
    if ( v8 )
      v8(pContext, &a6, &a5);
    SmbCepPrepareExchangeForResumeLite(pContext, a6, a3, a4, a5);
    if ( v14 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)v18, v14[16]);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17, 0xFFFFFFFF) == 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_2ecbbf7dc68f37694aaad8a30b991413_Traceguids, v14);
        }
        v21 = *((_QWORD *)v14 + 12);
        if ( v21 )
        {
          SmbCeDereferenceBindingObject(v21);
          *((_QWORD *)v14 + 12) = 0;
        }
        *(_WORD *)v14 = -1;
        v22 = KeAcquireSpinLockRaiseToDpc(&SmbCeCompoundingKeyListLock);
        v23 = (char **)*((_QWORD *)v14 + 4);
        if ( v23[1] != v14 + 32 || (v24 = (void **)*((_QWORD *)v14 + 5), *v24 != v14 + 32) )
          __fastfail(3u);
        *v24 = v23;
        v23[1] = (char *)v24;
        KeReleaseSpinLock(&SmbCeCompoundingKeyListLock, v22);
        ExFreePoolWithTag(v14, 0x6D53794Bu);
      }
    }
    else
    {
      KeReleaseSpinLock(v19, *(_BYTE *)(pContext + 32));
      SmbCeDereferenceExchange(pContext);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_d39beb3e593835eae73483c3886eb046_Traceguids, pContext, v14);
    }
    RxPostToWorkerThread(
      v15,
      NormalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(pContext + 240),
      SmbCepResumeExchangeWorker,
      (PVOID)pContext);
    v9 = a2;
    v12 = (__int128 *)v26;
  }
  return v7 != 0;
}

```

## disassembly

```asm
0x140005740  mov     [rsp+arg_18], r9d
0x140005745  mov     [rsp+arg_10], r8d
0x14000574a  mov     [rsp+arg_8], edx
0x14000574e  push    rbx
0x14000574f  push    r12
0x140005751  push    r15
0x140005753  sub     rsp, 70h
0x140005757  mov     rbx, rcx
0x14000575a  xor     r15d, r15d
0x14000575d  mov     rcx, [rsp+88h+arg_28]
0x140005765  xor     r12d, r12d
0x140005768  xorps   xmm0, xmm0
0x14000576b  mov     r8d, edx
0x14000576e  movups  [rsp+88h+var_58], xmm0
0x140005773  test    rcx, rcx
0x140005776  jz      short loc_140005796
0x140005778  movzx   eax, word ptr [rcx+2]
0x14000577c  test    ax, ax
0x14000577f  jnz     short loc_140005785
0x140005781  xor     eax, eax
0x140005783  jmp     short loc_140005788
0x140005785  add     rax, rcx
0x140005788  mov     r12, [rax+110h]
0x14000578f  mov     [rax+110h], r15
0x140005796  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000579d  lea     rdx, WPP_GLOBAL_Control
0x1400057a4  cmp     rcx, rdx
0x1400057a7  jz      short loc_1400057E7
0x1400057a9  mov     eax, [rcx+2Ch]
0x1400057ac  test    al, 10h
0x1400057ae  jz      short loc_1400057E7
0x1400057b0  cmp     byte ptr [rcx+29h], 4
0x1400057b4  jb      short loc_1400057E7
0x1400057b6  mov     r9d, dword ptr [rsp+88h+arg_20]
0x1400057be  mov     edx, 24h ; '$'
0x1400057c3  mov     rcx, [rcx+18h]
0x1400057c7  mov     dword ptr [rsp+88h+pContext], r8d
0x1400057cc  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x1400057d3  call    WPP_SF_Dd
0x1400057d8  mov     r8d, [rsp+88h+arg_8]
0x1400057e0  lea     rdx, WPP_GLOBAL_Control
0x1400057e7  cmp     [rbx], rbx
0x1400057ea  jnz     short loc_140005802
0x1400057ec  lea     rax, [rsp+88h+var_58]
0x1400057f1  lea     rbx, [rsp+88h+var_58]
0x1400057f6  mov     qword ptr [rsp+88h+var_58+8], rax
0x1400057fb  mov     qword ptr [rsp+88h+var_58], rbx
0x140005800  jmp     short loc_140005835
0x140005802  mov     rcx, [rbx]
0x140005805  mov     rax, [rbx+8]
0x140005809  mov     qword ptr [rsp+88h+var_58+8], rax
0x14000580e  lea     rax, [rsp+88h+var_58]
0x140005813  mov     qword ptr [rsp+88h+var_58], rcx
0x140005818  mov     [rcx+8], rax
0x14000581c  lea     rcx, [rsp+88h+var_58]
0x140005821  mov     rax, qword ptr [rsp+88h+var_58+8]
0x140005826  mov     [rax], rcx
0x140005829  mov     [rbx+8], rbx
0x14000582d  mov     [rbx], rbx
0x140005830  mov     rbx, qword ptr [rsp+88h+var_58]
0x140005835  mov     [rsp+88h+var_20], rbp
0x14000583a  mov     [rsp+88h+var_28], rsi
0x14000583f  mov     [rsp+88h+var_30], rdi
0x140005844  mov     [rsp+88h+var_38], r13
0x140005849  mov     [rsp+88h+var_40], r14
0x14000584e  xchg    ax, ax
0x140005850  lea     rax, [rsp+88h+var_58]
0x140005855  cmp     rbx, rax
0x140005858  jz      loc_140005AED
0x14000585e  add     rbx, 0FFFFFFFFFFFFFF80h
0x140005862  mov     dword ptr [rsp+88h+arg_28], r8d
0x14000586a  mov     rax, [rbx+48h]
0x14000586e  mov     rdi, [rbx+38h]
0x140005872  mov     r13, [rax+18h]
0x140005876  mov     eax, [rbx+44h]
0x140005879  test    al, 20h
0x14000587b  lea     eax, [r15+1]
0x14000587f  cmovz   eax, r15d
0x140005883  mov     r15d, eax
0x140005886  test    rdi, rdi
0x140005889  jz      short loc_1400058AE
0x14000588b  lea     rsi, [rdi+4]
0x14000588f  lock inc dword ptr [rsi]
0x140005892  lea     r14, [rdi+8]
0x140005896  mov     rcx, r14; SpinLock
0x140005899  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400058a0  nop     dword ptr [rax+rax+00h]
0x1400058a5  mov     [rdi+10h], al
0x1400058a8  lea     rbp, [rbx+18h]
0x1400058ac  jmp     short loc_14000591C
0x1400058ae  mov     r8d, 1
0x1400058b4  lock xadd [rbx+4], r8d
0x1400058ba  inc     r8d
0x1400058bd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400058c4  cmp     rcx, rdx
0x1400058c7  jz      short loc_1400058FB
0x1400058c9  mov     eax, [rcx+2Ch]
0x1400058cc  test    al, 10h
0x1400058ce  jz      short loc_1400058FB
0x1400058d0  cmp     byte ptr [rcx+29h], 4
0x1400058d4  jb      short loc_1400058FB
0x1400058d6  mov     rcx, [rcx+18h]
0x1400058da  lea     eax, [r8-1]
0x1400058de  mov     [rsp+88h+var_60], r8d
0x1400058e3  mov     edx, 21h ; '!'
0x1400058e8  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x1400058ef  mov     dword ptr [rsp+88h+pContext], eax
0x1400058f3  mov     r9, rbx
0x1400058f6  call    WPP_SF_qDD
0x1400058fb  lea     rbp, [rbx+18h]
0x1400058ff  mov     rcx, rbp; SpinLock
0x140005902  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005909  nop     dword ptr [rax+rax+00h]
0x14000590e  mov     [rbx+20h], al
0x140005911  mov     esi, 4
0x140005916  mov     r14d, 8
0x14000591c  test    r12, r12
0x14000591f  jz      short loc_14000593C
0x140005921  lea     r8, [rsp+88h+arg_20]
0x140005929  mov     rcx, rbx
0x14000592c  lea     rdx, [rsp+88h+arg_28]
0x140005934  mov     rax, r12
0x140005937  call    _guard_dispatch_icall
0x14000593c  mov     rax, [rsp+88h+arg_20]
0x140005944  mov     rcx, rbx
0x140005947  mov     r9d, [rsp+88h+arg_18]
0x14000594f  mov     r8d, [rsp+88h+arg_10]
0x140005957  mov     edx, dword ptr [rsp+88h+arg_28]
0x14000595e  mov     [rsp+88h+pContext], rax
0x140005963  call    SmbCepPrepareExchangeForResumeLite
0x140005968  test    rdi, rdi
0x14000596b  jz      loc_140005A4E
0x140005971  movzx   edx, byte ptr [rdi+10h]; NewIrql
0x140005975  mov     rcx, r14; SpinLock
0x140005978  call    cs:__imp_KeReleaseSpinLock
0x14000597f  nop     dword ptr [rax+rax+00h]
0x140005984  mov     eax, 0FFFFFFFFh
0x140005989  lock xadd [rsi], eax
0x14000598d  cmp     eax, 1
0x140005990  jnz     loc_140005A69
0x140005996  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000599d  lea     rsi, WPP_GLOBAL_Control
0x1400059a4  cmp     rcx, rsi
0x1400059a7  jz      short loc_1400059CE
0x1400059a9  mov     eax, [rcx+2Ch]
0x1400059ac  test    al, 20h
0x1400059ae  jz      short loc_1400059CE
0x1400059b0  cmp     byte ptr [rcx+29h], 2
0x1400059b4  jb      short loc_1400059CE
0x1400059b6  mov     rcx, [rcx+18h]
0x1400059ba  lea     r8, WPP_2ecbbf7dc68f37694aaad8a30b991413_Traceguids
0x1400059c1  mov     edx, 0Ch
0x1400059c6  mov     r9, rdi
0x1400059c9  call    WPP_SF_q
0x1400059ce  mov     rcx, [rdi+60h]; BugCheckParameter2
0x1400059d2  test    rcx, rcx
0x1400059d5  jz      short loc_1400059E4
0x1400059d7  call    SmbCeDereferenceBindingObject
0x1400059dc  mov     qword ptr [rdi+60h], 0
0x1400059e4  lea     rcx, SmbCeCompoundingKeyListLock; SpinLock
0x1400059eb  mov     word ptr [rdi], 0FFFFh
0x1400059f0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400059f7  nop     dword ptr [rax+rax+00h]
0x1400059fc  mov     r8, [rdi+20h]
0x140005a00  lea     rcx, [rdi+20h]
0x140005a04  cmp     [r8+8], rcx
0x140005a08  jnz     loc_140005AE6
0x140005a0e  mov     rdx, [rdi+28h]
0x140005a12  cmp     [rdx], rcx
0x140005a15  jnz     loc_140005AE6
0x140005a1b  mov     [rdx], r8
0x140005a1e  lea     rcx, SmbCeCompoundingKeyListLock; SpinLock
0x140005a25  mov     [r8+8], rdx
0x140005a29  movzx   edx, al; NewIrql
0x140005a2c  call    cs:__imp_KeReleaseSpinLock
0x140005a33  nop     dword ptr [rax+rax+00h]
0x140005a38  mov     edx, 6D53794Bh; Tag
0x140005a3d  mov     rcx, rdi; P
0x140005a40  call    cs:__imp_ExFreePoolWithTag
0x140005a47  nop     dword ptr [rax+rax+00h]
0x140005a4c  jmp     short loc_140005A70
0x140005a4e  movzx   edx, byte ptr [rbx+20h]; NewIrql
0x140005a52  mov     rcx, rbp; SpinLock
0x140005a55  call    cs:__imp_KeReleaseSpinLock
0x140005a5c  nop     dword ptr [rax+rax+00h]
0x140005a61  mov     rcx, rbx; pContext
0x140005a64  call    SmbCeDereferenceExchange
0x140005a69  lea     rsi, WPP_GLOBAL_Control
0x140005a70  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140005a77  cmp     rcx, rsi
0x140005a7a  jz      short loc_140005AA6
0x140005a7c  mov     eax, [rcx+2Ch]
0x140005a7f  test    al, 10h
0x140005a81  jz      short loc_140005AA6
0x140005a83  cmp     byte ptr [rcx+29h], 4
0x140005a87  jb      short loc_140005AA6
0x140005a89  mov     rcx, [rcx+18h]
0x140005a8d  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x140005a94  mov     edx, 25h ; '%'
0x140005a99  mov     [rsp+88h+pContext], rdi
0x140005a9e  mov     r9, rbx
0x140005aa1  call    WPP_SF_qq
0x140005aa6  lea     r8, [rbx+0F0h]; pWorkQueueItem
0x140005aad  mov     [rsp+88h+pContext], rbx; pContext
0x140005ab2  lea     r9, SmbCepResumeExchangeWorker; Routine
0x140005ab9  mov     edx, 3; WorkQueueType
0x140005abe  mov     rcx, r13; pMRxDeviceObject
0x140005ac1  call    cs:__imp_RxPostToWorkerThread
0x140005ac8  nop     dword ptr [rax+rax+00h]
0x140005acd  mov     r8d, [rsp+88h+arg_8]
0x140005ad5  lea     rdx, WPP_GLOBAL_Control
0x140005adc  mov     rbx, qword ptr [rsp+88h+var_58]
0x140005ae1  jmp     loc_140005850
0x140005ae6  mov     ecx, 3
0x140005aeb  int     29h; Win8: RtlFailFast(ecx)
0x140005aed  mov     r14, [rsp+88h+var_40]
0x140005af2  test    r15d, r15d
0x140005af5  mov     r13, [rsp+88h+var_38]
0x140005afa  mov     rdi, [rsp+88h+var_30]
0x140005aff  setnz   al
0x140005b02  mov     rsi, [rsp+88h+var_28]
0x140005b07  mov     rbp, [rsp+88h+var_20]
0x140005b0c  add     rsp, 70h
0x140005b10  pop     r15
0x140005b12  pop     r12
0x140005b14  pop     rbx
0x140005b15  retn
```
