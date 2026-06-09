# CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal(void)

- ea: `0x1800a1010`
- end: `0x1800a16da`
- name: `?CreateD3DVideoProcessorInternal@CxCodeVideoProcD3D12DataHandler@@MEAAJXZ`
- size: `1738`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D12DataHandler *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180054140`
- `0x1800a1010`
- `0x1800a2f08`
- `0x1800a30dc`
- `0x1800a31a4`
- `0x1800a324c`
- `0x1800a32f8`
- `0x1800be5b8`
- `0x1800beaf8`
- `0x1800d1010`

## string_xrefs

- `0x1800a15bf`: `XVP VP Command Queue`
- `0x1800a1139`: `CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal`
- `0x1800a14d1`: `CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal`
- `0x1800a1590`: `CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal`
- `0x1800a163a`: `CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal`
- `0x1800a1665`: `XVP VP Command List`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal(
        CxCodeVideoProcD3D12DataHandler *this)
{
  struct D3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT *v2; // rax
  __int64 v3; // rdx
  _OWORD *v4; // rcx
  __int64 v5; // r8
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  D3D12_VIDEO_PROCESS_FILTER_RANGE v11; // xmm0
  D3D12_VIDEO_PROCESS_FILTER_RANGE v12; // xmm1
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  _OWORD *v18; // rax
  _OWORD *v19; // rcx
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  int v32; // ebx
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  int *v36; // rbx
  enum D3D12_VIDEO_PROCESS_FEATURE_FLAGS v37; // eax
  enum D3D12_VIDEO_PROCESS_DEINTERLACE_FLAGS v38; // edi
  struct D3D12_FEATURE_DATA_VIDEO_PROCESS_REFERENCE_INFO *v39; // rax
  __int64 v40; // rcx
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  struct D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC *v43; // rax
  __int128 v44; // xmm1
  D3D12_VIDEO_SIZE_RANGE SourceSizeRange; // xmm2
  D3D12_VIDEO_SIZE_RANGE DestinationSizeRange; // xmm3
  __int128 v47; // xmm4
  __int128 v48; // xmm5
  __int128 v49; // xmm6
  BOOL v50; // eax
  const struct xvpDataHandlerState *v51; // rdx
  struct D3D12_VIDEO_PROCESS_OUTPUT_STREAM_DESC *v52; // rax
  __int128 v53; // xmm2
  __int64 v54; // r8
  __int128 v55; // xmm1
  __int128 v56; // xmm3
  __int128 v57; // xmm3
  __int128 v58; // xmm0
  __int128 v59; // xmm4
  __int128 v60; // xmm5
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, __int64, char *); // rbx
  CallStackTracing *v63; // rcx
  struct CallStackContext *v64; // rax
  __int64 v65; // rdi
  __int64 (__fastcall *v66)(__int64, _OWORD *, GUID *, char *); // rbx
  CallStackTracing *v67; // rcx
  struct CallStackContext *v68; // rax
  unsigned int v69; // r8d
  CallStackTracing *v70; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v73[8]; // [rsp+48h] [rbp-C0h] BYREF
  D3D12_FEATURE_DATA_VIDEO_PROCESS_REFERENCE_INFO v74; // [rsp+50h] [rbp-B8h] BYREF
  D3D12_VIDEO_PROCESS_OUTPUT_STREAM_DESC v75; // [rsp+80h] [rbp-88h] BYREF
  D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC v76; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v77[608]; // [rsp+128h] [rbp+20h] BYREF
  D3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT v78; // [rsp+388h] [rbp+280h] BYREF
  __int128 v79; // [rsp+5E8h] [rbp+4E0h] BYREF
  _BYTE v80[28]; // [rsp+5F8h] [rbp+4F0h]
  _OWORD v81[2]; // [rsp+618h] [rbp+510h] BYREF
  __int128 v82; // [rsp+638h] [rbp+530h]
  __int128 v83; // [rsp+648h] [rbp+540h]
  __int128 v84; // [rsp+658h] [rbp+550h]
  __int128 v85; // [rsp+668h] [rbp+560h]
  __int128 v86; // [rsp+678h] [rbp+570h]
  __int128 v87; // [rsp+688h] [rbp+580h]

  v2 = StateToD3D12Support(&v78, *((const struct xvpDataHandlerState **)this + 2));
  v3 = 4;
  v4 = v77;
  v5 = 4;
  do
  {
    v6 = *(_OWORD *)&v2->InputSample.Format.ColorSpace;
    *v4 = *(_OWORD *)&v2->NodeIndex;
    v7 = *(_OWORD *)&v2->InputFrameRate.Denominator;
    v4[1] = v6;
    v8 = *(_OWORD *)&v2->OutputFrameRate.Numerator;
    v4[2] = v7;
    v9 = *(_OWORD *)&v2->ScaleSupport.OutputSizeRange.MaxHeight;
    v4[3] = v8;
    v10 = *(_OWORD *)&v2->FeatureSupport;
    v4[4] = v9;
    v11 = v2->FilterRangeSupport[0];
    v4[5] = v10;
    v12 = v2->FilterRangeSupport[1];
    v2 = (struct D3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT *)((char *)v2 + 128);
    v4[6] = v11;
    v4[7] = v12;
    v4 += 8;
    --v5;
  }
  while ( v5 );
  v13 = *(_OWORD *)&v2->InputSample.Format.ColorSpace;
  *v4 = *(_OWORD *)&v2->NodeIndex;
  v14 = *(_OWORD *)&v2->InputFrameRate.Denominator;
  v4[1] = v13;
  v15 = *(_OWORD *)&v2->OutputFrameRate.Numerator;
  v4[2] = v14;
  v16 = *(_OWORD *)&v2->ScaleSupport.OutputSizeRange.MaxHeight;
  v4[3] = v15;
  v17 = *(_OWORD *)&v2->FeatureSupport;
  v18 = (_OWORD *)((char *)this + 3280);
  v4[4] = v16;
  v4[5] = v17;
  v19 = v77;
  do
  {
    v20 = v19[1];
    *v18 = *v19;
    v21 = v19[2];
    v18[1] = v20;
    v22 = v19[3];
    v18[2] = v21;
    v23 = v19[4];
    v18[3] = v22;
    v24 = v19[5];
    v18[4] = v23;
    v25 = v19[6];
    v18[5] = v24;
    v26 = v19[7];
    v19 += 8;
    v18[6] = v25;
    v18[7] = v26;
    v18 += 8;
    --v3;
  }
  while ( v3 );
  v27 = v19[1];
  *v18 = *v19;
  v28 = v19[2];
  v18[1] = v27;
  v29 = v19[3];
  v18[2] = v28;
  v30 = v19[4];
  v18[3] = v29;
  v31 = v19[5];
  v18[4] = v30;
  v18[5] = v31;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v73,
    "CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal",
    420);
  v32 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, __int64))(**((_QWORD **)this + 507) + 24LL))(
          *((_QWORD *)this + 507),
          5,
          (char *)this + 3280,
          608);
  if ( v32 >= 0 )
  {
    if ( (*((_BYTE *)this + 3336) & 1) != 0
      && (v36 = (int *)*((_QWORD *)this + 2),
          v37 = StateToD3D12RequiredFeatures((const struct xvpDataHandlerState *)v36),
          (v37 & *((_DWORD *)this + 840)) == v37) )
    {
      if ( v36[6] > 2 )
        v38 = *((_DWORD *)this + 841);
      else
        v38 = D3D12_VIDEO_PROCESS_DEINTERLACE_FLAG_NONE;
      v39 = StateToD3D12ReferenceInfo(&v74, (const struct xvpDataHandlerState *)v36, v38);
      v40 = *((_QWORD *)this + 507);
      v79 = *(_OWORD *)&v39->NodeIndex;
      *(_OWORD *)v80 = *(_OWORD *)&v39->InputFrameRate.Numerator;
      *(_OWORD *)&v80[12] = *(_OWORD *)&v39->OutputFrameRate.Denominator;
      v32 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v40 + 24LL))(v40, 7, &v79);
      if ( v32 >= 0 )
      {
        v43 = StateToD3D12InputDesc(
                &v76,
                *((const struct xvpDataHandlerState **)this + 2),
                v38,
                *(unsigned int *)&v80[20],
                *(unsigned int *)&v80[24]);
        v44 = *(_OWORD *)&v43->DestinationAspectRatio.Numerator;
        SourceSizeRange = v43->SourceSizeRange;
        DestinationSizeRange = v43->DestinationSizeRange;
        v47 = *(_OWORD *)&v43->EnableOrientation;
        v48 = *(_OWORD *)&v43->DeinterlaceMode;
        v49 = *(_OWORD *)&v43->LumaKey.Upper;
        *((_OWORD *)this + 243) = *(_OWORD *)&v43->Format;
        *((_OWORD *)this + 244) = v44;
        *((D3D12_VIDEO_SIZE_RANGE *)this + 245) = SourceSizeRange;
        *((D3D12_VIDEO_SIZE_RANGE *)this + 246) = DestinationSizeRange;
        *((_OWORD *)this + 247) = v47;
        *((_OWORD *)this + 248) = v48;
        *((_OWORD *)this + 249) = v49;
        v50 = *((_DWORD *)this + 999) && *((_DWORD *)this + 842);
        v51 = (const struct xvpDataHandlerState *)*((_QWORD *)this + 2);
        *((_DWORD *)this + 999) = v50;
        v52 = StateToD3D12OutputDesc(&v75, v51);
        v53 = *((_OWORD *)this + 244);
        v54 = *((_QWORD *)this + 487);
        v55 = *(_OWORD *)&v52->BackgroundColor[3];
        v56 = *(_OWORD *)&v52->Format;
        *(_OWORD *)&v74.InputFrameRate.Numerator = *(_OWORD *)v52->BackgroundColor;
        *((_OWORD *)this + 250) = v56;
        v57 = *((_OWORD *)this + 243);
        *(_OWORD *)&v74.OutputFrameRate.Denominator = v55;
        v81[1] = v57;
        *((_OWORD *)this + 251) = *(_OWORD *)&v74.InputFrameRate.Numerator;
        v83 = *((_OWORD *)this + 245);
        v58 = *((_OWORD *)this + 249);
        *(_OWORD *)((char *)this + 4028) = v55;
        v87 = v58;
        v82 = v53;
        v85 = v59;
        v86 = v60;
        v84 = *((_OWORD *)this + 246);
        if ( (_DWORD)v54 * DWORD1(v53) == (_DWORD)v53 * HIDWORD(v54) )
          *(_QWORD *)&v82 = v54;
        v61 = *((_QWORD *)this + 507);
        v62 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v61 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 4064);
        v32 = v62(v61, 1, (char *)this + 4000);
        if ( v32 >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 508) + 48LL))(
            *((_QWORD *)this + 508),
            L"XVP VP");
          v65 = *((_QWORD *)this + 506);
          v81[0] = _mm_load_si128((const __m128i *)&_xmm);
          v66 = *(__int64 (__fastcall **)(__int64, _OWORD *, GUID *, char *))(*(_QWORD *)v65 + 64LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 4224);
          v32 = v66(v65, v81, &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed, (char *)this + 4224);
          if ( v32 >= 0 )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 528) + 48LL))(
              *((_QWORD *)this + 528),
              L"XVP VP Command Queue");
            MFD3D::DX12CommandAllocatorManager::CreateAllocators(
              (CxCodeVideoProcD3D12DataHandler *)((char *)this + 4232),
              D3D12_COMMAND_LIST_TYPE_VIDEO_PROCESS,
              v69,
              *((struct ID3D12Device **)this + 506));
            v32 = MFD3D::DX12CommandListManager<ID3D12VideoProcessCommandList,5>::Create(
                    (void **)this + 540,
                    *((struct ID3D12Device **)this + 506),
                    (CxCodeVideoProcD3D12DataHandler *)((char *)this + 4232));
            if ( v32 >= 0 )
            {
              (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 540) + 48LL))(
                *((_QWORD *)this + 540),
                L"XVP VP Command List");
            }
            else
            {
              v70 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v70 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v70 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v70);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v32 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal",
                    474,
                    v32);
              }
              if ( g_wppLevels )
              {
                v35 = 19;
                goto LABEL_13;
              }
            }
          }
          else
          {
            v67 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v67 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v67 + 8) )
            {
              v68 = CallStackTracing::GetThreadRelativeContext(v67);
              if ( *((_DWORD *)v68 + 499) != v32 )
                CallStackContext::TraceFailure(
                  v68,
                  "CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal",
                  468,
                  v32);
            }
            if ( g_wppLevels )
            {
              v35 = 18;
              goto LABEL_13;
            }
          }
        }
        else
        {
          v63 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v63 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v63 + 8) )
          {
            v64 = CallStackTracing::GetThreadRelativeContext(v63);
            if ( *((_DWORD *)v64 + 499) != v32 )
              CallStackContext::TraceFailure(
                v64,
                "CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal",
                463,
                v32);
          }
          if ( g_wppLevels )
          {
            v35 = 17;
            goto LABEL_13;
          }
        }
      }
      else
      {
        v41 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v41 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext(v41);
          if ( *((_DWORD *)v42 + 499) != v32 )
            CallStackContext::TraceFailure(
              v42,
              "CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal",
              441,
              v32);
        }
        if ( g_wppLevels )
        {
          v35 = 16;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v32 = -1072861834;
    }
  }
  else
  {
    v33 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v33 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext(v33);
      if ( *((_DWORD *)v34 + 499) != v32 )
        CallStackContext::TraceFailure(
          v34,
          "CxCodeVideoProcD3D12DataHandler::CreateD3DVideoProcessorInternal",
          420,
          v32);
    }
    if ( g_wppLevels )
    {
      v35 = 15;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, WPP_dede7ec529653c28119a7df0a5ed8741_Traceguids, this, v32);
    }
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 42), 20, WPP_dede7ec529653c28119a7df0a5ed8741_Traceguids, this, v32);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v73);
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x1800a1010  mov     rax, rsp
0x1800a1013  push    rbp
0x1800a1014  push    rbx
0x1800a1015  push    rsi
0x1800a1016  push    rdi
0x1800a1017  push    r12
0x1800a1019  push    r15
0x1800a101b  lea     rbp, [rax-5E8h]
0x1800a1022  sub     rsp, 6B8h
0x1800a1029  movaps  xmmword ptr [rax-48h], xmm6
0x1800a102d  mov     rax, cs:__security_cookie
0x1800a1034  xor     rax, rsp
0x1800a1037  mov     [rbp+5E0h+var_50], rax
0x1800a103e  mov     rdx, [rcx+10h]; struct xvpDataHandlerState *
0x1800a1042  mov     rsi, rcx
0x1800a1045  lea     rcx, [rbp+5E0h+var_360]; retstr
0x1800a104c  call    ?StateToD3D12Support@@YA?AUD3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT@@PEBUxvpDataHandlerState@@@Z; StateToD3D12Support(xvpDataHandlerState const *)
0x1800a1051  mov     edx, 4
0x1800a1056  lea     rcx, [rbp+5E0h+var_5C0]
0x1800a105a  mov     r8d, edx
0x1800a105d  lea     r9d, [rdx+7Ch]
0x1800a1061  movups  xmm0, xmmword ptr [rax]
0x1800a1064  movups  xmm1, xmmword ptr [rax+10h]
0x1800a1068  movups  xmmword ptr [rcx], xmm0
0x1800a106b  movups  xmm0, xmmword ptr [rax+20h]
0x1800a106f  movups  xmmword ptr [rcx+10h], xmm1
0x1800a1073  movups  xmm1, xmmword ptr [rax+30h]
0x1800a1077  movups  xmmword ptr [rcx+20h], xmm0
0x1800a107b  movups  xmm0, xmmword ptr [rax+40h]
0x1800a107f  movups  xmmword ptr [rcx+30h], xmm1
0x1800a1083  movups  xmm1, xmmword ptr [rax+50h]
0x1800a1087  movups  xmmword ptr [rcx+40h], xmm0
0x1800a108b  movups  xmm0, xmmword ptr [rax+60h]
0x1800a108f  movups  xmmword ptr [rcx+50h], xmm1
0x1800a1093  movups  xmm1, xmmword ptr [rax+70h]
0x1800a1097  add     rax, r9
0x1800a109a  movups  xmmword ptr [rcx+60h], xmm0
0x1800a109e  movups  xmmword ptr [rcx+70h], xmm1
0x1800a10a2  add     rcx, r9
0x1800a10a5  sub     r8, 1
0x1800a10a9  jnz     short loc_1800A1061
0x1800a10ab  movups  xmm0, xmmword ptr [rax]
0x1800a10ae  lea     rbx, [rsi+0CD0h]
0x1800a10b5  movups  xmm1, xmmword ptr [rax+10h]
0x1800a10b9  movups  xmmword ptr [rcx], xmm0
0x1800a10bc  movups  xmm0, xmmword ptr [rax+20h]
0x1800a10c0  movups  xmmword ptr [rcx+10h], xmm1
0x1800a10c4  movups  xmm1, xmmword ptr [rax+30h]
0x1800a10c8  movups  xmmword ptr [rcx+20h], xmm0
0x1800a10cc  movups  xmm0, xmmword ptr [rax+40h]
0x1800a10d0  movups  xmmword ptr [rcx+30h], xmm1
0x1800a10d4  movups  xmm1, xmmword ptr [rax+50h]
0x1800a10d8  mov     rax, rbx
0x1800a10db  movups  xmmword ptr [rcx+40h], xmm0
0x1800a10df  movups  xmmword ptr [rcx+50h], xmm1
0x1800a10e3  lea     rcx, [rbp+5E0h+var_5C0]
0x1800a10e7  movups  xmm0, xmmword ptr [rcx]
0x1800a10ea  movups  xmm1, xmmword ptr [rcx+10h]
0x1800a10ee  movups  xmmword ptr [rax], xmm0
0x1800a10f1  movups  xmm0, xmmword ptr [rcx+20h]
0x1800a10f5  movups  xmmword ptr [rax+10h], xmm1
0x1800a10f9  movups  xmm1, xmmword ptr [rcx+30h]
0x1800a10fd  movups  xmmword ptr [rax+20h], xmm0
0x1800a1101  movups  xmm0, xmmword ptr [rcx+40h]
0x1800a1105  movups  xmmword ptr [rax+30h], xmm1
0x1800a1109  movups  xmm1, xmmword ptr [rcx+50h]
0x1800a110d  movups  xmmword ptr [rax+40h], xmm0
0x1800a1111  movups  xmm0, xmmword ptr [rcx+60h]
0x1800a1115  movups  xmmword ptr [rax+50h], xmm1
0x1800a1119  movups  xmm1, xmmword ptr [rcx+70h]
0x1800a111d  add     rcx, r9
0x1800a1120  movups  xmmword ptr [rax+60h], xmm0
0x1800a1124  movups  xmmword ptr [rax+70h], xmm1
0x1800a1128  add     rax, r9
0x1800a112b  sub     rdx, 1
0x1800a112f  jnz     short loc_1800A10E7
0x1800a1131  movups  xmm0, xmmword ptr [rcx]
0x1800a1134  mov     edi, 1A4h
0x1800a1139  lea     r15, aCxcodevideopro_131; "CxCodeVideoProcD3D12DataHandler::Create"...
0x1800a1140  movups  xmm1, xmmword ptr [rcx+10h]
0x1800a1144  mov     r8d, edi; int
0x1800a1147  mov     rdx, r15; char *
0x1800a114a  movups  xmmword ptr [rax], xmm0
0x1800a114d  movups  xmm0, xmmword ptr [rcx+20h]
0x1800a1151  movups  xmmword ptr [rax+10h], xmm1
0x1800a1155  movups  xmm1, xmmword ptr [rcx+30h]
0x1800a1159  movups  xmmword ptr [rax+20h], xmm0
0x1800a115d  movups  xmm0, xmmword ptr [rcx+40h]
0x1800a1161  movups  xmmword ptr [rax+30h], xmm1
0x1800a1165  movups  xmm1, xmmword ptr [rcx+50h]
0x1800a1169  lea     rcx, [rsp+6E0h+var_6A0]; this
0x1800a116e  movups  xmmword ptr [rax+40h], xmm0
0x1800a1172  movups  xmmword ptr [rax+50h], xmm1
0x1800a1176  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a117b  mov     rcx, [rsi+0FD8h]
0x1800a1182  mov     r9d, 260h
0x1800a1188  mov     r8, rbx
0x1800a118b  mov     edx, 5
0x1800a1190  mov     rax, [rcx]
0x1800a1193  mov     rax, [rax+18h]
0x1800a1197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a119c  mov     ebx, eax
0x1800a119e  test    eax, eax
0x1800a11a0  jns     short loc_1800A1213
0x1800a11a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a11a9  test    rcx, rcx
0x1800a11ac  jnz     short loc_1800A11BA
0x1800a11ae  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a11b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a11ba  cmp     byte ptr [rcx+8], 0
0x1800a11be  jz      short loc_1800A11DE
0x1800a11c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a11c5  cmp     [rax+7CCh], ebx
0x1800a11cb  jz      short loc_1800A11DE
0x1800a11cd  mov     r9d, ebx; int
0x1800a11d0  mov     r8d, edi; int
0x1800a11d3  mov     rdx, r15; char *
0x1800a11d6  mov     rcx, rax; this
0x1800a11d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a11de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a11e5  jb      loc_1800A1678
0x1800a11eb  mov     edx, 0Fh
0x1800a11f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a11f7  lea     r8, WPP_dede7ec529653c28119a7df0a5ed8741_Traceguids
0x1800a11fe  mov     r9, rsi
0x1800a1201  mov     [rsp+6E0h+var_6C0], ebx
0x1800a1205  mov     rcx, [rcx+10h]
0x1800a1209  call    WPP_SF_qD
0x1800a120e  jmp     loc_1800A1678
0x1800a1213  test    byte ptr [rsi+0D08h], 1
0x1800a121a  jnz     short loc_1800A1226
0x1800a121c  mov     ebx, 0C00D6D76h
0x1800a1221  jmp     loc_1800A1678
0x1800a1226  mov     rbx, [rsi+10h]
0x1800a122a  mov     rcx, rbx; struct xvpDataHandlerState *
0x1800a122d  call    ?StateToD3D12RequiredFeatures@@YA?AW4D3D12_VIDEO_PROCESS_FEATURE_FLAGS@@PEBUxvpDataHandlerState@@@Z; StateToD3D12RequiredFeatures(xvpDataHandlerState const *)
0x1800a1232  mov     ecx, [rsi+0D20h]
0x1800a1238  and     ecx, eax
0x1800a123a  cmp     ecx, eax
0x1800a123c  jnz     short loc_1800A121C
0x1800a123e  cmp     dword ptr [rbx+18h], 2
0x1800a1242  jg      short loc_1800A1248
0x1800a1244  xor     edi, edi
0x1800a1246  jmp     short loc_1800A124E
0x1800a1248  mov     edi, [rsi+0D24h]
0x1800a124e  mov     r8d, edi; enum D3D12_VIDEO_PROCESS_DEINTERLACE_FLAGS
0x1800a1251  lea     rcx, [rsp+6E0h+var_698]; retstr
0x1800a1256  mov     rdx, rbx; struct xvpDataHandlerState *
0x1800a1259  call    ?StateToD3D12ReferenceInfo@@YA?AUD3D12_FEATURE_DATA_VIDEO_PROCESS_REFERENCE_INFO@@PEBUxvpDataHandlerState@@W4D3D12_VIDEO_PROCESS_DEINTERLACE_FLAGS@@@Z; StateToD3D12ReferenceInfo(xvpDataHandlerState const *,D3D12_VIDEO_PROCESS_DEINTERLACE_FLAGS)
0x1800a125e  mov     rcx, [rsi+0FD8h]
0x1800a1265  lea     r8, [rbp+5E0h+var_100]
0x1800a126c  mov     r9d, 2Ch ; ','
0x1800a1272  movups  xmm1, xmmword ptr [rax]
0x1800a1275  lea     edx, [r9-25h]
0x1800a1279  movups  [rbp+5E0h+var_100], xmm1
0x1800a1280  movups  xmm0, xmmword ptr [rax+10h]
0x1800a1284  movups  [rbp+5E0h+var_F0], xmm0
0x1800a128b  movups  xmm1, xmmword ptr [rax+1Ch]
0x1800a128f  movups  [rbp+5E0h+var_F0+0Ch], xmm1
0x1800a1296  mov     rax, [rcx]
0x1800a1299  mov     rax, [rax+18h]
0x1800a129d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a12a2  mov     ebx, eax
0x1800a12a4  test    eax, eax
0x1800a12a6  jns     short loc_1800A12FE
0x1800a12a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a12af  test    rcx, rcx
0x1800a12b2  jnz     short loc_1800A12C0
0x1800a12b4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a12b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a12c0  cmp     byte ptr [rcx+8], 0
0x1800a12c4  jz      short loc_1800A12E7
0x1800a12c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a12cb  cmp     [rax+7CCh], ebx
0x1800a12d1  jz      short loc_1800A12E7
0x1800a12d3  mov     r9d, ebx; int
0x1800a12d6  mov     r8d, 1B9h; int
0x1800a12dc  mov     rdx, r15; char *
0x1800a12df  mov     rcx, rax; this
0x1800a12e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a12e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a12ee  jb      loc_1800A1678
0x1800a12f4  mov     edx, 10h
0x1800a12f9  jmp     loc_1800A11F0
0x1800a12fe  mov     eax, [rbp+5E0h+var_D8]
0x1800a1304  lea     rcx, [rbp+5E0h+var_638]; retstr
0x1800a1308  mov     rdx, [rsi+10h]; struct xvpDataHandlerState *
0x1800a130c  mov     r8d, edi; enum D3D12_VIDEO_PROCESS_DEINTERLACE_FLAGS
0x1800a130f  mov     r9d, [rbp+5E0h+var_DC]; unsigned int
0x1800a1316  mov     [rsp+6E0h+var_6C0], eax; unsigned int
0x1800a131a  call    ?StateToD3D12InputDesc@@YA?AUD3D12_VIDEO_PROCESS_INPUT_STREAM_DESC@@PEBUxvpDataHandlerState@@W4D3D12_VIDEO_PROCESS_DEINTERLACE_FLAGS@@II@Z; StateToD3D12InputDesc(xvpDataHandlerState const *,D3D12_VIDEO_PROCESS_DEINTERLACE_FLAGS,uint,uint)
0x1800a131f  movups  xmm0, xmmword ptr [rax]
0x1800a1322  movups  xmm1, xmmword ptr [rax+10h]
0x1800a1326  movups  xmm2, xmmword ptr [rax+20h]
0x1800a132a  movups  xmm3, xmmword ptr [rax+30h]
0x1800a132e  movups  xmm4, xmmword ptr [rax+40h]
0x1800a1332  movups  xmm5, xmmword ptr [rax+50h]
0x1800a1336  movups  xmm6, xmmword ptr [rax+60h]
0x1800a133a  movups  xmmword ptr [rsi+0F30h], xmm0
0x1800a1341  movups  xmmword ptr [rsi+0F40h], xmm1
0x1800a1348  movups  xmmword ptr [rsi+0F50h], xmm2
0x1800a134f  movups  xmmword ptr [rsi+0F60h], xmm3
0x1800a1356  movups  xmmword ptr [rsi+0F70h], xmm4
0x1800a135d  movups  xmmword ptr [rsi+0F80h], xmm5
0x1800a1364  movups  xmmword ptr [rsi+0F90h], xmm6
0x1800a136b  cmp     dword ptr [rsi+0F9Ch], 0
0x1800a1372  jz      short loc_1800A1384
0x1800a1374  cmp     dword ptr [rsi+0D28h], 0
0x1800a137b  jz      short loc_1800A1384
0x1800a137d  mov     eax, 1
0x1800a1382  jmp     short loc_1800A1386
0x1800a1384  xor     eax, eax
0x1800a1386  mov     rdx, [rsi+10h]; struct xvpDataHandlerState *
0x1800a138a  lea     rcx, [rsp+6E0h+var_668]; retstr
0x1800a138f  mov     [rsi+0F9Ch], eax
0x1800a1395  call    ?StateToD3D12OutputDesc@@YA?AUD3D12_VIDEO_PROCESS_OUTPUT_STREAM_DESC@@PEBUxvpDataHandlerState@@@Z; StateToD3D12OutputDesc(xvpDataHandlerState const *)
0x1800a139a  movups  xmm2, xmmword ptr [rsi+0F40h]
0x1800a13a1  mov     r8, [rsi+0F38h]
0x1800a13a8  lea     r12, [rsi+0FA0h]
0x1800a13af  movups  xmm0, xmmword ptr [rax+10h]
0x1800a13b3  movups  xmm1, xmmword ptr [rax+1Ch]
0x1800a13b7  movups  xmm3, xmmword ptr [rax]
0x1800a13ba  mov     rax, r8
0x1800a13bd  movups  xmmword ptr [rsp+6E0h+var_698.InputFrameRate.Numerator], xmm0
0x1800a13c2  shr     rax, 20h
0x1800a13c6  movups  xmmword ptr [r12], xmm3
0x1800a13cb  movups  xmm3, xmmword ptr [rsi+0F30h]
0x1800a13d2  movups  xmmword ptr [rsp+6E0h+var_698.OutputFrameRate.Denominator], xmm1
0x1800a13d7  movups  xmm0, xmmword ptr [rsp+6E0h+var_698.InputFrameRate.Numerator]
0x1800a13dc  movq    rcx, xmm2
0x1800a13e1  movaps  [rbp+5E0h+var_C0], xmm3
0x1800a13e8  movups  xmmword ptr [r12+10h], xmm0
0x1800a13ee  mov     rdx, rcx
0x1800a13f1  movups  xmm0, xmmword ptr [rsi+0F50h]
0x1800a13f8  shr     rdx, 20h
0x1800a13fc  imul    edx, r8d
0x1800a1400  imul    eax, ecx
0x1800a1403  movaps  [rbp+5E0h+var_A0], xmm0
0x1800a140a  movups  xmm0, xmmword ptr [rsi+0F90h]
0x1800a1411  movups  xmmword ptr [r12+1Ch], xmm1
0x1800a1417  movaps  [rbp+5E0h+var_60], xmm0
0x1800a141e  movaps  [rbp+5E0h+var_B0], xmm2
0x1800a1425  movaps  [rbp+5E0h+var_80], xmm4
0x1800a142c  movaps  [rbp+5E0h+var_70], xmm5
0x1800a1433  movups  xmm1, xmmword ptr [rsi+0F60h]
0x1800a143a  movaps  [rbp+5E0h+var_90], xmm1
0x1800a1441  cmp     edx, eax
0x1800a1443  jnz     short loc_1800A144C
0x1800a1445  mov     qword ptr [rbp+5E0h+var_B0], r8
0x1800a144c  mov     rdi, [rsi+0FD8h]
0x1800a1453  lea     r15, [rsi+0FE0h]
0x1800a145a  mov     rcx, r15
0x1800a145d  mov     rax, [rdi]
0x1800a1460  mov     rbx, [rax+30h]
0x1800a1464  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a1469  lea     rax, _GUID_304fdb32_bede_410a_8545_943ac6a46138
0x1800a1470  mov     [rsp+30h], r15
0x1800a1475  mov     [rsp+6E0h+var_6B8], rax
0x1800a147a  mov     r9d, 1
0x1800a1480  lea     rax, [rbp+5E0h+var_C0]
0x1800a1487  mov     r8, r12
0x1800a148a  mov     qword ptr [rsp+6E0h+var_6C0], rax
0x1800a148f  mov     edx, r9d
0x1800a1492  mov     rax, rbx
0x1800a1495  mov     rcx, rdi
0x1800a1498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a149d  mov     ebx, eax
0x1800a149f  test    eax, eax
0x1800a14a1  jns     short loc_1800A14FD
0x1800a14a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a14aa  test    rcx, rcx
0x1800a14ad  jnz     short loc_1800A14BB
0x1800a14af  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a14b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a14bb  cmp     byte ptr [rcx+8], 0
0x1800a14bf  jz      short loc_1800A14E6
0x1800a14c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a14c6  cmp     [rax+7CCh], ebx
0x1800a14cc  jz      short loc_1800A14E6
0x1800a14ce  mov     r9d, ebx; int
0x1800a14d1  lea     rdx, aCxcodevideopro_131; "CxCodeVideoProcD3D12DataHandler::Create"...
0x1800a14d8  mov     r8d, 1CFh; int
0x1800a14de  mov     rcx, rax; this
0x1800a14e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a14e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a14ed  jb      loc_1800A1678
0x1800a14f3  mov     edx, 11h
0x1800a14f8  jmp     loc_1800A11F0
0x1800a14fd  mov     rcx, [r15]
0x1800a1500  lea     rdx, aXvpVp; "XVP VP"
0x1800a1507  mov     rax, [rcx]
0x1800a150a  mov     rax, [rax+30h]
0x1800a150e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1513  mov     rdi, [rsi+0FD0h]
0x1800a151a  lea     r15, [rsi+1080h]
0x1800a1521  movdqa  xmm0, cs:__xmm@00000000000000000000000000000005
0x1800a1529  mov     rcx, r15
0x1800a152c  movdqu  [rbp+5E0h+var_D0], xmm0
0x1800a1534  mov     rax, [rdi]
0x1800a1537  mov     rbx, [rax+40h]
  ... truncated ...
```
