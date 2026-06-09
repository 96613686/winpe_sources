# RecorderObj::ShadowBitmapUpdated(HDC__ *,HRGN__ *)

- ea: `0x180075204`
- end: `0x180075865`
- name: `?ShadowBitmapUpdated@RecorderObj@@QEAAJPEAUHDC__@@PEAUHRGN__@@@Z`
- size: `1633`
- prototype: `__int64 __fastcall(RecorderObj *__hidden this, HDC, HRGN)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18001c170`

## callees

- `0x1800186a0`
- `0x1800186d0`
- `0x18001cdc0`
- `0x1800204e8`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x180075204`
- `0x1800e9b1c`
- `0x1801c4c10`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800754f4`
- `KERNEL32!GetLastError` at `0x1800755e7`
- `KERNEL32!GetLastError` at `0x1800754f4`
- `KERNEL32!GetLastError` at `0x1800755e7`
- `GDI32!SelectClipRgn` at `0x18007558d`
- `GDI32!SelectClipRgn` at `0x18007558d`
- `GDI32!BitBlt` at `0x1800754ea`
- `GDI32!BitBlt` at `0x1800755dd`
- `GDI32!BitBlt` at `0x1800754ea`
- `GDI32!BitBlt` at `0x1800755dd`
- `GDI32!GetClipBox` at `0x18007559e`
- `GDI32!GetClipBox` at `0x18007559e`
- `USER32!IntersectRect` at `0x1800752d3`
- `USER32!IntersectRect` at `0x180075635`
- `USER32!IntersectRect` at `0x1800752d3`
- `USER32!IntersectRect` at `0x180075635`
- `USER32!SetRect` at `0x1800752c1`
- `USER32!SetRect` at `0x1800752c1`
- `USER32!IsRectEmpty` at `0x1800752e7`
- `USER32!IsRectEmpty` at `0x18007532a`
- `USER32!IsRectEmpty` at `0x180075402`
- `USER32!IsRectEmpty` at `0x18007563f`
- `USER32!IsRectEmpty` at `0x180075717`
- `USER32!IsRectEmpty` at `0x1800757b2`
- `USER32!IsRectEmpty` at `0x1800752e7`
- `USER32!IsRectEmpty` at `0x18007532a`
- `USER32!IsRectEmpty` at `0x180075402`
- `USER32!IsRectEmpty` at `0x18007563f`
- `USER32!IsRectEmpty` at `0x180075717`
- `USER32!IsRectEmpty` at `0x1800757b2`

## string_xrefs

- `0x18007538e`: `Failed to create recording frame`

## pseudocode

```c
__int64 __fastcall RecorderObj::ShadowBitmapUpdated(RecorderObj *this, HDC a2, HRGN a3)
{
  __int64 v4; // rsi
  int DCW; // edi
  int v6; // r9d
  __int64 v7; // r14
  unsigned int v8; // r13d
  int yBottom; // eax
  unsigned int v10; // r15d
  unsigned int v11; // r12d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v13; // edx
  const char *v14; // rcx
  unsigned int v16; // eax
  int v17; // r9d
  HDC v18; // rcx
  DWORD LastError; // ebx
  unsigned int v20; // eax
  __int64 v21; // rdx
  int v22; // r14d
  int v23; // eax
  int v24; // r14d
  HDC v25; // rcx
  unsigned int v26; // eax
  int v27; // edx
  const char *v28; // rcx
  int v29; // ebx
  unsigned int v30; // eax
  HDC hdcSrc; // [rsp+28h] [rbp-81h]
  HDC hdcSrca; // [rsp+28h] [rbp-81h]
  char *v33; // [rsp+50h] [rbp-59h] BYREF
  int v34; // [rsp+58h] [rbp-51h]
  int v35; // [rsp+5Ch] [rbp-4Dh]
  __int64 v36; // [rsp+60h] [rbp-49h] BYREF
  int v37; // [rsp+68h] [rbp-41h]
  HDC v38; // [rsp+70h] [rbp-39h]
  HRGN hrgn; // [rsp+78h] [rbp-31h]
  struct tagRECT rcDst; // [rsp+80h] [rbp-29h] BYREF
  RECT v41; // [rsp+90h] [rbp-19h] BYREF
  struct tagRECT rect; // [rsp+A0h] [rbp-9h] BYREF
  struct tagRECT rc; // [rsp+B0h] [rbp+7h] BYREF

  hrgn = a3;
  v38 = a2;
  v4 = 0;
  v33 = (char *)this + 64;
  DCW = 0;
  v36 = 0;
  rcDst = 0;
  rc = 0;
  v41 = 0;
  CTSCriticalSection::Lock((RecorderObj *)((char *)this + 64));
  if ( !*((_QWORD *)this + 7) )
    goto LABEL_19;
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v36);
  v36 = *((_QWORD *)this + 7);
  v4 = v36;
  TCntPtr<IPin>::SafeAddRef(&v36);
  if ( !v4 )
    goto LABEL_19;
  v6 = *((_DWORD *)this + 50);
  LODWORD(v36) = *((_DWORD *)this + 20);
  v7 = 0;
  v37 = *((_DWORD *)this + 22);
  v8 = 0;
  yBottom = *((_DWORD *)this + 51);
  v35 = v6;
  v34 = 0;
  SetRect(&rc, 0, 0, v6, yBottom);
  IntersectRect(&rcDst, (const RECT *)((char *)this + 92), &rc);
  if ( *((_DWORD *)this + 22) )
  {
    if ( !*((_DWORD *)this + 21) || IsRectEmpty(&rcDst) )
    {
      v10 = *((_DWORD *)this + 50);
      v11 = *((_DWORD *)this + 51);
    }
    else
    {
      v10 = rcDst.right - rcDst.left;
      v11 = rcDst.bottom - rcDst.top;
    }
    *((_DWORD *)this + 22) = 0;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  if ( *((_QWORD *)this + 7) && !IsRectEmpty(&rcDst) )
  {
    if ( *((_DWORD *)this + 20) )
    {
      DCW = CRdpEncDC::CreateDCW(
              (RecorderObj *)((char *)this + 112),
              *((_DWORD *)this + 50),
              *((_DWORD *)this + 51),
              0x20u);
      if ( DCW < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 13;
        v14 = "Failed to create recording frame";
        goto LABEL_18;
      }
      if ( IsRectEmpty(&rcDst) )
      {
        DCW = 1;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids, v16);
        }
        goto LABEL_19;
      }
      if ( !*((_QWORD *)this + 7) )
      {
        DCW = 1;
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 15;
        v14 = "_spRecorderDataConsumer";
LABEL_18:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (unsigned int)WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v14,
          DCW);
LABEL_19:
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v33);
        goto LABEL_20;
      }
      v17 = *((_DWORD *)this + 50);
      v8 = rcDst.right - rcDst.left;
      v18 = (HDC)*((_QWORD *)this + 22);
      v34 = rcDst.bottom - rcDst.top;
      if ( !BitBlt(v18, 0, 0, v17, *((_DWORD *)this + 51), v38, 0, 0, 0xCC0020u) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        v21 = 16;
        goto LABEL_38;
      }
      v22 = *((_DWORD *)this + 51) - rcDst.bottom;
      v23 = *((_DWORD *)this + 50) & 0x7FFFFFF;
      *((_DWORD *)this + 20) = 0;
      v24 = rcDst.left + v23 * v22;
      goto LABEL_47;
    }
    v25 = (HDC)*((_QWORD *)this + 22);
    rect = 0;
    SelectClipRgn(v25, hrgn);
    GetClipBox(*((HDC *)this + 22), &rect);
    if ( !BitBlt(
            *((HDC *)this + 22),
            rect.left,
            rect.top,
            rect.right - rect.left,
            rect.bottom - rect.top,
            v38,
            rect.left,
            rect.top,
            0xCC0020u) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 17;
LABEL_38:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids,
        v20,
        LastError);
      goto LABEL_19;
    }
    IntersectRect(&v41, &rcDst, &rect);
    if ( !IsRectEmpty(&v41) )
    {
      v24 = v41.left + (*((_DWORD *)this + 50) & 0x7FFFFFF) * (*((_DWORD *)this + 51) - v41.bottom);
LABEL_47:
      v7 = *((_QWORD *)this + 24) + (unsigned int)(4 * v24);
    }
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v33);
  if ( v37
    && (DCW = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v4 + 32LL))(v4, v10, v11, 32),
        DCW < 0) )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      v27 = 18;
      v28 = "Failed ResetRecordingParameters";
LABEL_54:
      LODWORD(hdcSrc) = DCW;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        (unsigned int)WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids,
        v26,
        (__int64)v28,
        hdcSrc);
    }
  }
  else if ( !IsRectEmpty(&rcDst) )
  {
    if ( (_DWORD)v36 )
    {
      if ( v7 )
      {
        DCW = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, int, __int64))(*(_QWORD *)v4 + 40LL))(
                v4,
                0,
                0,
                v8,
                v34,
                v35,
                v7);
        if ( DCW < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          v27 = 19;
          v28 = "Failed to EncodeScreenData";
          goto LABEL_54;
        }
      }
    }
    else if ( !IsRectEmpty(&v41) && v7 )
    {
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, int, __int64))(*(_QWORD *)v4 + 40LL))(
              v4,
              (unsigned int)(v41.left - rcDst.left),
              (unsigned int)(v41.top - rcDst.top),
              (unsigned int)(v41.right - v41.left),
              v41.bottom - v41.top,
              v35,
              v7);
      if ( v29 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(hdcSrca) = v29;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids,
          v30,
          (__int64)"Recorder Consumer Failed to EncodeScreenData",
          hdcSrca);
      }
      DCW = 0;
    }
  }
LABEL_20:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)DCW;
}

```

## disassembly

```asm
0x180075204  mov     [rsp-8+arg_18], rbx
0x180075209  push    rbp
0x18007520a  push    rsi
0x18007520b  push    rdi
0x18007520c  push    r12
0x18007520e  push    r13
0x180075210  push    r14
0x180075212  push    r15
0x180075214  lea     rbp, [rsp-27h]
0x180075219  sub     rsp, 0D0h
0x180075220  mov     rax, cs:__security_cookie
0x180075227  xor     rax, rsp
0x18007522a  mov     [rbp+57h+var_40], rax
0x18007522e  xorps   xmm0, xmm0
0x180075231  mov     [rbp+57h+hrgn], r8
0x180075235  mov     rbx, rcx
0x180075238  mov     [rbp+57h+var_90], rdx
0x18007523c  add     rcx, 40h ; '@'; this
0x180075240  xorps   xmm1, xmm1
0x180075243  xor     esi, esi
0x180075245  mov     [rbp+57h+var_B0], rcx
0x180075249  xor     edi, edi
0x18007524b  mov     [rbp+57h+var_A0], rsi
0x18007524f  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180075253  movups  xmmword ptr [rbp+57h+rc.left], xmm1
0x180075257  movups  xmmword ptr [rbp+57h+var_70.left], xmm0
0x18007525b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180075260  cmp     [rbx+38h], rsi
0x180075264  jz      loc_1800753B8
0x18007526a  lea     rcx, [rbp+57h+var_A0]; void *
0x18007526e  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x180075273  mov     rsi, [rbx+38h]
0x180075277  lea     rcx, [rbp+57h+var_A0]
0x18007527b  mov     [rbp+57h+var_A0], rsi
0x18007527f  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ; TCntPtr<IPin>::SafeAddRef(void)
0x180075284  test    rsi, rsi
0x180075287  jz      loc_1800753B8
0x18007528d  mov     ecx, [rbx+0C8h]
0x180075293  xor     r8d, r8d; yTop
0x180075296  mov     eax, [rbx+50h]
0x180075299  mov     r9d, ecx; xRight
0x18007529c  mov     dword ptr [rbp+57h+var_A0], eax
0x18007529f  xor     edx, edx; xLeft
0x1800752a1  mov     eax, [rbx+58h]
0x1800752a4  xor     r14d, r14d
0x1800752a7  mov     [rbp+57h+var_98], eax
0x1800752aa  xor     r13d, r13d
0x1800752ad  mov     eax, [rbx+0CCh]
0x1800752b3  mov     [rbp+57h+var_A4], ecx
0x1800752b6  lea     rcx, [rbp+57h+rc]; lprc
0x1800752ba  mov     [rsp+100h+yBottom], eax; yBottom
0x1800752be  mov     [rbp+57h+var_A8], edi
0x1800752c1  call    cs:__imp_SetRect
0x1800752c7  lea     rdx, [rbx+5Ch]; lprcSrc1
0x1800752cb  lea     r8, [rbp+57h+rc]; lprcSrc2
0x1800752cf  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800752d3  call    cs:__imp_IntersectRect
0x1800752d9  cmp     [rbx+58h], edi
0x1800752dc  jz      short loc_180075316
0x1800752de  cmp     [rbx+54h], edi
0x1800752e1  jz      short loc_180075303
0x1800752e3  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800752e7  call    cs:__imp_IsRectEmpty
0x1800752ed  test    eax, eax
0x1800752ef  jnz     short loc_180075303
0x1800752f1  mov     r15d, [rbp+57h+rcDst.right]
0x1800752f5  sub     r15d, [rbp+57h+rcDst.left]
0x1800752f9  mov     r12d, [rbp+57h+rcDst.bottom]
0x1800752fd  sub     r12d, [rbp+57h+rcDst.top]
0x180075301  jmp     short loc_180075311
0x180075303  mov     r15d, [rbx+0C8h]
0x18007530a  mov     r12d, [rbx+0CCh]
0x180075311  mov     [rbx+58h], edi
0x180075314  jmp     short loc_18007531C
0x180075316  xor     r15d, r15d
0x180075319  xor     r12d, r12d
0x18007531c  cmp     [rbx+38h], rdi
0x180075320  jz      loc_180075672
0x180075326  lea     rcx, [rbp+57h+rcDst]; lprc
0x18007532a  call    cs:__imp_IsRectEmpty
0x180075330  test    eax, eax
0x180075332  jnz     loc_180075672
0x180075338  lea     rcx, [rbx+70h]; this
0x18007533c  cmp     [rbx+50h], edi
0x18007533f  jz      loc_18007557E
0x180075345  mov     r8d, [rbx+0CCh]; unsigned int
0x18007534c  lea     r9d, [rax+20h]; unsigned int
0x180075350  mov     edx, [rbx+0C8h]; unsigned int
0x180075356  call    ?CreateDCW@CRdpEncDC@@QEAAJKKK@Z; CRdpEncDC::CreateDCW(ulong,ulong,ulong)
0x18007535b  mov     edi, eax
0x18007535d  test    eax, eax
0x18007535f  jns     loc_1800753FE
0x180075365  mov     rax, cs:WPP_GLOBAL_Control
0x18007536c  lea     rcx, WPP_GLOBAL_Control
0x180075373  cmp     rax, rcx
0x180075376  jz      short loc_1800753B8
0x180075378  test    byte ptr [rax+1Ch], 8
0x18007537c  jz      short loc_1800753B8
0x18007537e  cmp     byte ptr [rax+19h], 2
0x180075382  jb      short loc_1800753B8
0x180075384  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075389  mov     edx, 0Dh
0x18007538e  lea     rcx, aFailedToCreate_60; "Failed to create recording frame"
0x180075395  mov     dword ptr [rsp+100h+hdcSrc], edi
0x180075399  lea     r8, WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids
0x1800753a0  mov     qword ptr [rsp+100h+yBottom], rcx
0x1800753a5  mov     r9d, eax
0x1800753a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800753af  mov     rcx, [rcx+10h]
0x1800753b3  call    WPP_SF_DsD
0x1800753b8  lea     rcx, [rbp+57h+var_B0]; this
0x1800753bc  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800753c1  test    rsi, rsi
0x1800753c4  jz      short loc_1800753D5
0x1800753c6  mov     rax, [rsi]
0x1800753c9  mov     rcx, rsi
0x1800753cc  mov     rax, [rax+10h]
0x1800753d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800753d5  mov     eax, edi
0x1800753d7  mov     rcx, [rbp+57h+var_40]
0x1800753db  xor     rcx, rsp; StackCookie
0x1800753de  call    __security_check_cookie
0x1800753e3  mov     rbx, [rsp+100h+arg_18]
0x1800753eb  add     rsp, 0D0h
0x1800753f2  pop     r15
0x1800753f4  pop     r14
0x1800753f6  pop     r13
0x1800753f8  pop     r12
0x1800753fa  pop     rdi
0x1800753fb  pop     rsi
0x1800753fc  pop     rbp
0x1800753fd  retn
0x1800753fe  lea     rcx, [rbp+57h+rcDst]; lprc
0x180075402  call    cs:__imp_IsRectEmpty
0x180075408  xor     ecx, ecx
0x18007540a  test    eax, eax
0x18007540c  jz      short loc_180075459
0x18007540e  mov     rax, cs:WPP_GLOBAL_Control
0x180075415  lea     rcx, WPP_GLOBAL_Control
0x18007541c  mov     edi, 1
0x180075421  cmp     rax, rcx
0x180075424  jz      short loc_1800753B8
0x180075426  test    [rax+1Ch], dil
0x18007542a  jz      short loc_1800753B8
0x18007542c  cmp     byte ptr [rax+19h], 5
0x180075430  jb      short loc_1800753B8
0x180075432  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075437  mov     rcx, cs:WPP_GLOBAL_Control
0x18007543e  lea     edx, [rdi+0Dh]
0x180075441  mov     r9d, eax
0x180075444  lea     r8, WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids
0x18007544b  mov     rcx, [rcx+10h]
0x18007544f  call    WPP_SF_d
0x180075454  jmp     loc_1800753B8
0x180075459  cmp     [rbx+38h], rcx
0x18007545d  jnz     short loc_1800754A3
0x18007545f  mov     rax, cs:WPP_GLOBAL_Control
0x180075466  lea     rcx, WPP_GLOBAL_Control
0x18007546d  mov     edi, 1
0x180075472  cmp     rax, rcx
0x180075475  jz      loc_1800753B8
0x18007547b  test    byte ptr [rax+1Ch], 8
0x18007547f  jz      loc_1800753B8
0x180075485  cmp     byte ptr [rax+19h], 2
0x180075489  jb      loc_1800753B8
0x18007548f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075494  lea     edx, [rdi+0Eh]
0x180075497  lea     rcx, aSprecorderdata; "_spRecorderDataConsumer"
0x18007549e  jmp     loc_180075395
0x1800754a3  mov     eax, [rbp+57h+rcDst.bottom]
0x1800754a6  xor     r8d, r8d; y
0x1800754a9  sub     eax, [rbp+57h+rcDst.top]
0x1800754ac  xor     edx, edx; x
0x1800754ae  mov     r13d, [rbp+57h+rcDst.right]
0x1800754b2  mov     r9d, [rbx+0C8h]; cx
0x1800754b9  sub     r13d, [rbp+57h+rcDst.left]
0x1800754bd  mov     [rsp+100h+rop], 0CC0020h; rop
0x1800754c5  mov     [rsp+100h+y1], ecx; y1
0x1800754c9  mov     [rsp+100h+x1], ecx; x1
0x1800754cd  mov     rcx, [rbp+57h+var_90]
0x1800754d1  mov     [rsp+100h+hdcSrc], rcx; hdcSrc
0x1800754d6  mov     rcx, [rbx+0B0h]; hdc
0x1800754dd  mov     [rbp+57h+var_A8], eax
0x1800754e0  mov     eax, [rbx+0CCh]
0x1800754e6  mov     [rsp+100h+yBottom], eax; cy
0x1800754ea  call    cs:__imp_BitBlt
0x1800754f0  test    eax, eax
0x1800754f2  jnz     short loc_180075554
0x1800754f4  call    cs:__imp_GetLastError
0x1800754fa  mov     ebx, eax
0x1800754fc  mov     rdx, cs:WPP_GLOBAL_Control
0x180075503  lea     rcx, WPP_GLOBAL_Control
0x18007550a  cmp     rdx, rcx
0x18007550d  jz      loc_1800753B8
0x180075513  test    byte ptr [rdx+1Ch], 8
0x180075517  jz      loc_1800753B8
0x18007551d  cmp     byte ptr [rdx+19h], 2
0x180075521  jb      loc_1800753B8
0x180075527  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007552c  mov     edx, 10h
0x180075531  mov     rcx, cs:WPP_GLOBAL_Control
0x180075538  lea     r8, WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids
0x18007553f  mov     r9d, eax
0x180075542  mov     [rsp+100h+yBottom], ebx
0x180075546  mov     rcx, [rcx+10h]
0x18007554a  call    WPP_SF_Dd
0x18007554f  jmp     loc_1800753B8
0x180075554  mov     r14d, [rbx+0CCh]
0x18007555b  sub     r14d, [rbp+57h+rcDst.bottom]
0x18007555f  mov     eax, [rbx+0C8h]
0x180075565  and     eax, 7FFFFFFh
0x18007556a  mov     dword ptr [rbx+50h], 0
0x180075571  imul    r14d, eax
0x180075575  add     r14d, [rbp+57h+rcDst.left]
0x180075579  jmp     loc_180075667
0x18007557e  mov     rdx, [rbp+57h+hrgn]; hrgn
0x180075582  xorps   xmm0, xmm0
0x180075585  mov     rcx, [rcx+40h]; hdc
0x180075589  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x18007558d  call    cs:__imp_SelectClipRgn
0x180075593  mov     rcx, [rbx+0B0h]; hdc
0x18007559a  lea     rdx, [rbp+57h+rect]; lprect
0x18007559e  call    cs:__imp_GetClipBox
0x1800755a4  mov     r8d, [rbp+57h+rect.top]; y
0x1800755a8  mov     edx, [rbp+57h+rect.left]; x
0x1800755ab  mov     eax, [rbp+57h+rect.bottom]
0x1800755ae  mov     rcx, [rbp+57h+var_90]
0x1800755b2  sub     eax, r8d
0x1800755b5  mov     r9d, [rbp+57h+rect.right]
0x1800755b9  mov     [rsp+100h+rop], 0CC0020h; rop
0x1800755c1  sub     r9d, edx; cx
0x1800755c4  mov     [rsp+100h+y1], r8d; y1
0x1800755c9  mov     [rsp+100h+x1], edx; x1
0x1800755cd  mov     [rsp+100h+hdcSrc], rcx; hdcSrc
0x1800755d2  mov     rcx, [rbx+0B0h]; hdc
0x1800755d9  mov     [rsp+100h+yBottom], eax; cy
0x1800755dd  call    cs:__imp_BitBlt
0x1800755e3  test    eax, eax
0x1800755e5  jnz     short loc_180075629
0x1800755e7  call    cs:__imp_GetLastError
0x1800755ed  mov     ebx, eax
0x1800755ef  mov     rdx, cs:WPP_GLOBAL_Control
0x1800755f6  lea     rcx, WPP_GLOBAL_Control
0x1800755fd  cmp     rdx, rcx
0x180075600  jz      loc_1800753B8
0x180075606  test    byte ptr [rdx+1Ch], 8
0x18007560a  jz      loc_1800753B8
0x180075610  cmp     byte ptr [rdx+19h], 2
0x180075614  jb      loc_1800753B8
0x18007561a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007561f  mov     edx, 11h
0x180075624  jmp     loc_180075531
0x180075629  lea     r8, [rbp+57h+rect]; lprcSrc2
0x18007562d  lea     rdx, [rbp+57h+rcDst]; lprcSrc1
0x180075631  lea     rcx, [rbp+57h+var_70]; lprcDst
0x180075635  call    cs:__imp_IntersectRect
0x18007563b  lea     rcx, [rbp+57h+var_70]; lprc
0x18007563f  call    cs:__imp_IsRectEmpty
0x180075645  test    eax, eax
0x180075647  jnz     short loc_180075672
0x180075649  mov     r14d, [rbx+0CCh]
0x180075650  sub     r14d, [rbp+57h+var_70.bottom]
0x180075654  mov     eax, [rbx+0C8h]
0x18007565a  and     eax, 7FFFFFFh
0x18007565f  imul    r14d, eax
0x180075663  add     r14d, [rbp+57h+var_70.left]
0x180075667  shl     r14d, 2
0x18007566b  add     r14, [rbx+0C0h]
0x180075672  lea     rcx, [rbp+57h+var_B0]; this
0x180075676  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18007567b  cmp     [rbp+57h+var_98], 0
0x18007567f  jz      loc_18007570A
0x180075685  mov     rax, [rsi]
0x180075688  mov     r9d, 20h ; ' '
0x18007568e  mov     r8d, r12d
0x180075691  mov     edx, r15d
0x180075694  mov     rcx, rsi
0x180075697  mov     rax, [rax+20h]
0x18007569b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756a0  mov     edi, eax
0x1800756a2  test    eax, eax
0x1800756a4  jns     short loc_18007570A
0x1800756a6  mov     rax, cs:WPP_GLOBAL_Control
0x1800756ad  lea     rcx, WPP_GLOBAL_Control
0x1800756b4  cmp     rax, rcx
0x1800756b7  jz      loc_1800753C1
0x1800756bd  test    byte ptr [rax+1Ch], 8
0x1800756c1  jz      loc_1800753C1
0x1800756c7  cmp     byte ptr [rax+19h], 2
0x1800756cb  jb      loc_1800753C1
0x1800756d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800756d6  mov     edx, 12h
0x1800756db  lea     rcx, aFailedResetrec; "Failed ResetRecordingParameters"
0x1800756e2  mov     dword ptr [rsp+100h+hdcSrc], edi
0x1800756e6  lea     r8, WPP_6ae8688a18883e2f526b99f9f92008c8_Traceguids
0x1800756ed  mov     qword ptr [rsp+100h+yBottom], rcx
0x1800756f2  mov     r9d, eax
0x1800756f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800756fc  mov     rcx, [rcx+10h]
0x180075700  call    WPP_SF_DsD
  ... truncated ...
```
