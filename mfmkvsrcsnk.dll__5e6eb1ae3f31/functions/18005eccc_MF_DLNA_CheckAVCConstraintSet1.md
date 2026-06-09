# MF::DLNA::CheckAVCConstraintSet1

- ea: `0x18005eccc`
- end: `0x18005f270`
- name: `MF::DLNA::CheckAVCConstraintSet1`
- size: `1444`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005f278`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18005eccc`
- `0x18006408c`
- `0x180071330`
- `0x180078b50`
- `0x180078bf4`
- `0x18007c1c4`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f24e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f24e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ed66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ee13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ef3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f003`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f092`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f121`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f1b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ed66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ee13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ef3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f003`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f092`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f121`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f1b2`

## pseudocode

```c
__int64 __fastcall MF::DLNA::CheckAVCConstraintSet1(__int64 *a1)
{
  __int64 v2; // rax
  __int64 (__fastcall *v3)(__int64 *, const GUID *, LPVOID *, unsigned int *); // rax
  __int64 v4; // rdx
  int started; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  int v18; // r14d
  unsigned int i; // edi
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // r15d
  unsigned int v24; // esi
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  LPVOID pv; // [rsp+30h] [rbp-48h] BYREF
  __int64 v45; // [rsp+38h] [rbp-40h] BYREF
  char v46; // [rsp+40h] [rbp-38h]
  __int64 v47; // [rsp+44h] [rbp-34h]
  __int64 v48; // [rsp+4Ch] [rbp-2Ch]
  __int64 v49; // [rsp+54h] [rbp-24h]
  __int64 v50; // [rsp+5Ch] [rbp-1Ch]
  __int64 v51; // [rsp+68h] [rbp-10h]
  unsigned int v52; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v53; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int v54; // [rsp+D0h] [rbp+58h] BYREF
  int v55; // [rsp+D8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v52, "MF::DLNA::CheckAVCConstraintSet1", 8028);
  v2 = *a1;
  v45 = 0;
  v46 = 0;
  v3 = *(__int64 (__fastcall **)(__int64 *, const GUID *, LPVOID *, unsigned int *))(v2 + 128);
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  pv = 0;
  v53 = 0;
  v55 = 0;
  v52 = 0;
  v54 = 0;
  started = v3(a1, &MF_MT_MPEG_SEQUENCE_HEADER, &pv, &v53);
  if ( started < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != started )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MF::DLNA::CheckAVCConstraintSet1", 8045, started);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v11 = 132;
    goto LABEL_12;
  }
  started = MFFindNextStartCode((const unsigned __int8 *)pv, v53, &v52, &v54);
  if ( started < 0 )
  {
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != started )
        CallStackContext::TraceFailure(v17, "MF::DLNA::CheckAVCConstraintSet1", 8047, started);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v11 = 133;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, 0, started);
    goto LABEL_87;
  }
  v18 = 1;
  for ( i = v52 + v54; ; i += v23 + v54 )
  {
    if ( !v18 )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      started = -1072875819;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != -1072875819 )
          CallStackContext::TraceFailure(v42, "MF::DLNA::CheckAVCConstraintSet1", 8097, -1072875819);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          139,
          &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
          0,
          -1072875819);
      goto LABEL_87;
    }
    v20 = MFFindNextStartCode((const unsigned __int8 *)pv + i, v53 - i, &v52, &v54);
    v23 = v52;
    started = v20;
    if ( v20 == -1072875819 )
    {
      v18 = 0;
      v24 = v53 - i;
      goto LABEL_30;
    }
    if ( v20 < 0 )
      break;
    v24 = v52;
LABEL_30:
    started = MFH264GetNALUType((const unsigned __int8 *)pv + i, v53 - i, (enum H264_NALU_TYPE *)&v55);
    if ( started < 0 )
    {
      v34 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != started )
          CallStackContext::TraceFailure(v36, "MF::DLNA::CheckAVCConstraintSet1", 8076, started);
      }
      if ( g_wppLevels )
      {
        v11 = 135;
        goto LABEL_12;
      }
      goto LABEL_87;
    }
    if ( v55 == 7 )
    {
      started = CAVCSequenceParameterSet::ParseData(
                  (CAVCSequenceParameterSet *)&v45,
                  v24,
                  (const unsigned __int8 *)pv + i);
      if ( started >= 0 )
      {
        if ( !(_DWORD)v50 )
        {
          if ( (unsigned __int8)byte_1800D78D3 >= 0x10u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 137, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          started = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v33, "MF::DLNA::CheckAVCConstraintSet1", 8085, -1072863756);
          }
          if ( g_wppLevels )
          {
            v11 = 138;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != started )
            CallStackContext::TraceFailure(v30, "MF::DLNA::CheckAVCConstraintSet1", 8080, started);
        }
        if ( g_wppLevels )
        {
          v11 = 136;
          goto LABEL_12;
        }
      }
      goto LABEL_87;
    }
  }
  v37 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53, v21, v22);
    CallStackTracing::s_wpInstance = v38;
    if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
    {
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v37 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v37 + 8) )
  {
    v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
    if ( *((_DWORD *)v39 + 499) != started )
      CallStackContext::TraceFailure(v39, "MF::DLNA::CheckAVCConstraintSet1", 8069, started);
  }
  if ( g_wppLevels )
  {
    v11 = 134;
    goto LABEL_12;
  }
LABEL_87:
  CoTaskMemFree(pv);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v52);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18005eccc  push    rbp
0x18005ecce  push    rbx
0x18005eccf  push    rsi
0x18005ecd0  push    rdi
0x18005ecd1  push    r12
0x18005ecd3  push    r13
0x18005ecd5  push    r14
0x18005ecd7  push    r15
0x18005ecd9  mov     rbp, rsp
0x18005ecdc  sub     rsp, 78h
0x18005ece0  mov     rbx, rcx
0x18005ece3  lea     r15, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x18005ecea  mov     rdx, r15; char *
0x18005eced  lea     rcx, [rbp+arg_0]; this
0x18005ecf1  mov     r8d, 1F5Ch; int
0x18005ecf7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005ecfc  mov     rax, [rbx]
0x18005ecff  lea     r9, [rbp+arg_8]
0x18005ed03  xor     r13d, r13d
0x18005ed06  lea     r8, [rbp+pv]
0x18005ed0a  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x18005ed11  mov     [rbp+var_40], r13
0x18005ed15  mov     rcx, rbx
0x18005ed18  mov     [rbp+var_38], r13b
0x18005ed1c  mov     rax, [rax+80h]
0x18005ed23  mov     [rbp+var_34], r13
0x18005ed27  mov     [rbp+var_2C], r13
0x18005ed2b  mov     [rbp+var_24], r13
0x18005ed2f  mov     [rbp+var_1C], r13
0x18005ed33  mov     [rbp+var_10], r13
0x18005ed37  mov     [rbp+pv], r13
0x18005ed3b  mov     [rbp+arg_8], r13d
0x18005ed3f  mov     [rbp+arg_18], r13d
0x18005ed43  mov     [rbp+arg_0], r13d
0x18005ed47  mov     [rbp+arg_10], r13d
0x18005ed4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed50  mov     ebx, eax
0x18005ed52  test    eax, eax
0x18005ed54  jns     loc_18005EDE9
0x18005ed5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ed61  test    rcx, rcx
0x18005ed64  jnz     short loc_18005EDA7
0x18005ed66  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ed6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ed73  mov     rcx, rax
0x18005ed76  test    rax, rax
0x18005ed79  jz      short loc_18005ED99
0x18005ed7b  mov     rax, [rax]
0x18005ed7e  mov     edx, 7F0h
0x18005ed83  mov     rax, [rax+8]
0x18005ed87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed8c  test    eax, eax
0x18005ed8e  jz      short loc_18005ED99
0x18005ed90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ed97  jmp     short loc_18005EDA7
0x18005ed99  lea     rcx, qword_1800D6F70; this
0x18005eda0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005eda7  cmp     [rcx+8], r13b
0x18005edab  jz      short loc_18005EDCE
0x18005edad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005edb2  cmp     [rax+7CCh], ebx
0x18005edb8  jz      short loc_18005EDCE
0x18005edba  mov     r9d, ebx; int
0x18005edbd  mov     r8d, 1F6Dh; int
0x18005edc3  mov     rdx, r15; char *
0x18005edc6  mov     rcx, rax; this
0x18005edc9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005edce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005edd5  jb      loc_18005F24A
0x18005eddb  mov     edx, 84h
0x18005ede0  mov     [rsp+78h+var_58], ebx
0x18005ede4  jmp     loc_18005F230
0x18005ede9  mov     edx, [rbp+arg_8]; unsigned int
0x18005edec  lea     r9, [rbp+arg_10]; unsigned int *
0x18005edf0  mov     rcx, [rbp+pv]; unsigned __int8 *
0x18005edf4  lea     r8, [rbp+arg_0]; unsigned int *
0x18005edf8  call    ?MFFindNextStartCode@@YAJPEBEKPEAK1@Z; MFFindNextStartCode(uchar const *,ulong,ulong *,ulong *)
0x18005edfd  mov     ebx, eax
0x18005edff  test    eax, eax
0x18005ee01  jns     loc_18005EE92
0x18005ee07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ee0e  test    rcx, rcx
0x18005ee11  jnz     short loc_18005EE54
0x18005ee13  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ee19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ee20  mov     rcx, rax
0x18005ee23  test    rax, rax
0x18005ee26  jz      short loc_18005EE46
0x18005ee28  mov     rax, [rax]
0x18005ee2b  mov     edx, 7F0h
0x18005ee30  mov     rax, [rax+8]
0x18005ee34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee39  test    eax, eax
0x18005ee3b  jz      short loc_18005EE46
0x18005ee3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ee44  jmp     short loc_18005EE54
0x18005ee46  lea     rcx, qword_1800D6F70; this
0x18005ee4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ee54  cmp     [rcx+8], r13b
0x18005ee58  jz      short loc_18005EE7B
0x18005ee5a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005ee5f  cmp     [rax+7CCh], ebx
0x18005ee65  jz      short loc_18005EE7B
0x18005ee67  mov     r9d, ebx; int
0x18005ee6a  mov     r8d, 1F6Fh; int
0x18005ee70  mov     rdx, r15; char *
0x18005ee73  mov     rcx, rax; this
0x18005ee76  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005ee7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005ee82  jb      loc_18005F24A
0x18005ee88  mov     edx, 85h
0x18005ee8d  jmp     loc_18005EDE0
0x18005ee92  mov     edi, [rbp+arg_10]
0x18005ee95  mov     r14d, 1
0x18005ee9b  add     edi, [rbp+arg_0]
0x18005ee9e  mov     esi, 0C00D36D5h
0x18005eea3  test    r14d, r14d
0x18005eea6  jz      loc_18005F1A4
0x18005eeac  mov     edx, [rbp+arg_8]
0x18005eeaf  lea     r9, [rbp+arg_10]; unsigned int *
0x18005eeb3  mov     rcx, [rbp+pv]
0x18005eeb7  lea     r8, [rbp+arg_0]; unsigned int *
0x18005eebb  mov     r12d, edi
0x18005eebe  sub     edx, edi; unsigned int
0x18005eec0  add     rcx, r12; unsigned __int8 *
0x18005eec3  call    ?MFFindNextStartCode@@YAJPEBEKPEAK1@Z; MFFindNextStartCode(uchar const *,ulong,ulong *,ulong *)
0x18005eec8  mov     r15d, [rbp+arg_0]
0x18005eecc  mov     ebx, eax
0x18005eece  mov     edx, [rbp+arg_8]
0x18005eed1  cmp     eax, esi
0x18005eed3  jnz     short loc_18005EEDE
0x18005eed5  mov     esi, edx
0x18005eed7  mov     r14d, r13d
0x18005eeda  sub     esi, edi
0x18005eedc  jmp     short loc_18005EEE9
0x18005eede  test    ebx, ebx
0x18005eee0  js      loc_18005F115
0x18005eee6  mov     esi, r15d
0x18005eee9  mov     rcx, [rbp+pv]
0x18005eeed  lea     r8, [rbp+arg_18]; enum H264_NALU_TYPE *
0x18005eef1  add     rcx, r12; unsigned __int8 *
0x18005eef4  sub     edx, edi; unsigned int
0x18005eef6  call    ?MFH264GetNALUType@@YAJPEBEKPEAW4H264_NALU_TYPE@@@Z; MFH264GetNALUType(uchar const *,ulong,H264_NALU_TYPE *)
0x18005eefb  mov     ebx, eax
0x18005eefd  test    eax, eax
0x18005eeff  js      loc_18005F086
0x18005ef05  cmp     [rbp+arg_18], 7
0x18005ef09  jz      short loc_18005EF15
0x18005ef0b  mov     ecx, [rbp+arg_10]
0x18005ef0e  add     ecx, r15d
0x18005ef11  add     edi, ecx
0x18005ef13  jmp     short loc_18005EE9E
0x18005ef15  mov     r8, [rbp+pv]
0x18005ef19  lea     rcx, [rbp+var_40]; this
0x18005ef1d  add     r8, r12; unsigned __int8 *
0x18005ef20  mov     edx, esi; unsigned int
0x18005ef22  call    ?ParseData@CAVCSequenceParameterSet@@QEAAJKPEBE@Z; CAVCSequenceParameterSet::ParseData(ulong,uchar const *)
0x18005ef27  mov     ebx, eax
0x18005ef29  test    eax, eax
0x18005ef2b  jns     loc_18005EFC0
0x18005ef31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ef38  test    rcx, rcx
0x18005ef3b  jnz     short loc_18005EF7E
0x18005ef3d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ef43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ef4a  mov     rcx, rax
0x18005ef4d  test    rax, rax
0x18005ef50  jz      short loc_18005EF70
0x18005ef52  mov     rax, [rax]
0x18005ef55  mov     edx, 7F0h
0x18005ef5a  mov     rax, [rax+8]
0x18005ef5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef63  test    eax, eax
0x18005ef65  jz      short loc_18005EF70
0x18005ef67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ef6e  jmp     short loc_18005EF7E
0x18005ef70  lea     rcx, qword_1800D6F70; this
0x18005ef77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ef7e  cmp     [rcx+8], r13b
0x18005ef82  jz      short loc_18005EFA9
0x18005ef84  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005ef89  cmp     [rax+7CCh], ebx
0x18005ef8f  jz      short loc_18005EFA9
0x18005ef91  mov     r9d, ebx; int
0x18005ef94  lea     rdx, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x18005ef9b  mov     r8d, 1F90h; int
0x18005efa1  mov     rcx, rax; this
0x18005efa4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005efa9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005efb0  jb      loc_18005F24A
0x18005efb6  mov     edx, 88h
0x18005efbb  jmp     loc_18005EDE0
0x18005efc0  cmp     dword ptr [rbp+var_1C], r13d
0x18005efc4  jnz     loc_18005F24A
0x18005efca  cmp     cs:byte_1800D78D3, 10h
0x18005efd1  jb      short loc_18005EFF2
0x18005efd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005efda  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18005efe1  mov     edx, 89h
0x18005efe6  mov     rcx, [rcx+88h]
0x18005efed  call    WPP_SF_
0x18005eff2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005eff9  mov     ebx, 0C00D65F4h
0x18005effe  test    rcx, rcx
0x18005f001  jnz     short loc_18005F044
0x18005f003  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005f009  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f010  mov     rcx, rax
0x18005f013  test    rax, rax
0x18005f016  jz      short loc_18005F036
0x18005f018  mov     rax, [rax]
0x18005f01b  mov     edx, 7F0h
0x18005f020  mov     rax, [rax+8]
0x18005f024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f029  test    eax, eax
0x18005f02b  jz      short loc_18005F036
0x18005f02d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f034  jmp     short loc_18005F044
0x18005f036  lea     rcx, qword_1800D6F70; this
0x18005f03d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f044  cmp     [rcx+8], r13b
0x18005f048  jz      short loc_18005F06F
0x18005f04a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005f04f  cmp     [rax+7CCh], ebx
0x18005f055  jz      short loc_18005F06F
0x18005f057  mov     r9d, ebx; int
0x18005f05a  lea     rdx, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x18005f061  mov     r8d, 1F95h; int
0x18005f067  mov     rcx, rax; this
0x18005f06a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005f06f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005f076  jb      loc_18005F24A
0x18005f07c  mov     edx, 8Ah
0x18005f081  jmp     loc_18005EDE0
0x18005f086  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f08d  test    rcx, rcx
0x18005f090  jnz     short loc_18005F0D3
0x18005f092  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005f098  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f09f  mov     rcx, rax
0x18005f0a2  test    rax, rax
0x18005f0a5  jz      short loc_18005F0C5
0x18005f0a7  mov     rax, [rax]
0x18005f0aa  mov     edx, 7F0h
0x18005f0af  mov     rax, [rax+8]
0x18005f0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f0b8  test    eax, eax
0x18005f0ba  jz      short loc_18005F0C5
0x18005f0bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f0c3  jmp     short loc_18005F0D3
0x18005f0c5  lea     rcx, qword_1800D6F70; this
0x18005f0cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f0d3  cmp     [rcx+8], r13b
0x18005f0d7  jz      short loc_18005F0FE
0x18005f0d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005f0de  cmp     [rax+7CCh], ebx
0x18005f0e4  jz      short loc_18005F0FE
0x18005f0e6  mov     r9d, ebx; int
0x18005f0e9  lea     rdx, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x18005f0f0  mov     r8d, 1F8Ch; int
0x18005f0f6  mov     rcx, rax; this
0x18005f0f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005f0fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005f105  jb      loc_18005F24A
0x18005f10b  mov     edx, 87h
0x18005f110  jmp     loc_18005EDE0
0x18005f115  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f11c  test    rcx, rcx
0x18005f11f  jnz     short loc_18005F162
0x18005f121  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005f127  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f12e  mov     rcx, rax
0x18005f131  test    rax, rax
0x18005f134  jz      short loc_18005F154
0x18005f136  mov     rax, [rax]
0x18005f139  mov     edx, 7F0h
0x18005f13e  mov     rax, [rax+8]
0x18005f142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f147  test    eax, eax
0x18005f149  jz      short loc_18005F154
0x18005f14b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f152  jmp     short loc_18005F162
0x18005f154  lea     rcx, qword_1800D6F70; this
0x18005f15b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f162  cmp     [rcx+8], r13b
0x18005f166  jz      short loc_18005F18D
0x18005f168  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005f16d  cmp     [rax+7CCh], ebx
0x18005f173  jz      short loc_18005F18D
0x18005f175  mov     r9d, ebx; int
0x18005f178  lea     rdx, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x18005f17f  mov     r8d, 1F85h; int
0x18005f185  mov     rcx, rax; this
0x18005f188  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005f18d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005f194  jb      loc_18005F24A
0x18005f19a  mov     edx, 86h
0x18005f19f  jmp     loc_18005EDE0
0x18005f1a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f1ab  mov     ebx, esi
  ... truncated ...
```
