# RxWaitForStableLViewOnFcbAndAcquireRundown

- ea: `0x140008f60`
- end: `0x140009b7a`
- name: `RxWaitForStableLViewOnFcbAndAcquireRundown`
- size: `3098`
- prototype: `__int64 __usercall@<rax>(PRX_BLOCK_CONDITION Condition@<rcx>, PMRX_FCB MrxFcb@<rdx>, __int64)`
- caller_count: `11`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140001b70`
- `0x140008910`
- `0x140008e50`
- `0x140015290`
- `0x14005e2b0`
- `0x14005e810`
- `0x140063090`
- `0x140072d20`
- `0x140075940`
- `0x140075b10`
- `0x140077390`

## callees

- `0x140008e10`
- `0x140008f60`
- `0x140009b80`
- `0x140015230`
- `0x140017280`
- `0x140017a38`
- `0x14001d5e8`
- `0x14002540c`
- `0x140057660`
- `0x140058f00`
- `0x14005f110`
- `0x1400621c0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140009108`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400092c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009108`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400092c1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140009010`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400091ef`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000979a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140009010`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400091ef`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000979a`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140008fee`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140008fee`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400096b2`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400098c5`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400096b2`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400098c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009690`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400098a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000991c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009690`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400098a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000991c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009658`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400096c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009863`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400098d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009658`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400096c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009863`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400098d8`

## pseudocode

```c
__int64 __fastcall RxWaitForStableLViewOnFcbAndAcquireRundown(
        enum _RX_BLOCK_CONDITION *Condition,
        PMRX_FCB MrxFcb,
        unsigned __int8 a3,
        char a4,
        _BYTE *a5)
{
  char v5; // r12
  unsigned __int8 v7; // bp
  PMRX_FCB v8; // rsi
  struct _RX_CONTEXT *v9; // r15
  _BYTE *v11; // rdx
  bool v12; // zf
  unsigned __int8 v13; // di
  struct _KTHREAD **v14; // r13
  struct _KTHREAD **v16; // rcx
  char v17; // r14
  ULONG v18; // r8d
  const CHAR *v19; // r9
  __int64 v20; // rax
  struct _KTHREAD *v21; // r12
  NTSTATUS *v22; // r9
  int v23; // eax
  _QWORD *v24; // rdx
  unsigned __int64 v25; // rtt
  _QWORD *v26; // rdx
  unsigned __int64 v27; // rtt
  const CHAR *v28; // r9
  signed __int64 *v29; // rdx
  unsigned __int64 v30; // rtt
  struct _KTHREAD *v31; // r8
  signed __int64 *v32; // rdx
  unsigned __int64 v33; // rtt
  struct _KTHREAD **v34; // r8
  char v35; // di
  struct _KTHREAD *v36; // r8
  signed __int64 *v37; // rdx
  unsigned __int64 v38; // rtt
  struct _KTHREAD *v39; // rdi
  struct _KTHREAD *v40; // r8
  signed __int64 *v41; // rdx
  unsigned __int64 v42; // rtt
  signed __int64 kk; // rax
  signed __int64 *v44; // rax
  signed __int64 jj; // rax
  signed __int64 *v46; // rax
  signed __int64 v47; // rax
  signed __int64 v48; // rtt
  signed __int64 v49; // rax
  struct _KTHREAD *v50; // r8
  signed __int64 *v51; // rdx
  unsigned __int64 v52; // rtt
  signed __int64 i; // rax
  signed __int64 *v54; // rax
  _QWORD *v55; // rdx
  unsigned __int64 v56; // rtt
  _QWORD *v57; // rdx
  unsigned __int64 v58; // rtt
  signed __int64 v59; // rax
  signed __int64 *v60; // rdx
  unsigned __int64 v61; // rtt
  struct _KTHREAD *v62; // r8
  signed __int64 *v63; // rdx
  unsigned __int64 v64; // rtt
  signed __int64 m; // rax
  signed __int64 *v66; // rax
  signed __int64 n; // rax
  signed __int64 *v68; // rax
  struct _KTHREAD *CurrentThread; // r15
  struct _KTHREAD *v70; // rbx
  KSPIN_LOCK *v71; // r15
  KIRQL v72; // al
  PVOID *v73; // rsi
  _QWORD *v74; // rcx
  KIRQL v75; // al
  PVOID **v76; // rcx
  PVOID *v77; // rdi
  signed __int64 v78; // rax
  struct _KTHREAD *v79; // r8
  signed __int64 *v80; // rdx
  unsigned __int64 v81; // rtt
  signed __int64 j; // rax
  signed __int64 *v83; // rax
  signed __int64 k; // rax
  signed __int64 *v85; // rax
  KSPIN_LOCK *v86; // rsi
  KIRQL v87; // al
  PVOID *v88; // rdi
  _QWORD *v89; // rcx
  PVOID **v90; // rcx
  PVOID *v91; // rbx
  KSPIN_LOCK *v92; // rcx
  signed __int64 ii; // rax
  signed __int64 *v94; // rax
  signed __int64 v95; // rtt
  signed __int64 v96; // rtt
  signed __int64 v97; // rtt
  signed __int64 v98; // rtt
  signed __int64 v99; // rtt
  signed __int64 v100; // rtt
  signed __int64 v101; // rtt
  signed __int64 v102; // rtt
  signed __int64 v103; // rtt
  signed __int64 v104; // rtt
  signed __int64 v105; // rtt
  const CHAR *v106; // [rsp+20h] [rbp-88h]
  ULONG v107; // [rsp+28h] [rbp-80h]
  struct _RX_CONTEXT *v108; // [rsp+40h] [rbp-68h]
  _DWORD *v109; // [rsp+48h] [rbp-60h]
  _DWORD *v110; // [rsp+50h] [rbp-58h]
  struct _KTHREAD *v111; // [rsp+58h] [rbp-50h]
  ULONG BackTraceHash; // [rsp+C8h] [rbp+20h] BYREF

  v5 = 0;
  v7 = 0;
  v8 = MrxFcb;
  v9 = 0;
  v108 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v107 = a3;
    v106 = (const CHAR *)MrxFcb;
    WPP_SF_qqDD(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, Condition);
  }
  v11 = a5;
  if ( a5 )
    *a5 = 0;
  v12 = a4 == 0;
  v13 = a3;
  if ( !v12 )
  {
    LOBYTE(v9) = a3 != 0;
    v9 = (struct _RX_CONTEXT *)((char *)v9 - 2);
    v108 = v9;
  }
  if ( *(_QWORD *)&v8->OpenCount )
  {
    if ( !(unsigned __int8)ExIsResourceAcquiredSharedLite(v8->Header.Resource) )
    {
      v14 = 0;
      if ( v9 )
      {
        if ( _RxAcquireFcb((PFCB)v8, v9, 2u, a3, v106, v107) )
          goto LABEL_11;
      }
      else if ( !ExAcquireResourceSharedLite(v8->Header.Resource, a3 == 0) )
      {
        goto LABEL_11;
      }
      v5 = 1;
    }
    v11 = a5;
  }
  v16 = *(struct _KTHREAD ***)&v8->OpenCount;
  v17 = 0;
  v14 = v16;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids);
      v11 = a5;
    }
    if ( v11 )
      *v11 = 1;
    goto LABEL_53;
  }
  if ( KeGetCurrentThread() == v16[30] )
  {
    RxReference(v16);
    v35 = 1;
    goto LABEL_42;
  }
  if ( v5 )
    goto LABEL_20;
  if ( v9 )
  {
    if ( _RxAcquireFcb((PFCB)v8, v9, 2u, a3, v106, v107) )
      goto LABEL_11;
  }
  else if ( !ExAcquireResourceSharedLite(v8->Header.Resource, a3 == 0) )
  {
    goto LABEL_11;
  }
  v5 = 1;
  while ( 1 )
  {
LABEL_20:
    v14 = *(struct _KTHREAD ***)&v8->OpenCount;
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids);
      }
      if ( a5 )
        *a5 = 1;
      v17 = 0;
      v7 = 0;
      goto LABEL_53;
    }
    RxReference(*(PVOID *)&v8->OpenCount);
    if ( !Condition || *((_BYTE *)Condition + 32) != 12 || (v20 = 28, *((_BYTE *)Condition + 33) != 2) )
      v20 = 27;
    v21 = v14[v20];
    v111 = v21;
    if ( v9 )
      _RxReleaseFcb(0, v8, v18, v19, (ULONG)v106);
    else
      ExReleaseResourceLite(v8->Header.Resource);
    if ( v13 )
      break;
    v109 = (_DWORD *)((char *)v21 + 24);
    v110 = (_DWORD *)((char *)v21 + 20);
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
LABEL_28:
          LOBYTE(v22) = 1;
          RxWaitForStableCondition(Condition, (PLIST_ENTRY)v14 + 12, (PRX_CONTEXT)(v14 + 25), v22);
        }
        while ( v23 );
        v24 = (_QWORD *)(*(_QWORD *)v14[29]
                       + (unsigned int)(*((_DWORD *)v14[29] + 5)
                                      * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v14[29] + 6))));
        _m_prefetchw(v24);
        v25 = *v24 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( v25 == _InterlockedCompareExchange64(v24, v25 + 2, v25) )
          break;
        v47 = *v24;
        while ( (v47 & 1) == 0 )
        {
          v48 = v47;
          v47 = _InterlockedCompareExchange64(v24, v47 + 2, v47);
          if ( v48 == v47 )
            goto LABEL_30;
        }
      }
LABEL_30:
      v22 = (NTSTATUS *)((char *)v21 + 24);
      v17 = 1;
      v26 = (_QWORD *)(*(_QWORD *)v21 + (unsigned int)(*v110 * (HIDWORD(KeGetPcr()[1].LockArray) % *v109)));
      _m_prefetchw(v26);
      v27 = *v26 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v27 == _InterlockedCompareExchange64(v26, v27 + 2, v27) )
        break;
      v49 = *v26;
      while ( (v49 & 1) == 0 )
      {
        v97 = v49;
        v49 = _InterlockedCompareExchange64(v26, v49 + 2, v49);
        if ( v97 == v49 )
          goto LABEL_31;
      }
      v50 = v14[29];
      v51 = (signed __int64 *)(*(_QWORD *)v50
                             + (unsigned int)(*((_DWORD *)v50 + 5)
                                            * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v50 + 6))));
      _m_prefetchw(v51);
      v52 = *v51 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v52 != _InterlockedCompareExchange64(v51, v52 - 2, v52) )
      {
        for ( i = *v51; ; i = *v54 )
        {
          while ( (i & 1) == 0 )
          {
            v98 = i;
            i = _InterlockedCompareExchange64(v51, i - 2, i);
            if ( v98 == i )
              goto LABEL_28;
          }
          if ( i != 1 )
            break;
          v54 = *(signed __int64 **)v50;
          if ( v51 == *(signed __int64 **)v50 )
            __int2c();
          v51 = *(signed __int64 **)v50;
          _m_prefetchw(v54);
        }
        RfsDecrementRundownWaitBlockCount(i & 0xFFFFFFFFFFFFFFFEuLL, v51);
      }
    }
LABEL_31:
    v13 = a3;
    v7 = 1;
    v8 = MrxFcb;
LABEL_32:
    if ( v9 )
    {
      if ( _RxAcquireFcb((PFCB)v8, v9, 2u, v13, v106, v107) )
      {
LABEL_34:
        v29 = (signed __int64 *)(*(_QWORD *)v21 + (unsigned int)(*v110 * (HIDWORD(KeGetPcr()[1].LockArray) % *v109)));
        _m_prefetchw(v29);
        v30 = *v29 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( v30 != _InterlockedCompareExchange64(v29, v30 - 2, v30) )
        {
          for ( j = *v29; ; j = *v83 )
          {
            while ( (j & 1) == 0 )
            {
              v102 = j;
              j = _InterlockedCompareExchange64(v29, j - 2, j);
              if ( v102 == j )
                goto LABEL_35;
            }
            if ( j != 1 )
              break;
            v83 = *(signed __int64 **)v21;
            if ( v29 == *(signed __int64 **)v21 )
              __int2c();
            v29 = *(signed __int64 **)v21;
            _m_prefetchw(v83);
          }
          RfsDecrementRundownWaitBlockCount(j & 0xFFFFFFFFFFFFFFFEuLL, v29);
        }
LABEL_35:
        v31 = v14[29];
        v7 = 0;
        v32 = (signed __int64 *)(*(_QWORD *)v31
                               + (unsigned int)(*((_DWORD *)v31 + 5)
                                              * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v31 + 6))));
        _m_prefetchw(v32);
        v33 = *v32 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( v33 != _InterlockedCompareExchange64(v32, v33 - 2, v33) )
        {
          for ( k = *v32; ; k = *v85 )
          {
            while ( (k & 1) == 0 )
            {
              v103 = k;
              k = _InterlockedCompareExchange64(v32, k - 2, k);
              if ( v103 == k )
                goto LABEL_36;
            }
            if ( k != 1 )
              break;
            v85 = *(signed __int64 **)v31;
            if ( v32 == *(signed __int64 **)v31 )
              __int2c();
            v32 = *(signed __int64 **)v31;
            _m_prefetchw(v85);
          }
          RfsDecrementRundownWaitBlockCount(k & 0xFFFFFFFFFFFFFFFEuLL, v32);
        }
LABEL_36:
        RxDereference(v14, LHS_LockNotHeld);
        v14 = 0;
        goto LABEL_11;
      }
    }
    else if ( !ExAcquireResourceSharedLite(v8->Header.Resource, v13 == 0) )
    {
      goto LABEL_34;
    }
    v34 = *(struct _KTHREAD ***)&v8->OpenCount;
    v35 = 1;
    if ( v34 == v14 )
    {
      if ( v9 )
        _RxReleaseFcb(0, v8, (ULONG)v34, v28, (ULONG)v106);
      else
        ExReleaseResourceLite(v8->Header.Resource);
      goto LABEL_41;
    }
    v5 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
        v14,
        *(_QWORD *)&v8->OpenCount);
    }
    v60 = (signed __int64 *)(*(_QWORD *)v111
                           + (unsigned int)(*((_DWORD *)v111 + 5)
                                          * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v111 + 6))));
    _m_prefetchw(v60);
    v61 = *v60 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( v61 != _InterlockedCompareExchange64(v60, v61 - 2, v61) )
    {
      for ( m = *v60; ; m = *v66 )
      {
        while ( (m & 1) == 0 )
        {
          v99 = m;
          m = _InterlockedCompareExchange64(v60, m - 2, m);
          if ( v99 == m )
            goto LABEL_89;
        }
        if ( m != 1 )
          break;
        v66 = *(signed __int64 **)v111;
        if ( v60 == *(signed __int64 **)v111 )
          __int2c();
        v60 = *(signed __int64 **)v111;
        _m_prefetchw(v66);
      }
      RfsDecrementRundownWaitBlockCount(m & 0xFFFFFFFFFFFFFFFEuLL, v60);
    }
LABEL_89:
    v62 = v14[29];
    v63 = (signed __int64 *)(*(_QWORD *)v62
                           + (unsigned int)(*((_DWORD *)v62 + 5)
                                          * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v62 + 6))));
    _m_prefetchw(v63);
    v64 = *v63 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( v64 != _InterlockedCompareExchange64(v63, v64 - 2, v64) )
    {
      for ( n = *v63; ; n = *v68 )
      {
        while ( (n & 1) == 0 )
        {
          v100 = n;
          n = _InterlockedCompareExchange64(v63, n - 2, n);
          if ( v100 == n )
            goto LABEL_90;
        }
        if ( n != 1 )
          break;
        v68 = *(signed __int64 **)v62;
        if ( v63 == *(signed __int64 **)v62 )
          __int2c();
        v63 = *(signed __int64 **)v62;
        _m_prefetchw(v68);
      }
      RfsDecrementRundownWaitBlockCount(n & 0xFFFFFFFFFFFFFFFEuLL, v63);
    }
LABEL_90:
    RxDereference(v14, LHS_LockNotHeld);
    v13 = a3;
  }
  v55 = (_QWORD *)(*(_QWORD *)v14[29]
                 + (unsigned int)(*((_DWORD *)v14[29] + 5)
                                * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v14[29] + 6))));
  _m_prefetchw(v55);
  v56 = *v55 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v56 != _InterlockedCompareExchange64(v55, v56 + 2, v56) )
  {
    v59 = *v55;
    while ( (v59 & 1) == 0 )
    {
      v95 = v59;
      v59 = _InterlockedCompareExchange64(v55, v59 + 2, v59);
      if ( v95 == v59 )
        goto LABEL_80;
    }
    v17 = 0;
    v7 = 0;
    goto LABEL_86;
  }
LABEL_80:
  if ( *((_DWORD *)v14 + 48) != 3 )
    goto LABEL_114;
  v109 = (_DWORD *)((char *)v21 + 24);
  v110 = (_DWORD *)((char *)v21 + 20);
  v57 = (_QWORD *)(*(_QWORD *)v21
                 + (unsigned int)(*((_DWORD *)v21 + 5) * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v21 + 6))));
  _m_prefetchw(v57);
  v58 = *v57 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v58 == _InterlockedCompareExchange64(v57, v58 + 2, v58) )
  {
LABEL_82:
    v17 = 1;
    v7 = 1;
    goto LABEL_32;
  }
  v78 = *v57;
  while ( (v78 & 1) == 0 )
  {
    v96 = v78;
    v78 = _InterlockedCompareExchange64(v57, v78 + 2, v78);
    if ( v96 == v78 )
      goto LABEL_82;
  }
LABEL_114:
  v79 = v14[29];
  v7 = 0;
  v80 = (signed __int64 *)(*(_QWORD *)v79
                         + (unsigned int)(*((_DWORD *)v79 + 5)
                                        * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v79 + 6))));
  _m_prefetchw(v80);
  v81 = *v80 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v81 != _InterlockedCompareExchange64(v80, v81 - 2, v81) )
  {
    for ( ii = *v80; ; ii = *v94 )
    {
      while ( (ii & 1) == 0 )
      {
        v101 = ii;
        ii = _InterlockedCompareExchange64(v80, ii - 2, ii);
        if ( v101 == ii )
          goto LABEL_115;
      }
      if ( ii != 1 )
        break;
      v94 = *(signed __int64 **)v79;
      if ( v80 == *(signed __int64 **)v79 )
        __int2c();
      v80 = *(signed __int64 **)v79;
      _m_prefetchw(v94);
    }
    RfsDecrementRundownWaitBlockCount(ii & 0xFFFFFFFFFFFFFFFEuLL, v80);
  }
LABEL_115:
  v17 = 0;
LABEL_86:
  RxDereference(v14, LHS_LockNotHeld);
  v35 = 0;
LABEL_41:
  v5 = 0;
LABEL_42:
  if ( Condition )
  {
    if ( v35 )
      *((_QWORD *)Condition + 14) = v14;
    if ( v7 )
      *((_DWORD *)Condition + 30) |= 0x40000u;
    if ( v17 )
    {
      v36 = v14[29];
      v37 = (signed __int64 *)(*(_QWORD *)v36
                             + (unsigned int)(*((_DWORD *)v36 + 5)
                                            * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v36 + 6))));
      _m_prefetchw(v37);
      v38 = *v37 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v38 != _InterlockedCompareExchange64(v37, v38 - 2, v38) )
      {
        for ( jj = *v37; ; jj = *v46 )
        {
          while ( (jj & 1) == 0 )
          {
            v104 = jj;
            jj = _InterlockedCompareExchange64(v37, jj - 2, jj);
            if ( v104 == jj )
              goto LABEL_49;
          }
          if ( jj != 1 )
            break;
          v46 = *(signed __int64 **)v36;
          if ( v37 == *(signed __int64 **)v36 )
            __int2c();
          v37 = *(signed __int64 **)v36;
          _m_prefetchw(v46);
        }
        RfsDecrementRundownWaitBlockCount(jj & 0xFFFFFFFFFFFFFFFEuLL, v37);
      }
LABEL_49:
      v17 = 0;
    }
  }
  if ( v7 )
  {
    if ( !Condition )
    {
      CurrentThread = KeGetCurrentThread();
      v70 = v14[31];
      BackTraceHash = 0;
      if ( !v70 || (*((_DWORD *)v70 + 11) & 1) == 0 )
      {
        v9 = v108;
        goto LABEL_53;
      }
      v86 = (KSPIN_LOCK *)((char *)v70 + 48);
      v87 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v70 + 6);
      if ( *(struct _KTHREAD **)v70 == v70 )
        __debugbreak();
      v88 = *(PVOID **)v70;
      if ( *(struct _KTHREAD **)(*(_QWORD *)v70 + 8LL) != v70 )
        goto LABEL_111;
      v89 = *v88;
      if ( *((PVOID **)*v88 + 1) != v88 )
        goto LABEL_111;
      *(_QWORD *)v70 = v89;
      v89[1] = v70;
      _InterlockedIncrement((volatile signed __int32 *)v70 + 10);
      KeReleaseSpinLock((PKSPIN_LOCK)v70 + 6, v87);
      RtlCaptureStackBackTrace(1u, 5u, v88 + 2, &BackTraceHash);
      v88[7] = CurrentThread;
      v75 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v70 + 6);
      v90 = (PVOID **)*((_QWORD *)v70 + 3);
      v91 = (PVOID *)((char *)v70 + 16);
      if ( *v90 != v91 )
LABEL_111:
        __fastfail(3u);
      v88[1] = v90;
      *v88 = v91;
      *v90 = v88;
      v92 = v86;
      v91[1] = v88;
      goto LABEL_150;
    }
    v39 = v14[31];
    BackTraceHash = 0;
    if ( v39 && (*((_DWORD *)v39 + 11) & 1) != 0 )
    {
      v71 = (KSPIN_LOCK *)((char *)v39 + 48);
      v72 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v39 + 6);
      if ( *(struct _KTHREAD **)v39 == v39 )
        __debugbreak();
      v73 = *(PVOID **)v39;
      if ( *(struct _KTHREAD **)(*(_QWORD *)v39 + 8LL) != v39 )
        goto LABEL_111;
      v74 = *v73;
      if ( *((PVOID **)*v73 + 1) != v73 )
        goto LABEL_111;
      *(_QWORD *)v39 = v74;
      v74[1] = v39;
      _InterlockedIncrement((volatile signed __int32 *)v39 + 10);
      KeReleaseSpinLock((PKSPIN_LOCK)v39 + 6, v72);
      RtlCaptureStackBackTrace(1u, 5u, v73 + 2, &BackTraceHash);
      v73[7] = Condition;
      v75 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v39 + 6);
      v76 = (PVOID **)*((_QWORD *)v39 + 3);
      v77 = (PVOID *)((char *)v39 + 16);
      if ( *v76 != v77 )
        goto LABEL_111;
      v73[1] = v76;
      *v73 = v77;
      *v76 = v73;
      v92 = v71;
      v77[1] = v73;
LABEL_150:
      KeReleaseSpinLock(v92, v75);
      v8 = MrxFcb;
      v9 = v108;
    }
  }
LABEL_53:
  if ( v5 )
    RxReleaseFcbForLogicalViewLookup(v9, v8);
  if ( v17 )
  {
    v40 = v14[29];
    v41 = (signed __int64 *)(*(_QWORD *)v40
                           + (unsigned int)(*((_DWORD *)v40 + 5)
                                          * (HIDWORD(KeGetPcr()[1].LockArray) % *((_DWORD *)v40 + 6))));
    _m_prefetchw(v41);
    v42 = *v41 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( v42 != _InterlockedCompareExchange64(v41, v42 - 2, v42) )
    {
      for ( kk = *v41; ; kk = *v44 )
      {
        while ( (kk & 1) == 0 )
        {
          v105 = kk;
          kk = _InterlockedCompareExchange64(v41, kk - 2, kk);
          if ( v105 == kk )
            goto LABEL_11;
        }
        if ( kk != 1 )
          break;
        v44 = *(signed __int64 **)v40;
        if ( v41 == *(signed __int64 **)v40 )
          __int2c();
        v41 = *(signed __int64 **)v40;
        _m_prefetchw(v44);
      }
      RfsDecrementRundownWaitBlockCount(kk & 0xFFFFFFFFFFFFFFFEuLL, v41);
    }
  }
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, v7, v14);
  }
  return v7;
}

```

## disassembly

```asm
0x140008f60  mov     [rsp+arg_10], r8b
0x140008f65  mov     [rsp+Fcb], rdx
0x140008f6a  push    rbx
0x140008f6b  push    rbp
0x140008f6c  push    rsi
0x140008f6d  push    rdi
0x140008f6e  push    r12
0x140008f70  push    r15
0x140008f72  sub     rsp, 78h
0x140008f76  xor     r12b, r12b
0x140008f79  movzx   edi, r9b
0x140008f7d  xor     bpl, bpl
0x140008f80  mov     rsi, rdx
0x140008f83  xor     r15d, r15d
0x140008f86  mov     rbx, rcx
0x140008f89  mov     [rsp+0A8h+var_68], r15
0x140008f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f95  lea     r9, WPP_GLOBAL_Control
0x140008f9c  cmp     rcx, r9
0x140008f9f  jz      short loc_140008FAE
0x140008fa1  test    dword ptr [rcx+2Ch], 400h
0x140008fa8  jnz     loc_140009A3E
0x140008fae  mov     rdx, [rsp+0A8h+arg_20]
0x140008fb6  test    rdx, rdx
0x140008fb9  jz      short loc_140008FBE
0x140008fbb  mov     [rdx], bpl
0x140008fbe  test    dil, dil
0x140008fc1  movzx   edi, [rsp+0A8h+arg_10]
0x140008fc9  jnz     loc_140009A7E
0x140008fcf  cmp     qword ptr [rsi+80h], 0
0x140008fd7  mov     [rsp+0A8h+arg_0], r13
0x140008fdf  mov     [rsp+0A8h+var_38], r14
0x140008fe4  jz      loc_14000908A
0x140008fea  mov     rcx, [rsi+8]; Resource
0x140008fee  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140008ff5  nop     dword ptr [rax+rax+00h]
0x140008ffa  test    al, al
0x140008ffc  jnz     short loc_14000907B
0x140008ffe  xor     r13d, r13d
0x140009001  test    r15, r15
0x140009004  jnz     short loc_14000905F
0x140009006  mov     rcx, [rsi+8]; Resource
0x14000900a  test    dil, dil
0x14000900d  setz    dl; Wait
0x140009010  call    cs:__imp_ExAcquireResourceSharedLite
0x140009017  nop     dword ptr [rax+rax+00h]
0x14000901c  test    al, al
0x14000901e  jnz     short loc_140009078
0x140009020  mov     rcx, cs:WPP_GLOBAL_Control
0x140009027  lea     rax, WPP_GLOBAL_Control
0x14000902e  cmp     rcx, rax
0x140009031  jz      short loc_140009040
0x140009033  test    dword ptr [rcx+2Ch], 400h
0x14000903a  jnz     loc_140009B4D
0x140009040  mov     r14, [rsp+0A8h+var_38]
0x140009045  movzx   eax, bpl
0x140009049  mov     r13, [rsp+0A8h+arg_0]
0x140009051  add     rsp, 78h
0x140009055  pop     r15
0x140009057  pop     r12
0x140009059  pop     rdi
0x14000905a  pop     rsi
0x14000905b  pop     rbp
0x14000905c  pop     rbx
0x14000905d  retn
0x14000905f  movzx   r9d, dil; LineNumber
0x140009063  mov     r8d, 2; Mode
0x140009069  mov     rdx, r15; RxContext
0x14000906c  mov     rcx, rsi; Fcb
0x14000906f  call    __RxAcquireFcb
0x140009074  test    eax, eax
0x140009076  jnz     short loc_140009020
0x140009078  mov     r12b, 1
0x14000907b  mov     rdx, [rsp+0A8h+arg_20]
0x140009083  lea     r9, WPP_GLOBAL_Control
0x14000908a  mov     rcx, [rsi+80h]; Instance
0x140009091  xor     r14b, r14b
0x140009094  mov     r13, rcx
0x140009097  test    rcx, rcx
0x14000909a  jz      loc_140009761
0x1400090a0  mov     rax, gs:188h
0x1400090a9  cmp     rax, [rcx+0F0h]
0x1400090b0  jz      loc_140009826
0x1400090b6  test    r12b, r12b
0x1400090b9  jz      loc_14000978B
0x1400090bf  lea     rbp, WPP_GLOBAL_Control
0x1400090c6  mov     r13, [rsi+80h]
0x1400090cd  test    r13, r13
0x1400090d0  jz      loc_140009735
0x1400090d6  mov     rcx, r13; Instance
0x1400090d9  call    RxReference
0x1400090de  test    rbx, rbx
0x1400090e1  jz      short loc_1400090ED
0x1400090e3  cmp     byte ptr [rbx+20h], 0Ch
0x1400090e7  jz      loc_1400095B2
0x1400090ed  mov     eax, 0D8h
0x1400090f2  mov     r12, [rax+r13]
0x1400090f6  mov     [rsp+0A8h+var_50], r12
0x1400090fb  test    r15, r15
0x1400090fe  jnz     loc_140009833
0x140009104  mov     rcx, [rsi+8]; Resource
0x140009108  call    cs:__imp_ExReleaseResourceLite
0x14000910f  nop     dword ptr [rax+rax+00h]
0x140009114  test    dil, dil
0x140009117  jnz     loc_14000946D
0x14000911d  lea     rcx, [r12+18h]
0x140009122  lea     rax, [r12+14h]
0x140009127  mov     [rsp+0A8h+var_60], rcx
0x14000912c  mov     [rsp+0A8h+var_58], rax
0x140009131  mov     r9b, 1; AsyncStatus
0x140009134  lea     r8, [r13+0C8h]; RxContext
0x14000913b  lea     rdx, [r13+0C0h]; TransitionWaitList
0x140009142  mov     rcx, rbx; Condition
0x140009145  call    RxWaitForStableCondition
0x14000914a  test    eax, eax
0x14000914c  jnz     short loc_140009131
0x14000914e  mov     r8, [r13+0E8h]
0x140009155  xor     edx, edx
0x140009157  mov     eax, gs:1A4h
0x14000915f  div     dword ptr [r8+18h]
0x140009163  imul    edx, [r8+14h]
0x140009168  add     rdx, [r8]
0x14000916b  prefetchw byte ptr [rdx]
0x14000916e  mov     rax, [rdx]
0x140009171  and     rax, 0FFFFFFFFFFFFFFFEh
0x140009175  lea     rcx, [rax+2]
0x140009179  lock cmpxchg [rdx], rcx
0x14000917e  jnz     loc_1400093E9
0x140009184  mov     eax, gs:1A4h
0x14000918c  xor     edx, edx
0x14000918e  mov     r9, [rsp+0A8h+var_60]
0x140009193  mov     r14b, 1
0x140009196  mov     r10, [rsp+0A8h+var_58]
0x14000919b  div     dword ptr [r9]
0x14000919e  imul    edx, [r10]
0x1400091a2  add     rdx, [r12]
0x1400091a6  prefetchw byte ptr [rdx]
0x1400091a9  mov     rax, [rdx]
0x1400091ac  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400091b0  lea     rcx, [rax+2]
0x1400091b4  lock cmpxchg [rdx], rcx
0x1400091b9  jnz     loc_140009404
0x1400091bf  mov     [rsp+0A8h+var_60], r9
0x1400091c4  mov     [rsp+0A8h+var_58], r10
0x1400091c9  movzx   edi, [rsp+0A8h+arg_10]
0x1400091d1  mov     bpl, 1
0x1400091d4  mov     rsi, [rsp+0A8h+Fcb]
0x1400091dc  test    r15, r15
0x1400091df  jnz     loc_140009284
0x1400091e5  mov     rcx, [rsi+8]; Resource
0x1400091e9  test    dil, dil
0x1400091ec  setz    dl; Wait
0x1400091ef  call    cs:__imp_ExAcquireResourceSharedLite
0x1400091f6  nop     dword ptr [rax+rax+00h]
0x1400091fb  test    al, al
0x1400091fd  jnz     loc_1400092A1
0x140009203  mov     eax, gs:1A4h
0x14000920b  xor     edx, edx
0x14000920d  mov     rcx, [rsp+0A8h+var_60]
0x140009212  div     dword ptr [rcx]
0x140009214  mov     rax, [rsp+0A8h+var_58]
0x140009219  imul    edx, [rax]
0x14000921c  add     rdx, [r12]
0x140009220  prefetchw byte ptr [rdx]
0x140009223  mov     rax, [rdx]
0x140009226  and     rax, 0FFFFFFFFFFFFFFFEh
0x14000922a  lea     rcx, [rax-2]
0x14000922e  lock cmpxchg [rdx], rcx
0x140009233  jnz     loc_1400097B0
0x140009239  mov     r8, [r13+0E8h]
0x140009240  xor     edx, edx
0x140009242  mov     eax, gs:1A4h
0x14000924a  xor     bpl, bpl
0x14000924d  div     dword ptr [r8+18h]
0x140009251  imul    edx, [r8+14h]
0x140009256  add     rdx, [r8]
0x140009259  prefetchw byte ptr [rdx]
0x14000925c  mov     rax, [rdx]
0x14000925f  and     rax, 0FFFFFFFFFFFFFFFEh
0x140009263  lea     rcx, [rax-2]
0x140009267  lock cmpxchg [rdx], rcx
0x14000926c  jnz     loc_1400097D9
0x140009272  xor     edx, edx; LockHoldingState
0x140009274  mov     rcx, r13; Instance
0x140009277  call    RxDereference
0x14000927c  xor     r13d, r13d
0x14000927f  jmp     loc_140009020
0x140009284  movzx   r9d, dil; LineNumber
0x140009288  mov     r8d, 2; Mode
0x14000928e  mov     rdx, r15; RxContext
0x140009291  mov     rcx, rsi; Fcb
0x140009294  call    __RxAcquireFcb
0x140009299  test    eax, eax
0x14000929b  jnz     loc_140009203
0x1400092a1  mov     r8, [rsi+80h]; LineNumber
0x1400092a8  mov     dil, 1
0x1400092ab  cmp     r8, r13
0x1400092ae  jnz     loc_14000951E
0x1400092b4  test    r15, r15
0x1400092b7  jnz     loc_140009842
0x1400092bd  mov     rcx, [rsi+8]; Resource
0x1400092c1  call    cs:__imp_ExReleaseResourceLite
0x1400092c8  nop     dword ptr [rax+rax+00h]
0x1400092cd  xor     r12b, r12b
0x1400092d0  test    rbx, rbx
0x1400092d3  jz      short loc_140009328
0x1400092d5  test    dil, dil
0x1400092d8  jz      short loc_1400092DE
0x1400092da  mov     [rbx+70h], r13
0x1400092de  test    bpl, bpl
0x1400092e1  jz      short loc_1400092EA
0x1400092e3  or      dword ptr [rbx+78h], 40000h
0x1400092ea  test    r14b, r14b
0x1400092ed  jz      short loc_140009328
0x1400092ef  mov     r8, [r13+0E8h]
0x1400092f6  xor     edx, edx
0x1400092f8  mov     eax, gs:1A4h
0x140009300  div     dword ptr [r8+18h]
0x140009304  imul    edx, [r8+14h]
0x140009309  add     rdx, [r8]
0x14000930c  prefetchw byte ptr [rdx]
0x14000930f  mov     rax, [rdx]
0x140009312  and     rax, 0FFFFFFFFFFFFFFFEh
0x140009316  lea     rcx, [rax-2]
0x14000931a  lock cmpxchg [rdx], rcx
0x14000931f  jnz     loc_1400093C1
0x140009325  xor     r14b, r14b
0x140009328  test    bpl, bpl
0x14000932b  jz      short loc_140009351
0x14000932d  test    rbx, rbx
0x140009330  jz      loc_140009618
0x140009336  mov     rdi, [r13+0F8h]
0x14000933d  mov     [rsp+0A8h+BackTraceHash], 0
0x140009348  test    rdi, rdi
0x14000934b  jnz     loc_140009646
0x140009351  test    r12b, r12b
0x140009354  jnz     loc_140009B3D
0x14000935a  test    r14b, r14b
0x14000935d  jz      loc_140009020
0x140009363  mov     r8, [r13+0E8h]
0x14000936a  xor     edx, edx
0x14000936c  mov     eax, gs:1A4h
0x140009374  div     dword ptr [r8+18h]
0x140009378  imul    edx, [r8+14h]
0x14000937d  add     rdx, [r8]
0x140009380  prefetchw byte ptr [rdx]
0x140009383  mov     rax, [rdx]
0x140009386  and     rax, 0FFFFFFFFFFFFFFFEh
0x14000938a  lea     rcx, [rax-2]
0x14000938e  lock cmpxchg [rdx], rcx
0x140009393  jz      loc_140009020
0x140009399  mov     rax, [rdx]
0x14000939c  test    al, 1
0x14000939e  jz      loc_140009A2A
0x1400093a4  cmp     rax, 1
0x1400093a8  jnz     loc_1400272F6
0x1400093ae  mov     rax, [r8]
0x1400093b1  cmp     rdx, rax
0x1400093b4  jnz     loc_1400272E8
0x1400093ba  int     2Ch; Windows NT - assertion failure
0x1400093bc  jmp     loc_1400272E8
0x1400093c1  mov     rax, [rdx]
0x1400093c4  test    al, 1
0x1400093c6  jz      loc_140009A16
0x1400093cc  cmp     rax, 1
0x1400093d0  jnz     loc_1400272D6
0x1400093d6  mov     rax, [r8]
0x1400093d9  cmp     rdx, rax
0x1400093dc  jnz     loc_1400272C8
0x1400093e2  int     2Ch; Windows NT - assertion failure
0x1400093e4  jmp     loc_1400272C8
0x1400093e9  mov     rax, [rdx]
0x1400093ec  test    al, 1
0x1400093ee  jnz     loc_140009131
0x1400093f4  lea     rcx, [rax+2]
0x1400093f8  lock cmpxchg [rdx], rcx
0x1400093fd  jnz     short loc_1400093EC
0x1400093ff  jmp     loc_140009184
0x140009404  mov     rax, [rdx]
0x140009407  test    al, 1
0x140009409  jz      loc_14000998A
0x14000940f  mov     r8, [r13+0E8h]
0x140009416  xor     edx, edx
0x140009418  mov     eax, gs:1A4h
0x140009420  div     dword ptr [r8+18h]
0x140009424  imul    edx, [r8+14h]
0x140009429  add     rdx, [r8]
0x14000942c  prefetchw byte ptr [rdx]
0x14000942f  mov     rax, [rdx]
0x140009432  and     rax, 0FFFFFFFFFFFFFFFEh
0x140009436  lea     rcx, [rax-2]
0x14000943a  lock cmpxchg [rdx], rcx
0x14000943f  jz      loc_140009131
0x140009445  mov     rax, [rdx]
0x140009448  test    al, 1
0x14000944a  jz      loc_14000999E
0x140009450  cmp     rax, 1
0x140009454  jnz     loc_140027216
0x14000945a  mov     rax, [r8]
0x14000945d  cmp     rdx, rax
  ... truncated ...
```
