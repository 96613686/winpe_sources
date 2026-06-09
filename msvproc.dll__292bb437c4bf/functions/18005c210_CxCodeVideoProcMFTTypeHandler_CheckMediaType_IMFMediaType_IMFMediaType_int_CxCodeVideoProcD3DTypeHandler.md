# CxCodeVideoProcMFTTypeHandler::CheckMediaType(IMFMediaType *,IMFMediaType *,int,CxCodeVideoProcD3DTypeHandler *)

- ea: `0x18005c210`
- end: `0x18005d262`
- name: `?CheckMediaType@CxCodeVideoProcMFTTypeHandler@@QEAAJPEAUIMFMediaType@@0HPEAVCxCodeVideoProcD3DTypeHandler@@@Z`
- size: `4178`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTTypeHandler *this, struct IMFMediaType *, struct IMFMediaType *, unsigned int, struct CxCodeVideoProcD3DTypeHandler *)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005e680`
- `0x18005e9c0`
- `0x180062120`

## callees

- `0x180009578`
- `0x18000c9d0`
- `0x18000ecf0`
- `0x180021d7c`
- `0x180036268`
- `0x18003639c`
- `0x1800364d0`
- `0x180053bfc`
- `0x180054140`
- `0x180059ebc`
- `0x18005a1ec`
- `0x18005c210`
- `0x180066ad8`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c2b5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005c555`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005c747`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005cb5d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005ce42`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005d013`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005c555`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005c747`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005cb5d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005ce42`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005d013`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c2a5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c2a5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005c565`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005c757`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005cb6d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005ce52`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005d023`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005c565`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005c757`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005cb6d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005ce52`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005d023`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c2cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c2cb`

## string_xrefs

- `0x18005cd79`: `No color conversion avaliable for input and output combination`
- `0x18005d179`: `No color conversion avaliable for input and output combination`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CxCodeVideoProcMFTTypeHandler::CheckMediaType(
        CxCodeVideoProcMFTTypeHandler *this,
        struct IMFMediaType *a2,
        struct IMFMediaType *a3,
        unsigned int a4,
        struct CxCodeVideoProcD3DTypeHandler *a5)
{
  struct CxCodeVideoProcD3DTypeHandler *v5; // r12
  struct IMFMediaType *v6; // r14
  unsigned int v8; // edi
  CallStackTracing *v9; // rbx
  char *v10; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  __int64 v15; // rax
  int v16; // ebx
  __int128 v17; // xmm0
  char v18; // r15
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  int v20; // ebx
  __int16 *v21; // r9
  unsigned int v22; // edx
  const struct TypeSurface near *const *v23; // rax
  __int128 v24; // xmm1
  __m128i v25; // xmm2
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  struct IMFMediaTypeVtbl *v28; // rax
  unsigned int v29; // esi
  unsigned int v30; // edi
  struct IMFMediaTypeVtbl *v31; // rax
  unsigned int v32; // esi
  unsigned int v33; // edi
  struct IMFMediaTypeVtbl *v34; // rax
  struct IMFMediaType *v35; // r14
  struct IMFMediaTypeVtbl *v36; // rax
  int v37; // r15d
  __int64 v38; // r14
  BOOL v39; // eax
  __int64 v40; // r9
  unsigned int v41; // edi
  unsigned int v42; // edx
  const struct TypeSurface near *const *v43; // rax
  unsigned int v44; // r8d
  unsigned int v45; // edx
  __int128 v46; // xmm1
  __int128 v47; // xmm2
  __int128 v48; // xmm0
  const struct TypeSurface near *const *v49; // rax
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  unsigned int v53; // esi
  __int64 v54; // r8
  __int64 v55; // r9
  unsigned int v56; // r14d
  unsigned int j; // edx
  __int64 v58; // rcx
  unsigned int v59; // edx
  __int64 v60; // rcx
  __int64 v61; // r8
  unsigned int k; // edx
  __int64 v63; // rcx
  unsigned int v64; // edx
  __int64 v65; // rcx
  int v66; // eax
  char v67; // si
  struct IMFMediaTypeVtbl *v68; // rax
  __int64 v69; // r9
  int v70; // ecx
  unsigned int i; // edx
  __int64 v72; // rcx
  unsigned int v73; // ebx
  char v74; // di
  struct CxCodeVideoProcD3DTypeHandler *v75; // rax
  struct IMFMediaType *v76; // rdx
  struct IMFMediaType *v77; // r8
  char v79; // [rsp+30h] [rbp-A1h]
  _BYTE v80[3]; // [rsp+31h] [rbp-A0h] BYREF
  unsigned int v81; // [rsp+34h] [rbp-9Dh] BYREF
  unsigned int v82[2]; // [rsp+38h] [rbp-99h] BYREF
  unsigned int v83; // [rsp+40h] [rbp-91h] BYREF
  struct IMFMediaType *v84; // [rsp+48h] [rbp-89h] BYREF
  _MFVideoPrimaries v85; // [rsp+50h] [rbp-81h] BYREF
  EVENT_DESCRIPTOR v86; // [rsp+58h] [rbp-79h] BYREF
  struct IMFMediaType *v87; // [rsp+68h] [rbp-69h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-61h] BYREF
  unsigned int v89[4]; // [rsp+80h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-41h] BYREF
  __int128 v91; // [rsp+A0h] [rbp-31h]
  __int128 v92; // [rsp+B0h] [rbp-21h]
  __int128 v93; // [rsp+C0h] [rbp-11h]
  __int128 v94; // [rsp+D0h] [rbp-1h]

  v5 = a5;
  v84 = a3;
  v6 = a2;
  v87 = a2;
  v81 = a4;
  v8 = a4;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v80,
    "CxCodeVideoProcMFTTypeHandler::CheckMediaType",
    7467);
  v9 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 48) )
  {
    v10 = (char *)CallStackTracing::s_wpInstance + 208;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)v9 + 3));
      if ( Value )
      {
        v10 = Value;
      }
      else if ( !GetLastError() )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        v15 = (*(__int64 (__fastcall **)(__int64 *))*v13)(v13);
        if ( v15 )
          v10 = (char *)v15;
      }
      SetLastError(LastError);
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 296LL))(*((_QWORD *)this + 48));
    v17 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, EVENT_DESCRIPTOR *))(**((_QWORD **)this + 48) + 280LL))(
                       *((_QWORD *)this + 48),
                       &EventDescriptor);
    *((_DWORD *)v10 + 504) = v16;
    *((_OWORD *)v10 + 125) = v17;
    v8 = v81;
  }
  v18 = a5 && (*(unsigned __int8 (__fastcall **)(struct CxCodeVideoProcD3DTypeHandler *))(*(_QWORD *)a5 + 24LL))(a5);
  lpVtbl = v6->lpVtbl;
  v80[0] = v18;
  *(_OWORD *)v89 = 0;
  v20 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *))lpVtbl->GetGUID)(
          v6,
          &MF_MT_SUBTYPE,
          v89);
  if ( v20 )
    goto LABEL_172;
  v79 = 0;
  v21 = &_ImageBase;
  if ( !v18 )
  {
    v22 = 0;
    while ( 1 )
    {
      v23 = &CtypeSurfaces::types + 10 * v22;
      if ( *(_DWORD *)v23 == v89[0] )
        break;
      if ( ++v22 >= 0x24 )
        goto LABEL_35;
    }
    v24 = *((_OWORD *)v23 + 1);
    v25 = *((__m128i *)v23 + 2);
    UserData = *(struct _EVENT_DATA_DESCRIPTOR *)v23;
    v26 = *((_OWORD *)v23 + 3);
    v91 = v24;
    v27 = *((_OWORD *)v23 + 4);
    v93 = v26;
    v94 = v27;
    if ( !_mm_cvtsi128_si32(_mm_srli_si128(v25, 4)) )
    {
      if ( !*(_BYTE *)(*((_QWORD *)this + 45) + 28LL) )
      {
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            357,
            &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
            this,
            v89[0]);
        v20 = -1072875852;
        if ( (unsigned int)dword_1801520E8 > 5 )
        {
          v82[0] = -1072875852;
          *(_QWORD *)&v93 = v82;
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_1801520F0;
          *(_QWORD *)&v94 = L"Input format unsupported";
          *((_QWORD *)&v94 + 1) = 50;
          *((_QWORD *)&v93 + 1) = 4;
          *(_QWORD *)&v92 = "CxCodeVideoProcMFTTypeHandler::CheckMediaType";
          *((_QWORD *)&v92 + 1) = 46;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1801520F0;
          *(_QWORD *)&v91 = &dword_180147FC4;
          UserData.Reserved = 2;
          *((_QWORD *)&v91 + 1) = 0x10000002BLL;
          v83 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
        }
        RoOriginateErrorW(3222091444LL, 24, L"Input format unsupported", v21);
        goto LABEL_172;
      }
      v79 = 1;
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          358,
          &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
          this,
          v89[0]);
    }
  }
LABEL_35:
  if ( v8 )
  {
    if ( !*(_DWORD *)(*((_QWORD *)this + 45) + 4LL) )
    {
      v28 = v6->lpVtbl;
      *(_QWORD *)v82 = 0;
      if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *, __int16 *))v28->GetUINT64)(
             v6,
             &MF_MT_FRAME_RATE,
             v82,
             v21) >= 0 )
      {
        v29 = v82[0];
        v30 = v82[1];
        if ( !v82[0] )
        {
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qdd(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              359,
              &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
              this,
              v82[1],
              v82[0]);
          v20 = XvpOriginateError<51>();
          if ( v20 )
            goto LABEL_172;
        }
        if ( !v30 )
        {
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qdd(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              360,
              &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
              this,
              0,
              v29);
          v20 = -1072875852;
          if ( (unsigned int)dword_1801520E8 > 5 )
          {
            v82[0] = -1072875852;
            *(_QWORD *)&v93 = v82;
            *(_QWORD *)&v94 = L"Output frame rate unsupported(invalid numerator)";
            *(_QWORD *)&v92 = "CxCodeVideoProcMFTTypeHandler::CheckMediaType";
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_1801520F0;
            *((_QWORD *)&v94 + 1) = 98;
            *((_QWORD *)&v93 + 1) = 4;
            *((_QWORD *)&v92 + 1) = 46;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 0;
            UserData.Size = *(unsigned __int16 *)off_1801520F0;
            *(_QWORD *)&v91 = &word_180147D9E;
            UserData.Reserved = 2;
            *((_QWORD *)&v91 + 1) = 0x10000002BLL;
            v83 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
          }
          RoOriginateErrorW(3222091444LL, 48, L"Output frame rate unsupported(invalid numerator)", v21);
          goto LABEL_172;
        }
      }
    }
  }
  v31 = v6->lpVtbl;
  *(_QWORD *)v82 = 0;
  v20 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *, __int16 *))v31->GetUINT64)(
          v6,
          &MF_MT_FRAME_SIZE,
          v82,
          v21);
  if ( v20 )
    goto LABEL_172;
  v32 = v82[0];
  v33 = v82[1];
  v20 = CxCodeVideoProcMFTTypeHandler::CheckMediaDims(this, v82[1], v82[0], v89[0]);
  if ( v20 )
    goto LABEL_172;
  v34 = v6->lpVtbl;
  *(_QWORD *)v82 = 0;
  if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *))v34->GetUINT64)(
         v6,
         &MF_MT_PIXEL_ASPECT_RATIO,
         v82) >= 0
    && (!v82[0] || !v82[1])
    && (unsigned __int8)byte_180153DE0 >= 0x20u )
  {
    WPP_SF_qdd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      361,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      v82[1],
      v82[0]);
  }
  if ( !v84 )
    goto LABEL_132;
  v35 = v84;
  EventDescriptor = 0;
  v20 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, EVENT_DESCRIPTOR *))v84->lpVtbl->GetGUID)(
          v84,
          &MF_MT_SUBTYPE,
          &EventDescriptor);
  if ( v20 )
    goto LABEL_172;
  v36 = v35->lpVtbl;
  *(_QWORD *)&v86.Id = 0;
  v20 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, EVENT_DESCRIPTOR *))v36->GetUINT64)(
          v35,
          &MF_MT_FRAME_SIZE,
          &v86);
  if ( v20 )
    goto LABEL_172;
  v37 = *(_DWORD *)&v86.Id;
  v38 = HIDWORD(*(_QWORD *)&v86.Id);
  v20 = CxCodeVideoProcMFTTypeHandler::CheckMediaDims(
          this,
          *(unsigned int *)&v86.Level,
          *(unsigned int *)&v86.Id,
          *(unsigned int *)&EventDescriptor.Id);
  if ( v20 )
    goto LABEL_172;
  v83 = 2;
  v82[0] = 2;
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *))v87->lpVtbl->GetUINT32)(
    v87,
    &MF_MT_INTERLACE_MODE,
    &v83);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *))v84->lpVtbl->GetUINT32)(
    v84,
    &MF_MT_INTERLACE_MODE,
    v82);
  v39 = v83 != 2 || v82[0] != 2;
  if ( v80[0] )
    goto LABEL_81;
  v40 = *((_QWORD *)this + 45);
  if ( *(_DWORD *)(v40 + 12) || v33 == (_DWORD)v38 && v32 == v37 && !v39 )
    goto LABEL_81;
  v41 = v89[0];
  v42 = 0;
  while ( 1 )
  {
    v43 = &CtypeSurfaces::types + 10 * v42;
    if ( *(_DWORD *)v43 == v89[0] )
      break;
    if ( ++v42 >= 0x24 )
      goto LABEL_172;
  }
  v44 = *(_DWORD *)&EventDescriptor.Id;
  v45 = 0;
  v46 = *((_OWORD *)v43 + 1);
  v47 = *((_OWORD *)v43 + 3);
  UserData = *(struct _EVENT_DATA_DESCRIPTOR *)v43;
  v48 = *((_OWORD *)v43 + 2);
  v91 = v46;
  v92 = v48;
  v94 = *((_OWORD *)v43 + 4);
  while ( 1 )
  {
    v49 = &CtypeSurfaces::types + 10 * v45;
    if ( *(_DWORD *)v49 == *(_DWORD *)&EventDescriptor.Id )
      break;
    if ( ++v45 >= 0x24 )
      goto LABEL_172;
  }
  v50 = *((_OWORD *)v49 + 1);
  UserData = *(struct _EVENT_DATA_DESCRIPTOR *)v49;
  v51 = *((_OWORD *)v49 + 2);
  v91 = v50;
  v52 = *((_OWORD *)v49 + 3);
  v92 = v51;
  v94 = *((_OWORD *)v49 + 4);
  if ( !(_QWORD)v47 && !(_QWORD)v52 )
  {
    if ( !*(_BYTE *)(v40 + 28) )
    {
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          363,
          *(unsigned int *)&EventDescriptor.Id,
          this,
          v89[0],
          *(_DWORD *)&EventDescriptor.Id);
      v20 = -1072875852;
      if ( (unsigned int)dword_1801520E8 > 5 )
      {
        v81 = -1072875852;
        *(_QWORD *)&v93 = &v81;
        *(_QWORD *)&v94 = L"Scaler unavaliable for type";
        *(_QWORD *)&v92 = "CxCodeVideoProcMFTTypeHandler::CheckMediaType";
        *(_DWORD *)&v86.Level = 5;
        UserData.Ptr = (ULONGLONG)off_1801520F0;
        *((_QWORD *)&v94 + 1) = 56;
        *((_QWORD *)&v93 + 1) = 4;
        *((_QWORD *)&v92 + 1) = 46;
        *(_DWORD *)&v86.Id = 184549376;
        v86.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_1801520F0;
        *(_QWORD *)&v91 = word_180147E7A;
        UserData.Reserved = 2;
        *((_QWORD *)&v91 + 1) = 0x10000002BLL;
        LODWORD(v84) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &v86, 0, 0, 5u, &UserData);
      }
      RoOriginateErrorW(3222091444LL, 27, L"Scaler unavaliable for type", v40);
      goto LABEL_172;
    }
    v79 = 1;
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    {
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        362,
        *(unsigned int *)&EventDescriptor.Id,
        this,
        v89[0],
        *(_DWORD *)&EventDescriptor.Id);
LABEL_81:
      v44 = *(_DWORD *)&EventDescriptor.Id;
      v41 = v89[0];
    }
  }
  if ( v81 )
  {
    v53 = v44;
  }
  else
  {
    v53 = v41;
    v41 = v44;
  }
  v6 = v87;
  v85 = MFVideoPrimaries_Unknown;
  if ( v53 == 808596553 )
    v53 = 1448433993;
  if ( v41 == 808596553 )
    v41 = 1448433993;
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, _MFVideoPrimaries *))v87->lpVtbl->GetUINT32)(
    v87,
    &MF_MT_VIDEO_PRIMARIES,
    &v85);
  v54 = *((_QWORD *)this + 45);
  v18 = v80[0];
  if ( *(_DWORD *)(v54 + 12) != 1 || v80[0] )
  {
    if ( *(_DWORD *)&EventDescriptor.Id == v89[0] )
    {
      v20 = 0;
    }
    else if ( !v80[0] )
    {
      v55 = 0;
      for ( i = 0; i < 0x8D; ++i )
      {
        v72 = 6LL * i;
        if ( *(_DWORD *)((char *)&CtypeConversions::types + v72 * 4) == v53 && dword_1800D3204[v72] == v41 )
        {
          v73 = dword_1800D3210[v72];
          goto LABEL_151;
        }
      }
      if ( !*(_BYTE *)(v54 + 28) )
      {
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        {
          WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 42), 366, v54, this, v53, v41);
          v55 = 0;
        }
        v20 = -1072875852;
        if ( (unsigned int)dword_1801520E8 > 5 )
        {
          v86.Keyword = 0;
          goto LABEL_125;
        }
        goto LABEL_126;
      }
      v73 = 0;
      v79 = 1;
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 42), 365, v54, this, v53, v41);
LABEL_151:
      v20 = CxCodeVideoProcMFTTypeHandler::VerifyPrimaries(this, v53, v41, v85, v73);
      if ( v20 >= 0 )
        goto LABEL_132;
      if ( *(_BYTE *)(*((_QWORD *)this + 45) + 28LL) )
      {
        v67 = 1;
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 367, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this);
        goto LABEL_133;
      }
      v20 = XvpOriginateError<40>();
      if ( v20 )
        goto LABEL_172;
    }
  }
  else
  {
    v55 = 0;
    v56 = 0;
    if ( v53 == 1448433985 )
    {
      v61 = 0;
    }
    else
    {
      for ( j = 0; j < 0x12; ++j )
      {
        v58 = 6LL * j;
        if ( *(_DWORD *)((char *)&CtypeConversions::types_hq + v58 * 4) == v53 && dword_1800D53A4[v58] == 1448433985 )
        {
          v55 = (unsigned int)dword_1800D53B0[v58];
          v61 = 0;
          goto LABEL_109;
        }
      }
      v59 = 0;
      while ( 1 )
      {
        v60 = 6LL * v59;
        if ( *(_DWORD *)((char *)&CtypeConversions::types + v60 * 4) == v53 && dword_1800D3204[v60] == 1448433985 )
          break;
        if ( ++v59 >= 0x8D )
        {
          v61 = 2147500037LL;
          goto LABEL_109;
        }
      }
      v55 = (unsigned int)dword_1800D3210[v60];
      v61 = 0;
    }
LABEL_109:
    if ( v41 != 1448433985 )
    {
      for ( k = 0; k < 0x12; ++k )
      {
        v63 = 6LL * k;
        if ( *(_DWORD *)((char *)&CtypeConversions::types_hq + v63 * 4) == 1448433985 && dword_1800D53A4[v63] == v41 )
        {
          v56 = dword_1800D53B0[v63];
          v66 = 1;
          goto LABEL_119;
        }
      }
      v64 = 0;
      while ( 1 )
      {
        v65 = 6LL * v64;
        if ( *(_DWORD *)((char *)&CtypeConversions::types + v65 * 4) == 1448433985 && dword_1800D3204[v65] == v41 )
          break;
        if ( ++v64 >= 0x8D )
        {
          v66 = 0;
          goto LABEL_119;
        }
      }
      v56 = dword_1800D3210[v65];
      v66 = 1;
LABEL_119:
      if ( !v66 )
        goto LABEL_121;
    }
    if ( (int)v61 < 0 )
    {
LABEL_121:
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 42), 364, v61, this, v53, v41);
      v20 = -1072875852;
      if ( (unsigned int)dword_1801520E8 > 5 )
      {
        v86.Keyword = 0;
LABEL_125:
        *(_DWORD *)&v86.Id = 184549376;
        *(_QWORD *)&v93 = &v84;
        *(_QWORD *)&v92 = "CxCodeVideoProcMFTTypeHandler::CheckMediaType";
        *(_DWORD *)&v86.Level = 5;
        *((_QWORD *)&v92 + 1) = 46;
        *((_QWORD *)&v93 + 1) = 4;
        *((_QWORD *)&v94 + 1) = 126;
        *(_QWORD *)&v94 = L"No color conversion avaliable for input and output combination";
        UserData.Ptr = (ULONGLONG)off_1801520F0;
        LODWORD(v84) = -1072875852;
        UserData.Size = *(unsigned __int16 *)off_1801520F0;
        *(_QWORD *)&v91 = &byte_180147D67;
        UserData.Reserved = 2;
        *((_QWORD *)&v91 + 1) = 0x10000002BLL;
        v81 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &v86, 0, 0, 5u, &UserData);
      }
LABEL_126:
      RoOriginateErrorW(3222091444LL, 62, L"No color conversion avaliable for input and output combination", v55);
      goto LABEL_172;
    }
    v20 = CxCodeVideoProcMFTTypeHandler::VerifyPrimaries(this, v53, v41, v85, v55);
    if ( v20 )
      goto LABEL_172;
    v20 = CxCodeVideoProcMFTTypeHandler::VerifyPrimaries(this, v53, v41, v85, v56);
    if ( v20 )
      goto LABEL_172;
    v6 = v87;
  }
LABEL_132:
  v67 = v79;
LABEL_133:
  if ( !v81
    || (v68 = v6->lpVtbl,
        v82[0] = 2,
        ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *))v68->GetUINT32)(
          v6,
          &MF_MT_INTERLACE_MODE,
          v82),
        v82[0] <= 7)
    && (v70 = 133, _bittest(&v70, v82[0])) )
  {
    v74 = 0;
    if ( !v18 )
    {
      if ( !v67 )
        goto LABEL_172;
      v75 = (struct CxCodeVideoProcD3DTypeHandler *)operator new(0x20u);
      v5 = v75;
      if ( !v75 )
      {
        v20 = -2147024882;
        goto LABEL_172;
      }
      v74 = 1;
      *((_QWORD *)v75 + 1) = 0;
      *((_QWORD *)v75 + 2) = 0;
      *(_QWORD *)v75 = &CxCodeVideoProcWARPTypeHandler::`vftable';
      *((_QWORD *)v75 + 3) = 0;
    }
    if ( v81 )
    {
      v76 = v84;
      v77 = v6;
    }
    else
    {
      v77 = v84;
      v76 = v6;
    }
    v20 = (*(__int64 (__fastcall **)(struct CxCodeVideoProcD3DTypeHandler *, struct IMFMediaType *, struct IMFMediaType *, __int64, _DWORD))(*(_QWORD *)v5 + 8LL))(
            v5,
            v76,
            v77,
            1,
            0);
    if ( v74 )
      (**(void (__fastcall ***)(struct CxCodeVideoProcD3DTypeHandler *, __int64))v5)(v5, 1);
  }
  else
  {
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        368,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        this,
        v82[0]);
    v20 = -1072875852;
    if ( (unsigned int)dword_1801520E8 > 5 )
    {
      LODWORD(v84) = -1072875852;
      *(_QWORD *)&v93 = &v84;
      *(_QWORD *)&v94 = L"Interlaced output unsupported";
      *(_QWORD *)&v92 = "CxCodeVideoProcMFTTypeHandler::CheckMediaType";
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_1801520F0;
      *((_QWORD *)&v94 + 1) = 60;
      *((_QWORD *)&v93 + 1) = 4;
      *((_QWORD *)&v92 + 1) = 46;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_1801520F0;
      *(_QWORD *)&v91 = &dword_180147E0C;
      UserData.Reserved = 2;
      *((_QWORD *)&v91 + 1) = 0x10000002BLL;
      v83 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
    RoOriginateErrorW(3222091444LL, 29, L"Interlaced output unsupported", v69);
  }
LABEL_172:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v80);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18005c210  push    rbp
0x18005c212  push    rbx
0x18005c213  push    rsi
0x18005c214  push    rdi
0x18005c215  push    r12
0x18005c217  push    r13
0x18005c219  push    r14
0x18005c21b  lea     rbp, [rsp-1Fh]
0x18005c220  sub     rsp, 0F0h
0x18005c227  mov     rax, cs:__security_cookie
0x18005c22e  xor     rax, rsp
0x18005c231  mov     [rbp+4Fh+var_40], rax
0x18005c235  mov     r12, [rbp+4Fh+arg_20]
0x18005c239  lea     rsi, aCxcodevideopro_143; "CxCodeVideoProcMFTTypeHandler::CheckMed"...
0x18005c240  mov     [rsp+120h+var_D8], r8
0x18005c245  mov     r14, rdx
0x18005c248  mov     [rbp+4Fh+var_B8], rdx
0x18005c24c  mov     r13, rcx
0x18005c24f  mov     rdx, rsi; char *
0x18005c252  mov     [rsp+120h+var_EC], r9d
0x18005c257  mov     r8d, 1D2Bh; int
0x18005c25d  lea     rcx, [rsp+120h+var_EF]; this
0x18005c262  mov     edi, r9d
0x18005c265  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005c26a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c271  cmp     byte ptr [rbx+8], 0
0x18005c275  jz      loc_18005C376
0x18005c27b  cmp     qword ptr [r13+180h], 0
0x18005c283  jz      loc_18005C376
0x18005c289  cmp     byte ptr [rbx+8], 0
0x18005c28d  lea     rdi, [rbx+0D0h]
0x18005c294  jz      loc_18005C32D
0x18005c29a  call    cs:__imp_GetLastError
0x18005c2a0  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18005c2a3  mov     esi, eax
0x18005c2a5  call    cs:__imp_TlsGetValue
0x18005c2ab  test    rax, rax
0x18005c2ae  jz      short loc_18005C2B5
0x18005c2b0  mov     rdi, rax
0x18005c2b3  jmp     short loc_18005C31E
0x18005c2b5  call    cs:__imp_GetLastError
0x18005c2bb  test    eax, eax
0x18005c2bd  jnz     short loc_18005C31E
0x18005c2bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c2c6  test    rcx, rcx
0x18005c2c9  jnz     short loc_18005C30C
0x18005c2cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c2d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c2d8  mov     rcx, rax
0x18005c2db  test    rax, rax
0x18005c2de  jz      short loc_18005C2FE
0x18005c2e0  mov     rax, [rax]
0x18005c2e3  mov     edx, 7F0h
0x18005c2e8  mov     rax, [rax+8]
0x18005c2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c2f1  test    eax, eax
0x18005c2f3  jz      short loc_18005C2FE
0x18005c2f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c2fc  jmp     short loc_18005C30C
0x18005c2fe  lea     rcx, qword_180153440
0x18005c305  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c30c  mov     rax, [rcx]
0x18005c30f  mov     rax, [rax]
0x18005c312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c317  test    rax, rax
0x18005c31a  cmovnz  rdi, rax
0x18005c31e  mov     ecx, esi; dwErrCode
0x18005c320  call    cs:__imp_SetLastError
0x18005c326  lea     rsi, aCxcodevideopro_143; "CxCodeVideoProcMFTTypeHandler::CheckMed"...
0x18005c32d  mov     rcx, [r13+180h]
0x18005c334  mov     rax, [rcx]
0x18005c337  mov     rax, [rax+128h]
0x18005c33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c343  mov     r8, [r13+180h]
0x18005c34a  lea     rdx, [rbp+4Fh+EventDescriptor]
0x18005c34e  mov     ebx, eax
0x18005c350  mov     rcx, [r8]
0x18005c353  mov     rax, [rcx+118h]
0x18005c35a  mov     rcx, r8
0x18005c35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c362  movups  xmm0, xmmword ptr [rax]
0x18005c365  mov     [rdi+7E0h], ebx
0x18005c36b  movups  xmmword ptr [rdi+7D0h], xmm0
0x18005c372  mov     edi, [rsp+120h+var_EC]
0x18005c376  mov     [rsp+120h+arg_18], r15
0x18005c37e  test    r12, r12
0x18005c381  jz      short loc_18005C39C
0x18005c383  mov     rax, [r12]
0x18005c387  mov     rcx, r12
0x18005c38a  mov     rax, [rax+18h]
0x18005c38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c393  test    al, al
0x18005c395  jz      short loc_18005C39C
0x18005c397  mov     r15b, 1
0x18005c39a  jmp     short loc_18005C39F
0x18005c39c  xor     r15b, r15b
0x18005c39f  mov     rax, [r14]
0x18005c3a2  lea     r8, [rbp+4Fh+var_A0]
0x18005c3a6  xorps   xmm0, xmm0
0x18005c3a9  mov     [rsp+120h+var_EF], r15b
0x18005c3ae  lea     rdx, MF_MT_SUBTYPE
0x18005c3b5  mov     rcx, r14
0x18005c3b8  movups  xmmword ptr [rbp+4Fh+var_A0], xmm0
0x18005c3bc  mov     rax, [rax+50h]
0x18005c3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3c5  mov     ebx, eax
0x18005c3c7  test    eax, eax
0x18005c3c9  jnz     loc_18005D230
0x18005c3cf  xor     r10d, r10d
0x18005c3d2  mov     [rsp+120h+var_F0], al
0x18005c3d6  lea     r9, __ImageBase
0x18005c3dd  test    r15b, r15b
0x18005c3e0  jnz     loc_18005C5A8
0x18005c3e6  mov     r8d, [rbp+4Fh+var_A0]
0x18005c3ea  mov     edx, r10d
0x18005c3ed  nop     dword ptr [rax]
0x18005c3f0  mov     eax, edx
0x18005c3f2  lea     rcx, [rax+rax*4]
0x18005c3f6  shl     rcx, 4
0x18005c3fa  lea     rax, rva ?types@CtypeSurfaces@@0QBUTypeSurface@@B[r9]; TypeSurface const near * const CtypeSurfaces::types ...
0x18005c401  add     rax, rcx
0x18005c404  cmp     [rax], r8d
0x18005c407  jz      short loc_18005C415
0x18005c409  inc     edx
0x18005c40b  cmp     edx, 24h ; '$'
0x18005c40e  jb      short loc_18005C3F0
0x18005c410  jmp     loc_18005C5A8
0x18005c415  movups  xmm0, xmmword ptr [rax]
0x18005c418  movups  xmm1, xmmword ptr [rax+10h]
0x18005c41c  movups  xmm2, xmmword ptr [rax+20h]
0x18005c420  movaps  xmmword ptr [rbp+4Fh+var_90.Ptr], xmm0
0x18005c424  movups  xmm0, xmmword ptr [rax+30h]
0x18005c428  movaps  [rbp+4Fh+var_80], xmm1
0x18005c42c  movups  xmm1, xmmword ptr [rax+40h]
0x18005c430  psrldq  xmm2, 4
0x18005c435  movd    eax, xmm2
0x18005c439  movaps  [rbp+4Fh+var_60], xmm0
0x18005c43d  movaps  [rbp+4Fh+var_50], xmm1
0x18005c441  test    eax, eax
0x18005c443  jnz     loc_18005C5A8
0x18005c449  mov     rax, [r13+168h]
0x18005c450  cmp     [rax+1Ch], r10b
0x18005c454  jnz     loc_18005C570
0x18005c45a  cmp     cs:byte_180153DE0, 20h ; ' '
0x18005c461  jb      short loc_18005C48D
0x18005c463  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c46a  mov     edx, 165h
0x18005c46f  mov     [rsp+120h+UserDataCount], r8d
0x18005c474  mov     r9, r13
0x18005c477  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18005c47e  mov     rcx, [rcx+150h]
0x18005c485  call    WPP_SF_qD
0x18005c48a  xor     r10d, r10d
0x18005c48d  mov     eax, cs:dword_1801520E8
0x18005c493  lea     rdi, aInputFormatUns; "Input format unsupported"
0x18005c49a  mov     ebx, 0C00D36B4h
0x18005c49f  cmp     eax, 5
0x18005c4a2  jbe     loc_18005C55B
0x18005c4a8  lea     rax, [rsp+120h+var_E8]
0x18005c4ad  mov     [rsp+120h+var_E8], ebx
0x18005c4b1  mov     qword ptr [rbp+4Fh+var_60], rax
0x18005c4b5  lea     rcx, _TraceLoggingMetadata
0x18005c4bc  movzx   eax, cs:word_180147FBA
0x18005c4c3  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x18005c4c7  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x18005c4ca  xor     r9d, r9d; RelatedActivityId
0x18005c4cd  mov     rax, cs:off_1801520F0
0x18005c4d4  xor     r8d, r8d; ActivityId
0x18005c4d7  mov     [rbp+4Fh+var_90.Ptr], rax
0x18005c4db  mov     qword ptr [rbp+4Fh+var_50], rdi
0x18005c4df  mov     qword ptr [rbp+4Fh+var_50+8], 32h ; '2'
0x18005c4e7  mov     qword ptr [rbp+4Fh+var_60+8], 4
0x18005c4ef  mov     qword ptr [rbp+4Fh+var_70], rsi
0x18005c4f3  mov     qword ptr [rbp+4Fh+var_70+8], 2Eh ; '.'
0x18005c4fb  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x18005c502  mov     [rbp+4Fh+EventDescriptor.Keyword], r10
0x18005c506  movzx   eax, word ptr [rax]
0x18005c509  mov     [rbp+4Fh+var_90.Size], eax
0x18005c50c  lea     rax, dword_180147FC4
0x18005c513  mov     qword ptr [rbp+4Fh+var_80], rax
0x18005c517  lea     rax, _TraceLoggingMetadataEnd
0x18005c51e  sub     eax, ecx
0x18005c520  mov     dword ptr [rbp+4Fh+var_90.0Ch], 2
0x18005c527  mov     dword ptr [rbp+4Fh+var_80+8], 2Bh ; '+'
0x18005c52e  mov     dword ptr [rbp+4Fh+var_80+0Ch], 1
0x18005c535  mov     [rsp+120h+var_E0], eax
0x18005c539  mov     eax, [rsp+120h+var_E0]
0x18005c53d  mov     rcx, cs:RegHandle; RegHandle
0x18005c544  lea     rax, [rbp+4Fh+var_90]
0x18005c548  mov     [rsp+120h+UserData], rax; UserData
0x18005c54d  mov     [rsp+120h+UserDataCount], 5; UserDataCount
0x18005c555  call    cs:__imp_EventWriteTransfer
0x18005c55b  mov     r8, rdi
0x18005c55e  mov     edx, 18h
0x18005c563  mov     ecx, ebx
0x18005c565  call    cs:__imp_RoOriginateErrorW
0x18005c56b  jmp     loc_18005D230
0x18005c570  mov     [rsp+120h+var_F0], 1
0x18005c575  cmp     cs:byte_180153DE0, 20h ; ' '
0x18005c57c  jb      short loc_18005C5A8
0x18005c57e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c585  mov     edx, 166h
0x18005c58a  mov     [rsp+120h+UserDataCount], r8d
0x18005c58f  mov     r9, r13
0x18005c592  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18005c599  mov     rcx, [rcx+150h]
0x18005c5a0  call    WPP_SF_qD
0x18005c5a5  xor     r10d, r10d
0x18005c5a8  test    edi, edi
0x18005c5aa  jz      loc_18005C762
0x18005c5b0  mov     rax, [r13+168h]
0x18005c5b7  cmp     dword ptr [rax+4], 0
0x18005c5bb  jnz     loc_18005C762
0x18005c5c1  mov     rax, [r14]
0x18005c5c4  lea     r8, [rsp+120h+var_E8]
0x18005c5c9  lea     rdx, MF_MT_FRAME_RATE
0x18005c5d0  mov     qword ptr [rsp+120h+var_E8], r10
0x18005c5d5  mov     rcx, r14
0x18005c5d8  mov     rax, [rax+40h]
0x18005c5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5e1  test    eax, eax
0x18005c5e3  js      loc_18005C762
0x18005c5e9  mov     rsi, qword ptr [rsp+120h+var_E8]
0x18005c5ee  mov     rdi, rsi
0x18005c5f1  shr     rdi, 20h
0x18005c5f5  test    esi, esi
0x18005c5f7  jnz     short loc_18005C63B
0x18005c5f9  cmp     cs:byte_180153DE0, 20h ; ' '
0x18005c600  jb      short loc_18005C62C
0x18005c602  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c609  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18005c610  mov     edx, 167h
0x18005c615  mov     dword ptr [rsp+120h+UserData], esi
0x18005c619  mov     r9, r13
0x18005c61c  mov     [rsp+120h+UserDataCount], edi
0x18005c620  mov     rcx, [rcx+150h]
0x18005c627  call    WPP_SF_qdd
0x18005c62c  call    ??$XvpOriginateError@$0DD@@@YAJQEADJAEAY0DD@$$CBG@Z; XvpOriginateError<51>(char * const,long,ushort const (&)[51])
0x18005c631  mov     ebx, eax
0x18005c633  test    eax, eax
0x18005c635  jnz     loc_18005D230
0x18005c63b  test    edi, edi
0x18005c63d  jnz     loc_18005C762
0x18005c643  xor     edi, edi
0x18005c645  cmp     cs:byte_180153DE0, 20h ; ' '
0x18005c64c  jb      short loc_18005C678
0x18005c64e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c655  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18005c65c  mov     edx, 168h
0x18005c661  mov     dword ptr [rsp+120h+UserData], esi
0x18005c665  mov     r9, r13
0x18005c668  mov     [rsp+120h+UserDataCount], edi
0x18005c66c  mov     rcx, [rcx+150h]
0x18005c673  call    WPP_SF_qdd
0x18005c678  mov     eax, cs:dword_1801520E8
0x18005c67e  lea     rsi, aOutputFrameRat_0; "Output frame rate unsupported(invalid n"...
0x18005c685  mov     ebx, 0C00D36B4h
0x18005c68a  cmp     eax, 5
0x18005c68d  jbe     loc_18005C74D
0x18005c693  mov     [rsp+120h+var_E8], ebx
0x18005c697  lea     rax, [rsp+120h+var_E8]
0x18005c69c  mov     qword ptr [rbp+4Fh+var_60], rax
0x18005c6a0  lea     rcx, _TraceLoggingMetadata
0x18005c6a7  lea     rax, aCxcodevideopro_143; "CxCodeVideoProcMFTTypeHandler::CheckMed"...
0x18005c6ae  mov     qword ptr [rbp+4Fh+var_50], rsi
0x18005c6b2  mov     qword ptr [rbp+4Fh+var_70], rax
0x18005c6b6  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x18005c6ba  movzx   eax, cs:word_180147D94
0x18005c6c1  xor     r9d, r9d; RelatedActivityId
0x18005c6c4  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x18005c6c7  xor     r8d, r8d; ActivityId
0x18005c6ca  mov     rax, cs:off_1801520F0
0x18005c6d1  mov     [rbp+4Fh+var_90.Ptr], rax
0x18005c6d5  mov     qword ptr [rbp+4Fh+var_50+8], 62h ; 'b'
0x18005c6dd  mov     qword ptr [rbp+4Fh+var_60+8], 4
0x18005c6e5  mov     qword ptr [rbp+4Fh+var_70+8], 2Eh ; '.'
0x18005c6ed  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x18005c6f4  mov     [rbp+4Fh+EventDescriptor.Keyword], rdi
0x18005c6f8  movzx   eax, word ptr [rax]
0x18005c6fb  mov     [rbp+4Fh+var_90.Size], eax
0x18005c6fe  lea     rax, word_180147D9E
0x18005c705  mov     qword ptr [rbp+4Fh+var_80], rax
0x18005c709  lea     rax, _TraceLoggingMetadataEnd
0x18005c710  sub     eax, ecx
0x18005c712  mov     dword ptr [rbp+4Fh+var_90.0Ch], 2
0x18005c719  mov     dword ptr [rbp+4Fh+var_80+8], 2Bh ; '+'
0x18005c720  mov     dword ptr [rbp+4Fh+var_80+0Ch], 1
0x18005c727  mov     [rsp+120h+var_E0], eax
0x18005c72b  mov     eax, [rsp+120h+var_E0]
0x18005c72f  mov     rcx, cs:RegHandle; RegHandle
0x18005c736  lea     rax, [rbp+4Fh+var_90]
0x18005c73a  mov     [rsp+120h+UserData], rax; UserData
0x18005c73f  mov     [rsp+120h+UserDataCount], 5; UserDataCount
0x18005c747  call    cs:__imp_EventWriteTransfer
0x18005c74d  mov     r8, rsi
0x18005c750  mov     edx, 30h ; '0'
0x18005c755  mov     ecx, ebx
0x18005c757  call    cs:__imp_RoOriginateErrorW
0x18005c75d  jmp     loc_18005D230
0x18005c762  mov     rax, [r14]
  ... truncated ...
```
