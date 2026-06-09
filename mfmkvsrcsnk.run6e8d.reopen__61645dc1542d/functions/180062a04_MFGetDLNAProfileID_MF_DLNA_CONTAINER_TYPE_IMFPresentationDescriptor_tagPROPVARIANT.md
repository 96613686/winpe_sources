# MFGetDLNAProfileID(MF_DLNA_CONTAINER_TYPE,IMFPresentationDescriptor *,tagPROPVARIANT *)

- ea: `0x180062a04`
- end: `0x180063273`
- name: `?MFGetDLNAProfileID@@YAJW4MF_DLNA_CONTAINER_TYPE@@PEAUIMFPresentationDescriptor@@PEAUtagPROPVARIANT@@@Z`
- size: `2159`
- prototype: `int __high(enum MF_DLNA_CONTAINER_TYPE, struct IMFPresentationDescriptor *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004cff0`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000de1c`
- `0x1800202d0`
- `0x1800203f0`
- `0x180020d84`
- `0x180049b7c`
- `0x18004f47c`
- `0x180060c64`
- `0x180061ee4`
- `0x180062148`
- `0x180062a04`
- `0x18006408c`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063229`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x180062f8a`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x180062f8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062aab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062b62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062c1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062ccd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062e6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062fa8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006303d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800630d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063192`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062aab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062b62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062c1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062ccd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062e6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062fa8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006303d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800630d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063192`

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
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v17 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v24 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v30 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    if ( (unsigned __int8)byte_1800D78D3 >= 0x10u )
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
          v58 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      if ( (unsigned __int8)byte_1800D78D3 < 0x10u )
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
          v54 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      if ( (unsigned __int8)byte_1800D78D3 < 0x10u )
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
          v41 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    if ( (unsigned __int8)byte_1800D78D3 < 0x10u )
      continue;
    v37 = 224;
LABEL_64:
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), v37, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
  }
  if ( (unsigned __int8)byte_1800D78D3 >= 8u )
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
        v49 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
  if ( (unsigned __int8)byte_1800D78D3 >= 4u )
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
      v62 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180062a04  mov     [rsp-8+arg_0], rbx
0x180062a09  push    rbp
0x180062a0a  push    rsi
0x180062a0b  push    rdi
0x180062a0c  push    r12
0x180062a0e  push    r13
0x180062a10  push    r14
0x180062a12  push    r15
0x180062a14  lea     rbp, [rsp-27h]
0x180062a19  sub     rsp, 0A0h
0x180062a20  mov     rax, cs:__security_cookie
0x180062a27  xor     rax, rsp
0x180062a2a  mov     [rbp+57h+var_40], rax
0x180062a2e  mov     r13, r8
0x180062a31  lea     rdi, aMfgetdlnaprofi; "MFGetDLNAProfileID"
0x180062a38  mov     rbx, rdx
0x180062a3b  lea     rcx, [rbp+57h+var_90]; this
0x180062a3f  mov     rdx, rdi; char *
0x180062a42  mov     r8d, 2494h; int
0x180062a48  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180062a4d  xor     esi, esi
0x180062a4f  lea     r9, [rbp+57h+var_88]
0x180062a53  xorps   xmm0, xmm0
0x180062a56  mov     [rbp+57h+var_70], rsi
0x180062a5a  xorps   xmm1, xmm1
0x180062a5d  mov     [rbp+57h+var_78], rsi
0x180062a61  xor     eax, eax
0x180062a63  mov     [rbp+57h+var_80], rsi
0x180062a67  movups  xmmword ptr [r13+0], xmm0
0x180062a6c  lea     r8, [rbp+57h+var_78]
0x180062a70  mov     [r13+10h], rax
0x180062a74  lea     rdx, [rbp+57h+var_70]
0x180062a78  mov     [rbp+57h+var_8C], esi
0x180062a7b  mov     rcx, rbx
0x180062a7e  mov     [rbp+57h+var_68], rsi
0x180062a82  movups  [rbp+57h+var_50], xmm0
0x180062a86  mov     r12d, esi
0x180062a89  mov     dword ptr [rbp+57h+var_88], esi
0x180062a8c  movups  [rbp+57h+var_60], xmm1
0x180062a90  call    MF__DLNA__GetStreamInformation
0x180062a95  mov     ebx, eax
0x180062a97  test    eax, eax
0x180062a99  jns     loc_180062B31
0x180062a9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062aa6  test    rcx, rcx
0x180062aa9  jnz     short loc_180062AEC
0x180062aab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062ab1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062ab8  mov     rcx, rax
0x180062abb  test    rax, rax
0x180062abe  jz      short loc_180062ADE
0x180062ac0  mov     rax, [rax]
0x180062ac3  mov     edx, 7F0h
0x180062ac8  mov     rax, [rax+8]
0x180062acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062ad1  test    eax, eax
0x180062ad3  jz      short loc_180062ADE
0x180062ad5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062adc  jmp     short loc_180062AEC
0x180062ade  lea     rcx, qword_1800D6F70; this
0x180062ae5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062aec  cmp     [rcx+8], sil
0x180062af0  jz      short loc_180062B13
0x180062af2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062af7  cmp     [rax+7CCh], ebx
0x180062afd  jz      short loc_180062B13
0x180062aff  mov     r9d, ebx; int
0x180062b02  mov     r8d, 24A7h; int
0x180062b08  mov     rdx, rdi; char *
0x180062b0b  mov     rcx, rax; this
0x180062b0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062b13  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062b1a  jb      loc_180063226
0x180062b20  mov     edx, 0D6h
0x180062b25  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x180062b2c  jmp     loc_18006320F
0x180062b31  mov     rcx, [rbp+57h+var_70]
0x180062b35  lea     r8, [rbp+57h+var_50]
0x180062b39  lea     rdx, MF_MT_SUBTYPE
0x180062b40  mov     rax, [rcx]
0x180062b43  mov     rax, [rax+50h]
0x180062b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b4c  mov     ebx, eax
0x180062b4e  test    eax, eax
0x180062b50  jns     loc_180062BE1
0x180062b56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062b5d  test    rcx, rcx
0x180062b60  jnz     short loc_180062BA3
0x180062b62  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062b68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062b6f  mov     rcx, rax
0x180062b72  test    rax, rax
0x180062b75  jz      short loc_180062B95
0x180062b77  mov     rax, [rax]
0x180062b7a  mov     edx, 7F0h
0x180062b7f  mov     rax, [rax+8]
0x180062b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b88  test    eax, eax
0x180062b8a  jz      short loc_180062B95
0x180062b8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062b93  jmp     short loc_180062BA3
0x180062b95  lea     rcx, qword_1800D6F70; this
0x180062b9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062ba3  cmp     [rcx+8], sil
0x180062ba7  jz      short loc_180062BCA
0x180062ba9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062bae  cmp     [rax+7CCh], ebx
0x180062bb4  jz      short loc_180062BCA
0x180062bb6  mov     r9d, ebx; int
0x180062bb9  mov     r8d, 24A9h; int
0x180062bbf  mov     rdx, rdi; char *
0x180062bc2  mov     rcx, rax; this
0x180062bc5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062bca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062bd1  jb      loc_180063226
0x180062bd7  mov     edx, 0D7h
0x180062bdc  jmp     loc_180062B25
0x180062be1  mov     rcx, [rbp+57h+var_78]
0x180062be5  test    rcx, rcx
0x180062be8  jz      loc_180062C9A
0x180062bee  mov     rax, [rcx]
0x180062bf1  lea     r8, [rbp+57h+var_60]
0x180062bf5  lea     rdx, MF_MT_SUBTYPE
0x180062bfc  mov     rax, [rax+50h]
0x180062c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c05  mov     ebx, eax
0x180062c07  test    eax, eax
0x180062c09  jns     loc_180062CA6
0x180062c0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062c16  test    rcx, rcx
0x180062c19  jnz     short loc_180062C5C
0x180062c1b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062c21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062c28  mov     rcx, rax
0x180062c2b  test    rax, rax
0x180062c2e  jz      short loc_180062C4E
0x180062c30  mov     rax, [rax]
0x180062c33  mov     edx, 7F0h
0x180062c38  mov     rax, [rax+8]
0x180062c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c41  test    eax, eax
0x180062c43  jz      short loc_180062C4E
0x180062c45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062c4c  jmp     short loc_180062C5C
0x180062c4e  lea     rcx, qword_1800D6F70; this
0x180062c55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062c5c  cmp     [rcx+8], sil
0x180062c60  jz      short loc_180062C83
0x180062c62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062c67  cmp     [rax+7CCh], ebx
0x180062c6d  jz      short loc_180062C83
0x180062c6f  mov     r9d, ebx; int
0x180062c72  mov     r8d, 24ADh; int
0x180062c78  mov     rdx, rdi; char *
0x180062c7b  mov     rcx, rax; this
0x180062c7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062c83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062c8a  jb      loc_180063226
0x180062c90  mov     edx, 0D8h
0x180062c95  jmp     loc_180062B25
0x180062c9a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180062ca1  movdqu  [rbp+57h+var_60], xmm0
0x180062ca6  lea     r9, [rbp+57h+var_80]
0x180062caa  lea     r8, [rbp+57h+var_60]
0x180062cae  lea     rdx, [rbp+57h+var_50]
0x180062cb2  call    MF__DLNA__GetPotentialDLNAProfiles
0x180062cb7  mov     ebx, eax
0x180062cb9  test    eax, eax
0x180062cbb  jns     loc_180062D4C
0x180062cc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062cc8  test    rcx, rcx
0x180062ccb  jnz     short loc_180062D0E
0x180062ccd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062cd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062cda  mov     rcx, rax
0x180062cdd  test    rax, rax
0x180062ce0  jz      short loc_180062D00
0x180062ce2  mov     rax, [rax]
0x180062ce5  mov     edx, 7F0h
0x180062cea  mov     rax, [rax+8]
0x180062cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062cf3  test    eax, eax
0x180062cf5  jz      short loc_180062D00
0x180062cf7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062cfe  jmp     short loc_180062D0E
0x180062d00  lea     rcx, qword_1800D6F70; this
0x180062d07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062d0e  cmp     [rcx+8], sil
0x180062d12  jz      short loc_180062D35
0x180062d14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062d19  cmp     [rax+7CCh], ebx
0x180062d1f  jz      short loc_180062D35
0x180062d21  mov     r9d, ebx; int
0x180062d24  mov     r8d, 24BAh; int
0x180062d2a  mov     rdx, rdi; char *
0x180062d2d  mov     rcx, rax; this
0x180062d30  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062d35  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062d3c  jb      loc_180063226
0x180062d42  mov     edx, 0D9h
0x180062d47  jmp     loc_180062B25
0x180062d4c  mov     r15, [rbp+57h+var_80]
0x180062d50  lea     rdi, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x180062d57  mov     r14d, esi
0x180062d5a  cmp     r14d, [r15+20h]
0x180062d5e  jnb     loc_18006315B
0x180062d64  mov     eax, r14d
0x180062d67  imul    rsi, rax, 70h ; 'p'
0x180062d6b  add     rsi, [r15+28h]
0x180062d6f  cmp     cs:byte_1800D78D3, 10h
0x180062d76  jb      short loc_180062D96
0x180062d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d7f  mov     edx, 0DAh
0x180062d84  mov     r9, [rsi]
0x180062d87  mov     r8, rdi
0x180062d8a  mov     rcx, [rcx+88h]
0x180062d91  call    WPP_SF_S
0x180062d96  mov     ecx, dword ptr [rbp+57h+var_88]; this
0x180062d99  lea     r8, [rbp+57h+var_8C]; struct MF::DLNA::DLNAProfile *
0x180062d9d  mov     rdx, rsi; unsigned int
0x180062da0  call    ?CheckSystemConstraints@DLNA@MF@@YAJIPEBUDLNAProfile@12@PEAH@Z; MF::DLNA::CheckSystemConstraints(uint,MF::DLNA::DLNAProfile const *,int *)
0x180062da5  xor     r9d, r9d
0x180062da8  mov     ebx, eax
0x180062daa  test    eax, eax
0x180062dac  js      loc_1800630C6
0x180062db2  cmp     [rbp+57h+var_8C], r9d
0x180062db6  jnz     short loc_180062DCC
0x180062db8  cmp     cs:byte_1800D78D3, 10h
0x180062dbf  jb      loc_180062E57
0x180062dc5  mov     edx, 0DCh
0x180062dca  jmp     short loc_180062E41
0x180062dcc  mov     rcx, [rbp+57h+var_70]
0x180062dd0  lea     r8, [rbp+57h+var_8C]
0x180062dd4  mov     rax, [r15+8]
0x180062dd8  mov     rdx, rsi
0x180062ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062de0  xor     r9d, r9d
0x180062de3  mov     ebx, eax
0x180062de5  test    eax, eax
0x180062de7  js      loc_180063031
0x180062ded  cmp     [rbp+57h+var_8C], r9d
0x180062df1  jnz     short loc_180062E03
0x180062df3  cmp     cs:byte_1800D78D3, 10h
0x180062dfa  jb      short loc_180062E57
0x180062dfc  mov     edx, 0DEh
0x180062e01  jmp     short loc_180062E41
0x180062e03  mov     rax, [r15+18h]
0x180062e07  test    rax, rax
0x180062e0a  jz      loc_180062EF4
0x180062e10  mov     rcx, [rbp+57h+var_78]
0x180062e14  lea     r8, [rbp+57h+var_8C]
0x180062e18  mov     rdx, rsi
0x180062e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e20  xor     r9d, r9d
0x180062e23  mov     ebx, eax
0x180062e25  test    eax, eax
0x180062e27  js      short loc_180062E5F
0x180062e29  cmp     [rbp+57h+var_8C], r9d
0x180062e2d  jnz     loc_180062EF4
0x180062e33  cmp     cs:byte_1800D78D3, 10h
0x180062e3a  jb      short loc_180062E57
0x180062e3c  mov     edx, 0E0h
0x180062e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e48  mov     r8, rdi
0x180062e4b  mov     rcx, [rcx+88h]
0x180062e52  call    WPP_SF_
0x180062e57  inc     r14d
0x180062e5a  jmp     loc_180062D5A
0x180062e5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062e66  test    rcx, rcx
0x180062e69  jnz     short loc_180062EB2
0x180062e6b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062e71  xor     r9d, r9d
0x180062e74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062e7b  mov     rcx, rax
0x180062e7e  test    rax, rax
0x180062e81  jz      short loc_180062EA4
0x180062e83  mov     rax, [rax]
0x180062e86  mov     edx, 7F0h
0x180062e8b  mov     rax, [rax+8]
0x180062e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e94  xor     r9d, r9d
0x180062e97  test    eax, eax
0x180062e99  jz      short loc_180062EA4
0x180062e9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062ea2  jmp     short loc_180062EB2
0x180062ea4  lea     rcx, qword_1800D6F70; this
0x180062eab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062eb2  cmp     [rcx+8], r9b
0x180062eb6  jz      short loc_180062EDD
0x180062eb8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062ebd  cmp     [rax+7CCh], ebx
0x180062ec3  jz      short loc_180062EDD
0x180062ec5  mov     r9d, ebx; int
0x180062ec8  lea     rdx, aMfgetdlnaprofi; "MFGetDLNAProfileID"
0x180062ecf  mov     r8d, 24E0h; int
0x180062ed5  mov     rcx, rax; this
0x180062ed8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062edd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062ee4  jb      loc_180063226
  ... truncated ...
```
