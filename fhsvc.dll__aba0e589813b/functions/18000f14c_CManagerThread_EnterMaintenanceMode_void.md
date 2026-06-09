# CManagerThread::EnterMaintenanceMode(void)

- ea: `0x18000f14c`
- end: `0x18000f2b9`
- name: `?EnterMaintenanceMode@CManagerThread@@QEAAXXZ`
- size: `365`
- prototype: `void __fastcall(CManagerThread *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000e470`

## callees

- `0x1800011b0`
- `0x180004e30`
- `0x180007300`
- `0x1800076d0`
- `0x18000b5f8`
- `0x18000d840`
- `0x18000d910`
- `0x18000f14c`
- `0x1800109d4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000f291`
- `KERNEL32!SetEvent` at `0x18000f291`
- `KERNEL32!EnterCriticalSection` at `0x18000f179`
- `KERNEL32!EnterCriticalSection` at `0x18000f179`
- `KERNEL32!LeaveCriticalSection` at `0x18000f2a8`
- `KERNEL32!LeaveCriticalSection` at `0x18000f2a8`
- `KERNEL32!ResetEvent` at `0x18000f284`
- `KERNEL32!ResetEvent` at `0x18000f284`

## pseudocode

```c
void __fastcall CManagerThread::EnterMaintenanceMode(CManagerThread *this)
{
  int v1; // edi
  __int64 v2; // rsi
  __int64 v3; // r8
  __int64 v4; // r9
  CManagerThread *v5; // rbx
  __int64 v6; // r9
  _QWORD *v7; // rax
  CManagerThread *v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = this;
  if ( _InterlockedIncrement((volatile signed __int32 *)&qword_180019948) == 1 )
  {
    EnterCriticalSection(&CriticalSection);
    SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v8);
    v1 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
    v2 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
           &xmmword_1800198F0,
           xmmword_1800198F0);
    while ( v2 )
    {
      v2 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(
             &xmmword_1800198F0,
             v2,
             v3,
             v2);
      SmartPtr<CConfigDescriptor>::operator=((__int64 *)&v8, (__int64 *)(v4 + 8));
      v5 = v8;
      if ( *(_DWORD *)(*(_QWORD *)v8 + 16LL) )
      {
        *(_DWORD *)(*(_QWORD *)v8 + 20LL) = 1;
        v6 = *(_QWORD *)v5;
        v7 = *(_QWORD **)(*(_QWORD *)v5 + 136LL);
        if ( v7 && *v7 && *(_DWORD *)(v6 + 88) == 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              85,
              &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
              *(_QWORD *)v6);
          CWorkerThread::Stop(**(CWorkerThread ***)(*(_QWORD *)v5 + 136LL), 0);
        }
        ++v1;
      }
    }
    HIDWORD(qword_180019948) = v1;
    if ( v1 > 0 )
      ResetEvent(qword_180019950);
    SetEvent(hEvent);
    SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>((__int64 *)&v8);
    LeaveCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x18000f14c  mov     [rsp+arg_0], rcx
0x18000f151  push    rbx
0x18000f152  push    rsi
0x18000f153  push    rdi
0x18000f154  push    r14
0x18000f156  sub     rsp, 28h
0x18000f15a  mov     eax, 1
0x18000f15f  lock xadd dword ptr cs:qword_180019948, eax
0x18000f167  inc     eax
0x18000f169  cmp     eax, 1
0x18000f16c  jnz     loc_18000F2AF
0x18000f172  lea     rcx, CriticalSection; lpCriticalSection
0x18000f179  call    cs:__imp_EnterCriticalSection
0x18000f17f  lea     rcx, [rsp+48h+arg_0]
0x18000f184  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000f189  xor     edi, edi
0x18000f18b  lea     r14, WPP_GLOBAL_Control
0x18000f192  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f199  cmp     rcx, r14
0x18000f19c  jz      short loc_18000F1B7
0x18000f19e  test    byte ptr [rcx+1Ch], 8
0x18000f1a2  jz      short loc_18000F1B7
0x18000f1a4  lea     edx, [rdi+54h]
0x18000f1a7  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000f1ae  mov     rcx, [rcx+10h]
0x18000f1b2  call    WPP_SF_
0x18000f1b7  mov     rdx, qword ptr cs:xmmword_1800198F0
0x18000f1be  lea     rcx, xmmword_1800198F0
0x18000f1c5  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000f1ca  mov     rsi, rax
0x18000f1cd  test    rax, rax
0x18000f1d0  jz      loc_18000F273
0x18000f1d6  mov     r9, rsi
0x18000f1d9  mov     rdx, rsi
0x18000f1dc  lea     rcx, xmmword_1800198F0
0x18000f1e3  call    ?Successor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000f1e8  mov     rsi, rax
0x18000f1eb  lea     rdx, [r9+8]
0x18000f1ef  lea     rcx, [rsp+48h+arg_0]
0x18000f1f4  call    ??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CConfigDescriptor>::operator=(SmartPtr<CConfigDescriptor> const &)
0x18000f1f9  mov     rbx, [rsp+48h+arg_0]
0x18000f1fe  mov     rax, [rbx]
0x18000f201  cmp     dword ptr [rax+10h], 0
0x18000f205  jz      short loc_18000F26A
0x18000f207  mov     dword ptr [rax+14h], 1
0x18000f20e  mov     r9, [rbx]
0x18000f211  mov     rax, [r9+88h]
0x18000f218  test    rax, rax
0x18000f21b  jz      short loc_18000F268
0x18000f21d  cmp     qword ptr [rax], 0
0x18000f221  jz      short loc_18000F268
0x18000f223  cmp     dword ptr [r9+58h], 1
0x18000f228  jnz     short loc_18000F268
0x18000f22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f231  cmp     rcx, r14
0x18000f234  jz      short loc_18000F254
0x18000f236  test    byte ptr [rcx+1Ch], 8
0x18000f23a  jz      short loc_18000F254
0x18000f23c  mov     edx, 55h ; 'U'
0x18000f241  mov     r9, [r9]
0x18000f244  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000f24b  mov     rcx, [rcx+10h]
0x18000f24f  call    WPP_SF_S
0x18000f254  mov     rax, [rbx]
0x18000f257  mov     rcx, [rax+88h]
0x18000f25e  xor     edx, edx; int
0x18000f260  mov     rcx, [rcx]; this
0x18000f263  call    ?Stop@CWorkerThread@@QEAAJH@Z; CWorkerThread::Stop(int)
0x18000f268  inc     edi
0x18000f26a  test    rsi, rsi
0x18000f26d  jnz     loc_18000F1D6
0x18000f273  mov     dword ptr cs:qword_180019948+4, edi
0x18000f279  test    edi, edi
0x18000f27b  jle     short loc_18000F28A
0x18000f27d  mov     rcx, cs:qword_180019950; hEvent
0x18000f284  call    cs:__imp_ResetEvent
0x18000f28a  mov     rcx, cs:hEvent; hEvent
0x18000f291  call    cs:__imp_SetEvent
0x18000f297  lea     rcx, [rsp+48h+arg_0]
0x18000f29c  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x18000f2a1  lea     rcx, CriticalSection; lpCriticalSection
0x18000f2a8  call    cs:__imp_LeaveCriticalSection
0x18000f2ae  nop
0x18000f2af  add     rsp, 28h
0x18000f2b3  pop     r14
0x18000f2b5  pop     rdi
0x18000f2b6  pop     rsi
0x18000f2b7  pop     rbx
0x18000f2b8  retn
```
