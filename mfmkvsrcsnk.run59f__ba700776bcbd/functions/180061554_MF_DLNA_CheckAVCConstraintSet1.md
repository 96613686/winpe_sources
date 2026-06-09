# MF::DLNA::CheckAVCConstraintSet1

- ea: `0x180061554`
- end: `0x180061b29`
- name: `MF::DLNA::CheckAVCConstraintSet1`
- size: `1493`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180061b30`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180061554`
- `0x180066af0`
- `0x1800744d8`
- `0x18007c260`
- `0x18007c304`
- `0x18007f9c4`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061b00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061b00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800615ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800616a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800617d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006189d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061932`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800619c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061a5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800615ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800616a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800617d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006189d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061932`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800619c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061a5e`

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
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v15 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v40 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v34 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          if ( (unsigned __int8)byte_1800DC8D3 >= 0x10u )
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
              v31 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v28 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v37 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180061554  push    rbp
0x180061556  push    rbx
0x180061557  push    rsi
0x180061558  push    rdi
0x180061559  push    r12
0x18006155b  push    r13
0x18006155d  push    r14
0x18006155f  push    r15
0x180061561  mov     rbp, rsp
0x180061564  sub     rsp, 78h
0x180061568  mov     rbx, rcx
0x18006156b  lea     r15, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x180061572  mov     rdx, r15; char *
0x180061575  lea     rcx, [rbp+arg_0]; this
0x180061579  mov     r8d, 1F5Ch; int
0x18006157f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180061584  mov     rax, [rbx]
0x180061587  lea     r9, [rbp+arg_8]
0x18006158b  xor     r13d, r13d
0x18006158e  lea     r8, [rbp+pv]
0x180061592  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x180061599  mov     [rbp+var_40], r13
0x18006159d  mov     rcx, rbx
0x1800615a0  mov     [rbp+var_38], r13b
0x1800615a4  mov     rax, [rax+80h]
0x1800615ab  mov     [rbp+var_34], r13
0x1800615af  mov     [rbp+var_2C], r13
0x1800615b3  mov     [rbp+var_24], r13
0x1800615b7  mov     [rbp+var_1C], r13
0x1800615bb  mov     [rbp+var_10], r13
0x1800615bf  mov     [rbp+pv], r13
0x1800615c3  mov     [rbp+arg_8], r13d
0x1800615c7  mov     [rbp+arg_18], r13d
0x1800615cb  mov     [rbp+arg_0], r13d
0x1800615cf  mov     [rbp+arg_10], r13d
0x1800615d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615d8  mov     ebx, eax
0x1800615da  test    eax, eax
0x1800615dc  jns     loc_180061677
0x1800615e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800615e9  test    rcx, rcx
0x1800615ec  jnz     short loc_180061635
0x1800615ee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800615f5  nop     dword ptr [rax+rax+00h]
0x1800615fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061601  mov     rcx, rax
0x180061604  test    rax, rax
0x180061607  jz      short loc_180061627
0x180061609  mov     rax, [rax]
0x18006160c  mov     edx, 7F0h
0x180061611  mov     rax, [rax+8]
0x180061615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006161a  test    eax, eax
0x18006161c  jz      short loc_180061627
0x18006161e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061625  jmp     short loc_180061635
0x180061627  lea     rcx, qword_1800DBF70; this
0x18006162e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061635  cmp     [rcx+8], r13b
0x180061639  jz      short loc_18006165C
0x18006163b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061640  cmp     [rax+7CCh], ebx
0x180061646  jz      short loc_18006165C
0x180061648  mov     r9d, ebx; int
0x18006164b  mov     r8d, 1F6Dh; int
0x180061651  mov     rdx, r15; char *
0x180061654  mov     rcx, rax; this
0x180061657  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006165c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061663  jb      loc_180061AFC
0x180061669  mov     edx, 84h
0x18006166e  mov     [rsp+78h+var_58], ebx
0x180061672  jmp     loc_180061AE2
0x180061677  mov     edx, [rbp+arg_8]; unsigned int
0x18006167a  lea     r9, [rbp+arg_10]; unsigned int *
0x18006167e  mov     rcx, [rbp+pv]; unsigned __int8 *
0x180061682  lea     r8, [rbp+arg_0]; unsigned int *
0x180061686  call    ?MFFindNextStartCode@@YAJPEBEKPEAK1@Z; MFFindNextStartCode(uchar const *,ulong,ulong *,ulong *)
0x18006168b  mov     ebx, eax
0x18006168d  test    eax, eax
0x18006168f  jns     loc_180061726
0x180061695  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006169c  test    rcx, rcx
0x18006169f  jnz     short loc_1800616E8
0x1800616a1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800616a8  nop     dword ptr [rax+rax+00h]
0x1800616ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800616b4  mov     rcx, rax
0x1800616b7  test    rax, rax
0x1800616ba  jz      short loc_1800616DA
0x1800616bc  mov     rax, [rax]
0x1800616bf  mov     edx, 7F0h
0x1800616c4  mov     rax, [rax+8]
0x1800616c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616cd  test    eax, eax
0x1800616cf  jz      short loc_1800616DA
0x1800616d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800616d8  jmp     short loc_1800616E8
0x1800616da  lea     rcx, qword_1800DBF70; this
0x1800616e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800616e8  cmp     [rcx+8], r13b
0x1800616ec  jz      short loc_18006170F
0x1800616ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800616f3  cmp     [rax+7CCh], ebx
0x1800616f9  jz      short loc_18006170F
0x1800616fb  mov     r9d, ebx; int
0x1800616fe  mov     r8d, 1F6Fh; int
0x180061704  mov     rdx, r15; char *
0x180061707  mov     rcx, rax; this
0x18006170a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006170f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061716  jb      loc_180061AFC
0x18006171c  mov     edx, 85h
0x180061721  jmp     loc_18006166E
0x180061726  mov     edi, [rbp+arg_10]
0x180061729  mov     r14d, 1
0x18006172f  add     edi, [rbp+arg_0]
0x180061732  mov     esi, 0C00D36D5h
0x180061737  test    r14d, r14d
0x18006173a  jz      loc_180061A50
0x180061740  mov     edx, [rbp+arg_8]
0x180061743  lea     r9, [rbp+arg_10]; unsigned int *
0x180061747  mov     rcx, [rbp+pv]
0x18006174b  lea     r8, [rbp+arg_0]; unsigned int *
0x18006174f  mov     r12d, edi
0x180061752  sub     edx, edi; unsigned int
0x180061754  add     rcx, r12; unsigned __int8 *
0x180061757  call    ?MFFindNextStartCode@@YAJPEBEKPEAK1@Z; MFFindNextStartCode(uchar const *,ulong,ulong *,ulong *)
0x18006175c  mov     r15d, [rbp+arg_0]
0x180061760  mov     ebx, eax
0x180061762  mov     edx, [rbp+arg_8]
0x180061765  cmp     eax, esi
0x180061767  jnz     short loc_180061772
0x180061769  mov     esi, edx
0x18006176b  mov     r14d, r13d
0x18006176e  sub     esi, edi
0x180061770  jmp     short loc_18006177D
0x180061772  test    ebx, ebx
0x180061774  js      loc_1800619BB
0x18006177a  mov     esi, r15d
0x18006177d  mov     rcx, [rbp+pv]
0x180061781  lea     r8, [rbp+arg_18]; enum H264_NALU_TYPE *
0x180061785  add     rcx, r12; unsigned __int8 *
0x180061788  sub     edx, edi; unsigned int
0x18006178a  call    ?MFH264GetNALUType@@YAJPEBEKPEAW4H264_NALU_TYPE@@@Z; MFH264GetNALUType(uchar const *,ulong,H264_NALU_TYPE *)
0x18006178f  mov     ebx, eax
0x180061791  test    eax, eax
0x180061793  js      loc_180061926
0x180061799  cmp     [rbp+arg_18], 7
0x18006179d  jz      short loc_1800617A9
0x18006179f  mov     ecx, [rbp+arg_10]
0x1800617a2  add     ecx, r15d
0x1800617a5  add     edi, ecx
0x1800617a7  jmp     short loc_180061732
0x1800617a9  mov     r8, [rbp+pv]
0x1800617ad  lea     rcx, [rbp+var_40]; this
0x1800617b1  add     r8, r12; unsigned __int8 *
0x1800617b4  mov     edx, esi; unsigned int
0x1800617b6  call    ?ParseData@CAVCSequenceParameterSet@@QEAAJKPEBE@Z; CAVCSequenceParameterSet::ParseData(ulong,uchar const *)
0x1800617bb  mov     ebx, eax
0x1800617bd  test    eax, eax
0x1800617bf  jns     loc_18006185A
0x1800617c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800617cc  test    rcx, rcx
0x1800617cf  jnz     short loc_180061818
0x1800617d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800617d8  nop     dword ptr [rax+rax+00h]
0x1800617dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800617e4  mov     rcx, rax
0x1800617e7  test    rax, rax
0x1800617ea  jz      short loc_18006180A
0x1800617ec  mov     rax, [rax]
0x1800617ef  mov     edx, 7F0h
0x1800617f4  mov     rax, [rax+8]
0x1800617f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617fd  test    eax, eax
0x1800617ff  jz      short loc_18006180A
0x180061801  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061808  jmp     short loc_180061818
0x18006180a  lea     rcx, qword_1800DBF70; this
0x180061811  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061818  cmp     [rcx+8], r13b
0x18006181c  jz      short loc_180061843
0x18006181e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061823  cmp     [rax+7CCh], ebx
0x180061829  jz      short loc_180061843
0x18006182b  mov     r9d, ebx; int
0x18006182e  lea     rdx, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x180061835  mov     r8d, 1F90h; int
0x18006183b  mov     rcx, rax; this
0x18006183e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061843  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006184a  jb      loc_180061AFC
0x180061850  mov     edx, 88h
0x180061855  jmp     loc_18006166E
0x18006185a  cmp     dword ptr [rbp+var_1C], r13d
0x18006185e  jnz     loc_180061AFC
0x180061864  cmp     cs:byte_1800DC8D3, 10h
0x18006186b  jb      short loc_18006188C
0x18006186d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061874  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18006187b  mov     edx, 89h
0x180061880  mov     rcx, [rcx+88h]
0x180061887  call    WPP_SF_
0x18006188c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061893  mov     ebx, 0C00D65F4h
0x180061898  test    rcx, rcx
0x18006189b  jnz     short loc_1800618E4
0x18006189d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800618a4  nop     dword ptr [rax+rax+00h]
0x1800618a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618b0  mov     rcx, rax
0x1800618b3  test    rax, rax
0x1800618b6  jz      short loc_1800618D6
0x1800618b8  mov     rax, [rax]
0x1800618bb  mov     edx, 7F0h
0x1800618c0  mov     rax, [rax+8]
0x1800618c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618c9  test    eax, eax
0x1800618cb  jz      short loc_1800618D6
0x1800618cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618d4  jmp     short loc_1800618E4
0x1800618d6  lea     rcx, qword_1800DBF70; this
0x1800618dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618e4  cmp     [rcx+8], r13b
0x1800618e8  jz      short loc_18006190F
0x1800618ea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800618ef  cmp     [rax+7CCh], ebx
0x1800618f5  jz      short loc_18006190F
0x1800618f7  mov     r9d, ebx; int
0x1800618fa  lea     rdx, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x180061901  mov     r8d, 1F95h; int
0x180061907  mov     rcx, rax; this
0x18006190a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006190f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061916  jb      loc_180061AFC
0x18006191c  mov     edx, 8Ah
0x180061921  jmp     loc_18006166E
0x180061926  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006192d  test    rcx, rcx
0x180061930  jnz     short loc_180061979
0x180061932  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061939  nop     dword ptr [rax+rax+00h]
0x18006193e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061945  mov     rcx, rax
0x180061948  test    rax, rax
0x18006194b  jz      short loc_18006196B
0x18006194d  mov     rax, [rax]
0x180061950  mov     edx, 7F0h
0x180061955  mov     rax, [rax+8]
0x180061959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006195e  test    eax, eax
0x180061960  jz      short loc_18006196B
0x180061962  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061969  jmp     short loc_180061979
0x18006196b  lea     rcx, qword_1800DBF70; this
0x180061972  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061979  cmp     [rcx+8], r13b
0x18006197d  jz      short loc_1800619A4
0x18006197f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061984  cmp     [rax+7CCh], ebx
0x18006198a  jz      short loc_1800619A4
0x18006198c  mov     r9d, ebx; int
0x18006198f  lea     rdx, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x180061996  mov     r8d, 1F8Ch; int
0x18006199c  mov     rcx, rax; this
0x18006199f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800619a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800619ab  jb      loc_180061AFC
0x1800619b1  mov     edx, 87h
0x1800619b6  jmp     loc_18006166E
0x1800619bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800619c2  test    rcx, rcx
0x1800619c5  jnz     short loc_180061A0E
0x1800619c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800619ce  nop     dword ptr [rax+rax+00h]
0x1800619d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800619da  mov     rcx, rax
0x1800619dd  test    rax, rax
0x1800619e0  jz      short loc_180061A00
0x1800619e2  mov     rax, [rax]
0x1800619e5  mov     edx, 7F0h
0x1800619ea  mov     rax, [rax+8]
0x1800619ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619f3  test    eax, eax
0x1800619f5  jz      short loc_180061A00
0x1800619f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800619fe  jmp     short loc_180061A0E
0x180061a00  lea     rcx, qword_1800DBF70; this
0x180061a07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a0e  cmp     [rcx+8], r13b
0x180061a12  jz      short loc_180061A39
0x180061a14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061a19  cmp     [rax+7CCh], ebx
0x180061a1f  jz      short loc_180061A39
0x180061a21  mov     r9d, ebx; int
0x180061a24  lea     rdx, aMfDlnaCheckavc_0; "MF::DLNA::CheckAVCConstraintSet1"
0x180061a2b  mov     r8d, 1F85h; int
0x180061a31  mov     rcx, rax; this
0x180061a34  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
