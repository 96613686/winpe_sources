# CTray::RecomputeWorkArea(HMONITOR__ *,tagRECT *)

- ea: `0x14008cc40`
- end: `0x14008ceda`
- name: `?RecomputeWorkArea@CTray@@AEAAHPEAUHMONITOR__@@PEAUtagRECT@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(CTray *__hidden this, HMONITOR, struct tagRECT *)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140076810`
- `0x14008e0d0`
- `0x140112ec0`

## callees

- `0x140006c50`
- `0x140031564`
- `0x14004a5c4`
- `0x1400656ec`
- `0x140076ffc`
- `0x14008cc40`
- `0x14008d0b4`
- `0x1400b53fc`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x14008cc94`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x14008cc94`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x14008cdb0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x14008ce5d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x14008cdb0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x14008ce5d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x14008ccd2`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x14008ccd2`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x14008cd5c`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x14008cd5c`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14008ccba`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14008cdce`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14008ce1b`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14008ccba`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14008cdce`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14008ce1b`

## pseudocode

```c
_BOOL8 __fastcall CTray::RecomputeWorkArea(CTray *this, struct ITrayUIHost *a2, struct tagRECT *a3)
{
  bool v7; // si
  CTray *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  char v11; // al
  RECT *p_rc; // r8
  BOOL v13; // eax
  __int64 v14; // rcx
  BOOL v15; // r15d
  BOOL v16; // r12d
  struct tagRECT *v17; // r9
  bool v18; // al
  struct tagRECT v19; // xmm0
  bool v20; // [rsp+30h] [rbp-79h] BYREF
  bool v21; // [rsp+31h] [rbp-78h] BYREF
  int v22; // [rsp+34h] [rbp-75h] BYREF
  unsigned int DPIForMonitor; // [rsp+38h] [rbp-71h] BYREF
  RECT rc; // [rsp+40h] [rbp-69h] BYREF
  RECT rc2; // [rsp+50h] [rbp-59h] BYREF
  RECT rcSrc2; // [rsp+60h] [rbp-49h] BYREF
  struct tagRECT rcDst; // [rsp+70h] [rbp-39h] BYREF
  HMONITOR__ v28[4]; // [rsp+80h] [rbp-29h] BYREF
  struct tagMONITORINFO mi; // [rsp+90h] [rbp-19h] BYREF
  __int128 v30; // [rsp+B8h] [rbp+Fh] BYREF

  mi.cbSize = 40;
  mi.dwFlags = 0;
  *a3 = 0;
  memset(&mi.rcMonitor, 0, 32);
  if ( !GetMonitorInfoW((HMONITOR)a2, &mi) )
    return 0;
  if ( *((_DWORD *)this + 51) )
  {
    *a3 = mi.rcMonitor;
    return !EqualRect(a3, &mi.rcWork);
  }
  CopyRect(a3, &mi.rcMonitor);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 120LL))(*((_QWORD *)this + 133));
  v7 = ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 144LL))(*((_QWORD *)this + 133)) & 1) == 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl'::`2'::impl)
    && CTray::IsTrayCloaked(v8) )
  {
    v7 = 0;
  }
  v9 = *((_QWORD *)this + 133);
  rc = 0;
  (*(void (__fastcall **)(__int64, struct ITrayUIHost *, RECT *))(*(_QWORD *)v9 + 136LL))(v9, a2, &rc);
  if ( (unsigned int)TrayCommon::GetMultiMonTaskbarState() == 2 )
  {
    if ( IsRectEmpty(&rc) )
      return 0;
  }
  if ( v7 )
  {
    v10 = *((_QWORD *)this + 133);
    v30 = 0;
    *(_OWORD *)&v28[0].unused = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, struct ITrayUIHost *, __int128 *, HMONITOR__ *))(*(_QWORD *)v10 + 128LL))(
            v10,
            a2,
            &v30,
            v28);
    p_rc = (RECT *)&v30;
    if ( !v11 )
      p_rc = &rc;
    SubtractRect(a3, a3, p_rc);
  }
  v20 = CTray::_AppBarSubtractRects(this, (HMONITOR)a2, a3);
  v13 = EqualRect(a3, &mi.rcWork);
  v14 = *((_QWORD *)this + 133);
  v15 = v13;
  rc2 = 0;
  v16 = !v13;
  rcSrc2 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int64, struct ITrayUIHost *, RECT *, RECT *))(*(_QWORD *)v14 + 128LL))(
         v14,
         a2,
         &rc2,
         &rcSrc2) )
  {
    v18 = !EqualRect(&rc, &rc2);
  }
  else
  {
    v18 = 0;
    rc2 = rc;
    rcSrc2 = rc;
  }
  v19 = *a3;
  rcDst = *a3;
  if ( (!v7 || v18) && *((_DWORD *)this + 121) != 1 )
  {
    SubtractRect(&rcDst, &rcDst, &rcSrc2);
    v19 = rcDst;
  }
  *(struct tagRECT *)&v28[0].unused = v19;
  ImmersiveTray::NotifyAutohideImmuneWorkAreaMayHaveChanged((CTray *)((char *)this + 56), a2, v28, v17);
  v22 = (int)a2;
  DPIForMonitor = GetDPIForMonitor((HMONITOR)a2);
  v21 = !v15;
  TrayTelemetry::TrayCalculatedWorkArea<bool,bool &,int &,unsigned int,unsigned long,tagRECT &>(
    (int)&v21,
    (int)&v20,
    (_DWORD)this + 72,
    (int)&DPIForMonitor,
    (__int64)&v22,
    a3);
  return v16;
}

```

## disassembly

```asm
0x14008cc40  push    rbp
0x14008cc42  push    rbx
0x14008cc43  push    rsi
0x14008cc44  push    rdi
0x14008cc45  push    r12
0x14008cc47  push    r14
0x14008cc49  push    r15
0x14008cc4b  lea     rbp, [rsp-27h]
0x14008cc50  sub     rsp, 0D0h
0x14008cc57  mov     rax, cs:__security_cookie
0x14008cc5e  xor     rax, rsp
0x14008cc61  mov     [rbp+57h+var_38], rax
0x14008cc65  mov     r14, rdx
0x14008cc68  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x14008cc6f  xorps   xmm1, xmm1
0x14008cc72  lea     rdx, [rbp+57h+mi]; lpmi
0x14008cc76  mov     rdi, rcx
0x14008cc79  xorps   xmm0, xmm0
0x14008cc7c  xor     eax, eax
0x14008cc7e  mov     rcx, r14; hMonitor
0x14008cc81  mov     rbx, r8
0x14008cc84  mov     [rbp+57h+mi.dwFlags], eax
0x14008cc87  movdqu  xmmword ptr [r8], xmm0
0x14008cc8c  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm1
0x14008cc90  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm1
0x14008cc94  call    cs:__imp_GetMonitorInfoW
0x14008cc9a  test    eax, eax
0x14008cc9c  jz      loc_14008CEBA
0x14008cca2  cmp     dword ptr [rdi+0CCh], 0
0x14008cca9  mov     rcx, rbx; lprcDst
0x14008ccac  jz      short loc_14008CCCE
0x14008ccae  movups  xmm0, xmmword ptr [rbp+57h+mi.rcMonitor.left]
0x14008ccb2  lea     rdx, [rbp+57h+mi.rcWork]; lprc2
0x14008ccb6  movdqu  xmmword ptr [rbx], xmm0
0x14008ccba  call    cs:__imp_EqualRect
0x14008ccc0  xor     ecx, ecx
0x14008ccc2  test    eax, eax
0x14008ccc4  setz    cl
0x14008ccc7  mov     eax, ecx
0x14008ccc9  jmp     loc_14008CEBC
0x14008ccce  lea     rdx, [rbp+57h+mi.rcMonitor]; lprcSrc
0x14008ccd2  call    cs:__imp_CopyRect
0x14008ccd8  mov     rcx, [rdi+428h]
0x14008ccdf  mov     rax, [rcx]
0x14008cce2  mov     rax, [rax+78h]
0x14008cce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cceb  mov     rcx, [rdi+428h]
0x14008ccf2  mov     rax, [rcx]
0x14008ccf5  mov     rax, [rax+90h]
0x14008ccfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cd01  mov     esi, eax
0x14008cd03  not     sil
0x14008cd06  and     sil, 1
0x14008cd0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x14008cd11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x14008cd16  test    al, al
0x14008cd18  jz      short loc_14008CD2A
0x14008cd1a  call    ?IsTrayCloaked@CTray@@QEAA_NXZ; CTray::IsTrayCloaked(void)
0x14008cd1f  xor     ecx, ecx
0x14008cd21  movzx   esi, sil
0x14008cd25  test    al, al
0x14008cd27  cmovnz  esi, ecx
0x14008cd2a  mov     rcx, [rdi+428h]
0x14008cd31  lea     r8, [rbp+57h+rc]
0x14008cd35  xorps   xmm0, xmm0
0x14008cd38  mov     rdx, r14
0x14008cd3b  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x14008cd3f  mov     rax, [rcx]
0x14008cd42  mov     rax, [rax+88h]
0x14008cd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cd4e  call    ?GetMultiMonTaskbarState@TrayCommon@@YA?AW4MultiMonTaskbarState@1@XZ; TrayCommon::GetMultiMonTaskbarState(void)
0x14008cd53  cmp     eax, 2
0x14008cd56  jnz     short loc_14008CD6A
0x14008cd58  lea     rcx, [rbp+57h+rc]; lprc
0x14008cd5c  call    cs:__imp_IsRectEmpty
0x14008cd62  test    eax, eax
0x14008cd64  jnz     loc_14008CEBA
0x14008cd6a  test    sil, sil
0x14008cd6d  jz      short loc_14008CDB6
0x14008cd6f  mov     rcx, [rdi+428h]
0x14008cd76  lea     r9, [rbp+57h+var_80]
0x14008cd7a  xorps   xmm0, xmm0
0x14008cd7d  lea     r8, [rbp+57h+var_48]
0x14008cd81  xorps   xmm1, xmm1
0x14008cd84  mov     rdx, r14
0x14008cd87  movups  [rbp+57h+var_48], xmm0
0x14008cd8b  movups  xmmword ptr [rbp+57h+var_80.unused], xmm1
0x14008cd8f  mov     rax, [rcx]
0x14008cd92  mov     rax, [rax+80h]
0x14008cd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cd9e  lea     r8, [rbp+57h+var_48]
0x14008cda2  mov     rdx, rbx; lprcSrc1
0x14008cda5  mov     rcx, rbx; lprcDst
0x14008cda8  test    al, al
0x14008cdaa  jnz     short loc_14008CDB0
0x14008cdac  lea     r8, [rbp+57h+rc]; lprcSrc2
0x14008cdb0  call    cs:__imp_SubtractRect
0x14008cdb6  mov     r8, rbx; struct tagRECT *
0x14008cdb9  mov     rdx, r14; HMONITOR
0x14008cdbc  mov     rcx, rdi; this
0x14008cdbf  call    ?_AppBarSubtractRects@CTray@@IEAA_NPEAUHMONITOR__@@PEAUtagRECT@@@Z; CTray::_AppBarSubtractRects(HMONITOR__ *,tagRECT *)
0x14008cdc4  lea     rdx, [rbp+57h+mi.rcWork]; lprc2
0x14008cdc8  mov     byte ptr [rbp+57h+var_D0], al
0x14008cdcb  mov     rcx, rbx; lprc1
0x14008cdce  call    cs:__imp_EqualRect
0x14008cdd4  mov     rcx, [rdi+428h]
0x14008cddb  lea     r9, [rbp+57h+rcSrc2]
0x14008cddf  xorps   xmm0, xmm0
0x14008cde2  lea     r8, [rbp+57h+rc2]
0x14008cde6  xorps   xmm1, xmm1
0x14008cde9  xor     r12d, r12d
0x14008cdec  test    eax, eax
0x14008cdee  mov     r15d, eax
0x14008cdf1  movups  xmmword ptr [rbp+57h+rc2.left], xmm0
0x14008cdf5  setz    r12b
0x14008cdf9  movups  xmmword ptr [rbp+57h+rcSrc2.left], xmm1
0x14008cdfd  mov     rdx, [rcx]
0x14008ce00  mov     rax, [rdx+80h]
0x14008ce07  mov     rdx, r14
0x14008ce0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ce0f  test    al, al
0x14008ce11  jz      short loc_14008CE28
0x14008ce13  lea     rdx, [rbp+57h+rc2]; lprc2
0x14008ce17  lea     rcx, [rbp+57h+rc]; lprc1
0x14008ce1b  call    cs:__imp_EqualRect
0x14008ce21  test    eax, eax
0x14008ce23  setz    al
0x14008ce26  jmp     short loc_14008CE38
0x14008ce28  movaps  xmm0, xmmword ptr [rbp+57h+rc.left]
0x14008ce2c  xor     al, al
0x14008ce2e  movdqa  xmmword ptr [rbp+57h+rc2.left], xmm0
0x14008ce33  movdqa  xmmword ptr [rbp+57h+rcSrc2.left], xmm0
0x14008ce38  movups  xmm0, xmmword ptr [rbx]
0x14008ce3b  movaps  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x14008ce3f  test    sil, sil
0x14008ce42  jz      short loc_14008CE48
0x14008ce44  test    al, al
0x14008ce46  jz      short loc_14008CE67
0x14008ce48  cmp     dword ptr [rdi+1E4h], 1
0x14008ce4f  jz      short loc_14008CE67
0x14008ce51  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x14008ce55  lea     rdx, [rbp+57h+rcDst]; lprcSrc1
0x14008ce59  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x14008ce5d  call    cs:__imp_SubtractRect
0x14008ce63  movaps  xmm0, xmmword ptr [rbp+57h+rcDst.left]
0x14008ce67  lea     rcx, [rdi+38h]; this
0x14008ce6b  movdqa  xmmword ptr [rbp+57h+var_80.unused], xmm0
0x14008ce70  lea     r8, [rbp+57h+var_80]; HMONITOR
0x14008ce74  mov     rdx, r14; struct ITrayUIHost *
0x14008ce77  call    ?NotifyAutohideImmuneWorkAreaMayHaveChanged@ImmersiveTray@@YAXPEAUITrayUIHost@@PEAUHMONITOR__@@UtagRECT@@@Z; ImmersiveTray::NotifyAutohideImmuneWorkAreaMayHaveChanged(ITrayUIHost *,HMONITOR__ *,tagRECT)
0x14008ce7c  mov     rcx, r14; HMONITOR
0x14008ce7f  mov     dword ptr [rbp+57h+var_CC], r14d
0x14008ce83  call    ?GetDPIForMonitor@@YAIPEAUHMONITOR__@@@Z; GetDPIForMonitor(HMONITOR__ *)
0x14008ce88  mov     dword ptr [rbp+57h+var_CC+4], eax
0x14008ce8b  lea     r8, [rdi+48h]; int
0x14008ce8f  test    r15d, r15d
0x14008ce92  mov     [rsp+100h+var_D8], rbx; struct tagRECT *
0x14008ce97  lea     rax, [rbp+57h+var_CC]
0x14008ce9b  lea     r9, [rbp+57h+var_CC+4]; int
0x14008ce9f  mov     [rsp+100h+var_E0], rax; __int64
0x14008cea4  lea     rdx, [rbp+57h+var_D0]; int
0x14008cea8  setz    byte ptr [rbp+57h+var_D0+1]
0x14008ceac  lea     rcx, [rbp+57h+var_D0+1]; int
0x14008ceb0  call    ??$TrayCalculatedWorkArea@_NAEA_NAEAHIKAEAUtagRECT@@@TrayTelemetry@@SAX$$QEA_NAEA_NAEAH$$QEAI$$QEAKAEAUtagRECT@@@Z; TrayTelemetry::TrayCalculatedWorkArea<bool,bool &,int &,uint,ulong,tagRECT &>(bool &&,bool &,int &,uint &&,ulong &&,tagRECT &)
0x14008ceb5  mov     eax, r12d
0x14008ceb8  jmp     short loc_14008CEBC
0x14008ceba  xor     eax, eax
0x14008cebc  mov     rcx, [rbp+57h+var_38]
0x14008cec0  xor     rcx, rsp; StackCookie
0x14008cec3  call    __security_check_cookie
0x14008cec8  add     rsp, 0D0h
0x14008cecf  pop     r15
0x14008ced1  pop     r14
0x14008ced3  pop     r12
0x14008ced5  pop     rdi
0x14008ced6  pop     rsi
0x14008ced7  pop     rbx
0x14008ced8  pop     rbp
0x14008ced9  retn
```
