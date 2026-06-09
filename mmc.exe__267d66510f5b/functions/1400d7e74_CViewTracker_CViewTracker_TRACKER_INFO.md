# CViewTracker::CViewTracker(TRACKER_INFO &)

- ea: `0x1400d7e74`
- end: `0x1400d813f`
- name: `??0CViewTracker@@QEAA@AEAUTRACKER_INFO@@@Z`
- size: `715`
- prototype: `CViewTracker *__fastcall(CViewTracker *__hidden this, struct TRACKER_INFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400d8644`
- `0x1400d8698`

## callees

- `0x140008d90`
- `0x14000c1d0`
- `0x1400aee88`
- `0x1400d7e30`
- `0x1400d7e74`
- `0x1400d8554`

## import_xrefs

- `USER32!GetFocus` at `0x1400d801f`
- `USER32!GetFocus` at `0x1400d801f`
- `USER32!UpdateWindow` at `0x1400d7f07`
- `USER32!UpdateWindow` at `0x1400d7f07`
- `USER32!SystemParametersInfoW` at `0x1400d7eb1`
- `USER32!SystemParametersInfoW` at `0x1400d7eb1`
- `MFC42u!__imp_??0CClientDC@@QEAA@PEAVCWnd@@@Z` at `0x1400d7f46`
- `MFC42u!__imp_??0CClientDC@@QEAA@PEAVCWnd@@@Z` at `0x1400d7f46`
- `MFC42u!__imp_?AfxThrowMemoryException@@YAXXZ` at `0x1400d8108`
- `MFC42u!__imp_?AfxThrowMemoryException@@YAXXZ` at `0x1400d8108`
- `MFC42u!__imp_?GetHalftoneBrush@CDC@@SAPEAVCBrush@@XZ` at `0x1400d7f5f`
- `MFC42u!__imp_?GetHalftoneBrush@CDC@@SAPEAVCBrush@@XZ` at `0x1400d7f5f`
- `MFC42u!__imp_?GetStyle@CWnd@@QEBAKXZ` at `0x1400d7f1e`
- `MFC42u!__imp_?GetStyle@CWnd@@QEBAKXZ` at `0x1400d7f1e`
- `MFC42u!__imp_?GetTopLevelFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ` at `0x1400d80b8`
- `MFC42u!__imp_?GetTopLevelFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ` at `0x1400d80b8`
- `MFC42u!__imp_?ModifyStyle@CWnd@@QEAAHKKI@Z` at `0x1400d7f36`
- `MFC42u!__imp_?ModifyStyle@CWnd@@QEAAHKKI@Z` at `0x1400d7f36`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCBrush@@PEAV2@@Z` at `0x1400d7f6b`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCBrush@@PEAV2@@Z` at `0x1400d7f6b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d7ff7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d8120`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d7ff7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d8120`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400d8001`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400d8001`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400d7fb9`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400d7fb9`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x1400d800f`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x1400d800f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400d7fec`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400d7fec`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400d7fcb`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400d7fcb`

## pseudocode

```c
CViewTracker *__fastcall CViewTracker::CViewTracker(CViewTracker *this, struct TRACKER_INFO *a2)
{
  BOOL v4; // eax
  CWnd *v5; // r14
  struct CBrush *HalftoneBrush; // rax
  struct CBrush *v7; // rax
  __int64 v8; // rax
  CHeapFactory *v9; // rcx
  HWND Focus; // rsi
  unsigned int v11; // r8d
  CTrackingSubclasserBase *v12; // rax
  CTrackingSubclasserBase *v13; // rdi
  CTrackingSubclasserBase *v14; // rax
  CTrackingSubclasserBase *v15; // rdi
  struct CFrameWnd *TopLevelFrame; // rax
  CHeapFactory *v17; // rcx
  unsigned int v18; // r8d
  HWND v19; // rsi
  CTrackingSubclasserBase *v20; // rax
  CTrackingSubclasserBase *v21; // rdi
  _BYTE v23[24]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v24[24]; // [rsp+38h] [rbp-18h] BYREF
  CTrackingSubclasserBase *pvParam; // [rsp+78h] [rbp+28h] BYREF

  *(_QWORD *)this = &CViewTracker::`vftable';
  LODWORD(pvParam) = 0;
  v4 = SystemParametersInfoW(0x26u, 0, &pvParam, 0);
  if ( v4 )
    LOBYTE(v4) = (_DWORD)pvParam != 0;
  *((_BYTE *)this + 8) = v4;
  *((_BYTE *)this + 9) = 0;
  *((_OWORD *)this + 1) = *(_OWORD *)a2;
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 3) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 4);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 5);
  pvParam = (CViewTracker *)((char *)this + 112);
  v5 = *(CWnd **)a2;
  UpdateWindow(*(HWND *)(*(_QWORD *)a2 + 64LL));
  CWnd::SetCapture(v5);
  if ( !*((_BYTE *)this + 8) && (CWnd::GetStyle(v5) & 0x2000000) != 0 )
  {
    CWnd::ModifyStyle(v5, 0x2000000u, 0, 0);
    *((_BYTE *)this + 9) = 1;
  }
  CClientDC::CClientDC((CViewTracker *)((char *)this + 112), v5);
  *((_QWORD *)this + 14) = &CHalftoneClientDC::`vftable';
  *((_QWORD *)this + 19) = 0;
  HalftoneBrush = (struct CBrush *)CDC::GetHalftoneBrush();
  v7 = CDC::SelectObject((CViewTracker *)((char *)this + 112), HalftoneBrush);
  if ( v7 )
    *((_QWORD *)this + 19) = *((_QWORD *)v7 + 1);
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 46) = *((_DWORD *)a2 + 6);
  *((_QWORD *)this + 24) = 0;
  mmcerror::SC::SC((mmcerror::SC *)v23, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v23, L"CViewTracker::CViewTracker");
  v8 = ScCheckPointers(v24, *((_QWORD *)this + 2), 2147942487LL);
  mmcerror::SC::operator=(v23, v8);
  mmcerror::SC::~SC((mmcerror::SC *)v24);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v23) )
    mmcerror::SC::Throw((mmcerror::SC *)v23);
  if ( *((_BYTE *)this + 104) )
  {
    Focus = GetFocus();
    if ( Focus )
    {
      v12 = (CTrackingSubclasserBase *)CHeapFactory::Alloc(v9, 0x18u, v11);
      v13 = v12;
      pvParam = v12;
      if ( v12 )
      {
        CTrackingSubclasserBase::CTrackingSubclasserBase(v12, this, Focus);
        *(_QWORD *)v13 = &CFocusSubclasser::`vftable';
      }
      else
      {
        v13 = 0;
      }
      *((_QWORD *)this + 20) = v13;
      if ( !v13 )
        goto LABEL_26;
    }
    v14 = (CTrackingSubclasserBase *)CHeapFactory::Alloc(v9, 0x18u, v11);
    v15 = v14;
    pvParam = v14;
    if ( v14 )
    {
      CTrackingSubclasserBase::CTrackingSubclasserBase(v14, this, *(HWND *)(*((_QWORD *)this + 2) + 64LL));
      *(_QWORD *)v15 = &CViewSubclasser::`vftable';
    }
    else
    {
      v15 = 0;
    }
    *((_QWORD *)this + 21) = v15;
    if ( !v15 )
      goto LABEL_26;
    TopLevelFrame = CWnd::GetTopLevelFrame(*((CWnd **)this + 2));
    if ( TopLevelFrame )
    {
      v19 = (HWND)*((_QWORD *)TopLevelFrame + 8);
      if ( v19 )
      {
        v20 = (CTrackingSubclasserBase *)CHeapFactory::Alloc(v17, 0x18u, v18);
        v21 = v20;
        pvParam = v20;
        if ( v20 )
        {
          CTrackingSubclasserBase::CTrackingSubclasserBase(v20, this, v19);
          *(_QWORD *)v21 = &CFrameSubclasser::`vftable';
        }
        else
        {
          v21 = 0;
        }
        *((_QWORD *)this + 22) = v21;
        if ( !v21 )
LABEL_26:
          AfxThrowMemoryException();
      }
    }
  }
  CViewTracker::DrawTracker(this, (CViewTracker *)((char *)this + 40));
  mmcerror::SC::~SC((mmcerror::SC *)v23);
  return this;
}

```

## disassembly

```asm
0x1400d7e74  mov     [rsp-18h+arg_10], rbx
0x1400d7e79  mov     [rsp-18h+arg_18], rsi
0x1400d7e7e  mov     [rsp-18h+arg_0], rcx
0x1400d7e83  push    rbp
0x1400d7e84  push    rdi
0x1400d7e85  push    r14
0x1400d7e87  mov     rbp, rsp
0x1400d7e8a  sub     rsp, 50h
0x1400d7e8e  mov     rsi, rdx
0x1400d7e91  mov     rbx, rcx
0x1400d7e94  lea     rax, ??_7CViewTracker@@6B@; const CViewTracker::`vftable'
0x1400d7e9b  mov     [rcx], rax
0x1400d7e9e  mov     dword ptr [rbp+pvParam], 0
0x1400d7ea5  xor     r9d, r9d; fWinIni
0x1400d7ea8  lea     r8, [rbp+pvParam]; pvParam
0x1400d7eac  xor     edx, edx; uiParam
0x1400d7eae  lea     ecx, [rdx+26h]; uiAction
0x1400d7eb1  call    cs:__imp_SystemParametersInfoW
0x1400d7eb7  test    eax, eax
0x1400d7eb9  jz      short loc_1400D7EC2
0x1400d7ebb  cmp     dword ptr [rbp+pvParam], 0
0x1400d7ebf  setnz   al
0x1400d7ec2  mov     [rbx+8], al
0x1400d7ec5  mov     byte ptr [rbx+9], 0
0x1400d7ec9  movaps  xmm0, xmmword ptr [rsi]
0x1400d7ecc  movups  xmmword ptr [rbx+10h], xmm0
0x1400d7ed0  movaps  xmm1, xmmword ptr [rsi+10h]
0x1400d7ed4  movups  xmmword ptr [rbx+20h], xmm1
0x1400d7ed8  movaps  xmm0, xmmword ptr [rsi+20h]
0x1400d7edc  movups  xmmword ptr [rbx+30h], xmm0
0x1400d7ee0  movaps  xmm1, xmmword ptr [rsi+30h]
0x1400d7ee4  movups  xmmword ptr [rbx+40h], xmm1
0x1400d7ee8  movaps  xmm0, xmmword ptr [rsi+40h]
0x1400d7eec  movups  xmmword ptr [rbx+50h], xmm0
0x1400d7ef0  movaps  xmm1, xmmword ptr [rsi+50h]
0x1400d7ef4  movups  xmmword ptr [rbx+60h], xmm1
0x1400d7ef8  lea     rdi, [rbx+70h]
0x1400d7efc  mov     [rbp+pvParam], rdi
0x1400d7f00  mov     r14, [rsi]
0x1400d7f03  mov     rcx, [r14+40h]; hWnd
0x1400d7f07  call    cs:__imp_UpdateWindow
0x1400d7f0d  mov     rcx, r14; this
0x1400d7f10  call    ?SetCapture@CWnd@@QEAAPEAV1@XZ; CWnd::SetCapture(void)
0x1400d7f15  cmp     byte ptr [rbx+8], 0
0x1400d7f19  jnz     short loc_1400D7F40
0x1400d7f1b  mov     rcx, r14
0x1400d7f1e  call    cs:__imp_?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1400d7f24  mov     edx, 2000000h
0x1400d7f29  test    edx, eax
0x1400d7f2b  jz      short loc_1400D7F40
0x1400d7f2d  xor     r9d, r9d
0x1400d7f30  xor     r8d, r8d
0x1400d7f33  mov     rcx, r14
0x1400d7f36  call    cs:__imp_?ModifyStyle@CWnd@@QEAAHKKI@Z; CWnd::ModifyStyle(ulong,ulong,uint)
0x1400d7f3c  mov     byte ptr [rbx+9], 1
0x1400d7f40  mov     rdx, r14
0x1400d7f43  mov     rcx, rdi
0x1400d7f46  call    cs:__imp_??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x1400d7f4c  nop
0x1400d7f4d  lea     rax, ??_7CHalftoneClientDC@@6B@; const CHalftoneClientDC::`vftable'
0x1400d7f54  mov     [rdi], rax
0x1400d7f57  mov     qword ptr [rdi+28h], 0
0x1400d7f5f  call    cs:__imp_?GetHalftoneBrush@CDC@@SAPEAVCBrush@@XZ; CDC::GetHalftoneBrush(void)
0x1400d7f65  mov     rdx, rax
0x1400d7f68  mov     rcx, rdi
0x1400d7f6b  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCBrush@@PEAV2@@Z; CDC::SelectObject(CBrush *)
0x1400d7f71  test    rax, rax
0x1400d7f74  jz      short loc_1400D7F7E
0x1400d7f76  mov     rax, [rax+8]
0x1400d7f7a  mov     [rdi+28h], rax
0x1400d7f7e  mov     qword ptr [rbx+0A0h], 0
0x1400d7f89  mov     qword ptr [rbx+0A8h], 0
0x1400d7f94  mov     qword ptr [rbx+0B0h], 0
0x1400d7f9f  mov     eax, [rsi+18h]
0x1400d7fa2  mov     [rbx+0B8h], eax
0x1400d7fa8  mov     qword ptr [rbx+0C0h], 0
0x1400d7fb3  xor     edx, edx
0x1400d7fb5  lea     rcx, [rbp+var_30]
0x1400d7fb9  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400d7fbf  nop
0x1400d7fc0  lea     rdx, aCviewtrackerCv; "CViewTracker::CViewTracker"
0x1400d7fc7  lea     rcx, [rbp+var_30]
0x1400d7fcb  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400d7fd1  mov     r8d, 80070057h
0x1400d7fd7  mov     rdx, [rbx+10h]
0x1400d7fdb  lea     rcx, [rbp+var_18]
0x1400d7fdf  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1400d7fe4  nop
0x1400d7fe5  mov     rdx, rax
0x1400d7fe8  lea     rcx, [rbp+var_30]
0x1400d7fec  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400d7ff2  nop
0x1400d7ff3  lea     rcx, [rbp+var_18]
0x1400d7ff7  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400d7ffd  lea     rcx, [rbp+var_30]
0x1400d8001  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400d8007  test    al, al
0x1400d8009  jz      short loc_1400D8015
0x1400d800b  lea     rcx, [rbp+var_30]
0x1400d800f  call    cs:__imp_?Throw@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Throw(void)
0x1400d8015  cmp     byte ptr [rbx+68h], 0
0x1400d8019  jz      loc_1400D810F
0x1400d801f  call    cs:__imp_GetFocus
0x1400d8025  mov     rsi, rax
0x1400d8028  mov     r14d, 18h
0x1400d802e  test    rax, rax
0x1400d8031  jz      short loc_1400D8073
0x1400d8033  mov     edx, r14d; unsigned __int64
0x1400d8036  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x1400d803b  mov     rdi, rax
0x1400d803e  mov     [rbp+pvParam], rax
0x1400d8042  test    rax, rax
0x1400d8045  jz      short loc_1400D8061
0x1400d8047  mov     r8, rsi; HWND
0x1400d804a  mov     rdx, rbx; struct CViewTracker *
0x1400d804d  mov     rcx, rax; this
0x1400d8050  call    ??0CTrackingSubclasserBase@@QEAA@PEAVCViewTracker@@PEAUHWND__@@@Z; CTrackingSubclasserBase::CTrackingSubclasserBase(CViewTracker *,HWND__ *)
0x1400d8055  lea     rax, ??_7CFocusSubclasser@@6B@; const CFocusSubclasser::`vftable'
0x1400d805c  mov     [rdi], rax
0x1400d805f  jmp     short loc_1400D8063
0x1400d8061  xor     edi, edi
0x1400d8063  mov     [rbx+0A0h], rdi
0x1400d806a  test    rdi, rdi
0x1400d806d  jz      loc_1400D8108
0x1400d8073  mov     rdx, r14; unsigned __int64
0x1400d8076  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x1400d807b  mov     rdi, rax
0x1400d807e  mov     [rbp+pvParam], rax
0x1400d8082  test    rax, rax
0x1400d8085  jz      short loc_1400D80A6
0x1400d8087  mov     r8, [rbx+10h]
0x1400d808b  mov     r8, [r8+40h]; HWND
0x1400d808f  mov     rdx, rbx; struct CViewTracker *
0x1400d8092  mov     rcx, rax; this
0x1400d8095  call    ??0CTrackingSubclasserBase@@QEAA@PEAVCViewTracker@@PEAUHWND__@@@Z; CTrackingSubclasserBase::CTrackingSubclasserBase(CViewTracker *,HWND__ *)
0x1400d809a  lea     rax, ??_7CViewSubclasser@@6B@; const CViewSubclasser::`vftable'
0x1400d80a1  mov     [rdi], rax
0x1400d80a4  jmp     short loc_1400D80A8
0x1400d80a6  xor     edi, edi
0x1400d80a8  mov     [rbx+0A8h], rdi
0x1400d80af  test    rdi, rdi
0x1400d80b2  jz      short loc_1400D8108
0x1400d80b4  mov     rcx, [rbx+10h]
0x1400d80b8  call    cs:__imp_?GetTopLevelFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetTopLevelFrame(void)
0x1400d80be  test    rax, rax
0x1400d80c1  jz      short loc_1400D810F
0x1400d80c3  mov     rsi, [rax+40h]
0x1400d80c7  test    rsi, rsi
0x1400d80ca  jz      short loc_1400D810F
0x1400d80cc  mov     rdx, r14; unsigned __int64
0x1400d80cf  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x1400d80d4  mov     rdi, rax
0x1400d80d7  mov     [rbp+pvParam], rax
0x1400d80db  test    rax, rax
0x1400d80de  jz      short loc_1400D80FA
0x1400d80e0  mov     r8, rsi; HWND
0x1400d80e3  mov     rdx, rbx; struct CViewTracker *
0x1400d80e6  mov     rcx, rax; this
0x1400d80e9  call    ??0CTrackingSubclasserBase@@QEAA@PEAVCViewTracker@@PEAUHWND__@@@Z; CTrackingSubclasserBase::CTrackingSubclasserBase(CViewTracker *,HWND__ *)
0x1400d80ee  lea     rax, ??_7CFrameSubclasser@@6B@; const CFrameSubclasser::`vftable'
0x1400d80f5  mov     [rdi], rax
0x1400d80f8  jmp     short loc_1400D80FC
0x1400d80fa  xor     edi, edi
0x1400d80fc  mov     [rbx+0B0h], rdi
0x1400d8103  test    rdi, rdi
0x1400d8106  jnz     short loc_1400D810F
0x1400d8108  call    cs:__imp_?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
0x1400d810f  lea     rdx, [rbx+28h]; struct CRect *
0x1400d8113  mov     rcx, rbx; this
0x1400d8116  call    ?DrawTracker@CViewTracker@@AEBAXAEAVCRect@@@Z; CViewTracker::DrawTracker(CRect &)
0x1400d811b  nop
0x1400d811c  lea     rcx, [rbp+var_30]
0x1400d8120  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400d8126  nop
0x1400d8127  mov     rax, rbx
0x1400d812a  lea     r11, [rsp+50h+var_s0]
0x1400d812f  mov     rbx, [r11+30h]
0x1400d8133  mov     rsi, [r11+38h]
0x1400d8137  mov     rsp, r11
0x1400d813a  pop     r14
0x1400d813c  pop     rdi
0x1400d813d  pop     rbp
0x1400d813e  retn
```
