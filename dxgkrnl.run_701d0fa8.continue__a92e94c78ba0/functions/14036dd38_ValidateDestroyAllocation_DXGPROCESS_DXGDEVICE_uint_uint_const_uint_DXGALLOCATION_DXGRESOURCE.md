# ValidateDestroyAllocation(DXGPROCESS *,DXGDEVICE *,uint,uint const *,uint,DXGALLOCATION * *,DXGRESOURCE * *)

- ea: `0x14036dd38`
- end: `0x14036e60e`
- name: `?ValidateDestroyAllocation@@YAJPEAVDXGPROCESS@@PEAVDXGDEVICE@@IPEBIIPEAPEAVDXGALLOCATION@@PEAPEAVDXGRESOURCE@@@Z`
- size: `2262`
- prototype: `__int64 __usercall@<rax>(struct DXGPROCESS *@<rcx>, struct DXGDEVICE *@<rdx>, unsigned int@<r8d>, const unsigned int *@<r9>, unsigned int, struct DXGALLOCATION **, struct DXGRESOURCE **)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1403ccf10`

## callees

- `0x140015448`
- `0x140015618`
- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x1400a0bd0`
- `0x1403181e4`
- `0x14032e980`
- `0x14032fd70`
- `0x14036dd38`
- `0x14036fa30`
- `0x14036fdd0`
- `0x14038cde4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036e0e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036e0e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14036e0db`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14036e0db`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14036e091`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14036e2af`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14036e091`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14036e2af`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14036e00f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14036e2a0`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14036e00f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14036e2a0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036dfe1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e000`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e1ee`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e275`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e291`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036dfe1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e000`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e1ee`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e275`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e291`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14036e0a0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14036e4ba`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14036e0a0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14036e4ba`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14036e435`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14036e517`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14036e435`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14036e517`
- `watchdog!WdLogSingleEntry4` at `0x14036e148`
- `watchdog!WdLogSingleEntry4` at `0x14036e45a`
- `watchdog!WdLogSingleEntry4` at `0x14036e148`
- `watchdog!WdLogSingleEntry4` at `0x14036e45a`
- `watchdog!WdLogSingleEntry2` at `0x14036e549`
- `watchdog!WdLogSingleEntry2` at `0x14036e573`
- `watchdog!WdLogSingleEntry2` at `0x14036e549`
- `watchdog!WdLogSingleEntry2` at `0x14036e573`
- `watchdog!WdLogSingleEntry3` at `0x14036e3e2`
- `watchdog!WdLogSingleEntry3` at `0x14036e40c`
- `watchdog!WdLogSingleEntry3` at `0x14036e4ee`
- `watchdog!WdLogSingleEntry3` at `0x14036e5a0`
- `watchdog!WdLogSingleEntry3` at `0x14036e3e2`
- `watchdog!WdLogSingleEntry3` at `0x14036e40c`
- `watchdog!WdLogSingleEntry3` at `0x14036e4ee`
- `watchdog!WdLogSingleEntry3` at `0x14036e5a0`
- `watchdog!WdLogSingleEntry0` at `0x14036e302`
- `watchdog!WdLogSingleEntry0` at `0x14036e355`
- `watchdog!WdLogSingleEntry0` at `0x14036e5c0`
- `watchdog!WdLogSingleEntry0` at `0x14036e302`
- `watchdog!WdLogSingleEntry0` at `0x14036e355`
- `watchdog!WdLogSingleEntry0` at `0x14036e5c0`

## pseudocode

```c
__int64 __fastcall ValidateDestroyAllocation(
        struct DXGPROCESS *a1,
        struct DXGDEVICE *a2,
        unsigned int a3,
        struct _EX_RUNDOWN_REF *a4,
        unsigned int a5,
        struct DXGALLOCATION **a6,
        struct DXGRESOURCE **a7)
{
  unsigned int v7; // esi
  struct DXGALLOCATION **v8; // r15
  struct DXGPROCESS *v10; // rdi
  struct _EX_RUNDOWN_REF *v11; // rbx
  __int64 v12; // r14
  __int64 v13; // rax
  _QWORD *v14; // rsi
  unsigned int *v15; // r15
  __int64 v16; // r14
  struct DXGRESOURCE **v17; // rax
  __int64 v18; // rdi
  int v19; // edx
  struct DXGALLOCATION *v20; // rdx
  struct DXGALLOCATION *v21; // r8
  struct DXGDEVICE *v22; // r9
  __int64 v23; // rcx
  int v24; // ecx
  int v25; // esi
  unsigned int v26; // r12d
  int v27; // edx
  struct DXGRESOURCE *v28; // rdx
  struct DXGDEVICE *Count; // r9
  int v30; // ecx
  DXGFASTMUTEX *v31; // r14
  ULONG_PTR i; // r8
  unsigned int v33; // ecx
  unsigned int v34; // eax
  int v35; // edx
  struct DXGALLOCATION *v36; // rbx
  DXGPUSHLOCK *v37; // rcx
  unsigned int v39; // r12d
  __int64 v40; // rdi
  struct DXGALLOCATION **v41; // r13
  struct DXGALLOCATION *v42; // r14
  unsigned __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rbx
  unsigned int j; // edi
  struct _EX_RUNDOWN_REF *v47; // rsi
  struct DXGALLOCATION *v48; // [rsp+50h] [rbp-71h] BYREF
  char v49; // [rsp+58h] [rbp-69h]
  char v50; // [rsp+59h] [rbp-68h]
  __int64 v51; // [rsp+60h] [rbp-61h] BYREF
  struct _EX_RUNDOWN_REF *v52; // [rsp+68h] [rbp-59h] BYREF
  struct DXGRESOURCE **v53; // [rsp+70h] [rbp-51h]
  struct _EX_RUNDOWN_REF *v54; // [rsp+78h] [rbp-49h] BYREF
  char v55[8]; // [rsp+80h] [rbp-41h] BYREF
  DXGPUSHLOCK *v56; // [rsp+88h] [rbp-39h]
  int v57; // [rsp+90h] [rbp-31h]
  __int64 v58; // [rsp+98h] [rbp-29h]
  struct DXGALLOCATION **v59; // [rsp+A0h] [rbp-21h]
  _BYTE v60[12]; // [rsp+A8h] [rbp-19h] BYREF

  v7 = 0;
  v8 = a6;
  v10 = a1;
  *(_QWORD *)v60 = a1;
  v54 = a4;
  v11 = 0;
  v12 = a3;
  v52 = 0;
  v59 = a6;
  v53 = a7;
  v50 = 0;
  DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE((DXGHANDLETABLELOCKEXCLUSIVE *)v55, a1);
  LODWORD(v51) = 0;
  if ( (_DWORD)v12 )
  {
    v14 = (_QWORD *)((char *)v10 + 280);
    v15 = (unsigned int *)((char *)v10 + 296);
    v26 = ((unsigned int)v12 >> 6) & 0xFFFFFF;
    if ( v26 < *((_DWORD *)v10 + 74)
      && (((unsigned int)v12 >> 25) & 0x60) == (*(_BYTE *)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF) + 8)
                                              & 0x60)
      && (*(_DWORD *)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF) + 8) & 0x2000) == 0
      && (v27 = *(_DWORD *)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF) + 8) & 0x1F) != 0 )
    {
      if ( v27 == 4 )
      {
        v28 = *(struct DXGRESOURCE **)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF));
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v28 = 0;
      }
    }
    else
    {
      v28 = 0;
    }
    DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v48, v28);
    v11 = (struct _EX_RUNDOWN_REF *)v48;
    v52 = (struct _EX_RUNDOWN_REF *)v48;
    v48 = 0;
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((struct _EX_RUNDOWN_REF **)&v48);
    if ( !v11 )
    {
      WdLogSingleEntry3(3, a2, v12, -1073741811);
      WdLogGlobalForLineNumber = 9497;
      goto LABEL_74;
    }
    if ( v26 < *v15 && (*(_DWORD *)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF) + 8) & 0x4000) != 0 )
    {
      WdLogSingleEntry3(3, a2, v12, -1073741267);
      WdLogGlobalForLineNumber = 9507;
      *(_DWORD *)v60 = 58022139;
      *(_QWORD *)&v60[4] = 4;
      RtlLogUnexpectedCodepath(v60);
      goto LABEL_74;
    }
    Count = (struct DXGDEVICE *)v11[1].Count;
    if ( Count != a2 )
    {
      WdLogSingleEntry4(3, a2, v11, Count, -1073741811);
      WdLogGlobalForLineNumber = 9526;
      DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v48, 0);
      DXGRESOURCEREFERENCE::MoveAssign(&v52, &v48);
      DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((struct _EX_RUNDOWN_REF **)&v48);
      v11 = v52;
      goto LABEL_74;
    }
    if ( v26 < *v15 )
    {
      v30 = *(_DWORD *)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF) + 8);
      if ( (((unsigned int)v12 >> 25) & 0x60) == (*(_BYTE *)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF) + 8)
                                                & 0x60)
        && (v30 & 0x2000) == 0
        && (v30 & 0x1F) != 0 )
      {
        *(_DWORD *)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF) + 8) = v30 | 0x2000;
      }
    }
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v55);
    ExReleaseRundownProtection(v11 + 9);
    v54 = 0;
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(&v54);
    ExReleaseRundownProtection(v11 + 9);
    ExWaitForRundownProtectionRelease(v11 + 9);
    v31 = (DXGFASTMUTEX *)&v11[10];
    DXGFASTMUTEX::Acquire((DXGFASTMUTEX *)&v11[10]);
    DXGPUSHLOCK::AcquireExclusive(v56);
    v57 = 2;
    for ( i = v11[3].Count; i; i = *(_QWORD *)(i + 64) )
    {
      v33 = *(_DWORD *)(i + 16);
      if ( v33 )
      {
        v34 = (v33 >> 6) & 0xFFFFFF;
        if ( v34 < *v15 )
        {
          v35 = *(_DWORD *)(*v14 + 16LL * v34 + 8);
          if ( ((v33 >> 25) & 0x60) == (*(_BYTE *)(*v14 + 16LL * v34 + 8) & 0x60)
            && (v35 & 0x2000) == 0
            && (v35 & 0x1F) != 0 )
          {
            *(_DWORD *)(*v14 + 16LL * v34 + 8) = v35 | 0x2000;
          }
        }
      }
    }
    ExInitializeRundownProtection(v11 + 9);
    ExAcquireRundownProtection(v11 + 9);
    DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v48, (struct DXGRESOURCE *)v11);
    v36 = v48;
    v52 = (struct _EX_RUNDOWN_REF *)v48;
    v48 = 0;
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((struct _EX_RUNDOWN_REF **)&v48);
    v37 = v56;
    v57 = 0;
    *((_QWORD *)v56 + 1) = 0;
    ExReleasePushLockExclusiveEx(v37, 0);
    KeLeaveCriticalRegion();
    DXGFASTMUTEX::Release(v31);
    *v53 = v36;
    goto LABEL_49;
  }
  v49 = 0;
  v58 = 0;
  while ( 1 )
  {
    if ( v7 >= a5 )
    {
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v55);
      for ( j = 0; j < a5; ++j )
      {
        DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v48, v8[j]);
        v47 = (struct _EX_RUNDOWN_REF *)v48;
        v48 = 0;
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v48);
        if ( v47 )
          ExReleaseRundownProtection(v47 + 11);
        *(_QWORD *)v60 = 0;
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v60);
        ExReleaseRundownProtection(v47 + 11);
        ExWaitForRundownProtectionRelease(v47 + 11);
        ExInitializeRundownProtection(v47 + 11);
        DxgkReferenceDxgAllocation((struct DXGALLOCATION *)v47);
        DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v51, (struct DXGALLOCATION *)v47);
        *(_QWORD *)v60 = v51;
        v51 = 0;
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v51);
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v60);
      }
LABEL_49:
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v55);
      DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(&v52);
      return 0;
    }
    v13 = v7;
    v14 = (_QWORD *)((char *)v10 + 280);
    v15 = (unsigned int *)((char *)v10 + 296);
    v16 = *((unsigned int *)&v54->Count + v13);
    v17 = (struct DXGRESOURCE **)((*((_DWORD *)&v54->Count + v13) >> 6) & 0xFFFFFF);
    v53 = v17;
    v18 = 2LL * (unsigned int)v17;
    if ( (unsigned int)v17 < *v15
      && (((unsigned int)v16 >> 25) & 0x60) == (*(_BYTE *)(*v14 + 16LL * (unsigned int)v17 + 8) & 0x60)
      && (*(_DWORD *)(*v14 + 16LL * (unsigned int)v17 + 8) & 0x2000) == 0 )
    {
      v19 = *(_DWORD *)(*v14 + 16LL * (unsigned int)v17 + 8) & 0x1F;
      if ( v19 )
      {
        if ( v19 == 5 )
        {
          v20 = *(struct DXGALLOCATION **)(*v14 + 16LL * (unsigned int)v17);
          goto LABEL_10;
        }
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
      }
    }
    v20 = 0;
LABEL_10:
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v48, v20);
    v21 = v48;
    if ( !v48 )
    {
      WdLogSingleEntry3(3, a2, v16, -1073741811);
      WdLogGlobalForLineNumber = 9605;
      goto LABEL_51;
    }
    if ( (unsigned int)v53 < *v15 && (*(_DWORD *)(*v14 + 8 * v18 + 8) & 0x4000) != 0 )
    {
      WdLogSingleEntry3(3, a2, v16, -1073741267);
      WdLogGlobalForLineNumber = 9615;
      *(_DWORD *)v60 = 58022139;
      *(_QWORD *)&v60[4] = 5;
      RtlLogUnexpectedCodepath(v60);
      goto LABEL_51;
    }
    v22 = (struct DXGDEVICE *)*((_QWORD *)v48 + 1);
    if ( v22 != a2 )
    {
      WdLogSingleEntry4(3, a2, v48, v22, -1073741811);
      WdLogGlobalForLineNumber = 9634;
LABEL_51:
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v48);
      goto LABEL_52;
    }
    if ( !v49 )
    {
      v58 = *((_QWORD *)v48 + 5);
      v49 = 1;
    }
    v23 = *((_QWORD *)v48 + 5);
    if ( v23 != v58 )
    {
      WdLogSingleEntry2(3, a2, -1073741811);
      WdLogGlobalForLineNumber = 9653;
      goto LABEL_51;
    }
    if ( v23 )
      break;
LABEL_18:
    if ( (unsigned int)v53 < *v15 )
    {
      v24 = *(_DWORD *)(*v14 + 8 * v18 + 8);
      if ( (((unsigned int)v16 >> 25) & 0x60) == (*(_BYTE *)(*v14 + 8 * v18 + 8) & 0x60)
        && (v24 & 0x2000) == 0
        && (v24 & 0x1F) != 0 )
      {
        *(_DWORD *)(*v14 + 8 * v18 + 8) = v24 | 0x2000;
        v21 = v48;
      }
    }
    v25 = v51;
    v8 = v59;
    v59[(unsigned int)v51] = v21;
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v48);
    v10 = *(struct DXGPROCESS **)v60;
    v7 = v25 + 1;
    LODWORD(v51) = v7;
  }
  if ( (*(_DWORD *)(v23 + 4) & 1) != 0 )
  {
    WdLogSingleEntry2(3, a2, -1073741811);
    WdLogGlobalForLineNumber = 9667;
    goto LABEL_51;
  }
  if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)(v23 + 72)) )
  {
    *((_DWORD *)v48 + 18) |= 0x100000u;
    v21 = v48;
    goto LABEL_18;
  }
  v50 = 1;
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v48);
LABEL_74:
  if ( v11 )
  {
LABEL_75:
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v55);
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(&v52);
    return 3221225485LL;
  }
  else
  {
LABEL_52:
    v39 = v51;
    v40 = 0;
    if ( (_DWORD)v51 )
    {
      v41 = v59;
      do
      {
        v42 = v41[v40];
        v43 = *((unsigned int *)&v54->Count + v40);
        v44 = (*((_DWORD *)&v54->Count + v40) >> 6) & 0xFFFFFF;
        if ( (unsigned int)v44 < *v15
          && (((unsigned int)v43 >> 25) & 0x60) == (*(_BYTE *)(*v14 + 16 * v44 + 8) & 0x60)
          && (*(_DWORD *)(*v14 + 16 * v44 + 8) & 0x1F) != 0 )
        {
          v45 = 16 * ((v43 >> 6) & 0xFFFFFF);
          if ( (*(_DWORD *)(v45 + *v14 + 8) & 0x2000) == 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 224;
            DxgkLogInternalTriageEvent(
              0,
              262146,
              -1,
              (unsigned int)L"m_pEntryTable[GetIndex(hObject)].Destroyed",
              224,
              0,
              0,
              0,
              0);
          }
          *(_DWORD *)(v45 + *v14 + 8) &= ~0x2000u;
        }
        if ( (*((_DWORD *)v42 + 18) & 0x100000) != 0 )
        {
          ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*((_QWORD *)v42 + 5) + 72LL));
          *((_DWORD *)v42 + 18) &= ~0x100000u;
        }
        v40 = (unsigned int)(v40 + 1);
      }
      while ( (unsigned int)v40 < v39 );
    }
    if ( !v50 )
      goto LABEL_75;
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v55);
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(&v52);
    return 255;
  }
}

```

## disassembly

```asm
0x14036dd38  push    rbp
0x14036dd3a  push    rbx
0x14036dd3b  push    rsi
0x14036dd3c  push    rdi
0x14036dd3d  push    r12
0x14036dd3f  push    r13
0x14036dd41  push    r14
0x14036dd43  push    r15
0x14036dd45  lea     rbp, [rsp-7]
0x14036dd4a  sub     rsp, 0C8h
0x14036dd51  mov     rax, cs:__security_cookie
0x14036dd58  xor     rax, rsp
0x14036dd5b  mov     [rbp+3Fh+var_48], rax
0x14036dd5f  mov     rax, [rbp+3Fh+arg_30]
0x14036dd63  xor     esi, esi
0x14036dd65  mov     r15, [rbp+3Fh+arg_28]
0x14036dd69  mov     r13, rdx
0x14036dd6c  mov     rdi, rcx
0x14036dd6f  mov     [rbp+3Fh+var_58], rcx
0x14036dd73  mov     rdx, rcx; struct DXGPROCESS *
0x14036dd76  mov     [rbp+3Fh+var_88], r9
0x14036dd7a  mov     ebx, esi
0x14036dd7c  mov     r14d, r8d
0x14036dd7f  lea     rcx, [rbp+3Fh+var_80]; this
0x14036dd83  mov     [rbp+3Fh+var_98], rbx
0x14036dd87  mov     [rbp+3Fh+var_60], r15
0x14036dd8b  mov     [rbp+3Fh+var_90], rax
0x14036dd8f  mov     [rbp+3Fh+var_A7], sil
0x14036dd93  call    ??0DXGHANDLETABLELOCKEXCLUSIVE@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE(DXGPROCESS *)
0x14036dd98  mov     dword ptr [rbp+3Fh+var_A0], esi
0x14036dd9b  test    r14d, r14d
0x14036dd9e  jnz     loc_14036DEE4
0x14036dda4  mov     r12d, [rbp+3Fh+arg_20]
0x14036dda8  mov     [rbp+3Fh+var_A8], sil
0x14036ddac  mov     [rbp+3Fh+var_68], rsi
0x14036ddb0  cmp     esi, r12d
0x14036ddb3  jnb     loc_14036E231
0x14036ddb9  mov     rcx, [rbp+3Fh+var_88]
0x14036ddbd  mov     eax, esi
0x14036ddbf  lea     rsi, [rdi+118h]
0x14036ddc6  lea     r15, [rsi+10h]
0x14036ddca  mov     r14d, [rcx+rax*4]
0x14036ddce  mov     eax, r14d
0x14036ddd1  shr     eax, 6
0x14036ddd4  and     eax, 0FFFFFFh
0x14036ddd9  mov     edi, eax
0x14036dddb  mov     [rbp+3Fh+var_90], rax
0x14036dddf  add     rdi, rdi
0x14036dde2  cmp     eax, [r15]
0x14036dde5  jnb     loc_14036E349
0x14036ddeb  mov     r8, [rsi]
0x14036ddee  mov     ecx, r14d
0x14036ddf1  shr     ecx, 19h
0x14036ddf4  and     ecx, 60h
0x14036ddf7  mov     edx, [r8+rdi*8+8]
0x14036ddfc  mov     eax, edx
0x14036ddfe  and     eax, 60h
0x14036de01  cmp     cl, al
0x14036de03  jnz     loc_14036E349
0x14036de09  bt      edx, 0Dh
0x14036de0d  jb      loc_14036E349
0x14036de13  and     edx, 1Fh
0x14036de16  jz      loc_14036E349
0x14036de1c  cmp     edx, 5
0x14036de1f  jnz     loc_14036E2FD
0x14036de25  mov     rdx, [r8+rdi*8]; struct DXGALLOCATION *
0x14036de29  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036de2d  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x14036de32  mov     r8, [rbp+3Fh+var_B0]
0x14036de36  test    r8, r8
0x14036de39  jz      loc_14036E58E
0x14036de3f  mov     rax, [rbp+3Fh+var_90]
0x14036de43  cmp     eax, [r15]
0x14036de46  jnb     short loc_14036DE5B
0x14036de48  mov     rax, [rsi]
0x14036de4b  mov     ecx, [rax+rdi*8+8]
0x14036de4f  shr     ecx, 0Eh
0x14036de52  test    cl, 1
0x14036de55  jnz     loc_14036E4DC
0x14036de5b  mov     r9, [r8+8]
0x14036de5f  cmp     r9, r13
0x14036de62  jnz     loc_14036E137
0x14036de68  cmp     [rbp+3Fh+var_A8], bl
0x14036de6b  jz      loc_14036E49A
0x14036de71  mov     rcx, [r8+28h]
0x14036de75  cmp     rcx, [rbp+3Fh+var_68]
0x14036de79  jnz     loc_14036E564
0x14036de7f  test    rcx, rcx
0x14036de82  jnz     loc_14036E4AB
0x14036de88  mov     rax, [rbp+3Fh+var_90]
0x14036de8c  cmp     eax, [r15]
0x14036de8f  jnb     short loc_14036DEC2
0x14036de91  mov     rdx, [rsi]
0x14036de94  shr     r14d, 19h
0x14036de98  and     r14d, 60h
0x14036de9c  mov     ecx, [rdx+rdi*8+8]
0x14036dea0  mov     eax, ecx
0x14036dea2  and     eax, 60h
0x14036dea5  cmp     r14b, al
0x14036dea8  jnz     short loc_14036DEC2
0x14036deaa  mov     eax, 2000h
0x14036deaf  test    eax, ecx
0x14036deb1  jnz     short loc_14036DEC2
0x14036deb3  test    cl, 1Fh
0x14036deb6  jz      short loc_14036DEC2
0x14036deb8  or      ecx, eax
0x14036deba  mov     [rdx+rdi*8+8], ecx
0x14036debe  mov     r8, [rbp+3Fh+var_B0]
0x14036dec2  mov     esi, dword ptr [rbp+3Fh+var_A0]
0x14036dec5  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036dec9  mov     r15, [rbp+3Fh+var_60]
0x14036decd  mov     [r15+rsi*8], r8
0x14036ded1  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14036ded6  mov     rdi, [rbp+3Fh+var_58]
0x14036deda  inc     esi
0x14036dedc  mov     dword ptr [rbp+3Fh+var_A0], esi
0x14036dedf  jmp     loc_14036DDB0
0x14036dee4  lea     rsi, [rdi+118h]
0x14036deeb  mov     eax, r14d
0x14036deee  shr     eax, 6
0x14036def1  lea     r15, [rsi+10h]
0x14036def5  and     eax, 0FFFFFFh
0x14036defa  mov     edi, eax
0x14036defc  add     rdi, rdi
0x14036deff  mov     r12d, eax
0x14036df02  cmp     eax, [r15]
0x14036df05  jnb     loc_14036E3A4
0x14036df0b  mov     r8, [rsi]
0x14036df0e  mov     ecx, r14d
0x14036df11  shr     ecx, 19h
0x14036df14  and     ecx, 60h
0x14036df17  mov     edx, [r8+rdi*8+8]
0x14036df1c  mov     eax, edx
0x14036df1e  and     eax, 60h
0x14036df21  cmp     cl, al
0x14036df23  jnz     loc_14036E3A4
0x14036df29  bt      edx, 0Dh
0x14036df2d  jb      loc_14036E3A4
0x14036df33  and     edx, 1Fh
0x14036df36  jz      loc_14036E3A4
0x14036df3c  cmp     edx, 4
0x14036df3f  jnz     loc_14036E350
0x14036df45  mov     rdx, [r8+rdi*8]; struct DXGRESOURCE *
0x14036df49  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036df4d  call    ??0DXGRESOURCEREFERENCE@@QEAA@PEAVDXGRESOURCE@@@Z; DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE(DXGRESOURCE *)
0x14036df52  mov     rbx, [rbp+3Fh+var_B0]
0x14036df56  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036df5a  mov     [rbp+3Fh+var_98], rbx
0x14036df5e  mov     [rbp+3Fh+var_B0], 0
0x14036df66  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14036df6b  test    rbx, rbx
0x14036df6e  jz      loc_14036E3D0
0x14036df74  mov     edx, [r15]
0x14036df77  cmp     r12d, edx
0x14036df7a  jnb     short loc_14036DF8F
0x14036df7c  mov     rax, [rsi]
0x14036df7f  mov     ecx, [rax+rdi*8+8]
0x14036df83  shr     ecx, 0Eh
0x14036df86  test    cl, 1
0x14036df89  jnz     loc_14036E3FA
0x14036df8f  mov     r9, [rbx+8]
0x14036df93  cmp     r9, r13
0x14036df96  jnz     loc_14036E446
0x14036df9c  cmp     r12d, edx
0x14036df9f  mov     r12d, 2000h
0x14036dfa5  jnb     short loc_14036DFD1
0x14036dfa7  mov     rdx, [rsi]
0x14036dfaa  shr     r14d, 19h
0x14036dfae  and     r14d, 60h
0x14036dfb2  mov     ecx, [rdx+rdi*8+8]
0x14036dfb6  mov     eax, ecx
0x14036dfb8  and     eax, 60h
0x14036dfbb  cmp     r14b, al
0x14036dfbe  jnz     short loc_14036DFD1
0x14036dfc0  test    r12d, ecx
0x14036dfc3  jnz     short loc_14036DFD1
0x14036dfc5  test    cl, 1Fh
0x14036dfc8  jz      short loc_14036DFD1
0x14036dfca  or      ecx, r12d
0x14036dfcd  mov     [rdx+rdi*8+8], ecx
0x14036dfd1  lea     rcx, [rbp+3Fh+var_80]; this
0x14036dfd5  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14036dfda  lea     rdi, [rbx+48h]
0x14036dfde  mov     rcx, rdi; RunRef
0x14036dfe1  call    cs:__imp_ExReleaseRundownProtection
0x14036dfe8  nop     dword ptr [rax+rax+00h]
0x14036dfed  xor     r13d, r13d
0x14036dff0  lea     rcx, [rbp+3Fh+var_88]; this
0x14036dff4  mov     [rbp+3Fh+var_88], r13
0x14036dff8  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14036dffd  mov     rcx, rdi; RunRef
0x14036e000  call    cs:__imp_ExReleaseRundownProtection
0x14036e007  nop     dword ptr [rax+rax+00h]
0x14036e00c  mov     rcx, rdi; RunRef
0x14036e00f  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14036e016  nop     dword ptr [rax+rax+00h]
0x14036e01b  lea     r14, [rbx+50h]
0x14036e01f  mov     rcx, r14; this
0x14036e022  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x14036e027  mov     rcx, [rbp+3Fh+var_78]; this
0x14036e02b  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x14036e030  mov     [rbp+3Fh+var_70], 2
0x14036e037  mov     r8, [rbx+18h]
0x14036e03b  test    r8, r8
0x14036e03e  jz      short loc_14036E08E
0x14036e040  mov     ecx, [r8+10h]
0x14036e044  test    ecx, ecx
0x14036e046  jnz     short loc_14036E04E
0x14036e048  mov     r8, [r8+40h]
0x14036e04c  jmp     short loc_14036E03B
0x14036e04e  mov     eax, ecx
0x14036e050  shr     eax, 6
0x14036e053  and     eax, 0FFFFFFh
0x14036e058  cmp     eax, [r15]
0x14036e05b  jnb     short loc_14036E048
0x14036e05d  mov     r10, [rsi]
0x14036e060  mov     r9d, eax
0x14036e063  add     r9, r9
0x14036e066  shr     ecx, 19h
0x14036e069  and     ecx, 60h
0x14036e06c  mov     edx, [r10+r9*8+8]
0x14036e071  mov     eax, edx
0x14036e073  and     eax, 60h
0x14036e076  cmp     cl, al
0x14036e078  jnz     short loc_14036E048
0x14036e07a  test    r12d, edx
0x14036e07d  jnz     short loc_14036E048
0x14036e07f  test    dl, 1Fh
0x14036e082  jz      short loc_14036E048
0x14036e084  or      edx, r12d
0x14036e087  mov     [r10+r9*8+8], edx
0x14036e08c  jmp     short loc_14036E048
0x14036e08e  mov     rcx, rdi; RunRef
0x14036e091  call    cs:__imp_ExInitializeRundownProtection
0x14036e098  nop     dword ptr [rax+rax+00h]
0x14036e09d  mov     rcx, rdi; RunRef
0x14036e0a0  call    cs:__imp_ExAcquireRundownProtection
0x14036e0a7  nop     dword ptr [rax+rax+00h]
0x14036e0ac  mov     rdx, rbx; struct DXGRESOURCE *
0x14036e0af  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036e0b3  call    ??0DXGRESOURCEREFERENCE@@QEAA@PEAVDXGRESOURCE@@@Z; DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE(DXGRESOURCE *)
0x14036e0b8  mov     rbx, [rbp+3Fh+var_B0]
0x14036e0bc  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036e0c0  mov     [rbp+3Fh+var_98], rbx
0x14036e0c4  mov     [rbp+3Fh+var_B0], r13
0x14036e0c8  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14036e0cd  mov     rcx, [rbp+3Fh+var_78]
0x14036e0d1  xor     edx, edx
0x14036e0d3  mov     [rbp+3Fh+var_70], r13d
0x14036e0d7  mov     [rcx+8], r13
0x14036e0db  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14036e0e2  nop     dword ptr [rax+rax+00h]
0x14036e0e7  call    cs:__imp_KeLeaveCriticalRegion
0x14036e0ee  nop     dword ptr [rax+rax+00h]
0x14036e0f3  mov     rcx, r14; this
0x14036e0f6  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x14036e0fb  mov     rax, [rbp+3Fh+var_90]
0x14036e0ff  mov     [rax], rbx
0x14036e102  lea     rcx, [rbp+3Fh+var_80]; this
0x14036e106  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14036e10b  lea     rcx, [rbp+3Fh+var_98]; this
0x14036e10f  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14036e114  xor     eax, eax
0x14036e116  mov     rcx, [rbp+3Fh+var_48]
0x14036e11a  xor     rcx, rsp; StackCookie
0x14036e11d  call    __security_check_cookie
0x14036e122  add     rsp, 0C8h
0x14036e129  pop     r15
0x14036e12b  pop     r14
0x14036e12d  pop     r13
0x14036e12f  pop     r12
0x14036e131  pop     rdi
0x14036e132  pop     rsi
0x14036e133  pop     rbx
0x14036e134  pop     rbp
0x14036e135  retn
0x14036e137  mov     rdx, r13
0x14036e13a  mov     [rsp+100h+var_E0], 0FFFFFFFFC000000Dh
0x14036e143  mov     ecx, 3
0x14036e148  call    cs:__imp_WdLogSingleEntry4
0x14036e14f  nop     dword ptr [rax+rax+00h]
0x14036e154  mov     cs:WdLogGlobalForLineNumber, 25A2h
0x14036e15e  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036e162  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14036e167  mov     r12d, dword ptr [rbp+3Fh+var_A0]
0x14036e16b  xor     edi, edi
0x14036e16d  test    r12d, r12d
0x14036e170  jz      loc_14036E20B
0x14036e176  mov     r13, [rbp+3Fh+var_60]
0x14036e17a  mov     rcx, [rbp+3Fh+var_88]
0x14036e17e  mov     r14, [r13+rdi*8+0]
0x14036e183  mov     ebx, [rcx+rdi*4]
0x14036e186  mov     eax, ebx
0x14036e188  shr     eax, 6
0x14036e18b  and     eax, 0FFFFFFh
0x14036e190  cmp     eax, [r15]
0x14036e193  jnb     short loc_14036E1DC
0x14036e195  mov     r8, [rsi]
0x14036e198  add     rax, rax
0x14036e19b  mov     ecx, ebx
  ... truncated ...
```
