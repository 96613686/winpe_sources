# CVideoProcessor::Blt(ID3D11VideoProcessorOutputView *,uint,uint,D3D11_VIDEO_PROCESSOR_STREAM const *)

- ea: `0x180035f10`
- end: `0x180037289`
- name: `?Blt@CVideoProcessor@@UEAAJPEAUID3D11VideoProcessorOutputView@@IIPEBUD3D11_VIDEO_PROCESSOR_STREAM@@@Z`
- size: `4985`
- prototype: `__int64 __fastcall(CVideoProcessor *this, struct ID3D11VideoProcessorOutputView *, unsigned int, unsigned int, const struct D3D11_VIDEO_PROCESSOR_STREAM *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180034720`

## callees

- `0x180008b5c`
- `0x180022400`
- `0x1800354b8`
- `0x180035518`
- `0x180035cf0`
- `0x180035f10`
- `0x180037290`
- `0x1800617a0`
- `0x180061d08`
- `0x180062d40`
- `0x180063000`
- `0x18006f23c`
- `0x18006f3e4`
- `0x18007a9c8`
- `0x18007b4ac`
- `0x1800977b8`
- `0x1800a0e4c`
- `0x1800a9d20`
- `0x1800aa9a8`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180036672`
- `ntdll!EtwEventWrite` at `0x180036672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036263`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036263`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVideoProcessor::Blt(
        CVideoProcessor *this,
        struct ID3D11VideoProcessorOutputView *a2,
        unsigned int a3,
        unsigned int a4,
        const struct D3D11_VIDEO_PROCESSOR_STREAM *a5)
{
  __int64 v5; // r15
  unsigned int v8; // r14d
  struct ID3D11VideoProcessorOutputViewVtbl *lpVtbl; // rax
  unsigned int SetPrivateData; // edx
  unsigned int SetPrivateData_high; // ecx
  enum DXGI_FORMAT v12; // r10d
  __int64 v13; // rax
  CD3D11TelemetryHelper *v14; // rcx
  unsigned int v15; // edx
  char v16; // r12
  unsigned int v17; // r13d
  unsigned int v18; // ebx
  char *v19; // r13
  __int64 v20; // r14
  struct CVideoProcessorOutputView *v21; // rsi
  const struct tagRECT *v22; // rax
  CVideoProcessor *v23; // r15
  __int64 v24; // rsi
  int v25; // r12d
  __int64 v26; // rbx
  char *v27; // rdx
  __int64 v28; // rcx
  unsigned int v29; // edi
  unsigned int v30; // edx
  int v31; // r14d
  char v32; // al
  __int64 v34; // r9
  __int64 v35; // rbx
  int v36; // ecx
  unsigned int OutputFramesForCustomRate; // r8d
  unsigned int *v38; // rsi
  unsigned int v39; // edx
  char *v40; // rsi
  __int64 v41; // rbx
  struct CVideoProcessorInputView *v42; // r12
  __int64 v43; // r15
  __int64 v44; // r8
  __int64 v45; // r15
  __int64 v46; // r15
  char *v47; // rcx
  void **v48; // rdi
  unsigned int v49; // edx
  unsigned int v50; // edx
  unsigned int v51; // edx
  int v52; // eax
  __int64 v53; // r8
  unsigned int v54; // edx
  __int64 v55; // rcx
  unsigned int v56; // r10d
  unsigned int v57; // edx
  enum DXGI_FORMAT v58; // r15d
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  int v62; // ecx
  __int64 i; // rdx
  unsigned int v64; // r8d
  int v65; // ecx
  __int64 v66; // rax
  __int64 v67; // rax
  unsigned __int64 v68; // rax
  __int64 m; // r12
  unsigned __int64 v70; // rax
  __int64 n; // r15
  unsigned __int64 v72; // rax
  __int64 j; // r15
  unsigned __int64 v74; // rax
  __int64 k; // r12
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  unsigned int v79; // [rsp+40h] [rbp-358h] BYREF
  enum DXGI_FORMAT v80; // [rsp+48h] [rbp-350h]
  tagRECT v81; // [rsp+50h] [rbp-348h] BYREF
  unsigned int v82; // [rsp+60h] [rbp-338h]
  unsigned int v83; // [rsp+68h] [rbp-330h] BYREF
  unsigned int v84; // [rsp+70h] [rbp-328h] BYREF
  LONG v85; // [rsp+78h] [rbp-320h] BYREF
  int v86; // [rsp+80h] [rbp-318h] BYREF
  struct CVideoProcessorInputView *v87; // [rsp+88h] [rbp-310h] BYREF
  int v88; // [rsp+90h] [rbp-308h]
  int v89; // [rsp+94h] [rbp-304h]
  int v90; // [rsp+98h] [rbp-300h]
  int v91; // [rsp+9Ch] [rbp-2FCh]
  enum DXGI_FORMAT v92; // [rsp+A0h] [rbp-2F8h] BYREF
  int v93; // [rsp+A8h] [rbp-2F0h] BYREF
  unsigned int v94; // [rsp+B0h] [rbp-2E8h]
  struct CVideoProcessorOutputView *v95; // [rsp+B8h] [rbp-2E0h]
  unsigned int v96; // [rsp+C0h] [rbp-2D8h]
  char *v97; // [rsp+C8h] [rbp-2D0h]
  _BYTE v98[20]; // [rsp+D0h] [rbp-2C8h] BYREF
  __int64 v99; // [rsp+E8h] [rbp-2B0h] BYREF
  __int16 v100; // [rsp+F0h] [rbp-2A8h]
  __int128 v101; // [rsp+F8h] [rbp-2A0h] BYREF
  void **v102; // [rsp+110h] [rbp-288h] BYREF
  int v103; // [rsp+118h] [rbp-280h]
  __int128 v104; // [rsp+120h] [rbp-278h]
  void **pExceptionObject; // [rsp+130h] [rbp-268h] BYREF
  int v106; // [rsp+138h] [rbp-260h]
  __int128 v107; // [rsp+140h] [rbp-258h]
  void **v108; // [rsp+150h] [rbp-248h] BYREF
  int v109; // [rsp+158h] [rbp-240h]
  __int128 v110; // [rsp+160h] [rbp-238h]
  void **v111; // [rsp+170h] [rbp-228h] BYREF
  int v112; // [rsp+178h] [rbp-220h]
  __int128 v113; // [rsp+180h] [rbp-218h]
  void **v114; // [rsp+190h] [rbp-208h] BYREF
  int v115; // [rsp+198h] [rbp-200h]
  __int128 v116; // [rsp+1A0h] [rbp-1F8h]
  void **v117; // [rsp+1B0h] [rbp-1E8h] BYREF
  int v118; // [rsp+1B8h] [rbp-1E0h]
  __int128 v119; // [rsp+1C0h] [rbp-1D8h]
  void **v120; // [rsp+1D0h] [rbp-1C8h] BYREF
  int v121; // [rsp+1D8h] [rbp-1C0h]
  __int128 v122; // [rsp+1E0h] [rbp-1B8h]
  void **v123; // [rsp+1F0h] [rbp-1A8h] BYREF
  int v124; // [rsp+1F8h] [rbp-1A0h]
  __int128 v125; // [rsp+200h] [rbp-198h]
  void **v126; // [rsp+210h] [rbp-188h] BYREF
  int v127; // [rsp+218h] [rbp-180h]
  __int128 v128; // [rsp+220h] [rbp-178h]
  void **v129; // [rsp+230h] [rbp-168h] BYREF
  int v130; // [rsp+238h] [rbp-160h]
  __int128 v131; // [rsp+240h] [rbp-158h]
  void **v132; // [rsp+250h] [rbp-148h] BYREF
  int v133; // [rsp+258h] [rbp-140h]
  __int128 v134; // [rsp+260h] [rbp-138h]
  void **v135; // [rsp+270h] [rbp-128h] BYREF
  int v136; // [rsp+278h] [rbp-120h]
  __int128 v137; // [rsp+280h] [rbp-118h]
  CVideoProcessor *v138; // [rsp+290h] [rbp-108h]
  int v139; // [rsp+298h] [rbp-100h]
  struct tagRECT v140; // [rsp+29Ch] [rbp-FCh] BYREF
  _QWORD v141[20]; // [rsp+2B0h] [rbp-E8h] BYREF

  v5 = a4;
  v82 = a4;
  v94 = a3;
  v95 = (struct CVideoProcessorOutputView *)a2;
  v96 = a4;
  *(_QWORD *)v98 = a5;
  v8 = 0;
  v97 = 0;
  v99 = *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL);
  v100 = 7169;
  if ( !*((_DWORD *)this + 140) )
    CVideoProcessor::InitState(this);
  if ( (unsigned int)v5 > *((_DWORD *)this + 75) )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
      3145890,
      v5);
    ThrowFailure(-2147024809);
  }
  if ( !a2 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
      3145889,
      0);
    ThrowFailure(-2147024809);
  }
  lpVtbl = a2[26].lpVtbl;
  SetPrivateData = (unsigned int)lpVtbl[4].SetPrivateData;
  v83 = SetPrivateData;
  SetPrivateData_high = HIDWORD(lpVtbl[4].SetPrivateData);
  v84 = SetPrivateData_high;
  v12 = SWORD2(lpVtbl[3].SetPrivateData);
  v92 = v12;
  if ( *((_DWORD *)this + 76) )
  {
    v81 = *(tagRECT *)((char *)this + 308);
    v13 = *(_QWORD *)((char *)this + 316);
    if ( SetPrivateData < (unsigned int)v13 || SetPrivateData_high < HIDWORD(v13) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
        3145891,
        0);
      v102 = &_com_error::`vftable';
      v103 = -2147024809;
      v104 = 0;
      throw (_com_error *)&v102;
    }
    if ( (unsigned int)CVideoProcessor::AdjustRectForFormat(this, v12, 1, &v81) )
      CVideoProcessor::SetOutputTargetRect(this, 1, &v81);
  }
  v101 = 0;
  ((void (__fastcall *)(struct ID3D11VideoProcessorOutputView *, __int128 *))a2->lpVtbl->GetDesc)(a2, &v101);
  v15 = HIDWORD(v101);
  if ( (_DWORD)v101 == 1 )
    v15 = 1;
  if ( *((_DWORD *)this + 92) )
  {
    if ( v15 != 2 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
        3145898,
        v15);
      ThrowFailure(-2147024809);
    }
  }
  else if ( v15 != 1 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
      3145899,
      0);
    ThrowFailure(-2147024809);
  }
  v16 = 1;
  v80 = DXGI_FORMAT_UNKNOWN;
  v91 = 0;
  v90 = 0;
  v89 = 0;
  v88 = 0;
  v85 = 0;
  v86 = -1;
  v17 = 0;
  v79 = 0;
  while ( v8 < (unsigned int)v5 )
  {
    v34 = 1324LL * v8;
    *(_QWORD *)&v81.left = v34;
    v35 = v34 + *((_QWORD *)this + 52);
    v36 = *(_DWORD *)(v35 + 8);
    OutputFramesForCustomRate = 0;
    if ( v36 )
    {
      v65 = v36 - 1;
      if ( v65 )
      {
        if ( v65 == 1 )
        {
          OutputFramesForCustomRate = CVideoProcessor::GetOutputFramesForCustomRate(
                                        this,
                                        (const struct DXGI_RATIONAL *)(v35 + 16),
                                        *(enum D3D11_VIDEO_FRAME_FORMAT *)v35);
          v34 = *(_QWORD *)&v81.left;
        }
      }
      else
      {
        OutputFramesForCustomRate = 1;
      }
    }
    else
    {
      LOBYTE(OutputFramesForCustomRate) = *(_DWORD *)v35 != 0;
      ++OutputFramesForCustomRate;
    }
    v38 = (unsigned int *)(*(_QWORD *)v98 + 72LL * v8);
    v39 = v38[1];
    if ( v39 >= OutputFramesForCustomRate )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
        3145892,
        v39);
      pExceptionObject = &_com_error::`vftable';
      v106 = -2147024809;
      v107 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    v52 = *(_DWORD *)(v35 + 1136);
    v53 = *((_QWORD *)v38 + 7);
    if ( v52 == 3 )
    {
      if ( !v53 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
          *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
          3145900,
          0,
          v34);
        v108 = &_com_error::`vftable';
        v109 = -2147024809;
        v110 = 0;
        throw (_com_error *)&v108;
      }
    }
    else if ( v53 || *((_QWORD *)v38 + 6) || *((_QWORD *)v38 + 8) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
        3145901,
        0,
        v34);
      v135 = &_com_error::`vftable';
      v136 = -2147024809;
      v137 = 0;
      throw (_com_error *)&v135;
    }
    v14 = (CD3D11TelemetryHelper *)*v38;
    if ( (_DWORD)v14 && v52 )
    {
      if ( v52 == 4 && !*((_DWORD *)this + 92) )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
          *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
          3145902,
          0);
        v111 = &_com_error::`vftable';
        v112 = -2147024809;
        v113 = 0;
        throw (_com_error *)&v111;
      }
      ++v79;
    }
    v54 = v38[3];
    if ( v54 > *((_DWORD *)this + 62) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
        3145893,
        v54);
      v114 = &_com_error::`vftable';
      v115 = -2147024809;
      v116 = 0;
      throw (_com_error *)&v114;
    }
    if ( v38[4] > *((_DWORD *)this + 63) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
        3145894,
        v38[3]);
      v117 = &_com_error::`vftable';
      v118 = -2147024809;
      v119 = 0;
      throw (_com_error *)&v117;
    }
    if ( (_DWORD)v14 )
    {
      v55 = *(_QWORD *)(*((_QWORD *)v38 + 4) + 208LL);
      v56 = *(_DWORD *)(v55 + 328);
      LODWORD(v87) = v56;
      v57 = *(_DWORD *)(v55 + 332);
      v93 = v57;
      v58 = *(__int16 *)(v55 + 260);
      if ( v16 )
      {
        v80 = *(__int16 *)(v55 + 260);
        v86 = *(_DWORD *)(v35 + 1232);
        v85 = *(_DWORD *)(v35 + 1160);
      }
      if ( v53 )
      {
        v78 = *(_QWORD *)(v53 + 208);
        if ( *(_DWORD *)(v78 + 328) != v56 || *(_DWORD *)(v78 + 332) != v57 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL)
                                                                   + 32LL))(
            *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
            3145903,
            0,
            v34);
          v120 = &_com_error::`vftable';
          v121 = -2147024809;
          v122 = 0;
          throw (_com_error *)&v120;
        }
      }
      if ( *(_DWORD *)(v35 + 24) )
      {
        if ( v56 < *(_DWORD *)(v35 + 36) || v57 < *(_DWORD *)(v35 + 40) )
        {
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL)
                                                                   + 32LL))(
            *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
            3145895,
            0,
            v34);
          v123 = &_com_error::`vftable';
          v124 = -2147024809;
          v125 = 0;
          throw (_com_error *)&v123;
        }
        if ( (unsigned int)CVideoProcessor::AdjustRectForFormat(this, v58, 0, (struct tagRECT *)(v35 + 28)) )
          CVideoProcessor::SetStreamSourceRect(
            this,
            v8,
            1,
            (const struct tagRECT *)(*(_QWORD *)&v81.left + 28LL + *((_QWORD *)this + 52)));
        v34 = *(_QWORD *)&v81.left;
        if ( v16 )
        {
          v59 = *((_QWORD *)this + 52);
          v91 = *(_DWORD *)(*(_QWORD *)&v81.left + v59 + 36) - *(_DWORD *)(*(_QWORD *)&v81.left + v59 + 28);
          v90 = *(_DWORD *)(*(_QWORD *)&v81.left + v59 + 40) - *(_DWORD *)(*(_QWORD *)&v81.left + v59 + 32);
        }
      }
      else if ( v16 )
      {
        v91 = v56;
        v90 = v57;
      }
      v60 = *((_QWORD *)this + 52);
      if ( *(_DWORD *)(v34 + v60 + 44) )
      {
        if ( v83 < *(_DWORD *)(v34 + v60 + 56) || v84 < *(_DWORD *)(v34 + v60 + 60) )
        {
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
            *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
            3145896,
            0);
          v126 = &_com_error::`vftable';
          v127 = -2147024809;
          v128 = 0;
          throw (_com_error *)&v126;
        }
        if ( (unsigned int)CVideoProcessor::AdjustRectForFormat(this, v92, 1, (struct tagRECT *)(v60 + 48 + v34)) )
          CVideoProcessor::SetStreamDestRect(
            this,
            v8,
            1,
            (const struct tagRECT *)(*(_QWORD *)&v81.left + 48LL + *((_QWORD *)this + 52)));
        v34 = *(_QWORD *)&v81.left;
        if ( v16 )
        {
          v61 = *((_QWORD *)this + 52);
          v89 = *(_DWORD *)(*(_QWORD *)&v81.left + v61 + 56) - *(_DWORD *)(*(_QWORD *)&v81.left + v61 + 48);
          v62 = *(_DWORD *)(*(_QWORD *)&v81.left + v61 + 60) - *(_DWORD *)(*(_QWORD *)&v81.left + v61 + 52);
          goto LABEL_88;
        }
      }
      else if ( v16 )
      {
        v89 = v83;
        v62 = v84;
LABEL_88:
        v88 = v62;
      }
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v64 = v38[3];
        v14 = (CD3D11TelemetryHelper *)(v64 + v38[4]);
        if ( (unsigned int)i >= (unsigned int)v14 )
          break;
        if ( (unsigned int)i < v64 )
          v66 = *(_QWORD *)(*((_QWORD *)v38 + 3) + 8 * i);
        else
          v66 = *(_QWORD *)(*((_QWORD *)v38 + 5) + 8LL * ((unsigned int)i - v64));
        v67 = *(_QWORD *)(v66 + 208);
        if ( *(_DWORD *)(v67 + 328) != (_DWORD)v87 || *(_DWORD *)(v67 + 332) != v93 || *(__int16 *)(v67 + 260) != v58 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL)
                                                                   + 32LL))(
            *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
            3145897,
            0,
            v34);
          v132 = &_com_error::`vftable';
          v133 = -2147024809;
          v134 = 0;
          throw (_com_error *)&v132;
        }
        if ( *(_DWORD *)(v34 + *((_QWORD *)this + 52) + 1136) == 3 )
        {
          v76 = (unsigned int)i >= v64
              ? *(_QWORD *)(*((_QWORD *)v38 + 8) + 8LL * ((unsigned int)i - v64))
              : *(_QWORD *)(*((_QWORD *)v38 + 6) + 8 * i);
          v77 = *(_QWORD *)(v76 + 208);
          if ( *(_DWORD *)(v77 + 328) != (_DWORD)v87 || *(_DWORD *)(v77 + 332) != v93 || *(__int16 *)(v77 + 260) != v58 )
          {
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
              *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
              3145897,
              0);
            v129 = &_com_error::`vftable';
            v130 = -2147024809;
            v131 = 0;
            throw (_com_error *)&v129;
          }
        }
      }
      ++v17;
      v16 = 0;
      LODWORD(v5) = v82;
    }
    ++v8;
  }
  if ( v17 > *((_DWORD *)this + 74) )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
      3145890,
      v17);
    ThrowFailure(-2147024809);
  }
  v18 = v79;
  if ( *((_DWORD *)this + 92) && !v79 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
      3145904,
      0);
    ThrowFailure(-2147024809);
  }
  if ( byte_18022B788 && (v17 != *((_DWORD *)this + 143) || v79 != *((_DWORD *)this + 144)) )
  {
    CD3D11TelemetryHelper::LogVideoProcessorStreamUsage(v14, v17, v79);
    *((_DWORD *)this + 143) = v17;
    *((_DWORD *)this + 144) = v18;
  }
  v19 = (char *)operator new[](saturated_mul((unsigned int)v5, 0x48u));
  v97 = v19;
  memset_0(v19, 0, 72LL * (unsigned int)v5);
  v20 = 0;
  while ( (unsigned int)v20 < (unsigned int)v5 )
  {
    v40 = &v19[72 * v20];
    memset_0(v40, 0, 0x48u);
    v41 = *(_QWORD *)v98 + 72 * v20;
    if ( *(_DWORD *)v41 )
    {
      *(_DWORD *)v40 = 1;
      *((_DWORD *)v40 + 1) = *(_DWORD *)(v41 + 4);
      *((_DWORD *)v40 + 2) = *(_DWORD *)(v41 + 8);
      *((_DWORD *)v40 + 3) = *(_DWORD *)(v41 + 12);
      *((_DWORD *)v40 + 4) = *(_DWORD *)(v41 + 16);
      v42 = *(struct CVideoProcessorInputView **)(v41 + 32);
      CVideoProcessor::CheckInputHazardTracking(this, v42);
      *((_QWORD *)v40 + 4) = (char *)v42 + 288;
      v43 = 1324LL * (unsigned int)v20;
      *(_QWORD *)&v81.left = v43;
      v44 = *((_QWORD *)this + 52);
      if ( *(_DWORD *)(v44 + v43 + 1248) )
      {
        CVideoProcessor::SetLegacyStreamColorSpace(
          this,
          v20,
          *(struct D3D11_VIDEO_PROCESSOR_COLOR_SPACE *)(v44 + v43 + 4),
          (enum DXGI_FORMAT)*(__int16 *)(*((_QWORD *)v42 + 26) + 260LL));
        *(_DWORD *)(v43 + *((_QWORD *)this + 52) + 1248) = 0;
      }
      v45 = *(_QWORD *)(v41 + 56);
      if ( v45 )
      {
        CVideoProcessor::CheckInputHazardTracking(this, *(struct CVideoProcessorInputView **)(v41 + 56));
        *((_QWORD *)v40 + 7) = v45 + 288;
      }
      if ( *((_DWORD *)v40 + 3) )
      {
        v72 = 8LL * *((unsigned int *)v40 + 3);
        if ( !is_mul_ok(*((unsigned int *)v40 + 3), 8u) )
          v72 = -1;
        *((_QWORD *)v40 + 3) = operator new[](v72);
        for ( j = 0; (unsigned int)j < *((_DWORD *)v40 + 3); j = (unsigned int)(j + 1) )
        {
          v87 = *(struct CVideoProcessorInputView **)(8 * j + *(_QWORD *)(v41 + 24));
          CVideoProcessor::CheckInputHazardTracking(this, v87);
          *(_QWORD *)(8 * j + *((_QWORD *)v40 + 3)) = (char *)v87 + 288;
        }
        v46 = *(_QWORD *)&v81.left;
        if ( *(_DWORD *)(*((_QWORD *)this + 52) + *(_QWORD *)&v81.left + 1136LL) == 3 )
        {
          v74 = 8LL * *((unsigned int *)v40 + 3);
          if ( !is_mul_ok(*((unsigned int *)v40 + 3), 8u) )
            v74 = -1;
          *((_QWORD *)v40 + 6) = operator new[](v74);
          for ( k = 0; (unsigned int)k < *((_DWORD *)v40 + 3); k = (unsigned int)(k + 1) )
          {
            v87 = (struct CVideoProcessorInputView *)(8 * k);
            *(_QWORD *)&v81.left = *(_QWORD *)(8 * k + *(_QWORD *)(v41 + 48));
            CVideoProcessor::CheckInputHazardTracking(this, *(struct CVideoProcessorInputView **)&v81.left);
            *(_QWORD *)((char *)v87 + *((_QWORD *)v40 + 6)) = *(_QWORD *)&v81.left + 288LL;
          }
        }
      }
      else
      {
        v46 = *(_QWORD *)&v81.left;
      }
      if ( *((_DWORD *)v40 + 4) )
      {
        v68 = 8LL * *((unsigned int *)v40 + 4);
        if ( !is_mul_ok(*((unsigned int *)v40 + 4), 8u) )
          v68 = -1;
        *((_QWORD *)v40 + 5) = operator new[](v68);
        for ( m = 0; (unsigned int)m < *((_DWORD *)v40 + 4); m = (unsigned int)(m + 1) )
        {
          v87 = (struct CVideoProcessorInputView *)(8 * m);
          *(_QWORD *)&v81.left = *(_QWORD *)(8 * m + *(_QWORD *)(v41 + 40));
          CVideoProcessor::CheckInputHazardTracking(this, *(struct CVideoProcessorInputView **)&v81.left);
          *(_QWORD *)((char *)v87 + *((_QWORD *)v40 + 5)) = *(_QWORD *)&v81.left + 288LL;
        }
        if ( *(_DWORD *)(*((_QWORD *)this + 52) + v46 + 1136) == 3 )
        {
          v70 = 8LL * *((unsigned int *)v40 + 4);
          if ( !is_mul_ok(*((unsigned int *)v40 + 4), 8u) )
            v70 = -1;
          *((_QWORD *)v40 + 8) = operator new[](v70);
          for ( n = 0; (unsigned int)n < *((_DWORD *)v40 + 4); n = (unsigned int)(n + 1) )
          {
            *(_QWORD *)&v81.left = *(_QWORD *)(8 * n + *(_QWORD *)(v41 + 64));
            CVideoProcessor::CheckInputHazardTracking(this, *(struct CVideoProcessorInputView **)&v81.left);
            *(_QWORD *)(8 * n + *((_QWORD *)v40 + 8)) = *(_QWORD *)&v81.left + 288LL;
          }
        }
      }
    }
    v20 = (unsigned int)(v20 + 1);
    LODWORD(v5) = v82;
  }
  v21 = v95;
  v22 = CVideoProcessor::CheckOutputHazardTracking(this, v95);
  v23 = 0;
  v138 = 0;
  if ( v22 )
  {
    v23 = this;
    v138 = this;
    v139 = *((_DWORD *)this + 76);
    v140 = *(struct tagRECT *)((char *)this + 308);
    *(struct tagRECT *)v98 = *v22;
    if ( v139 )
    {
      D3D11IntersectRect((struct tagRECT *)v98, v22, &v140);
      v23 = v138;
    }
    CVideoProcessor::SetOutputTargetRect(v23, 1, (const struct tagRECT *)v98);
  }
  if ( *((_DWORD *)this + 94) )
  {
    CVideoProcessor::SetLegacyOutputColorSpace(
      this,
      *(struct D3D11_VIDEO_PROCESSOR_COLOR_SPACE *)((char *)this + 344),
      (enum DXGI_FORMAT)*(__int16 *)(*((_QWORD *)v21 + 26) + 260LL));
    *((_DWORD *)this + 94) = 0;
  }
  v79 = *((_DWORD *)this + 93);
  v83 = *(__int16 *)(*((_QWORD *)v21 + 26) + 260LL);
  v81.left = v85;
  v84 = v88;
  v85 = v89;
  v92 = v80;
  v93 = v90;
  LODWORD(v87) = v91;
  *(_QWORD *)v98 = this;
  if ( dword_1802282A4
    && (qword_180228290 & 0x4000000000000000LL) != 0
    && (qword_180228298 & 0x4000000000000000LL) == qword_180228298 )
  {
    v141[0] = v98;
    v141[1] = 8;
    v141[2] = &v87;
    v141[3] = 4;
    v141[4] = &v93;
    v141[5] = 4;
    v141[6] = &v92;
    v141[7] = 4;
    v141[8] = &v86;
    v141[9] = 4;
    v141[10] = &v85;
    v141[11] = 4;
    v141[12] = &v84;
    v141[13] = 4;
    v141[14] = &v83;
    v141[15] = 4;
    v141[16] = &v79;
    v141[17] = 4;
    v141[18] = &v81;
    v141[19] = 4;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, ID3D11VideoContext_VideoProcessorBltParameters, 10, v141);
  }
  v24 = *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL);
  *(_QWORD *)v98 = v24;
  v25 = *(_DWORD *)(v24 + 3688);
  *(_DWORD *)&v98[8] = v25;
  v26 = *(_QWORD *)(v24 + 3692);
  *(_QWORD *)&v98[12] = v26;
  *(_DWORD *)(v24 + 3688) = GetCurrentThreadId();
  *(_BYTE *)(v24 + 3692) = 0;
  *(_WORD *)(v24 + 3693) = *(_WORD *)((char *)&v95 + 1);
  *(_BYTE *)(v24 + 3695) = BYTE3(v95);
  *(_DWORD *)(v24 + 3696) = 0;
  v27 = (char *)this + 600;
  v28 = *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL) + 40768LL;
  v29 = v82;
  v31 = (*(__int64 (__fastcall **)(__int64, char *, char *, _QWORD, unsigned int, char *))(v24 + 3280))(
          v28,
          v27,
          (char *)v95 + 288,
          v94,
          v82,
          v19);
  v32 = 1;
  if ( v31 >= 0 )
    v32 = 2;
  LOBYTE(v100) = v32;
  v80 = DXGI_FORMAT_UNKNOWN;
  if ( v29 )
  {
    v47 = 0;
    v95 = 0;
    do
    {
      v48 = (void **)&v19[72 * (_QWORD)v47];
      SmallDDIElLayout::operator delete(v48[3], v30);
      SmallDDIElLayout::operator delete(v48[5], v49);
      SmallDDIElLayout::operator delete(v48[6], v50);
      SmallDDIElLayout::operator delete(v48[8], v51);
      ++v80;
      v47 = (char *)v95 + 1;
      v95 = (struct CVideoProcessorOutputView *)((char *)v95 + 1);
    }
    while ( v80 < v82 );
  }
  SmallDDIElLayout::operator delete(v19, v30);
  *(_DWORD *)(v24 + 3688) = v25;
  *(_QWORD *)(v24 + 3692) = v26;
  if ( v23 )
    CVideoProcessor::SetOutputTargetRect(v23, v139, &v140);
  LogMarkerHelper::~LogMarkerHelper((LogMarkerHelper *)&v99);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x180035f10  push    rbx
0x180035f12  push    rsi
0x180035f13  push    rdi
0x180035f14  push    r12
0x180035f16  push    r13
0x180035f18  push    r14
0x180035f1a  push    r15
0x180035f1c  sub     rsp, 360h
0x180035f23  mov     rax, cs:__security_cookie
0x180035f2a  xor     rax, rsp
0x180035f2d  mov     [rsp+398h+var_48], rax
0x180035f35  mov     r15d, r9d
0x180035f38  mov     [rsp+398h+var_338], r15d
0x180035f3d  mov     [rsp+398h+var_2E8], r8d
0x180035f45  mov     rsi, rdx
0x180035f48  mov     [rsp+398h+var_2E0], rdx
0x180035f50  mov     rdi, rcx
0x180035f53  mov     [rsp+398h+var_2D8], r15d
0x180035f5b  mov     rax, [rsp+398h+arg_20]
0x180035f63  mov     qword ptr [rsp+398h+var_2C8.left], rax
0x180035f6b  xor     r14d, r14d
0x180035f6e  mov     [rsp+398h+var_2D0], r14
0x180035f76  mov     rax, [rcx+0A0h]
0x180035f7d  mov     rcx, [rax+438h]
0x180035f84  mov     [rsp+398h+var_2B0], rcx
0x180035f8c  mov     [rsp+398h+var_2A8], 1C01h
0x180035f96  cmp     [rdi+230h], r14d
0x180035f9d  jz      loc_1800370B7
0x180035fa3  cmp     r15d, [rdi+12Ch]
0x180035faa  ja      loc_1800370C4
0x180035fb0  test    rsi, rsi
0x180035fb3  jz      loc_1800370F5
0x180035fb9  mov     rax, [rsi+0D0h]
0x180035fc0  mov     edx, [rax+148h]
0x180035fc6  mov     [rsp+398h+var_330], edx
0x180035fca  mov     ecx, [rax+14Ch]
0x180035fd0  mov     [rsp+398h+var_328], ecx
0x180035fd4  movsx   r10d, word ptr [rax+104h]
0x180035fdc  mov     [rsp+398h+var_2F8], r10d
0x180035fe4  cmp     dword ptr [rdi+130h], 0
0x180035feb  jz      loc_180036515
0x180035ff1  movups  xmm0, xmmword ptr [rdi+134h]
0x180035ff8  movups  xmmword ptr [rsp+398h+var_348.left], xmm0
0x180035ffd  mov     rax, [rdi+13Ch]
0x180036004  cmp     edx, eax
0x180036006  jb      loc_18003705A
0x18003600c  shr     rax, 20h
0x180036010  cmp     ecx, eax
0x180036012  jb      loc_18003705A
0x180036018  lea     r9, [rsp+398h+var_348]; struct tagRECT *
0x18003601d  mov     ebx, 1
0x180036022  mov     r8d, ebx; int
0x180036025  mov     edx, r10d; enum DXGI_FORMAT
0x180036028  mov     rcx, rdi; this
0x18003602b  call    ?AdjustRectForFormat@CVideoProcessor@@UEAAHW4DXGI_FORMAT@@HPEAUtagRECT@@@Z; CVideoProcessor::AdjustRectForFormat(DXGI_FORMAT,int,tagRECT *)
0x180036030  test    eax, eax
0x180036032  jnz     loc_180037126
0x180036038  xorps   xmm0, xmm0
0x18003603b  movups  [rsp+398h+var_2A0], xmm0
0x180036043  mov     rax, [rsi]
0x180036046  lea     rdx, [rsp+398h+var_2A0]
0x18003604e  mov     rcx, rsi
0x180036051  mov     rax, [rax+40h]
0x180036055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003605a  mov     edx, dword ptr [rsp+398h+var_2A0+0Ch]
0x180036061  cmp     dword ptr [rsp+398h+var_2A0], 1
0x180036069  cmovz   edx, ebx
0x18003606c  cmp     dword ptr [rdi+170h], 0
0x180036073  jnz     loc_180036ED0
0x180036079  cmp     edx, 1
0x18003607c  jnz     loc_18003713A
0x180036082  mov     r12b, 1
0x180036085  mov     [rsp+398h+var_350], r14d
0x18003608a  mov     [rsp+398h+var_2FC], r14d
0x180036092  mov     [rsp+398h+var_300], r14d
0x18003609a  mov     [rsp+398h+var_304], r14d
0x1800360a2  mov     [rsp+398h+var_308], r14d
0x1800360aa  mov     [rsp+398h+var_320], r14d
0x1800360af  mov     [rsp+398h+var_318], 0FFFFFFFFh
0x1800360ba  mov     r13d, r14d
0x1800360bd  mov     [rsp+398h+var_358], r14d
0x1800360c2  cmp     r14d, r15d
0x1800360c5  jb      loc_180036366
0x1800360cb  cmp     r13d, [rdi+128h]
0x1800360d2  ja      loc_180037174
0x1800360d8  mov     ebx, [rsp+398h+var_358]
0x1800360dc  cmp     dword ptr [rdi+170h], 0
0x1800360e3  jnz     loc_1800371A5
0x1800360e9  cmp     cs:byte_18022B788, 0
0x1800360f0  jz      short loc_18003610B
0x1800360f2  cmp     r13d, [rdi+23Ch]
0x1800360f9  jnz     loc_180036DBF
0x1800360ff  cmp     ebx, [rdi+240h]
0x180036105  jnz     loc_180036DBF
0x18003610b  mov     ebx, r15d
0x18003610e  mov     eax, 48h ; 'H'
0x180036113  mul     rbx
0x180036116  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18003611d  cmovb   rax, r12
0x180036121  mov     rcx, rax; unsigned __int64
0x180036124  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180036129  mov     r13, rax
0x18003612c  mov     [rsp+398h+var_2D0], rax
0x180036134  lea     r8, [rbx+rbx*8]
0x180036138  shl     r8, 3; Size
0x18003613c  xor     edx, edx; Val
0x18003613e  mov     rcx, rax; void *
0x180036141  call    memset_0
0x180036146  xor     r14d, r14d
0x180036149  cmp     r14d, r15d
0x18003614c  jb      loc_180036410
0x180036152  mov     rsi, [rsp+398h+var_2E0]
0x18003615a  mov     rdx, rsi; struct CVideoProcessorOutputView *
0x18003615d  mov     rcx, rdi; this
0x180036160  call    ?CheckOutputHazardTracking@CVideoProcessor@@QEAAPEBUtagRECT@@PEAVCVideoProcessorOutputView@@@Z; CVideoProcessor::CheckOutputHazardTracking(CVideoProcessorOutputView *)
0x180036165  xor     r15d, r15d
0x180036168  mov     [rsp+398h+var_108], r15
0x180036170  test    rax, rax
0x180036173  jnz     loc_1800371DE
0x180036179  cmp     dword ptr [rdi+178h], 0
0x180036180  jz      short loc_1800361A9
0x180036182  mov     rax, [rsi+0D0h]
0x180036189  movsx   r8d, word ptr [rax+104h]; enum DXGI_FORMAT
0x180036191  mov     edx, [rdi+158h]; struct D3D11_VIDEO_PROCESSOR_COLOR_SPACE
0x180036197  mov     rcx, rdi; this
0x18003619a  call    ?SetLegacyOutputColorSpace@CVideoProcessor@@QEAAXUD3D11_VIDEO_PROCESSOR_COLOR_SPACE@@W4DXGI_FORMAT@@@Z; CVideoProcessor::SetLegacyOutputColorSpace(D3D11_VIDEO_PROCESSOR_COLOR_SPACE,DXGI_FORMAT)
0x18003619f  mov     dword ptr [rdi+178h], 0
0x1800361a9  mov     eax, [rdi+174h]
0x1800361af  mov     [rsp+398h+var_358], eax
0x1800361b3  mov     rax, [rsi+0D0h]
0x1800361ba  movsx   ecx, word ptr [rax+104h]
0x1800361c1  mov     [rsp+398h+var_330], ecx
0x1800361c5  mov     eax, [rsp+398h+var_320]
0x1800361c9  mov     [rsp+398h+var_348.left], eax
0x1800361cd  mov     ecx, [rsp+398h+var_308]
0x1800361d4  mov     [rsp+398h+var_328], ecx
0x1800361d8  mov     eax, [rsp+398h+var_304]
0x1800361df  mov     [rsp+398h+var_320], eax
0x1800361e3  mov     ecx, [rsp+398h+var_318]
0x1800361ea  mov     [rsp+398h+var_318], ecx
0x1800361f1  mov     eax, [rsp+398h+var_350]
0x1800361f5  mov     [rsp+398h+var_2F8], eax
0x1800361fc  mov     edx, [rsp+398h+var_300]
0x180036203  mov     [rsp+398h+var_2F0], edx
0x18003620a  mov     r10d, [rsp+398h+var_2FC]
0x180036212  mov     dword ptr [rsp+398h+var_310], r10d
0x18003621a  mov     qword ptr [rsp+398h+var_2C8.left], rdi
0x180036222  cmp     cs:dword_1802282A4, 0
0x180036229  jnz     loc_18003651F
0x18003622f  mov     rax, [rdi+0A0h]
0x180036236  mov     rsi, [rax+438h]
0x18003623d  mov     qword ptr [rsp+398h+var_2C8.left], rsi
0x180036245  mov     r12d, [rsi+0E68h]
0x18003624c  mov     [rsp+398h+var_2C8.right], r12d
0x180036254  mov     rbx, [rsi+0E6Ch]
0x18003625b  mov     qword ptr [rsp+398h+var_2C8.bottom], rbx
0x180036263  call    cs:__imp_GetCurrentThreadId
0x180036269  mov     [rsi+0E68h], eax
0x18003626f  mov     byte ptr [rsi+0E6Ch], 0
0x180036276  movzx   eax, word ptr [rsp+398h+var_2E0+1]
0x18003627e  mov     [rsi+0E6Dh], ax
0x180036285  movzx   eax, byte ptr [rsp+398h+var_2E0+3]
0x18003628d  mov     [rsi+0E6Fh], al
0x180036293  mov     dword ptr [rsi+0E70h], 0
0x18003629d  mov     r8, [rsp+398h+var_2E0]
0x1800362a5  add     r8, 120h
0x1800362ac  lea     rdx, [rdi+258h]
0x1800362b3  mov     rcx, [rdi+0A0h]
0x1800362ba  mov     rcx, [rcx+438h]
0x1800362c1  add     rcx, 9F40h
0x1800362c8  mov     [rsp+398h+var_370], r13
0x1800362cd  mov     edi, [rsp+398h+var_338]
0x1800362d1  mov     [rsp+398h+var_378], edi
0x1800362d5  mov     r9d, [rsp+398h+var_2E8]
0x1800362dd  mov     rax, [rsi+0CD0h]
0x1800362e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362e9  mov     r14d, eax
0x1800362ec  mov     al, 1
0x1800362ee  movzx   eax, al
0x1800362f1  mov     ecx, 2
0x1800362f6  test    r14d, r14d
0x1800362f9  cmovns  eax, ecx
0x1800362fc  mov     byte ptr [rsp+398h+var_2A8], al
0x180036303  mov     [rsp+398h+var_350], 0
0x18003630b  test    edi, edi
0x18003630d  jnz     loc_18003667D
0x180036313  mov     rcx, r13; void *
0x180036316  call    ??3SmallDDIElLayout@@KAXPEAXI@Z; SmallDDIElLayout::operator delete(void *,uint)
0x18003631b  nop
0x18003631c  mov     [rsi+0E68h], r12d
0x180036323  mov     [rsi+0E6Ch], rbx
0x18003632a  test    r15, r15
0x18003632d  jnz     loc_18003723D
0x180036333  lea     rcx, [rsp+398h+var_2B0]; this
0x18003633b  call    ??1LogMarkerHelper@@QEAA@XZ; LogMarkerHelper::~LogMarkerHelper(void)
0x180036340  mov     eax, r14d
0x180036343  mov     rcx, [rsp+398h+var_48]
0x18003634b  xor     rcx, rsp; StackCookie
0x18003634e  call    __security_check_cookie
0x180036353  add     rsp, 360h
0x18003635a  pop     r15
0x18003635c  pop     r14
0x18003635e  pop     r13
0x180036360  pop     r12
0x180036362  pop     rdi
0x180036363  pop     rsi
0x180036364  pop     rbx
0x180036365  retn
0x180036366  mov     esi, r14d
0x180036369  imul    r9, rsi, 52Ch
0x180036370  mov     qword ptr [rsp+398h+var_348.left], r9
0x180036375  mov     rbx, [rdi+1A0h]
0x18003637c  add     rbx, r9
0x18003637f  mov     ecx, [rbx+8]
0x180036382  xor     r8d, r8d
0x180036385  test    ecx, ecx
0x180036387  jnz     loc_180036A2F
0x18003638d  cmp     [rbx], r8d
0x180036390  setnz   r8b
0x180036394  inc     r8d
0x180036397  lea     rax, [rsi+rsi*8]
0x18003639b  mov     rcx, qword ptr [rsp+398h+var_2C8.left]
0x1800363a3  lea     rsi, [rcx+rax*8]
0x1800363a7  mov     edx, [rsi+4]
0x1800363aa  cmp     edx, r8d
0x1800363ad  jb      loc_1800366E3
0x1800363b3  mov     rax, [rdi+0A0h]
0x1800363ba  mov     rcx, [rax+4E0h]
0x1800363c1  mov     rax, [rcx]
0x1800363c4  mov     r8d, edx
0x1800363c7  mov     edx, 3000A4h
0x1800363cc  mov     rax, [rax+20h]
0x1800363d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363d5  nop
0x1800363d6  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800363dd  mov     [rsp+398h+pExceptionObject], rax
0x1800363e5  mov     [rsp+398h+var_260], 80070057h
0x1800363f0  xorps   xmm0, xmm0
0x1800363f3  movdqu  [rsp+398h+var_258], xmm0
0x1800363fc  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180036403  lea     rcx, [rsp+398h+pExceptionObject]; pExceptionObject
0x18003640b  call    _CxxThrowException_0
0x180036410  mov     r15d, r14d
0x180036413  lea     rax, [r14+r14*8]
0x180036417  lea     rbx, ds:0[rax*8]
0x18003641f  lea     rsi, [rbx+r13]
0x180036423  xor     edx, edx; Val
0x180036425  mov     r8d, 48h ; 'H'; Size
0x18003642b  mov     rcx, rsi; void *
0x18003642e  call    memset_0
0x180036433  add     rbx, qword ptr [rsp+398h+var_2C8.left]
0x18003643b  cmp     dword ptr [rbx], 0
0x18003643e  jz      loc_180036508
0x180036444  mov     dword ptr [rsi], 1
0x18003644a  mov     eax, [rbx+4]
0x18003644d  mov     [rsi+4], eax
0x180036450  mov     eax, [rbx+8]
0x180036453  mov     [rsi+8], eax
0x180036456  mov     eax, [rbx+0Ch]
0x180036459  mov     [rsi+0Ch], eax
0x18003645c  mov     eax, [rbx+10h]
0x18003645f  mov     [rsi+10h], eax
0x180036462  mov     r12, [rbx+20h]
0x180036466  mov     rdx, r12; struct CVideoProcessorInputView *
0x180036469  mov     rcx, rdi; this
0x18003646c  call    ?CheckInputHazardTracking@CVideoProcessor@@QEAAXPEAVCVideoProcessorInputView@@@Z; CVideoProcessor::CheckInputHazardTracking(CVideoProcessorInputView *)
0x180036471  lea     rax, [r12+120h]
0x180036479  mov     [rsi+20h], rax
0x18003647d  imul    r15, 52Ch
0x180036484  mov     qword ptr [rsp+398h+var_348.left], r15
0x180036489  mov     r8, [rdi+1A0h]
0x180036490  cmp     dword ptr [r8+r15+4E0h], 0
0x180036499  jz      short loc_1800364CE
0x18003649b  mov     rax, [r12+0D0h]
0x1800364a3  movsx   r9d, word ptr [rax+104h]; enum DXGI_FORMAT
0x1800364ab  mov     r8d, [r8+r15+4]; struct D3D11_VIDEO_PROCESSOR_COLOR_SPACE
0x1800364b0  mov     edx, r14d; unsigned int
0x1800364b3  mov     rcx, rdi; this
0x1800364b6  call    ?SetLegacyStreamColorSpace@CVideoProcessor@@QEAAXIUD3D11_VIDEO_PROCESSOR_COLOR_SPACE@@W4DXGI_FORMAT@@@Z; CVideoProcessor::SetLegacyStreamColorSpace(uint,D3D11_VIDEO_PROCESSOR_COLOR_SPACE,DXGI_FORMAT)
0x1800364bb  mov     rax, [rdi+1A0h]
0x1800364c2  mov     dword ptr [r15+rax+4E0h], 0
0x1800364ce  mov     r15, [rbx+38h]
0x1800364d2  test    r15, r15
0x1800364d5  jz      short loc_1800364ED
0x1800364d7  mov     rdx, r15; struct CVideoProcessorInputView *
0x1800364da  mov     rcx, rdi; this
0x1800364dd  call    ?CheckInputHazardTracking@CVideoProcessor@@QEAAXPEAVCVideoProcessorInputView@@@Z; CVideoProcessor::CheckInputHazardTracking(CVideoProcessorInputView *)
0x1800364e2  lea     rax, [r15+120h]
0x1800364e9  mov     [rsi+38h], rax
0x1800364ed  mov     eax, [rsi+0Ch]
0x1800364f0  test    eax, eax
0x1800364f2  jnz     loc_180036CBC
0x1800364f8  mov     r15, qword ptr [rsp+398h+var_348.left]
0x1800364fd  mov     eax, [rsi+10h]
0x180036500  test    eax, eax
0x180036502  jnz     loc_180036BBB
0x180036508  inc     r14d
0x18003650b  mov     r15d, [rsp+398h+var_338]
0x180036510  jmp     loc_180036149
0x180036515  mov     ebx, 1
  ... truncated ...
```
