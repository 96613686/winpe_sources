# SmbCeCancelExchange

- ea: `0x14000ea90`
- end: `0x14000f192`
- name: `SmbCeCancelExchange`
- size: `1794`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x140006680`
- `0x140009360`
- `0x1400093a0`
- `0x140009fc0`
- `0x14000c030`
- `0x14000c6a0`
- `0x14000df60`
- `0x14000e4c0`
- `0x14000ea90`
- `0x140017930`
- `0x14001a480`
- `0x140028960`
- `0x140038068`
- `0x1400383d0`
- `0x140048498`
- `0x14004a7d0`
- `0x140059dc0`
- `0x140059ea0`
- `0x14005a200`
- `0x14008d220`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000eae8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000eae8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000ebe0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000ebe0`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x14000eb7a`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x14000eb99`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x14000eb7a`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x14000eb99`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000ec9f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000ec9f`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000eeee`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000eeee`
- `ntoskrnl!MmUnlockPages` at `0x14000f01a`
- `ntoskrnl!MmUnlockPages` at `0x14000f01a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eb0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f181`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eb0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f181`
- `rdbss!RxFreeMdl` at `0x14000f063`
- `rdbss!RxFreeMdl` at `0x14000f063`
- `rdbss!RxAllocateMdl2` at `0x14000ee82`
- `rdbss!RxAllocateMdl2` at `0x14000ee82`

## pseudocode

```c
__int64 __fastcall SmbCeCancelExchange(__int64 a1)
{
  KIRQL v2; // al
  KIRQL v3; // r14
  unsigned __int64 v4; // rbx
  unsigned int v5; // r13d
  __int64 v6; // r15
  unsigned int v7; // r13d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int64 v11; // rsi
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // r14d
  unsigned int v16; // esi
  _QWORD *v17; // r14
  _QWORD *v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // r14
  struct _MDL *Mdl2; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // r10
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  int v29; // [rsp+28h] [rbp-1E0h]
  ULONG SendLength; // [rsp+40h] [rbp-1C8h] BYREF
  __int64 v31; // [rsp+48h] [rbp-1C0h]
  PMDL MemoryDescriptorList; // [rsp+50h] [rbp-1B8h]
  _QWORD *v33; // [rsp+58h] [rbp-1B0h]
  LARGE_INTEGER Interval; // [rsp+60h] [rbp-1A8h] BYREF
  __int64 v35; // [rsp+70h] [rbp-198h]
  __int64 v36; // [rsp+78h] [rbp-190h]
  __int64 v37; // [rsp+80h] [rbp-188h]
  __int64 v38; // [rsp+88h] [rbp-180h]
  __int64 v39; // [rsp+90h] [rbp-178h]
  __int64 v40; // [rsp+98h] [rbp-170h]
  volatile signed __int32 *v41; // [rsp+A0h] [rbp-168h]
  volatile signed __int32 *v42; // [rsp+A8h] [rbp-160h]
  _QWORD v43[14]; // [rsp+B0h] [rbp-158h] BYREF
  PVOID pContext[2]; // [rsp+120h] [rbp-E8h] BYREF
  __int128 v45; // [rsp+130h] [rbp-D8h]
  __int128 v46; // [rsp+140h] [rbp-C8h]
  _BYTE v47[128]; // [rsp+150h] [rbp-B8h] BYREF

  memset(v47, 0, sizeof(v47));
  SendLength = 0;
  Interval.QuadPart = 0;
  while ( 1 )
  {
    v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 224));
    v3 = v2;
    v4 = *(_QWORD *)(a1 + 208);
    if ( !v4 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 224), v2);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_2ed4b0d8e3883b7ea50b1283a39c615b_Traceguids, a1);
      }
      return (unsigned int)-1073741823;
    }
    v37 = *(_QWORD *)(a1 + 208);
    v6 = *(_QWORD *)(v4 + 56);
    v39 = v6;
    if ( !v6 )
      break;
    if ( KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v6 + 8)) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 4));
      goto LABEL_13;
    }
LABEL_88:
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 224), v3);
  }
  if ( !KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 24)) )
    goto LABEL_88;
  SmbCeReferenceExchange(v4);
LABEL_13:
  v7 = 0;
  *(_QWORD *)(a1 + 208) = 0;
  v41 = (volatile signed __int32 *)(v4 + 68);
  _InterlockedOr((volatile signed __int32 *)(v4 + 68), 0x100u);
  _InterlockedAnd((volatile signed __int32 *)(v4 + 68), 0xFFFFFDFF);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 224));
  if ( v6 )
    *(_BYTE *)(v6 + 16) = v3;
  else
    *(_BYTE *)(v4 + 32) = v3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_2ed4b0d8e3883b7ea50b1283a39c615b_Traceguids, v4, a1);
  }
  v42 = (volatile signed __int32 *)(v4 + 36);
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 36));
  SmbCeReferenceExchange(v4);
  v35 = *(_QWORD *)(v4 + 72);
  v38 = v35;
  v36 = *(_QWORD *)(v4 + 80);
  v40 = v36;
  Interval.QuadPart = -10000;
  do
  {
    if ( *(_DWORD *)(v4 + 36) == 1 )
      break;
    if ( v6 )
      SmbCeReleaseCompoundingKeyLock(v6);
    else
      SmbCeReleaseExchangeLock((PVOID)v4);
    KeDelayExecutionThread(0, 0, &Interval);
    Interval.QuadPart *= 2LL;
    if ( v6 )
      SmbCeAcquireCompoundingKeyLock(v6, v8, v9, v10);
    else
      SmbCeAcquireExchangeLock(v4);
    ++v7;
  }
  while ( v7 < 0xA );
  v11 = v4;
  v33 = (_QWORD *)(v4 + 160);
  v12 = *(_QWORD **)(v4 + 160);
  v5 = 0;
  if ( v6 )
  {
    v13 = v12 - 1;
    if ( v12 == v33 )
      v13 = 0;
    if ( v13 )
    {
      if ( *((_BYTE *)v13 + 84) )
      {
        if ( !*((_BYTE *)v13 + 85) )
        {
          *(_OWORD *)pContext = 0;
          v45 = 0;
          v46 = 0;
          v14 = SmbCepAbortCompoundedExchangesLite(v6, 0x10C0000120LL, pContext);
          v15 = 0;
          if ( v14 )
          {
            v16 = v14;
            do
              SmbCepCompleteExchangeLiteEx((char *)pContext[v15++], 0);
            while ( v15 < v16 );
            v11 = v4;
          }
        }
      }
    }
  }
  else
  {
    v17 = v12 - 1;
    if ( v12 == v33 )
      v17 = 0;
    if ( v17 )
    {
      v18 = v33;
      do
      {
        if ( *((_BYTE *)v17 + 84) && !*((_BYTE *)v17 + 85) )
        {
          MemoryDescriptorList = (PMDL)0x10C0000120LL;
          SmbCseAbortBufferContext(*(PVOID *)(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 392LL) + 512LL));
          v18 = v33;
        }
        v19 = (_QWORD *)v17[1];
        v17 = 0;
        if ( v19 != v18 )
          v17 = v19 - 1;
      }
      while ( v17 );
    }
  }
  v20 = *v33 - 8LL;
  if ( (_QWORD *)*v33 == v33 )
    v20 = 0;
  while ( 1 )
  {
    v31 = v20;
    if ( !v20 )
      break;
    if ( *(_BYTE *)(v20 + 85) && (*(_DWORD *)(v20 + 4) & 3) != 0 )
    {
      SendLength = 128;
      (*(void (__fastcall **)(__int64, _BYTE *, ULONG *))(*(_QWORD *)(v35 + 56) + 864LL))(v20, v47, &SendLength);
      if ( v6 )
        SmbCeReleaseCompoundingKeyLock(v6);
      else
        SmbCeReleaseExchangeLock((PVOID)v4);
      Mdl2 = (struct _MDL *)RxAllocateMdl2(v47, SendLength, 0, 0, 0);
      MemoryDescriptorList = Mdl2;
      if ( Mdl2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_2ed4b0d8e3883b7ea50b1283a39c615b_Traceguids,
            v4,
            v20,
            SendLength);
          Mdl2 = MemoryDescriptorList;
        }
        v5 = 0;
        MmProbeAndLockPages(Mdl2, 0, IoModifyAccess);
        *(_DWORD *)(v20 + 872) = 0x10000000;
        if ( (unsigned __int8)ExchangeRequiresEncryption(v4) )
        {
          if ( *(_DWORD *)(v25 + 320) != 4 || (LODWORD(v31) = 0x10000000, !*(_BYTE *)(v25 + 604)) )
          {
            *(_DWORD *)(v20 + 872) = 1342177280;
            LODWORD(v31) = 1342177280;
          }
          memset(v43, 0, 0x68u);
          v26 = *(_QWORD *)(v11 + 96);
          v43[0] = *(_QWORD *)(v26 + 528);
          v43[1] = *(_QWORD *)(v36 + 440);
          VctSend(*(PRXCE_VC *)(v26 + 392), v31, MemoryDescriptorList, SendLength, v43, v29, 0);
        }
        else
        {
          VctSend((PRXCE_VC)v25, 0x10000000u, MemoryDescriptorList, SendLength, 0, v29, 0);
        }
        MmUnlockPages(MemoryDescriptorList);
        RxFreeMdl(MemoryDescriptorList);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_2ed4b0d8e3883b7ea50b1283a39c615b_Traceguids, v4, v20);
      }
      if ( v6 )
        SmbCeAcquireCompoundingKeyLock(v6, v22, v23, v24);
      else
        SmbCeAcquireExchangeLock(v4);
    }
    v27 = *(_QWORD **)(v20 + 8);
    v20 = 0;
    if ( v27 != v33 )
      v20 = (__int64)(v27 - 1);
  }
  if ( (*(_DWORD *)(v4 + 68) & 0x40) != 0 )
  {
    _InterlockedAnd(v41, 0xFFFFFFBF);
    SmbCeSetExchangeExpiryTimeEx(v4, 0, 0, 0);
  }
  if ( _InterlockedExchangeAdd(v42, 0xFFFFFFFF) == 1
    && (unsigned __int8)SmbCepCheckExchangeForDeferredAbortOrIfFinalizable(v4) )
  {
    SmbCepCompleteExchangeLiteEx((char *)v4, 0);
  }
  SmbCeDereferenceExchange(v4);
  if ( v6 )
    SmbCeReleaseCompoundingKeyLock(v6);
  else
    SmbCeReleaseExchangeLock((PVOID)v4);
  return v5;
}

```

## disassembly

```asm
0x14000ea90  mov     [rsp+arg_8], rbx
0x14000ea95  mov     [rsp+arg_10], rsi
0x14000ea9a  push    rdi
0x14000ea9b  push    r12
0x14000ea9d  push    r13
0x14000ea9f  push    r14
0x14000eaa1  push    r15
0x14000eaa3  sub     rsp, 1E0h
0x14000eaaa  mov     rax, cs:__security_cookie
0x14000eab1  xor     rax, rsp
0x14000eab4  mov     [rsp+208h+var_38], rax
0x14000eabc  mov     rsi, rcx
0x14000eabf  xor     edx, edx; Val
0x14000eac1  mov     r8d, 80h; Size
0x14000eac7  lea     rcx, [rsp+208h+var_B8]; void *
0x14000eacf  call    memset
0x14000ead4  xor     r12d, r12d
0x14000ead7  mov     [rsp+208h+SendLength], r12d
0x14000eadc  mov     qword ptr [rsp+208h+Interval], r12
0x14000eae1  lea     rcx, [rsi+0E0h]; SpinLock
0x14000eae8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000eaef  nop     dword ptr [rax+rax+00h]
0x14000eaf4  movzx   r14d, al
0x14000eaf8  mov     rbx, [rsi+0D0h]
0x14000eaff  test    rbx, rbx
0x14000eb02  jnz     short loc_14000EB5D
0x14000eb04  movzx   edx, al; NewIrql
0x14000eb07  lea     rcx, [rsi+0E0h]; SpinLock
0x14000eb0e  call    cs:__imp_KeReleaseSpinLock
0x14000eb15  nop     dword ptr [rax+rax+00h]
0x14000eb1a  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x14000eb21  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb28  cmp     rcx, rdi
0x14000eb2b  jz      short loc_14000EB52
0x14000eb2d  mov     eax, [rcx+2Ch]
0x14000eb30  test    al, 1
0x14000eb32  jz      short loc_14000EB52
0x14000eb34  cmp     byte ptr [rcx+29h], 1
0x14000eb38  jb      short loc_14000EB52
0x14000eb3a  mov     edx, 0Ch
0x14000eb3f  mov     r9, rsi
0x14000eb42  lea     r8, WPP_2ed4b0d8e3883b7ea50b1283a39c615b_Traceguids
0x14000eb49  mov     rcx, [rcx+18h]
0x14000eb4d  call    WPP_SF_q
0x14000eb52  mov     r13d, 0C0000001h
0x14000eb58  jmp     loc_14000F145
0x14000eb5d  mov     [rsp+208h+var_188], rbx
0x14000eb65  mov     r15, [rbx+38h]
0x14000eb69  mov     [rsp+208h+var_178], r15
0x14000eb71  test    r15, r15
0x14000eb74  jz      short loc_14000EB95
0x14000eb76  lea     rcx, [r15+8]; SpinLock
0x14000eb7a  call    cs:__imp_KeTryToAcquireSpinLockAtDpcLevel
0x14000eb81  nop     dword ptr [rax+rax+00h]
0x14000eb86  test    al, al
0x14000eb88  jz      loc_14000F176
0x14000eb8e  lock inc dword ptr [r15+4]
0x14000eb93  jmp     short loc_14000EBB5
0x14000eb95  lea     rcx, [rbx+18h]; SpinLock
0x14000eb99  call    cs:__imp_KeTryToAcquireSpinLockAtDpcLevel
0x14000eba0  nop     dword ptr [rax+rax+00h]
0x14000eba5  test    al, al
0x14000eba7  jz      loc_14000F176
0x14000ebad  mov     rcx, rbx
0x14000ebb0  call    SmbCeReferenceExchange
0x14000ebb5  mov     r13d, r12d
0x14000ebb8  mov     [rsi+0D0h], r12
0x14000ebbf  lea     rax, [rbx+44h]
0x14000ebc3  mov     [rsp+208h+var_168], rax
0x14000ebcb  lock or dword ptr [rax], 100h
0x14000ebd2  lock and dword ptr [rax], 0FFFFFDFFh
0x14000ebd9  lea     rcx, [rsi+0E0h]; SpinLock
0x14000ebe0  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000ebe7  nop     dword ptr [rax+rax+00h]
0x14000ebec  test    r15, r15
0x14000ebef  jz      short loc_14000EBF7
0x14000ebf1  mov     [r15+10h], r14b
0x14000ebf5  jmp     short loc_14000EBFB
0x14000ebf7  mov     [rbx+20h], r14b
0x14000ebfb  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ec02  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec09  cmp     rcx, rdi
0x14000ec0c  jz      short loc_14000EC38
0x14000ec0e  mov     eax, [rcx+2Ch]
0x14000ec11  test    al, 10h
0x14000ec13  jz      short loc_14000EC38
0x14000ec15  cmp     byte ptr [rcx+29h], 2
0x14000ec19  jb      short loc_14000EC38
0x14000ec1b  mov     edx, 0Dh
0x14000ec20  mov     [rsp+208h+var_1E8], rsi
0x14000ec25  mov     r9, rbx
0x14000ec28  lea     r8, WPP_2ed4b0d8e3883b7ea50b1283a39c615b_Traceguids
0x14000ec2f  mov     rcx, [rcx+18h]
0x14000ec33  call    WPP_SF_qq
0x14000ec38  lea     rsi, [rbx+24h]
0x14000ec3c  mov     [rsp+208h+var_160], rsi
0x14000ec44  lock inc dword ptr [rsi]
0x14000ec47  mov     rcx, rbx
0x14000ec4a  call    SmbCeReferenceExchange
0x14000ec4f  mov     rax, [rbx+48h]
0x14000ec53  mov     [rsp+208h+var_198], rax
0x14000ec58  mov     [rsp+208h+var_180], rax
0x14000ec60  mov     rax, [rbx+50h]
0x14000ec64  mov     [rsp+208h+var_190], rax
0x14000ec69  mov     [rsp+208h+var_170], rax
0x14000ec71  mov     qword ptr [rsp+208h+Interval], 0FFFFFFFFFFFFD8F0h
0x14000ec7a  cmp     dword ptr [rsi], 1
0x14000ec7d  jz      short loc_14000ECD8
0x14000ec7f  test    r15, r15
0x14000ec82  jz      short loc_14000EC8E
0x14000ec84  mov     rcx, r15
0x14000ec87  call    SmbCeReleaseCompoundingKeyLock
0x14000ec8c  jmp     short loc_14000EC96
0x14000ec8e  mov     rcx, rbx
0x14000ec91  call    SmbCeReleaseExchangeLock
0x14000ec96  lea     r8, [rsp+208h+Interval]; Interval
0x14000ec9b  xor     edx, edx; Alertable
0x14000ec9d  xor     ecx, ecx; WaitMode
0x14000ec9f  call    cs:__imp_KeDelayExecutionThread
0x14000eca6  nop     dword ptr [rax+rax+00h]
0x14000ecab  mov     rax, qword ptr [rsp+208h+Interval]
0x14000ecb0  add     rax, rax
0x14000ecb3  mov     qword ptr [rsp+208h+Interval], rax
0x14000ecb8  test    r15, r15
0x14000ecbb  jz      short loc_14000ECC7
0x14000ecbd  mov     rcx, r15
0x14000ecc0  call    SmbCeAcquireCompoundingKeyLock
0x14000ecc5  jmp     short loc_14000ECCF
0x14000ecc7  mov     rcx, rbx
0x14000ecca  call    SmbCeAcquireExchangeLock
0x14000eccf  inc     r13d
0x14000ecd2  cmp     r13d, 0Ah
0x14000ecd6  jb      short loc_14000EC7A
0x14000ecd8  mov     rsi, rbx
0x14000ecdb  lea     rcx, [rbx+0A0h]
0x14000ece2  mov     [rsp+208h+var_1B0], rcx
0x14000ece7  mov     rcx, [rcx]
0x14000ecea  test    r15, r15
0x14000eced  mov     r13d, r12d
0x14000ecf0  jz      loc_14000ED81
0x14000ecf6  lea     rax, [rcx-8]
0x14000ecfa  cmp     rcx, [rsp+208h+var_1B0]
0x14000ecff  cmovz   rax, r12
0x14000ed03  test    rax, rax
0x14000ed06  jz      loc_14000EDEF
0x14000ed0c  cmp     [rax+54h], r12b
0x14000ed10  jz      loc_14000EDEF
0x14000ed16  cmp     [rax+55h], r12b
0x14000ed1a  jnz     loc_14000EDEF
0x14000ed20  xorps   xmm0, xmm0
0x14000ed23  movups  xmmword ptr [rsp+208h+pContext], xmm0
0x14000ed2b  movups  [rsp+208h+var_D8], xmm0
0x14000ed33  movups  [rsp+208h+var_C8], xmm0
0x14000ed3b  mov     rdx, 10C0000120h
0x14000ed45  lea     r8, [rsp+208h+pContext]
0x14000ed4d  mov     rcx, r15
0x14000ed50  call    SmbCepAbortCompoundedExchangesLite
0x14000ed55  mov     r14d, r12d
0x14000ed58  test    eax, eax
0x14000ed5a  jz      loc_14000EDEF
0x14000ed60  mov     esi, eax
0x14000ed62  mov     ecx, r14d
0x14000ed65  xor     edx, edx
0x14000ed67  mov     rcx, [rsp+rcx*8+208h+pContext]; pContext
0x14000ed6f  call    SmbCepCompleteExchangeLiteEx
0x14000ed74  inc     r14d
0x14000ed77  cmp     r14d, esi
0x14000ed7a  jb      short loc_14000ED62
0x14000ed7c  mov     rsi, rbx
0x14000ed7f  jmp     short loc_14000EDEF
0x14000ed81  lea     r14, [rcx-8]
0x14000ed85  cmp     rcx, [rsp+208h+var_1B0]
0x14000ed8a  cmovz   r14, r12
0x14000ed8e  test    r14, r14
0x14000ed91  jz      short loc_14000EDEF
0x14000ed93  mov     rdx, [rsp+208h+var_1B0]
0x14000ed98  cmp     [r14+54h], r12b
0x14000ed9c  jz      short loc_14000EDD8
0x14000ed9e  cmp     [r14+55h], r12b
0x14000eda2  jnz     short loc_14000EDD8
0x14000eda4  mov     dword ptr [rsp+208h+MemoryDescriptorList], 0C0000120h
0x14000edac  mov     dword ptr [rsp+208h+MemoryDescriptorList+4], 10h
0x14000edb4  mov     rax, [rbx+60h]
0x14000edb8  mov     rcx, [rax+188h]
0x14000edbf  mov     r8, [rsp+208h+MemoryDescriptorList]
0x14000edc4  mov     rdx, r14
0x14000edc7  mov     rcx, [rcx+200h]; pContext
0x14000edce  call    SmbCseAbortBufferContext
0x14000edd3  mov     rdx, [rsp+208h+var_1B0]
0x14000edd8  mov     rcx, [r14+8]
0x14000eddc  lea     rax, [rcx-8]
0x14000ede0  mov     r14, r12
0x14000ede3  cmp     rcx, rdx
0x14000ede6  cmovnz  r14, rax
0x14000edea  test    r14, r14
0x14000eded  jnz     short loc_14000ED98
0x14000edef  mov     rcx, [rsp+208h+var_1B0]
0x14000edf4  mov     rax, [rcx]
0x14000edf7  lea     r14, [rax-8]
0x14000edfb  cmp     rax, rcx
0x14000edfe  cmovz   r14, r12
0x14000ee02  mov     [rsp+208h+var_1C0], r14
0x14000ee07  test    r14, r14
0x14000ee0a  jz      loc_14000F0D7
0x14000ee10  cmp     byte ptr [r14+55h], 0
0x14000ee15  jbe     loc_14000F0BE
0x14000ee1b  mov     eax, [r14+4]
0x14000ee1f  test    al, 3
0x14000ee21  jz      loc_14000F0BE
0x14000ee27  mov     [rsp+208h+SendLength], 80h
0x14000ee2f  mov     rdx, [rsp+208h+var_198]
0x14000ee34  mov     rax, [rdx+38h]
0x14000ee38  mov     rax, [rax+360h]
0x14000ee3f  lea     r8, [rsp+208h+SendLength]
0x14000ee44  lea     rdx, [rsp+208h+var_B8]
0x14000ee4c  mov     rcx, r14
0x14000ee4f  call    _guard_dispatch_icall
0x14000ee54  test    r15, r15
0x14000ee57  jz      short loc_14000EE63
0x14000ee59  mov     rcx, r15
0x14000ee5c  call    SmbCeReleaseCompoundingKeyLock
0x14000ee61  jmp     short loc_14000EE6B
0x14000ee63  mov     rcx, rbx
0x14000ee66  call    SmbCeReleaseExchangeLock
0x14000ee6b  mov     [rsp+208h+var_1E8], r12
0x14000ee70  xor     r9d, r9d
0x14000ee73  xor     r8d, r8d
0x14000ee76  mov     edx, [rsp+208h+SendLength]
0x14000ee7a  lea     rcx, [rsp+208h+var_B8]
0x14000ee82  call    cs:__imp_RxAllocateMdl2
0x14000ee89  nop     dword ptr [rax+rax+00h]
0x14000ee8e  mov     [rsp+208h+MemoryDescriptorList], rax
0x14000ee93  test    rax, rax
0x14000ee96  jz      loc_14000F071
0x14000ee9c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000eea3  cmp     rcx, rdi
0x14000eea6  jz      short loc_14000EEE0
0x14000eea8  mov     edx, [rcx+2Ch]
0x14000eeab  test    dl, 1
0x14000eeae  jz      short loc_14000EEE0
0x14000eeb0  cmp     byte ptr [rcx+29h], 1
0x14000eeb4  jb      short loc_14000EEE0
0x14000eeb6  mov     edx, 0Eh
0x14000eebb  mov     eax, [rsp+208h+SendLength]
0x14000eebf  mov     [rsp+208h+var_1E0], eax
0x14000eec3  mov     [rsp+208h+var_1E8], r14
0x14000eec8  mov     r9, rbx
0x14000eecb  lea     r8, WPP_2ed4b0d8e3883b7ea50b1283a39c615b_Traceguids
0x14000eed2  mov     rcx, [rcx+18h]
0x14000eed6  call    WPP_SF_qqD
0x14000eedb  mov     rax, [rsp+208h+MemoryDescriptorList]
0x14000eee0  mov     r13d, r12d
0x14000eee3  xor     edx, edx; AccessMode
0x14000eee5  mov     r8d, 2; Operation
0x14000eeeb  mov     rcx, rax; MemoryDescriptorList
0x14000eeee  call    cs:__imp_MmProbeAndLockPages
0x14000eef5  nop     dword ptr [rax+rax+00h]
0x14000eefa  jmp     short loc_14000EF3B
0x14000eefc  mov     r13d, eax
0x14000eeff  xor     r12d, r12d
0x14000ef02  lea     rdi, WPP_GLOBAL_Control
0x14000ef09  mov     rbx, [rsp+208h+var_188]
0x14000ef11  mov     rax, [rsp+208h+var_180]
0x14000ef19  mov     [rsp+208h+var_198], rax
0x14000ef1e  mov     r14, [rsp+208h+var_1C0]
0x14000ef23  mov     r15, [rsp+208h+var_178]
0x14000ef2b  mov     rax, [rsp+208h+var_170]
0x14000ef33  mov     [rsp+208h+var_190], rax
0x14000ef38  mov     rsi, rbx
0x14000ef3b  test    r13d, r13d
0x14000ef3e  js      loc_14000F028
0x14000ef44  mov     dword ptr [r14+368h], 10000000h
0x14000ef4f  mov     rax, [rsi+60h]
0x14000ef53  mov     r10, [rax+188h]
0x14000ef5a  mov     rcx, rbx
0x14000ef5d  call    ExchangeRequiresEncryption
0x14000ef62  test    al, al
0x14000ef64  jz      loc_14000EFF4
0x14000ef6a  cmp     dword ptr [r10+140h], 4
0x14000ef72  jnz     short loc_14000EF86
0x14000ef74  mov     dword ptr [rsp+208h+var_1C0], 10000000h
0x14000ef7c  cmp     byte ptr [r10+25Ch], 0
0x14000ef84  jnz     short loc_14000EF99
0x14000ef86  mov     dword ptr [r14+368h], 50000000h
0x14000ef91  mov     dword ptr [rsp+208h+var_1C0], 50000000h
0x14000ef99  xor     edx, edx; Val
0x14000ef9b  mov     r8d, 68h ; 'h'; Size
0x14000efa1  lea     rcx, [rsp+208h+var_158]; void *
0x14000efa9  call    memset
0x14000efae  mov     rcx, [rsi+60h]
0x14000efb2  mov     rax, [rcx+210h]
0x14000efb9  mov     [rsp+208h+var_158], rax
0x14000efc1  mov     rax, [rsp+208h+var_190]
0x14000efc6  mov     rax, [rax+1B8h]
0x14000efcd  mov     [rsp+208h+var_150], rax
0x14000efd5  mov     [rsp+208h+var_1D8], r12
0x14000efda  lea     rax, [rsp+208h+var_158]
0x14000efe2  mov     [rsp+208h+var_1E8], rax
0x14000efe7  mov     edx, dword ptr [rsp+208h+var_1C0]
0x14000efeb  mov     rcx, [rcx+188h]
  ... truncated ...
```
