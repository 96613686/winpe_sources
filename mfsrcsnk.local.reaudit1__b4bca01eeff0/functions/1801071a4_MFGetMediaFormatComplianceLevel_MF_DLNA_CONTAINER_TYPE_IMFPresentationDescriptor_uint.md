# MFGetMediaFormatComplianceLevel(MF_DLNA_CONTAINER_TYPE,IMFPresentationDescriptor *,uint *)

- ea: `0x1801071a4`
- end: `0x180107913`
- name: `?MFGetMediaFormatComplianceLevel@@YAJW4MF_DLNA_CONTAINER_TYPE@@PEAUIMFPresentationDescriptor@@PEAI@Z`
- size: `1903`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180077f4c`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180078758`
- `0x180079680`
- `0x1800a6cf0`
- `0x1801071a4`
- `0x180110ed0`
- `0x18011cbac`
- `0x18016a15c`
- `0x180179854`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010723e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801072fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801073ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180107472`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010760b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180107706`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180107756`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801077eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010723e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801072fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801073ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180107472`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010760b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180107706`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180107756`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801077eb`

## string_xrefs

- `0x1801071cf`: `MFGetMediaFormatComplianceLevel`
- `0x180107668`: `MFGetMediaFormatComplianceLevel`
- `0x1801077b3`: `MFGetMediaFormatComplianceLevel`
- `0x180107848`: `MFGetMediaFormatComplianceLevel`
- `0x180107891`: `MFGetMediaFormatComplianceLevel`

## pseudocode

```c
__int64 __fastcall MFGetMediaFormatComplianceLevel(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v5; // rdx
  int StreamInformation; // ebx
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  int *v21; // r9
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // r15
  unsigned int i; // esi
  _QWORD *v27; // r14
  __int64 v28; // rdx
  __int64 (__fastcall *v29)(__int64, _QWORD *, int *); // rax
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct CallStackContext *v41; // rax
  _BYTE v43[4]; // [rsp+30h] [rbp-50h] BYREF
  int v44; // [rsp+34h] [rbp-4Ch] BYREF
  MF::DLNA *v45; // [rsp+38h] [rbp-48h] BYREF
  __int64 v46; // [rsp+40h] [rbp-40h] BYREF
  __int64 v47; // [rsp+48h] [rbp-38h] BYREF
  __int64 v48; // [rsp+50h] [rbp-30h] BYREF
  GUID v49; // [rsp+58h] [rbp-28h] BYREF
  __int128 v50; // [rsp+68h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v43, "MFGetMediaFormatComplianceLevel", 9482);
  v47 = 0;
  v46 = 0;
  v48 = 0;
  v44 = 0;
  LODWORD(v45) = 0;
  v50 = 0;
  *a3 = 0;
  v49 = 0;
  StreamInformation = MF::DLNA::GetStreamInformation(a2, &v47, &v46, &v45);
  if ( StreamInformation < 0 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamInformation )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MFGetMediaFormatComplianceLevel",
          9500,
          StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_113;
    v10 = 230;
    goto LABEL_112;
  }
  StreamInformation = (*(__int64 (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v47 + 80LL))(
                        v47,
                        &MF_MT_SUBTYPE,
                        &v50);
  if ( StreamInformation < 0 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v14, "MFGetMediaFormatComplianceLevel", 9502, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_113;
    v10 = 231;
    goto LABEL_112;
  }
  v15 = v46;
  if ( v46 )
  {
    StreamInformation = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v46 + 80LL))(
                          v46,
                          &MF_MT_SUBTYPE,
                          &v49);
    if ( StreamInformation < 0 )
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v19, "MFGetMediaFormatComplianceLevel", 9506, StreamInformation);
      }
      if ( !g_wppLevels )
        goto LABEL_113;
      v10 = 232;
      goto LABEL_112;
    }
  }
  else
  {
    v49 = GUID_00000000_0000_0000_0000_000000000000;
  }
  StreamInformation = MF::DLNA::GetMediaFormatComplianceProfiles(v15, &v50, &v49, &v48);
  if ( StreamInformation < 0 )
  {
    v22 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != StreamInformation )
        CallStackContext::TraceFailure(v24, "MFGetMediaFormatComplianceLevel", 9519, StreamInformation);
    }
    if ( !g_wppLevels )
      goto LABEL_113;
    v10 = 233;
LABEL_112:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
      0,
      StreamInformation);
    goto LABEL_113;
  }
  v25 = v48;
  for ( i = 0; i < *(_DWORD *)(v25 + 32); ++i )
  {
    v27 = (_QWORD *)(*(_QWORD *)(v25 + 40) + 112LL * i);
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 234, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v27);
    StreamInformation = MF::DLNA::CheckSystemConstraints(
                          (MF::DLNA *)(unsigned int)v45,
                          (unsigned int)v27,
                          (const struct MF::DLNA::DLNAProfile *)&v44,
                          v21);
    if ( StreamInformation < 0 )
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v40, "MFGetMediaFormatComplianceLevel", 9533, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v10 = 235;
        goto LABEL_112;
      }
      goto LABEL_113;
    }
    if ( !v44 )
    {
      if ( (unsigned __int8)byte_1801BA10B < 0x10u )
        continue;
      v28 = 236;
      goto LABEL_64;
    }
    StreamInformation = (*(__int64 (__fastcall **)(__int64, _QWORD *, int *))(v25 + 8))(v47, v27, &v44);
    if ( StreamInformation < 0 )
    {
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
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
          CallStackContext::TraceFailure(v37, "MFGetMediaFormatComplianceLevel", 9544, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v10 = 237;
        goto LABEL_112;
      }
      goto LABEL_113;
    }
    if ( !v44 )
    {
      if ( (unsigned __int8)byte_1801BA10B < 0x10u )
        continue;
      v28 = 238;
      goto LABEL_64;
    }
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD *, int *))(v25 + 24);
    if ( !v29 )
      goto LABEL_76;
    StreamInformation = v29(v46, v27, &v44);
    if ( StreamInformation < 0 )
    {
      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v32 + 499) != StreamInformation )
          CallStackContext::TraceFailure(v32, "MFGetMediaFormatComplianceLevel", 9557, StreamInformation);
      }
      if ( g_wppLevels )
      {
        v10 = 239;
        goto LABEL_112;
      }
      goto LABEL_113;
    }
    if ( v44 )
    {
LABEL_76:
      if ( (unsigned __int8)byte_1801BA10B >= 8u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 241, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v27);
      *a3 = 1;
      break;
    }
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
    {
      v28 = 240;
LABEL_64:
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), v28, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
      continue;
    }
  }
  if ( !*a3 )
  {
    if ( (unsigned __int8)byte_1801BA10B >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 242, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    StreamInformation = -1072863756;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( *((_DWORD *)v41 + 499) != -1072863756 )
        CallStackContext::TraceFailure(v41, "MFGetMediaFormatComplianceLevel", 9579, -1072863756);
    }
    if ( g_wppLevels )
    {
      v10 = 243;
      goto LABEL_112;
    }
  }
LABEL_113:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v46);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v47);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
  return (unsigned int)StreamInformation;
}

```

## disassembly

```asm
0x1801071a4  mov     [rsp-38h+arg_0], rbx
0x1801071a9  push    rbp
0x1801071aa  push    rsi
0x1801071ab  push    rdi
0x1801071ac  push    r12
0x1801071ae  push    r13
0x1801071b0  push    r14
0x1801071b2  push    r15
0x1801071b4  mov     rbp, rsp
0x1801071b7  sub     rsp, 80h
0x1801071be  mov     rax, cs:__security_cookie
0x1801071c5  xor     rax, rsp
0x1801071c8  mov     [rbp+var_8], rax
0x1801071cc  mov     r12, r8
0x1801071cf  lea     r14, aMfgetmediaform; "MFGetMediaFormatComplianceLevel"
0x1801071d6  mov     rbx, rdx
0x1801071d9  lea     rcx, [rbp+var_50]; this
0x1801071dd  mov     rdx, r14; char *
0x1801071e0  mov     r8d, 250Ah; int
0x1801071e6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801071eb  xor     r13d, r13d
0x1801071ee  lea     r9, [rbp+var_48]
0x1801071f2  xorps   xmm0, xmm0
0x1801071f5  mov     [rbp+var_38], r13
0x1801071f9  xorps   xmm1, xmm1
0x1801071fc  mov     [rbp+var_40], r13
0x180107200  lea     r8, [rbp+var_40]
0x180107204  mov     [rbp+var_30], r13
0x180107208  lea     rdx, [rbp+var_38]
0x18010720c  mov     [rbp+var_4C], r13d
0x180107210  mov     rcx, rbx
0x180107213  mov     dword ptr [rbp+var_48], r13d
0x180107217  movups  [rbp+var_18], xmm0
0x18010721b  mov     [r12], r13d
0x18010721f  movups  [rbp+var_28], xmm1
0x180107223  call    MF__DLNA__GetStreamInformation
0x180107228  mov     ebx, eax
0x18010722a  test    eax, eax
0x18010722c  jns     loc_1801072CA
0x180107232  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180107239  test    rcx, rcx
0x18010723c  jnz     short loc_180107285
0x18010723e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180107245  nop     dword ptr [rax+rax+00h]
0x18010724a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180107251  mov     rcx, rax
0x180107254  test    rax, rax
0x180107257  jz      short loc_180107277
0x180107259  mov     rax, [rax]
0x18010725c  mov     edx, 7F0h
0x180107261  mov     rax, [rax+8]
0x180107265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010726a  test    eax, eax
0x18010726c  jz      short loc_180107277
0x18010726e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180107275  jmp     short loc_180107285
0x180107277  lea     rcx, qword_1801B97E0; this
0x18010727e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180107285  cmp     [rcx+8], r13b
0x180107289  jz      short loc_1801072AC
0x18010728b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180107290  cmp     [rax+7CCh], ebx
0x180107296  jz      short loc_1801072AC
0x180107298  mov     r9d, ebx; int
0x18010729b  mov     r8d, 251Ch; int
0x1801072a1  mov     rdx, r14; char *
0x1801072a4  mov     rcx, rax; this
0x1801072a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801072ac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801072b3  jb      loc_1801078CE
0x1801072b9  mov     edx, 0E6h
0x1801072be  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1801072c5  jmp     loc_1801078B7
0x1801072ca  mov     rcx, [rbp+var_38]
0x1801072ce  lea     r8, [rbp+var_18]
0x1801072d2  lea     rdx, MF_MT_SUBTYPE
0x1801072d9  mov     rax, [rcx]
0x1801072dc  mov     rax, [rax+50h]
0x1801072e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801072e5  mov     ebx, eax
0x1801072e7  test    eax, eax
0x1801072e9  jns     loc_180107380
0x1801072ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801072f6  test    rcx, rcx
0x1801072f9  jnz     short loc_180107342
0x1801072fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180107302  nop     dword ptr [rax+rax+00h]
0x180107307  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010730e  mov     rcx, rax
0x180107311  test    rax, rax
0x180107314  jz      short loc_180107334
0x180107316  mov     rax, [rax]
0x180107319  mov     edx, 7F0h
0x18010731e  mov     rax, [rax+8]
0x180107322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107327  test    eax, eax
0x180107329  jz      short loc_180107334
0x18010732b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180107332  jmp     short loc_180107342
0x180107334  lea     rcx, qword_1801B97E0; this
0x18010733b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180107342  cmp     [rcx+8], r13b
0x180107346  jz      short loc_180107369
0x180107348  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010734d  cmp     [rax+7CCh], ebx
0x180107353  jz      short loc_180107369
0x180107355  mov     r9d, ebx; int
0x180107358  mov     r8d, 251Eh; int
0x18010735e  mov     rdx, r14; char *
0x180107361  mov     rcx, rax; this
0x180107364  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180107369  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180107370  jb      loc_1801078CE
0x180107376  mov     edx, 0E7h
0x18010737b  jmp     loc_1801072BE
0x180107380  mov     rcx, [rbp+var_40]
0x180107384  test    rcx, rcx
0x180107387  jz      loc_18010743F
0x18010738d  mov     rax, [rcx]
0x180107390  lea     r8, [rbp+var_28]
0x180107394  lea     rdx, MF_MT_SUBTYPE
0x18010739b  mov     rax, [rax+50h]
0x18010739f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801073a4  mov     ebx, eax
0x1801073a6  test    eax, eax
0x1801073a8  jns     loc_18010744B
0x1801073ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801073b5  test    rcx, rcx
0x1801073b8  jnz     short loc_180107401
0x1801073ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801073c1  nop     dword ptr [rax+rax+00h]
0x1801073c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801073cd  mov     rcx, rax
0x1801073d0  test    rax, rax
0x1801073d3  jz      short loc_1801073F3
0x1801073d5  mov     rax, [rax]
0x1801073d8  mov     edx, 7F0h
0x1801073dd  mov     rax, [rax+8]
0x1801073e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801073e6  test    eax, eax
0x1801073e8  jz      short loc_1801073F3
0x1801073ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801073f1  jmp     short loc_180107401
0x1801073f3  lea     rcx, qword_1801B97E0; this
0x1801073fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180107401  cmp     [rcx+8], r13b
0x180107405  jz      short loc_180107428
0x180107407  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010740c  cmp     [rax+7CCh], ebx
0x180107412  jz      short loc_180107428
0x180107414  mov     r9d, ebx; int
0x180107417  mov     r8d, 2522h; int
0x18010741d  mov     rdx, r14; char *
0x180107420  mov     rcx, rax; this
0x180107423  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180107428  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010742f  jb      loc_1801078CE
0x180107435  mov     edx, 0E8h
0x18010743a  jmp     loc_1801072BE
0x18010743f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180107446  movdqu  [rbp+var_28], xmm0
0x18010744b  lea     r9, [rbp+var_30]
0x18010744f  lea     r8, [rbp+var_28]
0x180107453  lea     rdx, [rbp+var_18]
0x180107457  call    MF__DLNA__GetMediaFormatComplianceProfiles
0x18010745c  mov     ebx, eax
0x18010745e  test    eax, eax
0x180107460  jns     loc_1801074F7
0x180107466  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010746d  test    rcx, rcx
0x180107470  jnz     short loc_1801074B9
0x180107472  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180107479  nop     dword ptr [rax+rax+00h]
0x18010747e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180107485  mov     rcx, rax
0x180107488  test    rax, rax
0x18010748b  jz      short loc_1801074AB
0x18010748d  mov     rax, [rax]
0x180107490  mov     edx, 7F0h
0x180107495  mov     rax, [rax+8]
0x180107499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010749e  test    eax, eax
0x1801074a0  jz      short loc_1801074AB
0x1801074a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801074a9  jmp     short loc_1801074B9
0x1801074ab  lea     rcx, qword_1801B97E0; this
0x1801074b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801074b9  cmp     [rcx+8], r13b
0x1801074bd  jz      short loc_1801074E0
0x1801074bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801074c4  cmp     [rax+7CCh], ebx
0x1801074ca  jz      short loc_1801074E0
0x1801074cc  mov     r9d, ebx; int
0x1801074cf  mov     r8d, 252Fh; int
0x1801074d5  mov     rdx, r14; char *
0x1801074d8  mov     rcx, rax; this
0x1801074db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801074e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801074e7  jb      loc_1801078CE
0x1801074ed  mov     edx, 0E9h
0x1801074f2  jmp     loc_1801072BE
0x1801074f7  mov     r15, [rbp+var_30]
0x1801074fb  lea     rdi, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x180107502  mov     esi, r13d
0x180107505  cmp     esi, [r15+20h]
0x180107509  jnb     loc_1801076C3
0x18010750f  mov     eax, esi
0x180107511  imul    r14, rax, 70h ; 'p'
0x180107515  add     r14, [r15+28h]
0x180107519  cmp     cs:byte_1801BA10B, 10h
0x180107520  jb      short loc_180107540
0x180107522  mov     rcx, cs:WPP_GLOBAL_Control
0x180107529  mov     edx, 0EAh
0x18010752e  mov     r9, [r14]
0x180107531  mov     r8, rdi
0x180107534  mov     rcx, [rcx+88h]
0x18010753b  call    WPP_SF_S
0x180107540  mov     ecx, dword ptr [rbp+var_48]; this
0x180107543  lea     r8, [rbp+var_4C]; struct MF::DLNA::DLNAProfile *
0x180107547  mov     rdx, r14; unsigned int
0x18010754a  call    ?CheckSystemConstraints@DLNA@MF@@YAJIPEBUDLNAProfile@12@PEAH@Z; MF::DLNA::CheckSystemConstraints(uint,MF::DLNA::DLNAProfile const *,int *)
0x18010754f  mov     ebx, eax
0x180107551  test    eax, eax
0x180107553  js      loc_1801077DF
0x180107559  cmp     [rbp+var_4C], r13d
0x18010755d  jnz     short loc_180107573
0x18010755f  cmp     cs:byte_1801BA10B, 10h
0x180107566  jb      loc_1801075F8
0x18010756c  mov     edx, 0ECh
0x180107571  jmp     short loc_1801075E2
0x180107573  mov     rcx, [rbp+var_38]
0x180107577  lea     r8, [rbp+var_4C]
0x18010757b  mov     rax, [r15+8]
0x18010757f  mov     rdx, r14
0x180107582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107587  mov     ebx, eax
0x180107589  test    eax, eax
0x18010758b  js      loc_18010774A
0x180107591  cmp     [rbp+var_4C], r13d
0x180107595  jnz     short loc_1801075A7
0x180107597  cmp     cs:byte_1801BA10B, 10h
0x18010759e  jb      short loc_1801075F8
0x1801075a0  mov     edx, 0EEh
0x1801075a5  jmp     short loc_1801075E2
0x1801075a7  mov     rax, [r15+18h]
0x1801075ab  test    rax, rax
0x1801075ae  jz      loc_180107694
0x1801075b4  mov     rcx, [rbp+var_40]
0x1801075b8  lea     r8, [rbp+var_4C]
0x1801075bc  mov     rdx, r14
0x1801075bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801075c4  mov     ebx, eax
0x1801075c6  test    eax, eax
0x1801075c8  js      short loc_1801075FF
0x1801075ca  cmp     [rbp+var_4C], r13d
0x1801075ce  jnz     loc_180107694
0x1801075d4  cmp     cs:byte_1801BA10B, 10h
0x1801075db  jb      short loc_1801075F8
0x1801075dd  mov     edx, 0F0h
0x1801075e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801075e9  mov     r8, rdi
0x1801075ec  mov     rcx, [rcx+88h]
0x1801075f3  call    WPP_SF_
0x1801075f8  inc     esi
0x1801075fa  jmp     loc_180107505
0x1801075ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180107606  test    rcx, rcx
0x180107609  jnz     short loc_180107652
0x18010760b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180107612  nop     dword ptr [rax+rax+00h]
0x180107617  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010761e  mov     rcx, rax
0x180107621  test    rax, rax
0x180107624  jz      short loc_180107644
0x180107626  mov     rax, [rax]
0x180107629  mov     edx, 7F0h
0x18010762e  mov     rax, [rax+8]
0x180107632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107637  test    eax, eax
0x180107639  jz      short loc_180107644
0x18010763b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180107642  jmp     short loc_180107652
0x180107644  lea     rcx, qword_1801B97E0; this
0x18010764b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180107652  cmp     [rcx+8], r13b
0x180107656  jz      short loc_18010767D
0x180107658  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010765d  cmp     [rax+7CCh], ebx
0x180107663  jz      short loc_18010767D
0x180107665  mov     r9d, ebx; int
0x180107668  lea     rdx, aMfgetmediaform; "MFGetMediaFormatComplianceLevel"
0x18010766f  mov     r8d, 2555h; int
0x180107675  mov     rcx, rax; this
0x180107678  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010767d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180107684  jb      loc_1801078CE
0x18010768a  mov     edx, 0EFh
0x18010768f  jmp     loc_1801078B4
0x180107694  cmp     cs:byte_1801BA10B, 8
0x18010769b  jb      short loc_1801076BB
  ... truncated ...
```
