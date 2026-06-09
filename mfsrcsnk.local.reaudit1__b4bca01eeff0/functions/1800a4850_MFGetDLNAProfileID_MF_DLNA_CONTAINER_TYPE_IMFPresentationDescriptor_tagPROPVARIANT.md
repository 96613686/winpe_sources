# MFGetDLNAProfileID(MF_DLNA_CONTAINER_TYPE,IMFPresentationDescriptor *,tagPROPVARIANT *)

- ea: `0x1800a4850`
- end: `0x1800a50d1`
- name: `?MFGetDLNAProfileID@@YAJW4MF_DLNA_CONTAINER_TYPE@@PEAUIMFPresentationDescriptor@@PEAUtagPROPVARIANT@@@Z`
- size: `2177`
- prototype: `int __high(enum MF_DLNA_CONTAINER_TYPE, struct IMFPresentationDescriptor *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801657c0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180078758`
- `0x180079680`
- `0x1800a4850`
- `0x1800cb104`
- `0x180110ed0`
- `0x18011cbac`
- `0x180128f04`
- `0x18016a15c`
- `0x180179854`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a48f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a49b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4a73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4b2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4cc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4db3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4e88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4fe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a48f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a49b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4a73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4b2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4cc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4db3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4e88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4fe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5080`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x1800a4e69`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x1800a4e69`

## pseudocode

```c
__int64 __fastcall MFGetDLNAProfileID(__int64 a1, __int64 a2, PROPVARIANT *a3)
{
  WCHAR *v5; // r12
  __int64 v6; // rdx
  HRESULT StreamInformation; // ebx
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  int *v22; // r9
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // r15
  unsigned int i; // r14d
  _QWORD *v28; // rsi
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rcx
  __int64 (__fastcall *v33)(__int64, _QWORD *, int *); // rax
  int v34; // eax
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // r9
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  _BYTE v52[4]; // [rsp+30h] [rbp-39h] BYREF
  int v53; // [rsp+34h] [rbp-35h] BYREF
  MF::DLNA *v54; // [rsp+38h] [rbp-31h] BYREF
  PCWSTR psz; // [rsp+40h] [rbp-29h]
  __int64 v56; // [rsp+48h] [rbp-21h] BYREF
  __int64 v57; // [rsp+50h] [rbp-19h] BYREF
  __int64 v58; // [rsp+58h] [rbp-11h] BYREF
  GUID v59; // [rsp+60h] [rbp-9h] BYREF
  __int128 v60; // [rsp+70h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v52, "MFGetDLNAProfileID", 9364);
  v57 = 0;
  v56 = 0;
  v58 = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v53 = 0;
  psz = 0;
  v60 = 0;
  v5 = 0;
  LODWORD(v54) = 0;
  v59 = 0;
  StreamInformation = MF::DLNA::GetStreamInformation(a2, &v57, &v56, &v54);
  if ( StreamInformation < 0 )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamInformation )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFGetDLNAProfileID", 9383, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_127;
    v11 = 214;
    goto LABEL_126;
  }
  StreamInformation = (*(__int64 (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v57 + 80LL))(
                        v57,
                        &MF_MT_SUBTYPE,
                        &v60);
  if ( StreamInformation < 0 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v15, "MFGetDLNAProfileID", 9385, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_127;
    v11 = 215;
    goto LABEL_126;
  }
  v16 = v56;
  if ( v56 )
  {
    StreamInformation = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v56 + 80LL))(
                          v56,
                          &MF_MT_SUBTYPE,
                          &v59);
    if ( StreamInformation < 0 )
    {
      v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v20, "MFGetDLNAProfileID", 9389, StreamInformation);
      }
      if ( !g_wppLevels )
        goto LABEL_127;
      v11 = 216;
      goto LABEL_126;
    }
  }
  else
  {
    v59 = GUID_00000000_0000_0000_0000_000000000000;
  }
  StreamInformation = MF::DLNA::GetPotentialDLNAProfiles(v16, &v60, &v59, &v58);
  if ( StreamInformation < 0 )
  {
    v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v25, "MFGetDLNAProfileID", 9402, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_127;
    v11 = 217;
LABEL_126:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
      0,
      StreamInformation);
    goto LABEL_127;
  }
  v26 = v58;
  for ( i = 0; i < *(_DWORD *)(v26 + 32); ++i )
  {
    v28 = (_QWORD *)(*(_QWORD *)(v26 + 40) + 112LL * i);
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 218, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v28);
    v29 = MF::DLNA::CheckSystemConstraints(
            (MF::DLNA *)(unsigned int)v54,
            (unsigned int)v28,
            (const struct MF::DLNA::DLNAProfile *)&v53,
            v22);
    v21 = 0;
    StreamInformation = v29;
    if ( v29 < 0 )
    {
      v45 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v47, "MFGetDLNAProfileID", 9416, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v11 = 219;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( !v53 )
    {
      if ( (unsigned __int8)byte_1801BA10B < 0x10u )
        continue;
      v30 = 220;
      goto LABEL_64;
    }
    v31 = (*(__int64 (__fastcall **)(__int64, _QWORD *, int *))(v26 + 8))(v57, v28, &v53);
    v21 = 0;
    StreamInformation = v31;
    if ( v31 < 0 )
    {
      v42 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v44, "MFGetDLNAProfileID", 9427, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v11 = 221;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( !v53 )
    {
      if ( (unsigned __int8)byte_1801BA10B < 0x10u )
        continue;
      v30 = 222;
      goto LABEL_64;
    }
    v33 = *(__int64 (__fastcall **)(__int64, _QWORD *, int *))(v26 + 24);
    if ( !v33 )
      goto LABEL_76;
    v34 = v33(v56, v28, &v53);
    v21 = 0;
    StreamInformation = v34;
    if ( v34 < 0 )
    {
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v37, "MFGetDLNAProfileID", 9440, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v11 = 223;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( v53 )
    {
LABEL_76:
      if ( (unsigned __int8)byte_1801BA10B >= 8u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 225, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v28);
      v38 = -1;
      do
        ++v38;
      while ( *(_WORD *)(*v28 + 2 * v38) );
      StreamInformation = _AllocStringWorker<CTCoAllocPolicy>(v32, v21);
      if ( StreamInformation < 0 )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v40;
          if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
          {
            v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v39 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v39 + 8) )
        {
          v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
          if ( *((_DWORD *)v41 + 499) != StreamInformation )
            CallStackContext::TraceFailure(v41, "MFGetDLNAProfileID", 9455, StreamInformation);
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
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
    {
      v30 = 224;
LABEL_64:
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), v30, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
      continue;
    }
  }
  if ( (unsigned __int8)byte_1801BA10B >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 227, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
  v48 = (wchar_t *)CallStackTracing::s_wpInstance;
  StreamInformation = -1072863756;
  if ( !CallStackTracing::s_wpInstance )
  {
    v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
    CallStackTracing::s_wpInstance = v49;
    if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
    {
      v48 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v48 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v48 + 8) )
  {
    v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
    if ( *((_DWORD *)v50 + 499) != -1072863756 )
      CallStackContext::TraceFailure(v50, "MFGetDLNAProfileID", 9463, -1072863756);
  }
  if ( g_wppLevels )
  {
    v11 = 228;
    goto LABEL_126;
  }
LABEL_127:
  CoTaskMemFree(v5);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v56);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v57);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
  return (unsigned int)StreamInformation;
}

```

## disassembly

```asm
0x1800a4850  mov     [rsp-8+arg_0], rbx
0x1800a4855  push    rbp
0x1800a4856  push    rsi
0x1800a4857  push    rdi
0x1800a4858  push    r12
0x1800a485a  push    r13
0x1800a485c  push    r14
0x1800a485e  push    r15
0x1800a4860  lea     rbp, [rsp-27h]
0x1800a4865  sub     rsp, 90h
0x1800a486c  mov     rax, cs:__security_cookie
0x1800a4873  xor     rax, rsp
0x1800a4876  mov     [rbp+57h+var_40], rax
0x1800a487a  mov     r13, r8
0x1800a487d  lea     rdi, aMfgetdlnaprofi; "MFGetDLNAProfileID"
0x1800a4884  mov     rbx, rdx
0x1800a4887  lea     rcx, [rbp+57h+var_90]; this
0x1800a488b  mov     rdx, rdi; char *
0x1800a488e  mov     r8d, 2494h; int
0x1800a4894  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a4899  xor     esi, esi
0x1800a489b  lea     r9, [rbp+57h+var_88]
0x1800a489f  xorps   xmm0, xmm0
0x1800a48a2  mov     [rbp+57h+var_70], rsi
0x1800a48a6  xorps   xmm1, xmm1
0x1800a48a9  mov     [rbp+57h+var_78], rsi
0x1800a48ad  xor     eax, eax
0x1800a48af  mov     [rbp+57h+var_68], rsi
0x1800a48b3  movups  xmmword ptr [r13+0], xmm0
0x1800a48b8  lea     r8, [rbp+57h+var_78]
0x1800a48bc  mov     [r13+10h], rax
0x1800a48c0  lea     rdx, [rbp+57h+var_70]
0x1800a48c4  mov     [rbp+57h+var_8C], esi
0x1800a48c7  mov     rcx, rbx
0x1800a48ca  mov     [rbp+57h+psz], rsi
0x1800a48ce  movups  [rbp+57h+var_50], xmm0
0x1800a48d2  mov     r12d, esi
0x1800a48d5  mov     dword ptr [rbp+57h+var_88], esi
0x1800a48d8  movups  [rbp+57h+var_60], xmm1
0x1800a48dc  call    MF__DLNA__GetStreamInformation
0x1800a48e1  mov     ebx, eax
0x1800a48e3  test    eax, eax
0x1800a48e5  jns     loc_1800A4983
0x1800a48eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a48f2  test    rcx, rcx
0x1800a48f5  jnz     short loc_1800A493E
0x1800a48f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a48fe  nop     dword ptr [rax+rax+00h]
0x1800a4903  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a490a  mov     rcx, rax
0x1800a490d  test    rax, rax
0x1800a4910  jz      short loc_1800A4930
0x1800a4912  mov     rax, [rax]
0x1800a4915  mov     edx, 7F0h
0x1800a491a  mov     rax, [rax+8]
0x1800a491e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4923  test    eax, eax
0x1800a4925  jz      short loc_1800A4930
0x1800a4927  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a492e  jmp     short loc_1800A493E
0x1800a4930  lea     rcx, qword_1801B97E0; this
0x1800a4937  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a493e  cmp     [rcx+8], sil
0x1800a4942  jz      short loc_1800A4965
0x1800a4944  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4949  cmp     [rax+7CCh], ebx
0x1800a494f  jz      short loc_1800A4965
0x1800a4951  mov     r9d, ebx; int
0x1800a4954  mov     r8d, 24A7h; int
0x1800a495a  mov     rdx, rdi; char *
0x1800a495d  mov     rcx, rax; this
0x1800a4960  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4965  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a496c  jb      loc_1800A507D
0x1800a4972  mov     edx, 0D6h
0x1800a4977  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800a497e  jmp     loc_1800A5066
0x1800a4983  mov     rcx, [rbp+57h+var_70]
0x1800a4987  lea     r8, [rbp+57h+var_50]
0x1800a498b  lea     rdx, MF_MT_SUBTYPE
0x1800a4992  mov     rax, [rcx]
0x1800a4995  mov     rax, [rax+50h]
0x1800a4999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a499e  mov     ebx, eax
0x1800a49a0  test    eax, eax
0x1800a49a2  jns     loc_1800A4A39
0x1800a49a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a49af  test    rcx, rcx
0x1800a49b2  jnz     short loc_1800A49FB
0x1800a49b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a49bb  nop     dword ptr [rax+rax+00h]
0x1800a49c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a49c7  mov     rcx, rax
0x1800a49ca  test    rax, rax
0x1800a49cd  jz      short loc_1800A49ED
0x1800a49cf  mov     rax, [rax]
0x1800a49d2  mov     edx, 7F0h
0x1800a49d7  mov     rax, [rax+8]
0x1800a49db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a49e0  test    eax, eax
0x1800a49e2  jz      short loc_1800A49ED
0x1800a49e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a49eb  jmp     short loc_1800A49FB
0x1800a49ed  lea     rcx, qword_1801B97E0; this
0x1800a49f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a49fb  cmp     [rcx+8], sil
0x1800a49ff  jz      short loc_1800A4A22
0x1800a4a01  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4a06  cmp     [rax+7CCh], ebx
0x1800a4a0c  jz      short loc_1800A4A22
0x1800a4a0e  mov     r9d, ebx; int
0x1800a4a11  mov     r8d, 24A9h; int
0x1800a4a17  mov     rdx, rdi; char *
0x1800a4a1a  mov     rcx, rax; this
0x1800a4a1d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4a22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4a29  jb      loc_1800A507D
0x1800a4a2f  mov     edx, 0D7h
0x1800a4a34  jmp     loc_1800A4977
0x1800a4a39  mov     rcx, [rbp+57h+var_78]
0x1800a4a3d  test    rcx, rcx
0x1800a4a40  jz      loc_1800A4AF8
0x1800a4a46  mov     rax, [rcx]
0x1800a4a49  lea     r8, [rbp+57h+var_60]
0x1800a4a4d  lea     rdx, MF_MT_SUBTYPE
0x1800a4a54  mov     rax, [rax+50h]
0x1800a4a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4a5d  mov     ebx, eax
0x1800a4a5f  test    eax, eax
0x1800a4a61  jns     loc_1800A4B04
0x1800a4a67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4a6e  test    rcx, rcx
0x1800a4a71  jnz     short loc_1800A4ABA
0x1800a4a73  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a4a7a  nop     dword ptr [rax+rax+00h]
0x1800a4a7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4a86  mov     rcx, rax
0x1800a4a89  test    rax, rax
0x1800a4a8c  jz      short loc_1800A4AAC
0x1800a4a8e  mov     rax, [rax]
0x1800a4a91  mov     edx, 7F0h
0x1800a4a96  mov     rax, [rax+8]
0x1800a4a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4a9f  test    eax, eax
0x1800a4aa1  jz      short loc_1800A4AAC
0x1800a4aa3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4aaa  jmp     short loc_1800A4ABA
0x1800a4aac  lea     rcx, qword_1801B97E0; this
0x1800a4ab3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4aba  cmp     [rcx+8], sil
0x1800a4abe  jz      short loc_1800A4AE1
0x1800a4ac0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4ac5  cmp     [rax+7CCh], ebx
0x1800a4acb  jz      short loc_1800A4AE1
0x1800a4acd  mov     r9d, ebx; int
0x1800a4ad0  mov     r8d, 24ADh; int
0x1800a4ad6  mov     rdx, rdi; char *
0x1800a4ad9  mov     rcx, rax; this
0x1800a4adc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4ae1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4ae8  jb      loc_1800A507D
0x1800a4aee  mov     edx, 0D8h
0x1800a4af3  jmp     loc_1800A4977
0x1800a4af8  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800a4aff  movdqu  [rbp+57h+var_60], xmm0
0x1800a4b04  lea     r9, [rbp+57h+var_68]
0x1800a4b08  lea     r8, [rbp+57h+var_60]
0x1800a4b0c  lea     rdx, [rbp+57h+var_50]
0x1800a4b10  call    MF__DLNA__GetPotentialDLNAProfiles
0x1800a4b15  mov     ebx, eax
0x1800a4b17  test    eax, eax
0x1800a4b19  jns     loc_1800A4BB0
0x1800a4b1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4b26  test    rcx, rcx
0x1800a4b29  jnz     short loc_1800A4B72
0x1800a4b2b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a4b32  nop     dword ptr [rax+rax+00h]
0x1800a4b37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4b3e  mov     rcx, rax
0x1800a4b41  test    rax, rax
0x1800a4b44  jz      short loc_1800A4B64
0x1800a4b46  mov     rax, [rax]
0x1800a4b49  mov     edx, 7F0h
0x1800a4b4e  mov     rax, [rax+8]
0x1800a4b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b57  test    eax, eax
0x1800a4b59  jz      short loc_1800A4B64
0x1800a4b5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4b62  jmp     short loc_1800A4B72
0x1800a4b64  lea     rcx, qword_1801B97E0; this
0x1800a4b6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4b72  cmp     [rcx+8], sil
0x1800a4b76  jz      short loc_1800A4B99
0x1800a4b78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4b7d  cmp     [rax+7CCh], ebx
0x1800a4b83  jz      short loc_1800A4B99
0x1800a4b85  mov     r9d, ebx; int
0x1800a4b88  mov     r8d, 24BAh; int
0x1800a4b8e  mov     rdx, rdi; char *
0x1800a4b91  mov     rcx, rax; this
0x1800a4b94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4b99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4ba0  jb      loc_1800A507D
0x1800a4ba6  mov     edx, 0D9h
0x1800a4bab  jmp     loc_1800A4977
0x1800a4bb0  mov     r15, [rbp+57h+var_68]
0x1800a4bb4  lea     rdi, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800a4bbb  mov     r14d, esi
0x1800a4bbe  cmp     r14d, [r15+20h]
0x1800a4bc2  jnb     loc_1800A4FAC
0x1800a4bc8  mov     eax, r14d
0x1800a4bcb  imul    rsi, rax, 70h ; 'p'
0x1800a4bcf  add     rsi, [r15+28h]
0x1800a4bd3  cmp     cs:byte_1801BA10B, 10h
0x1800a4bda  jb      short loc_1800A4BFA
0x1800a4bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4be3  mov     edx, 0DAh
0x1800a4be8  mov     r9, [rsi]
0x1800a4beb  mov     r8, rdi
0x1800a4bee  mov     rcx, [rcx+88h]
0x1800a4bf5  call    WPP_SF_S
0x1800a4bfa  mov     ecx, dword ptr [rbp+57h+var_88]; this
0x1800a4bfd  lea     r8, [rbp+57h+var_8C]; struct MF::DLNA::DLNAProfile *
0x1800a4c01  mov     rdx, rsi; unsigned int
0x1800a4c04  call    ?CheckSystemConstraints@DLNA@MF@@YAJIPEBUDLNAProfile@12@PEAH@Z; MF::DLNA::CheckSystemConstraints(uint,MF::DLNA::DLNAProfile const *,int *)
0x1800a4c09  xor     edx, edx
0x1800a4c0b  mov     ebx, eax
0x1800a4c0d  test    eax, eax
0x1800a4c0f  js      loc_1800A4F14
0x1800a4c15  cmp     [rbp+57h+var_8C], edx
0x1800a4c18  jnz     short loc_1800A4C2E
0x1800a4c1a  cmp     cs:byte_1801BA10B, 10h
0x1800a4c21  jb      loc_1800A4CB5
0x1800a4c27  mov     edx, 0DCh
0x1800a4c2c  jmp     short loc_1800A4C9F
0x1800a4c2e  mov     rcx, [rbp+57h+var_70]
0x1800a4c32  lea     r8, [rbp+57h+var_8C]
0x1800a4c36  mov     rax, [r15+8]
0x1800a4c3a  mov     rdx, rsi
0x1800a4c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4c42  xor     edx, edx
0x1800a4c44  mov     ebx, eax
0x1800a4c46  test    eax, eax
0x1800a4c48  js      loc_1800A4E7C
0x1800a4c4e  cmp     [rbp+57h+var_8C], edx
0x1800a4c51  jnz     short loc_1800A4C63
0x1800a4c53  cmp     cs:byte_1801BA10B, 10h
0x1800a4c5a  jb      short loc_1800A4CB5
0x1800a4c5c  mov     edx, 0DEh
0x1800a4c61  jmp     short loc_1800A4C9F
0x1800a4c63  mov     rax, [r15+18h]
0x1800a4c67  test    rax, rax
0x1800a4c6a  jz      loc_1800A4D55
0x1800a4c70  mov     rcx, [rbp+57h+var_78]
0x1800a4c74  lea     r8, [rbp+57h+var_8C]
0x1800a4c78  mov     rdx, rsi
0x1800a4c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4c80  xor     edx, edx
0x1800a4c82  mov     ebx, eax
0x1800a4c84  test    eax, eax
0x1800a4c86  js      short loc_1800A4CBD
0x1800a4c88  cmp     [rbp+57h+var_8C], edx
0x1800a4c8b  jnz     loc_1800A4D55
0x1800a4c91  cmp     cs:byte_1801BA10B, 10h
0x1800a4c98  jb      short loc_1800A4CB5
0x1800a4c9a  mov     edx, 0E0h
0x1800a4c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4ca6  mov     r8, rdi
0x1800a4ca9  mov     rcx, [rcx+88h]
0x1800a4cb0  call    WPP_SF_
0x1800a4cb5  inc     r14d
0x1800a4cb8  jmp     loc_1800A4BBE
0x1800a4cbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4cc4  test    rcx, rcx
0x1800a4cc7  jnz     short loc_1800A4D14
0x1800a4cc9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a4cd0  nop     dword ptr [rax+rax+00h]
0x1800a4cd5  xor     edx, edx
0x1800a4cd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4cde  mov     rcx, rax
0x1800a4ce1  test    rax, rax
0x1800a4ce4  jz      short loc_1800A4D06
0x1800a4ce6  mov     rax, [rax]
0x1800a4ce9  mov     edx, 7F0h
0x1800a4cee  mov     rax, [rax+8]
0x1800a4cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4cf7  xor     edx, edx
0x1800a4cf9  test    eax, eax
0x1800a4cfb  jz      short loc_1800A4D06
0x1800a4cfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4d04  jmp     short loc_1800A4D14
0x1800a4d06  lea     rcx, qword_1801B97E0; this
0x1800a4d0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4d14  cmp     [rcx+8], dl
0x1800a4d17  jz      short loc_1800A4D3E
0x1800a4d19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4d1e  cmp     [rax+7CCh], ebx
0x1800a4d24  jz      short loc_1800A4D3E
0x1800a4d26  mov     r9d, ebx; int
0x1800a4d29  lea     rdx, aMfgetdlnaprofi; "MFGetDLNAProfileID"
  ... truncated ...
```
