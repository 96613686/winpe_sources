# MFGetDLNAProfileID(MF_DLNA_CONTAINER_TYPE,IMFPresentationDescriptor *,tagPROPVARIANT *)

- ea: `0x18009f3c4`
- end: `0x18009fc02`
- name: `?MFGetDLNAProfileID@@YAJW4MF_DLNA_CONTAINER_TYPE@@PEAUIMFPresentationDescriptor@@PEAUtagPROPVARIANT@@@Z`
- size: `2110`
- prototype: `int __high(enum MF_DLNA_CONTAINER_TYPE, struct IMFPresentationDescriptor *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18015cbd0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180072b60`
- `0x180073b14`
- `0x18009f3c4`
- `0x1800c5168`
- `0x1801099f0`
- `0x180115a1c`
- `0x18012218c`
- `0x18016135c`
- `0x180170580`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f46b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f522`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f5db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f68d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f825`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f909`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f9d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fa64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fb21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f46b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f522`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f5db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f68d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f825`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f909`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f9d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fa64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fb21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009fbb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009fbb8`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18009f9b9`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18009f9b9`

## pseudocode

```c
__int64 __fastcall MFGetDLNAProfileID(__int64 a1, __int64 a2, PROPVARIANT *a3)
{
  WCHAR *v5; // r12
  __int64 v6; // rdx
  HRESULT StreamInformation; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  int *v29; // r9
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // r15
  unsigned int i; // r14d
  _QWORD *v35; // rsi
  int v36; // eax
  __int64 v37; // rdx
  int v38; // eax
  __int64 v39; // rcx
  __int64 (__fastcall *v40)(__int64, _QWORD *, int *); // rax
  int v41; // eax
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // r9
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  _BYTE v59[4]; // [rsp+30h] [rbp-39h] BYREF
  int v60; // [rsp+34h] [rbp-35h] BYREF
  MF::DLNA *v61; // [rsp+38h] [rbp-31h] BYREF
  PCWSTR psz; // [rsp+40h] [rbp-29h]
  __int64 v63; // [rsp+48h] [rbp-21h] BYREF
  __int64 v64; // [rsp+50h] [rbp-19h] BYREF
  __int64 v65; // [rsp+58h] [rbp-11h] BYREF
  GUID v66; // [rsp+60h] [rbp-9h] BYREF
  __int128 v67; // [rsp+70h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v59, "MFGetDLNAProfileID", 9364);
  v64 = 0;
  v63 = 0;
  v65 = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v60 = 0;
  psz = 0;
  v67 = 0;
  v5 = 0;
  LODWORD(v61) = 0;
  v66 = 0;
  StreamInformation = MF::DLNA::GetStreamInformation(a2, &v64, &v63, &v61);
  if ( StreamInformation < 0 )
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamInformation )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFGetDLNAProfileID", 9383, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_127;
    v13 = 214;
    goto LABEL_126;
  }
  StreamInformation = (*(__int64 (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v64 + 80LL))(
                        v64,
                        &MF_MT_SUBTYPE,
                        &v67);
  if ( StreamInformation < 0 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v19, "MFGetDLNAProfileID", 9385, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_127;
    v13 = 215;
    goto LABEL_126;
  }
  v20 = v63;
  if ( v63 )
  {
    StreamInformation = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v63 + 80LL))(
                          v63,
                          &MF_MT_SUBTYPE,
                          &v66);
    if ( StreamInformation < 0 )
    {
      v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v26, "MFGetDLNAProfileID", 9389, StreamInformation);
      }
      if ( !g_wppLevels )
        goto LABEL_127;
      v13 = 216;
      goto LABEL_126;
    }
  }
  else
  {
    v66 = GUID_00000000_0000_0000_0000_000000000000;
  }
  StreamInformation = MF::DLNA::GetPotentialDLNAProfiles(v20, &v67, &v66, &v65);
  if ( StreamInformation < 0 )
  {
    v30 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v32, "MFGetDLNAProfileID", 9402, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_127;
    v13 = 217;
LABEL_126:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
      0,
      StreamInformation);
    goto LABEL_127;
  }
  v33 = v65;
  for ( i = 0; i < *(_DWORD *)(v33 + 32); ++i )
  {
    v35 = (_QWORD *)(*(_QWORD *)(v33 + 40) + 112LL * i);
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 218, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v35);
    v36 = MF::DLNA::CheckSystemConstraints(
            (MF::DLNA *)(unsigned int)v61,
            (unsigned int)v35,
            (const struct MF::DLNA::DLNAProfile *)&v60,
            v29);
    v27 = 0;
    StreamInformation = v36;
    if ( v36 < 0 )
    {
      v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v28, v29);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v54, "MFGetDLNAProfileID", 9416, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v13 = 219;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( !v60 )
    {
      if ( (unsigned __int8)byte_1801B110B < 0x10u )
        continue;
      v37 = 220;
      goto LABEL_64;
    }
    v38 = (*(__int64 (__fastcall **)(__int64, _QWORD *, int *))(v33 + 8))(v64, v35, &v60);
    v27 = 0;
    StreamInformation = v38;
    if ( v38 < 0 )
    {
      v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v28, v29);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v51, "MFGetDLNAProfileID", 9427, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v13 = 221;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( !v60 )
    {
      if ( (unsigned __int8)byte_1801B110B < 0x10u )
        continue;
      v37 = 222;
      goto LABEL_64;
    }
    v40 = *(__int64 (__fastcall **)(__int64, _QWORD *, int *))(v33 + 24);
    if ( !v40 )
      goto LABEL_76;
    v41 = v40(v63, v35, &v60);
    v27 = 0;
    StreamInformation = v41;
    if ( v41 < 0 )
    {
      v42 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v28, v29);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v44, "MFGetDLNAProfileID", 9440, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v13 = 223;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( v60 )
    {
LABEL_76:
      if ( (unsigned __int8)byte_1801B110B >= 8u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 225, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v35);
      v45 = -1;
      do
        ++v45;
      while ( *(_WORD *)(*v35 + 2 * v45) );
      StreamInformation = _AllocStringWorker<CTCoAllocPolicy>(v39, v27);
      if ( StreamInformation < 0 )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != StreamInformation )
            CallStackContext::TraceFailure(v48, "MFGetDLNAProfileID", 9455, StreamInformation);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            226,
            &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
            0,
            StreamInformation);
        v5 = (WCHAR *)psz;
        goto LABEL_127;
      }
      v5 = (WCHAR *)psz;
      if ( psz )
      {
        StreamInformation = InitPropVariantFromStringAsVector(psz, a3);
        goto LABEL_127;
      }
      break;
    }
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
    {
      v37 = 224;
LABEL_64:
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), v37, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
      continue;
    }
  }
  if ( (unsigned __int8)byte_1801B110B >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 227, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
  v55 = (wchar_t *)CallStackTracing::s_wpInstance;
  StreamInformation = -1072863756;
  if ( !CallStackTracing::s_wpInstance )
  {
    v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
    CallStackTracing::s_wpInstance = v56;
    if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
    {
      v55 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v55 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v55 + 8) )
  {
    v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
    if ( *((_DWORD *)v57 + 499) != -1072863756 )
      CallStackContext::TraceFailure(v57, "MFGetDLNAProfileID", 9463, -1072863756);
  }
  if ( g_wppLevels )
  {
    v13 = 228;
    goto LABEL_126;
  }
LABEL_127:
  CoTaskMemFree(v5);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v63);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v64);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v59);
  return (unsigned int)StreamInformation;
}

```

## disassembly

```asm
0x18009f3c4  mov     [rsp-8+arg_0], rbx
0x18009f3c9  push    rbp
0x18009f3ca  push    rsi
0x18009f3cb  push    rdi
0x18009f3cc  push    r12
0x18009f3ce  push    r13
0x18009f3d0  push    r14
0x18009f3d2  push    r15
0x18009f3d4  lea     rbp, [rsp-27h]
0x18009f3d9  sub     rsp, 90h
0x18009f3e0  mov     rax, cs:__security_cookie
0x18009f3e7  xor     rax, rsp
0x18009f3ea  mov     [rbp+57h+var_40], rax
0x18009f3ee  mov     r13, r8
0x18009f3f1  lea     rdi, aMfgetdlnaprofi; "MFGetDLNAProfileID"
0x18009f3f8  mov     rbx, rdx
0x18009f3fb  lea     rcx, [rbp+57h+var_90]; this
0x18009f3ff  mov     rdx, rdi; char *
0x18009f402  mov     r8d, 2494h; int
0x18009f408  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009f40d  xor     esi, esi
0x18009f40f  lea     r9, [rbp+57h+var_88]
0x18009f413  xorps   xmm0, xmm0
0x18009f416  mov     [rbp+57h+var_70], rsi
0x18009f41a  xorps   xmm1, xmm1
0x18009f41d  mov     [rbp+57h+var_78], rsi
0x18009f421  xor     eax, eax
0x18009f423  mov     [rbp+57h+var_68], rsi
0x18009f427  movups  xmmword ptr [r13+0], xmm0
0x18009f42c  lea     r8, [rbp+57h+var_78]
0x18009f430  mov     [r13+10h], rax
0x18009f434  lea     rdx, [rbp+57h+var_70]
0x18009f438  mov     [rbp+57h+var_8C], esi
0x18009f43b  mov     rcx, rbx
0x18009f43e  mov     [rbp+57h+psz], rsi
0x18009f442  movups  [rbp+57h+var_50], xmm0
0x18009f446  mov     r12d, esi
0x18009f449  mov     dword ptr [rbp+57h+var_88], esi
0x18009f44c  movups  [rbp+57h+var_60], xmm1
0x18009f450  call    MF__DLNA__GetStreamInformation
0x18009f455  mov     ebx, eax
0x18009f457  test    eax, eax
0x18009f459  jns     loc_18009F4F1
0x18009f45f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f466  test    rcx, rcx
0x18009f469  jnz     short loc_18009F4AC
0x18009f46b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f471  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f478  mov     rcx, rax
0x18009f47b  test    rax, rax
0x18009f47e  jz      short loc_18009F49E
0x18009f480  mov     rax, [rax]
0x18009f483  mov     edx, 7F0h
0x18009f488  mov     rax, [rax+8]
0x18009f48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f491  test    eax, eax
0x18009f493  jz      short loc_18009F49E
0x18009f495  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f49c  jmp     short loc_18009F4AC
0x18009f49e  lea     rcx, qword_1801B07E0; this
0x18009f4a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f4ac  cmp     [rcx+8], sil
0x18009f4b0  jz      short loc_18009F4D3
0x18009f4b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f4b7  cmp     [rax+7CCh], ebx
0x18009f4bd  jz      short loc_18009F4D3
0x18009f4bf  mov     r9d, ebx; int
0x18009f4c2  mov     r8d, 24A7h; int
0x18009f4c8  mov     rdx, rdi; char *
0x18009f4cb  mov     rcx, rax; this
0x18009f4ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f4d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f4da  jb      loc_18009FBB5
0x18009f4e0  mov     edx, 0D6h
0x18009f4e5  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18009f4ec  jmp     loc_18009FB9E
0x18009f4f1  mov     rcx, [rbp+57h+var_70]
0x18009f4f5  lea     r8, [rbp+57h+var_50]
0x18009f4f9  lea     rdx, MF_MT_SUBTYPE
0x18009f500  mov     rax, [rcx]
0x18009f503  mov     rax, [rax+50h]
0x18009f507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f50c  mov     ebx, eax
0x18009f50e  test    eax, eax
0x18009f510  jns     loc_18009F5A1
0x18009f516  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f51d  test    rcx, rcx
0x18009f520  jnz     short loc_18009F563
0x18009f522  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f528  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f52f  mov     rcx, rax
0x18009f532  test    rax, rax
0x18009f535  jz      short loc_18009F555
0x18009f537  mov     rax, [rax]
0x18009f53a  mov     edx, 7F0h
0x18009f53f  mov     rax, [rax+8]
0x18009f543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f548  test    eax, eax
0x18009f54a  jz      short loc_18009F555
0x18009f54c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f553  jmp     short loc_18009F563
0x18009f555  lea     rcx, qword_1801B07E0; this
0x18009f55c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f563  cmp     [rcx+8], sil
0x18009f567  jz      short loc_18009F58A
0x18009f569  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f56e  cmp     [rax+7CCh], ebx
0x18009f574  jz      short loc_18009F58A
0x18009f576  mov     r9d, ebx; int
0x18009f579  mov     r8d, 24A9h; int
0x18009f57f  mov     rdx, rdi; char *
0x18009f582  mov     rcx, rax; this
0x18009f585  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f58a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f591  jb      loc_18009FBB5
0x18009f597  mov     edx, 0D7h
0x18009f59c  jmp     loc_18009F4E5
0x18009f5a1  mov     rcx, [rbp+57h+var_78]
0x18009f5a5  test    rcx, rcx
0x18009f5a8  jz      loc_18009F65A
0x18009f5ae  mov     rax, [rcx]
0x18009f5b1  lea     r8, [rbp+57h+var_60]
0x18009f5b5  lea     rdx, MF_MT_SUBTYPE
0x18009f5bc  mov     rax, [rax+50h]
0x18009f5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f5c5  mov     ebx, eax
0x18009f5c7  test    eax, eax
0x18009f5c9  jns     loc_18009F666
0x18009f5cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f5d6  test    rcx, rcx
0x18009f5d9  jnz     short loc_18009F61C
0x18009f5db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f5e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f5e8  mov     rcx, rax
0x18009f5eb  test    rax, rax
0x18009f5ee  jz      short loc_18009F60E
0x18009f5f0  mov     rax, [rax]
0x18009f5f3  mov     edx, 7F0h
0x18009f5f8  mov     rax, [rax+8]
0x18009f5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f601  test    eax, eax
0x18009f603  jz      short loc_18009F60E
0x18009f605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f60c  jmp     short loc_18009F61C
0x18009f60e  lea     rcx, qword_1801B07E0; this
0x18009f615  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f61c  cmp     [rcx+8], sil
0x18009f620  jz      short loc_18009F643
0x18009f622  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f627  cmp     [rax+7CCh], ebx
0x18009f62d  jz      short loc_18009F643
0x18009f62f  mov     r9d, ebx; int
0x18009f632  mov     r8d, 24ADh; int
0x18009f638  mov     rdx, rdi; char *
0x18009f63b  mov     rcx, rax; this
0x18009f63e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f643  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f64a  jb      loc_18009FBB5
0x18009f650  mov     edx, 0D8h
0x18009f655  jmp     loc_18009F4E5
0x18009f65a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18009f661  movdqu  [rbp+57h+var_60], xmm0
0x18009f666  lea     r9, [rbp+57h+var_68]
0x18009f66a  lea     r8, [rbp+57h+var_60]
0x18009f66e  lea     rdx, [rbp+57h+var_50]
0x18009f672  call    MF__DLNA__GetPotentialDLNAProfiles
0x18009f677  mov     ebx, eax
0x18009f679  test    eax, eax
0x18009f67b  jns     loc_18009F70C
0x18009f681  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f688  test    rcx, rcx
0x18009f68b  jnz     short loc_18009F6CE
0x18009f68d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f693  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f69a  mov     rcx, rax
0x18009f69d  test    rax, rax
0x18009f6a0  jz      short loc_18009F6C0
0x18009f6a2  mov     rax, [rax]
0x18009f6a5  mov     edx, 7F0h
0x18009f6aa  mov     rax, [rax+8]
0x18009f6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6b3  test    eax, eax
0x18009f6b5  jz      short loc_18009F6C0
0x18009f6b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f6be  jmp     short loc_18009F6CE
0x18009f6c0  lea     rcx, qword_1801B07E0; this
0x18009f6c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f6ce  cmp     [rcx+8], sil
0x18009f6d2  jz      short loc_18009F6F5
0x18009f6d4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f6d9  cmp     [rax+7CCh], ebx
0x18009f6df  jz      short loc_18009F6F5
0x18009f6e1  mov     r9d, ebx; int
0x18009f6e4  mov     r8d, 24BAh; int
0x18009f6ea  mov     rdx, rdi; char *
0x18009f6ed  mov     rcx, rax; this
0x18009f6f0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f6f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f6fc  jb      loc_18009FBB5
0x18009f702  mov     edx, 0D9h
0x18009f707  jmp     loc_18009F4E5
0x18009f70c  mov     r15, [rbp+57h+var_68]
0x18009f710  lea     rdi, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18009f717  mov     r14d, esi
0x18009f71a  cmp     r14d, [r15+20h]
0x18009f71e  jnb     loc_18009FAEA
0x18009f724  mov     eax, r14d
0x18009f727  imul    rsi, rax, 70h ; 'p'
0x18009f72b  add     rsi, [r15+28h]
0x18009f72f  cmp     cs:byte_1801B110B, 10h
0x18009f736  jb      short loc_18009F756
0x18009f738  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f73f  mov     edx, 0DAh
0x18009f744  mov     r9, [rsi]
0x18009f747  mov     r8, rdi
0x18009f74a  mov     rcx, [rcx+88h]
0x18009f751  call    WPP_SF_S
0x18009f756  mov     ecx, dword ptr [rbp+57h+var_88]; this
0x18009f759  lea     r8, [rbp+57h+var_8C]; struct MF::DLNA::DLNAProfile *
0x18009f75d  mov     rdx, rsi; unsigned int
0x18009f760  call    ?CheckSystemConstraints@DLNA@MF@@YAJIPEBUDLNAProfile@12@PEAH@Z; MF::DLNA::CheckSystemConstraints(uint,MF::DLNA::DLNAProfile const *,int *)
0x18009f765  xor     edx, edx
0x18009f767  mov     ebx, eax
0x18009f769  test    eax, eax
0x18009f76b  js      loc_18009FA58
0x18009f771  cmp     [rbp+57h+var_8C], edx
0x18009f774  jnz     short loc_18009F78A
0x18009f776  cmp     cs:byte_1801B110B, 10h
0x18009f77d  jb      loc_18009F811
0x18009f783  mov     edx, 0DCh
0x18009f788  jmp     short loc_18009F7FB
0x18009f78a  mov     rcx, [rbp+57h+var_70]
0x18009f78e  lea     r8, [rbp+57h+var_8C]
0x18009f792  mov     rax, [r15+8]
0x18009f796  mov     rdx, rsi
0x18009f799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f79e  xor     edx, edx
0x18009f7a0  mov     ebx, eax
0x18009f7a2  test    eax, eax
0x18009f7a4  js      loc_18009F9C6
0x18009f7aa  cmp     [rbp+57h+var_8C], edx
0x18009f7ad  jnz     short loc_18009F7BF
0x18009f7af  cmp     cs:byte_1801B110B, 10h
0x18009f7b6  jb      short loc_18009F811
0x18009f7b8  mov     edx, 0DEh
0x18009f7bd  jmp     short loc_18009F7FB
0x18009f7bf  mov     rax, [r15+18h]
0x18009f7c3  test    rax, rax
0x18009f7c6  jz      loc_18009F8AB
0x18009f7cc  mov     rcx, [rbp+57h+var_78]
0x18009f7d0  lea     r8, [rbp+57h+var_8C]
0x18009f7d4  mov     rdx, rsi
0x18009f7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f7dc  xor     edx, edx
0x18009f7de  mov     ebx, eax
0x18009f7e0  test    eax, eax
0x18009f7e2  js      short loc_18009F819
0x18009f7e4  cmp     [rbp+57h+var_8C], edx
0x18009f7e7  jnz     loc_18009F8AB
0x18009f7ed  cmp     cs:byte_1801B110B, 10h
0x18009f7f4  jb      short loc_18009F811
0x18009f7f6  mov     edx, 0E0h
0x18009f7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f802  mov     r8, rdi
0x18009f805  mov     rcx, [rcx+88h]
0x18009f80c  call    WPP_SF_
0x18009f811  inc     r14d
0x18009f814  jmp     loc_18009F71A
0x18009f819  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f820  test    rcx, rcx
0x18009f823  jnz     short loc_18009F86A
0x18009f825  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f82b  xor     edx, edx
0x18009f82d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f834  mov     rcx, rax
0x18009f837  test    rax, rax
0x18009f83a  jz      short loc_18009F85C
0x18009f83c  mov     rax, [rax]
0x18009f83f  mov     edx, 7F0h
0x18009f844  mov     rax, [rax+8]
0x18009f848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f84d  xor     edx, edx
0x18009f84f  test    eax, eax
0x18009f851  jz      short loc_18009F85C
0x18009f853  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f85a  jmp     short loc_18009F86A
0x18009f85c  lea     rcx, qword_1801B07E0; this
0x18009f863  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f86a  cmp     [rcx+8], dl
0x18009f86d  jz      short loc_18009F894
0x18009f86f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f874  cmp     [rax+7CCh], ebx
0x18009f87a  jz      short loc_18009F894
0x18009f87c  mov     r9d, ebx; int
0x18009f87f  lea     rdx, aMfgetdlnaprofi; "MFGetDLNAProfileID"
0x18009f886  mov     r8d, 24E0h; int
0x18009f88c  mov     rcx, rax; this
0x18009f88f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f894  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f89b  jb      loc_18009FBB5
  ... truncated ...
```
