# CClfsLogFcbPhysical::FlushLog(_CLS_LSN &,IClfsRequestAsync *,ulong,ulong &)

- ea: `0x1400083c0`
- end: `0x140008c04`
- name: `?FlushLog@CClfsLogFcbPhysical@@UEAAJAEAT_CLS_LSN@@PEAUIClfsRequestAsync@@KAEAK@Z`
- size: `2116`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, CLFS_LSN *plsn1@<rdx>, struct IClfsRequestAsync *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400155c0`

## callees

- `0x140001da0`
- `0x140005840`
- `0x140007034`
- `0x1400083c0`
- `0x140008c0c`
- `0x140008c40`
- `0x1400093d0`
- `0x14000a420`
- `0x14000a448`
- `0x14000a4a0`
- `0x14000d6b8`
- `0x140017f20`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400084da`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140008561`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400084da`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140008561`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008b35`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008b35`
- `ntoskrnl!KeClearEvent` at `0x14000872b`
- `ntoskrnl!KeClearEvent` at `0x14000872b`
- `ntoskrnl!KeBugCheckEx` at `0x140008415`
- `ntoskrnl!KeBugCheckEx` at `0x14000844b`
- `ntoskrnl!KeBugCheckEx` at `0x140008476`
- `ntoskrnl!KeBugCheckEx` at `0x1400084a9`
- `ntoskrnl!KeBugCheckEx` at `0x1400086d9`
- `ntoskrnl!KeBugCheckEx` at `0x14000897f`
- `ntoskrnl!KeBugCheckEx` at `0x140008af2`
- `ntoskrnl!KeBugCheckEx` at `0x140008415`
- `ntoskrnl!KeBugCheckEx` at `0x14000844b`
- `ntoskrnl!KeBugCheckEx` at `0x140008476`
- `ntoskrnl!KeBugCheckEx` at `0x1400084a9`
- `ntoskrnl!KeBugCheckEx` at `0x1400086d9`
- `ntoskrnl!KeBugCheckEx` at `0x14000897f`
- `ntoskrnl!KeBugCheckEx` at `0x140008af2`
- `ntoskrnl!KeDelayExecutionThread` at `0x140008ba3`
- `ntoskrnl!KeDelayExecutionThread` at `0x140008ba3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400086ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008872`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400088f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008992`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400086ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008872`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400088f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008992`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008766`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400088ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008930`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400089cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008766`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400088ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008930`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400089cd`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::FlushLog(
        CClfsLogFcbPhysical *this,
        CLFS_LSN *plsn1,
        struct IClfsRequestAsync *a3,
        unsigned int a4,
        CClfsLogFcbPhysical *a5)
{
  char v5; // r13
  NTSTATUS v9; // edi
  unsigned int v10; // r15d
  BOOLEAN v11; // dl
  ULONGLONG ullOffset; // rbx
  unsigned int v13; // edx
  int v14; // r8d
  _QWORD *v15; // r8
  bool v17; // al
  CLFS_LSN *v18; // rbx
  bool v20; // cf
  char v21; // bl
  int ContainerQueue; // eax
  _QWORD *v23; // r13
  _QWORD *v24; // rax
  __int64 v25; // r13
  unsigned int v26; // eax
  KIRQL v27; // bl
  __int64 v28; // rdx
  __int64 v29; // rdx
  KIRQL v30; // bl
  __int64 v31; // rdx
  __int64 v32; // rdx
  struct CClfsAuthContainer *v33; // rbx
  int v34; // eax
  KIRQL v35; // bl
  __int64 v36; // rdx
  __int64 v37; // rdx
  int v38; // eax
  BOOLEAN v40; // [rsp+30h] [rbp-78h]
  char v41; // [rsp+31h] [rbp-77h]
  char v42; // [rsp+32h] [rbp-76h]
  char v43; // [rsp+33h] [rbp-75h]
  KIRQL NewIrql; // [rsp+34h] [rbp-74h]
  KIRQL NewIrqla; // [rsp+34h] [rbp-74h]
  char v46; // [rsp+3Ch] [rbp-6Ch]
  int v47; // [rsp+40h] [rbp-68h]
  struct CClfsAuthContainer *Container; // [rsp+50h] [rbp-58h]
  _QWORD *v49; // [rsp+58h] [rbp-50h]
  _QWORD *v50; // [rsp+60h] [rbp-48h]
  LARGE_INTEGER Interval; // [rsp+68h] [rbp-40h] BYREF
  __int64 v52; // [rsp+70h] [rbp-38h] BYREF
  __int64 v53; // [rsp+78h] [rbp-30h]
  char v54; // [rsp+C8h] [rbp+20h]

  v54 = a4;
  v5 = a4;
  v52 = 0;
  v53 = 0;
  if ( (a4 & 0xFFFFFFF0) != 0 )
    KeBugCheckEx(0xC1F5u, 0x36u, a4, (ULONG_PTR)this, 0);
  v46 = a4 & 1;
  if ( (a4 & 1) != 0 )
  {
    if ( (a4 & 2) != 0 )
      KeBugCheckEx(0xC1F5u, 0x37u, a4, (ULONG_PTR)this, 0);
    if ( a3 )
      KeBugCheckEx(0xC1F5u, 0x38u, a4, (ULONG_PTR)this, 0);
  }
  v47 = a4 & 4;
  if ( (a4 & 4) != 0 && a3 )
    KeBugCheckEx(0xC1F5u, 0x39u, a4, (ULONG_PTR)this, 0);
  v9 = 0;
  v10 = 0;
  v41 = 0;
  v43 = 0;
  *(_DWORD *)a5 = 0;
  v11 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
  v40 = v11;
  ullOffset = CLFS_LSN_NULL.ullOffset;
  if ( this != (CClfsLogFcbPhysical *)-504LL && CLFS_LSN_NULL.ullOffset == *((_QWORD *)this + 63) )
  {
    if ( plsn1 && CLFS_LSN_NULL.ullOffset == plsn1->ullOffset )
    {
LABEL_42:
      v9 = 0;
      goto LABEL_112;
    }
    v13 = 1;
LABEL_16:
    v14 = -1073741811;
    goto LABEL_17;
  }
  if ( ClfsLsnGreater(plsn1, (const CLFS_LSN *)this + 63) )
  {
    v13 = 2;
    goto LABEL_16;
  }
  while ( v9 >= 0 )
  {
    v11 = v40;
    if ( !v40 )
    {
      v11 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
      v40 = v11;
      ullOffset = CLFS_LSN_NULL.ullOffset;
    }
    if ( v47 && v10 < 5 )
    {
      if ( v10 == 4 )
      {
        _InterlockedExchange((volatile __int32 *)this + 336, 0);
        v43 = 1;
        ullOffset = CLFS_LSN_NULL.ullOffset;
      }
      plsn1->ullOffset = ullOffset;
      ullOffset = CLFS_LSN_NULL.ullOffset;
    }
    if ( !plsn1 || ullOffset != plsn1->ullOffset )
    {
      v15 = (_QWORD *)((char *)this + 504);
      if ( this == (CClfsLogFcbPhysical *)-504LL || !plsn1 || *v15 != plsn1->ullOffset )
        goto LABEL_44;
      v17 = this != (CClfsLogFcbPhysical *)-504LL
         && this != (CClfsLogFcbPhysical *)-480LL
         && *v15 == *((_QWORD *)this + 60);
      if ( v17 && !v47 )
        goto LABEL_42;
    }
    *plsn1 = *(CLFS_LSN *)((char *)this + 1376);
LABEL_44:
    v18 = (CLFS_LSN *)((char *)this + 480);
    if ( ClfsLsnLess(plsn1, (const CLFS_LSN *)this + 60) && !v47 )
    {
      *plsn1 = *v18;
      break;
    }
    if ( v46 )
    {
      if ( plsn1 && this != (CClfsLogFcbPhysical *)-480LL && plsn1->ullOffset == v18->ullOffset )
        goto LABEL_53;
    }
    if ( v10 && (*((_DWORD *)this + 91) & 0x1000) != 0 && !v47 )
    {
      *plsn1 = *v18;
      v9 = -1072037848;
      v14 = -1072037848;
      v13 = 3;
      goto LABEL_18;
    }
    v20 = ++v10 < 0xC8;
    if ( v10 == 200 )
    {
      if ( (v5 & 8) != 0 )
        goto LABEL_54;
      v20 = 0;
    }
    if ( !v20 )
      KeBugCheckEx(0xC1F5u, 0x3Au, v10, (ULONG_PTR)this, 0);
    NewIrql = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)this + 120));
    CClfsLogFcbPhysical::AcquireFlushRef(this);
    v41 = 1;
    if ( _InterlockedExchange((volatile __int32 *)this + 333, 1) )
    {
      v42 = 0;
    }
    else
    {
      v42 = 1;
      KeClearEvent(*((PRKEVENT *)this + 170));
      *((_DWORD *)this + 334) = v5 & 2;
      if ( !a3 && !v43 )
        *((_QWORD *)this + 169) = &v52;
    }
    KeReleaseSpinLock(*((PKSPIN_LOCK *)this + 120), NewIrql);
    if ( !v42 )
    {
      if ( !v46 )
        goto LABEL_94;
      v14 = -1073741431;
      v13 = 4;
LABEL_17:
      v9 = v14;
LABEL_18:
      CClfsLogFcbPhysical::SetFlushFailureTag(this, v13, v14);
      break;
    }
    v21 = v46;
    if ( *(_DWORD *)(*((_QWORD *)this + 89) + 232LL) > 1u || v46 || (*((_DWORD *)this + 91) & 0x1000) != 0 )
    {
      ContainerQueue = 0;
      v23 = (_QWORD *)*((_QWORD *)this + 119);
    }
    else
    {
      ContainerQueue = CClfsLogFcbPhysical::CreateContainerQueue(this);
      v23 = (_QWORD *)*((_QWORD *)this + 705);
    }
    v50 = v23;
    NewIrqla = CClfsLogFcbPhysical::SetEarlyFlushStatus(this, ContainerQueue);
    v24 = (_QWORD *)*v23;
    while ( 1 )
    {
      v49 = v24;
      if ( v24 == v23 )
        break;
      v25 = v24[2];
      if ( v21 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64, CLFS_LSN *))(*(_QWORD *)v25 + 8LL))(v25, plsn1) )
          break;
      }
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 16LL))(v25, 0);
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 48LL))(v25);
      Container = CClfsLogFcbPhysical::GetContainer(this, v26);
      if ( !Container )
      {
        v9 = -1072037875;
        v14 = -1072037875;
        v13 = 5;
        goto LABEL_18;
      }
      if ( NewIrqla )
      {
        v27 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)this + 120));
        LOBYTE(v28) = 2;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL))(v25, v28);
        LOBYTE(v29) = 1;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 24LL))(v25, v29);
        KeReleaseSpinLock(*((PKSPIN_LOCK *)this + 120), v27);
LABEL_91:
        v33 = Container;
        goto LABEL_92;
      }
      if ( v21 || (*((_DWORD *)this + 91) & 0x1000) != 0 )
      {
        v35 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)this + 120));
        LOBYTE(v36) = 16;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL))(v25, v36);
        LOBYTE(v37) = 8;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 24LL))(v25, v37);
        KeReleaseSpinLock(*((PKSPIN_LOCK *)this + 120), v35);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 16LL))(v25, 1);
        goto LABEL_91;
      }
      CClfsLogFcbPhysical::AcquireFlushRef(this);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 40LL))(v25);
      v30 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)this + 120));
      LOBYTE(v31) = 16;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL))(v25, v31);
      LOBYTE(v32) = 2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 24LL))(v25, v32);
      KeReleaseSpinLock(*((PKSPIN_LOCK *)this + 120), v30);
      v33 = Container;
      v34 = (**(__int64 (__fastcall ***)(__int64, struct CClfsAuthContainer *))v25)(v25, Container);
      if ( v34 != 259 && v34 )
        KeBugCheckEx(0xC1F5u, 0x3Cu, v34, (ULONG_PTR)this, 0);
LABEL_92:
      (*(void (__fastcall **)(struct CClfsAuthContainer *))(*(_QWORD *)v33 + 8LL))(v33);
      v24 = (_QWORD *)*v49;
      v21 = v46;
      v23 = v50;
    }
    v18 = (CLFS_LSN *)((char *)this + 480);
    v5 = v54;
LABEL_94:
    if ( !v43 )
    {
      if ( a3 )
      {
        (**(void (__fastcall ***)(struct IClfsRequestAsync *))a3)(a3);
        (*(void (__fastcall **)(struct IClfsRequestAsync *, CLFS_LSN *))(*(_QWORD *)a3 + 184LL))(a3, plsn1);
        v38 = (*(__int64 (__fastcall **)(char *, struct IClfsRequestAsync *))(*((_QWORD *)this + 76) + 408LL))(
                (char *)this + 608,
                a3);
        v9 = v38;
        if ( v38 != -1073741431 )
        {
          if ( v38 )
          {
            CClfsLogFcbPhysical::SetFlushFailureTag(this, 6u, v38);
            (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a3 + 8LL))(a3);
          }
          else
          {
            v9 = 259;
          }
          break;
        }
        (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a3 + 8LL))(a3);
LABEL_53:
        *plsn1 = *v18;
LABEL_54:
        v9 = 0;
        break;
      }
      if ( !v40 )
        KeBugCheckEx(0xC1F5u, 0x3Du, (ULONG_PTR)this, 0, 0);
      ClfsReleaseResourceLite((char *)this + 200);
      v40 = 0;
      CClfsLogFcbPhysical::ReleaseFlushRef(this);
      v41 = 0;
      v9 = KeWaitForSingleObject(*((PVOID *)this + 170), Executive, 0, 0, 0);
      if ( v42 )
      {
        v9 = v52;
        *(_DWORD *)a5 = v53;
        if ( v9 < 0 && v47 )
          v10 = 4;
        if ( CClfsLogFcbPhysical::IsRetryableFlushError(a5, v9) && v10 < 0xA )
        {
          Interval.QuadPart = -100000;
          KeDelayExecutionThread(0, 0, &Interval);
          v9 = 0;
        }
      }
      ullOffset = CLFS_LSN_NULL.ullOffset;
      continue;
    }
    break;
  }
  v11 = v40;
LABEL_112:
  if ( v11 )
    ClfsReleaseResourceLite((char *)this + 200);
  if ( v41 )
    CClfsLogFcbPhysical::ReleaseFlushRef(this);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400083c0  mov     rax, rsp
0x1400083c3  mov     [rax+10h], rbx
0x1400083c7  mov     [rax+18h], rsi
0x1400083cb  mov     [rax+20h], r9d
0x1400083cf  mov     [rax+8], rcx
0x1400083d3  push    rdi
0x1400083d4  push    r12
0x1400083d6  push    r13
0x1400083d8  push    r14
0x1400083da  push    r15
0x1400083dc  sub     rsp, 80h
0x1400083e3  mov     r13d, r9d
0x1400083e6  mov     r12, r8
0x1400083e9  mov     r14, rdx
0x1400083ec  mov     rsi, rcx
0x1400083ef  xor     ecx, ecx
0x1400083f1  mov     [rax-38h], rcx
0x1400083f5  mov     [rax-30h], rcx
0x1400083f9  test    r9d, 0FFFFFFF0h
0x140008400  jz      short loc_140008422
0x140008402  mov     r8d, r13d; BugCheckParameter2
0x140008405  mov     [rsp+0A8h+BugCheckParameter4], rcx; BugCheckParameter4
0x14000840a  mov     r9, rsi; BugCheckParameter3
0x14000840d  lea     edx, [rcx+36h]; BugCheckParameter1
0x140008410  mov     ecx, 0C1F5h; BugCheckCode
0x140008415  call    cs:__imp_KeBugCheckEx
0x140008422  mov     eax, r13d
0x140008425  and     eax, 1
0x140008428  mov     [rsp+0A8h+var_6C], eax
0x14000842c  test    al, al
0x14000842e  jz      short loc_140008483
0x140008430  test    r13b, 2
0x140008434  jz      short loc_140008458
0x140008436  mov     r8, r13; BugCheckParameter2
0x140008439  mov     [rsp+0A8h+BugCheckParameter4], rcx; BugCheckParameter4
0x14000843e  mov     r9, rsi; BugCheckParameter3
0x140008441  mov     edx, 37h ; '7'; BugCheckParameter1
0x140008446  mov     ecx, 0C1F5h; BugCheckCode
0x14000844b  call    cs:__imp_KeBugCheckEx
0x140008458  test    al, al
0x14000845a  jz      short loc_140008483
0x14000845c  test    r12, r12
0x14000845f  jz      short loc_140008483
0x140008461  mov     r8, r13; BugCheckParameter2
0x140008464  mov     [rsp+0A8h+BugCheckParameter4], rcx; BugCheckParameter4
0x140008469  mov     r9, rsi; BugCheckParameter3
0x14000846c  mov     edx, 38h ; '8'; BugCheckParameter1
0x140008471  mov     ecx, 0C1F5h; BugCheckCode
0x140008476  call    cs:__imp_KeBugCheckEx
0x140008483  mov     eax, r13d
0x140008486  and     eax, 4
0x140008489  mov     [rsp+0A8h+var_68], eax
0x14000848d  jz      short loc_1400084B6
0x14000848f  test    r12, r12
0x140008492  jz      short loc_1400084B6
0x140008494  mov     r8, r13; BugCheckParameter2
0x140008497  mov     [rsp+0A8h+BugCheckParameter4], rcx; BugCheckParameter4
0x14000849c  mov     r9, rsi; BugCheckParameter3
0x14000849f  mov     edx, 39h ; '9'; BugCheckParameter1
0x1400084a4  mov     ecx, 0C1F5h; BugCheckCode
0x1400084a9  call    cs:__imp_KeBugCheckEx
0x1400084b6  mov     edi, ecx
0x1400084b8  mov     r15d, ecx
0x1400084bb  mov     [rsp+0A8h+var_78], cl
0x1400084bf  mov     [rsp+0A8h+var_77], cl
0x1400084c3  mov     [rsp+0A8h+var_75], cl
0x1400084c7  mov     rax, [rsp+0A8h+arg_20]
0x1400084cf  mov     [rax], ecx
0x1400084d1  lea     rcx, [rsi+0C8h]; Resource
0x1400084d8  mov     dl, 1; Wait
0x1400084da  call    cs:__imp_ExAcquireResourceSharedLite
0x1400084e1  nop     dword ptr [rax+rax+00h]
0x1400084e6  mov     dl, al
0x1400084e8  mov     [rsp+0A8h+var_78], al
0x1400084ec  lea     rax, [rsi+1F8h]
0x1400084f3  mov     rbx, qword ptr cs:CLFS_LSN_NULL
0x1400084fa  test    rax, rax
0x1400084fd  jz      short loc_140008532
0x1400084ff  cmp     rbx, [rax]
0x140008502  jnz     short loc_140008532
0x140008504  test    r14, r14
0x140008507  jz      short loc_140008512
0x140008509  cmp     rbx, [r14]
0x14000850c  jz      loc_140008603
0x140008512  mov     edx, 1; unsigned int
0x140008517  mov     r8d, 0C000000Dh; int
0x14000851d  mov     edi, r8d
0x140008520  mov     [rsp+0A8h+var_70], r8d
0x140008525  mov     rcx, rsi; this
0x140008528  call    ?SetFlushFailureTag@CClfsLogFcbPhysical@@QEAAXKJ@Z; CClfsLogFcbPhysical::SetFlushFailureTag(ulong,long)
0x14000852d  jmp     loc_140008BC1
0x140008532  mov     rdx, rax; plsn2
0x140008535  mov     rcx, r14; plsn1
0x140008538  call    ClfsLsnGreater
0x14000853d  test    al, al
0x14000853f  jz      short loc_140008548
0x140008541  mov     edx, 2
0x140008546  jmp     short loc_140008517
0x140008548  test    edi, edi
0x14000854a  js      loc_140008BC1
0x140008550  mov     dl, [rsp+0A8h+var_78]
0x140008554  test    dl, dl
0x140008556  jnz     short loc_14000857A
0x140008558  mov     dl, 1; Wait
0x14000855a  lea     rcx, [rsi+0C8h]; Resource
0x140008561  call    cs:__imp_ExAcquireResourceSharedLite
0x140008568  nop     dword ptr [rax+rax+00h]
0x14000856d  mov     dl, al
0x14000856f  mov     [rsp+0A8h+var_78], al
0x140008573  mov     rbx, qword ptr cs:CLFS_LSN_NULL
0x14000857a  mov     ecx, [rsp+0A8h+var_68]
0x14000857e  test    ecx, ecx
0x140008580  jz      short loc_1400085B1
0x140008582  cmp     r15d, 5
0x140008586  jnb     short loc_1400085B1
0x140008588  cmp     r15d, 4
0x14000858c  jnz     short loc_1400085A7
0x14000858e  xor     eax, eax
0x140008590  xchg    eax, [rsi+540h]
0x140008596  mov     al, 1
0x140008598  mov     [rsp+0A8h+var_75], al
0x14000859c  mov     [rsp+0A8h+var_64], al
0x1400085a0  mov     rbx, qword ptr cs:CLFS_LSN_NULL
0x1400085a7  mov     [r14], rbx
0x1400085aa  mov     rbx, qword ptr cs:CLFS_LSN_NULL
0x1400085b1  test    r14, r14
0x1400085b4  jz      short loc_1400085BB
0x1400085b6  cmp     rbx, [r14]
0x1400085b9  jz      short loc_14000860E
0x1400085bb  lea     r8, [rsi+1F8h]
0x1400085c2  test    r8, r8
0x1400085c5  jz      short loc_1400085D7
0x1400085c7  test    r14, r14
0x1400085ca  jz      short loc_1400085D7
0x1400085cc  mov     rax, [r14]
0x1400085cf  cmp     [r8], rax
0x1400085d2  setz    al
0x1400085d5  jmp     short loc_1400085D9
0x1400085d7  xor     al, al
0x1400085d9  test    al, al
0x1400085db  jz      short loc_140008618
0x1400085dd  test    r8, r8
0x1400085e0  jz      short loc_1400085F9
0x1400085e2  lea     rax, [rsi+1E0h]
0x1400085e9  test    rax, rax
0x1400085ec  jz      short loc_1400085F9
0x1400085ee  mov     rax, [rax]
0x1400085f1  cmp     [r8], rax
0x1400085f4  setz    al
0x1400085f7  jmp     short loc_1400085FB
0x1400085f9  xor     al, al
0x1400085fb  test    al, al
0x1400085fd  jz      short loc_14000860E
0x1400085ff  test    ecx, ecx
0x140008601  jnz     short loc_14000860E
0x140008603  xor     edi, edi
0x140008605  mov     [rsp+0A8h+var_70], edi
0x140008609  jmp     loc_140008BC5
0x14000860e  mov     rax, [rsi+560h]
0x140008615  mov     [r14], rax
0x140008618  lea     rbx, [rsi+1E0h]
0x14000861f  mov     rdx, rbx; plsn2
0x140008622  mov     rcx, r14; plsn1
0x140008625  call    ClfsLsnLess
0x14000862a  mov     ecx, [rsp+0A8h+var_68]
0x14000862e  test    al, al
0x140008630  jz      short loc_140008641
0x140008632  test    ecx, ecx
0x140008634  jnz     short loc_140008641
0x140008636  mov     rax, [rbx]
0x140008639  mov     [r14], rax
0x14000863c  jmp     loc_140008BC1
0x140008641  cmp     byte ptr [rsp+0A8h+var_6C], 0
0x140008646  jz      short loc_140008674
0x140008648  test    r14, r14
0x14000864b  jz      short loc_14000865D
0x14000864d  test    rbx, rbx
0x140008650  jz      short loc_14000865D
0x140008652  mov     rax, [rbx]
0x140008655  cmp     [r14], rax
0x140008658  setz    al
0x14000865b  jmp     short loc_14000865F
0x14000865d  xor     al, al
0x14000865f  test    al, al
0x140008661  jz      short loc_140008674
0x140008663  mov     rax, [rbx]
0x140008666  mov     [r14], rax
0x140008669  xor     edi, edi
0x14000866b  mov     [rsp+0A8h+var_70], edi
0x14000866f  jmp     loc_140008BC1
0x140008674  test    r15d, r15d
0x140008677  jz      short loc_1400086A3
0x140008679  test    dword ptr [rsi+16Ch], 1000h
0x140008683  jz      short loc_1400086A3
0x140008685  test    ecx, ecx
0x140008687  jnz     short loc_1400086A3
0x140008689  mov     rax, [rbx]
0x14000868c  mov     [r14], rax
0x14000868f  mov     edi, 0C01A0028h
0x140008694  mov     [rsp+0A8h+var_70], edi
0x140008698  mov     r8d, edi
0x14000869b  lea     edx, [rcx+3]
0x14000869e  jmp     loc_140008525
0x1400086a3  inc     r15d
0x1400086a6  mov     [rsp+0A8h+var_60], r15d
0x1400086ab  mov     eax, 0C8h
0x1400086b0  cmp     r15d, eax
0x1400086b3  jnz     short loc_1400086BE
0x1400086b5  test    r13b, 8
0x1400086b9  jnz     short loc_140008669
0x1400086bb  cmp     r15d, eax
0x1400086be  jb      short loc_1400086E5
0x1400086c0  mov     r8d, r15d; BugCheckParameter2
0x1400086c3  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x1400086cc  mov     r9, rsi; BugCheckParameter3
0x1400086cf  mov     edx, 3Ah ; ':'; BugCheckParameter1
0x1400086d4  mov     ecx, 0C1F5h; BugCheckCode
0x1400086d9  call    cs:__imp_KeBugCheckEx
0x1400086e5  mov     rcx, [rsi+3C0h]; SpinLock
0x1400086ec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400086f3  nop     dword ptr [rax+rax+00h]
0x1400086f8  mov     [rsp+0A8h+NewIrql], al
0x1400086fc  mov     rcx, rsi; this
0x1400086ff  call    ?AcquireFlushRef@CClfsLogFcbPhysical@@QEAAKXZ; CClfsLogFcbPhysical::AcquireFlushRef(void)
0x140008704  mov     [rsp+0A8h+var_77], 1
0x140008709  mov     eax, 1
0x14000870e  xchg    eax, [rsi+534h]
0x140008714  test    eax, eax
0x140008716  jz      short loc_14000871F
0x140008718  mov     [rsp+0A8h+var_76], 0
0x14000871d  jmp     short loc_14000875B
0x14000871f  mov     [rsp+0A8h+var_76], 1
0x140008724  mov     rcx, [rsi+550h]; Event
0x14000872b  call    cs:__imp_KeClearEvent
0x140008732  nop     dword ptr [rax+rax+00h]
0x140008737  mov     eax, r13d
0x14000873a  and     eax, 2
0x14000873d  mov     [rsi+538h], eax
0x140008743  test    r12, r12
0x140008746  jnz     short loc_14000875B
0x140008748  cmp     [rsp+0A8h+var_75], r12b
0x14000874d  jnz     short loc_14000875B
0x14000874f  lea     rax, [rsp+0A8h+var_38]
0x140008754  mov     [rsi+548h], rax
0x14000875b  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x14000875f  mov     rcx, [rsi+3C0h]; SpinLock
0x140008766  call    cs:__imp_KeReleaseSpinLock
0x14000876d  nop     dword ptr [rax+rax+00h]
0x140008772  cmp     [rsp+0A8h+var_76], 0
0x140008777  jnz     short loc_140008794
0x140008779  cmp     byte ptr [rsp+0A8h+var_6C], 0
0x14000877e  jz      loc_140008A27
0x140008784  mov     r8d, 0C0000189h
0x14000878a  mov     edx, 4
0x14000878f  jmp     loc_14000851D
0x140008794  mov     rax, [rsi+2C8h]
0x14000879b  mov     ebx, [rsp+0A8h+var_6C]
0x14000879f  cmp     dword ptr [rax+0E8h], 1
0x1400087a6  ja      short loc_1400087C9
0x1400087a8  test    bl, bl
0x1400087aa  jnz     short loc_1400087C9
0x1400087ac  test    dword ptr [rsi+16Ch], 1000h
0x1400087b6  jnz     short loc_1400087C9
0x1400087b8  mov     rcx, rsi; this
0x1400087bb  call    ?CreateContainerQueue@CClfsLogFcbPhysical@@AEAAJXZ; CClfsLogFcbPhysical::CreateContainerQueue(void)
0x1400087c0  mov     r13, [rsi+1608h]
0x1400087c7  jmp     short loc_1400087D2
0x1400087c9  xor     eax, eax
0x1400087cb  mov     r13, [rsi+3B8h]
0x1400087d2  mov     [rsp+0A8h+var_48], r13
0x1400087d7  mov     edx, eax; int
0x1400087d9  mov     rcx, rsi; this
0x1400087dc  call    ?SetEarlyFlushStatus@CClfsLogFcbPhysical@@QEAAEJ@Z; CClfsLogFcbPhysical::SetEarlyFlushStatus(long)
0x1400087e1  mov     [rsp+0A8h+NewIrql], al
0x1400087e5  mov     rax, [r13+0]
0x1400087e9  mov     [rsp+0A8h+var_50], rax
0x1400087ee  cmp     rax, r13
0x1400087f1  jz      loc_140008A18
0x1400087f7  mov     r13, [rax+10h]
0x1400087fb  test    bl, bl
0x1400087fd  jz      short loc_14000881A
0x1400087ff  mov     rax, [r13+0]
0x140008803  mov     rax, [rax+8]
0x140008807  mov     rdx, r14
0x14000880a  mov     rcx, r13
0x14000880d  call    _guard_dispatch_icall
0x140008812  test    al, al
0x140008814  jnz     loc_140008A18
0x14000881a  mov     rax, [r13+0]
0x14000881e  mov     rax, [rax+10h]
0x140008822  xor     edx, edx
0x140008824  mov     rcx, r13
0x140008827  call    _guard_dispatch_icall
0x14000882c  mov     rax, [r13+0]
0x140008830  mov     rax, [rax+30h]
0x140008834  mov     rcx, r13
0x140008837  call    _guard_dispatch_icall
0x14000883c  mov     edx, eax; unsigned int
0x14000883e  mov     rcx, rsi; this
0x140008841  call    ?GetContainer@CClfsLogFcbPhysical@@AEAAPEAVCClfsAuthContainer@@K@Z; CClfsLogFcbPhysical::GetContainer(ulong)
  ... truncated ...
```
