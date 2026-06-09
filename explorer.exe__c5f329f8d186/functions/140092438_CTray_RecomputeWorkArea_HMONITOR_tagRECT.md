# CTray::RecomputeWorkArea(HMONITOR__ *,tagRECT *)

- ea: `0x140092438`
- end: `0x140092703`
- name: `?RecomputeWorkArea@CTray@@AEAAHPEAUHMONITOR__@@PEAUtagRECT@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(CTray *__hidden this, HMONITOR, struct tagRECT *)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x14007b920`
- `0x1400937f0`
- `0x14011d5a0`

## callees

- `0x140023d84`
- `0x140044d78`
- `0x140068068`
- `0x14007bf70`
- `0x140080c80`
- `0x1400923f0`
- `0x140092438`
- `0x1400bb4e0`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x14009248c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x14009248c`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1400924d6`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1400924d6`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x1400925c0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x14009267f`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x1400925c0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x14009267f`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1400924b8`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1400925e4`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x140092637`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1400924b8`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1400925e4`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x140092637`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140092566`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140092566`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl'::`2'::impl)
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
0x140092438  push    rbp
0x14009243a  push    rbx
0x14009243b  push    rsi
0x14009243c  push    rdi
0x14009243d  push    r12
0x14009243f  push    r14
0x140092441  push    r15
0x140092443  lea     rbp, [rsp-27h]
0x140092448  sub     rsp, 0D0h
0x14009244f  mov     rax, cs:__security_cookie
0x140092456  xor     rax, rsp
0x140092459  mov     [rbp+57h+var_38], rax
0x14009245d  mov     r14, rdx
0x140092460  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x140092467  xorps   xmm1, xmm1
0x14009246a  lea     rdx, [rbp+57h+mi]; lpmi
0x14009246e  mov     rdi, rcx
0x140092471  xorps   xmm0, xmm0
0x140092474  xor     eax, eax
0x140092476  mov     rcx, r14; hMonitor
0x140092479  mov     rbx, r8
0x14009247c  mov     [rbp+57h+mi.dwFlags], eax
0x14009247f  movdqu  xmmword ptr [r8], xmm0
0x140092484  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm1
0x140092488  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm1
0x14009248c  call    cs:__imp_GetMonitorInfoW
0x140092493  nop     dword ptr [rax+rax+00h]
0x140092498  test    eax, eax
0x14009249a  jz      loc_1400926E2
0x1400924a0  cmp     dword ptr [rdi+0CCh], 0
0x1400924a7  mov     rcx, rbx; lprcDst
0x1400924aa  jz      short loc_1400924D2
0x1400924ac  movups  xmm0, xmmword ptr [rbp+57h+mi.rcMonitor.left]
0x1400924b0  lea     rdx, [rbp+57h+mi.rcWork]; lprc2
0x1400924b4  movdqu  xmmword ptr [rbx], xmm0
0x1400924b8  call    cs:__imp_EqualRect
0x1400924bf  nop     dword ptr [rax+rax+00h]
0x1400924c4  xor     ecx, ecx
0x1400924c6  test    eax, eax
0x1400924c8  setz    cl
0x1400924cb  mov     eax, ecx
0x1400924cd  jmp     loc_1400926E4
0x1400924d2  lea     rdx, [rbp+57h+mi.rcMonitor]; lprcSrc
0x1400924d6  call    cs:__imp_CopyRect
0x1400924dd  nop     dword ptr [rax+rax+00h]
0x1400924e2  mov     rcx, [rdi+428h]
0x1400924e9  mov     rax, [rcx]
0x1400924ec  mov     rax, [rax+78h]
0x1400924f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400924f5  mov     rcx, [rdi+428h]
0x1400924fc  mov     rax, [rcx]
0x1400924ff  mov     rax, [rax+90h]
0x140092506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009250b  mov     esi, eax
0x14009250d  not     sil
0x140092510  and     sil, 1
0x140092514  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x14009251b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x140092520  test    al, al
0x140092522  jz      short loc_140092534
0x140092524  call    ?IsTrayCloaked@CTray@@QEAA_NXZ; CTray::IsTrayCloaked(void)
0x140092529  xor     ecx, ecx
0x14009252b  movzx   esi, sil
0x14009252f  test    al, al
0x140092531  cmovnz  esi, ecx
0x140092534  mov     rcx, [rdi+428h]
0x14009253b  lea     r8, [rbp+57h+rc]
0x14009253f  xorps   xmm0, xmm0
0x140092542  mov     rdx, r14
0x140092545  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x140092549  mov     rax, [rcx]
0x14009254c  mov     rax, [rax+88h]
0x140092553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092558  call    ?GetMultiMonTaskbarState@TrayCommon@@YA?AW4MultiMonTaskbarState@1@XZ; TrayCommon::GetMultiMonTaskbarState(void)
0x14009255d  cmp     eax, 2
0x140092560  jnz     short loc_14009257A
0x140092562  lea     rcx, [rbp+57h+rc]; lprc
0x140092566  call    cs:__imp_IsRectEmpty
0x14009256d  nop     dword ptr [rax+rax+00h]
0x140092572  test    eax, eax
0x140092574  jnz     loc_1400926E2
0x14009257a  test    sil, sil
0x14009257d  jz      short loc_1400925CC
0x14009257f  mov     rcx, [rdi+428h]
0x140092586  lea     r9, [rbp+57h+var_80]
0x14009258a  xorps   xmm0, xmm0
0x14009258d  lea     r8, [rbp+57h+var_48]
0x140092591  xorps   xmm1, xmm1
0x140092594  mov     rdx, r14
0x140092597  movups  [rbp+57h+var_48], xmm0
0x14009259b  movups  xmmword ptr [rbp+57h+var_80.unused], xmm1
0x14009259f  mov     rax, [rcx]
0x1400925a2  mov     rax, [rax+80h]
0x1400925a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400925ae  lea     r8, [rbp+57h+var_48]
0x1400925b2  mov     rdx, rbx; lprcSrc1
0x1400925b5  mov     rcx, rbx; lprcDst
0x1400925b8  test    al, al
0x1400925ba  jnz     short loc_1400925C0
0x1400925bc  lea     r8, [rbp+57h+rc]; lprcSrc2
0x1400925c0  call    cs:__imp_SubtractRect
0x1400925c7  nop     dword ptr [rax+rax+00h]
0x1400925cc  mov     r8, rbx; struct tagRECT *
0x1400925cf  mov     rdx, r14; HMONITOR
0x1400925d2  mov     rcx, rdi; this
0x1400925d5  call    ?_AppBarSubtractRects@CTray@@IEAA_NPEAUHMONITOR__@@PEAUtagRECT@@@Z; CTray::_AppBarSubtractRects(HMONITOR__ *,tagRECT *)
0x1400925da  lea     rdx, [rbp+57h+mi.rcWork]; lprc2
0x1400925de  mov     byte ptr [rbp+57h+var_D0], al
0x1400925e1  mov     rcx, rbx; lprc1
0x1400925e4  call    cs:__imp_EqualRect
0x1400925eb  nop     dword ptr [rax+rax+00h]
0x1400925f0  mov     rcx, [rdi+428h]
0x1400925f7  lea     r9, [rbp+57h+rcSrc2]
0x1400925fb  xorps   xmm0, xmm0
0x1400925fe  lea     r8, [rbp+57h+rc2]
0x140092602  xorps   xmm1, xmm1
0x140092605  xor     r12d, r12d
0x140092608  test    eax, eax
0x14009260a  mov     r15d, eax
0x14009260d  movups  xmmword ptr [rbp+57h+rc2.left], xmm0
0x140092611  setz    r12b
0x140092615  movups  xmmword ptr [rbp+57h+rcSrc2.left], xmm1
0x140092619  mov     rdx, [rcx]
0x14009261c  mov     rax, [rdx+80h]
0x140092623  mov     rdx, r14
0x140092626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009262b  test    al, al
0x14009262d  jz      short loc_14009264A
0x14009262f  lea     rdx, [rbp+57h+rc2]; lprc2
0x140092633  lea     rcx, [rbp+57h+rc]; lprc1
0x140092637  call    cs:__imp_EqualRect
0x14009263e  nop     dword ptr [rax+rax+00h]
0x140092643  test    eax, eax
0x140092645  setz    al
0x140092648  jmp     short loc_14009265A
0x14009264a  movaps  xmm0, xmmword ptr [rbp+57h+rc.left]
0x14009264e  xor     al, al
0x140092650  movdqa  xmmword ptr [rbp+57h+rc2.left], xmm0
0x140092655  movdqa  xmmword ptr [rbp+57h+rcSrc2.left], xmm0
0x14009265a  movups  xmm0, xmmword ptr [rbx]
0x14009265d  movaps  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x140092661  test    sil, sil
0x140092664  jz      short loc_14009266A
0x140092666  test    al, al
0x140092668  jz      short loc_14009268F
0x14009266a  cmp     dword ptr [rdi+1E4h], 1
0x140092671  jz      short loc_14009268F
0x140092673  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x140092677  lea     rdx, [rbp+57h+rcDst]; lprcSrc1
0x14009267b  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x14009267f  call    cs:__imp_SubtractRect
0x140092686  nop     dword ptr [rax+rax+00h]
0x14009268b  movaps  xmm0, xmmword ptr [rbp+57h+rcDst.left]
0x14009268f  lea     rcx, [rdi+38h]; this
0x140092693  movdqa  xmmword ptr [rbp+57h+var_80.unused], xmm0
0x140092698  lea     r8, [rbp+57h+var_80]; HMONITOR
0x14009269c  mov     rdx, r14; struct ITrayUIHost *
0x14009269f  call    ?NotifyAutohideImmuneWorkAreaMayHaveChanged@ImmersiveTray@@YAXPEAUITrayUIHost@@PEAUHMONITOR__@@UtagRECT@@@Z; ImmersiveTray::NotifyAutohideImmuneWorkAreaMayHaveChanged(ITrayUIHost *,HMONITOR__ *,tagRECT)
0x1400926a4  mov     rcx, r14; HMONITOR
0x1400926a7  mov     dword ptr [rbp+57h+var_CC], r14d
0x1400926ab  call    ?GetDPIForMonitor@@YAIPEAUHMONITOR__@@@Z; GetDPIForMonitor(HMONITOR__ *)
0x1400926b0  mov     dword ptr [rbp+57h+var_CC+4], eax
0x1400926b3  lea     r8, [rdi+48h]; int
0x1400926b7  test    r15d, r15d
0x1400926ba  mov     [rsp+100h+var_D8], rbx; struct tagRECT *
0x1400926bf  lea     rax, [rbp+57h+var_CC]
0x1400926c3  lea     r9, [rbp+57h+var_CC+4]; int
0x1400926c7  mov     [rsp+100h+var_E0], rax; __int64
0x1400926cc  lea     rdx, [rbp+57h+var_D0]; int
0x1400926d0  setz    byte ptr [rbp+57h+var_D0+1]
0x1400926d4  lea     rcx, [rbp+57h+var_D0+1]; int
0x1400926d8  call    ??$TrayCalculatedWorkArea@_NAEA_NAEAHIKAEAUtagRECT@@@TrayTelemetry@@SAX$$QEA_NAEA_NAEAH$$QEAI$$QEAKAEAUtagRECT@@@Z; TrayTelemetry::TrayCalculatedWorkArea<bool,bool &,int &,uint,ulong,tagRECT &>(bool &&,bool &,int &,uint &&,ulong &&,tagRECT &)
0x1400926dd  mov     eax, r12d
0x1400926e0  jmp     short loc_1400926E4
0x1400926e2  xor     eax, eax
0x1400926e4  mov     rcx, [rbp+57h+var_38]
0x1400926e8  xor     rcx, rsp; StackCookie
0x1400926eb  call    __security_check_cookie
0x1400926f0  add     rsp, 0D0h
0x1400926f7  pop     r15
0x1400926f9  pop     r14
0x1400926fb  pop     r12
0x1400926fd  pop     rdi
0x1400926fe  pop     rsi
0x1400926ff  pop     rbx
0x140092700  pop     rbp
0x140092701  retn
```
