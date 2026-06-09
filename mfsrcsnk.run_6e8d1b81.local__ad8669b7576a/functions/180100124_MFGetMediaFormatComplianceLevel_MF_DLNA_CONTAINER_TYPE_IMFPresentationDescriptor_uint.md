# MFGetMediaFormatComplianceLevel(MF_DLNA_CONTAINER_TYPE,IMFPresentationDescriptor *,uint *)

- ea: `0x180100124`
- end: `0x180100862`
- name: `?MFGetMediaFormatComplianceLevel@@YAJW4MF_DLNA_CONTAINER_TYPE@@PEAUIMFPresentationDescriptor@@PEAI@Z`
- size: `1854`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180072394`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180072b60`
- `0x180073b14`
- `0x1800a1764`
- `0x180100124`
- `0x1801099f0`
- `0x180115a1c`
- `0x18016135c`
- `0x180170580`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801001be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180100275`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010032e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801003e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180100573`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180100668`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801006b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180100741`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801001be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180100275`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010032e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801003e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180100573`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180100668`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801006b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180100741`

## string_xrefs

- `0x18010014f`: `MFGetMediaFormatComplianceLevel`
- `0x1801005ca`: `MFGetMediaFormatComplianceLevel`
- `0x180100709`: `MFGetMediaFormatComplianceLevel`
- `0x180100798`: `MFGetMediaFormatComplianceLevel`
- `0x1801007e1`: `MFGetMediaFormatComplianceLevel`

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
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v12 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v17 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v22 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
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
          v38 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      if ( (unsigned __int8)byte_1801B110B < 0x10u )
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
          v35 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      if ( (unsigned __int8)byte_1801B110B < 0x10u )
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
          v30 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      if ( (unsigned __int8)byte_1801B110B >= 8u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), 241, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, *v27);
      *a3 = 1;
      break;
    }
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
    {
      v28 = 240;
LABEL_64:
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), v28, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
      continue;
    }
  }
  if ( !*a3 )
  {
    if ( (unsigned __int8)byte_1801B110B >= 4u )
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
        v33 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x180100124  mov     [rsp-38h+arg_0], rbx
0x180100129  push    rbp
0x18010012a  push    rsi
0x18010012b  push    rdi
0x18010012c  push    r12
0x18010012e  push    r13
0x180100130  push    r14
0x180100132  push    r15
0x180100134  mov     rbp, rsp
0x180100137  sub     rsp, 80h
0x18010013e  mov     rax, cs:__security_cookie
0x180100145  xor     rax, rsp
0x180100148  mov     [rbp+var_8], rax
0x18010014c  mov     r12, r8
0x18010014f  lea     r14, aMfgetmediaform; "MFGetMediaFormatComplianceLevel"
0x180100156  mov     rbx, rdx
0x180100159  lea     rcx, [rbp+var_50]; this
0x18010015d  mov     rdx, r14; char *
0x180100160  mov     r8d, 250Ah; int
0x180100166  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18010016b  xor     r13d, r13d
0x18010016e  lea     r9, [rbp+var_48]
0x180100172  xorps   xmm0, xmm0
0x180100175  mov     [rbp+var_38], r13
0x180100179  xorps   xmm1, xmm1
0x18010017c  mov     [rbp+var_40], r13
0x180100180  lea     r8, [rbp+var_40]
0x180100184  mov     [rbp+var_30], r13
0x180100188  lea     rdx, [rbp+var_38]
0x18010018c  mov     [rbp+var_4C], r13d
0x180100190  mov     rcx, rbx
0x180100193  mov     dword ptr [rbp+var_48], r13d
0x180100197  movups  [rbp+var_18], xmm0
0x18010019b  mov     [r12], r13d
0x18010019f  movups  [rbp+var_28], xmm1
0x1801001a3  call    MF__DLNA__GetStreamInformation
0x1801001a8  mov     ebx, eax
0x1801001aa  test    eax, eax
0x1801001ac  jns     loc_180100244
0x1801001b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801001b9  test    rcx, rcx
0x1801001bc  jnz     short loc_1801001FF
0x1801001be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801001c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801001cb  mov     rcx, rax
0x1801001ce  test    rax, rax
0x1801001d1  jz      short loc_1801001F1
0x1801001d3  mov     rax, [rax]
0x1801001d6  mov     edx, 7F0h
0x1801001db  mov     rax, [rax+8]
0x1801001df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801001e4  test    eax, eax
0x1801001e6  jz      short loc_1801001F1
0x1801001e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801001ef  jmp     short loc_1801001FF
0x1801001f1  lea     rcx, qword_1801B07E0; this
0x1801001f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801001ff  cmp     [rcx+8], r13b
0x180100203  jz      short loc_180100226
0x180100205  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010020a  cmp     [rax+7CCh], ebx
0x180100210  jz      short loc_180100226
0x180100212  mov     r9d, ebx; int
0x180100215  mov     r8d, 251Ch; int
0x18010021b  mov     rdx, r14; char *
0x18010021e  mov     rcx, rax; this
0x180100221  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180100226  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010022d  jb      loc_18010081E
0x180100233  mov     edx, 0E6h
0x180100238  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18010023f  jmp     loc_180100807
0x180100244  mov     rcx, [rbp+var_38]
0x180100248  lea     r8, [rbp+var_18]
0x18010024c  lea     rdx, MF_MT_SUBTYPE
0x180100253  mov     rax, [rcx]
0x180100256  mov     rax, [rax+50h]
0x18010025a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010025f  mov     ebx, eax
0x180100261  test    eax, eax
0x180100263  jns     loc_1801002F4
0x180100269  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180100270  test    rcx, rcx
0x180100273  jnz     short loc_1801002B6
0x180100275  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18010027b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180100282  mov     rcx, rax
0x180100285  test    rax, rax
0x180100288  jz      short loc_1801002A8
0x18010028a  mov     rax, [rax]
0x18010028d  mov     edx, 7F0h
0x180100292  mov     rax, [rax+8]
0x180100296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010029b  test    eax, eax
0x18010029d  jz      short loc_1801002A8
0x18010029f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801002a6  jmp     short loc_1801002B6
0x1801002a8  lea     rcx, qword_1801B07E0; this
0x1801002af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801002b6  cmp     [rcx+8], r13b
0x1801002ba  jz      short loc_1801002DD
0x1801002bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801002c1  cmp     [rax+7CCh], ebx
0x1801002c7  jz      short loc_1801002DD
0x1801002c9  mov     r9d, ebx; int
0x1801002cc  mov     r8d, 251Eh; int
0x1801002d2  mov     rdx, r14; char *
0x1801002d5  mov     rcx, rax; this
0x1801002d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801002dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801002e4  jb      loc_18010081E
0x1801002ea  mov     edx, 0E7h
0x1801002ef  jmp     loc_180100238
0x1801002f4  mov     rcx, [rbp+var_40]
0x1801002f8  test    rcx, rcx
0x1801002fb  jz      loc_1801003AD
0x180100301  mov     rax, [rcx]
0x180100304  lea     r8, [rbp+var_28]
0x180100308  lea     rdx, MF_MT_SUBTYPE
0x18010030f  mov     rax, [rax+50h]
0x180100313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100318  mov     ebx, eax
0x18010031a  test    eax, eax
0x18010031c  jns     loc_1801003B9
0x180100322  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180100329  test    rcx, rcx
0x18010032c  jnz     short loc_18010036F
0x18010032e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180100334  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010033b  mov     rcx, rax
0x18010033e  test    rax, rax
0x180100341  jz      short loc_180100361
0x180100343  mov     rax, [rax]
0x180100346  mov     edx, 7F0h
0x18010034b  mov     rax, [rax+8]
0x18010034f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100354  test    eax, eax
0x180100356  jz      short loc_180100361
0x180100358  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010035f  jmp     short loc_18010036F
0x180100361  lea     rcx, qword_1801B07E0; this
0x180100368  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010036f  cmp     [rcx+8], r13b
0x180100373  jz      short loc_180100396
0x180100375  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010037a  cmp     [rax+7CCh], ebx
0x180100380  jz      short loc_180100396
0x180100382  mov     r9d, ebx; int
0x180100385  mov     r8d, 2522h; int
0x18010038b  mov     rdx, r14; char *
0x18010038e  mov     rcx, rax; this
0x180100391  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180100396  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010039d  jb      loc_18010081E
0x1801003a3  mov     edx, 0E8h
0x1801003a8  jmp     loc_180100238
0x1801003ad  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1801003b4  movdqu  [rbp+var_28], xmm0
0x1801003b9  lea     r9, [rbp+var_30]
0x1801003bd  lea     r8, [rbp+var_28]
0x1801003c1  lea     rdx, [rbp+var_18]
0x1801003c5  call    MF__DLNA__GetMediaFormatComplianceProfiles
0x1801003ca  mov     ebx, eax
0x1801003cc  test    eax, eax
0x1801003ce  jns     loc_18010045F
0x1801003d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801003db  test    rcx, rcx
0x1801003de  jnz     short loc_180100421
0x1801003e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801003e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801003ed  mov     rcx, rax
0x1801003f0  test    rax, rax
0x1801003f3  jz      short loc_180100413
0x1801003f5  mov     rax, [rax]
0x1801003f8  mov     edx, 7F0h
0x1801003fd  mov     rax, [rax+8]
0x180100401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100406  test    eax, eax
0x180100408  jz      short loc_180100413
0x18010040a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180100411  jmp     short loc_180100421
0x180100413  lea     rcx, qword_1801B07E0; this
0x18010041a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180100421  cmp     [rcx+8], r13b
0x180100425  jz      short loc_180100448
0x180100427  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010042c  cmp     [rax+7CCh], ebx
0x180100432  jz      short loc_180100448
0x180100434  mov     r9d, ebx; int
0x180100437  mov     r8d, 252Fh; int
0x18010043d  mov     rdx, r14; char *
0x180100440  mov     rcx, rax; this
0x180100443  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180100448  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010044f  jb      loc_18010081E
0x180100455  mov     edx, 0E9h
0x18010045a  jmp     loc_180100238
0x18010045f  mov     r15, [rbp+var_30]
0x180100463  lea     rdi, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18010046a  mov     esi, r13d
0x18010046d  cmp     esi, [r15+20h]
0x180100471  jnb     loc_180100625
0x180100477  mov     eax, esi
0x180100479  imul    r14, rax, 70h ; 'p'
0x18010047d  add     r14, [r15+28h]
0x180100481  cmp     cs:byte_1801B110B, 10h
0x180100488  jb      short loc_1801004A8
0x18010048a  mov     rcx, cs:WPP_GLOBAL_Control
0x180100491  mov     edx, 0EAh
0x180100496  mov     r9, [r14]
0x180100499  mov     r8, rdi
0x18010049c  mov     rcx, [rcx+88h]
0x1801004a3  call    WPP_SF_S
0x1801004a8  mov     ecx, dword ptr [rbp+var_48]; this
0x1801004ab  lea     r8, [rbp+var_4C]; struct MF::DLNA::DLNAProfile *
0x1801004af  mov     rdx, r14; unsigned int
0x1801004b2  call    ?CheckSystemConstraints@DLNA@MF@@YAJIPEBUDLNAProfile@12@PEAH@Z; MF::DLNA::CheckSystemConstraints(uint,MF::DLNA::DLNAProfile const *,int *)
0x1801004b7  mov     ebx, eax
0x1801004b9  test    eax, eax
0x1801004bb  js      loc_180100735
0x1801004c1  cmp     [rbp+var_4C], r13d
0x1801004c5  jnz     short loc_1801004DB
0x1801004c7  cmp     cs:byte_1801B110B, 10h
0x1801004ce  jb      loc_180100560
0x1801004d4  mov     edx, 0ECh
0x1801004d9  jmp     short loc_18010054A
0x1801004db  mov     rcx, [rbp+var_38]
0x1801004df  lea     r8, [rbp+var_4C]
0x1801004e3  mov     rax, [r15+8]
0x1801004e7  mov     rdx, r14
0x1801004ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801004ef  mov     ebx, eax
0x1801004f1  test    eax, eax
0x1801004f3  js      loc_1801006A6
0x1801004f9  cmp     [rbp+var_4C], r13d
0x1801004fd  jnz     short loc_18010050F
0x1801004ff  cmp     cs:byte_1801B110B, 10h
0x180100506  jb      short loc_180100560
0x180100508  mov     edx, 0EEh
0x18010050d  jmp     short loc_18010054A
0x18010050f  mov     rax, [r15+18h]
0x180100513  test    rax, rax
0x180100516  jz      loc_1801005F6
0x18010051c  mov     rcx, [rbp+var_40]
0x180100520  lea     r8, [rbp+var_4C]
0x180100524  mov     rdx, r14
0x180100527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010052c  mov     ebx, eax
0x18010052e  test    eax, eax
0x180100530  js      short loc_180100567
0x180100532  cmp     [rbp+var_4C], r13d
0x180100536  jnz     loc_1801005F6
0x18010053c  cmp     cs:byte_1801B110B, 10h
0x180100543  jb      short loc_180100560
0x180100545  mov     edx, 0F0h
0x18010054a  mov     rcx, cs:WPP_GLOBAL_Control
0x180100551  mov     r8, rdi
0x180100554  mov     rcx, [rcx+88h]
0x18010055b  call    WPP_SF_
0x180100560  inc     esi
0x180100562  jmp     loc_18010046D
0x180100567  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010056e  test    rcx, rcx
0x180100571  jnz     short loc_1801005B4
0x180100573  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180100579  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180100580  mov     rcx, rax
0x180100583  test    rax, rax
0x180100586  jz      short loc_1801005A6
0x180100588  mov     rax, [rax]
0x18010058b  mov     edx, 7F0h
0x180100590  mov     rax, [rax+8]
0x180100594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100599  test    eax, eax
0x18010059b  jz      short loc_1801005A6
0x18010059d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801005a4  jmp     short loc_1801005B4
0x1801005a6  lea     rcx, qword_1801B07E0; this
0x1801005ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801005b4  cmp     [rcx+8], r13b
0x1801005b8  jz      short loc_1801005DF
0x1801005ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801005bf  cmp     [rax+7CCh], ebx
0x1801005c5  jz      short loc_1801005DF
0x1801005c7  mov     r9d, ebx; int
0x1801005ca  lea     rdx, aMfgetmediaform; "MFGetMediaFormatComplianceLevel"
0x1801005d1  mov     r8d, 2555h; int
0x1801005d7  mov     rcx, rax; this
0x1801005da  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801005df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801005e6  jb      loc_18010081E
0x1801005ec  mov     edx, 0EFh
0x1801005f1  jmp     loc_180100804
0x1801005f6  cmp     cs:byte_1801B110B, 8
0x1801005fd  jb      short loc_18010061D
0x1801005ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180100606  mov     edx, 0F1h
0x18010060b  mov     r9, [r14]
0x18010060e  mov     r8, rdi
0x180100611  mov     rcx, [rcx+88h]
  ... truncated ...
```
