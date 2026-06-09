# CSystemScanner::~CSystemScanner(void)

- ea: `0x180013948`
- end: `0x180013a81`
- name: `??1CSystemScanner@@QEAA@XZ`
- size: `313`
- prototype: `void __fastcall(CSystemScanner *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003224`

## callees

- `0x180003180`
- `0x180006874`
- `0x18001376c`
- `0x180013820`
- `0x180013920`
- `0x180013948`
- `0x18001628c`
- `0x1800162f8`

## import_xrefs

- `msvcrt!free` at `0x180013a31`
- `msvcrt!free` at `0x180013a4e`
- `msvcrt!free` at `0x180013a31`
- `msvcrt!free` at `0x180013a4e`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x1800139b7`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x1800139b7`

## pseudocode

```c
void __fastcall CSystemScanner::~CSystemScanner(CSystemScanner *this)
{
  PTP_WORK *v2; // rdi
  __int64 v3; // r9
  void *v4; // rcx
  void *v5; // rcx

  v2 = (PTP_WORK *)((char *)this + 240);
  *(_QWORD *)this = &CSystemScanner::`vftable'{for `IDiskScanNotify'};
  v3 = *((_QWORD *)this + 30);
  *((_QWORD *)this + 1) = &CSystemScanner::`vftable'{for `IDiskPnpNotify'};
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids, v3);
    }
    WaitForThreadpoolWorkCallbacks(*v2, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids, *v2);
    }
  }
  CDiskPnpMonitor::~CDiskPnpMonitor((CSystemScanner *)((char *)this + 272));
  CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(v2);
  CSpacePortUtil::~CSpacePortUtil((CSystemScanner *)((char *)this + 236));
  ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::RemoveAll((char *)this + 208);
  ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::RemoveAll((char *)this + 160);
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 16) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 17);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 17) = 0;
  }
  *((_DWORD *)this + 36) = 0;
  ATL::CAtlList<ATL::CAutoPtr<CSpacePoolContext>,ATL::CAutoPtrElementTraits<CSpacePoolContext>>::RemoveAll((char *)this + 80);
}

```

## disassembly

```asm
0x180013948  mov     [rsp+arg_0], rbx
0x18001394d  mov     [rsp+arg_8], rbp
0x180013952  push    rdi
0x180013953  sub     rsp, 20h
0x180013957  lea     rax, ??_7CSystemScanner@@6BIDiskScanNotify@@@; const CSystemScanner::`vftable'{for `IDiskScanNotify'}
0x18001395e  mov     rbx, rcx
0x180013961  lea     rdi, [rcx+0F0h]
0x180013968  mov     [rcx], rax
0x18001396b  mov     r9, [rdi]
0x18001396e  lea     rax, ??_7CSystemScanner@@6BIDiskPnpNotify@@@; const CSystemScanner::`vftable'{for `IDiskPnpNotify'}
0x180013975  mov     [rcx+8], rax
0x180013979  test    r9, r9
0x18001397c  jz      short loc_1800139ED
0x18001397e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013985  lea     rbp, WPP_GLOBAL_Control
0x18001398c  cmp     rcx, rbp
0x18001398f  jz      short loc_1800139B2
0x180013991  test    byte ptr [rcx+1Ch], 1
0x180013995  jz      short loc_1800139B2
0x180013997  cmp     byte ptr [rcx+19h], 4
0x18001399b  jb      short loc_1800139B2
0x18001399d  mov     rcx, [rcx+10h]
0x1800139a1  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x1800139a8  mov     edx, 0Ch
0x1800139ad  call    WPP_SF_q
0x1800139b2  mov     rcx, [rdi]; pwk
0x1800139b5  xor     edx, edx; fCancelPendingCallbacks
0x1800139b7  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800139bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139c4  cmp     rcx, rbp
0x1800139c7  jz      short loc_1800139ED
0x1800139c9  test    byte ptr [rcx+1Ch], 1
0x1800139cd  jz      short loc_1800139ED
0x1800139cf  cmp     byte ptr [rcx+19h], 4
0x1800139d3  jb      short loc_1800139ED
0x1800139d5  mov     r9, [rdi]
0x1800139d8  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x1800139df  mov     rcx, [rcx+10h]
0x1800139e3  mov     edx, 0Dh
0x1800139e8  call    WPP_SF_q
0x1800139ed  lea     rcx, [rbx+110h]; this
0x1800139f4  call    ??1CDiskPnpMonitor@@QEAA@XZ; CDiskPnpMonitor::~CDiskPnpMonitor(void)
0x1800139f9  mov     rcx, rdi; void *
0x1800139fc  call    ??1?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAA@XZ; CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(void)
0x180013a01  lea     rcx, [rbx+0ECh]; this
0x180013a08  call    ??1CSpacePortUtil@@QEAA@XZ; CSpacePortUtil::~CSpacePortUtil(void)
0x180013a0d  lea     rcx, [rbx+0D0h]
0x180013a14  call    ?RemoveAll@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::RemoveAll(void)
0x180013a19  lea     rcx, [rbx+0A0h]
0x180013a20  call    ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCDiskScanner@@@ATL@@V?$CAutoPtrElementTraits@VCDiskScanner@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::RemoveAll(void)
0x180013a25  mov     rcx, [rbx+80h]; Block
0x180013a2c  test    rcx, rcx
0x180013a2f  jz      short loc_180013A42
0x180013a31  call    cs:__imp_free
0x180013a37  mov     qword ptr [rbx+80h], 0
0x180013a42  mov     rcx, [rbx+88h]; Block
0x180013a49  test    rcx, rcx
0x180013a4c  jz      short loc_180013A5F
0x180013a4e  call    cs:__imp_free
0x180013a54  mov     qword ptr [rbx+88h], 0
0x180013a5f  lea     rcx, [rbx+50h]
0x180013a63  mov     dword ptr [rbx+90h], 0
0x180013a6d  mov     rbx, [rsp+28h+arg_0]
0x180013a72  mov     rbp, [rsp+28h+arg_8]
0x180013a77  add     rsp, 20h
0x180013a7b  pop     rdi
0x180013a7c  jmp     ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCSpacePoolContext@@@ATL@@V?$CAutoPtrElementTraits@VCSpacePoolContext@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CSpacePoolContext>,ATL::CAutoPtrElementTraits<CSpacePoolContext>>::RemoveAll(void)
```
