# CDCMPoolManager::ScavangePools(uchar const *,ulong,bool,bool,bool)

- ea: `0x18005f664`
- end: `0x18005fb5d`
- name: `?ScavangePools@CDCMPoolManager@@QEAAJPEBEK_N11@Z`
- size: `1273`
- prototype: `__int64 __usercall@<rax>(CDCMPoolManager *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned int@<r8d>, bool@<r9b>, bool, bool)`
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x18005ecc0`
- `0x18005f380`

## callees

- `0x180013870`
- `0x180026940`
- `0x180029560`
- `0x180029c30`
- `0x18002adb4`
- `0x18003c270`
- `0x18005daa0`
- `0x18005e930`
- `0x18005e9cc`
- `0x18005eab0`
- `0x18005f190`
- `0x18005f484`
- `0x18005f584`
- `0x18005f664`
- `0x180060874`
- `0x180060f1c`
- `0x180063030`
- `0x180064ff4`
- `0x180065670`
- `0x18006c800`
- `0x180087010`

## import_xrefs

- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18005fa47`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18005fa47`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18005fa0e`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18005fa0e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005f729`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005f729`
- `KERNEL32!Sleep` at `0x18005f787`
- `KERNEL32!Sleep` at `0x18005f787`
- `KERNEL32!EnterCriticalSection` at `0x18005fa70`
- `KERNEL32!EnterCriticalSection` at `0x18005fa70`
- `KERNEL32!LeaveCriticalSection` at `0x18005faaf`
- `KERNEL32!LeaveCriticalSection` at `0x18005faaf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18005fa2c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18005fa2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDCMPoolManager::ScavangePools(
        CDCMPoolManager *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        char a4,
        bool a5)
{
  CDCMPoolManager *v5; // r15
  unsigned int v6; // eax
  unsigned int v7; // r12d
  _QWORD *v8; // r13
  __int64 v9; // rcx
  int i; // ebx
  __int64 v11; // rcx
  int v12; // esi
  int v13; // edi
  __int64 PoolPointerNoWait; // rax
  __int64 v15; // rbx
  __int64 DPOPrototype; // rax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  CDCMPool *v20; // rbx
  _QWORD *v21; // rax
  CCMProviderInfoManager *v22; // rbx
  CDCMCreator *v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v27; // ebx
  int v28; // [rsp+28h] [rbp-E0h]
  __int64 v29; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v30; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD *v32; // [rsp+48h] [rbp-C0h]
  __int64 v33; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+70h] [rbp-98h] BYREF
  int v37; // [rsp+78h] [rbp-90h]
  int v38; // [rsp+7Ch] [rbp-8Ch]
  int v39; // [rsp+80h] [rbp-88h] BYREF
  char *v40; // [rsp+88h] [rbp-80h]
  volatile __int32 *v41; // [rsp+90h] [rbp-78h]
  __int64 v42; // [rsp+A0h] [rbp-68h] BYREF
  int v43; // [rsp+A8h] [rbp-60h]
  int v44; // [rsp+ACh] [rbp-5Ch]
  const unsigned __int8 *v45; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v46; // [rsp+B8h] [rbp-50h]
  int v47; // [rsp+BCh] [rbp-4Ch]
  _QWORD v48[9]; // [rsp+C0h] [rbp-48h] BYREF

  v5 = this;
  v33 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1800C9578[0] )
  {
    v6 = HashForTrace(a2, a3);
    bidScopeEnterW(&v33, off_1800C9578[0], v6, v5);
  }
  if ( _PrototypeManager )
  {
    v7 = 0;
    v8 = 0;
    v32 = 0;
    v40 = (char *)v5 + 8;
    v39 = 2;
    AcquireSRWLockExclusive((PSRWLOCK)v5 + 1);
    v41 = (volatile __int32 *)((char *)v5 + 112);
    if ( !_InterlockedExchange((volatile __int32 *)v5 + 28, 0) )
    {
      CAutoRWLock::~CAutoRWLock((CAutoRWLock *)&v39);
      goto LABEL_52;
    }
    if ( a5 )
    {
      v9 = *((_QWORD *)v5 + 10);
      if ( v9 )
      {
        _InterlockedExchange((volatile __int32 *)(v9 + 40), 1);
        _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v5 + 11) + 40LL), 1);
        for ( i = 0; i <= 100; ++i )
        {
          if ( !CDCMPool::sm_cBeingAsynchReleased )
            goto LABEL_18;
          Sleep(CDCMPool::sm_cBeingAsynchReleased);
        }
        if ( (bidGblFlags & 2) != 0 )
          v7 = bidTraceHR(off_1800C8418[0], 463881, L"<CDCMPoolManager::ScavangePools|Trace|HR> ", 2147500037LL);
        else
          v7 = -2147467259;
        CAutoRWLock::~CAutoRWLock((CAutoRWLock *)&v39);
LABEL_49:
        v25 = *((_QWORD *)v5 + 10);
        if ( v25 )
        {
          _InterlockedExchange((volatile __int32 *)(v25 + 40), 0);
          _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v5 + 11) + 40LL), 0);
        }
LABEL_51:
        _InterlockedExchange(v41, 1);
        goto LABEL_52;
      }
    }
LABEL_18:
    v11 = -(__int64)(*((_DWORD *)v5 + 7) != 0);
    v35 = v11;
    v12 = v38;
    v13 = v38;
    try
    {
      while ( 1 )
      {
        if ( !v11 )
          goto LABEL_72;
        v34 = 0;
        v31 = 0;
        v30 = 0;
        TCMHashTableLocked<SDCMKey,CPoolnCS *>::GetNextAssocUnlocked(v5, &v35, v48, &v30);
        v34 = v30;
        PoolPointerNoWait = CPoolnCS::GetPoolPointerNoWait(v30);
        v15 = PoolPointerNoWait;
        v31 = PoolPointerNoWait;
        if ( PoolPointerNoWait )
          break;
LABEL_34:
        ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v31);
        CAutoRefc<CPoolnCS>::~CAutoRefc<CPoolnCS>(&v34);
        v11 = v35;
      }
      DPOPrototype = CDCMPool::GetDPOPrototype(PoolPointerNoWait);
      v48[0] = DPOPrototype;
      if ( (!DPOPrototype || !*(_DWORD *)(DPOPrototype + 848))
        && (!*(_DWORD *)(v15 + 104) && !*(_DWORD *)(v15 + 108) || a5 && !*(_DWORD *)(v15 + 104))
        && (!DPOPrototype || (unsigned __int8)CPrototypeManager::ReleasePrototypeObj(v17, DPOPrototype)) )
      {
        v18 = *(_DWORD *)(v15 + 80);
        v19 = *(_QWORD *)(v15 + 72);
        if ( !a2 )
        {
LABEL_32:
          v36 = v19;
          v37 = v18;
          v38 = v13;
          TCMHashTableLocked<SDCMKey,CPoolnCS *>::RemoveKeyUnlocked(v5, &v36, v30);
          *(_QWORD *)(v15 + 264) = v8;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
          v8 = (_QWORD *)v15;
          v32 = (_QWORD *)v15;
          goto LABEL_33;
        }
        v42 = *(_QWORD *)(v15 + 72);
        v43 = v18;
        v44 = v13;
        v45 = a2;
        v46 = a3;
        v47 = v12;
        if ( !(unsigned __int8)CDCMPoolMap::KeyCompareIsEqual(v5, &v45, &v42) )
        {
          v18 = *(_DWORD *)(v15 + 80);
          v19 = *(_QWORD *)(v15 + 72);
          goto LABEL_32;
        }
      }
LABEL_33:
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(v48);
      goto LABEL_34;
    }
    catch ( long v29 )
    {
      v27 = v29;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v29, L"<CDCMPoolManager::ScavangePools|OLEDB|ERR> ", 0x203u);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800C88E8[0] )
            bidTraceA(off_1800C8418[0], 528384, off_1800C88E8[0], v27);
        }
      }
      v8 = v32;
      v7 = v27;
      v5 = this;
    }
    catch ( ... )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147418113, L"<CDCMPoolManager::ScavangePools|OLEDB|ERR> ", 0x209u);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800C88E0[0] )
            bidTraceA(off_1800C8418[0], 534528, off_1800C88E0[0], 0);
        }
      }
      v8 = v32;
      v7 = -2147418113;
      v5 = this;
    }
LABEL_72:
    while ( v8 )
    {
      v20 = (CDCMPool *)v8;
      v21 = v8 + 33;
      v8 = (_QWORD *)v8[33];
      *v21 = 0;
      CDCMPool::DetachFromHolder(v20);
      (*(void (__fastcall **)(CDCMPool *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    CAutoRWLock::~CAutoRWLock((CAutoRWLock *)&v39);
    if ( a4 && !*((_DWORD *)v5 + 7) )
    {
      CDCMPoolManager::ReleaseDispenserManager(v5);
      CConnStrParsingManager::RemoveAllItems(_ConnStrParsingManager);
      CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)g_rwLockSHA256Init);
      if ( g_fSHA256Inited && g_hAlgSHA256 )
      {
        BCryptCloseAlgorithmProvider(g_hAlgSHA256, 0);
        g_hAlgSHA256 = 0;
        g_fSHA256Inited = 0;
      }
      CReaderWriterLock3AR::WriteUnlock((CReaderWriterLock3AR *)g_rwLockSHA256Init);
      v22 = _ProviderInitInfoMap;
      TCMHashTableLocked<SProviderKey,CCMProviderInfo *>::CleanUpAllHash(_ProviderInitInfoMap);
      TCMHashTableLocked<SProviderKey,CCMProviderInfo *>::CleanUpAllHash((char *)v22 + 56);
      v23 = _DCMNonReusable;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)_DCMNonReusable + 96));
      if ( !*((_DWORD *)v23 + 18) && *((_BYTE *)v23 + 88) )
      {
        CDCMCreator::DetachFromHolder(v23);
        v24 = *((_QWORD *)v23 + 10);
        if ( v24 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          *((_QWORD *)v23 + 10) = 0;
        }
        *((_BYTE *)v23 + 88) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v23 + 96));
    }
    if ( !a5 )
      goto LABEL_51;
    goto LABEL_49;
  }
  v7 = -2147418113;
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_55;
  OLEDBTraceErr(-2147418113, L"<CDCMPoolManager::ScavangePools|OLEDB|ERR> ", 0x19Au);
LABEL_52:
  if ( (bidGblFlags & 2) != 0 && off_1800C9260[0] )
    bidTraceW(off_1800C8418[0], 590848, off_1800C9260[0], v5, v7, v28, v29);
LABEL_55:
  if ( (bidGblFlags & 4) != 0 && v33 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v33);
  return v7;
}

```

## disassembly

```asm
0x18005f664  mov     rax, rsp
0x18005f667  mov     [rax+20h], r9b
0x18005f66b  mov     [rax+18h], r8d
0x18005f66f  mov     [rax+10h], rdx
0x18005f673  mov     [rax+8], rcx
0x18005f677  push    rbx
0x18005f678  push    rsi
0x18005f679  push    rdi
0x18005f67a  push    r12
0x18005f67c  push    r13
0x18005f67e  push    r15
0x18005f680  sub     rsp, 0D8h
0x18005f687  mov     r9d, r8d
0x18005f68a  mov     r8, rdx
0x18005f68d  mov     r15, rcx
0x18005f690  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFFh
0x18005f699  test    byte ptr cs:_bidGblFlags, 4
0x18005f6a0  jz      short loc_18005F6D0
0x18005f6a2  mov     rax, cs:off_1800C9578; "<CDCMPoolManager::ScavangePools> Hash: "...
0x18005f6a9  test    rax, rax
0x18005f6ac  jz      short loc_18005F6D0
0x18005f6ae  mov     edx, r9d; unsigned int
0x18005f6b1  mov     rcx, r8; unsigned __int8 *
0x18005f6b4  call    ?HashForTrace@@YAIPEBEK@Z; HashForTrace(uchar const *,ulong)
0x18005f6b9  mov     rdx, cs:off_1800C9578; "<CDCMPoolManager::ScavangePools> Hash: "...
0x18005f6c0  mov     r9, r15
0x18005f6c3  mov     r8d, eax
0x18005f6c6  lea     rcx, [rsp+108h+var_B8]
0x18005f6cb  call    _bidScopeEnterW
0x18005f6d0  cmp     cs:?_PrototypeManager@@3PEAVCPrototypeManager@@EA, 0; CPrototypeManager * _PrototypeManager
0x18005f6d8  jnz     short loc_18005F707
0x18005f6da  mov     r12d, 8000FFFFh
0x18005f6e0  test    byte ptr cs:_bidGblFlags, 2
0x18005f6e7  jz      loc_18005FB15
0x18005f6ed  mov     r8d, 19Ah; unsigned int
0x18005f6f3  lea     rdx, aCdcmpoolmanage_5; "<CDCMPoolManager::ScavangePools|OLEDB|E"...
0x18005f6fa  mov     ecx, r12d; int
0x18005f6fd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005f702  jmp     loc_18005FAE0
0x18005f707  xor     r12d, r12d
0x18005f70a  xor     r13d, r13d
0x18005f70d  mov     [rsp+108h+var_C0], r13
0x18005f712  lea     rcx, [r15+8]; SRWLock
0x18005f716  mov     [rsp+108h+var_80], rcx
0x18005f71e  mov     [rsp+108h+var_88], 2
0x18005f729  call    cs:__imp_AcquireSRWLockExclusive
0x18005f72f  lea     rax, [r15+70h]
0x18005f733  mov     [rsp+108h+var_78], rax
0x18005f73b  xor     ecx, ecx
0x18005f73d  xchg    ecx, [rax]
0x18005f73f  test    ecx, ecx
0x18005f741  jnz     short loc_18005F755
0x18005f743  lea     rcx, [rsp+108h+var_88]; this
0x18005f74b  call    ??1CAutoRWLock@@QEAA@XZ; CAutoRWLock::~CAutoRWLock(void)
0x18005f750  jmp     loc_18005FAE0
0x18005f755  cmp     [rsp+108h+arg_20], 0
0x18005f75d  jz      short loc_18005F7D8
0x18005f75f  mov     rcx, [r15+50h]
0x18005f763  test    rcx, rcx
0x18005f766  jz      short loc_18005F7D8
0x18005f768  mov     esi, 1
0x18005f76d  mov     eax, esi
0x18005f76f  xchg    eax, [rcx+28h]
0x18005f772  mov     rcx, [r15+58h]
0x18005f776  mov     eax, esi
0x18005f778  xchg    eax, [rcx+28h]
0x18005f77b  xor     ebx, ebx
0x18005f77d  mov     ecx, cs:?sm_cBeingAsynchReleased@CDCMPool@@0KA; dwMilliseconds
0x18005f783  test    ecx, ecx
0x18005f785  jz      short loc_18005F7D8
0x18005f787  call    cs:__imp_Sleep
0x18005f78d  add     ebx, esi
0x18005f78f  cmp     ebx, 64h ; 'd'
0x18005f792  jle     short loc_18005F77D
0x18005f794  test    byte ptr cs:_bidGblFlags, 2
0x18005f79b  jz      short loc_18005F7C0
0x18005f79d  mov     r9d, 80004005h
0x18005f7a3  lea     r8, aCdcmpoolmanage; "<CDCMPoolManager::ScavangePools|Trace|H"...
0x18005f7aa  mov     edx, 71409h
0x18005f7af  mov     rcx, cs:off_1800C8418; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005f7b6  call    _bidTraceHR
0x18005f7bb  mov     r12d, eax
0x18005f7be  jmp     short loc_18005F7C6
0x18005f7c0  mov     r12d, 80004005h
0x18005f7c6  lea     rcx, [rsp+108h+var_88]; this
0x18005f7ce  call    ??1CAutoRWLock@@QEAA@XZ; CAutoRWLock::~CAutoRWLock(void)
0x18005f7d3  jmp     loc_18005FABF
0x18005f7d8  mov     eax, [r15+1Ch]
0x18005f7dc  neg     eax
0x18005f7de  sbb     rcx, rcx
0x18005f7e1  mov     [rsp+108h+var_A8], rcx
0x18005f7e6  mov     esi, [rsp+108h+var_8C]
0x18005f7ea  mov     edi, [rsp+108h+var_8C]
0x18005f7ee  test    rcx, rcx
0x18005f7f1  jz      loc_18005F97E
0x18005f7f7  mov     [rsp+108h+var_B0], 0
0x18005f800  mov     [rsp+108h+var_C8], 0
0x18005f809  mov     [rsp+108h+var_D0], 0
0x18005f812  lea     r9, [rsp+108h+var_D0]
0x18005f817  lea     r8, [rsp+108h+var_48]
0x18005f81f  lea     rdx, [rsp+108h+var_A8]
0x18005f824  mov     rcx, r15
0x18005f827  call    ?GetNextAssocUnlocked@?$TCMHashTableLocked@USDCMKey@@PEAVCPoolnCS@@@@QEAAXAEAPEBXAEAUSDCMKey@@AEAPEAVCPoolnCS@@@Z; TCMHashTableLocked<SDCMKey,CPoolnCS *>::GetNextAssocUnlocked(void const * &,SDCMKey &,CPoolnCS * &)
0x18005f82c  mov     rax, [rsp+108h+var_D0]
0x18005f831  mov     [rsp+108h+var_B0], rax
0x18005f836  mov     rcx, rax
0x18005f839  call    ?GetPoolPointerNoWait@CPoolnCS@@QEAAPEAV?$CComObject@VCDCMPool@@@ATL@@XZ; CPoolnCS::GetPoolPointerNoWait(void)
0x18005f83e  mov     rbx, rax
0x18005f841  mov     [rsp+108h+var_C8], rax
0x18005f846  test    rax, rax
0x18005f849  jz      loc_18005F95F
0x18005f84f  mov     rcx, rax
0x18005f852  call    ?GetDPOPrototype@CDCMPool@@QEAAPEAV?$CComObject@VCPrototype@@@ATL@@XZ; CDCMPool::GetDPOPrototype(void)
0x18005f857  mov     [rsp+108h+var_48], rax
0x18005f85f  test    rax, rax
0x18005f862  jz      short loc_18005F871
0x18005f864  cmp     dword ptr [rax+350h], 0
0x18005f86b  ja      loc_18005F951
0x18005f871  cmp     dword ptr [rbx+68h], 0
0x18005f875  jnz     short loc_18005F87D
0x18005f877  cmp     dword ptr [rbx+6Ch], 0
0x18005f87b  jz      short loc_18005F895
0x18005f87d  cmp     [rsp+108h+arg_20], 0
0x18005f885  jz      loc_18005F951
0x18005f88b  cmp     dword ptr [rbx+68h], 0
0x18005f88f  jnz     loc_18005F951
0x18005f895  test    rax, rax
0x18005f898  jz      short loc_18005F8AA
0x18005f89a  mov     rdx, rax
0x18005f89d  call    ?ReleasePrototypeObj@CPrototypeManager@@QEAA_NPEAV?$CComObject@VCPrototype@@@ATL@@@Z; CPrototypeManager::ReleasePrototypeObj(ATL::CComObject<CPrototype> *)
0x18005f8a2  test    al, al
0x18005f8a4  jz      loc_18005F951
0x18005f8aa  mov     eax, [rbx+50h]
0x18005f8ad  mov     rcx, [rbx+48h]
0x18005f8b1  mov     rdx, [rsp+108h+arg_8]
0x18005f8b9  test    rdx, rdx
0x18005f8bc  jz      short loc_18005F914
0x18005f8be  mov     [rsp+108h+var_68], rcx
0x18005f8c6  mov     [rsp+108h+var_60], eax
0x18005f8cd  mov     [rsp+108h+var_5C], edi
0x18005f8d4  mov     [rsp+108h+var_58], rdx
0x18005f8dc  mov     eax, [rsp+108h+arg_10]
0x18005f8e3  mov     [rsp+108h+var_50], eax
0x18005f8ea  mov     [rsp+108h+var_4C], esi
0x18005f8f1  lea     r8, [rsp+108h+var_68]
0x18005f8f9  lea     rdx, [rsp+108h+var_58]
0x18005f901  mov     rcx, r15
0x18005f904  call    ?KeyCompareIsEqual@CDCMPoolMap@@MEBA_NUSDCMKey@@0@Z; CDCMPoolMap::KeyCompareIsEqual(SDCMKey,SDCMKey)
0x18005f909  test    al, al
0x18005f90b  jnz     short loc_18005F951
0x18005f90d  mov     eax, [rbx+50h]
0x18005f910  mov     rcx, [rbx+48h]
0x18005f914  mov     [rsp+108h+var_98], rcx
0x18005f919  mov     [rsp+108h+var_90], eax
0x18005f91d  mov     [rsp+108h+var_8C], edi
0x18005f921  mov     r8, [rsp+108h+var_D0]
0x18005f926  lea     rdx, [rsp+108h+var_98]
0x18005f92b  mov     rcx, r15
0x18005f92e  call    ?RemoveKeyUnlocked@?$TCMHashTableLocked@USDCMKey@@PEAVCPoolnCS@@@@QEAAHUSDCMKey@@PEAVCPoolnCS@@@Z; TCMHashTableLocked<SDCMKey,CPoolnCS *>::RemoveKeyUnlocked(SDCMKey,CPoolnCS *)
0x18005f933  mov     [rbx+108h], r13
0x18005f93a  mov     rax, [rbx]
0x18005f93d  mov     rcx, rbx
0x18005f940  mov     rax, [rax+8]
0x18005f944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f949  mov     r13, rbx
0x18005f94c  mov     [rsp+108h+var_C0], rbx
0x18005f951  lea     rcx, [rsp+108h+var_48]
0x18005f959  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x18005f95e  nop
0x18005f95f  lea     rcx, [rsp+108h+var_C8]
0x18005f964  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x18005f969  nop
0x18005f96a  lea     rcx, [rsp+108h+var_B0]
0x18005f96f  call    ??1?$CAutoRefc@VCPoolnCS@@@@QEAA@XZ; CAutoRefc<CPoolnCS>::~CAutoRefc<CPoolnCS>(void)
0x18005f974  mov     rcx, [rsp+108h+var_A8]
0x18005f979  jmp     loc_18005F7EE
0x18005f97e  jmp     short loc_18005F997
0x18005f980  jmp     short $+2
0x18005f982  mov     r13, [rsp+108h+var_C0]
0x18005f987  mov     r12d, [rsp+108h+arg_28]
0x18005f98f  mov     r15, [rsp+108h+arg_0]
0x18005f997  mov     esi, 1
0x18005f99c  jmp     short loc_18005F9C9
0x18005f99e  mov     rbx, r13
0x18005f9a1  lea     rax, [r13+108h]
0x18005f9a8  mov     r13, [rax]
0x18005f9ab  mov     qword ptr [rax], 0
0x18005f9b2  mov     rcx, rbx; this
0x18005f9b5  call    ?DetachFromHolder@CDCMPool@@QEAAJXZ; CDCMPool::DetachFromHolder(void)
0x18005f9ba  mov     rax, [rbx]
0x18005f9bd  mov     rcx, rbx
0x18005f9c0  mov     rax, [rax+10h]
0x18005f9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f9c9  test    r13, r13
0x18005f9cc  jnz     short loc_18005F99E
0x18005f9ce  lea     rcx, [rsp+108h+var_88]; this
0x18005f9d6  call    ??1CAutoRWLock@@QEAA@XZ; CAutoRWLock::~CAutoRWLock(void)
0x18005f9db  cmp     [rsp+108h+arg_18], r13b
0x18005f9e3  jz      loc_18005FAB5
0x18005f9e9  cmp     [r15+1Ch], r13d
0x18005f9ed  jnz     loc_18005FAB5
0x18005f9f3  mov     rcx, r15; this
0x18005f9f6  call    ?ReleaseDispenserManager@CDCMPoolManager@@AEAAJXZ; CDCMPoolManager::ReleaseDispenserManager(void)
0x18005f9fb  mov     rcx, cs:?_ConnStrParsingManager@@3PEAVCConnStrParsingManager@@EA; this
0x18005fa02  call    ?RemoveAllItems@CConnStrParsingManager@@QEAAJXZ; CConnStrParsingManager::RemoveAllItems(void)
0x18005fa07  lea     rcx, ?g_rwLockSHA256Init@@3VCReaderWriterLock3AR@@A; CReaderWriterLock3AR g_rwLockSHA256Init
0x18005fa0e  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18005fa14  mov     al, cs:?g_fSHA256Inited@@3_NC; bool volatile g_fSHA256Inited
0x18005fa1a  test    al, al
0x18005fa1c  jz      short loc_18005FA40
0x18005fa1e  mov     rcx, cs:?g_hAlgSHA256@@3PEAXEA; hAlgorithm
0x18005fa25  test    rcx, rcx
0x18005fa28  jz      short loc_18005FA40
0x18005fa2a  xor     edx, edx; dwFlags
0x18005fa2c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18005fa32  mov     cs:?g_hAlgSHA256@@3PEAXEA, r13; void * g_hAlgSHA256
0x18005fa39  mov     cs:?g_fSHA256Inited@@3_NC, r13b; bool volatile g_fSHA256Inited
0x18005fa40  lea     rcx, ?g_rwLockSHA256Init@@3VCReaderWriterLock3AR@@A; CReaderWriterLock3AR g_rwLockSHA256Init
0x18005fa47  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18005fa4d  mov     rbx, cs:?_ProviderInitInfoMap@@3PEAVCCMProviderInfoManager@@EA; CCMProviderInfoManager * _ProviderInitInfoMap
0x18005fa54  mov     rcx, rbx
0x18005fa57  call    ?CleanUpAllHash@?$TCMHashTableLocked@USProviderKey@@PEAVCCMProviderInfo@@@@QEAAXXZ; TCMHashTableLocked<SProviderKey,CCMProviderInfo *>::CleanUpAllHash(void)
0x18005fa5c  lea     rcx, [rbx+38h]
0x18005fa60  call    ?CleanUpAllHash@?$TCMHashTableLocked@USProviderKey@@PEAVCCMProviderInfo@@@@QEAAXXZ; TCMHashTableLocked<SProviderKey,CCMProviderInfo *>::CleanUpAllHash(void)
0x18005fa65  mov     rbx, cs:?_DCMNonReusable@@3PEAV?$CComObject@VCDCMCreator@@@ATL@@EA; ATL::CComObject<CDCMCreator> * _DCMNonReusable
0x18005fa6c  lea     rcx, [rbx+60h]; lpCriticalSection
0x18005fa70  call    cs:__imp_EnterCriticalSection
0x18005fa76  cmp     dword ptr [rbx+48h], 0
0x18005fa7a  jnz     short loc_18005FAAB
0x18005fa7c  cmp     byte ptr [rbx+58h], 0
0x18005fa80  jz      short loc_18005FAAB
0x18005fa82  mov     rcx, rbx; this
0x18005fa85  call    ?DetachFromHolder@CDCMCreator@@QEAAJXZ; CDCMCreator::DetachFromHolder(void)
0x18005fa8a  mov     rcx, [rbx+50h]
0x18005fa8e  test    rcx, rcx
0x18005fa91  jz      short loc_18005FAA7
0x18005fa93  mov     rax, [rcx]
0x18005fa96  mov     rax, [rax+10h]
0x18005fa9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fa9f  mov     qword ptr [rbx+50h], 0
0x18005faa7  mov     byte ptr [rbx+58h], 0
0x18005faab  lea     rcx, [rbx+60h]; lpCriticalSection
0x18005faaf  call    cs:__imp_LeaveCriticalSection
0x18005fab5  cmp     [rsp+108h+arg_20], 0
0x18005fabd  jz      short loc_18005FAD6
0x18005fabf  mov     rcx, [r15+50h]
0x18005fac3  test    rcx, rcx
0x18005fac6  jz      short loc_18005FAD6
0x18005fac8  xor     eax, eax
0x18005faca  xchg    eax, [rcx+28h]
0x18005facd  mov     rcx, [r15+58h]
0x18005fad1  xor     eax, eax
0x18005fad3  xchg    eax, [rcx+28h]
0x18005fad6  mov     rax, [rsp+108h+var_78]
0x18005fade  xchg    esi, [rax]
0x18005fae0  test    byte ptr cs:_bidGblFlags, 2
0x18005fae7  jz      short loc_18005FB15
0x18005fae9  mov     rax, cs:off_1800C9260; "<CDCMPoolManager::ScavangePools|RET>  %"...
0x18005faf0  test    rax, rax
0x18005faf3  jz      short loc_18005FB15
0x18005faf5  mov     [rsp+108h+var_E8], r12d
0x18005fafa  mov     r9, r15
0x18005fafd  mov     r8, cs:off_1800C9260; "<CDCMPoolManager::ScavangePools|RET>  %"...
0x18005fb04  mov     edx, 90400h
0x18005fb09  mov     rcx, cs:off_1800C8418; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005fb10  call    _bidTraceW
0x18005fb15  test    byte ptr cs:_bidGblFlags, 4
0x18005fb1c  jz      short loc_18005FB49
0x18005fb1e  cmp     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFFh
0x18005fb24  jz      short loc_18005FB49
0x18005fb26  mov     rcx, cs:_bidID
0x18005fb2d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005fb31  jz      short loc_18005FB49
0x18005fb33  lea     r9, [rsp+108h+var_B8]
0x18005fb38  xor     r8d, r8d
0x18005fb3b  xor     edx, edx
0x18005fb3d  mov     rax, cs:off_1800BC0E8
0x18005fb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb49  mov     eax, r12d
0x18005fb4c  add     rsp, 0D8h
0x18005fb53  pop     r15
0x18005fb55  pop     r13
0x18005fb57  pop     r12
0x18005fb59  pop     rdi
0x18005fb5a  pop     rsi
0x18005fb5b  pop     rbx
0x18005fb5c  retn
```
