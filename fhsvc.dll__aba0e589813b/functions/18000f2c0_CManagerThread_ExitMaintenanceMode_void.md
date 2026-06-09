# CManagerThread::ExitMaintenanceMode(void)

- ea: `0x18000f2c0`
- end: `0x18000f441`
- name: `?ExitMaintenanceMode@CManagerThread@@QEAAXXZ`
- size: `385`
- prototype: `void __fastcall(CManagerThread *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000dd60`
- `0x18000e520`

## callees

- `0x1800011b0`
- `0x180004e30`
- `0x180007300`
- `0x1800076d0`
- `0x18000b5f8`
- `0x18000d840`
- `0x18000d910`
- `0x18000f2c0`
- `0x1800109d4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000f406`
- `KERNEL32!SetEvent` at `0x18000f413`
- `KERNEL32!SetEvent` at `0x18000f406`
- `KERNEL32!SetEvent` at `0x18000f413`
- `KERNEL32!EnterCriticalSection` at `0x18000f2ef`
- `KERNEL32!EnterCriticalSection` at `0x18000f2ef`
- `KERNEL32!LeaveCriticalSection` at `0x18000f42a`
- `KERNEL32!LeaveCriticalSection` at `0x18000f42a`

## pseudocode

```c
void __fastcall CManagerThread::ExitMaintenanceMode(CManagerThread *this)
{
  __int64 v1; // rdi
  __int64 v2; // r8
  __int64 v3; // r9
  CManagerThread *v4; // rbx
  __int64 v5; // r9
  _QWORD *v6; // rax
  CManagerThread *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = this;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&qword_180019948, 0xFFFFFFFF) == 1 )
  {
    EnterCriticalSection(&CriticalSection);
    SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v7);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
    v1 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
           &xmmword_1800198F0,
           xmmword_1800198F0);
    while ( v1 )
    {
      v1 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(
             &xmmword_1800198F0,
             v1,
             v2,
             v1);
      SmartPtr<CConfigDescriptor>::operator=((__int64 *)&v7, (__int64 *)(v3 + 8));
      v4 = v7;
      if ( *(_DWORD *)(*(_QWORD *)v7 + 20LL) && *(_DWORD *)(*(_QWORD *)v7 + 88LL) != 2 )
        --HIDWORD(qword_180019948);
      *(_DWORD *)(*(_QWORD *)v7 + 20LL) = 0;
      v5 = *(_QWORD *)v4;
      v6 = *(_QWORD **)(*(_QWORD *)v4 + 136LL);
      if ( v6 && *v6 && *(_DWORD *)(v5 + 88) == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            87,
            &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            *(_QWORD *)v5);
        CWorkerThread::Stop(**(CWorkerThread ***)(*(_QWORD *)v4 + 136LL), 0);
      }
    }
    if ( !HIDWORD(qword_180019948) )
      SetEvent(qword_180019950);
    SetEvent(hEvent);
    SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>((__int64 *)&v7);
    LeaveCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x18000f2c0  mov     [rsp+arg_8], rbx
0x18000f2c5  mov     [rsp+arg_10], rbp
0x18000f2ca  mov     [rsp+arg_0], rcx
0x18000f2cf  push    rdi
0x18000f2d0  sub     rsp, 20h
0x18000f2d4  or      eax, 0FFFFFFFFh
0x18000f2d7  lock xadd dword ptr cs:qword_180019948, eax
0x18000f2df  cmp     eax, 1
0x18000f2e2  jnz     loc_18000F431
0x18000f2e8  lea     rcx, CriticalSection; lpCriticalSection
0x18000f2ef  call    cs:__imp_EnterCriticalSection
0x18000f2f5  lea     rcx, [rsp+28h+arg_0]
0x18000f2fa  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000f2ff  lea     rbp, WPP_GLOBAL_Control
0x18000f306  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f30d  cmp     rcx, rbp
0x18000f310  jz      short loc_18000F32D
0x18000f312  test    byte ptr [rcx+1Ch], 8
0x18000f316  jz      short loc_18000F32D
0x18000f318  mov     edx, 56h ; 'V'
0x18000f31d  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000f324  mov     rcx, [rcx+10h]
0x18000f328  call    WPP_SF_
0x18000f32d  mov     rdx, qword ptr cs:xmmword_1800198F0
0x18000f334  lea     rcx, xmmword_1800198F0
0x18000f33b  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000f340  mov     rdi, rax
0x18000f343  test    rax, rax
0x18000f346  jz      loc_18000F3F6
0x18000f34c  mov     r9, rdi
0x18000f34f  mov     rdx, rdi
0x18000f352  lea     rcx, xmmword_1800198F0
0x18000f359  call    ?Successor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000f35e  mov     rdi, rax
0x18000f361  lea     rdx, [r9+8]
0x18000f365  lea     rcx, [rsp+28h+arg_0]
0x18000f36a  call    ??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CConfigDescriptor>::operator=(SmartPtr<CConfigDescriptor> const &)
0x18000f36f  mov     rbx, [rsp+28h+arg_0]
0x18000f374  mov     rax, [rbx]
0x18000f377  cmp     dword ptr [rax+14h], 0
0x18000f37b  jz      short loc_18000F389
0x18000f37d  cmp     dword ptr [rax+58h], 2
0x18000f381  jz      short loc_18000F389
0x18000f383  dec     dword ptr cs:qword_180019948+4
0x18000f389  mov     rax, [rbx]
0x18000f38c  mov     dword ptr [rax+14h], 0
0x18000f393  mov     r9, [rbx]
0x18000f396  mov     rax, [r9+88h]
0x18000f39d  test    rax, rax
0x18000f3a0  jz      short loc_18000F3ED
0x18000f3a2  cmp     qword ptr [rax], 0
0x18000f3a6  jz      short loc_18000F3ED
0x18000f3a8  cmp     dword ptr [r9+58h], 2
0x18000f3ad  jnz     short loc_18000F3ED
0x18000f3af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3b6  cmp     rcx, rbp
0x18000f3b9  jz      short loc_18000F3D9
0x18000f3bb  test    byte ptr [rcx+1Ch], 8
0x18000f3bf  jz      short loc_18000F3D9
0x18000f3c1  mov     edx, 57h ; 'W'
0x18000f3c6  mov     r9, [r9]
0x18000f3c9  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000f3d0  mov     rcx, [rcx+10h]
0x18000f3d4  call    WPP_SF_S
0x18000f3d9  mov     rax, [rbx]
0x18000f3dc  mov     rcx, [rax+88h]
0x18000f3e3  xor     edx, edx; int
0x18000f3e5  mov     rcx, [rcx]; this
0x18000f3e8  call    ?Stop@CWorkerThread@@QEAAJH@Z; CWorkerThread::Stop(int)
0x18000f3ed  test    rdi, rdi
0x18000f3f0  jnz     loc_18000F34C
0x18000f3f6  cmp     dword ptr cs:qword_180019948+4, 0
0x18000f3fd  jnz     short loc_18000F40C
0x18000f3ff  mov     rcx, cs:qword_180019950; hEvent
0x18000f406  call    cs:__imp_SetEvent
0x18000f40c  mov     rcx, cs:hEvent; hEvent
0x18000f413  call    cs:__imp_SetEvent
0x18000f419  lea     rcx, [rsp+28h+arg_0]
0x18000f41e  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x18000f423  lea     rcx, CriticalSection; lpCriticalSection
0x18000f42a  call    cs:__imp_LeaveCriticalSection
0x18000f430  nop
0x18000f431  mov     rbx, [rsp+28h+arg_8]
0x18000f436  mov     rbp, [rsp+28h+arg_10]
0x18000f43b  add     rsp, 20h
0x18000f43f  pop     rdi
0x18000f440  retn
```
