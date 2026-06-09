# CRenderer::CRenderer(ushort const *,IUnknown *,long *)

- ea: `0x18009c2cc`
- end: `0x18009c60f`
- name: `??0CRenderer@@QEAA@PEBGPEAUIUnknown@@PEAJ@Z`
- size: `835`
- prototype: `CRenderer *__fastcall(CRenderer *__hidden this, const unsigned __int16 *, struct IUnknown *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18009ce30`

## callees

- `0x18001efe0`
- `0x18002f120`
- `0x180039250`
- `0x18009c2cc`
- `0x18009c618`
- `0x18009d444`
- `0x18009e414`
- `0x1800a2614`
- `0x1800a3e1c`
- `0x1800a5268`
- `0x180141f68`
- `0x180143098`
- `0x180148fe4`
- `0x18014ab30`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18009c5d9`
- `KERNEL32!CreateEventW` at `0x18009c5d9`
- `KERNEL32!InitializeCriticalSection` at `0x18009c559`
- `KERNEL32!InitializeCriticalSection` at `0x18009c559`
- `USER32!GetSystemMetrics` at `0x18009c516`
- `USER32!GetSystemMetrics` at `0x18009c516`
- `USER32!SetRectEmpty` at `0x18009c40e`
- `USER32!SetRectEmpty` at `0x18009c41e`
- `USER32!SetRectEmpty` at `0x18009c40e`
- `USER32!SetRectEmpty` at `0x18009c41e`

## pseudocode

```c
CRenderer *__fastcall CRenderer::CRenderer(CRenderer *this, const unsigned __int16 *a2, struct IUnknown *a3, int *a4)
{
  unsigned __int64 v4; // r14
  unsigned __int64 v7; // rbx
  char *v8; // rsi
  int *v9; // r9
  int LastErrorToHResult; // eax
  __int64 v11; // rdx
  HANDLE EventW; // rax
  int *v14; // [rsp+20h] [rbp-58h]
  int *v15; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v16; // [rsp+20h] [rbp-58h]
  unsigned int v17; // [rsp+28h] [rbp-50h]

  v4 = (unsigned __int64)this + 8;
  CBaseRenderer::CBaseRenderer(
    (CRenderer *)((char *)this + 8),
    &CLSID_VideoRenderer,
    (const unsigned __int16 *)a3,
    a3,
    a4,
    v17);
  *(_QWORD *)v4 = &CBaseVideoRenderer::`vftable'{for `CUnknown'};
  *(_DWORD *)(v4 + 372) = 0;
  *(_QWORD *)(v4 + 24) = &CBaseVideoRenderer::`vftable'{for `IBaseFilter'};
  *(_QWORD *)(v4 + 32) = &CMpegAudioCodec::`vftable'{for `IAMovieSetup'};
  *(_QWORD *)(v4 + 352) = &CBaseVideoRenderer::`vftable'{for `IQualProp'};
  *(_QWORD *)(v4 + 360) = &CBaseVideoRenderer::`vftable'{for `IQualityControl'};
  *(_QWORD *)(v4 + 424) = 0;
  CBaseVideoRenderer::ResetStreamingTimes((CBaseVideoRenderer *)v4);
  *((_DWORD *)this + 128) = 0;
  *(_QWORD *)this = &CRenderer::`vftable'{for `ISpecifyPropertyPages'};
  *(_QWORD *)v4 = &CRenderer::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 4) = &CRenderer::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 5) = &CRenderer::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 45) = &CRenderer::`vftable'{for `IQualProp'};
  *((_QWORD *)this + 46) = &CRenderer::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 62) = &CRenderer::`vftable'{for `IKsPropertySet'};
  *((_QWORD *)this + 63) = &CRenderer::`vftable'{for `IDrawVideoImage'};
  *((_QWORD *)this + 65) = &CDrawImage::`vftable';
  v7 = ((unsigned __int64)this + 704) & -(__int64)((CRenderer *)((char *)this + 664) != 0);
  *((_QWORD *)this + 66) = v7;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_DWORD *)this + 155) = 1;
  SetRectEmpty((LPRECT)((char *)this + 568));
  SetRectEmpty((LPRECT)((char *)this + 584));
  *((_DWORD *)this + 154) = 0;
  *((_QWORD *)this + 65) = &CDrawVideo::`vftable';
  *((_QWORD *)this + 78) = this;
  *((_QWORD *)this + 81) = (char *)this + 520;
  *((_QWORD *)this + 79) = v7;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 80) = v4 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CVideoWindow::CVideoWindow(
    (CRenderer *)((char *)this + 664),
    this,
    (CRenderer *)((char *)this + 200),
    *((struct IUnknown **)this + 2),
    v14);
  CVideoAllocator::CVideoAllocator(
    (CRenderer *)((char *)this + 1064),
    this,
    (CRenderer *)((char *)this + 2976),
    (CRenderer *)((char *)this + 200),
    a4);
  COverlay::COverlay(
    (CRenderer *)((char *)this + 1296),
    this,
    (CRenderer *)((char *)this + 2976),
    (CRenderer *)((char *)this + 200),
    v15);
  v8 = (char *)this + 1464;
  CVideoInputPin::CVideoInputPin((CRenderer *)((char *)this + 1464), this, (CRenderer *)((char *)this + 200), v9, v16);
  CImageDisplay::CImageDisplay((LPCRITICAL_SECTION)((char *)this + 1808));
  CDirectDraw::CDirectDraw(
    (CRenderer *)((char *)this + 2976),
    this,
    (CRenderer *)((char *)this + 200),
    *((struct IUnknown **)this + 2),
    a4);
  memset_0((char *)this + 4160, 0, 0x58u);
  *((_DWORD *)this + 1050) = 1;
  *((_DWORD *)this + 1048) = 1;
  *((_DWORD *)this + 1068) = GetSystemMetrics(80);
  *((_QWORD *)this + 540) = 0;
  *((_QWORD *)this + 539) = -1;
  *((_DWORD *)this + 1082) = 0;
  *((_QWORD *)this + 542) = 0;
  *((_QWORD *)this + 543) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 4352));
  *((_QWORD *)this + 549) = 0;
  *((_DWORD *)this + 1100) = -1;
  *((_QWORD *)this + 24) = (char *)this + 1464;
  *((_QWORD *)this + 531) = 0;
  LastErrorToHResult = CBaseWindow::PrepareWindow((CRenderer *)((char *)this + 704));
  if ( LastErrorToHResult < 0 )
    goto LABEL_4;
  v11 = *((_QWORD *)this + 66);
  *((_QWORD *)this + 70) = *(_QWORD *)(v11 + 80);
  *((_QWORD *)this + 69) = *(_QWORD *)(v11 + 24);
  *((_QWORD *)this + 113) = v8;
  *((_QWORD *)this + 125) = v8;
  CRenderer::GetCurrentMonitor(this);
  CImageDisplay::RefreshDisplayType((LPCRITICAL_SECTION)((char *)this + 1808), (PCNZCH)this + 4276);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 549) = EventW;
  if ( !EventW )
  {
    LastErrorToHResult = AmGetLastErrorToHResult();
LABEL_4:
    *a4 = LastErrorToHResult;
  }
  return this;
}

```

## disassembly

```asm
0x18009c2cc  push    rbx
0x18009c2ce  push    rbp
0x18009c2cf  push    rsi
0x18009c2d0  push    rdi
0x18009c2d1  push    r12
0x18009c2d3  push    r13
0x18009c2d5  push    r14
0x18009c2d7  push    r15
0x18009c2d9  sub     rsp, 38h
0x18009c2dd  lea     r14, [rcx+8]
0x18009c2e1  mov     [rsp+78h+var_58], r9; int *
0x18009c2e6  mov     r12, r9
0x18009c2e9  lea     rdx, CLSID_VideoRenderer; struct _GUID *
0x18009c2f0  mov     r15, rcx
0x18009c2f3  mov     r9, r8; struct IUnknown *
0x18009c2f6  mov     rcx, r14; this
0x18009c2f9  call    ??0CBaseRenderer@@QEAA@AEBU_GUID@@PEBGPEAUIUnknown@@PEAJI@Z; CBaseRenderer::CBaseRenderer(_GUID const &,ushort const *,IUnknown *,long *,uint)
0x18009c2fe  lea     rax, ??_7CBaseVideoRenderer@@6BCUnknown@@@; const CBaseVideoRenderer::`vftable'{for `CUnknown'}
0x18009c305  xor     r13d, r13d
0x18009c308  mov     [r14], rax
0x18009c30b  mov     rcx, r14; this
0x18009c30e  lea     rax, ??_7CBaseVideoRenderer@@6BIBaseFilter@@@; const CBaseVideoRenderer::`vftable'{for `IBaseFilter'}
0x18009c315  mov     [r14+174h], r13d
0x18009c31c  mov     [r14+18h], rax
0x18009c320  lea     rax, ??_7CMpegAudioCodec@@6BIAMovieSetup@@@; const CMpegAudioCodec::`vftable'{for `IAMovieSetup'}
0x18009c327  mov     [r14+20h], rax
0x18009c32b  lea     rax, ??_7CBaseVideoRenderer@@6BIQualProp@@@; const CBaseVideoRenderer::`vftable'{for `IQualProp'}
0x18009c332  mov     [r14+160h], rax
0x18009c339  lea     rax, ??_7CBaseVideoRenderer@@6BIQualityControl@@@; const CBaseVideoRenderer::`vftable'{for `IQualityControl'}
0x18009c340  mov     [r14+168h], rax
0x18009c347  mov     [r14+1A8h], r13
0x18009c34e  call    ?ResetStreamingTimes@CBaseVideoRenderer@@UEAAJXZ; CBaseVideoRenderer::ResetStreamingTimes(void)
0x18009c353  mov     [r15+200h], r13d
0x18009c35a  lea     rdi, [r15+208h]
0x18009c361  lea     rax, ??_7CRenderer@@6BISpecifyPropertyPages@@@; const CRenderer::`vftable'{for `ISpecifyPropertyPages'}
0x18009c368  mov     [r15], rax
0x18009c36b  lea     rsi, [r15+298h]
0x18009c372  lea     rax, ??_7CRenderer@@6BCUnknown@@@; const CRenderer::`vftable'{for `CUnknown'}
0x18009c379  mov     [r14], rax
0x18009c37c  lea     rbp, [rsi+28h]
0x18009c380  lea     rax, ??_7CRenderer@@6BIBaseFilter@@@; const CRenderer::`vftable'{for `IBaseFilter'}
0x18009c387  mov     [r15+20h], rax
0x18009c38b  lea     rcx, [rdi+30h]; lprc
0x18009c38f  lea     rax, ??_7CRenderer@@6BIAMovieSetup@@@; const CRenderer::`vftable'{for `IAMovieSetup'}
0x18009c396  mov     [r15+28h], rax
0x18009c39a  lea     rax, ??_7CRenderer@@6BIQualProp@@@; const CRenderer::`vftable'{for `IQualProp'}
0x18009c3a1  mov     [r15+168h], rax
0x18009c3a8  lea     rax, ??_7CRenderer@@6BIQualityControl@@@; const CRenderer::`vftable'{for `IQualityControl'}
0x18009c3af  mov     [r15+170h], rax
0x18009c3b6  lea     rax, ??_7CRenderer@@6BIKsPropertySet@@@; const CRenderer::`vftable'{for `IKsPropertySet'}
0x18009c3bd  mov     [r15+1F0h], rax
0x18009c3c4  lea     rax, ??_7CRenderer@@6BIDrawVideoImage@@@; const CRenderer::`vftable'{for `IDrawVideoImage'}
0x18009c3cb  mov     [r15+1F8h], rax
0x18009c3d2  mov     rax, rsi
0x18009c3d5  neg     rax
0x18009c3d8  lea     rax, ??_7CDrawImage@@6B@; const CDrawImage::`vftable'
0x18009c3df  mov     [rdi], rax
0x18009c3e2  sbb     rbx, rbx
0x18009c3e5  and     rbx, rbp
0x18009c3e8  mov     [rdi+8], rbx
0x18009c3ec  mov     [rdi+10h], r13
0x18009c3f0  mov     [rdi+18h], r13
0x18009c3f4  mov     [rdi+20h], r13
0x18009c3f8  mov     [rdi+28h], r13
0x18009c3fc  mov     [rdi+50h], r13
0x18009c400  mov     [rdi+58h], r13
0x18009c404  mov     r13d, 1
0x18009c40a  mov     [rdi+64h], r13d
0x18009c40e  call    cs:__imp_SetRectEmpty
0x18009c415  nop     dword ptr [rax+rax+00h]
0x18009c41a  lea     rcx, [rdi+40h]; lprc
0x18009c41e  call    cs:__imp_SetRectEmpty
0x18009c425  nop     dword ptr [rax+rax+00h]
0x18009c42a  mov     dword ptr [rdi+60h], 0
0x18009c431  lea     rax, ??_7CDrawVideo@@6B@; const CDrawVideo::`vftable'
0x18009c438  mov     [rdi], rax
0x18009c43b  mov     rcx, rsi; this
0x18009c43e  mov     [rdi+68h], r15
0x18009c442  mov     rax, r15
0x18009c445  mov     [r15+288h], rdi
0x18009c44c  neg     rax
0x18009c44f  mov     [r15+278h], rbx
0x18009c456  lea     rdi, [r15+0C8h]
0x18009c45d  sbb     rdx, rdx
0x18009c460  mov     qword ptr [r15+290h], 0
0x18009c46b  and     rdx, r14
0x18009c46e  mov     r8, rdi; struct CCritSec *
0x18009c471  mov     [r15+280h], rdx
0x18009c478  mov     rdx, r15; struct CRenderer *
0x18009c47b  mov     r9, [r15+10h]; struct IUnknown *
0x18009c47f  call    ??0CVideoWindow@@QEAA@PEAVCRenderer@@PEAVCCritSec@@PEAUIUnknown@@PEAJ@Z; CVideoWindow::CVideoWindow(CRenderer *,CCritSec *,IUnknown *,long *)
0x18009c484  lea     rbx, [r15+0BA0h]
0x18009c48b  lea     rcx, [r15+428h]; this
0x18009c492  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x18009c497  mov     r9, rdi; struct CCritSec *
0x18009c49a  mov     r8, rbx; struct CDirectDraw *
0x18009c49d  mov     rdx, r15; struct CRenderer *
0x18009c4a0  call    ??0CVideoAllocator@@QEAA@PEAVCRenderer@@PEAVCDirectDraw@@PEAVCCritSec@@PEAJ@Z; CVideoAllocator::CVideoAllocator(CRenderer *,CDirectDraw *,CCritSec *,long *)
0x18009c4a5  lea     rcx, [r15+510h]; this
0x18009c4ac  mov     r9, rdi; struct CCritSec *
0x18009c4af  mov     r8, rbx; struct CDirectDraw *
0x18009c4b2  mov     rdx, r15; struct CRenderer *
0x18009c4b5  call    ??0COverlay@@QEAA@PEAVCRenderer@@PEAVCDirectDraw@@PEAVCCritSec@@PEAJ@Z; COverlay::COverlay(CRenderer *,CDirectDraw *,CCritSec *,long *)
0x18009c4ba  lea     rsi, [r15+5B8h]
0x18009c4c1  mov     r8, rdi; struct CCritSec *
0x18009c4c4  mov     rcx, rsi; this
0x18009c4c7  mov     rdx, r15; struct CRenderer *
0x18009c4ca  call    ??0CVideoInputPin@@QEAA@PEAVCRenderer@@PEAVCCritSec@@PEAJPEBG@Z; CVideoInputPin::CVideoInputPin(CRenderer *,CCritSec *,long *,ushort const *)
0x18009c4cf  lea     r14, [r15+710h]
0x18009c4d6  mov     rcx, r14; lpCriticalSection
0x18009c4d9  call    ??0CImageDisplay@@QEAA@XZ; CImageDisplay::CImageDisplay(void)
0x18009c4de  mov     r9, [r15+10h]; struct IUnknown *
0x18009c4e2  mov     r8, rdi; struct CCritSec *
0x18009c4e5  mov     rdx, r15; struct CRenderer *
0x18009c4e8  mov     [rsp+78h+var_58], r12; int *
0x18009c4ed  mov     rcx, rbx; this
0x18009c4f0  call    ??0CDirectDraw@@QEAA@PEAVCRenderer@@PEAVCCritSec@@PEAUIUnknown@@PEAJ@Z; CDirectDraw::CDirectDraw(CRenderer *,CCritSec *,IUnknown *,long *)
0x18009c4f5  lea     rbx, [r15+1040h]
0x18009c4fc  xor     edx, edx; Val
0x18009c4fe  mov     rcx, rbx; void *
0x18009c501  lea     r8d, [r13+57h]; Size
0x18009c505  call    memset_0
0x18009c50a  lea     ecx, [r13+4Fh]; nIndex
0x18009c50e  mov     [rbx+28h], r13d
0x18009c512  mov     [rbx+20h], r13d
0x18009c516  call    cs:__imp_GetSystemMetrics
0x18009c51d  nop     dword ptr [rax+rax+00h]
0x18009c522  xor     edi, edi
0x18009c524  mov     [r15+10B0h], eax
0x18009c52b  mov     [r15+10E0h], rdi
0x18009c532  lea     rcx, [r15+1100h]; lpCriticalSection
0x18009c539  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009c53d  mov     [r15+10D8h], rbx
0x18009c544  mov     [r15+10E8h], edi
0x18009c54b  mov     [r15+10F0h], rdi
0x18009c552  mov     [r15+10F8h], rdi
0x18009c559  call    cs:__imp_InitializeCriticalSection
0x18009c560  nop     dword ptr [rax+rax+00h]
0x18009c565  mov     rcx, rbp; this
0x18009c568  mov     [r15+1128h], rdi
0x18009c56f  mov     [r15+1130h], ebx
0x18009c576  mov     [r15+0C0h], rsi
0x18009c57d  mov     [r15+1098h], rdi
0x18009c584  call    ?PrepareWindow@CBaseWindow@@UEAAJXZ; CBaseWindow::PrepareWindow(void)
0x18009c589  test    eax, eax
0x18009c58b  js      short loc_18009C5F6
0x18009c58d  mov     rdx, [r15+210h]
0x18009c594  mov     rcx, r15; this
0x18009c597  mov     rax, [rdx+50h]
0x18009c59b  mov     [r15+230h], rax
0x18009c5a2  mov     rax, [rdx+18h]
0x18009c5a6  mov     [r15+228h], rax
0x18009c5ad  mov     [r15+388h], rsi
0x18009c5b4  mov     [r15+3E8h], rsi
0x18009c5bb  call    ?GetCurrentMonitor@CRenderer@@QEAA_JXZ; CRenderer::GetCurrentMonitor(void)
0x18009c5c0  lea     rdx, [r15+10B4h]; lpString1
0x18009c5c7  mov     rcx, r14; lpCriticalSection
0x18009c5ca  call    ?RefreshDisplayType@CImageDisplay@@QEAAJPEAD@Z; CImageDisplay::RefreshDisplayType(char *)
0x18009c5cf  xor     r9d, r9d; lpName
0x18009c5d2  xor     r8d, r8d; bInitialState
0x18009c5d5  xor     edx, edx; bManualReset
0x18009c5d7  xor     ecx, ecx; lpEventAttributes
0x18009c5d9  call    cs:__imp_CreateEventW
0x18009c5e0  nop     dword ptr [rax+rax+00h]
0x18009c5e5  mov     [r15+1128h], rax
0x18009c5ec  test    rax, rax
0x18009c5ef  jnz     short loc_18009C5FA
0x18009c5f1  call    ?AmGetLastErrorToHResult@@YAJXZ; AmGetLastErrorToHResult(void)
0x18009c5f6  mov     [r12], eax
0x18009c5fa  mov     rax, r15
0x18009c5fd  add     rsp, 38h
0x18009c601  pop     r15
0x18009c603  pop     r14
0x18009c605  pop     r13
0x18009c607  pop     r12
0x18009c609  pop     rdi
0x18009c60a  pop     rsi
0x18009c60b  pop     rbp
0x18009c60c  pop     rbx
0x18009c60d  retn
```
