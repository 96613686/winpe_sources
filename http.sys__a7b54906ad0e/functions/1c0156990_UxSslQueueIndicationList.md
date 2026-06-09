# UxSslQueueIndicationList

- ea: `0x1c0156990`
- end: `0x1c0156e3d`
- name: `UxSslQueueIndicationList`
- size: `1197`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0156970`

## callees

- `0x1c0001118`
- `0x1c000ead0`
- `0x1c000eb40`
- `0x1c001a4b0`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c008f3ec`
- `0x1c01560b8`
- `0x1c0156990`
- `0x1c0157918`
- `0x1c0158a70`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c0156c03`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c0156c03`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0156cbf`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0156cbf`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0156c74`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0156d1e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0156d91`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0157dd6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0157e4d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0157ea2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0156c74`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0156d1e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0156d91`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0157dd6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0157e4d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0157ea2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0156c31`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0157d99`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0157e10`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0156c31`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0157d99`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0157e10`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0157f03`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0157f03`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0156a7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0156a7f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0156a22`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0156a22`

## pseudocode

```c
__int64 __fastcall UxSslQueueIndicationList(__int64 a1, __int64 a2, __int64 *a3, unsigned __int64 a4)
{
  unsigned int v4; // esi
  unsigned int v8; // r12d
  unsigned int v9; // r14d
  KIRQL v10; // al
  __int64 v11; // rdx
  int v12; // r9d
  unsigned __int64 v13; // rcx
  unsigned int v14; // edi
  _QWORD *v15; // rbp
  int v16; // r12d
  int v17; // ecx
  unsigned int v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // rdx
  char *v21; // r9
  unsigned __int64 v22; // r12
  unsigned int v23; // ecx
  struct _MDL *v24; // r14
  unsigned int ByteCount; // eax
  char *MappedSystemVa; // rax
  unsigned int v27; // r13d
  __int64 v29; // r12
  unsigned int v30; // r8d
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rbp
  PSLIST_ENTRY v35; // rax
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 (__fastcall *v39)(__int64, __int64, __int64, __int64); // rax
  unsigned int v40; // r8d
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rax
  unsigned int v44; // edx
  unsigned int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // r14
  _QWORD *PoolWithTagPriority; // rdi
  int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 (__fastcall *v55)(__int64, __int64, __int64, __int64); // rax
  __int64 v56; // rdi
  unsigned int v57; // edx
  unsigned int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rax
  _QWORD *v61; // rdi
  unsigned int v62; // edx
  unsigned int v63; // eax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r14
  unsigned int v67; // edx
  unsigned int v68; // eax
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 (__fastcall *v74)(__int64, __int64, __int64, __int64); // rax
  int Data; // eax
  unsigned int i; // [rsp+30h] [rbp-78h]
  int v77; // [rsp+34h] [rbp-74h]
  char *v78; // [rsp+38h] [rbp-70h]
  _QWORD v79[3]; // [rsp+40h] [rbp-68h] BYREF
  char v80; // [rsp+58h] [rbp-50h]
  int v81; // [rsp+59h] [rbp-4Fh]
  __int16 v82; // [rsp+5Dh] [rbp-4Bh]
  char v83; // [rsp+5Fh] [rbp-49h]

  v4 = 0;
  v8 = 0;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 960) + 1568LL) )
  {
    v79[2] = *(_QWORD *)(a1 + 960);
    v81 = 0;
    v79[0] = a1 + 72;
    v82 = 0;
    v83 = 0;
    v79[1] = 0;
    v80 = 0;
    McTemplateK0qp_UlEtwWriteEventWrapper(a1, HTTP_EVENT_SSL_RECEIVE_RAW_DATA, v79);
  }
  v9 = a4;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000) != 0 )
    WPP_SF_qq(10, WPP_a22469013d8d37a4fc03866b4ef29eb7_Traceguids, a1, a4);
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 656));
  v11 = *(unsigned int *)(a1 + 664);
  v12 = *(_DWORD *)(a1 + 680);
  v13 = a4 + v11;
  if ( (v12 & 8) != 0 )
  {
    v14 = -1073741436;
  }
  else if ( v13 < a4 || v13 > *(unsigned int *)(a1 + 668) )
  {
    v8 = *(_DWORD *)(a1 + 668) - v11;
    if ( v8 )
      *(_DWORD *)(a1 + 680) = v12 | 1;
    if ( a4 > 0xFFFFFFFF )
      LODWORD(a4) = -1;
    *(_DWORD *)(a1 + 672) = a4;
    v14 = -1073741285;
  }
  else
  {
    v14 = 259;
    *(_DWORD *)(a1 + 664) = v9 + v11;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 656), v10);
  if ( v14 == 259 )
  {
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 752), 1, 0) )
    {
      v15 = *(_QWORD **)(a1 + 800);
      v16 = 0;
      if ( v15 )
      {
        v17 = *((_DWORD *)v15 + 12);
        if ( (int)v15 + *((_DWORD *)v15 + 13) - *((_DWORD *)v15 + 10) - v17 + 56 >= v9 )
        {
          v18 = v9 + v17;
          if ( v18 > v9
            || *((_DWORD *)v15 + 13) <= (unsigned int)UxSslSmallReceiveBufferSize
            || v18 > UxSslSmallReceiveBufferSize )
          {
            goto LABEL_15;
          }
        }
        if ( v9 + *((_DWORD *)v15 + 12) < v9 )
        {
          v15 = 0;
          goto LABEL_60;
        }
        v9 += *((_DWORD *)v15 + 12);
      }
      if ( v9 <= UxSslSmallReceiveBufferSize )
      {
        if ( UxCompactMode )
        {
          v56 = qword_1C0074480;
          v57 = KeGetCurrentNodeNumber() + 1;
          v58 = *(_DWORD *)v56 - 1;
          if ( v57 < *(_DWORD *)v56 )
            v58 = v57;
          v59 = v58;
          v60 = *(_QWORD *)(v56 + 32);
          v48 = *(_QWORD *)(v60 + 8 * v59);
          if ( !*(_BYTE *)(v48 + 112) )
            PplpLazyInitializeLookasideList(v56, *(_QWORD *)(v60 + 8 * v59));
          ++*(_DWORD *)(v48 + 20);
          PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v48);
          if ( PoolWithTagPriority )
            goto LABEL_51;
        }
        else
        {
          v44 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
          v45 = *(_DWORD *)qword_1C0074480 - 1;
          if ( v44 < *(_DWORD *)qword_1C0074480 )
            v45 = v44;
          v46 = v45;
          v47 = *(_QWORD *)(qword_1C0074480 + 32);
          v48 = *(_QWORD *)(v47 + 8 * v46);
          if ( !*(_BYTE *)(v48 + 112) )
            PplpLazyInitializeLookasideList(qword_1C0074480, *(_QWORD *)(v47 + 8 * v46));
          ++*(_DWORD *)(v48 + 20);
          PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v48);
          if ( PoolWithTagPriority )
            goto LABEL_51;
        }
        v52 = *(unsigned int *)(v48 + 40);
        v53 = *(unsigned int *)(v48 + 44);
        v54 = *(unsigned int *)(v48 + 36);
        v55 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v48 + 48);
        ++*(_DWORD *)(v48 + 24);
        PoolWithTagPriority = (_QWORD *)v55(v54, v53, v52, v48);
LABEL_51:
        v9 = UxSslSmallReceiveBufferSize;
        v50 = 0;
        goto LABEL_52;
      }
      if ( v9 > UxSslReceiverBufferSize )
      {
        if ( v9 >= v9 + 56 )
          PoolWithTagPriority = 0;
        else
          PoolWithTagPriority = ExAllocatePoolWithTagPriority((POOL_TYPE)512, v9 + 56LL, 0x42537855u, LowPoolPriority);
        v50 = 2;
LABEL_52:
        if ( PoolWithTagPriority )
        {
          *(_DWORD *)PoolWithTagPriority = 1112766549;
          PoolWithTagPriority[3] = PoolWithTagPriority + 7;
          PoolWithTagPriority[5] = PoolWithTagPriority + 7;
          *((_DWORD *)PoolWithTagPriority + 4) = v50;
          *((_DWORD *)PoolWithTagPriority + 13) = v9;
          *(_QWORD *)((char *)PoolWithTagPriority + 4) = 1;
          *((_BYTE *)PoolWithTagPriority + 12) = 0;
          *((_DWORD *)PoolWithTagPriority + 8) = 0;
          *((_DWORD *)PoolWithTagPriority + 12) = 0;
          if ( v15 )
          {
            *((_DWORD *)PoolWithTagPriority + 12) = *((_DWORD *)v15 + 12);
            memmove(PoolWithTagPriority + 7, (const void *)v15[5], *((unsigned int *)v15 + 12));
          }
        }
        v15 = PoolWithTagPriority;
        if ( PoolWithTagPriority )
        {
LABEL_56:
          v51 = *(_QWORD *)(a1 + 800);
          if ( v51 && _InterlockedExchangeAdd((volatile signed __int32 *)(v51 + 4), 0xFFFFFFFF) == 1 )
            UxSslFreeReceiverBuffer(*(PSLIST_ENTRY *)(a1 + 800));
          *(_QWORD *)(a1 + 800) = v15;
          if ( v16 < 0 )
          {
LABEL_100:
            UxSslAbortConnection(a1, (unsigned int)v16);
            v4 = -1073741285;
LABEL_26:
            LOBYTE(v20) = 1;
            UxSslQueueReceiverWorkItem(a1, v20);
            return v4;
          }
LABEL_15:
          v19 = v15[5];
          v20 = *((unsigned int *)v15 + 12);
          v21 = (char *)(v19 + v20);
          v78 = (char *)(v19 + v20);
          v77 = *((_DWORD *)v15 + 13) - v19 - v20 + (_DWORD)v15 + 56;
          while ( a3 )
          {
            v22 = a3[3];
            v23 = *((_DWORD *)a3 + 4);
            v24 = (struct _MDL *)a3[1];
            a3 = (__int64 *)*a3;
            for ( i = v23; v22; i = v23 )
            {
              ByteCount = v24->ByteCount;
              if ( v23 >= ByteCount )
              {
                v23 -= ByteCount;
              }
              else
              {
                if ( (v24->MdlFlags & 5) != 0 )
                {
                  MappedSystemVa = (char *)v24->MappedSystemVa;
                }
                else
                {
                  MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v24, 0, MmCached, 0, 0, 0x40000000u);
                  v23 = i;
                  v21 = v78;
                }
                if ( !MappedSystemVa )
                {
                  v16 = -1073741670;
                  goto LABEL_100;
                }
                v27 = v24->ByteCount - v23;
                if ( v27 > v22 )
                  v27 = v22;
                memmove(v21, &MappedSystemVa[v23], v27);
                v23 = 0;
                v77 -= v27;
                v21 = &v78[v27];
                *((_DWORD *)v15 + 12) += v27;
                v78 = v21;
                v22 -= v27;
              }
              v24 = v24->Next;
            }
          }
          goto LABEL_26;
        }
LABEL_60:
        v16 = -1073741670;
        goto LABEL_56;
      }
      if ( UxCompactMode )
      {
        v61 = P;
        v62 = KeGetCurrentNodeNumber() + 1;
        v63 = *(_DWORD *)v61 - 1;
        if ( v62 < *(_DWORD *)v61 )
          v63 = v62;
        v64 = v63;
        v65 = v61[4];
        v66 = *(_QWORD *)(v65 + 8 * v64);
        if ( !*(_BYTE *)(v66 + 112) )
          PplpLazyInitializeLookasideList(v61, *(_QWORD *)(v65 + 8 * v64));
        ++*(_DWORD *)(v66 + 20);
        PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v66);
        if ( PoolWithTagPriority )
          goto LABEL_91;
      }
      else
      {
        v67 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
        v68 = *(_DWORD *)P - 1;
        if ( v67 < *(_DWORD *)P )
          v68 = v67;
        v69 = v68;
        v70 = *((_QWORD *)P + 4);
        v66 = *(_QWORD *)(v70 + 8 * v69);
        if ( !*(_BYTE *)(v66 + 112) )
          PplpLazyInitializeLookasideList(P, *(_QWORD *)(v70 + 8 * v69));
        ++*(_DWORD *)(v66 + 20);
        PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v66);
        if ( PoolWithTagPriority )
          goto LABEL_91;
      }
      v71 = *(unsigned int *)(v66 + 40);
      v72 = *(unsigned int *)(v66 + 44);
      v73 = *(unsigned int *)(v66 + 36);
      v74 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v66 + 48);
      ++*(_DWORD *)(v66 + 24);
      PoolWithTagPriority = (_QWORD *)v74(v73, v72, v71, v66);
LABEL_91:
      v9 = UxSslReceiverBufferSize;
      v50 = 1;
      goto LABEL_52;
    }
    if ( UxCompactMode )
    {
      v29 = qword_1C00743C0;
      v30 = KeGetCurrentNodeNumber() + 1;
      v31 = *(_DWORD *)v29 - 1;
      if ( v30 < *(_DWORD *)v29 )
        v31 = v30;
      v32 = v31;
      v33 = *(_QWORD *)(v29 + 32);
      v34 = *(_QWORD *)(v33 + 8 * v32);
      if ( !*(_BYTE *)(v34 + 112) )
        PplpLazyInitializeLookasideList(v29, *(_QWORD *)(v33 + 8 * v32));
      ++*(_DWORD *)(v34 + 20);
      v35 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34);
      if ( !v35 )
        goto LABEL_34;
    }
    else
    {
      v40 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v41 = *(_DWORD *)qword_1C00743C0 - 1;
      if ( v40 < *(_DWORD *)qword_1C00743C0 )
        v41 = v40;
      v42 = v41;
      v43 = *(_QWORD *)(qword_1C00743C0 + 32);
      v34 = *(_QWORD *)(v43 + 8 * v42);
      if ( !*(_BYTE *)(v34 + 112) )
        PplpLazyInitializeLookasideList(qword_1C00743C0, *(_QWORD *)(v43 + 8 * v42));
      ++*(_DWORD *)(v34 + 20);
      v35 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34);
      if ( !v35 )
      {
LABEL_34:
        v36 = *(unsigned int *)(v34 + 40);
        v37 = *(unsigned int *)(v34 + 44);
        v38 = *(unsigned int *)(v34 + 36);
        v39 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v34 + 48);
        ++*(_DWORD *)(v34 + 24);
        v35 = (PSLIST_ENTRY)v39(v38, v37, v36, v34);
        if ( !v35 )
        {
          UxSslAbortConnection(a1, 3221225626LL);
          return 3221226011LL;
        }
      }
    }
    *((_QWORD *)&v35[2].Next + 1) = 0;
    LODWORD(v35[3].Next) = v9;
    v35[2].Next = (struct _SLIST_ENTRY *)a3;
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 688), v35 + 1) )
      UxSslQueueReceiverWorkItem(a1, 0);
    return 259;
  }
  if ( v14 == -1073741285 )
  {
    if ( v8 )
    {
      Data = UxpSslReadData(a1, v8);
      if ( Data < 0 )
        UxSslAbortConnection(a1, (unsigned int)Data);
      return 3221226011LL;
    }
    else
    {
      return 3221226011LL;
    }
  }
  else
  {
    UxSslAbortConnection(a1, v14);
    return 3221226011LL;
  }
}

```

## disassembly

```asm
0x1c0156990  push    rbx
0x1c0156992  push    rbp
0x1c0156993  push    rsi
0x1c0156994  push    rdi
0x1c0156995  push    r12
0x1c0156997  push    r14
0x1c0156999  push    r15
0x1c015699b  sub     rsp, 70h
0x1c015699f  mov     rax, cs:__security_cookie
0x1c01569a6  xor     rax, rsp
0x1c01569a9  mov     [rsp+0A8h+var_48], rax
0x1c01569ae  mov     rax, [rcx+3C0h]
0x1c01569b5  xor     esi, esi
0x1c01569b7  mov     rdi, r9
0x1c01569ba  mov     r15, r8
0x1c01569bd  mov     rbx, rcx
0x1c01569c0  mov     r12d, esi
0x1c01569c3  cmp     [rax+620h], sil
0x1c01569ca  jz      short loc_1C0156A08
0x1c01569cc  mov     [rsp+0A8h+var_58], rax
0x1c01569d1  lea     r8, [rsp+0A8h+var_68]
0x1c01569d6  lea     rax, [rcx+48h]
0x1c01569da  mov     [rsp+0A8h+var_4F], esi
0x1c01569de  lea     rdx, HTTP_EVENT_SSL_RECEIVE_RAW_DATA
0x1c01569e5  mov     [rsp+0A8h+var_68], rax
0x1c01569ea  mov     [rsp+0A8h+var_4B], si
0x1c01569ef  mov     [rsp+0A8h+var_49], sil
0x1c01569f4  mov     [rsp+0A8h+var_60], rsi
0x1c01569f9  mov     [rsp+0A8h+var_50], sil
0x1c01569fe  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rcx
0x1c0156a03  call    McTemplateK0qp_UlEtwWriteEventWrapper
0x1c0156a08  mov     r14d, edi
0x1c0156a0b  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000h
0x1c0156a15  jnz     loc_1C0157D0C
0x1c0156a1b  lea     rcx, [rbx+290h]; SpinLock
0x1c0156a22  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c0156a29  nop     dword ptr [rax+rax+00h]
0x1c0156a2e  mov     edx, [rbx+298h]
0x1c0156a34  movzx   r8d, al
0x1c0156a38  mov     r9d, [rbx+2A8h]
0x1c0156a3f  lea     rcx, [rdi+rdx]
0x1c0156a43  test    r9b, 8
0x1c0156a47  jnz     loc_1C0157D29
0x1c0156a4d  cmp     rcx, rdi
0x1c0156a50  jb      loc_1C0157D33
0x1c0156a56  mov     eax, [rbx+29Ch]
0x1c0156a5c  cmp     rcx, rax
0x1c0156a5f  ja      loc_1C0157D33
0x1c0156a65  lea     eax, [r14+rdx]
0x1c0156a69  mov     edi, 103h
0x1c0156a6e  mov     [rbx+298h], eax
0x1c0156a74  movzx   edx, r8b; NewIrql
0x1c0156a78  lea     rcx, [rbx+290h]; SpinLock
0x1c0156a7f  call    cs:__imp_KeReleaseSpinLock
0x1c0156a86  nop     dword ptr [rax+rax+00h]
0x1c0156a8b  cmp     edi, 103h
0x1c0156a91  jnz     loc_1C0157FA0
0x1c0156a97  mov     [rsp+0A8h+arg_8], r13
0x1c0156a9f  xor     eax, eax
0x1c0156aa1  mov     r13d, 1
0x1c0156aa7  lock cmpxchg [rbx+2F0h], r13d
0x1c0156ab0  jnz     loc_1C0156C1D
0x1c0156ab6  mov     rbp, [rbx+320h]
0x1c0156abd  mov     r12d, esi
0x1c0156ac0  test    rbp, rbp
0x1c0156ac3  jz      loc_1C0156D38
0x1c0156ac9  mov     edx, [rbp+34h]
0x1c0156acc  mov     eax, edx
0x1c0156ace  sub     eax, [rbp+28h]
0x1c0156ad1  mov     ecx, [rbp+30h]
0x1c0156ad4  sub     eax, ecx
0x1c0156ad6  add     eax, 38h ; '8'
0x1c0156ad9  add     eax, ebp
0x1c0156adb  cmp     eax, r14d
0x1c0156ade  jb      loc_1C0157D6E
0x1c0156ae4  add     ecx, r14d
0x1c0156ae7  cmp     ecx, r14d
0x1c0156aea  ja      short loc_1C0156AFA
0x1c0156aec  mov     eax, cs:UxSslSmallReceiveBufferSize
0x1c0156af2  cmp     edx, eax
0x1c0156af4  ja      loc_1C0157D66
0x1c0156afa  mov     rcx, [rbp+28h]
0x1c0156afe  mov     edx, [rbp+30h]
0x1c0156b01  mov     eax, [rbp+34h]
0x1c0156b04  sub     eax, ecx
0x1c0156b06  sub     eax, edx
0x1c0156b08  lea     r9, [rcx+rdx]
0x1c0156b0c  lea     ecx, [rbp+38h]
0x1c0156b0f  mov     [rsp+0A8h+var_70], r9
0x1c0156b14  add     ecx, eax
0x1c0156b16  mov     [rsp+0A8h+var_74], ecx
0x1c0156b1a  test    r15, r15
0x1c0156b1d  jz      loc_1C0156BBB
0x1c0156b23  mov     r12, [r15+18h]
0x1c0156b27  mov     ecx, [r15+10h]
0x1c0156b2b  mov     r14, [r15+8]
0x1c0156b2f  mov     r15, [r15]
0x1c0156b32  mov     [rsp+0A8h+var_78], ecx
0x1c0156b36  test    r12, r12
0x1c0156b39  jz      short loc_1C0156BB2
0x1c0156b3b  mov     eax, [r14+28h]
0x1c0156b3f  cmp     ecx, eax
0x1c0156b41  jnb     loc_1C0157F5F
0x1c0156b47  test    byte ptr [r14+0Ah], 5
0x1c0156b4c  jz      loc_1C0156BEC
0x1c0156b52  mov     rax, [r14+18h]
0x1c0156b56  test    rax, rax
0x1c0156b59  jz      loc_1C0157F6E
0x1c0156b5f  mov     r13d, [r14+28h]
0x1c0156b63  sub     r13d, ecx
0x1c0156b66  mov     edx, ecx
0x1c0156b68  add     rdx, rax; Src
0x1c0156b6b  mov     eax, r13d
0x1c0156b6e  cmp     rax, r12
0x1c0156b71  ja      loc_1C0157F66
0x1c0156b77  mov     r8d, r13d; Size
0x1c0156b7a  mov     rcx, r9; void *
0x1c0156b7d  mov     edi, r13d
0x1c0156b80  call    memmove
0x1c0156b85  mov     r9, [rsp+0A8h+var_70]
0x1c0156b8a  mov     ecx, esi
0x1c0156b8c  sub     [rsp+0A8h+var_74], r13d
0x1c0156b91  add     r9, rdi
0x1c0156b94  add     [rbp+30h], r13d
0x1c0156b98  mov     r13d, 1
0x1c0156b9e  mov     [rsp+0A8h+var_70], r9
0x1c0156ba3  sub     r12, rdi
0x1c0156ba6  mov     r14, [r14]
0x1c0156ba9  mov     [rsp+0A8h+var_78], ecx
0x1c0156bad  test    r12, r12
0x1c0156bb0  jnz     short loc_1C0156B3B
0x1c0156bb2  test    r15, r15
0x1c0156bb5  jnz     loc_1C0156B23
0x1c0156bbb  mov     dl, 1
0x1c0156bbd  mov     rcx, rbx
0x1c0156bc0  call    UxSslQueueReceiverWorkItem
0x1c0156bc5  mov     eax, esi
0x1c0156bc7  mov     r13, [rsp+0A8h+arg_8]
0x1c0156bcf  mov     rcx, [rsp+0A8h+var_48]
0x1c0156bd4  xor     rcx, rsp; StackCookie
0x1c0156bd7  call    __security_check_cookie
0x1c0156bdc  add     rsp, 70h
0x1c0156be0  pop     r15
0x1c0156be2  pop     r14
0x1c0156be4  pop     r12
0x1c0156be6  pop     rdi
0x1c0156be7  pop     rsi
0x1c0156be8  pop     rbp
0x1c0156be9  pop     rbx
0x1c0156bea  retn
0x1c0156bec  mov     [rsp+0A8h+Priority], 40000000h; Priority
0x1c0156bf4  xor     r9d, r9d; RequestedAddress
0x1c0156bf7  mov     r8d, r13d; CacheType
0x1c0156bfa  mov     [rsp+0A8h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1c0156bfe  xor     edx, edx; AccessMode
0x1c0156c00  mov     rcx, r14; MemoryDescriptorList
0x1c0156c03  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1c0156c0a  nop     dword ptr [rax+rax+00h]
0x1c0156c0f  mov     ecx, [rsp+0A8h+var_78]
0x1c0156c13  mov     r9, [rsp+0A8h+var_70]
0x1c0156c18  jmp     loc_1C0156B56
0x1c0156c1d  cmp     cs:UxCompactMode, sil
0x1c0156c24  jz      loc_1C0156CE1
0x1c0156c2a  mov     r12, cs:qword_1C00743C0
0x1c0156c31  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0156c38  nop     dword ptr [rax+rax+00h]
0x1c0156c3d  mov     edx, [r12]
0x1c0156c41  movzx   r8d, ax
0x1c0156c45  inc     r8d
0x1c0156c48  cmp     r8d, edx
0x1c0156c4b  lea     eax, [rdx-1]
0x1c0156c4e  cmovb   eax, r8d
0x1c0156c52  mov     edx, eax
0x1c0156c54  mov     rax, [r12+20h]
0x1c0156c59  mov     rbp, [rax+rdx*8]
0x1c0156c5d  cmp     [rbp+70h], sil
0x1c0156c61  jnz     short loc_1C0156C6E
0x1c0156c63  mov     rdx, rbp
0x1c0156c66  mov     rcx, r12
0x1c0156c69  call    PplpLazyInitializeLookasideList
0x1c0156c6e  inc     dword ptr [rbp+14h]
0x1c0156c71  mov     rcx, rbp; ListHead
0x1c0156c74  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0156c7b  nop     dword ptr [rax+rax+00h]
0x1c0156c80  test    rax, rax
0x1c0156c83  jnz     short loc_1C0156CA8
0x1c0156c85  mov     r8d, [rbp+28h]
0x1c0156c89  mov     r9, rbp
0x1c0156c8c  mov     edx, [rbp+2Ch]
0x1c0156c8f  mov     ecx, [rbp+24h]
0x1c0156c92  mov     rax, [rbp+30h]
0x1c0156c96  inc     dword ptr [rbp+18h]
0x1c0156c99  call    cs:__guard_dispatch_icall_fptr
0x1c0156c9f  test    rax, rax
0x1c0156ca2  jz      loc_1C0157F89
0x1c0156ca8  lea     rdx, [rax+10h]; ListEntry
0x1c0156cac  mov     [rax+28h], rsi
0x1c0156cb0  lea     rcx, [rbx+2B0h]; ListHead
0x1c0156cb7  mov     [rax+30h], r14d
0x1c0156cbb  mov     [rax+20h], r15
0x1c0156cbf  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c0156cc6  nop     dword ptr [rax+rax+00h]
0x1c0156ccb  test    rax, rax
0x1c0156cce  jnz     short loc_1C0156CDA
0x1c0156cd0  xor     edx, edx
0x1c0156cd2  mov     rcx, rbx
0x1c0156cd5  call    UxSslQueueReceiverWorkItem
0x1c0156cda  mov     eax, edi
0x1c0156cdc  jmp     loc_1C0156BC7
0x1c0156ce1  mov     eax, gs:1A4h
0x1c0156ce9  mov     rcx, cs:qword_1C00743C0
0x1c0156cf0  lea     r8d, [rax+1]
0x1c0156cf4  mov     edx, [rcx]
0x1c0156cf6  cmp     r8d, edx
0x1c0156cf9  lea     eax, [rdx-1]
0x1c0156cfc  cmovb   eax, r8d
0x1c0156d00  mov     edx, eax
0x1c0156d02  mov     rax, [rcx+20h]
0x1c0156d06  mov     rbp, [rax+rdx*8]
0x1c0156d0a  cmp     [rbp+70h], sil
0x1c0156d0e  jnz     short loc_1C0156D18
0x1c0156d10  mov     rdx, rbp
0x1c0156d13  call    PplpLazyInitializeLookasideList
0x1c0156d18  inc     dword ptr [rbp+14h]
0x1c0156d1b  mov     rcx, rbp; ListHead
0x1c0156d1e  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0156d25  nop     dword ptr [rax+rax+00h]
0x1c0156d2a  test    rax, rax
0x1c0156d2d  jnz     loc_1C0156CA8
0x1c0156d33  jmp     loc_1C0156C85
0x1c0156d38  cmp     r14d, cs:UxSslSmallReceiveBufferSize
0x1c0156d3f  ja      loc_1C0157DF3
0x1c0156d45  cmp     cs:UxCompactMode, sil
0x1c0156d4c  jnz     loc_1C0157D92
0x1c0156d52  mov     eax, gs:1A4h
0x1c0156d5a  mov     r8, cs:qword_1C0074480
0x1c0156d61  lea     edx, [rax+1]
0x1c0156d64  mov     ecx, [r8]
0x1c0156d67  cmp     edx, ecx
0x1c0156d69  lea     eax, [rcx-1]
0x1c0156d6c  cmovb   eax, edx
0x1c0156d6f  mov     ecx, eax
0x1c0156d71  mov     rax, [r8+20h]
0x1c0156d75  mov     r14, [rax+rcx*8]
0x1c0156d79  cmp     [r14+70h], sil
0x1c0156d7d  jnz     short loc_1C0156D8A
0x1c0156d7f  mov     rdx, r14
0x1c0156d82  mov     rcx, r8
0x1c0156d85  call    PplpLazyInitializeLookasideList
0x1c0156d8a  inc     dword ptr [r14+14h]
0x1c0156d8e  mov     rcx, r14; ListHead
0x1c0156d91  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0156d98  nop     dword ptr [rax+rax+00h]
0x1c0156d9d  mov     rdi, rax
0x1c0156da0  test    rax, rax
0x1c0156da3  jz      short loc_1C0156E10
0x1c0156da5  mov     r14d, cs:UxSslSmallReceiveBufferSize
0x1c0156dac  mov     eax, esi
0x1c0156dae  test    rdi, rdi
0x1c0156db1  jz      short loc_1C0156DE3
0x1c0156db3  mov     dword ptr [rdi], 42537855h
0x1c0156db9  lea     rcx, [rdi+38h]; void *
0x1c0156dbd  mov     [rdi+18h], rcx
0x1c0156dc1  mov     [rdi+28h], rcx
0x1c0156dc5  mov     [rdi+10h], eax
0x1c0156dc8  mov     [rdi+34h], r14d
0x1c0156dcc  mov     [rdi+4], r13
0x1c0156dd0  mov     [rdi+0Ch], sil
0x1c0156dd4  mov     [rdi+20h], esi
0x1c0156dd7  mov     [rdi+30h], esi
0x1c0156dda  test    rbp, rbp
0x1c0156ddd  jnz     loc_1C0157F21
0x1c0156de3  mov     rbp, rdi
0x1c0156de6  test    rdi, rdi
0x1c0156de9  jz      short loc_1C0156E35
0x1c0156deb  mov     rcx, [rbx+320h]
0x1c0156df2  test    rcx, rcx
0x1c0156df5  jnz     loc_1C0157F3A
0x1c0156dfb  mov     [rbx+320h], rbp
0x1c0156e02  test    r12d, r12d
0x1c0156e05  jns     loc_1C0156AFA
0x1c0156e0b  jmp     loc_1C0157F74
0x1c0156e10  mov     r8d, [r14+28h]
0x1c0156e14  mov     r9, r14
0x1c0156e17  mov     edx, [r14+2Ch]
0x1c0156e1b  mov     ecx, [r14+24h]
0x1c0156e1f  mov     rax, [r14+30h]
0x1c0156e23  inc     dword ptr [r14+18h]
0x1c0156e27  call    cs:__guard_dispatch_icall_fptr
0x1c0156e2d  mov     rdi, rax
0x1c0156e30  jmp     loc_1C0156DA5
0x1c0156e35  mov     r12d, 0C000009Ah
0x1c0156e3b  jmp     short loc_1C0156DEB
0x1c0157d0c  mov     ecx, 0Ah
0x1c0157d11  lea     rdx, WPP_a22469013d8d37a4fc03866b4ef29eb7_Traceguids
0x1c0157d18  mov     r9, rdi
0x1c0157d1b  mov     r8, rbx
0x1c0157d1e  call    WPP_SF_qq
0x1c0157d23  nop
0x1c0157d24  jmp     loc_1C0156A1B
  ... truncated ...
```
