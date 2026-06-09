# CxCodeVideoProcMFTDataHandler::UpdateInputRectangle(_MFVideoRotationFormat,tagRECT *)

- ea: `0x180007498`
- end: `0x180007c0a`
- name: `?UpdateInputRectangle@CxCodeVideoProcMFTDataHandler@@AEAAJW4_MFVideoRotationFormat@@PEAUtagRECT@@@Z`
- size: `1906`
- prototype: `__int64 __fastcall(__int64, unsigned int, LONG *)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, installer_update`

## callers

- `0x180005f64`
- `0x180007148`

## callees

- `0x180005c58`
- `0x180005d44`
- `0x180007498`
- `0x180009470`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800364d0`
- `0x180054140`
- `0x180054ee4`
- `0x180059e54`
- `0x180059f44`
- `0x180066f48`
- `0x1800d1010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800075a4`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800075a4`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180007724`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180007724`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800078ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180007936`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800078ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180007936`

## string_xrefs

- `0x180007501`: `CxCodeVideoProcMFTDataHandler::UpdateInputRectangle`
- `0x180007694`: `CxCodeVideoProcMFTDataHandler::UpdateInputRectangle`
- `0x18000790c`: `CxCodeVideoProcMFTDataHandler::UpdateInputRectangle`
- `0x180007988`: `CxCodeVideoProcMFTDataHandler::UpdateInputRectangle`
- `0x1800079b6`: `CxCodeVideoProcMFTDataHandler::UpdateInputRectangle`
- `0x180007b91`: `CxCodeVideoProcMFTDataHandler::UpdateInputRectangle`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::UpdateInputRectangle(__int64 a1, unsigned int a2, LONG *a3)
{
  unsigned __int64 v5; // rcx
  LONG right; // edx
  LONG bottom; // r8d
  LONG left; // r9d
  LONG top; // r10d
  int v10; // ecx
  int v11; // ecx
  LONG v12; // r13d
  LONG v13; // edx
  LONG v14; // r12d
  LONG v15; // r8d
  LONG v16; // r11d
  LONG v17; // ecx
  LONG v18; // r10d
  LONG v19; // r9d
  LONG v20; // ebx
  LONG v21; // edi
  LONG v22; // r14d
  LONG v23; // r15d
  LONG *v24; // rax
  _DWORD *v25; // r8
  _DWORD *v26; // rcx
  int ValidArea; // ebx
  CxCodeVideoProcMFTDataHandler *v29; // rcx
  CallStackTracing *v30; // rcx
  __int64 v31; // rdx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v33; // ebx
  __int128 v34; // xmm0
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct CallStackContext *v41; // rax
  CxCodeVideoProcMFTDataHandler *v42; // rcx
  LONG v43; // r8d
  LONG v44; // r9d
  LONG v45; // r10d
  LONG *v46; // rbx
  LONG *v47; // rdi
  __int64 v48; // [rsp+48h] [rbp-99h] BYREF
  LONG *v49; // [rsp+50h] [rbp-91h]
  _BYTE v50[20]; // [rsp+58h] [rbp-89h] BYREF
  unsigned int v51; // [rsp+6Ch] [rbp-75h]
  unsigned int v52; // [rsp+70h] [rbp-71h]
  tagRECT rcDst; // [rsp+A8h] [rbp-39h] BYREF
  RECT rcSrc2; // [rsp+B8h] [rbp-29h] BYREF
  RECT rcSrc1; // [rsp+C8h] [rbp-19h] BYREF
  char v56[16]; // [rsp+D8h] [rbp-9h] BYREF

  v49 = a3;
  *(_QWORD *)&rcDst.left = 0;
  rcSrc1 = 0;
  rcSrc2 = 0;
  memset_0(v50, 0, 0x50u);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v48,
    "CxCodeVideoProcMFTDataHandler::UpdateInputRectangle",
    3788);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *(_QWORD *)(a1 + 3104) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v33 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 3104) + 296LL))(*(_QWORD *)(a1 + 3104));
    v34 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 3104) + 280LL))(
                       *(_QWORD *)(a1 + 3104),
                       v56);
    *((_DWORD *)ThreadRelativeContext + 504) = v33;
    *((_OWORD *)ThreadRelativeContext + 125) = v34;
  }
  v5 = *(_QWORD *)(a1 + 580);
  if ( !v5 )
    v5 = *(_QWORD *)(a1 + 588) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( !v5 )
  {
    right = *(_DWORD *)(a1 + 300);
    bottom = *(_DWORD *)(a1 + 296);
    rcDst.right = right;
    rcDst.bottom = bottom;
LABEL_6:
    left = rcDst.left;
    top = rcDst.top;
    goto LABEL_7;
  }
  if ( (int)CtypeSurfaces::Find(*(_DWORD *)(a1 + 252), (struct TypeSurface *)v50) < 0 )
  {
    v47 = (LONG *)(a1 + 300);
    v46 = (LONG *)(a1 + 296);
  }
  else
  {
    v42 = (CxCodeVideoProcMFTDataHandler *)(unsigned int)*(__int16 *)(a1 + 582);
    v43 = *(__int16 *)(a1 + 586);
    v44 = (_DWORD)v42 + *(_DWORD *)(a1 + 588);
    v45 = v43 + *(_DWORD *)(a1 + 592);
    rcDst.left = *(__int16 *)(a1 + 582);
    rcDst.bottom = v45;
    rcDst.top = v43;
    rcDst.right = v44;
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qdddd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        197,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        a1,
        (_DWORD)v42,
        v44,
        v43,
        v45);
    v46 = (LONG *)(a1 + 296);
    v47 = (LONG *)(a1 + 300);
    if ( !(unsigned int)CxCodeVideoProcMFTDataHandler::GetValidArea(
                          v42,
                          *(_DWORD *)(a1 + 300),
                          *(_DWORD *)(a1 + 296),
                          v51,
                          v52,
                          &rcDst,
                          0,
                          1) )
    {
      bottom = rcDst.bottom;
      right = rcDst.right;
      goto LABEL_6;
    }
  }
  right = *v47;
  top = 0;
  bottom = *v46;
  left = 0;
  rcDst.right = *v47;
  rcDst.bottom = bottom;
  *(_QWORD *)&rcDst.left = 0;
LABEL_7:
  v10 = *(_DWORD *)(a1 + 604);
  rcSrc2 = rcDst;
  v11 = v10 - 2;
  if ( v11 )
  {
    if ( v11 == 1 && *(_DWORD *)(a1 + 992) <= 1u )
      rcSrc2.bottom = top + (bottom - top) / 2;
  }
  else if ( *(_DWORD *)(a1 + 992) <= 1u )
  {
    rcSrc2.right = left + (right - left) / 2;
  }
  if ( IsRectEmpty((const RECT *)(a1 + 280)) )
  {
    v12 = rcSrc2.left;
    v13 = rcSrc2.left;
    v14 = rcSrc2.top;
    v15 = rcSrc2.top;
    v16 = rcSrc2.right;
    v17 = rcSrc2.right;
    v18 = rcSrc2.bottom;
    v19 = rcSrc2.bottom;
    goto LABEL_11;
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qdddd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      198,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      a1,
      *(_DWORD *)(a1 + 280),
      *(_DWORD *)(a1 + 288),
      *(_DWORD *)(a1 + 284),
      *(_DWORD *)(a1 + 292));
  DestinationSpaceToSourceSpace(
    a2,
    a1 + 280,
    (unsigned int)(rcSrc2.right - rcSrc2.left),
    (unsigned int)(rcSrc2.bottom - rcSrc2.top),
    &rcSrc1,
    a1 + 248);
  rcDst = 0;
  if ( IntersectRect(&rcDst, &rcSrc1, &rcSrc2) )
    goto LABEL_21;
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 199, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, a1);
  ValidArea = XvpOriginateError<41>(
                "CxCodeVideoProcMFTDataHandler::UpdateInputRectangle",
                3222091451LL,
                L"App source rect is not in the video area");
  if ( ValidArea >= 0 )
  {
LABEL_21:
    ValidArea = CtypeSurfaces::Find(*(_DWORD *)(a1 + 252), (struct TypeSurface *)v50);
    if ( ValidArea < 0 )
    {
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != ValidArea )
          CallStackContext::TraceFailure(v40, "CxCodeVideoProcMFTDataHandler::UpdateInputRectangle", 3850, ValidArea);
      }
      if ( g_wppLevels )
      {
        v31 = 201;
        goto LABEL_34;
      }
    }
    else
    {
      ValidArea = CxCodeVideoProcMFTDataHandler::GetValidArea(
                    v29,
                    *(_DWORD *)(a1 + 300),
                    *(_DWORD *)(a1 + 296),
                    v51,
                    v52,
                    &rcDst,
                    0,
                    0);
      if ( ValidArea >= 0 )
      {
        v13 = rcDst.left;
        v15 = rcDst.top;
        v17 = rcDst.right;
        v19 = rcDst.bottom;
        v18 = rcSrc2.bottom;
        v16 = rcSrc2.right;
        v14 = rcSrc2.top;
        v12 = rcSrc2.left;
LABEL_11:
        if ( a2 == 90 || a2 == 270 )
        {
          v20 = v15;
          v21 = v13;
          v22 = v19;
          v23 = v17;
        }
        else
        {
          v20 = v13;
          v21 = v15;
          v22 = v17;
          v23 = v19;
        }
        *(_DWORD *)(a1 + 344) -= *(_DWORD *)(a1 + 336);
        *(_DWORD *)(a1 + 348) -= *(_DWORD *)(a1 + 340);
        v24 = v49;
        *(_QWORD *)(a1 + 336) = 0;
        if ( v24 )
        {
          *v24 = v20;
          v25 = (_DWORD *)(a1 + 316);
          v24[1] = v21;
          v26 = (_DWORD *)(a1 + 312);
          v24[2] = v22;
          v24[3] = v23;
        }
        else
        {
          *(_DWORD *)(a1 + 328) = v17;
          *(_DWORD *)(a1 + 324) = v15;
          *(_DWORD *)(a1 + 320) = v13;
          v25 = (_DWORD *)(a1 + 316);
          *(_DWORD *)(a1 + 332) = v19;
          *(_DWORD *)(a1 + 316) = v17 - v13;
          *(_DWORD *)(a1 + 336) = v20;
          v26 = (_DWORD *)(a1 + 312);
          *(_DWORD *)(a1 + 340) = v21;
          *(_DWORD *)(a1 + 344) = v22;
          *(_DWORD *)(a1 + 348) = v23;
          *(_DWORD *)(a1 + 308) = v16 - v12;
          *(_DWORD *)(a1 + 304) = v18 - v14;
          *(_DWORD *)(a1 + 312) = v19 - *(_DWORD *)(a1 + 324);
        }
        if ( *v25 > 0x5900u || *v26 > 0x5900u )
          ValidArea = XvpOriginateError<36>(
                        "CxCodeVideoProcMFTDataHandler::UpdateInputRectangle",
                        2147942487LL,
                        L"Invalid source rectangle calculated");
        else
          ValidArea = 0;
        goto LABEL_17;
      }
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v30 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext(v30);
        if ( *((_DWORD *)v41 + 499) != ValidArea )
          CallStackContext::TraceFailure(v41, "CxCodeVideoProcMFTDataHandler::UpdateInputRectangle", 3851, ValidArea);
      }
      if ( g_wppLevels )
      {
        v31 = 202;
LABEL_34:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v31,
          &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
          a1,
          ValidArea);
      }
    }
  }
  else
  {
    v35 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v36;
      if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v35 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v35 + 8) )
    {
      v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
      if ( *((_DWORD *)v37 + 499) != ValidArea )
        CallStackContext::TraceFailure(v37, "CxCodeVideoProcMFTDataHandler::UpdateInputRectangle", 3845, ValidArea);
    }
    if ( g_wppLevels )
    {
      v31 = 200;
      goto LABEL_34;
    }
  }
LABEL_17:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v48);
  return (unsigned int)ValidArea;
}

```

## disassembly

```asm
0x180007498  mov     rax, rsp
0x18000749b  mov     [rax+10h], rbx
0x18000749f  push    rbp
0x1800074a0  push    rsi
0x1800074a1  push    rdi
0x1800074a2  push    r12
0x1800074a4  push    r13
0x1800074a6  push    r14
0x1800074a8  push    r15
0x1800074aa  lea     rbp, [rax-5Fh]
0x1800074ae  sub     rsp, 100h
0x1800074b5  movaps  xmmword ptr [rax-48h], xmm6
0x1800074b9  mov     rax, cs:__security_cookie
0x1800074c0  xor     rax, rsp
0x1800074c3  mov     [rbp+57h+var_50], rax
0x1800074c7  xor     r12d, r12d
0x1800074ca  mov     [rsp+130h+var_E8], r8
0x1800074cf  mov     r15d, edx
0x1800074d2  mov     qword ptr [rbp+57h+rcDst.left], r12
0x1800074d6  mov     rsi, rcx
0x1800074d9  xorps   xmm0, xmm0
0x1800074dc  xorps   xmm1, xmm1
0x1800074df  lea     rcx, [rsp+130h+var_E0]; void *
0x1800074e4  lea     r8d, [r12+50h]; Size
0x1800074e9  xor     edx, edx; Val
0x1800074eb  xorps   xmm6, xmm6
0x1800074ee  movups  xmmword ptr [rbp+57h+rcSrc1.left], xmm0
0x1800074f2  movups  xmmword ptr [rbp+57h+rcSrc2.left], xmm1
0x1800074f6  call    memset_0
0x1800074fb  mov     r8d, 0ECCh; int
0x180007501  lea     rdx, aCxcodevideopro_95; "CxCodeVideoProcMFTDataHandler::UpdateIn"...
0x180007508  lea     rcx, [rsp+130h+var_F0]; this
0x18000750d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180007512  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180007519  cmp     [rcx+8], r12b
0x18000751d  jnz     loc_18000783C
0x180007523  mov     rcx, [rsi+244h]
0x18000752a  movq    rax, xmm6
0x18000752f  sub     rcx, rax
0x180007532  jnz     short loc_180007548
0x180007534  mov     rcx, [rsi+24Ch]
0x18000753b  psrldq  xmm6, 8
0x180007540  movq    rax, xmm6
0x180007545  sub     rcx, rax
0x180007548  lea     r14, [rsi+0F8h]
0x18000754f  lea     r13, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180007556  test    rcx, rcx
0x180007559  jnz     loc_1800079D0
0x18000755f  mov     edx, [r14+34h]
0x180007563  mov     r8d, [rsi+128h]
0x18000756a  mov     [rbp+57h+rcDst.right], edx
0x18000756d  mov     [rbp+57h+rcDst.bottom], r8d
0x180007571  mov     r9d, [rbp+57h+rcDst.left]
0x180007575  mov     r10d, [rbp+57h+rcDst.top]
0x180007579  mov     ecx, [rsi+25Ch]
0x18000757f  mov     r11d, 2
0x180007585  movaps  xmm0, xmmword ptr [rbp+57h+rcDst.left]
0x180007589  movdqa  xmmword ptr [rbp+57h+rcSrc2.left], xmm0
0x18000758e  sub     ecx, r11d
0x180007591  jz      loc_180007AEC
0x180007597  cmp     ecx, 1
0x18000759a  jz      loc_180007AC4
0x1800075a0  lea     rcx, [r14+20h]; lprc
0x1800075a4  call    cs:__imp_IsRectEmpty
0x1800075aa  test    eax, eax
0x1800075ac  jz      loc_1800076DA
0x1800075b2  mov     r13d, [rbp+57h+rcSrc2.left]
0x1800075b6  mov     edx, r13d
0x1800075b9  mov     r12d, [rbp+57h+rcSrc2.top]
0x1800075bd  mov     r8d, r12d
0x1800075c0  mov     r11d, [rbp+57h+rcSrc2.right]
0x1800075c4  mov     ecx, r11d
0x1800075c7  mov     r10d, [rbp+57h+rcSrc2.bottom]
0x1800075cb  mov     r9d, r10d
0x1800075ce  cmp     r15d, 5Ah ; 'Z'
0x1800075d2  jnz     loc_1800077A5
0x1800075d8  mov     ebx, r8d
0x1800075db  mov     edi, edx
0x1800075dd  mov     r14d, r9d
0x1800075e0  mov     r15d, ecx
0x1800075e3  mov     eax, [rsi+150h]
0x1800075e9  sub     [rsi+158h], eax
0x1800075ef  mov     eax, [rsi+154h]
0x1800075f5  sub     [rsi+15Ch], eax
0x1800075fb  mov     rax, [rsp+130h+var_E8]
0x180007600  mov     qword ptr [rsi+150h], 0
0x18000760b  test    rax, rax
0x18000760e  jnz     loc_1800077C2
0x180007614  mov     [rsi+148h], ecx
0x18000761a  sub     r11d, r13d
0x18000761d  sub     ecx, edx
0x18000761f  mov     [rsi+144h], r8d
0x180007626  sub     r10d, r12d
0x180007629  mov     [rsi+140h], edx
0x18000762f  lea     r8, [rsi+13Ch]
0x180007636  mov     [rsi+14Ch], r9d
0x18000763d  mov     [r8], ecx
0x180007640  mov     eax, r9d
0x180007643  mov     [rsi+150h], ebx
0x180007649  lea     rcx, [rsi+138h]
0x180007650  mov     [rsi+154h], edi
0x180007656  mov     [rsi+158h], r14d
0x18000765d  mov     [rsi+15Ch], r15d
0x180007664  mov     [rsi+134h], r11d
0x18000766b  mov     [rsi+130h], r10d
0x180007672  sub     eax, [rsi+144h]
0x180007678  mov     [rcx], eax
0x18000767a  mov     eax, 5900h
0x18000767f  cmp     [r8], eax
0x180007682  jbe     loc_1800077E2
0x180007688  lea     r8, aInvalidSourceR; "Invalid source rectangle calculated"
0x18000768f  mov     edx, 80070057h
0x180007694  lea     rcx, aCxcodevideopro_95; "CxCodeVideoProcMFTDataHandler::UpdateIn"...
0x18000769b  call    ??$XvpOriginateError@$0CE@@@YAJQEADJAEAY0CE@$$CBG@Z; XvpOriginateError<36>(char * const,long,ushort const (&)[36])
0x1800076a0  mov     ebx, eax
0x1800076a2  lea     rcx, [rsp+130h+var_F0]; this
0x1800076a7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800076ac  mov     eax, ebx
0x1800076ae  mov     rcx, [rbp+57h+var_50]
0x1800076b2  xor     rcx, rsp; StackCookie
0x1800076b5  call    __security_check_cookie
0x1800076ba  lea     r11, [rsp+130h+var_30]
0x1800076c2  mov     rbx, [r11+48h]
0x1800076c6  movaps  xmm6, xmmword ptr [r11-10h]
0x1800076cb  mov     rsp, r11
0x1800076ce  pop     r15
0x1800076d0  pop     r14
0x1800076d2  pop     r13
0x1800076d4  pop     r12
0x1800076d6  pop     rdi
0x1800076d7  pop     rsi
0x1800076d8  pop     rbp
0x1800076d9  retn
0x1800076da  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800076e1  jnb     loc_180007B13
0x1800076e7  mov     r9d, [rbp+57h+rcSrc2.bottom]
0x1800076eb  lea     rax, [rbp+57h+rcSrc1]
0x1800076ef  mov     r8d, [rbp+57h+rcSrc2.right]
0x1800076f3  lea     rdx, [r14+20h]
0x1800076f7  sub     r9d, [rbp+57h+rcSrc2.top]
0x1800076fb  mov     ecx, r15d
0x1800076fe  sub     r8d, [rbp+57h+rcSrc2.left]
0x180007702  mov     [rsp+130h+var_108], r14
0x180007707  mov     qword ptr [rsp+130h+var_110], rax
0x18000770c  call    ?DestinationSpaceToSourceSpace@@YAXW4_MFVideoRotationFormat@@AEBUtagRECT@@IIPEAU2@PEAUxvpDataHandlerState@@@Z; DestinationSpaceToSourceSpace(_MFVideoRotationFormat,tagRECT const &,uint,uint,tagRECT *,xvpDataHandlerState *)
0x180007711  xorps   xmm0, xmm0
0x180007714  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x180007718  lea     rdx, [rbp+57h+rcSrc1]; lprcSrc1
0x18000771c  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180007720  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180007724  call    cs:__imp_IntersectRect
0x18000772a  test    eax, eax
0x18000772c  jz      loc_180007B5E
0x180007732  mov     ecx, [rsi+0FCh]; unsigned int
0x180007738  lea     rdx, [rsp+130h+var_E0]; struct TypeSurface *
0x18000773d  call    ?Find@CtypeSurfaces@@SAJKPEAUTypeSurface@@@Z; CtypeSurfaces::Find(ulong,TypeSurface *)
0x180007742  mov     ebx, eax
0x180007744  test    eax, eax
0x180007746  js      loc_180007926
0x18000774c  mov     r9d, [rbp+57h+var_CC]; unsigned int
0x180007750  lea     rax, [rbp+57h+rcDst]
0x180007754  mov     r8d, [rsi+128h]; unsigned int
0x18000775b  mov     edx, [rsi+12Ch]; unsigned int
0x180007761  mov     [rsp+130h+var_F8], r12d; int
0x180007766  mov     [rsp+130h+var_100], r12d; int
0x18000776b  mov     [rsp+130h+var_108], rax; struct tagRECT *
0x180007770  mov     eax, [rbp+57h+var_C8]
0x180007773  mov     [rsp+130h+var_110], eax; unsigned int
0x180007777  call    ?GetValidArea@CxCodeVideoProcMFTDataHandler@@AEAAJKKKKPEAUtagRECT@@HH@Z; CxCodeVideoProcMFTDataHandler::GetValidArea(ulong,ulong,ulong,ulong,tagRECT *,int,int)
0x18000777c  mov     ebx, eax
0x18000777e  test    eax, eax
0x180007780  js      short loc_1800077F1
0x180007782  mov     edx, [rbp+57h+rcDst.left]
0x180007785  mov     r8d, [rbp+57h+rcDst.top]
0x180007789  mov     ecx, [rbp+57h+rcDst.right]
0x18000778c  mov     r9d, [rbp+57h+rcDst.bottom]
0x180007790  mov     r10d, [rbp+57h+rcSrc2.bottom]
0x180007794  mov     r11d, [rbp+57h+rcSrc2.right]
0x180007798  mov     r12d, [rbp+57h+rcSrc2.top]
0x18000779c  mov     r13d, [rbp+57h+rcSrc2.left]
0x1800077a0  jmp     loc_1800075CE
0x1800077a5  cmp     r15d, 10Eh
0x1800077ac  jz      loc_1800075D8
0x1800077b2  mov     ebx, edx
0x1800077b4  mov     edi, r8d
0x1800077b7  mov     r14d, ecx
0x1800077ba  mov     r15d, r9d
0x1800077bd  jmp     loc_1800075E3
0x1800077c2  mov     [rax], ebx
0x1800077c4  lea     r8, [rsi+13Ch]
0x1800077cb  mov     [rax+4], edi
0x1800077ce  lea     rcx, [rsi+138h]
0x1800077d5  mov     [rax+8], r14d
0x1800077d9  mov     [rax+0Ch], r15d
0x1800077dd  jmp     loc_18000767A
0x1800077e2  cmp     [rcx], eax
0x1800077e4  ja      loc_180007688
0x1800077ea  xor     ebx, ebx
0x1800077ec  jmp     loc_1800076A2
0x1800077f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800077f8  test    rcx, rcx
0x1800077fb  jz      loc_180007899
0x180007801  cmp     [rcx+8], r12b
0x180007805  jnz     loc_1800079A2
0x18000780b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007812  jb      loc_1800076A2
0x180007818  mov     edx, 0CAh
0x18000781d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007824  mov     r9, rsi
0x180007827  mov     r8, r13
0x18000782a  mov     [rsp+130h+var_110], ebx
0x18000782e  mov     rcx, [rcx+10h]
0x180007832  call    WPP_SF_qD
0x180007837  jmp     loc_1800076A2
0x18000783c  cmp     [rsi+0C20h], r12
0x180007843  jz      loc_180007523
0x180007849  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000784e  mov     rcx, [rsi+0C20h]
0x180007855  mov     rdi, rax
0x180007858  mov     rdx, [rcx]
0x18000785b  mov     rax, [rdx+128h]
0x180007862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007867  mov     rcx, [rsi+0C20h]
0x18000786e  mov     ebx, eax
0x180007870  mov     rdx, [rcx]
0x180007873  mov     rax, [rdx+118h]
0x18000787a  lea     rdx, [rbp+57h+var_60]
0x18000787e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007883  movups  xmm0, xmmword ptr [rax]
0x180007886  mov     [rdi+7E0h], ebx
0x18000788c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180007894  jmp     loc_180007523
0x180007899  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000789e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800078a5  jmp     loc_180007801
0x1800078aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800078b1  test    rcx, rcx
0x1800078b4  jnz     loc_180007BBA
0x1800078ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800078c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800078c7  mov     rcx, rax
0x1800078ca  test    rax, rax
0x1800078cd  jz      loc_180007BAC
0x1800078d3  mov     rax, [rax]
0x1800078d6  mov     edx, 7F0h
0x1800078db  mov     rax, [rax+8]
0x1800078df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e4  test    eax, eax
0x1800078e6  jz      loc_180007BAC
0x1800078ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800078f3  jmp     loc_180007BBA
0x1800078f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800078fd  cmp     [rax+7CCh], ebx
0x180007903  jz      loc_180007BC4
0x180007909  mov     r9d, ebx; int
0x18000790c  lea     rdx, aCxcodevideopro_95; "CxCodeVideoProcMFTDataHandler::UpdateIn"...
0x180007913  mov     r8d, 0F05h; int
0x180007919  mov     rcx, rax; this
0x18000791c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180007921  jmp     loc_180007BC4
0x180007926  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000792d  test    rcx, rcx
0x180007930  jnz     loc_180007BE9
0x180007936  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000793c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180007943  mov     rcx, rax
0x180007946  test    rax, rax
0x180007949  jz      loc_180007BDB
0x18000794f  mov     rax, [rax]
0x180007952  mov     edx, 7F0h
0x180007957  mov     rax, [rax+8]
0x18000795b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007960  test    eax, eax
0x180007962  jz      loc_180007BDB
0x180007968  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000796f  jmp     loc_180007BE9
0x180007974  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180007979  cmp     [rax+7CCh], ebx
0x18000797f  jz      loc_180007BF3
0x180007985  mov     r9d, ebx; int
0x180007988  lea     rdx, aCxcodevideopro_95; "CxCodeVideoProcMFTDataHandler::UpdateIn"...
0x18000798f  mov     r8d, 0F0Ah; int
0x180007995  mov     rcx, rax; this
0x180007998  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000799d  jmp     loc_180007BF3
0x1800079a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800079a7  cmp     [rax+7CCh], ebx
0x1800079ad  jz      loc_18000780B
0x1800079b3  mov     r9d, ebx; int
0x1800079b6  lea     rdx, aCxcodevideopro_95; "CxCodeVideoProcMFTDataHandler::UpdateIn"...
0x1800079bd  mov     r8d, 0F0Bh; int
0x1800079c3  mov     rcx, rax; this
0x1800079c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800079cb  jmp     loc_18000780B
0x1800079d0  mov     ecx, [r14+4]; unsigned int
0x1800079d4  lea     rdx, [rsp+130h+var_E0]; struct TypeSurface *
0x1800079d9  call    ?Find@CtypeSurfaces@@SAJKPEAUTypeSurface@@@Z; CtypeSurfaces::Find(ulong,TypeSurface *)
0x1800079de  test    eax, eax
0x1800079e0  js      loc_180007A9B
0x1800079e6  movsx   ecx, word ptr [rsi+246h]
  ... truncated ...
```
