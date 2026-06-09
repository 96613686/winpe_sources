# MFGetDLNAProfileID(MF_DLNA_CONTAINER_TYPE,IMFPresentationDescriptor *,tagPROPVARIANT *)

- ea: `0x180065424`
- end: `0x180065cd6`
- name: `?MFGetDLNAProfileID@@YAJW4MF_DLNA_CONTAINER_TYPE@@PEAUIMFPresentationDescriptor@@PEAUtagPROPVARIANT@@@Z`
- size: `2226`
- prototype: `int __high(enum MF_DLNA_CONTAINER_TYPE, struct IMFPresentationDescriptor *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004eff0`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000e41c`
- `0x180021120`
- `0x180021240`
- `0x180021b9c`
- `0x18004ba48`
- `0x1800516a4`
- `0x1800635e0`
- `0x1800648c0`
- `0x180064b30`
- `0x180065424`
- `0x180066af0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065c85`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x1800659c8`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x1800659c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800654cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065588`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065647`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800656ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800658a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800659ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065a87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065b22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065be8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800654cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065588`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065647`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800656ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800658a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800659ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065a87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065b22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065be8`

## pseudocode

```c
__int64 __fastcall MFGetDLNAProfileID(__int64 a1, __int64 a2, PROPVARIANT *a3)
{
  unsigned __int16 *v5; // r12
  __int64 v6; // rdx
  HRESULT StreamInformation; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned __int64 v27; // rdx
  __int64 v28; // r8
  int *v29; // r9
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned __int64 v33; // r15
  unsigned int i; // r14d
  const unsigned __int16 **v35; // rsi
  int v36; // eax
  __int64 v37; // rdx
  int v38; // eax
  __int64 (__fastcall *v39)(__int64, const unsigned __int16 **, int *, _QWORD); // rax
  int v40; // eax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  __int64 v43; // r8
  struct CallStackContext *v44; // rax
  const unsigned __int16 *v45; // r15
  unsigned __int64 v46; // rsi
  void *v47; // rcx
  int v48; // eax
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  __int64 v51; // r8
  int v52; // eax
  struct CallStackContext *v53; // rax
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  __int64 v56; // r8
  struct CallStackContext *v57; // rax
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  __int64 v60; // r8
  struct CallStackContext *v61; // rax
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  unsigned __int16 **v66; // [rsp+20h] [rbp-59h]
  unsigned __int64 *v67; // [rsp+28h] [rbp-51h]
  unsigned int v68; // [rsp+30h] [rbp-49h]
  _BYTE v69[4]; // [rsp+40h] [rbp-39h] BYREF
  int v70; // [rsp+44h] [rbp-35h] BYREF
  MF::DLNA *v71; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v72; // [rsp+50h] [rbp-29h] BYREF
  __int64 v73; // [rsp+58h] [rbp-21h] BYREF
  __int64 v74; // [rsp+60h] [rbp-19h] BYREF
  void *v75; // [rsp+68h] [rbp-11h] BYREF
  GUID v76; // [rsp+70h] [rbp-9h] BYREF
  __int128 v77; // [rsp+80h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v69, "MFGetDLNAProfileID", 9364);
  v74 = 0;
  v73 = 0;
  v72 = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v70 = 0;
  v75 = 0;
  v77 = 0;
  v5 = 0;
  LODWORD(v71) = 0;
  v76 = 0;
  StreamInformation = MF::DLNA::GetStreamInformation(a2, &v74, &v73, &v71);
  if ( StreamInformation < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamInformation )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFGetDLNAProfileID", 9383, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_130;
    v13 = 214;
    goto LABEL_129;
  }
  StreamInformation = (*(__int64 (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v74 + 80LL))(
                        v74,
                        &MF_MT_SUBTYPE,
                        &v77);
  if ( StreamInformation < 0 )
  {
    v17 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v19, "MFGetDLNAProfileID", 9385, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_130;
    v13 = 215;
    goto LABEL_129;
  }
  v20 = v73;
  if ( v73 )
  {
    StreamInformation = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v73 + 80LL))(
                          v73,
                          &MF_MT_SUBTYPE,
                          &v76);
    if ( StreamInformation < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v26, "MFGetDLNAProfileID", 9389, StreamInformation);
      }
      if ( !g_wppLevels )
        goto LABEL_130;
      v13 = 216;
      goto LABEL_129;
    }
  }
  else
  {
    v76 = GUID_00000000_0000_0000_0000_000000000000;
  }
  StreamInformation = MF::DLNA::GetPotentialDLNAProfiles(v20, &v77, &v76, &v72);
  if ( StreamInformation < 0 )
  {
    v30 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v32, "MFGetDLNAProfileID", 9402, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_130;
    v13 = 217;
LABEL_129:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
      0,
      StreamInformation);
    goto LABEL_130;
  }
  v33 = v72;
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(v33 + 32) )
      goto LABEL_117;
    v35 = (const unsigned __int16 **)(*(_QWORD *)(v33 + 40) + 112LL * i);
    if ( (unsigned __int8)byte_1800DC8D3 >= 0x10u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 218, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v35);
    v36 = MF::DLNA::CheckSystemConstraints(
            (MF::DLNA *)(unsigned int)v71,
            (unsigned int)v35,
            (const struct MF::DLNA::DLNAProfile *)&v70,
            v29);
    v29 = 0;
    StreamInformation = v36;
    if ( v36 < 0 )
    {
      v58 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, 0);
        CallStackTracing::s_wpInstance = v59;
        if ( v59
          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64, __int64, _QWORD))(*(_QWORD *)v59 + 8LL))(
               v59,
               2032,
               v60,
               0) )
        {
          v58 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v58 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v58 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
        if ( *((_DWORD *)v61 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v61, "MFGetDLNAProfileID", 9416, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v13 = 219;
        goto LABEL_129;
      }
      goto LABEL_130;
    }
    if ( !v70 )
    {
      if ( (unsigned __int8)byte_1800DC8D3 < 0x10u )
        continue;
      v37 = 220;
      goto LABEL_64;
    }
    v38 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **, int *, _QWORD))(v33 + 8))(v74, v35, &v70, 0);
    v29 = 0;
    StreamInformation = v38;
    if ( v38 < 0 )
    {
      v54 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, 0);
        CallStackTracing::s_wpInstance = v55;
        if ( v55
          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64, __int64, _QWORD))(*(_QWORD *)v55 + 8LL))(
               v55,
               2032,
               v56,
               0) )
        {
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v54 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v54 + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
        if ( *((_DWORD *)v57 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v57, "MFGetDLNAProfileID", 9427, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v13 = 221;
        goto LABEL_129;
      }
      goto LABEL_130;
    }
    if ( !v70 )
    {
      if ( (unsigned __int8)byte_1800DC8D3 < 0x10u )
        continue;
      v37 = 222;
      goto LABEL_64;
    }
    v39 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 **, int *, _QWORD))(v33 + 24);
    if ( !v39 )
      break;
    v40 = v39(v73, v35, &v70, 0);
    v29 = 0;
    StreamInformation = v40;
    if ( v40 < 0 )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, 0);
        CallStackTracing::s_wpInstance = v42;
        if ( v42
          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64, __int64, _QWORD))(*(_QWORD *)v42 + 8LL))(
               v42,
               2032,
               v43,
               0) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v44 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v44, "MFGetDLNAProfileID", 9440, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v13 = 223;
        goto LABEL_129;
      }
      goto LABEL_130;
    }
    if ( v70 )
      break;
    if ( (unsigned __int8)byte_1800DC8D3 < 0x10u )
      continue;
    v37 = 224;
LABEL_64:
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), v37, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
  }
  if ( (unsigned __int8)byte_1800DC8D3 >= 8u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 225, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v35);
    v29 = 0;
  }
  v45 = *v35;
  v46 = -1;
  do
    ++v46;
  while ( v45[v46] );
  if ( v46 + 1 < v46 )
  {
    StreamInformation = -2147024362;
    goto LABEL_87;
  }
  v72 = 0;
  StreamInformation = ULongLongMult(v46 + 1, v27, &v72);
  if ( StreamInformation >= 0 )
  {
    v48 = CTCoAllocPolicy::Alloc(v47, v27, v72, &v75);
    v5 = (unsigned __int16 *)v75;
    StreamInformation = v48;
    v29 = 0;
  }
  if ( StreamInformation < 0 )
  {
LABEL_87:
    v49 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
      LOBYTE(v29) = 0;
      CallStackTracing::s_wpInstance = v50;
      if ( v50
        && (v52 = (*(__int64 (__fastcall **)(CallStackTracing *, __int64, __int64, _QWORD))(*(_QWORD *)v50 + 8LL))(
                    v50,
                    2032,
                    v51,
                    0),
            LOBYTE(v29) = 0,
            v52) )
      {
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v49 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v49 + 8) != (_BYTE)v29 )
    {
      v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
      if ( *((_DWORD *)v53 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v53, "MFGetDLNAProfileID", 9455, StreamInformation);
    }
    if ( g_wppLevels )
    {
      v13 = 226;
      goto LABEL_129;
    }
    goto LABEL_130;
  }
  StringCchCopyNExW(v5, v46 + 1, v45, v46, v66, v67, v68);
  if ( v5 )
  {
    StreamInformation = InitPropVariantFromStringAsVector(v5, a3);
    goto LABEL_130;
  }
LABEL_117:
  if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 227, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
  v62 = (__int64 *)CallStackTracing::s_wpInstance;
  StreamInformation = -1072863756;
  if ( !CallStackTracing::s_wpInstance )
  {
    v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
    CallStackTracing::s_wpInstance = v63;
    if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
    {
      v62 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v62 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v62 + 8) )
  {
    v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
    if ( *((_DWORD *)v64 + 499) != -1072863756 )
      CallStackContext::TraceFailure(v64, "MFGetDLNAProfileID", 9463, -1072863756);
  }
  if ( g_wppLevels )
  {
    v13 = 228;
    goto LABEL_129;
  }
LABEL_130:
  CoTaskMemFree(v5);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v73);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v74);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v69);
  return (unsigned int)StreamInformation;
}

```

## disassembly

```asm
0x180065424  mov     [rsp-8+arg_0], rbx
0x180065429  push    rbp
0x18006542a  push    rsi
0x18006542b  push    rdi
0x18006542c  push    r12
0x18006542e  push    r13
0x180065430  push    r14
0x180065432  push    r15
0x180065434  lea     rbp, [rsp-27h]
0x180065439  sub     rsp, 0A0h
0x180065440  mov     rax, cs:__security_cookie
0x180065447  xor     rax, rsp
0x18006544a  mov     [rbp+57h+var_40], rax
0x18006544e  mov     r13, r8
0x180065451  lea     rdi, aMfgetdlnaprofi; "MFGetDLNAProfileID"
0x180065458  mov     rbx, rdx
0x18006545b  lea     rcx, [rbp+57h+var_90]; this
0x18006545f  mov     rdx, rdi; char *
0x180065462  mov     r8d, 2494h; int
0x180065468  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006546d  xor     esi, esi
0x18006546f  lea     r9, [rbp+57h+var_88]
0x180065473  xorps   xmm0, xmm0
0x180065476  mov     [rbp+57h+var_70], rsi
0x18006547a  xorps   xmm1, xmm1
0x18006547d  mov     [rbp+57h+var_78], rsi
0x180065481  xor     eax, eax
0x180065483  mov     [rbp+57h+var_80], rsi
0x180065487  movups  xmmword ptr [r13+0], xmm0
0x18006548c  lea     r8, [rbp+57h+var_78]
0x180065490  mov     [r13+10h], rax
0x180065494  lea     rdx, [rbp+57h+var_70]
0x180065498  mov     [rbp+57h+var_8C], esi
0x18006549b  mov     rcx, rbx
0x18006549e  mov     [rbp+57h+var_68], rsi
0x1800654a2  movups  [rbp+57h+var_50], xmm0
0x1800654a6  mov     r12d, esi
0x1800654a9  mov     dword ptr [rbp+57h+var_88], esi
0x1800654ac  movups  [rbp+57h+var_60], xmm1
0x1800654b0  call    MF__DLNA__GetStreamInformation
0x1800654b5  mov     ebx, eax
0x1800654b7  test    eax, eax
0x1800654b9  jns     loc_180065557
0x1800654bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800654c6  test    rcx, rcx
0x1800654c9  jnz     short loc_180065512
0x1800654cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800654d2  nop     dword ptr [rax+rax+00h]
0x1800654d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800654de  mov     rcx, rax
0x1800654e1  test    rax, rax
0x1800654e4  jz      short loc_180065504
0x1800654e6  mov     rax, [rax]
0x1800654e9  mov     edx, 7F0h
0x1800654ee  mov     rax, [rax+8]
0x1800654f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654f7  test    eax, eax
0x1800654f9  jz      short loc_180065504
0x1800654fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065502  jmp     short loc_180065512
0x180065504  lea     rcx, qword_1800DBF70; this
0x18006550b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065512  cmp     [rcx+8], sil
0x180065516  jz      short loc_180065539
0x180065518  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006551d  cmp     [rax+7CCh], ebx
0x180065523  jz      short loc_180065539
0x180065525  mov     r9d, ebx; int
0x180065528  mov     r8d, 24A7h; int
0x18006552e  mov     rdx, rdi; char *
0x180065531  mov     rcx, rax; this
0x180065534  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180065539  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065540  jb      loc_180065C82
0x180065546  mov     edx, 0D6h
0x18006554b  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x180065552  jmp     loc_180065C6B
0x180065557  mov     rcx, [rbp+57h+var_70]
0x18006555b  lea     r8, [rbp+57h+var_50]
0x18006555f  lea     rdx, MF_MT_SUBTYPE
0x180065566  mov     rax, [rcx]
0x180065569  mov     rax, [rax+50h]
0x18006556d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065572  mov     ebx, eax
0x180065574  test    eax, eax
0x180065576  jns     loc_18006560D
0x18006557c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065583  test    rcx, rcx
0x180065586  jnz     short loc_1800655CF
0x180065588  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006558f  nop     dword ptr [rax+rax+00h]
0x180065594  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006559b  mov     rcx, rax
0x18006559e  test    rax, rax
0x1800655a1  jz      short loc_1800655C1
0x1800655a3  mov     rax, [rax]
0x1800655a6  mov     edx, 7F0h
0x1800655ab  mov     rax, [rax+8]
0x1800655af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800655b4  test    eax, eax
0x1800655b6  jz      short loc_1800655C1
0x1800655b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800655bf  jmp     short loc_1800655CF
0x1800655c1  lea     rcx, qword_1800DBF70; this
0x1800655c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800655cf  cmp     [rcx+8], sil
0x1800655d3  jz      short loc_1800655F6
0x1800655d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800655da  cmp     [rax+7CCh], ebx
0x1800655e0  jz      short loc_1800655F6
0x1800655e2  mov     r9d, ebx; int
0x1800655e5  mov     r8d, 24A9h; int
0x1800655eb  mov     rdx, rdi; char *
0x1800655ee  mov     rcx, rax; this
0x1800655f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800655f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800655fd  jb      loc_180065C82
0x180065603  mov     edx, 0D7h
0x180065608  jmp     loc_18006554B
0x18006560d  mov     rcx, [rbp+57h+var_78]
0x180065611  test    rcx, rcx
0x180065614  jz      loc_1800656CC
0x18006561a  mov     rax, [rcx]
0x18006561d  lea     r8, [rbp+57h+var_60]
0x180065621  lea     rdx, MF_MT_SUBTYPE
0x180065628  mov     rax, [rax+50h]
0x18006562c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065631  mov     ebx, eax
0x180065633  test    eax, eax
0x180065635  jns     loc_1800656D8
0x18006563b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065642  test    rcx, rcx
0x180065645  jnz     short loc_18006568E
0x180065647  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006564e  nop     dword ptr [rax+rax+00h]
0x180065653  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006565a  mov     rcx, rax
0x18006565d  test    rax, rax
0x180065660  jz      short loc_180065680
0x180065662  mov     rax, [rax]
0x180065665  mov     edx, 7F0h
0x18006566a  mov     rax, [rax+8]
0x18006566e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065673  test    eax, eax
0x180065675  jz      short loc_180065680
0x180065677  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006567e  jmp     short loc_18006568E
0x180065680  lea     rcx, qword_1800DBF70; this
0x180065687  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006568e  cmp     [rcx+8], sil
0x180065692  jz      short loc_1800656B5
0x180065694  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065699  cmp     [rax+7CCh], ebx
0x18006569f  jz      short loc_1800656B5
0x1800656a1  mov     r9d, ebx; int
0x1800656a4  mov     r8d, 24ADh; int
0x1800656aa  mov     rdx, rdi; char *
0x1800656ad  mov     rcx, rax; this
0x1800656b0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800656b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800656bc  jb      loc_180065C82
0x1800656c2  mov     edx, 0D8h
0x1800656c7  jmp     loc_18006554B
0x1800656cc  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800656d3  movdqu  [rbp+57h+var_60], xmm0
0x1800656d8  lea     r9, [rbp+57h+var_80]
0x1800656dc  lea     r8, [rbp+57h+var_60]
0x1800656e0  lea     rdx, [rbp+57h+var_50]
0x1800656e4  call    MF__DLNA__GetPotentialDLNAProfiles
0x1800656e9  mov     ebx, eax
0x1800656eb  test    eax, eax
0x1800656ed  jns     loc_180065784
0x1800656f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800656fa  test    rcx, rcx
0x1800656fd  jnz     short loc_180065746
0x1800656ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065706  nop     dword ptr [rax+rax+00h]
0x18006570b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065712  mov     rcx, rax
0x180065715  test    rax, rax
0x180065718  jz      short loc_180065738
0x18006571a  mov     rax, [rax]
0x18006571d  mov     edx, 7F0h
0x180065722  mov     rax, [rax+8]
0x180065726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006572b  test    eax, eax
0x18006572d  jz      short loc_180065738
0x18006572f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065736  jmp     short loc_180065746
0x180065738  lea     rcx, qword_1800DBF70; this
0x18006573f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065746  cmp     [rcx+8], sil
0x18006574a  jz      short loc_18006576D
0x18006574c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065751  cmp     [rax+7CCh], ebx
0x180065757  jz      short loc_18006576D
0x180065759  mov     r9d, ebx; int
0x18006575c  mov     r8d, 24BAh; int
0x180065762  mov     rdx, rdi; char *
0x180065765  mov     rcx, rax; this
0x180065768  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006576d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065774  jb      loc_180065C82
0x18006577a  mov     edx, 0D9h
0x18006577f  jmp     loc_18006554B
0x180065784  mov     r15, [rbp+57h+var_80]
0x180065788  lea     rdi, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18006578f  mov     r14d, esi
0x180065792  cmp     r14d, [r15+20h]
0x180065796  jnb     loc_180065BB1
0x18006579c  mov     eax, r14d
0x18006579f  imul    rsi, rax, 70h ; 'p'
0x1800657a3  add     rsi, [r15+28h]
0x1800657a7  cmp     cs:byte_1800DC8D3, 10h
0x1800657ae  jb      short loc_1800657CE
0x1800657b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800657b7  mov     edx, 0DAh
0x1800657bc  mov     r9, [rsi]
0x1800657bf  mov     r8, rdi
0x1800657c2  mov     rcx, [rcx+88h]
0x1800657c9  call    WPP_SF_S
0x1800657ce  mov     ecx, dword ptr [rbp+57h+var_88]; this
0x1800657d1  lea     r8, [rbp+57h+var_8C]; struct MF::DLNA::DLNAProfile *
0x1800657d5  mov     rdx, rsi; unsigned int
0x1800657d8  call    ?CheckSystemConstraints@DLNA@MF@@YAJIPEBUDLNAProfile@12@PEAH@Z; MF::DLNA::CheckSystemConstraints(uint,MF::DLNA::DLNAProfile const *,int *)
0x1800657dd  xor     r9d, r9d
0x1800657e0  mov     ebx, eax
0x1800657e2  test    eax, eax
0x1800657e4  js      loc_180065B16
0x1800657ea  cmp     [rbp+57h+var_8C], r9d
0x1800657ee  jnz     short loc_180065804
0x1800657f0  cmp     cs:byte_1800DC8D3, 10h
0x1800657f7  jb      loc_18006588F
0x1800657fd  mov     edx, 0DCh
0x180065802  jmp     short loc_180065879
0x180065804  mov     rcx, [rbp+57h+var_70]
0x180065808  lea     r8, [rbp+57h+var_8C]
0x18006580c  mov     rax, [r15+8]
0x180065810  mov     rdx, rsi
0x180065813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065818  xor     r9d, r9d
0x18006581b  mov     ebx, eax
0x18006581d  test    eax, eax
0x18006581f  js      loc_180065A7B
0x180065825  cmp     [rbp+57h+var_8C], r9d
0x180065829  jnz     short loc_18006583B
0x18006582b  cmp     cs:byte_1800DC8D3, 10h
0x180065832  jb      short loc_18006588F
0x180065834  mov     edx, 0DEh
0x180065839  jmp     short loc_180065879
0x18006583b  mov     rax, [r15+18h]
0x18006583f  test    rax, rax
0x180065842  jz      loc_180065932
0x180065848  mov     rcx, [rbp+57h+var_78]
0x18006584c  lea     r8, [rbp+57h+var_8C]
0x180065850  mov     rdx, rsi
0x180065853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065858  xor     r9d, r9d
0x18006585b  mov     ebx, eax
0x18006585d  test    eax, eax
0x18006585f  js      short loc_180065897
0x180065861  cmp     [rbp+57h+var_8C], r9d
0x180065865  jnz     loc_180065932
0x18006586b  cmp     cs:byte_1800DC8D3, 10h
0x180065872  jb      short loc_18006588F
0x180065874  mov     edx, 0E0h
0x180065879  mov     rcx, cs:WPP_GLOBAL_Control
0x180065880  mov     r8, rdi
0x180065883  mov     rcx, [rcx+88h]
0x18006588a  call    WPP_SF_
0x18006588f  inc     r14d
0x180065892  jmp     loc_180065792
0x180065897  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006589e  test    rcx, rcx
0x1800658a1  jnz     short loc_1800658F0
0x1800658a3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800658aa  nop     dword ptr [rax+rax+00h]
0x1800658af  xor     r9d, r9d
0x1800658b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800658b9  mov     rcx, rax
0x1800658bc  test    rax, rax
0x1800658bf  jz      short loc_1800658E2
0x1800658c1  mov     rax, [rax]
0x1800658c4  mov     edx, 7F0h
0x1800658c9  mov     rax, [rax+8]
0x1800658cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800658d2  xor     r9d, r9d
0x1800658d5  test    eax, eax
0x1800658d7  jz      short loc_1800658E2
0x1800658d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800658e0  jmp     short loc_1800658F0
0x1800658e2  lea     rcx, qword_1800DBF70; this
0x1800658e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800658f0  cmp     [rcx+8], r9b
0x1800658f4  jz      short loc_18006591B
0x1800658f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800658fb  cmp     [rax+7CCh], ebx
0x180065901  jz      short loc_18006591B
0x180065903  mov     r9d, ebx; int
0x180065906  lea     rdx, aMfgetdlnaprofi; "MFGetDLNAProfileID"
  ... truncated ...
```
