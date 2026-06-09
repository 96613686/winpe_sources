# CDCMPoolManager::EnumPools(ulong *,IPoolInfo * * * const)

- ea: `0x18005e5e0`
- end: `0x18005e759`
- name: `?EnumPools@CDCMPoolManager@@QEAAJPEAKQEAPEAPEAUIPoolInfo@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(CDCMPoolManager *__hidden this, unsigned int *, struct IPoolInfo ***const)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180069d60`

## callees

- `0x180013870`
- `0x180026940`
- `0x18002adb4`
- `0x18005daa0`
- `0x18005e5e0`
- `0x18005e930`
- `0x18005e9cc`
- `0x180087010`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18005e62a`
- `KERNEL32!AcquireSRWLockShared` at `0x18005e62a`
- `ole32!CoTaskMemAlloc` at `0x18005e642`
- `ole32!CoTaskMemAlloc` at `0x18005e642`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDCMPoolManager::EnumPools(RTL_SRWLOCK *this, unsigned int *a2, struct IPoolInfo ***const a3)
{
  unsigned int v6; // edi
  __int64 v7; // rbx
  struct IPoolInfo **v8; // r12
  int (__fastcall ***PoolPointerNoWait)(_QWORD, GUID *, __int64); // rax
  __int64 v11; // [rsp+20h] [rbp-30h] BYREF
  __int64 v12; // [rsp+28h] [rbp-28h] BYREF
  int v13; // [rsp+30h] [rbp-20h] BYREF
  RTL_SRWLOCK *v14; // [rsp+38h] [rbp-18h]
  char v15[16]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+88h] [rbp+38h] BYREF
  int (__fastcall ***v17)(_QWORD, GUID *, __int64); // [rsp+98h] [rbp+48h] BYREF

  if ( a2 && a3 )
  {
    v6 = 0;
    *a2 = 0;
    *a3 = 0;
    v14 = this + 1;
    v13 = 1;
    AcquireSRWLockShared(this + 1);
    LODWORD(v7) = HIDWORD(this[3].Ptr);
    if ( (_DWORD)v7 )
    {
      v8 = (struct IPoolInfo **)CoTaskMemAlloc(8LL * (unsigned int)v7);
      if ( v8 )
      {
        if ( HIDWORD(this[3].Ptr) )
        {
          v7 = 0;
          v12 = -1;
          do
          {
            v11 = 0;
            v17 = 0;
            v16 = 0;
            TCMHashTableLocked<SDCMKey,CPoolnCS *>::GetNextAssocUnlocked(this, &v12, v15, &v16);
            v11 = v16;
            PoolPointerNoWait = (int (__fastcall ***)(_QWORD, GUID *, __int64))CPoolnCS::GetPoolPointerNoWait(v16);
            v17 = PoolPointerNoWait;
            if ( PoolPointerNoWait )
            {
              if ( (**PoolPointerNoWait)(PoolPointerNoWait, &IID_IPoolInfo, (__int64)&v8[v7]) >= 0 )
                v7 = (unsigned int)(v7 + 1);
            }
            ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v17);
            CAutoRefc<CPoolnCS>::~CAutoRefc<CPoolnCS>(&v11);
          }
          while ( v12 );
        }
        *a3 = v8;
        *a2 = v7;
      }
      else
      {
        v6 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147024882, L"<CDCMPoolManager::EnumPools|OLEDB|ERR> ", 0x416u);
      }
    }
    CAutoRWLock::~CAutoRWLock((CAutoRWLock *)&v13);
    return v6;
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(0, L"<CDCMPoolManager::EnumPools|OLEDB|ERR> ", 0x3EEu);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18005e5e0  mov     [rsp-28h+arg_0], rbx
0x18005e5e5  mov     [rsp-28h+arg_10], rsi
0x18005e5ea  push    rbp
0x18005e5eb  push    rdi
0x18005e5ec  push    r12
0x18005e5ee  push    r14
0x18005e5f0  push    r15
0x18005e5f2  mov     rbp, rsp
0x18005e5f5  sub     rsp, 50h
0x18005e5f9  mov     rsi, r8
0x18005e5fc  mov     r15, rdx
0x18005e5ff  mov     r14, rcx
0x18005e602  test    rdx, rdx
0x18005e605  jz      loc_18005E71E
0x18005e60b  test    r8, r8
0x18005e60e  jz      loc_18005E71E
0x18005e614  xor     edi, edi
0x18005e616  mov     [rdx], edi
0x18005e618  mov     [r8], rdi
0x18005e61b  add     rcx, 8; SRWLock
0x18005e61f  mov     [rbp+var_18], rcx
0x18005e623  mov     [rbp+var_20], 1
0x18005e62a  call    cs:__imp_AcquireSRWLockShared
0x18005e630  mov     ebx, [r14+1Ch]
0x18005e634  test    ebx, ebx
0x18005e636  jz      loc_18005E711
0x18005e63c  mov     ecx, ebx
0x18005e63e  shl     rcx, 3; cb
0x18005e642  call    cs:__imp_CoTaskMemAlloc
0x18005e648  mov     r12, rax
0x18005e64b  test    rax, rax
0x18005e64e  jz      loc_18005E6EE
0x18005e654  cmp     [r14+1Ch], edi
0x18005e658  jz      loc_18005E6E6
0x18005e65e  xor     ebx, ebx
0x18005e660  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x18005e668  mov     [rbp+var_30], 0
0x18005e670  mov     [rbp+arg_18], 0
0x18005e678  mov     [rbp+arg_8], 0
0x18005e680  lea     r9, [rbp+arg_8]
0x18005e684  lea     r8, [rbp+var_10]
0x18005e688  lea     rdx, [rbp+var_28]
0x18005e68c  mov     rcx, r14
0x18005e68f  call    ?GetNextAssocUnlocked@?$TCMHashTableLocked@USDCMKey@@PEAVCPoolnCS@@@@QEAAXAEAPEBXAEAUSDCMKey@@AEAPEAVCPoolnCS@@@Z; TCMHashTableLocked<SDCMKey,CPoolnCS *>::GetNextAssocUnlocked(void const * &,SDCMKey &,CPoolnCS * &)
0x18005e694  mov     rcx, [rbp+arg_8]
0x18005e698  mov     [rbp+var_30], rcx
0x18005e69c  call    ?GetPoolPointerNoWait@CPoolnCS@@QEAAPEAV?$CComObject@VCDCMPool@@@ATL@@XZ; CPoolnCS::GetPoolPointerNoWait(void)
0x18005e6a1  mov     r9, rax
0x18005e6a4  mov     [rbp+arg_18], rax
0x18005e6a8  test    rax, rax
0x18005e6ab  jz      short loc_18005E6CC
0x18005e6ad  mov     rcx, [rax]
0x18005e6b0  lea     r8, [r12+rbx*8]
0x18005e6b4  mov     rax, [rcx]
0x18005e6b7  lea     rdx, IID_IPoolInfo
0x18005e6be  mov     rcx, r9
0x18005e6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e6c6  test    eax, eax
0x18005e6c8  js      short loc_18005E6CC
0x18005e6ca  inc     ebx
0x18005e6cc  lea     rcx, [rbp+arg_18]
0x18005e6d0  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x18005e6d5  nop
0x18005e6d6  lea     rcx, [rbp+var_30]
0x18005e6da  call    ??1?$CAutoRefc@VCPoolnCS@@@@QEAA@XZ; CAutoRefc<CPoolnCS>::~CAutoRefc<CPoolnCS>(void)
0x18005e6df  cmp     [rbp+var_28], 0
0x18005e6e4  jnz     short loc_18005E668
0x18005e6e6  mov     [rsi], r12
0x18005e6e9  mov     [r15], ebx
0x18005e6ec  jmp     short loc_18005E711
0x18005e6ee  mov     edi, 8007000Eh
0x18005e6f3  test    byte ptr cs:_bidGblFlags, 2
0x18005e6fa  jz      short loc_18005E711
0x18005e6fc  mov     r8d, 416h; unsigned int
0x18005e702  lea     rdx, aCdcmpoolmanage_13; "<CDCMPoolManager::EnumPools|OLEDB|ERR> "
0x18005e709  mov     ecx, edi; int
0x18005e70b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005e710  nop
0x18005e711  lea     rcx, [rbp+var_20]; this
0x18005e715  call    ??1CAutoRWLock@@QEAA@XZ; CAutoRWLock::~CAutoRWLock(void)
0x18005e71a  mov     eax, edi
0x18005e71c  jmp     short loc_18005E740
0x18005e71e  test    byte ptr cs:_bidGblFlags, 2
0x18005e725  jz      short loc_18005E73B
0x18005e727  mov     r8d, 3EEh; unsigned int
0x18005e72d  lea     rdx, aCdcmpoolmanage_13; "<CDCMPoolManager::EnumPools|OLEDB|ERR> "
0x18005e734  xor     ecx, ecx; int
0x18005e736  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005e73b  mov     eax, 80070057h
0x18005e740  lea     r11, [rsp+50h+var_s0]
0x18005e745  mov     rbx, [r11+30h]
0x18005e749  mov     rsi, [r11+40h]
0x18005e74d  mov     rsp, r11
0x18005e750  pop     r15
0x18005e752  pop     r14
0x18005e754  pop     r12
0x18005e756  pop     rdi
0x18005e757  pop     rbp
0x18005e758  retn
```
