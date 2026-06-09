# MotionTurboJpeg::CMJPGMFTDataHandler::DoProcessSample(ulong,IMFSample * *,ulong *,ulong *)

- ea: `0x18001ef40`
- end: `0x18001fca7`
- name: `?DoProcessSample@CMJPGMFTDataHandler@MotionTurboJpeg@@UEAAJKPEAPEAUIMFSample@@PEAK1@Z`
- size: `3431`
- prototype: `__int64 __fastcall(MotionTurboJpeg::CMJPGMFTDataHandler *this, __int64, struct IMFSample **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callees

- `0x18001c990`
- `0x18001ef40`
- `0x18001ff0c`
- `0x180024220`
- `0x180024dec`
- `0x18003d58c`
- `0x18003e42c`
- `0x180042f08`
- `0x1800431b8`
- `0x18004451c`
- `0x1800445c8`
- `0x1800448bc`
- `0x180044b18`
- `0x180044d78`
- `0x180044db8`
- `0x180044e70`
- `0x180045060`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f367`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f37e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f37e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fc3a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fc3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f1b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f1b4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f4d2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f554`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f6ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f7fd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f4d2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f554`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f6ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f7fd`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001f4b9`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001f572`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001f694`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001f81c`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001f4b9`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001f572`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001f694`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001f81c`
- `MFPlat!MFCalculateImageSize` at `0x18001f90b`
- `MFPlat!MFCalculateImageSize` at `0x18001f90b`
- `bcrypt!BCryptGenRandom` at `0x18001f16e`
- `bcrypt!BCryptGenRandom` at `0x18001f16e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MotionTurboJpeg::CMJPGMFTDataHandler::DoProcessSample(
        MotionTurboJpeg::CMJPGMFTDataHandler *this,
        __int64 a2,
        struct IMFSample **a3,
        unsigned int *a4)
{
  BOOL v5; // r10d
  unsigned int v7; // r9d
  unsigned int v8; // r12d
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  __int64 v13; // rcx
  signed int updated; // ebx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  GUID *v18; // rax
  unsigned __int16 *v19; // rsi
  NTSTATUS v20; // eax
  __int64 v21; // r8
  int v22; // ebx
  int *v23; // r14
  __int64 v24; // rbx
  DWORD CurrentProcessId; // eax
  int v26; // eax
  int *v27; // rax
  int *v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  DWORD v31; // ecx
  CameraTrustlet **v32; // r14
  signed int LastError; // eax
  void *MjpegSession; // rax
  __int64 v35; // rcx
  signed int v36; // eax
  LARGE_INTEGER v37; // rcx
  LARGE_INTEGER v38; // rbx
  __int64 v39; // rcx
  __int64 (__fastcall *v40)(LARGE_INTEGER, GUID *, __int64 *); // rsi
  __int64 Time; // r14
  CameraTrustlet *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rbx
  __int64 (__fastcall *v45)(__int64, _QWORD *); // rsi
  __int64 v46; // rbx
  ULONGLONG v47; // rsi
  __int64 v48; // r14
  __int64 v49; // rdx
  __int64 v50; // r9
  __int64 v51; // rcx
  __int64 v52; // rcx
  char *v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r9
  __int64 v56; // rcx
  HRESULT v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rcx
  unsigned int v60; // r12d
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  unsigned __int16 *UserDataCount; // [rsp+28h] [rbp-E0h]
  unsigned int v68; // [rsp+38h] [rbp-D0h]
  __int64 v69; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+60h] [rbp-A8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v72[2]; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v73[2]; // [rsp+78h] [rbp-90h] BYREF
  UCHAR pbBuffer[16]; // [rsp+88h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-70h] BYREF
  __int128 v76; // [rsp+A8h] [rbp-60h] BYREF
  struct _GUID v77; // [rsp+B8h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C8h] [rbp-40h] BYREF
  char *v79; // [rsp+D8h] [rbp-30h]
  int v80; // [rsp+E0h] [rbp-28h]
  int v81; // [rsp+E4h] [rbp-24h]
  __int64 *v82; // [rsp+E8h] [rbp-20h]
  __int64 v83; // [rsp+F0h] [rbp-18h]

  v5 = *((_QWORD *)this + 73) > *((_QWORD *)this + 74);
  *((_QWORD *)this + 73) = 0;
  v7 = *((_DWORD *)this + 156);
  v8 = 0;
  v10 = *((unsigned int *)this + 155);
  v11 = *((unsigned int *)this + 154);
  v73[0] = 0;
  v12 = v10 * v7 % v11;
  v13 = *((_QWORD *)this + 2);
  v72[1] = 0;
  *((_DWORD *)this + 150) = v5 || v12 > v10;
  *((_DWORD *)this + 156) = v7 + 1;
  if ( v5 || v12 > v10 )
  {
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      *((_QWORD *)this + 2) = 0;
    }
    ++*((_DWORD *)this + 157);
    updated = -1072861838;
    goto LABEL_140;
  }
  updated = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v13 + 320LL))(v13, 0, v73);
  if ( updated )
  {
LABEL_139:
    if ( updated >= 0 )
      goto LABEL_142;
    goto LABEL_140;
  }
  v69 = 0;
  v15 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v73[0])(
          v73[0],
          &GUID_c1209904_e584_4752_a2d6_7f21693f8b21,
          &v69);
  v16 = v73[0];
  if ( v15 >= 0 )
  {
    v72[0] = 0;
    v72[1] = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v73[0] + 56LL))(v73[0], v72) )
    {
      v17 = v69;
      if ( !v69 )
        goto LABEL_142;
      goto LABEL_9;
    }
    if ( *((_QWORD *)this + 81) )
      goto LABEL_56;
    v18 = (GUID *)operator new(0xE8u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = (unsigned __int16 *)v18;
    if ( !v18 )
    {
      v31 = 8;
      goto LABEL_49;
    }
    v18[1] = GUID_00000000_0000_0000_0000_000000000000;
    if ( (unsigned __int8)byte_18009D825 >= 8u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, v18);
      if ( (unsigned __int8)byte_18009D825 >= 8u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, v19);
        if ( (unsigned __int8)byte_18009D825 >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 38, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, v19);
      }
    }
    *(_QWORD *)pbBuffer = 0;
    v20 = BCryptGenRandom(0, pbBuffer, 8u, 2u);
    v22 = v20 | 0x10000000;
    if ( v20 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids,
          v19,
          v20 | 0x10000000);
      v23 = (int *)(v19 + 16);
LABEL_23:
      if ( byte_18009D825 )
      {
        v27 = &dword_1800912B4;
        if ( v23 )
          v27 = v23;
        WPP_SF_qDS(*((_QWORD *)WPP_GLOBAL_Control + 27), 41, v21, (_DWORD)v19, v22, (__int64)v27);
      }
      if ( g_wppLevels )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, v19, v22);
      goto LABEL_40;
    }
    v24 = *(_QWORD *)pbBuffer;
    CurrentProcessId = GetCurrentProcessId();
    v23 = (int *)(v19 + 16);
    v26 = StringCchPrintfW(v19 + 16, 0x64u, L"FsIso_%u_%I64u", CurrentProcessId, v24);
    v22 = v26;
    if ( v26 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, v19, v26);
      goto LABEL_23;
    }
    if ( (unsigned __int8)byte_18009D825 >= 8u )
    {
      v28 = &dword_1800912B4;
      if ( v19 != (unsigned __int16 *)-32LL )
        v28 = (int *)(v19 + 16);
      WPP_SF_qDS(*((_QWORD *)WPP_GLOBAL_Control + 27), 42, v21, (_DWORD)v19, v22, (__int64)v28);
    }
    v29 = CameraTrustlet::LaunchProcess((CameraTrustlet *)v19);
    v22 = v29;
    if ( v29 >= 0 )
    {
      v29 = CameraTrustlet::EstablishRpcConnection((RPC_BINDING_HANDLE *)v19);
      v22 = v29;
      if ( v29 >= 0 )
      {
        if ( (unsigned __int8)byte_18009D825 >= 8u )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 22, v21, v19, v29);
        v32 = (CameraTrustlet **)((char *)this + 640);
        *((_QWORD *)this + 80) = v19;
LABEL_52:
        if ( !*v32 )
        {
          updated = -2147024809;
LABEL_136:
          v58 = v69;
LABEL_137:
          if ( v58 )
          {
            v69 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
          goto LABEL_139;
        }
        MjpegSession = CameraTrustlet::CreateMjpegSession(*v32);
        *((_QWORD *)this + 81) = MjpegSession;
        if ( !MjpegSession )
        {
          updated = -2147418113;
          goto LABEL_136;
        }
LABEL_56:
        *(_QWORD *)&EventDescriptor.Id = 0;
        EventDescriptor.Keyword = 0;
        v76 = 0u;
        v70 = 0;
        updated = (*(__int64 (__fastcall **)(__int64, EVENT_DESCRIPTOR *))(*(_QWORD *)v69 + 24LL))(
                    v69,
                    &EventDescriptor);
        if ( updated )
        {
LABEL_134:
          v64 = v70;
          if ( v70 )
          {
            v70 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
          }
          goto LABEL_136;
        }
        v35 = (__int64)*a3;
        PerformanceCount.QuadPart = 0;
        v36 = (*(__int64 (__fastcall **)(__int64, _QWORD, LARGE_INTEGER *))(*(_QWORD *)v35 + 320LL))(
                v35,
                0,
                &PerformanceCount);
        v37 = PerformanceCount;
        updated = v36;
        if ( !v36 )
        {
          updated = (*(__int64 (__fastcall **)(LARGE_INTEGER, unsigned int *))(*(_QWORD *)PerformanceCount.QuadPart
                                                                             + 56LL))(
                      PerformanceCount,
                      &v72[1]);
          if ( updated )
          {
            v37 = PerformanceCount;
            goto LABEL_132;
          }
          v38 = PerformanceCount;
          v39 = v70;
          v40 = **(__int64 (__fastcall ***)(LARGE_INTEGER, GUID *, __int64 *))PerformanceCount.QuadPart;
          if ( v70 )
          {
            v70 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          }
          updated = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v40)(
                      (LARGE_INTEGER)v38.QuadPart,
                      &GUID_c1209904_e584_4752_a2d6_7f21693f8b21,
                      &v70);
          if ( updated )
            goto LABEL_131;
          updated = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v70 + 24LL))(v70, &v76);
          if ( updated )
            goto LABEL_131;
          Time = (int)timeGetTime();
          if ( *((_BYTE *)this + 688) )
            QueryPerformanceCounter((LARGE_INTEGER *)this + 88);
          v42 = (CameraTrustlet *)*((_QWORD *)this + 80);
          if ( v42 )
          {
            v68 = *((_DWORD *)this + 124);
            *(_OWORD *)pbBuffer = v76;
            v77 = (struct _GUID)EventDescriptor;
            updated = CameraTrustlet::DecodeOneMJPGFrameSecure(
                        v42,
                        (char *)this + 496,
                        &v77,
                        v72[0],
                        v72[1],
                        (struct tagBITMAPINFOHEADER *)((char *)this + 496),
                        v68,
                        (struct _GUID *)pbBuffer,
                        (struct tagBITMAPINFOHEADER *)((char *)this + 536),
                        (unsigned int *)this + 134);
          }
          else
          {
            updated = -2147024809;
          }
          if ( *((_BYTE *)this + 688) )
          {
            *(_QWORD *)pbBuffer = 0;
            QueryPerformanceCounter((LARGE_INTEGER *)pbBuffer);
            *((_QWORD *)this + 87) += *(_QWORD *)pbBuffer - *((_QWORD *)this + 88);
            ++*((_DWORD *)this + 173);
          }
          *((_QWORD *)this + 74) = 10000 * ((int)timeGetTime() - Time);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix>::GetImpl'::`2'::impl)
            && (*(unsigned int (__fastcall **)(LARGE_INTEGER, _QWORD))(*(_QWORD *)PerformanceCount.QuadPart + 48LL))(
                 PerformanceCount,
                 *(unsigned int *)(*((_QWORD *)this + 1) + 92LL)) )
          {
LABEL_131:
            v37 = PerformanceCount;
          }
          else
          {
            v37 = PerformanceCount;
            if ( !updated )
            {
              if ( PerformanceCount.QuadPart )
              {
                PerformanceCount.QuadPart = 0;
                (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v37.QuadPart + 16LL))(v37);
              }
              v43 = v70;
              if ( v70 )
              {
                v70 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              }
              goto LABEL_110;
            }
          }
        }
LABEL_132:
        if ( v37.QuadPart )
        {
          PerformanceCount.QuadPart = 0;
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v37.QuadPart + 16LL))(v37);
        }
        goto LABEL_134;
      }
      if ( !g_wppLevels )
        goto LABEL_40;
      v30 = 20;
    }
    else
    {
      if ( !g_wppLevels )
      {
LABEL_40:
        if ( byte_18009D825 )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 21, v21, v19, v22);
        v31 = (unsigned __int16)v22;
        if ( (v22 & 0x1FFF0000) != 0x70000 )
          v31 = v22;
LABEL_49:
        SetLastError(v31);
        v32 = (CameraTrustlet **)((char *)this + 640);
        *((_QWORD *)this + 80) = 0;
        LastError = GetLastError();
        updated = LastError;
        if ( LastError > 0 )
          updated = (unsigned __int16)LastError | 0x80070000;
        if ( updated )
          goto LABEL_136;
        goto LABEL_52;
      }
      v30 = 19;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, v19, v29);
    goto LABEL_40;
  }
  v44 = *((_QWORD *)this + 2);
  v45 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v44 + 328LL);
  if ( v73[0] )
  {
    v73[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  updated = v45(v44, v73);
  if ( updated )
    goto LABEL_136;
  *(_QWORD *)pbBuffer = 0;
  LODWORD(v70) = 0;
  updated = (*(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, __int64 *))(*(_QWORD *)v73[0] + 24LL))(
              v73[0],
              pbBuffer,
              0,
              &v70);
  if ( updated )
    goto LABEL_136;
  v72[0] = 0;
  (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v73[0] + 40LL))(v73[0], v72);
  v46 = v72[0];
  v47 = *(_QWORD *)pbBuffer;
  v48 = (int)timeGetTime();
  if ( *((_BYTE *)this + 688) )
    QueryPerformanceCounter((LARGE_INTEGER *)this + 88);
  v49 = *((_QWORD *)this + 79);
  UserDataCount = (unsigned __int16 *)((char *)this + 536);
  *(_QWORD *)&EventDescriptor.Id = v46;
  EventDescriptor.Keyword = v47;
  updated = MotionTurboJpeg::CMJPGMFTDataHandler::DecodeOneMJPGFrame(this, v49, (char *)this + 496, &EventDescriptor);
  if ( updated )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled() )
      LogMjpegDecoderTelemetryError(
        (MotionTurboJpeg::CMJPGMFTDataHandler *)((char *)this + 736),
        v53,
        updated,
        *(_DWORD *)(*((_QWORD *)this + 79) + 48LL),
        UserDataCount);
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled() )
  {
    v51 = *((_QWORD *)this + 91);
    if ( !v51
      || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 320LL))(
            v51,
            MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
    {
      v52 = *((_QWORD *)this + 79);
      if ( v52 != -776 )
      {
        *(_QWORD *)&EventDescriptor.Id = 0;
        LOBYTE(v50) = 1;
        EventDescriptor.Id = *(_WORD *)(v52 + 232);
        EventDescriptor.Version = *(_BYTE *)(v52 + 784);
        EventDescriptor.Channel = *(_BYTE *)(v52 + 788);
        EventDescriptor.Level = *(_BYTE *)(v52 + 880);
        EventDescriptor.Opcode = *(_BYTE *)(v52 + 884);
        LOBYTE(EventDescriptor.Task) = *(_BYTE *)(v52 + 976);
        HIBYTE(EventDescriptor.Task) = *(_BYTE *)(v52 + 980);
        LOBYTE(EventDescriptor.Keyword) = *(_BYTE *)(v52 + 456);
        LOBYTE(UserDataCount) = 1;
        (*(void (__fastcall **)(char *, __int64, EVENT_DESCRIPTOR *, __int64, unsigned __int16 *))(*((_QWORD *)this + 92)
                                                                                                 + 56LL))(
          (char *)this + 736,
          2,
          &EventDescriptor,
          v50,
          UserDataCount);
      }
    }
  }
  if ( *((_BYTE *)this + 688) )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    *((_QWORD *)this + 87) += PerformanceCount.QuadPart - *((_QWORD *)this + 88);
    ++*((_DWORD *)this + 173);
  }
  *((_QWORD *)this + 74) = 10000 * ((int)timeGetTime() - v48);
  if ( updated == -1072861855 )
  {
    updated = MotionTurboJpeg::CMJPGMFTTypeHandler::UpdateAvaliableTypesForNewFormat(
                *((MotionTurboJpeg::CMJPGMFTTypeHandler **)this + 61),
                *(_DWORD *)(*((_QWORD *)this + 79) + 224LL),
                *(_DWORD *)(*((_QWORD *)this + 79) + 228LL));
    if ( updated )
      goto LABEL_136;
    v54 = *((_QWORD *)this + 79);
    *((_DWORD *)this + 126) = *(_DWORD *)(v54 + 228);
    *((_DWORD *)this + 125) = *(_DWORD *)(v54 + 224);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled() )
    {
      v56 = *((_QWORD *)this + 91);
      if ( !v56
        || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 320LL))(
              v56,
              MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
      {
        *(_DWORD *)&EventDescriptor.Id = *((_DWORD *)this + 125);
        LOBYTE(v55) = 1;
        *(_DWORD *)&EventDescriptor.Level = *((_DWORD *)this + 126);
        LOBYTE(UserDataCount) = 1;
        (*(void (__fastcall **)(char *, __int64, EVENT_DESCRIPTOR *, __int64, unsigned __int16 *))(*((_QWORD *)this + 92)
                                                                                                 + 56LL))(
          (char *)this + 736,
          1,
          &EventDescriptor,
          v55,
          UserDataCount);
      }
    }
    v57 = MFCalculateImageSize(
            &MFVideoFormat_RGB24,
            *((_DWORD *)this + 125),
            *((_DWORD *)this + 126),
            (UINT32 *)this + 129);
    v58 = v69;
    updated = v57;
    if ( v57 )
      goto LABEL_137;
    *a3 = 0;
    updated = -1072861855;
    *a4 = 256;
    if ( !v58 )
    {
LABEL_140:
      if ( (unsigned int)dword_18009C028 > 5 )
      {
        LODWORD(v70) = updated;
        v82 = &v70;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_18009C030;
        v83 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_18009C030;
        v79 = &byte_180093D97;
        UserData.Reserved = 2;
        v80 = 61;
        v81 = 1;
        v72[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
      goto LABEL_142;
    }
LABEL_102:
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    goto LABEL_140;
  }
  if ( updated == -2 )
  {
    v59 = *((_QWORD *)this + 2);
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      *((_QWORD *)this + 2) = 0;
    }
    v58 = v69;
    updated = -1072861838;
    if ( !v69 )
      goto LABEL_140;
    goto LABEL_102;
  }
  if ( updated )
    goto LABEL_136;
  v8 = v72[1];
LABEL_110:
  if ( !v8 )
  {
LABEL_118:
    ((void (__fastcall *)(_QWORD, const GUID *, _QWORD))(*a3)->lpVtbl->SetUINT32)(*a3, &MFSampleExtension_Interlaced, 0);
    goto LABEL_119;
  }
  v60 = v8 - 1;
  if ( v60 )
  {
    if ( v60 == 1 )
    {
      if ( ((unsigned int (__fastcall *)(_QWORD, const GUID *, __int64))(*a3)->lpVtbl->SetUINT32)(
             *a3,
             &MFSampleExtension_Interlaced,
             1) )
      {
        goto LABEL_119;
      }
      v61 = 1;
      goto LABEL_115;
    }
    goto LABEL_118;
  }
  if ( !((unsigned int (__fastcall *)(_QWORD, const GUID *, __int64))(*a3)->lpVtbl->SetUINT32)(
          *a3,
          &MFSampleExtension_Interlaced,
          1) )
  {
    v61 = 0;
LABEL_115:
    ((void (__fastcall *)(_QWORD, const GUID *, __int64))(*a3)->lpVtbl->SetUINT32)(
      *a3,
      &MFSampleExtension_BottomFieldFirst,
      v61);
  }
LABEL_119:
  updated = ((__int64 (__fastcall *)(_QWORD, const GUID *, __int64))(*a3)->lpVtbl->SetUINT32)(
              *a3,
              &MFSampleExtension_CleanPoint,
              1);
  if ( updated )
    goto LABEL_136;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled() )
  {
    *(_QWORD *)&v77.Data1 = *((_QWORD *)this + 74);
    LOBYTE(v62) = 1;
    LOBYTE(UserDataCount) = 1;
    (*(void (__fastcall **)(char *, _QWORD, struct _GUID *, __int64, unsigned __int16 *))(*((_QWORD *)this + 92) + 56LL))(
      (char *)this + 736,
      0,
      &v77,
      v62,
      UserDataCount);
  }
  if ( *a3 )
  {
    v63 = *((_QWORD *)this + 2);
    if ( v63 )
    {
      PerformanceCount.QuadPart = 0;
      if ( (*(int (__fastcall **)(__int64, LARGE_INTEGER *))(*(_QWORD *)v63 + 280LL))(v63, &PerformanceCount) >= 0 )
        ((void (__fastcall *)(_QWORD, _QWORD))(*a3)->lpVtbl->SetSampleTime)(
          *a3,
          (LARGE_INTEGER)PerformanceCount.QuadPart);
      if ( (*(int (__fastcall **)(_QWORD, LARGE_INTEGER *))(**((_QWORD **)this + 2) + 296LL))(
             *((_QWORD *)this + 2),
             &PerformanceCount) >= 0 )
        ((void (__fastcall *)(_QWORD, _QWORD))(*a3)->lpVtbl->SetSampleDuration)(
          *a3,
          (LARGE_INTEGER)PerformanceCount.QuadPart);
      updated = 0;
    }
  }
  v17 = v69;
  if ( v69 )
  {
LABEL_9:
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
LABEL_142:
  v65 = v73[0];
  if ( v73[0] )
  {
    v73[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001ef40  mov     r11, rsp
0x18001ef43  push    rbp
0x18001ef44  push    rbx
0x18001ef45  lea     rbp, [r11-38h]
0x18001ef49  sub     rsp, 128h
0x18001ef50  mov     rax, cs:__security_cookie
0x18001ef57  xor     rax, rsp
0x18001ef5a  mov     [rbp+30h+var_40], rax
0x18001ef5e  mov     rax, [rcx+250h]
0x18001ef65  mov     [r11+10h], rsi
0x18001ef69  xor     esi, esi
0x18001ef6b  cmp     [rcx+248h], rax
0x18001ef72  mov     r10d, esi
0x18001ef75  mov     [r11-18h], rdi
0x18001ef79  mov     rdi, rcx
0x18001ef7c  setnle  r10b
0x18001ef80  mov     [r11-20h], r12
0x18001ef84  mov     [r11-28h], r13
0x18001ef88  xor     edx, edx
0x18001ef8a  mov     [rcx+248h], rsi
0x18001ef91  mov     r13, r9
0x18001ef94  mov     r9d, [rcx+270h]
0x18001ef9b  mov     r12d, esi
0x18001ef9e  mov     [r11-30h], r14
0x18001efa2  mov     eax, r9d
0x18001efa5  mov     [r11-38h], r15
0x18001efa9  mov     r15, r8
0x18001efac  mov     r8d, [rcx+26Ch]
0x18001efb3  mov     ecx, [rcx+268h]
0x18001efb9  imul    rax, r8
0x18001efbd  mov     [rsp+70h], rsi
0x18001efc2  div     rcx
0x18001efc5  mov     rcx, [rdi+10h]
0x18001efc9  mov     eax, esi
0x18001efcb  cmp     rdx, r8
0x18001efce  mov     [rsp+130h+var_C8+4], esi
0x18001efd2  setnbe  al
0x18001efd5  or      eax, r10d
0x18001efd8  mov     [rdi+258h], eax
0x18001efde  lea     eax, [r9+1]
0x18001efe2  mov     [rdi+270h], eax
0x18001efe8  jz      short loc_18001F00F
0x18001efea  test    rcx, rcx
0x18001efed  jz      short loc_18001EFFF
0x18001efef  mov     rax, [rcx]
0x18001eff2  mov     rax, [rax+10h]
0x18001eff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001effb  mov     [rdi+10h], rsi
0x18001efff  inc     dword ptr [rdi+274h]
0x18001f005  mov     ebx, 0C00D6D72h
0x18001f00a  jmp     loc_18001FB96
0x18001f00f  mov     rax, [rcx]
0x18001f012  lea     r8, [rsp+70h]
0x18001f017  xor     edx, edx
0x18001f019  mov     rax, [rax+140h]
0x18001f020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f025  mov     ebx, eax
0x18001f027  test    eax, eax
0x18001f029  jnz     loc_18001FB8E
0x18001f02f  mov     rcx, [rsp+70h]
0x18001f034  lea     r8, [rsp+130h+var_E0]
0x18001f039  mov     [rsp+130h+var_E0], rsi
0x18001f03e  mov     rdx, [rcx]
0x18001f041  mov     rax, [rdx]
0x18001f044  lea     rdx, _GUID_c1209904_e584_4752_a2d6_7f21693f8b21
0x18001f04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f050  mov     rcx, [rsp+70h]
0x18001f055  test    eax, eax
0x18001f057  js      loc_18001F603
0x18001f05d  mov     [rsp+130h+var_C8], esi
0x18001f061  lea     rdx, [rsp+130h+var_C8]
0x18001f066  mov     [rsp+130h+var_C8+4], esi
0x18001f06a  mov     rax, [rcx]
0x18001f06d  mov     rax, [rax+38h]
0x18001f071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f076  test    eax, eax
0x18001f078  jz      short loc_18001F09E
0x18001f07a  mov     rcx, [rsp+130h+var_E0]
0x18001f07f  test    rcx, rcx
0x18001f082  jz      loc_18001FC40
0x18001f088  mov     [rsp+130h+var_E0], rsi
0x18001f08d  mov     rax, [rcx]
0x18001f090  mov     rax, [rax+10h]
0x18001f094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f099  jmp     loc_18001FC40
0x18001f09e  cmp     [rdi+288h], rsi
0x18001f0a5  jnz     loc_18001F3CE
0x18001f0ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f0b2  mov     ecx, 0E8h; unsigned __int64
0x18001f0b7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f0bc  mov     rsi, rax
0x18001f0bf  test    rax, rax
0x18001f0c2  jz      loc_18001F362
0x18001f0c8  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001f0cf  movups  xmmword ptr [rax+10h], xmm0
0x18001f0d3  movzx   eax, cs:byte_18009D825
0x18001f0da  cmp     al, 8
0x18001f0dc  jb      short loc_18001F158
0x18001f0de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0e5  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x18001f0ec  mov     edx, 0Ah
0x18001f0f1  mov     r9, rsi
0x18001f0f4  mov     rcx, [rcx+0D8h]
0x18001f0fb  call    WPP_SF_q
0x18001f100  movzx   eax, cs:byte_18009D825
0x18001f107  cmp     al, 8
0x18001f109  jb      short loc_18001F158
0x18001f10b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f112  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x18001f119  mov     edx, 11h
0x18001f11e  mov     r9, rsi
0x18001f121  mov     rcx, [rcx+0D8h]
0x18001f128  call    WPP_SF_q
0x18001f12d  cmp     cs:byte_18009D825, 8
0x18001f134  jb      short loc_18001F158
0x18001f136  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f13d  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x18001f144  mov     edx, 26h ; '&'
0x18001f149  mov     r9, rsi
0x18001f14c  mov     rcx, [rcx+0D8h]
0x18001f153  call    WPP_SF_q
0x18001f158  mov     r9d, 2; dwFlags
0x18001f15e  mov     qword ptr [rbp+30h+pbBuffer], r12
0x18001f162  mov     r8d, 8; cbBuffer
0x18001f168  lea     rdx, [rbp+30h+pbBuffer]; pbBuffer
0x18001f16c  xor     ecx, ecx; hAlgorithm
0x18001f16e  call    cs:__imp_BCryptGenRandom
0x18001f174  mov     ebx, eax
0x18001f176  or      ebx, 10000000h
0x18001f17c  jge     short loc_18001F1B0
0x18001f17e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f185  jb      short loc_18001F1AA
0x18001f187  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f18e  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x18001f195  mov     edx, 27h ; '''
0x18001f19a  mov     [rsp+130h+UserDataCount], ebx
0x18001f19e  mov     r9, rsi
0x18001f1a1  mov     rcx, [rcx+10h]
0x18001f1a5  call    WPP_SF_qd
0x18001f1aa  lea     r14, [rsi+20h]
0x18001f1ae  jmp     short loc_18001F20C
0x18001f1b0  mov     rbx, qword ptr [rbp+30h+pbBuffer]
0x18001f1b4  call    cs:__imp_GetCurrentProcessId
0x18001f1ba  lea     r14, [rsi+20h]
0x18001f1be  mov     qword ptr [rsp+130h+UserDataCount], rbx
0x18001f1c3  mov     r9d, eax
0x18001f1c6  lea     r8, aFsisoUI64u; "FsIso_%u_%I64u"
0x18001f1cd  mov     rcx, r14; unsigned __int16 *
0x18001f1d0  mov     edx, 64h ; 'd'; unsigned __int64
0x18001f1d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f1da  mov     ebx, eax
0x18001f1dc  test    eax, eax
0x18001f1de  jns     short loc_18001F25F
0x18001f1e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f1e7  jb      short loc_18001F20C
0x18001f1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1f0  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x18001f1f7  mov     edx, 28h ; '('
0x18001f1fc  mov     [rsp+130h+UserDataCount], eax
0x18001f200  mov     r9, rsi
0x18001f203  mov     rcx, [rcx+10h]
0x18001f207  call    WPP_SF_qd
0x18001f20c  cmp     cs:byte_18009D825, 1
0x18001f213  jb      short loc_18001F247
0x18001f215  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f21c  lea     rax, dword_1800912B4
0x18001f223  test    r14, r14
0x18001f226  mov     edx, 29h ; ')'
0x18001f22b  mov     r9, rsi
0x18001f22e  cmovnz  rax, r14
0x18001f232  mov     rcx, [rcx+0D8h]
0x18001f239  mov     [rsp+130h+UserData], rax
0x18001f23e  mov     [rsp+130h+UserDataCount], ebx
0x18001f242  call    WPP_SF_qDS
0x18001f247  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f24e  jb      loc_18001F2F2
0x18001f254  mov     edx, 12h
0x18001f259  mov     [rsp+130h+UserDataCount], ebx
0x18001f25d  jmp     short loc_18001F2D8
0x18001f25f  cmp     cs:byte_18009D825, 8
0x18001f266  jb      short loc_18001F29A
0x18001f268  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f26f  lea     rax, dword_1800912B4
0x18001f276  test    r14, r14
0x18001f279  mov     edx, 2Ah ; '*'
0x18001f27e  mov     r9, rsi
0x18001f281  cmovnz  rax, r14
0x18001f285  mov     rcx, [rcx+0D8h]
0x18001f28c  mov     [rsp+130h+UserData], rax
0x18001f291  mov     [rsp+130h+UserDataCount], ebx
0x18001f295  call    WPP_SF_qDS
0x18001f29a  mov     rcx, rsi; this
0x18001f29d  call    ?LaunchProcess@CameraTrustlet@@AEAAJXZ; CameraTrustlet::LaunchProcess(void)
0x18001f2a2  mov     ebx, eax
0x18001f2a4  test    eax, eax
0x18001f2a6  jns     short loc_18001F2B8
0x18001f2a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f2af  jb      short loc_18001F2F2
0x18001f2b1  mov     edx, 13h
0x18001f2b6  jmp     short loc_18001F2D4
0x18001f2b8  mov     rcx, rsi; Binding
0x18001f2bb  call    ?EstablishRpcConnection@CameraTrustlet@@AEAAJXZ; CameraTrustlet::EstablishRpcConnection(void)
0x18001f2c0  mov     ebx, eax
0x18001f2c2  test    eax, eax
0x18001f2c4  jns     short loc_18001F32E
0x18001f2c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f2cd  jb      short loc_18001F2F2
0x18001f2cf  mov     edx, 14h
0x18001f2d4  mov     [rsp+130h+UserDataCount], eax
0x18001f2d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2df  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x18001f2e6  mov     r9, rsi
0x18001f2e9  mov     rcx, [rcx+10h]
0x18001f2ed  call    WPP_SF_qd
0x18001f2f2  cmp     cs:byte_18009D825, 1
0x18001f2f9  jb      short loc_18001F31A
0x18001f2fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f302  mov     edx, 15h
0x18001f307  mov     r9, rsi
0x18001f30a  mov     [rsp+130h+UserDataCount], ebx
0x18001f30e  mov     rcx, [rcx+0D8h]
0x18001f315  call    WPP_SF_qD
0x18001f31a  mov     eax, ebx
0x18001f31c  movzx   ecx, bx
0x18001f31f  and     eax, 1FFF0000h
0x18001f324  cmp     eax, 70000h
0x18001f329  cmovnz  ecx, ebx
0x18001f32c  jmp     short loc_18001F367
0x18001f32e  cmp     cs:byte_18009D825, 8
0x18001f335  jb      short loc_18001F356
0x18001f337  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f33e  mov     edx, 16h
0x18001f343  mov     r9, rsi
0x18001f346  mov     [rsp+130h+UserDataCount], eax
0x18001f34a  mov     rcx, [rcx+0D8h]
0x18001f351  call    WPP_SF_qD
0x18001f356  lea     r14, [rdi+280h]
0x18001f35d  mov     [r14], rsi
0x18001f360  jmp     short loc_18001F39B
0x18001f362  mov     ecx, 8; dwErrCode
0x18001f367  call    cs:__imp_SetLastError
0x18001f36d  lea     r14, [rdi+280h]
0x18001f374  xor     esi, esi
0x18001f376  mov     rcx, r14
0x18001f379  mov     eax, esi
0x18001f37b  mov     [rcx], rax
0x18001f37e  call    cs:__imp_GetLastError
0x18001f384  mov     ebx, eax
0x18001f386  test    eax, eax
0x18001f388  jle     short loc_18001F393
0x18001f38a  movzx   ebx, ax
0x18001f38d  or      ebx, 80070000h
0x18001f393  test    ebx, ebx
0x18001f395  jnz     loc_18001FB73
0x18001f39b  mov     rcx, [r14]; this
0x18001f39e  test    rcx, rcx
0x18001f3a1  jnz     short loc_18001F3AF
0x18001f3a3  mov     ebx, 80070057h
0x18001f3a8  xor     esi, esi
0x18001f3aa  jmp     loc_18001FB73
0x18001f3af  call    ?CreateMjpegSession@CameraTrustlet@@QEAAPEAXXZ; CameraTrustlet::CreateMjpegSession(void)
0x18001f3b4  mov     [rdi+288h], rax
0x18001f3bb  test    rax, rax
0x18001f3be  jnz     short loc_18001F3CC
0x18001f3c0  mov     ebx, 8000FFFFh
0x18001f3c5  xor     esi, esi
0x18001f3c7  jmp     loc_18001FB73
0x18001f3cc  xor     esi, esi
0x18001f3ce  mov     rcx, [rsp+130h+var_E0]
0x18001f3d3  lea     rdx, [rbp+30h+EventDescriptor]
0x18001f3d7  mov     qword ptr [rbp+30h+EventDescriptor.Id], r12
0x18001f3db  mov     [rbp+30h+EventDescriptor.Keyword], r12
0x18001f3df  mov     qword ptr [rbp+30h+var_90], r12
0x18001f3e3  mov     qword ptr [rbp+30h+var_90+8], r12
0x18001f3e7  mov     [rsp+130h+var_D8], rsi
0x18001f3ec  mov     rax, [rcx]
0x18001f3ef  mov     rax, [rax+18h]
0x18001f3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3f8  mov     ebx, eax
0x18001f3fa  test    eax, eax
0x18001f3fc  jnz     loc_18001FB58
0x18001f402  mov     rcx, [r15]
0x18001f405  lea     r8, [rsp+130h+PerformanceCount]
0x18001f40a  mov     qword ptr [rsp+130h+PerformanceCount], rsi
0x18001f40f  xor     edx, edx
0x18001f411  mov     rax, [rcx]
0x18001f414  mov     rax, [rax+140h]
0x18001f41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f420  mov     rcx, qword ptr [rsp+130h+PerformanceCount]
0x18001f425  mov     ebx, eax
0x18001f427  test    eax, eax
0x18001f429  jnz     loc_18001FB42
0x18001f42f  mov     rax, [rcx]
0x18001f432  lea     rdx, [rsp+130h+var_C8+4]
0x18001f437  mov     rax, [rax+38h]
0x18001f43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f440  mov     ebx, eax
0x18001f442  test    eax, eax
0x18001f444  jz      short loc_18001F450
0x18001f446  mov     rcx, qword ptr [rsp+130h+PerformanceCount]
  ... truncated ...
```
