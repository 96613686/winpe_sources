# CapturePresentMultiPlaneOverlayArgs3(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const *,_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *,_D3DKMT_MULTIPLANE_OVERLAY3 * * *,_D3DKMT_MULTIPLANE_OVERLAY3 * *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 * *,tagRECT * * *,uint * *,uint * *,uchar * *,_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION * *)

- ea: `0x140408e50`
- end: `0x1404098af`
- name: `?CapturePresentMultiPlaneOverlayArgs3@@YAJPEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@PEAU1@PEAPEAPEAU_D3DKMT_MULTIPLANE_OVERLAY3@@PEAPEAU2@PEAPEAU_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3@@PEAPEAPEAUtagRECT@@PEAPEAI6PEAPEAEPEAPEAU_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION@@@Z`
- size: `2655`
- prototype: `__int64 __usercall@<rax>(const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *Src@<rcx>, struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *@<rdx>, struct _D3DKMT_MULTIPLANE_OVERLAY3 ***@<r8>, struct _D3DKMT_MULTIPLANE_OVERLAY3 **@<r9>, struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 **, struct tagRECT ***, unsigned int **, unsigned int **, unsigned __int8 **, struct _D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14040bd40`

## callees

- `0x1400091f0`
- `0x14001b9c0`
- `0x14002e2e0`
- `0x1400674c4`
- `0x1400a1000`
- `0x140247f40`
- `0x140394ef4`
- `0x140408e50`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140408f6a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140408fd9`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040903a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040909f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040910b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040917a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404091e0`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409242`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409411`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040948b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404094bf`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404096a2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404096d3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409733`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409767`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409798`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404097d6`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409819`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040984a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140408f6a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140408fd9`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040903a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040909f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040910b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040917a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404091e0`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409242`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409411`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040948b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404094bf`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404096a2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404096d3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409733`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409767`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409798`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404097d6`
- `ntoskrnl!PsGetCurrentProcess` at `0x140409819`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040984a`
- `watchdog!WdLogSingleEntry2` at `0x140408f87`
- `watchdog!WdLogSingleEntry2` at `0x140408ff5`
- `watchdog!WdLogSingleEntry2` at `0x140409057`
- `watchdog!WdLogSingleEntry2` at `0x1404090bd`
- `watchdog!WdLogSingleEntry2` at `0x140409127`
- `watchdog!WdLogSingleEntry2` at `0x140409197`
- `watchdog!WdLogSingleEntry2` at `0x1404091fe`
- `watchdog!WdLogSingleEntry2` at `0x140409260`
- `watchdog!WdLogSingleEntry2` at `0x14040942e`
- `watchdog!WdLogSingleEntry2` at `0x1404094a9`
- `watchdog!WdLogSingleEntry2` at `0x1404096bd`
- `watchdog!WdLogSingleEntry2` at `0x140409751`
- `watchdog!WdLogSingleEntry2` at `0x140409834`
- `watchdog!WdLogSingleEntry2` at `0x140408f87`
- `watchdog!WdLogSingleEntry2` at `0x140408ff5`
- `watchdog!WdLogSingleEntry2` at `0x140409057`
- `watchdog!WdLogSingleEntry2` at `0x1404090bd`
- `watchdog!WdLogSingleEntry2` at `0x140409127`
- `watchdog!WdLogSingleEntry2` at `0x140409197`
- `watchdog!WdLogSingleEntry2` at `0x1404091fe`
- `watchdog!WdLogSingleEntry2` at `0x140409260`
- `watchdog!WdLogSingleEntry2` at `0x14040942e`
- `watchdog!WdLogSingleEntry2` at `0x1404094a9`
- `watchdog!WdLogSingleEntry2` at `0x1404096bd`
- `watchdog!WdLogSingleEntry2` at `0x140409751`
- `watchdog!WdLogSingleEntry2` at `0x140409834`
- `watchdog!WdLogSingleEntry3` at `0x140409370`
- `watchdog!WdLogSingleEntry3` at `0x1404097b9`
- `watchdog!WdLogSingleEntry3` at `0x140409370`
- `watchdog!WdLogSingleEntry3` at `0x1404097b9`

## string_xrefs

- `0x14040987f`: `Fail to capture parameters, returing 0x%I64x at %I64x`
- `0x140409708`: `Fail to capture parameters, returing 0x%I64x at 0x%I64x`
- `0x1404097fb`: `Presenting multi plane overlay plane count (0x%I64x) is invalid, returing 0x%I64x at 0x%I64x`
- `0x14040978c`: `Invalid ContextCount, returing 0x%I64x at 0x%I64x`
- `0x1404094e4`: `Invalid AllocationCount, returing 0x%I64x at 0x%I64x`
- `0x1404093aa`: `Invalid DirtyRectCount:%u on plane %u, returing 0x%I64x`

## pseudocode

```c
__int64 __fastcall CapturePresentMultiPlaneOverlayArgs3(
        struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *Src,
        struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *a2,
        struct _D3DKMT_MULTIPLANE_OVERLAY3 ***a3,
        struct _D3DKMT_MULTIPLANE_OVERLAY3 **a4,
        struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 **a5,
        struct tagRECT ***a6,
        unsigned int **a7,
        unsigned int **a8,
        unsigned __int8 **a9,
        struct _D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION **a10)
{
  __int64 v11; // rax
  __int64 v12; // rcx
  void *v13; // r12
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  struct _D3DKMT_MULTIPLANE_OVERLAY3 *v19; // rsi
  __int64 v20; // rax
  __int64 v21; // rcx
  struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v22; // r13
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  void *v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rcx
  char *v30; // r14
  __int64 v31; // rcx
  __int64 v32; // rcx
  UINT *v33; // rdx
  unsigned int i; // ebx
  void **v35; // r15
  struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v36; // rsi
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rax
  unsigned __int64 DirtyRectCount; // kr00_8
  __int64 v42; // rax
  void **v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // r8
  void *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // r8
  unsigned int *v52; // rdi
  __int64 j; // r8
  __int64 v54; // rcx
  __int64 v55; // rbx
  __int64 CurrentProcess; // rax
  __int64 v57; // rbx
  __int64 v58; // rcx
  __int64 v59; // [rsp+28h] [rbp-110h]
  __int64 v60; // [rsp+30h] [rbp-108h]
  __int128 v61; // [rsp+50h] [rbp-E8h] BYREF
  __int128 v62; // [rsp+60h] [rbp-D8h]
  void *v63[2]; // [rsp+70h] [rbp-C8h]
  void *v64[2]; // [rsp+80h] [rbp-B8h]
  int v65; // [rsp+90h] [rbp-A8h]
  unsigned int v66; // [rsp+A0h] [rbp-98h]
  void *v67[17]; // [rsp+B0h] [rbp-88h] BYREF

  memset(v67, 0, 0x50u);
  if ( (unsigned int)IsMSRC110351_61431726_Enabled() )
  {
    *(_OWORD *)v67 = *(_OWORD *)&Src->hAdapter;
    *(_OWORD *)&v67[2] = *(_OWORD *)&Src->VidPnSourceId;
    *(_OWORD *)&v67[4] = *(_OWORD *)&Src->ppPresentPlanes;
    *(_OWORD *)&v67[6] = *(_OWORD *)&Src->Duration;
    *(_OWORD *)&v67[8] = *(_OWORD *)&Src->pHDRMetaData;
  }
  else
  {
    RtlCopyFromUser(v67, Src, 0x50u);
  }
  if ( (unsigned int)(HIDWORD(v67[3]) - 1) > 9 )
  {
    v55 = HIDWORD(v67[3]);
    CurrentProcess = PsGetCurrentProcess(HIDWORD(v67[3]));
    WdLogSingleEntry3(2, v55, -1073741811, CurrentProcess);
    WdLogGlobalForLineNumber = 2512;
    v57 = HIDWORD(v67[3]);
    v60 = PsGetCurrentProcess(v58);
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Presenting multi plane overlay plane count (0x%I64x) is invalid, returing 0x%I64x at 0x%I64x",
      v57,
      -1073741811,
      v60,
      0,
      0);
    return 3221225485LL;
  }
  if ( (unsigned int)(HIDWORD(v67[0]) - 1) > 0x3F )
  {
    PsGetCurrentProcess(HIDWORD(v67[3]));
    WdLogSingleEntry2(2, -1073741811);
    WdLogGlobalForLineNumber = 2521;
    v59 = PsGetCurrentProcess(v54);
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid ContextCount, returing 0x%I64x at 0x%I64x",
      -1073741811,
      v59,
      0,
      0,
      0);
    return 3221225485LL;
  }
  *((_QWORD *)&v61 + 1) = 0;
  v62 = 0;
  *(_OWORD *)v63 = 0;
  *(_OWORD *)v64 = 0;
  v65 = HIDWORD(v67[3]);
  v11 = 8LL * HIDWORD(v67[3]);
  if ( !is_mul_ok(HIDWORD(v67[3]), 8u) )
    v11 = -1;
  v13 = (void *)operator new[](v11, 1265072196, 256);
  *(_QWORD *)&v61 = v13;
  if ( !v13 )
  {
    PsGetCurrentProcess(v12);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2578;
LABEL_10:
    CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v61, v14, v15);
    return 3221225495LL;
  }
  v17 = 80LL * HIDWORD(v67[3]);
  if ( !is_mul_ok(HIDWORD(v67[3]), 0x50u) )
    v17 = -1;
  v19 = (struct _D3DKMT_MULTIPLANE_OVERLAY3 *)operator new[](v17, 1265072196, 256);
  *((_QWORD *)&v61 + 1) = v19;
  if ( !v19 )
  {
    PsGetCurrentProcess(v18);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2588;
    goto LABEL_10;
  }
  v20 = 88LL * HIDWORD(v67[3]);
  if ( !is_mul_ok(HIDWORD(v67[3]), 0x58u) )
    v20 = -1;
  v22 = (struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *)operator new[](v20, 1265072196, 256);
  *(_QWORD *)&v62 = v22;
  if ( !v22 )
  {
    PsGetCurrentProcess(v21);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2598;
    goto LABEL_10;
  }
  v23 = 8LL * HIDWORD(v67[3]);
  if ( !is_mul_ok(HIDWORD(v67[3]), 8u) )
    v23 = -1;
  v64[0] = (void *)operator new[](v23, 1265072196, 256);
  if ( !v64[0] )
  {
    PsGetCurrentProcess(v24);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2608;
    goto LABEL_10;
  }
  v25 = 4LL * HIDWORD(v67[0]);
  if ( !is_mul_ok(HIDWORD(v67[0]), 4u) )
    v25 = -1;
  v27 = (void *)operator new[](v25, 1265072196, 256);
  *((_QWORD *)&v62 + 1) = v27;
  if ( !v27 )
  {
    PsGetCurrentProcess(v26);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2618;
    goto LABEL_10;
  }
  v28 = 4LL * (unsigned int)(HIDWORD(v67[3]) * HIDWORD(v67[0]));
  if ( !is_mul_ok((unsigned int)(HIDWORD(v67[3]) * HIDWORD(v67[0])), 4u) )
    v28 = -1;
  v30 = (char *)operator new[](v28, 1265072196, 256);
  v63[0] = v30;
  if ( !v30 )
  {
    PsGetCurrentProcess(v29);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2628;
    goto LABEL_10;
  }
  if ( v67[8] )
  {
    if ( LODWORD(v67[7]) )
    {
      v63[1] = (void *)operator new[](LODWORD(v67[7]), 1265072196, 256);
      if ( !v63[1] )
      {
        PsGetCurrentProcess(v31);
        WdLogSingleEntry2(3, -1073741801);
        WdLogGlobalForLineNumber = 2640;
        goto LABEL_10;
      }
    }
  }
  if ( v67[5] )
  {
    v64[1] = (void *)operator new(40, 1265072196, 256);
    if ( !v64[1] )
    {
      PsGetCurrentProcess(v32);
      WdLogSingleEntry2(3, -1073741801);
      WdLogGlobalForLineNumber = 2653;
      goto LABEL_10;
    }
  }
  RtlCopyFromUser(v13, v67[4], 8LL * HIDWORD(v67[3]));
  RtlCopyFromUser(v27, v67[1], 4LL * HIDWORD(v67[0]));
  if ( v67[8] && LODWORD(v67[7]) )
    RtlCopyFromUser(v63[1], v67[8], LODWORD(v67[7]));
  v33 = (UINT *)v67[5];
  if ( v67[5] )
    RtlCopyFromUser(v64[1], v67[5], 0x28u);
  for ( i = 0; ; ++i )
  {
    v66 = i;
    if ( i >= HIDWORD(v67[3]) )
      break;
    v35 = (void **)((char *)v19 + 80 * i);
    RtlCopyFromUser(v35, *((void **)v13 + i), 0x50u);
    v36 = &v22[i];
    RtlCopyFromUser(v36, v35[6], 0x58u);
    v37 = i;
    if ( v36->DirtyRectCount > 0xFFF )
    {
      WdLogSingleEntry3(2, v22[v37].DirtyRectCount, i, -1073741811);
      WdLogGlobalForLineNumber = 2694;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid DirtyRectCount:%u on plane %u, returing 0x%I64x",
        v36->DirtyRectCount,
        i,
        -1073741811,
        0,
        0);
      CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v61, v38, v39);
      return 3221225485LL;
    }
    DirtyRectCount = v22[v37].DirtyRectCount;
    v40 = 16 * DirtyRectCount;
    if ( !is_mul_ok(DirtyRectCount, 0x10u) )
      v40 = -1;
    v42 = operator new[](v40, 1265072196, 256);
    v43 = (void **)v64[0];
    *((_QWORD *)v64[0] + i) = v42;
    if ( !v42 )
    {
      PsGetCurrentProcess(v43);
      WdLogSingleEntry2(3, -1073741801);
      WdLogGlobalForLineNumber = 2704;
      CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v61, v44, v45);
      return 3221225495LL;
    }
    RtlCopyFromUser(v43[i], v36->pDirtyRects, 16LL * v36->DirtyRectCount);
    v46 = v64[0];
    v36->pDirtyRects = (RECT *)*((_QWORD *)v64[0] + i);
    v47 = *((unsigned int *)v35 + 4);
    if ( (unsigned int)v47 > HIDWORD(v67[0]) )
    {
      PsGetCurrentProcess(v46);
      WdLogSingleEntry2(2, -1073741811);
      WdLogGlobalForLineNumber = 2714;
      v49 = PsGetCurrentProcess(v48);
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid AllocationCount, returing 0x%I64x at 0x%I64x",
        -1073741811,
        v49,
        0,
        0,
        0);
      CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v61, v50, v51);
      return 3221225485LL;
    }
    v30 = (char *)v63[0];
    if ( (_DWORD)v47 )
      RtlCopyFromUser((char *)v63[0] + 4 * HIDWORD(v67[0]) * i, v35[3], 4 * v47);
    v19 = (struct _D3DKMT_MULTIPLANE_OVERLAY3 *)*((_QWORD *)&v61 + 1);
  }
  v67[4] = v13;
  v52 = (unsigned int *)*((_QWORD *)&v62 + 1);
  v67[1] = *((void **)&v62 + 1);
  v67[8] = v63[1];
  v67[5] = v64[1];
  for ( j = 0; (unsigned int)j < HIDWORD(v67[3]); j = (unsigned int)(j + 1) )
  {
    v33 = &v19->LayerIndex + 20 * (unsigned int)j;
    *((_QWORD *)v13 + (unsigned int)j) = v33;
    *((_QWORD *)v33 + 6) = &v22[(unsigned int)j];
    *((_QWORD *)v33 + 3) = &v30[4 * (unsigned int)(HIDWORD(v67[0]) * j)];
  }
  *(_OWORD *)&a2->hAdapter = *(_OWORD *)v67;
  *(_OWORD *)&a2->VidPnSourceId = *(_OWORD *)&v67[2];
  *(_OWORD *)&a2->ppPresentPlanes = *(_OWORD *)&v67[4];
  *(_OWORD *)&a2->Duration = *(_OWORD *)&v67[6];
  *(_OWORD *)&a2->pHDRMetaData = *(_OWORD *)&v67[8];
  *a3 = (struct _D3DKMT_MULTIPLANE_OVERLAY3 **)v13;
  *a4 = v19;
  *a5 = v22;
  *a6 = (struct tagRECT **)v64[0];
  *a7 = v52;
  *a8 = (unsigned int *)v30;
  *a9 = (unsigned __int8 *)v63[1];
  *a10 = (struct _D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION *)v64[1];
  v61 = 0;
  v62 = 0u;
  v64[0] = 0;
  *(_OWORD *)v63 = 0;
  v64[1] = 0;
  CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v61, v33, j);
  return 0;
}

```

## disassembly

```asm
0x140408e50  mov     rax, rsp
0x140408e53  mov     [rax+20h], r9
0x140408e57  mov     [rax+18h], r8
0x140408e5b  mov     [rax+10h], rdx
0x140408e5f  push    rbx
0x140408e60  push    rsi
0x140408e61  push    rdi
0x140408e62  push    r12
0x140408e64  push    r13
0x140408e66  push    r14
0x140408e68  push    r15
0x140408e6a  sub     rsp, 100h
0x140408e71  mov     rbx, rcx
0x140408e74  mov     esi, 50h ; 'P'
0x140408e79  mov     r8d, esi; Size
0x140408e7c  xor     edx, edx; Val
0x140408e7e  lea     rcx, [rax-88h]; void *
0x140408e85  call    memset
0x140408e8a  call    ?IsMSRC110351_61431726_Enabled@@YAHXZ; IsMSRC110351_61431726_Enabled(void)
0x140408e8f  xor     r14d, r14d
0x140408e92  test    eax, eax
0x140408e94  jz      short loc_140408ED3
0x140408e96  movups  xmm0, xmmword ptr [rbx]
0x140408e99  movaps  xmmword ptr [rsp+138h+var_88], xmm0
0x140408ea1  movups  xmm1, xmmword ptr [rbx+10h]
0x140408ea5  movaps  [rsp+138h+var_78], xmm1
0x140408ead  movups  xmm0, xmmword ptr [rbx+20h]
0x140408eb1  movaps  xmmword ptr [rsp+138h+Src], xmm0
0x140408eb9  movups  xmm1, xmmword ptr [rbx+30h]
0x140408ebd  movaps  xmmword ptr [rsp+138h+Size], xmm1
0x140408ec5  movups  xmm0, xmmword ptr [rbx+40h]
0x140408ec9  movaps  xmmword ptr [rsp+138h+var_48], xmm0
0x140408ed1  jmp     short loc_140408EE7
0x140408ed3  mov     r8, rsi; Size
0x140408ed6  mov     rdx, rbx; Src
0x140408ed9  lea     rcx, [rsp+138h+var_88]; void *
0x140408ee1  call    RtlCopyFromUser
0x140408ee6  nop
0x140408ee7  mov     ecx, dword ptr [rsp+138h+var_78+0Ch]
0x140408eee  lea     eax, [rcx-1]
0x140408ef1  cmp     eax, 9
0x140408ef4  ja      loc_140409795
0x140408efa  mov     eax, dword ptr [rsp+138h+var_88+4]
0x140408f01  dec     eax
0x140408f03  cmp     eax, 3Fh ; '?'
0x140408f06  ja      loc_140409733
0x140408f0c  mov     qword ptr [rsp+138h+var_E8+8], r14
0x140408f11  xorps   xmm0, xmm0
0x140408f14  movdqa  [rsp+138h+var_D8], xmm0
0x140408f1a  xorps   xmm1, xmm1
0x140408f1d  movdqa  xmmword ptr [rsp+138h+var_C8], xmm1
0x140408f23  movdqa  xmmword ptr [rsp+138h+var_B8], xmm0
0x140408f2c  mov     [rsp+138h+var_A8], ecx
0x140408f33  mov     eax, 8
0x140408f38  mul     rcx
0x140408f3b  mov     r15, 0FFFFFFFFFFFFFFFFh
0x140408f42  cmovb   rax, r15
0x140408f46  mov     ebx, 100h
0x140408f4b  mov     r8d, ebx
0x140408f4e  mov     edi, 4B677844h
0x140408f53  mov     edx, edi
0x140408f55  mov     rcx, rax
0x140408f58  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140408f5d  mov     r12, rax
0x140408f60  mov     qword ptr [rsp+138h+var_E8], rax
0x140408f65  test    rax, rax
0x140408f68  jnz     short loc_140408FAE
0x140408f6a  call    cs:__imp_PsGetCurrentProcess
0x140408f71  nop     dword ptr [rax+rax+00h]
0x140408f76  mov     r8, rax
0x140408f79  mov     rbx, 0FFFFFFFFC0000017h
0x140408f80  mov     rdx, rbx
0x140408f83  lea     ecx, [r15+4]
0x140408f87  call    cs:__imp_WdLogSingleEntry2
0x140408f8e  nop     dword ptr [rax+rax+00h]
0x140408f93  mov     cs:WdLogGlobalForLineNumber, 0A12h
0x140408f9d  lea     rcx, [rsp+138h+var_E8]
0x140408fa2  call    _CapturePresentMultiPlaneOverlayArgs3____2____AUTO____AUTO
0x140408fa7  mov     eax, ebx
0x140408fa9  jmp     loc_14040989B
0x140408fae  mov     ecx, dword ptr [rsp+138h+var_78+0Ch]
0x140408fb5  mov     rax, rsi
0x140408fb8  mul     rcx
0x140408fbb  cmovb   rax, r15
0x140408fbf  mov     r8, rbx
0x140408fc2  mov     edx, edi
0x140408fc4  mov     rcx, rax
0x140408fc7  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140408fcc  mov     rsi, rax
0x140408fcf  mov     qword ptr [rsp+138h+var_E8+8], rax
0x140408fd4  test    rax, rax
0x140408fd7  jnz     short loc_14040900D
0x140408fd9  call    cs:__imp_PsGetCurrentProcess
0x140408fe0  nop     dword ptr [rax+rax+00h]
0x140408fe5  mov     r8, rax
0x140408fe8  mov     rbx, 0FFFFFFFFC0000017h
0x140408fef  mov     rdx, rbx
0x140408ff2  lea     ecx, [rsi+3]
0x140408ff5  call    cs:__imp_WdLogSingleEntry2
0x140408ffc  nop     dword ptr [rax+rax+00h]
0x140409001  mov     cs:WdLogGlobalForLineNumber, 0A1Ch
0x14040900b  jmp     short loc_140408F9D
0x14040900d  mov     ecx, dword ptr [rsp+138h+var_78+0Ch]
0x140409014  mov     eax, 58h ; 'X'
0x140409019  mul     rcx
0x14040901c  cmovb   rax, r15
0x140409020  mov     r8, rbx
0x140409023  mov     edx, edi
0x140409025  mov     rcx, rax
0x140409028  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14040902d  mov     r13, rax
0x140409030  mov     qword ptr [rsp+138h+var_D8], rax
0x140409035  test    rax, rax
0x140409038  jnz     short loc_140409072
0x14040903a  call    cs:__imp_PsGetCurrentProcess
0x140409041  nop     dword ptr [rax+rax+00h]
0x140409046  mov     r8, rax
0x140409049  mov     rbx, 0FFFFFFFFC0000017h
0x140409050  mov     rdx, rbx
0x140409053  lea     ecx, [r13+3]
0x140409057  call    cs:__imp_WdLogSingleEntry2
0x14040905e  nop     dword ptr [rax+rax+00h]
0x140409063  mov     cs:WdLogGlobalForLineNumber, 0A26h
0x14040906d  jmp     loc_140408F9D
0x140409072  mov     ecx, dword ptr [rsp+138h+var_78+0Ch]
0x140409079  mov     eax, 8
0x14040907e  mul     rcx
0x140409081  cmovb   rax, r15
0x140409085  mov     r8, rbx
0x140409088  mov     edx, edi
0x14040908a  mov     rcx, rax
0x14040908d  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140409092  mov     [rsp+138h+var_B8], rax
0x14040909a  test    rax, rax
0x14040909d  jnz     short loc_1404090D8
0x14040909f  call    cs:__imp_PsGetCurrentProcess
0x1404090a6  nop     dword ptr [rax+rax+00h]
0x1404090ab  mov     r8, rax
0x1404090ae  mov     rbx, 0FFFFFFFFC0000017h
0x1404090b5  mov     rdx, rbx
0x1404090b8  mov     ecx, 3
0x1404090bd  call    cs:__imp_WdLogSingleEntry2
0x1404090c4  nop     dword ptr [rax+rax+00h]
0x1404090c9  mov     cs:WdLogGlobalForLineNumber, 0A30h
0x1404090d3  jmp     loc_140408F9D
0x1404090d8  mov     ecx, dword ptr [rsp+138h+var_88+4]
0x1404090df  mov     eax, 4
0x1404090e4  mul     rcx
0x1404090e7  mov     r14, r15
0x1404090ea  cmovb   rax, r15
0x1404090ee  mov     r8, rbx
0x1404090f1  mov     edx, edi
0x1404090f3  mov     rcx, rax
0x1404090f6  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1404090fb  mov     rdi, rax
0x1404090fe  mov     qword ptr [rsp+138h+var_D8+8], rax
0x140409103  xor     r15d, r15d
0x140409106  test    rax, rax
0x140409109  jnz     short loc_140409142
0x14040910b  call    cs:__imp_PsGetCurrentProcess
0x140409112  nop     dword ptr [rax+rax+00h]
0x140409117  mov     r8, rax
0x14040911a  mov     rbx, 0FFFFFFFFC0000017h
0x140409121  mov     rdx, rbx
0x140409124  lea     ecx, [rdi+3]
0x140409127  call    cs:__imp_WdLogSingleEntry2
0x14040912e  nop     dword ptr [rax+rax+00h]
0x140409133  mov     cs:WdLogGlobalForLineNumber, 0A3Ah
0x14040913d  jmp     loc_140408F9D
0x140409142  mov     ecx, dword ptr [rsp+138h+var_88+4]
0x140409149  imul    ecx, dword ptr [rsp+138h+var_78+0Ch]
0x140409151  mov     eax, 4
0x140409156  mul     rcx
0x140409159  cmovb   rax, r14
0x14040915d  mov     r8, rbx
0x140409160  mov     edx, 4B677844h
0x140409165  mov     rcx, rax
0x140409168  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14040916d  mov     r14, rax
0x140409170  mov     [rsp+138h+var_C8], rax
0x140409175  test    rax, rax
0x140409178  jnz     short loc_1404091B2
0x14040917a  call    cs:__imp_PsGetCurrentProcess
0x140409181  nop     dword ptr [rax+rax+00h]
0x140409186  mov     r8, rax
0x140409189  mov     rbx, 0FFFFFFFFC0000017h
0x140409190  mov     rdx, rbx
0x140409193  lea     ecx, [r14+3]
0x140409197  call    cs:__imp_WdLogSingleEntry2
0x14040919e  nop     dword ptr [rax+rax+00h]
0x1404091a3  mov     cs:WdLogGlobalForLineNumber, 0A44h
0x1404091ad  jmp     loc_140408F9D
0x1404091b2  cmp     [rsp+138h+var_48], r15
0x1404091ba  jz      short loc_140409219
0x1404091bc  mov     eax, dword ptr [rsp+138h+Size+8]
0x1404091c3  test    eax, eax
0x1404091c5  jz      short loc_140409219
0x1404091c7  mov     ecx, eax
0x1404091c9  mov     r8, rbx
0x1404091cc  mov     edx, 4B677844h
0x1404091d1  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1404091d6  mov     [rsp+138h+var_C8+8], rax
0x1404091db  test    rax, rax
0x1404091de  jnz     short loc_140409219
0x1404091e0  call    cs:__imp_PsGetCurrentProcess
0x1404091e7  nop     dword ptr [rax+rax+00h]
0x1404091ec  mov     r8, rax
0x1404091ef  mov     rbx, 0FFFFFFFFC0000017h
0x1404091f6  mov     rdx, rbx
0x1404091f9  mov     ecx, 3
0x1404091fe  call    cs:__imp_WdLogSingleEntry2
0x140409205  nop     dword ptr [rax+rax+00h]
0x14040920a  mov     cs:WdLogGlobalForLineNumber, 0A50h
0x140409214  jmp     loc_140408F9D
0x140409219  cmp     [rsp+138h+Src+8], r15
0x140409221  jz      short loc_14040927B
0x140409223  mov     r8, rbx
0x140409226  mov     edx, 4B677844h
0x14040922b  mov     ecx, 28h ; '('
0x140409230  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140409235  mov     [rsp+138h+var_B8+8], rax
0x14040923d  test    rax, rax
0x140409240  jnz     short loc_14040927B
0x140409242  call    cs:__imp_PsGetCurrentProcess
0x140409249  nop     dword ptr [rax+rax+00h]
0x14040924e  mov     r8, rax
0x140409251  mov     rbx, 0FFFFFFFFC0000017h
0x140409258  mov     rdx, rbx
0x14040925b  mov     ecx, 3
0x140409260  call    cs:__imp_WdLogSingleEntry2
0x140409267  nop     dword ptr [rax+rax+00h]
0x14040926c  mov     cs:WdLogGlobalForLineNumber, 0A5Dh
0x140409276  jmp     loc_140408F9D
0x14040927b  mov     r8d, dword ptr [rsp+138h+var_78+0Ch]
0x140409283  shl     r8, 3; Size
0x140409287  mov     rdx, [rsp+138h+Src]; Src
0x14040928f  mov     rcx, r12; void *
0x140409292  call    RtlCopyFromUser
0x140409297  mov     r8d, dword ptr [rsp+138h+var_88+4]
0x14040929f  shl     r8, 2; Size
0x1404092a3  mov     rdx, [rsp+138h+var_88+8]; Src
0x1404092ab  mov     rcx, rdi; void *
0x1404092ae  call    RtlCopyFromUser
0x1404092b3  mov     rdx, [rsp+138h+var_48]; Src
0x1404092bb  test    rdx, rdx
0x1404092be  jz      short loc_1404092D8
0x1404092c0  mov     eax, dword ptr [rsp+138h+Size+8]
0x1404092c7  test    eax, eax
0x1404092c9  jz      short loc_1404092D8
0x1404092cb  mov     r8d, eax; Size
0x1404092ce  mov     rcx, [rsp+138h+var_C8+8]; void *
0x1404092d3  call    RtlCopyFromUser
0x1404092d8  mov     rdx, [rsp+138h+Src+8]; Src
0x1404092e0  test    rdx, rdx
0x1404092e3  jz      short loc_1404092F8
0x1404092e5  mov     r8d, 28h ; '('; Size
0x1404092eb  mov     rcx, [rsp+138h+var_B8+8]; void *
0x1404092f3  call    RtlCopyFromUser
0x1404092f8  mov     ebx, r15d
0x1404092fb  mov     [rsp+138h+var_98], ebx
0x140409302  mov     ecx, dword ptr [rsp+138h+var_78+0Ch]
0x140409309  cmp     ebx, ecx
0x14040930b  jnb     loc_14040953F
0x140409311  mov     edi, ebx
0x140409313  lea     r15, [rdi+rdi*4]
0x140409317  shl     r15, 4
0x14040931b  add     r15, rsi
0x14040931e  mov     r8d, 50h ; 'P'; Size
0x140409324  mov     rdx, [r12+rdi*8]; Src
0x140409328  mov     rcx, r15; void *
0x14040932b  call    RtlCopyFromUser
0x140409330  imul    rsi, rdi, 58h ; 'X'
0x140409334  add     rsi, r13
0x140409337  mov     r8d, 58h ; 'X'; Size
0x14040933d  mov     rdx, [r15+30h]; Src
0x140409341  mov     rcx, rsi; void *
0x140409344  call    RtlCopyFromUser
0x140409349  mov     r14d, ebx
0x14040934c  imul    rax, r14, 58h ; 'X'
0x140409350  cmp     dword ptr [rsi+3Ch], 0FFFh
0x140409357  jbe     short loc_1404093D2
0x140409359  mov     edx, [rax+r13+3Ch]
0x14040935e  mov     rdi, 0FFFFFFFFC000000Dh
0x140409365  mov     r9, rdi
0x140409368  mov     r8d, r14d
0x14040936b  mov     ecx, 2
0x140409370  call    cs:__imp_WdLogSingleEntry3
0x140409377  nop     dword ptr [rax+rax+00h]
0x14040937c  mov     cs:WdLogGlobalForLineNumber, 0A86h
0x140409386  mov     ecx, [rsi+3Ch]
0x140409389  mov     [rsp+138h+var_F8], 0
0x140409392  mov     [rsp+138h+var_100], 0
0x14040939b  mov     [rsp+138h+var_108], rdi
0x1404093a0  mov     [rsp+138h+var_110], r14
0x1404093a5  mov     [rsp+138h+var_118], rcx
0x1404093aa  lea     r9, aInvalidDirtyre; "Invalid DirtyRectCount:%u on plane %u, "...
0x1404093b1  or      r8d, 0FFFFFFFFh
0x1404093b5  mov     edx, 40000h
0x1404093ba  xor     ecx, ecx
0x1404093bc  call    DxgkLogInternalTriageEvent
  ... truncated ...
```
