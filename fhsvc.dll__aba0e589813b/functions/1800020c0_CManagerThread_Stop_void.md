# CManagerThread::Stop(void)

- ea: `0x1800020c0`
- end: `0x180002216`
- name: `?Stop@CManagerThread@@QEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(CManagerThread *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180001690`
- `0x1800017c0`

## callees

- `0x1800011b0`
- `0x1800020c0`
- `0x180004e30`
- `0x180004e50`
- `0x1800076d0`
- `0x18000d840`
- `0x1800109d4`

## import_xrefs

- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800021bf`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800021bf`
- `KERNEL32!CloseThreadpoolWait` at `0x1800021cc`
- `KERNEL32!CloseThreadpoolWait` at `0x1800021cc`
- `KERNEL32!EnterCriticalSection` at `0x180002113`
- `KERNEL32!EnterCriticalSection` at `0x180002113`
- `KERNEL32!LeaveCriticalSection` at `0x1800021a8`
- `KERNEL32!LeaveCriticalSection` at `0x1800021a8`

## pseudocode

```c
__int64 __fastcall CManagerThread::Stop(CManagerThread *this)
{
  __int64 v1; // rdi
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned int v4; // edx
  __int64 v5; // rbx
  CWorkerThread **v6; // rcx
  CWorkerThread *v7; // rcx
  CManagerThread *v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
  LODWORD(qword_1800199C8) = 1;
  EnterCriticalSection(&CriticalSection);
  v1 = xmmword_1800198F0;
  if ( (_QWORD)xmmword_1800198F0 && (_QWORD)xmmword_1800198F0 != qword_180019918 )
  {
    while ( *(_QWORD *)(v1 + 24) != qword_180019918 )
      v1 = *(_QWORD *)(v1 + 24);
    while ( v1 )
    {
      SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v9);
      v1 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(
             &xmmword_1800198F0,
             v1,
             v2,
             v1);
      SmartPtr<CConfigDescriptor>::operator=((__int64 *)&v9, (__int64 *)(v3 + 8));
      v5 = (__int64)v9;
      v6 = *(CWorkerThread ***)(*(_QWORD *)v9 + 136LL);
      if ( v6 )
      {
        v7 = *v6;
        if ( v7 )
          CWorkerThread::Stop(v7, 0);
      }
      SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(v5, v4);
    }
  }
  LeaveCriticalSection(&CriticalSection);
  if ( pwa )
  {
    WaitForThreadpoolWaitCallbacks(pwa, 1);
    CloseThreadpoolWait(pwa);
    pwa = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800020c0  mov     [rsp+arg_8], rbx
0x1800020c5  mov     [rsp+arg_10], rsi
0x1800020ca  mov     [rsp+arg_0], rcx
0x1800020cf  push    rdi
0x1800020d0  sub     rsp, 20h
0x1800020d4  lea     rsi, WPP_GLOBAL_Control
0x1800020db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020e2  cmp     rcx, rsi
0x1800020e5  jz      short loc_180002102
0x1800020e7  test    byte ptr [rcx+1Ch], 8
0x1800020eb  jz      short loc_180002102
0x1800020ed  mov     edx, 28h ; '('
0x1800020f2  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800020f9  mov     rcx, [rcx+10h]
0x1800020fd  call    WPP_SF_
0x180002102  mov     dword ptr cs:qword_1800199C8, 1
0x18000210c  lea     rcx, CriticalSection; lpCriticalSection
0x180002113  call    cs:__imp_EnterCriticalSection
0x180002119  mov     rdi, qword ptr cs:xmmword_1800198F0
0x180002120  test    rdi, rdi
0x180002123  jz      short loc_1800021A1
0x180002125  mov     rax, cs:qword_180019918
0x18000212c  cmp     rdi, rax
0x18000212f  jz      short loc_1800021A1
0x180002131  mov     rcx, [rdi+18h]
0x180002135  cmp     rcx, rax
0x180002138  jz      short loc_18000213F
0x18000213a  mov     rdi, rcx
0x18000213d  jmp     short loc_180002131
0x18000213f  test    rdi, rdi
0x180002142  jz      short loc_1800021A1
0x180002144  lea     rcx, [rsp+28h+arg_0]
0x180002149  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000214e  mov     r9, rdi
0x180002151  mov     rdx, rdi
0x180002154  lea     rcx, xmmword_1800198F0
0x18000215b  call    ?Successor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x180002160  mov     rdi, rax
0x180002163  lea     rdx, [r9+8]
0x180002167  lea     rcx, [rsp+28h+arg_0]
0x18000216c  call    ??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CConfigDescriptor>::operator=(SmartPtr<CConfigDescriptor> const &)
0x180002171  mov     rbx, [rsp+28h+arg_0]
0x180002176  mov     rax, [rbx]
0x180002179  mov     rcx, [rax+88h]
0x180002180  test    rcx, rcx
0x180002183  jz      short loc_180002194
0x180002185  mov     rcx, [rcx]; this
0x180002188  test    rcx, rcx
0x18000218b  jz      short loc_180002194
0x18000218d  xor     edx, edx; int
0x18000218f  call    ?Stop@CWorkerThread@@QEAAJH@Z; CWorkerThread::Stop(int)
0x180002194  mov     rcx, rbx
0x180002197  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x18000219c  test    rdi, rdi
0x18000219f  jnz     short loc_180002144
0x1800021a1  lea     rcx, CriticalSection; lpCriticalSection
0x1800021a8  call    cs:__imp_LeaveCriticalSection
0x1800021ae  mov     rcx, cs:pwa; pwa
0x1800021b5  test    rcx, rcx
0x1800021b8  jz      short loc_1800021DD
0x1800021ba  mov     edx, 1; fCancelPendingCallbacks
0x1800021bf  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800021c5  mov     rcx, cs:pwa; pwa
0x1800021cc  call    cs:__imp_CloseThreadpoolWait
0x1800021d2  mov     cs:pwa, 0
0x1800021dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021e4  cmp     rcx, rsi
0x1800021e7  jz      short loc_180002204
0x1800021e9  test    byte ptr [rcx+1Ch], 8
0x1800021ed  jz      short loc_180002204
0x1800021ef  mov     edx, 29h ; ')'
0x1800021f4  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800021fb  mov     rcx, [rcx+10h]
0x1800021ff  call    WPP_SF_
0x180002204  xor     eax, eax
0x180002206  mov     rbx, [rsp+28h+arg_8]
0x18000220b  mov     rsi, [rsp+28h+arg_10]
0x180002210  add     rsp, 20h
0x180002214  pop     rdi
0x180002215  retn
```
