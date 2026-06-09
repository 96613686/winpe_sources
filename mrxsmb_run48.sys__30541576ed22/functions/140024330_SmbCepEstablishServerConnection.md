# SmbCepEstablishServerConnection

- ea: `0x140024330`
- end: `0x140024671`
- name: `SmbCepEstablishServerConnection`
- size: `833`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140024310`
- `0x140092b0c`

## callees

- `0x1400050b0`
- `0x140013540`
- `0x140014400`
- `0x14001e7c0`
- `0x140021130`
- `0x1400221e0`
- `0x140024330`
- `0x140026d60`
- `0x14002cc00`
- `0x14004374c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400244e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400244e2`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400243ad`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140024477`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002451d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400243ad`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140024477`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002451d`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140024370`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400243bc`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140024370`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400243bc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002437f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400243cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002437f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400243cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024626`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024626`
- `rdbss!RxFinalizeSecurityContext` at `0x140024539`
- `rdbss!RxFinalizeSecurityContext` at `0x140024539`
- `rdbss!RxReferenceCredential` at `0x140024577`
- `rdbss!RxReferenceCredential` at `0x140024577`

## pseudocode

```c
__int64 __fastcall SmbCepEstablishServerConnection(
        ULONG_PTR BugCheckParameter2,
        void (__fastcall *a2)(int *P, __int64, __int64),
        __int64 a3)
{
  __int64 v3; // rbp
  void (__fastcall **v5)(int *, __int64, __int64); // r14
  KIRQL v6; // bl
  KIRQL v7; // r12
  _QWORD *v8; // rdi
  __int64 v9; // rbx
  ULONG_PTR v10; // rbx
  _QWORD *v11; // rcx
  _QWORD *v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rbx
  unsigned int v15; // edi
  void (__fastcall **Pool2)(int *, __int64, __int64); // rax
  __int64 v17; // rcx
  ULONG_PTR v18; // rcx
  void (__fastcall *v19)(int *, __int64, __int64); // rbx
  __int64 v23; // [rsp+A8h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(BugCheckParameter2 + 24);
  v23 = 0;
  v5 = 0;
  v6 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920));
  *(_DWORD *)(v3 + 2352) = (unsigned int)PsGetCurrentThreadId();
  _InterlockedExchange((volatile __int32 *)(BugCheckParameter2 + 12), 3);
  *(_DWORD *)(v3 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920), v6);
  v7 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920));
  v8 = (_QWORD *)(BugCheckParameter2 + 528);
  *(_DWORD *)(v3 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v9 = *(_QWORD *)(BugCheckParameter2 + 528);
  if ( v9 == BugCheckParameter2 + 528 || (v10 = v9 - 392) == 0 )
  {
LABEL_9:
    if ( (_QWORD *)*v8 == v8 || (v10 = *v8 - 392LL, *v8 == 392) )
    {
LABEL_15:
      *(_DWORD *)(v3 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920), v7);
      goto LABEL_16;
    }
    while ( *(int *)(v10 + 12) > 5 )
    {
      v12 = *(_QWORD **)(v10 + 392);
      v10 = 0;
      if ( v12 != v8 )
        v10 = (ULONG_PTR)(v12 - 49);
      if ( !v10 )
        goto LABEL_15;
    }
  }
  else
  {
    while ( *(_DWORD *)(v10 + 12) != 3 )
    {
      v11 = *(_QWORD **)(v10 + 392);
      v10 = 0;
      if ( v11 != v8 )
        v10 = (ULONG_PTR)(v11 - 49);
      if ( !v10 )
        goto LABEL_9;
    }
  }
  SmbCeReferenceSessionEntry(v10);
  *(_DWORD *)(v3 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920), v7);
  RxFinalizeSecurityContext(BugCheckParameter2 + 224);
  v17 = *(_QWORD *)(v10 + 128);
  *(_OWORD *)(BugCheckParameter2 + 224) = *(_OWORD *)(v10 + 96);
  *(_OWORD *)(BugCheckParameter2 + 240) = *(_OWORD *)(v10 + 112);
  *(_QWORD *)(BugCheckParameter2 + 256) = *(_QWORD *)(v10 + 128);
  if ( v17 )
    RxReferenceCredential();
  SmbCeDereferenceSessionEntryEx(v10);
LABEL_16:
  SmbCeComputeEffectivePorts(BugCheckParameter2, v3, *(_QWORD *)(BugCheckParameter2 + 872));
  v13 = SmbCeConstructBindingObject(&v23, *(_QWORD *)(BugCheckParameter2 + 24));
  v14 = v23;
  v15 = v13;
  if ( v13 )
    goto LABEL_23;
  *(_QWORD *)(v23 + 384) = BugCheckParameter2;
  SmbCeReferenceServerEntry(BugCheckParameter2);
  *(_QWORD *)(v14 + 432) = BugCheckParameter2;
  _InterlockedExchange((volatile __int32 *)(v14 + 12), 3);
  Pool2 = (void (__fastcall **)(int *, __int64, __int64))ExAllocatePool2(64, 48, 1834181187);
  v5 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = SmbCeCompleteServerEntryInitialization;
    Pool2[2] = a2;
    Pool2[3] = (void (__fastcall *)(int *, __int64, __int64))BugCheckParameter2;
    Pool2[4] = (void (__fastcall *)(int *, __int64, __int64))v14;
    v15 = SmbCeEstablishNegotiatedConnection(
            BugCheckParameter2,
            BugCheckParameter2,
            v14,
            (int)BugCheckParameter2 + 640,
            0,
            a3,
            (__int64)Pool2);
LABEL_23:
    if ( v15 == 259 )
      return v15;
    goto LABEL_24;
  }
  v15 = -1073741670;
LABEL_24:
  if ( v14 )
  {
    v18 = *(_QWORD *)(v14 + 432);
    if ( v18 )
    {
      SmbCeDereferenceServerEntryEx(v18);
      *(_QWORD *)(v14 + 432) = 0;
    }
    SmbMmFreeObjectPool(v14);
  }
  if ( v5 )
  {
    v19 = v5[1];
    ExFreePoolWithTag(v5, 0x6D536243u);
  }
  else
  {
    v19 = (void (__fastcall *)(int *, __int64, __int64))v15;
  }
  if ( v15 )
    SmbCeCompleteObjectConstruction(BugCheckParameter2, v19);
  return v15;
}

```

## disassembly

```asm
0x140024330  mov     [rsp+arg_10], r8
0x140024335  mov     [rsp+arg_8], rdx
0x14002433a  push    rbx
0x14002433b  push    rbp
0x14002433c  push    rsi
0x14002433d  push    rdi
0x14002433e  push    r12
0x140024340  push    r13
0x140024342  push    r14
0x140024344  push    r15
0x140024346  sub     rsp, 48h
0x14002434a  mov     rbp, [rcx+18h]
0x14002434e  xor     eax, eax
0x140024350  mov     rsi, rcx
0x140024353  mov     [rsp+88h+arg_18], rax
0x14002435b  mov     r14d, eax
0x14002435e  mov     [rsp+88h+arg_0], rax
0x140024366  lea     r15, [rbp+780h]
0x14002436d  mov     rcx, r15; SpinLock
0x140024370  call    cs:__imp_ExAcquireSpinLockExclusive
0x140024377  nop     dword ptr [rax+rax+00h]
0x14002437c  movzx   ebx, al
0x14002437f  call    cs:__imp_PsGetCurrentThreadId
0x140024386  nop     dword ptr [rax+rax+00h]
0x14002438b  mov     [rbp+930h], eax
0x140024391  mov     r13d, 3
0x140024397  mov     ecx, r13d
0x14002439a  movzx   edx, bl; OldIrql
0x14002439d  xchg    ecx, [rsi+0Ch]
0x1400243a0  mov     rcx, r15; SpinLock
0x1400243a3  mov     dword ptr [rbp+930h], 0FFFFFFFFh
0x1400243ad  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400243b4  nop     dword ptr [rax+rax+00h]
0x1400243b9  mov     rcx, r15; SpinLock
0x1400243bc  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400243c3  nop     dword ptr [rax+rax+00h]
0x1400243c8  movzx   r12d, al
0x1400243cc  call    cs:__imp_PsGetCurrentThreadId
0x1400243d3  nop     dword ptr [rax+rax+00h]
0x1400243d8  lea     rdi, [rsi+210h]
0x1400243df  mov     [rbp+930h], eax
0x1400243e5  mov     rbx, [rdi]
0x1400243e8  cmp     rbx, rdi
0x1400243eb  jz      short loc_14002442B
0x1400243ed  add     rbx, 0FFFFFFFFFFFFFE78h
0x1400243f4  jz      short loc_14002442B
0x1400243f6  cmp     [rbx+0Ch], r13d
0x1400243fa  jz      short loc_14002441A
0x1400243fc  mov     rcx, [rbx+188h]
0x140024403  xor     ebx, ebx
0x140024405  cmp     rcx, rdi
0x140024408  lea     rax, [rcx-188h]
0x14002440f  cmovnz  rbx, rax
0x140024413  test    rbx, rbx
0x140024416  jnz     short loc_1400243F6
0x140024418  jmp     short loc_14002442B
0x14002441a  mov     rcx, rbx
0x14002441d  call    SmbCeReferenceSessionEntry
0x140024422  test    rbx, rbx
0x140024425  jnz     loc_14002450C
0x14002442b  mov     rbx, [rdi]
0x14002442e  cmp     rbx, rdi
0x140024431  jz      short loc_140024466
0x140024433  add     rbx, 0FFFFFFFFFFFFFE78h
0x14002443a  jz      short loc_140024466
0x14002443c  nop     dword ptr [rax+00h]
0x140024440  cmp     dword ptr [rbx+0Ch], 5
0x140024444  jle     loc_140024504
0x14002444a  mov     rcx, [rbx+188h]
0x140024451  xor     ebx, ebx
0x140024453  cmp     rcx, rdi
0x140024456  lea     rax, [rcx-188h]
0x14002445d  cmovnz  rbx, rax
0x140024461  test    rbx, rbx
0x140024464  jnz     short loc_140024440
0x140024466  movzx   edx, r12b; OldIrql
0x14002446a  mov     dword ptr [rbp+930h], 0FFFFFFFFh
0x140024474  mov     rcx, r15; SpinLock
0x140024477  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002447e  nop     dword ptr [rax+rax+00h]
0x140024483  mov     r8, [rsi+368h]
0x14002448a  mov     rdx, rbp
0x14002448d  mov     rcx, rsi
0x140024490  call    SmbCeComputeEffectivePorts
0x140024495  mov     rdx, [rsi+18h]
0x140024499  lea     rcx, [rsp+88h+arg_18]
0x1400244a1  call    SmbCeConstructBindingObject
0x1400244a6  mov     rbx, [rsp+88h+arg_18]
0x1400244ae  mov     edi, eax
0x1400244b0  test    eax, eax
0x1400244b2  jnz     loc_1400245E2
0x1400244b8  mov     rcx, rsi; BugCheckParameter2
0x1400244bb  mov     [rbx+180h], rsi
0x1400244c2  call    SmbCeReferenceServerEntry
0x1400244c7  mov     [rbx+1B0h], rsi
0x1400244ce  mov     edx, 30h ; '0'
0x1400244d3  xchg    r13d, [rbx+0Ch]
0x1400244d7  mov     ecx, 40h ; '@'
0x1400244dc  mov     r8d, 6D536243h
0x1400244e2  call    cs:__imp_ExAllocatePool2
0x1400244e9  nop     dword ptr [rax+rax+00h]
0x1400244ee  mov     r14, rax
0x1400244f1  test    rax, rax
0x1400244f4  jnz     loc_140024592
0x1400244fa  mov     edi, 0C000009Ah
0x1400244ff  jmp     loc_1400245EA
0x140024504  mov     rcx, rbx
0x140024507  call    SmbCeReferenceSessionEntry
0x14002450c  movzx   edx, r12b; OldIrql
0x140024510  mov     dword ptr [rbp+930h], 0FFFFFFFFh
0x14002451a  mov     rcx, r15; SpinLock
0x14002451d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140024524  nop     dword ptr [rax+rax+00h]
0x140024529  test    rbx, rbx
0x14002452c  jz      loc_140024483
0x140024532  lea     rcx, [rsi+0E0h]
0x140024539  call    cs:__imp_RxFinalizeSecurityContext
0x140024540  nop     dword ptr [rax+rax+00h]
0x140024545  movups  xmm0, xmmword ptr [rbx+60h]
0x140024549  mov     rcx, [rbx+80h]
0x140024550  movups  xmmword ptr [rsi+0E0h], xmm0
0x140024557  movups  xmm1, xmmword ptr [rbx+70h]
0x14002455b  movups  xmmword ptr [rsi+0F0h], xmm1
0x140024562  movsd   xmm0, qword ptr [rbx+80h]
0x14002456a  movsd   qword ptr [rsi+100h], xmm0
0x140024572  test    rcx, rcx
0x140024575  jz      short loc_140024583
0x140024577  call    cs:__imp_RxReferenceCredential
0x14002457e  nop     dword ptr [rax+rax+00h]
0x140024583  xor     edx, edx
0x140024585  mov     rcx, rbx; BugCheckParameter2
0x140024588  call    SmbCeDereferenceSessionEntryEx
0x14002458d  jmp     loc_140024483
0x140024592  lea     rax, SmbCeCompleteServerEntryInitialization
0x140024599  mov     [rsp+88h+var_58], r14
0x14002459e  mov     [r14], rax
0x1400245a1  lea     r9, [rsi+280h]
0x1400245a8  mov     rax, [rsp+88h+arg_8]
0x1400245b0  mov     r8, rbx
0x1400245b3  mov     [r14+10h], rax
0x1400245b7  mov     rdx, rsi
0x1400245ba  mov     rax, [rsp+88h+arg_10]
0x1400245c2  mov     rcx, rsi
0x1400245c5  mov     [rsp+88h+var_60], rax
0x1400245ca  mov     [rsp+88h+var_68], 0
0x1400245d3  mov     [r14+18h], rsi
0x1400245d7  mov     [r14+20h], rbx
0x1400245db  call    SmbCeEstablishNegotiatedConnection
0x1400245e0  mov     edi, eax
0x1400245e2  cmp     edi, 103h
0x1400245e8  jz      short loc_14002465D
0x1400245ea  test    rbx, rbx
0x1400245ed  jz      short loc_140024615
0x1400245ef  mov     rcx, [rbx+1B0h]; BugCheckParameter2
0x1400245f6  test    rcx, rcx
0x1400245f9  jz      short loc_14002460D
0x1400245fb  xor     edx, edx
0x1400245fd  call    SmbCeDereferenceServerEntryEx
0x140024602  mov     qword ptr [rbx+1B0h], 0
0x14002460d  mov     rcx, rbx
0x140024610  call    SmbMmFreeObjectPool
0x140024615  test    r14, r14
0x140024618  jz      short loc_140024634
0x14002461a  mov     rbx, [r14+8]
0x14002461e  mov     edx, 6D536243h; Tag
0x140024623  mov     rcx, r14; P
0x140024626  call    cs:__imp_ExFreePoolWithTag
0x14002462d  nop     dword ptr [rax+rax+00h]
0x140024632  jmp     short loc_14002464E
0x140024634  mov     dword ptr [rsp+88h+arg_0], edi
0x14002463b  mov     dword ptr [rsp+88h+arg_0+4], 0
0x140024646  mov     rbx, [rsp+88h+arg_0]
0x14002464e  test    edi, edi
0x140024650  jz      short loc_14002465D
0x140024652  mov     rdx, rbx
0x140024655  mov     rcx, rsi
0x140024658  call    SmbCeCompleteObjectConstruction
0x14002465d  mov     eax, edi
0x14002465f  add     rsp, 48h
0x140024663  pop     r15
0x140024665  pop     r14
0x140024667  pop     r13
0x140024669  pop     r12
0x14002466b  pop     rdi
0x14002466c  pop     rsi
0x14002466d  pop     rbp
0x14002466e  pop     rbx
0x14002466f  retn
```
