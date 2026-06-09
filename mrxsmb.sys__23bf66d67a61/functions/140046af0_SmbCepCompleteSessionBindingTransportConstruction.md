# SmbCepCompleteSessionBindingTransportConstruction

- ea: `0x140046af0`
- end: `0x140046c4d`
- name: `SmbCepCompleteSessionBindingTransportConstruction`
- size: `349`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400463a8`

## callees

- `0x140003480`
- `0x140021840`
- `0x1400377dc`
- `0x140045c60`
- `0x140045fa0`
- `0x140046af0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140046b87`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140046c16`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140046b87`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140046c16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046bf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046bf3`
- `rdbss!RxPostToWorkerThread` at `0x140046bba`
- `rdbss!RxPostToWorkerThread` at `0x140046bba`

## pseudocode

```c
void __fastcall SmbCepCompleteSessionBindingTransportConstruction(_QWORD *P, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  int v5; // esi
  struct _RX_WORK_QUEUE_ITEM_ *v6; // r13
  _BYTE *v7; // r14
  _QWORD *v8; // rbx
  __int64 v9; // rbp
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  KIRQL v15; // bl
  KIRQL OldIrql; // [rsp+80h] [rbp+8h]

  v3 = P[2];
  v5 = *((_DWORD *)P + 2);
  v6 = (struct _RX_WORK_QUEUE_ITEM_ *)P[3];
  v7 = (_BYTE *)P[4];
  v8 = *(_QWORD **)(v3 + 384);
  v9 = v8[3];
  OldIrql = SmbCeAcquireSpinLock(v9, a2, a3);
  if ( v7 && v5 < 0 && v8[72] && (*v7 & 1) != 0 )
    SmbCeUpdateFailureCountLite(v8, (__int64)v7, 0);
  Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck(v11, v10);
  v12 = *(_DWORD *)(v3 + 12);
  if ( v12 != 12 && v12 )
    v5 = -1073741309;
  *(_DWORD *)(v9 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 1920), OldIrql);
  if ( v5 )
  {
    if ( v5 != 259 )
    {
      if ( v7 )
      {
        v15 = SmbCeAcquireSpinLock(v9, v13, v14);
        SmbCeDecrementConnectionInProgressCountLite(v3, *(unsigned __int16 *)v7);
        ExFreePoolWithTag(v7, 0x6D53634Du);
        P[4] = 0;
        *(_DWORD *)(v9 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 1920), v15);
      }
      *((_DWORD *)P + 3) = *((_DWORD *)P + 3);
      P[5] = 0;
      *((_DWORD *)P + 2) = v5;
      SmbCeCompleteSessionBindingInitialization(P);
    }
  }
  else
  {
    *P = SmbCeCompleteSessionBindingInitialization;
    RxPostToWorkerThread((PRDBSS_DEVICE_OBJECT)v9, DelayedWorkQueue, v6 + 5, DoSubRdrSessionSetupWorker, P);
  }
}

```

## disassembly

```asm
0x140046af0  push    rbx
0x140046af2  push    rbp
0x140046af3  push    rsi
0x140046af4  push    rdi
0x140046af5  push    r12
0x140046af7  push    r13
0x140046af9  push    r14
0x140046afb  push    r15
0x140046afd  sub     rsp, 38h
0x140046b01  mov     r15, [rcx+10h]
0x140046b05  mov     rdi, rcx
0x140046b08  mov     esi, [rcx+8]
0x140046b0b  mov     r13, [rcx+18h]
0x140046b0f  mov     r14, [rcx+20h]
0x140046b13  mov     rbx, [r15+180h]
0x140046b1a  mov     rbp, [rbx+18h]
0x140046b1e  mov     rcx, rbp
0x140046b21  call    SmbCeAcquireSpinLock
0x140046b26  mov     [rsp+78h+OldIrql], al
0x140046b2d  test    r14, r14
0x140046b30  jz      short loc_140046B54
0x140046b32  test    esi, esi
0x140046b34  jns     short loc_140046B54
0x140046b36  cmp     qword ptr [rbx+240h], 0
0x140046b3e  jz      short loc_140046B54
0x140046b40  test    byte ptr [r14], 1
0x140046b44  jz      short loc_140046B54
0x140046b46  xor     r8d, r8d
0x140046b49  mov     rdx, r14
0x140046b4c  mov     rcx, rbx; BugCheckParameter2
0x140046b4f  call    SmbCeUpdateFailureCountLite
0x140046b54  call    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck
0x140046b59  mov     eax, [r15+0Ch]
0x140046b5d  cmp     eax, 0Ch
0x140046b60  jz      short loc_140046B6C
0x140046b62  test    eax, eax
0x140046b64  mov     ecx, 0C0000203h
0x140046b69  cmovnz  esi, ecx
0x140046b6c  mov     dl, [rsp+78h+OldIrql]; OldIrql
0x140046b73  lea     r12, [rbp+780h]
0x140046b7a  mov     rcx, r12; SpinLock
0x140046b7d  mov     dword ptr [rbp+930h], 0FFFFFFFFh
0x140046b87  call    cs:__imp_ExReleaseSpinLockExclusive
0x140046b8e  nop     dword ptr [rax+rax+00h]
0x140046b93  test    esi, esi
0x140046b95  jnz     short loc_140046BC8
0x140046b97  lea     rax, SmbCeCompleteSessionBindingInitialization
0x140046b9e  mov     [rsp+78h+pContext], rdi; pContext
0x140046ba3  lea     r8, [r13+0C8h]; pWorkQueueItem
0x140046baa  mov     [rdi], rax
0x140046bad  lea     r9, DoSubRdrSessionSetupWorker; Routine
0x140046bb4  mov     rcx, rbp; pMRxDeviceObject
0x140046bb7  lea     edx, [rsi+1]; WorkQueueType
0x140046bba  call    cs:__imp_RxPostToWorkerThread
0x140046bc1  nop     dword ptr [rax+rax+00h]
0x140046bc6  jmp     short loc_140046C3B
0x140046bc8  cmp     esi, 103h
0x140046bce  jz      short loc_140046C3B
0x140046bd0  test    r14, r14
0x140046bd3  jz      short loc_140046C22
0x140046bd5  mov     rcx, rbp
0x140046bd8  call    SmbCeAcquireSpinLock
0x140046bdd  movzx   edx, word ptr [r14]
0x140046be1  mov     rcx, r15
0x140046be4  mov     bl, al
0x140046be6  call    SmbCeDecrementConnectionInProgressCountLite
0x140046beb  mov     edx, 6D53634Dh; Tag
0x140046bf0  mov     rcx, r14; P
0x140046bf3  call    cs:__imp_ExFreePoolWithTag
0x140046bfa  nop     dword ptr [rax+rax+00h]
0x140046bff  mov     qword ptr [rdi+20h], 0
0x140046c07  mov     dl, bl; OldIrql
0x140046c09  mov     rcx, r12; SpinLock
0x140046c0c  mov     dword ptr [rbp+930h], 0FFFFFFFFh
0x140046c16  call    cs:__imp_ExReleaseSpinLockExclusive
0x140046c1d  nop     dword ptr [rax+rax+00h]
0x140046c22  mov     eax, [rdi+0Ch]
0x140046c25  mov     rcx, rdi; P
0x140046c28  mov     [rdi+0Ch], eax
0x140046c2b  mov     qword ptr [rdi+28h], 0
0x140046c33  mov     [rdi+8], esi
0x140046c36  call    SmbCeCompleteSessionBindingInitialization
0x140046c3b  add     rsp, 38h
0x140046c3f  pop     r15
0x140046c41  pop     r14
0x140046c43  pop     r13
0x140046c45  pop     r12
0x140046c47  pop     rdi
0x140046c48  pop     rsi
0x140046c49  pop     rbp
0x140046c4a  pop     rbx
0x140046c4b  retn
```
