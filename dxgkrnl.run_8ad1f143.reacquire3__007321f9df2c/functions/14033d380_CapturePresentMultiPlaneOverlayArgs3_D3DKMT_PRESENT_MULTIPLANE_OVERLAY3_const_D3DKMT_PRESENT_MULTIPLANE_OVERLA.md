# CapturePresentMultiPlaneOverlayArgs3(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const *,_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *,_D3DKMT_MULTIPLANE_OVERLAY3 * * *,_D3DKMT_MULTIPLANE_OVERLAY3 * *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 * *,tagRECT * * *,uint * *,uint * *,uchar * *,_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION * *)

- ea: `0x14033d380`
- end: `0x14033de0a`
- name: `?CapturePresentMultiPlaneOverlayArgs3@@YAJPEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@PEAU1@PEAPEAPEAU_D3DKMT_MULTIPLANE_OVERLAY3@@PEAPEAU2@PEAPEAU_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3@@PEAPEAPEAUtagRECT@@PEAPEAI6PEAPEAEPEAPEAU_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION@@@Z`
- size: `2698`
- prototype: `__int64 __usercall@<rax>(const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *Src@<rcx>, struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *@<rdx>, struct _D3DKMT_MULTIPLANE_OVERLAY3 ***@<r8>, struct _D3DKMT_MULTIPLANE_OVERLAY3 **@<r9>, struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 **, struct tagRECT ***, unsigned int **, unsigned int **, unsigned __int8 **, struct _D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14033bd80`

## callees

- `0x140009030`
- `0x14001b890`
- `0x14002e110`
- `0x1400670a4`
- `0x1400a0540`
- `0x14033bcf0`
- `0x14033d380`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14033d3d4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d405`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d819`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d85e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d892`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d8e4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d915`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dab8`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033daf6`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033db85`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dbbb`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dc00`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dc36`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dc6c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dca5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dcde`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dd44`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dda3`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033ddd7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d3d4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d405`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d819`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d85e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d892`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d8e4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033d915`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dab8`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033daf6`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033db85`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dbbb`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dc00`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dc36`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dc6c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dca5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dcde`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dd44`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033dda3`
- `ntoskrnl!PsGetCurrentProcess` at `0x14033ddd7`
- `watchdog!WdLogSingleEntry2` at `0x14033d3ef`
- `watchdog!WdLogSingleEntry2` at `0x14033d837`
- `watchdog!WdLogSingleEntry2` at `0x14033d87c`
- `watchdog!WdLogSingleEntry2` at `0x14033d8ff`
- `watchdog!WdLogSingleEntry2` at `0x14033dba3`
- `watchdog!WdLogSingleEntry2` at `0x14033dbd9`
- `watchdog!WdLogSingleEntry2` at `0x14033dc1e`
- `watchdog!WdLogSingleEntry2` at `0x14033dc54`
- `watchdog!WdLogSingleEntry2` at `0x14033dc8a`
- `watchdog!WdLogSingleEntry2` at `0x14033dcc3`
- `watchdog!WdLogSingleEntry2` at `0x14033dcfc`
- `watchdog!WdLogSingleEntry2` at `0x14033dd62`
- `watchdog!WdLogSingleEntry2` at `0x14033ddc1`
- `watchdog!WdLogSingleEntry2` at `0x14033d3ef`
- `watchdog!WdLogSingleEntry2` at `0x14033d837`
- `watchdog!WdLogSingleEntry2` at `0x14033d87c`
- `watchdog!WdLogSingleEntry2` at `0x14033d8ff`
- `watchdog!WdLogSingleEntry2` at `0x14033dba3`
- `watchdog!WdLogSingleEntry2` at `0x14033dbd9`
- `watchdog!WdLogSingleEntry2` at `0x14033dc1e`
- `watchdog!WdLogSingleEntry2` at `0x14033dc54`
- `watchdog!WdLogSingleEntry2` at `0x14033dc8a`
- `watchdog!WdLogSingleEntry2` at `0x14033dcc3`
- `watchdog!WdLogSingleEntry2` at `0x14033dcfc`
- `watchdog!WdLogSingleEntry2` at `0x14033dd62`
- `watchdog!WdLogSingleEntry2` at `0x14033ddc1`
- `watchdog!WdLogSingleEntry3` at `0x14033d7be`
- `watchdog!WdLogSingleEntry3` at `0x14033dad9`
- `watchdog!WdLogSingleEntry3` at `0x14033d7be`
- `watchdog!WdLogSingleEntry3` at `0x14033dad9`

## string_xrefs

- `0x14033db1d`: `Presenting multi plane overlay plane count (0x%I64x) is invalid, returing 0x%I64x at 0x%I64x`
- `0x14033d43a`: `Fail to capture parameters, returing 0x%I64x at %I64x`
- `0x14033d94a`: `Fail to capture parameters, returing 0x%I64x at 0x%I64x`
- `0x14033d7f1`: `Invalid DirtyRectCount:%u on plane %u, returing 0x%I64x`
- `0x14033ddfe`: `Invalid ContextCount, returing 0x%I64x at 0x%I64x`
- `0x14033d8b7`: `Invalid AllocationCount, returing 0x%I64x at 0x%I64x`

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
  __int64 v14; // rax
  __int64 v15; // rcx
  struct _D3DKMT_MULTIPLANE_OVERLAY3 *v16; // r15
  __int64 v17; // rax
  __int64 v18; // rcx
  struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v19; // r14
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  void *v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int i; // ebx
  void **v28; // r13
  struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v29; // r14
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned __int64 v32; // kr00_8
  __int64 v33; // rax
  void **v34; // rcx
  void *v35; // rcx
  __int64 v36; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  unsigned int *v40; // rsi
  unsigned int v41; // r8d
  unsigned int *j; // r13
  __int64 v43; // rbx
  __int64 CurrentProcess; // rax
  __int64 v45; // rbx
  __int64 v46; // rcx
  char *v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // [rsp+28h] [rbp-110h]
  __int64 v52; // [rsp+30h] [rbp-108h]
  __int128 v53; // [rsp+50h] [rbp-E8h] BYREF
  __int128 v54; // [rsp+60h] [rbp-D8h]
  void *v55[2]; // [rsp+70h] [rbp-C8h]
  void *v56[2]; // [rsp+80h] [rbp-B8h]
  int v57; // [rsp+90h] [rbp-A8h]
  unsigned int v58; // [rsp+A0h] [rbp-98h]
  void *v59[17]; // [rsp+B0h] [rbp-88h] BYREF

  memset(v59, 0, 0x50u);
  RtlCopyFromUser(v59, Src, 0x50u);
  if ( (unsigned int)(HIDWORD(v59[3]) - 1) > 9 )
  {
    v43 = HIDWORD(v59[3]);
    CurrentProcess = PsGetCurrentProcess(HIDWORD(v59[3]));
    WdLogSingleEntry3(2, v43, -1073741811, CurrentProcess);
    WdLogGlobalForLineNumber = 2479;
    v45 = HIDWORD(v59[3]);
    v52 = PsGetCurrentProcess(v46);
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Presenting multi plane overlay plane count (0x%I64x) is invalid, returing 0x%I64x at 0x%I64x",
      v45,
      -1073741811,
      v52,
      0,
      0);
    return 3221225485LL;
  }
  if ( (unsigned int)(HIDWORD(v59[0]) - 1) > 0x3F )
  {
    PsGetCurrentProcess(HIDWORD(v59[3]));
    WdLogSingleEntry2(2, -1073741811);
    WdLogGlobalForLineNumber = 2488;
    v51 = PsGetCurrentProcess(v50);
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid ContextCount, returing 0x%I64x at 0x%I64x",
      -1073741811,
      v51,
      0,
      0,
      0);
    return 3221225485LL;
  }
  *((_QWORD *)&v53 + 1) = 0;
  v54 = 0;
  *(_OWORD *)v55 = 0;
  *(_OWORD *)v56 = 0;
  v57 = HIDWORD(v59[3]);
  v11 = 8LL * HIDWORD(v59[3]);
  if ( !is_mul_ok(HIDWORD(v59[3]), 8u) )
    v11 = -1;
  v13 = (void *)operator new[](v11, 1265072196, 256);
  *(_QWORD *)&v53 = v13;
  if ( !v13 )
  {
    PsGetCurrentProcess(v12);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2545;
LABEL_48:
    CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v53);
    return 3221225495LL;
  }
  v14 = 80LL * HIDWORD(v59[3]);
  if ( !is_mul_ok(HIDWORD(v59[3]), 0x50u) )
    v14 = -1;
  v16 = (struct _D3DKMT_MULTIPLANE_OVERLAY3 *)operator new[](v14, 1265072196, 256);
  *((_QWORD *)&v53 + 1) = v16;
  if ( !v16 )
  {
    PsGetCurrentProcess(v15);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2555;
    goto LABEL_48;
  }
  v17 = 88LL * HIDWORD(v59[3]);
  if ( !is_mul_ok(HIDWORD(v59[3]), 0x58u) )
    v17 = -1;
  v19 = (struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *)operator new[](v17, 1265072196, 256);
  *(_QWORD *)&v54 = v19;
  if ( !v19 )
  {
    PsGetCurrentProcess(v18);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2565;
    goto LABEL_48;
  }
  v20 = 8LL * HIDWORD(v59[3]);
  if ( !is_mul_ok(HIDWORD(v59[3]), 8u) )
    v20 = -1;
  v56[0] = (void *)operator new[](v20, 1265072196, 256);
  if ( !v56[0] )
  {
    PsGetCurrentProcess(v21);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2575;
    goto LABEL_48;
  }
  v22 = 4LL * HIDWORD(v59[0]);
  if ( !is_mul_ok(HIDWORD(v59[0]), 4u) )
    v22 = -1;
  v24 = (void *)operator new[](v22, 1265072196, 256);
  *((_QWORD *)&v54 + 1) = v24;
  if ( !v24 )
  {
    PsGetCurrentProcess(v23);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2585;
    goto LABEL_48;
  }
  v25 = 4LL * (unsigned int)(HIDWORD(v59[3]) * HIDWORD(v59[0]));
  if ( !is_mul_ok((unsigned int)(HIDWORD(v59[3]) * HIDWORD(v59[0])), 4u) )
    v25 = -1;
  v55[0] = (void *)operator new[](v25, 1265072196, 256);
  if ( !v55[0] )
  {
    PsGetCurrentProcess(v26);
    WdLogSingleEntry2(3, -1073741801);
    WdLogGlobalForLineNumber = 2595;
    goto LABEL_48;
  }
  if ( v59[8] )
  {
    if ( LODWORD(v59[7]) )
    {
      v55[1] = (void *)operator new[](LODWORD(v59[7]), 1265072196, 256);
      if ( !v55[1] )
      {
        PsGetCurrentProcess(v48);
        WdLogSingleEntry2(3, -1073741801);
        WdLogGlobalForLineNumber = 2607;
        goto LABEL_48;
      }
    }
  }
  if ( v59[5] )
  {
    v56[1] = (void *)operator new(40, 1265072196, 256);
    if ( !v56[1] )
    {
      PsGetCurrentProcess(v49);
      WdLogSingleEntry2(3, -1073741801);
      WdLogGlobalForLineNumber = 2620;
      goto LABEL_48;
    }
  }
  RtlCopyFromUser(v13, v59[4], 8LL * HIDWORD(v59[3]));
  RtlCopyFromUser(v24, v59[1], 4LL * HIDWORD(v59[0]));
  if ( v59[8] && LODWORD(v59[7]) )
    RtlCopyFromUser(v55[1], v59[8], LODWORD(v59[7]));
  if ( v59[5] )
    RtlCopyFromUser(v56[1], v59[5], 0x28u);
  for ( i = 0; ; ++i )
  {
    v58 = i;
    if ( i >= HIDWORD(v59[3]) )
      break;
    v28 = (void **)((char *)v16 + 80 * i);
    RtlCopyFromUser(v28, *((void **)v13 + i), 0x50u);
    v29 = &v19[i];
    RtlCopyFromUser(v29, v28[6], 0x58u);
    v30 = 88LL * i;
    if ( v29->DirtyRectCount > 0xFFF )
    {
      WdLogSingleEntry3(2, *(unsigned int *)(v30 + v54 + 60), i, -1073741811);
      WdLogGlobalForLineNumber = 2661;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid DirtyRectCount:%u on plane %u, returing 0x%I64x",
        v29->DirtyRectCount,
        i,
        -1073741811,
        0,
        0);
      CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v53);
      return 3221225485LL;
    }
    v32 = *(unsigned int *)(v30 + v54 + 60);
    v31 = 16 * v32;
    if ( !is_mul_ok(v32, 0x10u) )
      v31 = -1;
    v33 = operator new[](v31, 1265072196, 256);
    v34 = (void **)v56[0];
    *((_QWORD *)v56[0] + i) = v33;
    if ( !v33 )
    {
      PsGetCurrentProcess(v34);
      WdLogSingleEntry2(3, -1073741801);
      WdLogGlobalForLineNumber = 2671;
      CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v53);
      return 3221225495LL;
    }
    RtlCopyFromUser(v34[i], v29->pDirtyRects, 16LL * v29->DirtyRectCount);
    v35 = v56[0];
    v29->pDirtyRects = (RECT *)*((_QWORD *)v56[0] + i);
    v36 = *((unsigned int *)v28 + 4);
    if ( (unsigned int)v36 > HIDWORD(v59[0]) )
    {
      PsGetCurrentProcess(v35);
      WdLogSingleEntry2(2, -1073741811);
      WdLogGlobalForLineNumber = 2681;
      v39 = PsGetCurrentProcess(v38);
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid AllocationCount, returing 0x%I64x at 0x%I64x",
        -1073741811,
        v39,
        0,
        0,
        0);
      CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v53);
      return 3221225485LL;
    }
    if ( (_DWORD)v36 )
      RtlCopyFromUser((char *)v55[0] + 4 * HIDWORD(v59[0]) * i, v28[3], 4 * v36);
    v19 = (struct _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *)v54;
    v16 = (struct _D3DKMT_MULTIPLANE_OVERLAY3 *)*((_QWORD *)&v53 + 1);
  }
  v59[4] = v13;
  v40 = (unsigned int *)*((_QWORD *)&v54 + 1);
  v59[1] = *((void **)&v54 + 1);
  v59[8] = v55[1];
  v59[5] = v56[1];
  v41 = 0;
  for ( j = (unsigned int *)v55[0]; v41 < HIDWORD(v59[3]); ++v41 )
  {
    v47 = (char *)v16 + 80 * v41;
    *((_QWORD *)v13 + v41) = v47;
    *((_QWORD *)v47 + 6) = &v19[v41];
    *((_QWORD *)v47 + 3) = &j[HIDWORD(v59[0]) * v41];
  }
  *(_OWORD *)&a2->hAdapter = *(_OWORD *)v59;
  *(_OWORD *)&a2->VidPnSourceId = *(_OWORD *)&v59[2];
  *(_OWORD *)&a2->ppPresentPlanes = *(_OWORD *)&v59[4];
  *(_OWORD *)&a2->Duration = *(_OWORD *)&v59[6];
  *(_OWORD *)&a2->pHDRMetaData = *(_OWORD *)&v59[8];
  *a3 = (struct _D3DKMT_MULTIPLANE_OVERLAY3 **)v13;
  *a4 = v16;
  *a5 = v19;
  *a6 = (struct tagRECT **)v56[0];
  *a7 = v40;
  *a8 = j;
  *a9 = (unsigned __int8 *)v55[1];
  *a10 = (struct _D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION *)v56[1];
  v53 = 0;
  v54 = 0u;
  v56[0] = 0;
  *(_OWORD *)v55 = 0;
  v56[1] = 0;
  CapturePresentMultiPlaneOverlayArgs3_::_2_::_AUTO::__AUTO(&v53);
  return 0;
}

```

## disassembly

```asm
0x14033d380  mov     rax, rsp
0x14033d383  mov     [rax+20h], r9
0x14033d387  mov     [rax+18h], r8
0x14033d38b  mov     [rax+10h], rdx
0x14033d38f  push    rbx
0x14033d390  push    rsi
0x14033d391  push    rdi
0x14033d392  push    r12
0x14033d394  push    r13
0x14033d396  push    r14
0x14033d398  push    r15
0x14033d39a  sub     rsp, 100h
0x14033d3a1  mov     rbx, rcx
0x14033d3a4  mov     r14d, 50h ; 'P'
0x14033d3aa  mov     r8d, r14d; Size
0x14033d3ad  xor     edx, edx; Val
0x14033d3af  lea     rcx, [rax-88h]; void *
0x14033d3b6  call    memset
0x14033d3bb  nop
0x14033d3bc  mov     r8d, r14d; Size
0x14033d3bf  mov     rdx, rbx; Src
0x14033d3c2  lea     rcx, [rsp+138h+var_88]; void *
0x14033d3ca  call    RtlCopyFromUser
0x14033d3cf  jmp     loc_14033D45B
0x14033d3d4  call    cs:__imp_PsGetCurrentProcess
0x14033d3db  nop     dword ptr [rax+rax+00h]
0x14033d3e0  mov     r8, rax
0x14033d3e3  mov     rdx, 0FFFFFFFFC000000Dh
0x14033d3ea  mov     ecx, 2
0x14033d3ef  call    cs:__imp_WdLogSingleEntry2
0x14033d3f6  nop     dword ptr [rax+rax+00h]
0x14033d3fb  mov     cs:WdLogGlobalForLineNumber, 9A2h
0x14033d405  call    cs:__imp_PsGetCurrentProcess
0x14033d40c  nop     dword ptr [rax+rax+00h]
0x14033d411  mov     [rsp+138h+var_F8], 0
0x14033d41a  mov     [rsp+138h+var_100], 0
0x14033d423  mov     [rsp+138h+var_108], 0
0x14033d42c  mov     [rsp+138h+var_110], rax
0x14033d431  mov     [rsp+138h+var_118], 0FFFFFFFFC000000Dh
0x14033d43a  lea     r9, aFailToCaptureP; "Fail to capture parameters, returing 0x"...
0x14033d441  or      r8d, 0FFFFFFFFh
0x14033d445  mov     edx, 40000h
0x14033d44a  xor     ecx, ecx
0x14033d44c  call    DxgkLogInternalTriageEvent
0x14033d451  mov     eax, 0C000000Dh
0x14033d456  jmp     loc_14033DAA1
0x14033d45b  mov     ecx, [rsp+138h+var_6C]
0x14033d462  lea     eax, [rcx-1]
0x14033d465  cmp     eax, 9
0x14033d468  ja      loc_14033DAB5
0x14033d46e  mov     eax, dword ptr [rsp+138h+var_88+4]
0x14033d475  dec     eax
0x14033d477  cmp     eax, 3Fh ; '?'
0x14033d47a  ja      loc_14033DDA3
0x14033d480  xor     edi, edi
0x14033d482  mov     qword ptr [rsp+138h+var_E8+8], rdi
0x14033d487  xorps   xmm0, xmm0
0x14033d48a  movdqa  [rsp+138h+var_D8], xmm0
0x14033d490  xorps   xmm1, xmm1
0x14033d493  movdqa  xmmword ptr [rsp+138h+var_C8], xmm1
0x14033d499  movdqa  xmmword ptr [rsp+138h+var_B8], xmm0
0x14033d4a2  mov     [rsp+138h+var_A8], ecx
0x14033d4a9  lea     eax, [rdi+8]
0x14033d4ac  mul     rcx
0x14033d4af  lea     rsi, [rdi-1]
0x14033d4b3  cmovb   rax, rsi
0x14033d4b7  mov     ebx, 100h
0x14033d4bc  mov     r8d, ebx
0x14033d4bf  mov     r13d, 4B677844h
0x14033d4c5  mov     edx, r13d
0x14033d4c8  mov     rcx, rax
0x14033d4cb  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14033d4d0  mov     r12, rax
0x14033d4d3  mov     qword ptr [rsp+138h+var_E8], rax
0x14033d4d8  test    rax, rax
0x14033d4db  jz      loc_14033DB85
0x14033d4e1  mov     ecx, [rsp+138h+var_6C]
0x14033d4e8  mov     rax, r14
0x14033d4eb  mul     rcx
0x14033d4ee  cmovb   rax, rsi
0x14033d4f2  mov     r8d, ebx
0x14033d4f5  mov     edx, r13d
0x14033d4f8  mov     rcx, rax
0x14033d4fb  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14033d500  mov     r15, rax
0x14033d503  mov     qword ptr [rsp+138h+var_E8+8], rax
0x14033d508  test    rax, rax
0x14033d50b  jz      loc_14033DC00
0x14033d511  mov     ecx, [rsp+138h+var_6C]
0x14033d518  lea     eax, [rdi+58h]
0x14033d51b  mul     rcx
0x14033d51e  cmovb   rax, rsi
0x14033d522  mov     r8d, ebx
0x14033d525  mov     edx, r13d
0x14033d528  mov     rcx, rax
0x14033d52b  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14033d530  mov     r14, rax
0x14033d533  mov     qword ptr [rsp+138h+var_D8], rax
0x14033d538  test    rax, rax
0x14033d53b  jz      loc_14033DC36
0x14033d541  mov     ecx, [rsp+138h+var_6C]
0x14033d548  lea     eax, [rdi+8]
0x14033d54b  mul     rcx
0x14033d54e  cmovb   rax, rsi
0x14033d552  mov     r8d, ebx
0x14033d555  mov     edx, r13d
0x14033d558  mov     rcx, rax
0x14033d55b  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14033d560  mov     [rsp+138h+var_B8], rax
0x14033d568  test    rax, rax
0x14033d56b  jz      loc_14033DC6C
0x14033d571  mov     ecx, dword ptr [rsp+138h+var_88+4]
0x14033d578  lea     eax, [rdi+4]
0x14033d57b  mul     rcx
0x14033d57e  cmovb   rax, rsi
0x14033d582  mov     r8d, ebx
0x14033d585  mov     edx, r13d
0x14033d588  mov     rcx, rax
0x14033d58b  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14033d590  mov     rsi, rax
0x14033d593  mov     qword ptr [rsp+138h+var_D8+8], rax
0x14033d598  test    rax, rax
0x14033d59b  jz      loc_14033DCA5
0x14033d5a1  mov     ecx, dword ptr [rsp+138h+var_88+4]
0x14033d5a8  imul    ecx, [rsp+138h+var_6C]
0x14033d5b0  lea     eax, [rdi+4]
0x14033d5b3  mul     rcx
0x14033d5b6  lea     rcx, [rdi-1]
0x14033d5ba  cmovb   rax, rcx
0x14033d5be  mov     r8d, ebx
0x14033d5c1  mov     edx, r13d
0x14033d5c4  mov     rcx, rax
0x14033d5c7  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14033d5cc  mov     [rsp+138h+var_C8], rax
0x14033d5d1  test    rax, rax
0x14033d5d4  jz      loc_14033DCDE
0x14033d5da  cmp     [rsp+138h+var_48], rdi
0x14033d5e2  jnz     loc_14033DD17
0x14033d5e8  cmp     [rsp+138h+Src+8], rdi
0x14033d5f0  jnz     loc_14033DD7D
0x14033d5f6  mov     r8d, [rsp+138h+var_6C]
0x14033d5fe  shl     r8, 3; Size
0x14033d602  mov     rdx, [rsp+138h+Src]; Src
0x14033d60a  mov     rcx, r12; void *
0x14033d60d  call    RtlCopyFromUser
0x14033d612  mov     r8d, dword ptr [rsp+138h+var_88+4]
0x14033d61a  shl     r8, 2; Size
0x14033d61e  mov     rdx, [rsp+138h+var_88+8]; Src
0x14033d626  mov     rcx, rsi; void *
0x14033d629  call    RtlCopyFromUser
0x14033d62e  mov     rdx, [rsp+138h+var_48]; Src
0x14033d636  test    rdx, rdx
0x14033d639  jnz     loc_14033D767
0x14033d63f  mov     rdx, [rsp+138h+Src+8]; Src
0x14033d647  test    rdx, rdx
0x14033d64a  jnz     loc_14033D78B
0x14033d650  mov     ebx, edi
0x14033d652  mov     [rsp+138h+var_98], ebx
0x14033d659  cmp     ebx, [rsp+138h+var_6C]
0x14033d660  jnb     loc_14033D8DF
0x14033d666  mov     esi, ebx
0x14033d668  lea     r13, [rsi+rsi*4]
0x14033d66c  shl     r13, 4
0x14033d670  add     r13, r15
0x14033d673  mov     r8d, 50h ; 'P'; Size
0x14033d679  mov     rdx, [r12+rsi*8]; Src
0x14033d67d  mov     rcx, r13; void *
0x14033d680  call    RtlCopyFromUser
0x14033d685  imul    rax, rsi, 58h ; 'X'
0x14033d689  add     r14, rax
0x14033d68c  mov     r8d, 58h ; 'X'; Size
0x14033d692  mov     rdx, [r13+30h]; Src
0x14033d696  mov     rcx, r14; void *
0x14033d699  call    RtlCopyFromUser
0x14033d69e  mov     r15d, ebx
0x14033d6a1  imul    rax, r15, 58h ; 'X'
0x14033d6a5  cmp     dword ptr [r14+3Ch], 0FFFh
0x14033d6ad  ja      loc_14033D7A3
0x14033d6b3  mov     rcx, qword ptr [rsp+138h+var_D8]
0x14033d6b8  mov     ecx, [rax+rcx+3Ch]
0x14033d6bc  mov     eax, 10h
0x14033d6c1  mul     rcx
0x14033d6c4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14033d6cb  cmovb   rax, rcx
0x14033d6cf  mov     edx, 4B677844h
0x14033d6d4  mov     r8d, 100h
0x14033d6da  mov     rcx, rax
0x14033d6dd  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14033d6e2  mov     rcx, [rsp+138h+var_B8]
0x14033d6ea  mov     [rcx+r15*8], rax
0x14033d6ee  test    rax, rax
0x14033d6f1  jz      loc_14033D819
0x14033d6f7  mov     r8d, [r14+3Ch]
0x14033d6fb  shl     r8, 4; Size
0x14033d6ff  mov     rdx, [r14+40h]; Src
0x14033d703  mov     rcx, [rcx+rsi*8]; void *
0x14033d707  call    RtlCopyFromUser
0x14033d70c  mov     rcx, [rsp+138h+var_B8]
0x14033d714  mov     rax, [rcx+rsi*8]
0x14033d718  mov     [r14+40h], rax
0x14033d71c  mov     eax, [r13+10h]
0x14033d720  cmp     eax, dword ptr [rsp+138h+var_88+4]
0x14033d727  ja      loc_14033D85E
0x14033d72d  test    eax, eax
0x14033d72f  jnz     short loc_14033D742
0x14033d731  inc     ebx
0x14033d733  mov     r14, qword ptr [rsp+138h+var_D8]
0x14033d738  mov     r15, qword ptr [rsp+138h+var_E8+8]
0x14033d73d  jmp     loc_14033D652
0x14033d742  mov     r8, rax
0x14033d745  shl     r8, 2; Size
0x14033d749  mov     eax, ebx
0x14033d74b  imul    eax, dword ptr [rsp+138h+var_88+4]
0x14033d753  mov     rcx, [rsp+138h+var_C8]
0x14033d758  lea     rcx, [rcx+rax*4]; void *
0x14033d75c  mov     rdx, [r13+18h]; Src
0x14033d760  call    RtlCopyFromUser
0x14033d765  jmp     short loc_14033D731
0x14033d767  cmp     dword ptr [rsp+138h+Size], edi
0x14033d76e  jbe     loc_14033D63F
0x14033d774  mov     r8d, dword ptr [rsp+138h+Size]; Size
0x14033d77c  mov     rcx, [rsp+138h+var_C8+8]; void *
0x14033d781  call    RtlCopyFromUser
0x14033d786  jmp     loc_14033D63F
0x14033d78b  mov     r8d, 28h ; '('; Size
0x14033d791  mov     rcx, [rsp+138h+var_B8+8]; void *
0x14033d799  call    RtlCopyFromUser
0x14033d79e  jmp     loc_14033D650
0x14033d7a3  mov     rcx, qword ptr [rsp+138h+var_D8]
0x14033d7a8  mov     edx, [rax+rcx+3Ch]
0x14033d7ac  mov     rsi, 0FFFFFFFFC000000Dh
0x14033d7b3  mov     r9, rsi
0x14033d7b6  mov     r8, r15
0x14033d7b9  mov     ecx, 2
0x14033d7be  call    cs:__imp_WdLogSingleEntry3
0x14033d7c5  nop     dword ptr [rax+rax+00h]
0x14033d7ca  mov     cs:WdLogGlobalForLineNumber, 0A65h
0x14033d7d4  mov     ecx, [r14+3Ch]
0x14033d7d8  mov     [rsp+138h+var_F8], rdi
0x14033d7dd  mov     [rsp+138h+var_100], rdi
0x14033d7e2  mov     [rsp+138h+var_108], rsi
0x14033d7e7  mov     [rsp+138h+var_110], r15
0x14033d7ec  mov     [rsp+138h+var_118], rcx
0x14033d7f1  lea     r9, aInvalidDirtyre; "Invalid DirtyRectCount:%u on plane %u, "...
0x14033d7f8  or      r8d, 0FFFFFFFFh
0x14033d7fc  mov     edx, 40000h
0x14033d801  xor     ecx, ecx
0x14033d803  call    DxgkLogInternalTriageEvent
0x14033d808  lea     rcx, [rsp+138h+var_E8]
0x14033d80d  call    _CapturePresentMultiPlaneOverlayArgs3____2____AUTO____AUTO
0x14033d812  mov     eax, esi
0x14033d814  jmp     loc_14033DAA1
0x14033d819  call    cs:__imp_PsGetCurrentProcess
0x14033d820  nop     dword ptr [rax+rax+00h]
0x14033d825  mov     r8, rax
0x14033d828  mov     rbx, 0FFFFFFFFC0000017h
0x14033d82f  mov     rdx, rbx
0x14033d832  mov     ecx, 3
0x14033d837  call    cs:__imp_WdLogSingleEntry2
0x14033d83e  nop     dword ptr [rax+rax+00h]
0x14033d843  mov     cs:WdLogGlobalForLineNumber, 0A6Fh
0x14033d84d  lea     rcx, [rsp+138h+var_E8]
0x14033d852  call    _CapturePresentMultiPlaneOverlayArgs3____2____AUTO____AUTO
0x14033d857  mov     eax, ebx
0x14033d859  jmp     loc_14033DAA1
0x14033d85e  call    cs:__imp_PsGetCurrentProcess
0x14033d865  nop     dword ptr [rax+rax+00h]
0x14033d86a  mov     r8, rax
0x14033d86d  mov     rsi, 0FFFFFFFFC000000Dh
0x14033d874  mov     rdx, rsi
0x14033d877  mov     ecx, 2
0x14033d87c  call    cs:__imp_WdLogSingleEntry2
0x14033d883  nop     dword ptr [rax+rax+00h]
0x14033d888  mov     cs:WdLogGlobalForLineNumber, 0A79h
0x14033d892  call    cs:__imp_PsGetCurrentProcess
0x14033d899  nop     dword ptr [rax+rax+00h]
0x14033d89e  mov     [rsp+138h+var_F8], rdi
0x14033d8a3  mov     [rsp+138h+var_100], rdi
0x14033d8a8  mov     [rsp+138h+var_108], rdi
0x14033d8ad  mov     [rsp+138h+var_110], rax
0x14033d8b2  mov     [rsp+138h+var_118], rsi
0x14033d8b7  lea     r9, aInvalidAllocat_4; "Invalid AllocationCount, returing 0x%I6"...
0x14033d8be  or      r8d, 0FFFFFFFFh
0x14033d8c2  mov     edx, 40000h
0x14033d8c7  xor     ecx, ecx
0x14033d8c9  call    DxgkLogInternalTriageEvent
0x14033d8ce  lea     rcx, [rsp+138h+var_E8]
0x14033d8d3  call    _CapturePresentMultiPlaneOverlayArgs3____2____AUTO____AUTO
0x14033d8d8  mov     eax, esi
0x14033d8da  jmp     loc_14033DAA1
0x14033d8df  jmp     loc_14033D975
0x14033d8e4  call    cs:__imp_PsGetCurrentProcess
0x14033d8eb  nop     dword ptr [rax+rax+00h]
0x14033d8f0  mov     r8, rax
0x14033d8f3  mov     rdx, 0FFFFFFFFC000000Dh
0x14033d8fa  mov     ecx, 2
0x14033d8ff  call    cs:__imp_WdLogSingleEntry2
0x14033d906  nop     dword ptr [rax+rax+00h]
0x14033d90b  mov     cs:WdLogGlobalForLineNumber, 0A89h
0x14033d915  call    cs:__imp_PsGetCurrentProcess
  ... truncated ...
```
