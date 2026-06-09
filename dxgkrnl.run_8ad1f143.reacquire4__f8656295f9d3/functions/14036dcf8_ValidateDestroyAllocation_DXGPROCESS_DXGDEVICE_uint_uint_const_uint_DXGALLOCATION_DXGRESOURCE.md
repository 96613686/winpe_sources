# ValidateDestroyAllocation(DXGPROCESS *,DXGDEVICE *,uint,uint const *,uint,DXGALLOCATION * *,DXGRESOURCE * *)

- ea: `0x14036dcf8`
- end: `0x14036e5ce`
- name: `?ValidateDestroyAllocation@@YAJPEAVDXGPROCESS@@PEAVDXGDEVICE@@IPEBIIPEAPEAVDXGALLOCATION@@PEAPEAVDXGRESOURCE@@@Z`
- size: `2262`
- prototype: `__int64 __usercall@<rax>(struct DXGPROCESS *@<rcx>, struct DXGDEVICE *@<rdx>, unsigned int@<r8d>, const unsigned int *@<r9>, unsigned int, struct DXGALLOCATION **, struct DXGRESOURCE **)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1403ccaf0`

## callees

- `0x140015288`
- `0x140015458`
- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x1400a0100`
- `0x140311474`
- `0x140327c10`
- `0x140329000`
- `0x14036dcf8`
- `0x14036f9f0`
- `0x14036fd90`
- `0x14038dd14`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036e0a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036e0a7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14036e09b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14036e09b`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14036e051`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14036e26f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14036e051`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14036e26f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14036dfcf`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14036e260`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14036dfcf`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14036e260`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036dfa1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036dfc0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e1ae`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e235`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e251`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036dfa1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036dfc0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e1ae`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e235`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e251`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14036e060`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14036e47a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14036e060`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14036e47a`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14036e3f5`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14036e4d7`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14036e3f5`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14036e4d7`
- `watchdog!WdLogSingleEntry4` at `0x14036e108`
- `watchdog!WdLogSingleEntry4` at `0x14036e41a`
- `watchdog!WdLogSingleEntry4` at `0x14036e108`
- `watchdog!WdLogSingleEntry4` at `0x14036e41a`
- `watchdog!WdLogSingleEntry2` at `0x14036e509`
- `watchdog!WdLogSingleEntry2` at `0x14036e533`
- `watchdog!WdLogSingleEntry2` at `0x14036e509`
- `watchdog!WdLogSingleEntry2` at `0x14036e533`
- `watchdog!WdLogSingleEntry3` at `0x14036e3a2`
- `watchdog!WdLogSingleEntry3` at `0x14036e3cc`
- `watchdog!WdLogSingleEntry3` at `0x14036e4ae`
- `watchdog!WdLogSingleEntry3` at `0x14036e560`
- `watchdog!WdLogSingleEntry3` at `0x14036e3a2`
- `watchdog!WdLogSingleEntry3` at `0x14036e3cc`
- `watchdog!WdLogSingleEntry3` at `0x14036e4ae`
- `watchdog!WdLogSingleEntry3` at `0x14036e560`
- `watchdog!WdLogSingleEntry0` at `0x14036e2c2`
- `watchdog!WdLogSingleEntry0` at `0x14036e315`
- `watchdog!WdLogSingleEntry0` at `0x14036e580`
- `watchdog!WdLogSingleEntry0` at `0x14036e2c2`
- `watchdog!WdLogSingleEntry0` at `0x14036e315`
- `watchdog!WdLogSingleEntry0` at `0x14036e580`

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
      WdLogGlobalForLineNumber = 9471;
      goto LABEL_74;
    }
    if ( v26 < *v15 && (*(_DWORD *)(*v14 + 16LL * (((unsigned int)v12 >> 6) & 0xFFFFFF) + 8) & 0x4000) != 0 )
    {
      WdLogSingleEntry3(3, a2, v12, -1073741267);
      WdLogGlobalForLineNumber = 9481;
      *(_DWORD *)v60 = 58022139;
      *(_QWORD *)&v60[4] = 4;
      RtlLogUnexpectedCodepath(v60);
      goto LABEL_74;
    }
    Count = (struct DXGDEVICE *)v11[1].Count;
    if ( Count != a2 )
    {
      WdLogSingleEntry4(3, a2, v11, Count, -1073741811);
      WdLogGlobalForLineNumber = 9500;
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
      WdLogGlobalForLineNumber = 9579;
      goto LABEL_51;
    }
    if ( (unsigned int)v53 < *v15 && (*(_DWORD *)(*v14 + 8 * v18 + 8) & 0x4000) != 0 )
    {
      WdLogSingleEntry3(3, a2, v16, -1073741267);
      WdLogGlobalForLineNumber = 9589;
      *(_DWORD *)v60 = 58022139;
      *(_QWORD *)&v60[4] = 5;
      RtlLogUnexpectedCodepath(v60);
      goto LABEL_51;
    }
    v22 = (struct DXGDEVICE *)*((_QWORD *)v48 + 1);
    if ( v22 != a2 )
    {
      WdLogSingleEntry4(3, a2, v48, v22, -1073741811);
      WdLogGlobalForLineNumber = 9608;
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
      WdLogSingleEntry2(3, a2);
      WdLogGlobalForLineNumber = 9627;
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
    WdLogSingleEntry2(3, a2);
    WdLogGlobalForLineNumber = 9641;
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
0x14036dcf8  push    rbp
0x14036dcfa  push    rbx
0x14036dcfb  push    rsi
0x14036dcfc  push    rdi
0x14036dcfd  push    r12
0x14036dcff  push    r13
0x14036dd01  push    r14
0x14036dd03  push    r15
0x14036dd05  lea     rbp, [rsp-7]
0x14036dd0a  sub     rsp, 0C8h
0x14036dd11  mov     rax, cs:__security_cookie
0x14036dd18  xor     rax, rsp
0x14036dd1b  mov     [rbp+3Fh+var_48], rax
0x14036dd1f  mov     rax, [rbp+3Fh+arg_30]
0x14036dd23  xor     esi, esi
0x14036dd25  mov     r15, [rbp+3Fh+arg_28]
0x14036dd29  mov     r13, rdx
0x14036dd2c  mov     rdi, rcx
0x14036dd2f  mov     [rbp+3Fh+var_58], rcx
0x14036dd33  mov     rdx, rcx; struct DXGPROCESS *
0x14036dd36  mov     [rbp+3Fh+var_88], r9
0x14036dd3a  mov     ebx, esi
0x14036dd3c  mov     r14d, r8d
0x14036dd3f  lea     rcx, [rbp+3Fh+var_80]; this
0x14036dd43  mov     [rbp+3Fh+var_98], rbx
0x14036dd47  mov     [rbp+3Fh+var_60], r15
0x14036dd4b  mov     [rbp+3Fh+var_90], rax
0x14036dd4f  mov     [rbp+3Fh+var_A7], sil
0x14036dd53  call    ??0DXGHANDLETABLELOCKEXCLUSIVE@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE(DXGPROCESS *)
0x14036dd58  mov     dword ptr [rbp+3Fh+var_A0], esi
0x14036dd5b  test    r14d, r14d
0x14036dd5e  jnz     loc_14036DEA4
0x14036dd64  mov     r12d, [rbp+3Fh+arg_20]
0x14036dd68  mov     [rbp+3Fh+var_A8], sil
0x14036dd6c  mov     [rbp+3Fh+var_68], rsi
0x14036dd70  cmp     esi, r12d
0x14036dd73  jnb     loc_14036E1F1
0x14036dd79  mov     rcx, [rbp+3Fh+var_88]
0x14036dd7d  mov     eax, esi
0x14036dd7f  lea     rsi, [rdi+118h]
0x14036dd86  lea     r15, [rsi+10h]
0x14036dd8a  mov     r14d, [rcx+rax*4]
0x14036dd8e  mov     eax, r14d
0x14036dd91  shr     eax, 6
0x14036dd94  and     eax, 0FFFFFFh
0x14036dd99  mov     edi, eax
0x14036dd9b  mov     [rbp+3Fh+var_90], rax
0x14036dd9f  add     rdi, rdi
0x14036dda2  cmp     eax, [r15]
0x14036dda5  jnb     loc_14036E309
0x14036ddab  mov     r8, [rsi]
0x14036ddae  mov     ecx, r14d
0x14036ddb1  shr     ecx, 19h
0x14036ddb4  and     ecx, 60h
0x14036ddb7  mov     edx, [r8+rdi*8+8]
0x14036ddbc  mov     eax, edx
0x14036ddbe  and     eax, 60h
0x14036ddc1  cmp     cl, al
0x14036ddc3  jnz     loc_14036E309
0x14036ddc9  bt      edx, 0Dh
0x14036ddcd  jb      loc_14036E309
0x14036ddd3  and     edx, 1Fh
0x14036ddd6  jz      loc_14036E309
0x14036dddc  cmp     edx, 5
0x14036dddf  jnz     loc_14036E2BD
0x14036dde5  mov     rdx, [r8+rdi*8]; struct DXGALLOCATION *
0x14036dde9  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036dded  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x14036ddf2  mov     r8, [rbp+3Fh+var_B0]
0x14036ddf6  test    r8, r8
0x14036ddf9  jz      loc_14036E54E
0x14036ddff  mov     rax, [rbp+3Fh+var_90]
0x14036de03  cmp     eax, [r15]
0x14036de06  jnb     short loc_14036DE1B
0x14036de08  mov     rax, [rsi]
0x14036de0b  mov     ecx, [rax+rdi*8+8]
0x14036de0f  shr     ecx, 0Eh
0x14036de12  test    cl, 1
0x14036de15  jnz     loc_14036E49C
0x14036de1b  mov     r9, [r8+8]
0x14036de1f  cmp     r9, r13
0x14036de22  jnz     loc_14036E0F7
0x14036de28  cmp     [rbp+3Fh+var_A8], bl
0x14036de2b  jz      loc_14036E45A
0x14036de31  mov     rcx, [r8+28h]
0x14036de35  cmp     rcx, [rbp+3Fh+var_68]
0x14036de39  jnz     loc_14036E524
0x14036de3f  test    rcx, rcx
0x14036de42  jnz     loc_14036E46B
0x14036de48  mov     rax, [rbp+3Fh+var_90]
0x14036de4c  cmp     eax, [r15]
0x14036de4f  jnb     short loc_14036DE82
0x14036de51  mov     rdx, [rsi]
0x14036de54  shr     r14d, 19h
0x14036de58  and     r14d, 60h
0x14036de5c  mov     ecx, [rdx+rdi*8+8]
0x14036de60  mov     eax, ecx
0x14036de62  and     eax, 60h
0x14036de65  cmp     r14b, al
0x14036de68  jnz     short loc_14036DE82
0x14036de6a  mov     eax, 2000h
0x14036de6f  test    eax, ecx
0x14036de71  jnz     short loc_14036DE82
0x14036de73  test    cl, 1Fh
0x14036de76  jz      short loc_14036DE82
0x14036de78  or      ecx, eax
0x14036de7a  mov     [rdx+rdi*8+8], ecx
0x14036de7e  mov     r8, [rbp+3Fh+var_B0]
0x14036de82  mov     esi, dword ptr [rbp+3Fh+var_A0]
0x14036de85  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036de89  mov     r15, [rbp+3Fh+var_60]
0x14036de8d  mov     [r15+rsi*8], r8
0x14036de91  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14036de96  mov     rdi, [rbp+3Fh+var_58]
0x14036de9a  inc     esi
0x14036de9c  mov     dword ptr [rbp+3Fh+var_A0], esi
0x14036de9f  jmp     loc_14036DD70
0x14036dea4  lea     rsi, [rdi+118h]
0x14036deab  mov     eax, r14d
0x14036deae  shr     eax, 6
0x14036deb1  lea     r15, [rsi+10h]
0x14036deb5  and     eax, 0FFFFFFh
0x14036deba  mov     edi, eax
0x14036debc  add     rdi, rdi
0x14036debf  mov     r12d, eax
0x14036dec2  cmp     eax, [r15]
0x14036dec5  jnb     loc_14036E364
0x14036decb  mov     r8, [rsi]
0x14036dece  mov     ecx, r14d
0x14036ded1  shr     ecx, 19h
0x14036ded4  and     ecx, 60h
0x14036ded7  mov     edx, [r8+rdi*8+8]
0x14036dedc  mov     eax, edx
0x14036dede  and     eax, 60h
0x14036dee1  cmp     cl, al
0x14036dee3  jnz     loc_14036E364
0x14036dee9  bt      edx, 0Dh
0x14036deed  jb      loc_14036E364
0x14036def3  and     edx, 1Fh
0x14036def6  jz      loc_14036E364
0x14036defc  cmp     edx, 4
0x14036deff  jnz     loc_14036E310
0x14036df05  mov     rdx, [r8+rdi*8]; struct DXGRESOURCE *
0x14036df09  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036df0d  call    ??0DXGRESOURCEREFERENCE@@QEAA@PEAVDXGRESOURCE@@@Z; DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE(DXGRESOURCE *)
0x14036df12  mov     rbx, [rbp+3Fh+var_B0]
0x14036df16  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036df1a  mov     [rbp+3Fh+var_98], rbx
0x14036df1e  mov     [rbp+3Fh+var_B0], 0
0x14036df26  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14036df2b  test    rbx, rbx
0x14036df2e  jz      loc_14036E390
0x14036df34  mov     edx, [r15]
0x14036df37  cmp     r12d, edx
0x14036df3a  jnb     short loc_14036DF4F
0x14036df3c  mov     rax, [rsi]
0x14036df3f  mov     ecx, [rax+rdi*8+8]
0x14036df43  shr     ecx, 0Eh
0x14036df46  test    cl, 1
0x14036df49  jnz     loc_14036E3BA
0x14036df4f  mov     r9, [rbx+8]
0x14036df53  cmp     r9, r13
0x14036df56  jnz     loc_14036E406
0x14036df5c  cmp     r12d, edx
0x14036df5f  mov     r12d, 2000h
0x14036df65  jnb     short loc_14036DF91
0x14036df67  mov     rdx, [rsi]
0x14036df6a  shr     r14d, 19h
0x14036df6e  and     r14d, 60h
0x14036df72  mov     ecx, [rdx+rdi*8+8]
0x14036df76  mov     eax, ecx
0x14036df78  and     eax, 60h
0x14036df7b  cmp     r14b, al
0x14036df7e  jnz     short loc_14036DF91
0x14036df80  test    r12d, ecx
0x14036df83  jnz     short loc_14036DF91
0x14036df85  test    cl, 1Fh
0x14036df88  jz      short loc_14036DF91
0x14036df8a  or      ecx, r12d
0x14036df8d  mov     [rdx+rdi*8+8], ecx
0x14036df91  lea     rcx, [rbp+3Fh+var_80]; this
0x14036df95  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14036df9a  lea     rdi, [rbx+48h]
0x14036df9e  mov     rcx, rdi; RunRef
0x14036dfa1  call    cs:__imp_ExReleaseRundownProtection
0x14036dfa8  nop     dword ptr [rax+rax+00h]
0x14036dfad  xor     r13d, r13d
0x14036dfb0  lea     rcx, [rbp+3Fh+var_88]; this
0x14036dfb4  mov     [rbp+3Fh+var_88], r13
0x14036dfb8  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14036dfbd  mov     rcx, rdi; RunRef
0x14036dfc0  call    cs:__imp_ExReleaseRundownProtection
0x14036dfc7  nop     dword ptr [rax+rax+00h]
0x14036dfcc  mov     rcx, rdi; RunRef
0x14036dfcf  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14036dfd6  nop     dword ptr [rax+rax+00h]
0x14036dfdb  lea     r14, [rbx+50h]
0x14036dfdf  mov     rcx, r14; this
0x14036dfe2  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x14036dfe7  mov     rcx, [rbp+3Fh+var_78]; this
0x14036dfeb  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x14036dff0  mov     [rbp+3Fh+var_70], 2
0x14036dff7  mov     r8, [rbx+18h]
0x14036dffb  test    r8, r8
0x14036dffe  jz      short loc_14036E04E
0x14036e000  mov     ecx, [r8+10h]
0x14036e004  test    ecx, ecx
0x14036e006  jnz     short loc_14036E00E
0x14036e008  mov     r8, [r8+40h]
0x14036e00c  jmp     short loc_14036DFFB
0x14036e00e  mov     eax, ecx
0x14036e010  shr     eax, 6
0x14036e013  and     eax, 0FFFFFFh
0x14036e018  cmp     eax, [r15]
0x14036e01b  jnb     short loc_14036E008
0x14036e01d  mov     r10, [rsi]
0x14036e020  mov     r9d, eax
0x14036e023  add     r9, r9
0x14036e026  shr     ecx, 19h
0x14036e029  and     ecx, 60h
0x14036e02c  mov     edx, [r10+r9*8+8]
0x14036e031  mov     eax, edx
0x14036e033  and     eax, 60h
0x14036e036  cmp     cl, al
0x14036e038  jnz     short loc_14036E008
0x14036e03a  test    r12d, edx
0x14036e03d  jnz     short loc_14036E008
0x14036e03f  test    dl, 1Fh
0x14036e042  jz      short loc_14036E008
0x14036e044  or      edx, r12d
0x14036e047  mov     [r10+r9*8+8], edx
0x14036e04c  jmp     short loc_14036E008
0x14036e04e  mov     rcx, rdi; RunRef
0x14036e051  call    cs:__imp_ExInitializeRundownProtection
0x14036e058  nop     dword ptr [rax+rax+00h]
0x14036e05d  mov     rcx, rdi; RunRef
0x14036e060  call    cs:__imp_ExAcquireRundownProtection
0x14036e067  nop     dword ptr [rax+rax+00h]
0x14036e06c  mov     rdx, rbx; struct DXGRESOURCE *
0x14036e06f  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036e073  call    ??0DXGRESOURCEREFERENCE@@QEAA@PEAVDXGRESOURCE@@@Z; DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE(DXGRESOURCE *)
0x14036e078  mov     rbx, [rbp+3Fh+var_B0]
0x14036e07c  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036e080  mov     [rbp+3Fh+var_98], rbx
0x14036e084  mov     [rbp+3Fh+var_B0], r13
0x14036e088  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14036e08d  mov     rcx, [rbp+3Fh+var_78]
0x14036e091  xor     edx, edx
0x14036e093  mov     [rbp+3Fh+var_70], r13d
0x14036e097  mov     [rcx+8], r13
0x14036e09b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14036e0a2  nop     dword ptr [rax+rax+00h]
0x14036e0a7  call    cs:__imp_KeLeaveCriticalRegion
0x14036e0ae  nop     dword ptr [rax+rax+00h]
0x14036e0b3  mov     rcx, r14; this
0x14036e0b6  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x14036e0bb  mov     rax, [rbp+3Fh+var_90]
0x14036e0bf  mov     [rax], rbx
0x14036e0c2  lea     rcx, [rbp+3Fh+var_80]; this
0x14036e0c6  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14036e0cb  lea     rcx, [rbp+3Fh+var_98]; this
0x14036e0cf  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14036e0d4  xor     eax, eax
0x14036e0d6  mov     rcx, [rbp+3Fh+var_48]
0x14036e0da  xor     rcx, rsp; StackCookie
0x14036e0dd  call    __security_check_cookie
0x14036e0e2  add     rsp, 0C8h
0x14036e0e9  pop     r15
0x14036e0eb  pop     r14
0x14036e0ed  pop     r13
0x14036e0ef  pop     r12
0x14036e0f1  pop     rdi
0x14036e0f2  pop     rsi
0x14036e0f3  pop     rbx
0x14036e0f4  pop     rbp
0x14036e0f5  retn
0x14036e0f7  mov     rdx, r13
0x14036e0fa  mov     [rsp+100h+var_E0], 0FFFFFFFFC000000Dh
0x14036e103  mov     ecx, 3
0x14036e108  call    cs:__imp_WdLogSingleEntry4
0x14036e10f  nop     dword ptr [rax+rax+00h]
0x14036e114  mov     cs:WdLogGlobalForLineNumber, 2588h
0x14036e11e  lea     rcx, [rbp+3Fh+var_B0]; this
0x14036e122  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14036e127  mov     r12d, dword ptr [rbp+3Fh+var_A0]
0x14036e12b  xor     edi, edi
0x14036e12d  test    r12d, r12d
0x14036e130  jz      loc_14036E1CB
0x14036e136  mov     r13, [rbp+3Fh+var_60]
0x14036e13a  mov     rcx, [rbp+3Fh+var_88]
0x14036e13e  mov     r14, [r13+rdi*8+0]
0x14036e143  mov     ebx, [rcx+rdi*4]
0x14036e146  mov     eax, ebx
0x14036e148  shr     eax, 6
0x14036e14b  and     eax, 0FFFFFFh
0x14036e150  cmp     eax, [r15]
0x14036e153  jnb     short loc_14036E19C
0x14036e155  mov     r8, [rsi]
0x14036e158  add     rax, rax
0x14036e15b  mov     ecx, ebx
  ... truncated ...
```
