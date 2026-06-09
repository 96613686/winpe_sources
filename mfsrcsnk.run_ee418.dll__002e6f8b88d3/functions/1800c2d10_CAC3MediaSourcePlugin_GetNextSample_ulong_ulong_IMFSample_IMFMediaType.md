# CAC3MediaSourcePlugin::GetNextSample(ulong *,ulong *,IMFSample * *,IMFMediaType * *)

- ea: `0x1800c2d10`
- end: `0x1800c32dd`
- name: `?GetNextSample@CAC3MediaSourcePlugin@@UEAAJPEAK0PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z`
- size: `1485`
- prototype: `__int64 __fastcall(CAC3MediaSourcePlugin *__hidden this, unsigned int *, unsigned int *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180015318`
- `0x180018b90`
- `0x180034d10`
- `0x18003b91c`
- `0x180073b14`
- `0x1800a7d2c`
- `0x1800c2d10`
- `0x1801099f0`
- `0x18013190c`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c2dbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c2e8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c2f3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c2feb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c30a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3152`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c320d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c2dbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c2e8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c2f3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c2feb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c30a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3152`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c320d`
- `MFPlat!MFCreateSample` at `0x1800c2e71`
- `MFPlat!MFCreateSample` at `0x1800c2e71`

## string_xrefs

- `0x1800c2d42`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c2e16`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c2ee6`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c2f92`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c3043`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c30f8`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c31aa`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c3265`: `CAC3MediaSourcePlugin::GetNextSample`

## pseudocode

```c
__int64 __fastcall CAC3MediaSourcePlugin::GetNextSample(
        CAC3MediaSourcePlugin *this,
        unsigned int *a2,
        unsigned int *a3,
        struct IMFSample **a4,
        struct IMFMediaType **a5)
{
  HRESULT AvailableBufferSize; // r14d
  char *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  struct IMFSample *v54; // rcx
  _BYTE v56[4]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v57; // [rsp+34h] [rbp-34h] BYREF
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v59; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v60; // [rsp+48h] [rbp-20h] BYREF

  AvailableBufferSize = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v56, "CAC3MediaSourcePlugin::GetNextSample", 1229);
  *a2 = 0;
  *a3 = 1;
  *a4 = 0;
  *a5 = 0;
  v10 = (char *)this - 16;
  v59 = 0;
  v57 = 0;
  v60 = 0;
  ppIMFSample = 0;
  if ( (unsigned int)CAC3MediaSourcePlugin::FindNextFrameHeader(
                       (CAC3MediaSourcePlugin *)((char *)this - 16),
                       &v59,
                       &v60) )
  {
    AvailableBufferSize = CSourcePluginBufferReader::GetAvailableBufferSize(
                            (CAC3MediaSourcePlugin *)((char *)this + 32),
                            &v57);
    if ( AvailableBufferSize >= 0 )
    {
      if ( v57 < v59 )
        goto LABEL_83;
      AvailableBufferSize = MFCreateSample(&ppIMFSample);
      if ( AvailableBufferSize >= 0 )
      {
        AvailableBufferSize = CSourcePluginBufferReader::ReadSampleData(
                                (CAC3MediaSourcePlugin *)((char *)this + 32),
                                ppIMFSample,
                                v59);
        if ( AvailableBufferSize >= 0 )
        {
          if ( v10[584]
            && (AvailableBufferSize = anonymous_namespace_::SetSubSampleMapping(ppIMFSample), AvailableBufferSize < 0) )
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != AvailableBufferSize )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CAC3MediaSourcePlugin::GetNextSample",
                  1265,
                  AvailableBufferSize);
            }
            if ( g_wppLevels )
            {
              v17 = 96;
              goto LABEL_13;
            }
          }
          else
          {
            AvailableBufferSize = ((__int64 (__fastcall *)(IMFSample *, _QWORD))ppIMFSample->lpVtbl->SetSampleTime)(
                                    ppIMFSample,
                                    *((_QWORD *)this + 70));
            if ( AvailableBufferSize >= 0 )
            {
              AvailableBufferSize = ((__int64 (__fastcall *)(IMFSample *, unsigned __int64))ppIMFSample->lpVtbl->SetSampleDuration)(
                                      ppIMFSample,
                                      v60);
              if ( AvailableBufferSize >= 0 )
              {
                AvailableBufferSize = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                                        ppIMFSample,
                                        &MFSampleExtension_CleanPoint,
                                        1);
                if ( AvailableBufferSize >= 0 )
                {
                  v54 = ppIMFSample;
                  *((_QWORD *)this + 70) = v60 + *((_QWORD *)v10 + 72);
                  *a4 = v54;
                  ppIMFSample = 0;
                  goto LABEL_83;
                }
                v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49, v50);
                  CallStackTracing::s_wpInstance = v52;
                  if ( v52
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
                  {
                    v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v51 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v51 + 8) )
                {
                  v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
                  if ( *((_DWORD *)v53 + 499) != AvailableBufferSize )
                    CallStackContext::TraceFailure(
                      v53,
                      "CAC3MediaSourcePlugin::GetNextSample",
                      1272,
                      AvailableBufferSize);
                }
                if ( g_wppLevels )
                {
                  v17 = 99;
                  goto LABEL_13;
                }
              }
              else
              {
                v45 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
                  CallStackTracing::s_wpInstance = v46;
                  if ( v46
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                  {
                    v45 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v45 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v45 + 8) )
                {
                  v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
                  if ( *((_DWORD *)v47 + 499) != AvailableBufferSize )
                    CallStackContext::TraceFailure(
                      v47,
                      "CAC3MediaSourcePlugin::GetNextSample",
                      1270,
                      AvailableBufferSize);
                }
                if ( g_wppLevels )
                {
                  v17 = 98;
                  goto LABEL_13;
                }
              }
            }
            else
            {
              v39 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
                CallStackTracing::s_wpInstance = v40;
                if ( v40
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                {
                  v39 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v39 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v39 + 8) )
              {
                v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
                if ( *((_DWORD *)v41 + 499) != AvailableBufferSize )
                  CallStackContext::TraceFailure(v41, "CAC3MediaSourcePlugin::GetNextSample", 1268, AvailableBufferSize);
              }
              if ( g_wppLevels )
              {
                v17 = 97;
                goto LABEL_13;
              }
            }
          }
        }
        else
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
            CallStackTracing::s_wpInstance = v28;
            if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
            {
              v27 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v27 + 8) )
          {
            v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)v29 + 499) != AvailableBufferSize )
              CallStackContext::TraceFailure(v29, "CAC3MediaSourcePlugin::GetNextSample", 1261, AvailableBufferSize);
          }
          if ( g_wppLevels )
          {
            v17 = 95;
            goto LABEL_13;
          }
        }
      }
      else
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != AvailableBufferSize )
            CallStackContext::TraceFailure(v23, "CAC3MediaSourcePlugin::GetNextSample", 1259, AvailableBufferSize);
        }
        if ( g_wppLevels )
        {
          v17 = 94;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != AvailableBufferSize )
          CallStackContext::TraceFailure(v16, "CAC3MediaSourcePlugin::GetNextSample", 1252, AvailableBufferSize);
      }
      if ( g_wppLevels )
      {
        v17 = 93;
LABEL_13:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          &WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
          (char *)this - 16,
          AvailableBufferSize);
      }
    }
  }
LABEL_83:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
  return (unsigned int)AvailableBufferSize;
}

```

## disassembly

```asm
0x1800c2d10  push    rbp
0x1800c2d12  push    rbx
0x1800c2d13  push    rsi
0x1800c2d14  push    rdi
0x1800c2d15  push    r12
0x1800c2d17  push    r13
0x1800c2d19  push    r14
0x1800c2d1b  push    r15
0x1800c2d1d  mov     rbp, rsp
0x1800c2d20  sub     rsp, 68h
0x1800c2d24  mov     rax, cs:__security_cookie
0x1800c2d2b  xor     rax, rsp
0x1800c2d2e  mov     [rbp+var_18], rax
0x1800c2d32  mov     rbx, [rbp+arg_20]
0x1800c2d36  mov     rsi, r8
0x1800c2d39  mov     rdi, rdx
0x1800c2d3c  mov     r15, rcx
0x1800c2d3f  xor     r13d, r13d
0x1800c2d42  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c2d49  mov     r8d, 4CDh; int
0x1800c2d4f  lea     rcx, [rbp+var_38]; this
0x1800c2d53  mov     r14d, r13d
0x1800c2d56  mov     r12, r9
0x1800c2d59  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c2d5e  mov     [rdi], r13d
0x1800c2d61  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800c2d65  mov     dword ptr [rsi], 1
0x1800c2d6b  lea     rdx, [rbp+var_28]; unsigned int *
0x1800c2d6f  mov     [r12], r13
0x1800c2d73  mov     [rbx], r13
0x1800c2d76  lea     rbx, [r15-10h]
0x1800c2d7a  mov     rcx, rbx; this
0x1800c2d7d  mov     [rbp+var_28], r13d
0x1800c2d81  mov     [rbp+var_34], r13d
0x1800c2d85  mov     [rbp+var_20], r13
0x1800c2d89  mov     [rbp+ppIMFSample], r13
0x1800c2d8d  call    ?FindNextFrameHeader@CAC3MediaSourcePlugin@@AEAAHPEAKPEA_K@Z; CAC3MediaSourcePlugin::FindNextFrameHeader(ulong *,unsigned __int64 *)
0x1800c2d92  test    eax, eax
0x1800c2d94  jz      loc_1800C32AB
0x1800c2d9a  lea     rdx, [rbp+var_34]; unsigned int *
0x1800c2d9e  lea     rcx, [r15+20h]; this
0x1800c2da2  call    ?GetAvailableBufferSize@CSourcePluginBufferReader@@QEAAJPEAK@Z; CSourcePluginBufferReader::GetAvailableBufferSize(ulong *)
0x1800c2da7  mov     r14d, eax
0x1800c2daa  test    eax, eax
0x1800c2dac  jns     loc_1800C2E61
0x1800c2db2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2db9  test    rcx, rcx
0x1800c2dbc  jnz     short loc_1800C2DFF
0x1800c2dbe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c2dc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2dcb  mov     rcx, rax
0x1800c2dce  test    rax, rax
0x1800c2dd1  jz      short loc_1800C2DF1
0x1800c2dd3  mov     rax, [rax]
0x1800c2dd6  mov     edx, 7F0h
0x1800c2ddb  mov     rax, [rax+8]
0x1800c2ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2de4  test    eax, eax
0x1800c2de6  jz      short loc_1800C2DF1
0x1800c2de8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2def  jmp     short loc_1800C2DFF
0x1800c2df1  lea     rcx, qword_1801B07E0; this
0x1800c2df8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2dff  cmp     [rcx+8], r13b
0x1800c2e03  jz      short loc_1800C2E2B
0x1800c2e05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c2e0a  cmp     [rax+7CCh], r14d
0x1800c2e11  jz      short loc_1800C2E2B
0x1800c2e13  mov     r9d, r14d; int
0x1800c2e16  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c2e1d  mov     r8d, 4E4h; int
0x1800c2e23  mov     rcx, rax; this
0x1800c2e26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c2e2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c2e32  jb      loc_1800C32AB
0x1800c2e38  mov     edx, 5Dh ; ']'
0x1800c2e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2e44  lea     r8, WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids
0x1800c2e4b  mov     r9, rbx
0x1800c2e4e  mov     [rsp+68h+var_48], r14d
0x1800c2e53  mov     rcx, [rcx+10h]
0x1800c2e57  call    WPP_SF_qD
0x1800c2e5c  jmp     loc_1800C32AB
0x1800c2e61  mov     eax, [rbp+var_28]
0x1800c2e64  cmp     [rbp+var_34], eax
0x1800c2e67  jb      loc_1800C32AB
0x1800c2e6d  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x1800c2e71  call    cs:__imp_MFCreateSample
0x1800c2e77  mov     r14d, eax
0x1800c2e7a  test    eax, eax
0x1800c2e7c  jns     loc_1800C2F12
0x1800c2e82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2e89  test    rcx, rcx
0x1800c2e8c  jnz     short loc_1800C2ECF
0x1800c2e8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c2e94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2e9b  mov     rcx, rax
0x1800c2e9e  test    rax, rax
0x1800c2ea1  jz      short loc_1800C2EC1
0x1800c2ea3  mov     rax, [rax]
0x1800c2ea6  mov     edx, 7F0h
0x1800c2eab  mov     rax, [rax+8]
0x1800c2eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2eb4  test    eax, eax
0x1800c2eb6  jz      short loc_1800C2EC1
0x1800c2eb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2ebf  jmp     short loc_1800C2ECF
0x1800c2ec1  lea     rcx, qword_1801B07E0; this
0x1800c2ec8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2ecf  cmp     [rcx+8], r13b
0x1800c2ed3  jz      short loc_1800C2EFB
0x1800c2ed5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c2eda  cmp     [rax+7CCh], r14d
0x1800c2ee1  jz      short loc_1800C2EFB
0x1800c2ee3  mov     r9d, r14d; int
0x1800c2ee6  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c2eed  mov     r8d, 4EBh; int
0x1800c2ef3  mov     rcx, rax; this
0x1800c2ef6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c2efb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c2f02  jb      loc_1800C32AB
0x1800c2f08  mov     edx, 5Eh ; '^'
0x1800c2f0d  jmp     loc_1800C2E3D
0x1800c2f12  mov     r8d, [rbp+var_28]; unsigned int
0x1800c2f16  lea     rcx, [r15+20h]; this
0x1800c2f1a  mov     rdx, [rbp+ppIMFSample]; struct IMFSample *
0x1800c2f1e  call    ?ReadSampleData@CSourcePluginBufferReader@@QEAAJPEAUIMFSample@@K@Z; CSourcePluginBufferReader::ReadSampleData(IMFSample *,ulong)
0x1800c2f23  mov     r14d, eax
0x1800c2f26  test    eax, eax
0x1800c2f28  jns     loc_1800C2FBE
0x1800c2f2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2f35  test    rcx, rcx
0x1800c2f38  jnz     short loc_1800C2F7B
0x1800c2f3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c2f40  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2f47  mov     rcx, rax
0x1800c2f4a  test    rax, rax
0x1800c2f4d  jz      short loc_1800C2F6D
0x1800c2f4f  mov     rax, [rax]
0x1800c2f52  mov     edx, 7F0h
0x1800c2f57  mov     rax, [rax+8]
0x1800c2f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2f60  test    eax, eax
0x1800c2f62  jz      short loc_1800C2F6D
0x1800c2f64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2f6b  jmp     short loc_1800C2F7B
0x1800c2f6d  lea     rcx, qword_1801B07E0; this
0x1800c2f74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2f7b  cmp     [rcx+8], r13b
0x1800c2f7f  jz      short loc_1800C2FA7
0x1800c2f81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c2f86  cmp     [rax+7CCh], r14d
0x1800c2f8d  jz      short loc_1800C2FA7
0x1800c2f8f  mov     r9d, r14d; int
0x1800c2f92  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c2f99  mov     r8d, 4EDh; int
0x1800c2f9f  mov     rcx, rax; this
0x1800c2fa2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c2fa7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c2fae  jb      loc_1800C32AB
0x1800c2fb4  mov     edx, 5Fh ; '_'
0x1800c2fb9  jmp     loc_1800C2E3D
0x1800c2fbe  cmp     [rbx+248h], r13b
0x1800c2fc5  jz      loc_1800C306F
0x1800c2fcb  mov     rcx, [rbp+ppIMFSample]
0x1800c2fcf  call    _anonymous_namespace___SetSubSampleMapping
0x1800c2fd4  mov     r14d, eax
0x1800c2fd7  test    eax, eax
0x1800c2fd9  jns     loc_1800C306F
0x1800c2fdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2fe6  test    rcx, rcx
0x1800c2fe9  jnz     short loc_1800C302C
0x1800c2feb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c2ff1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2ff8  mov     rcx, rax
0x1800c2ffb  test    rax, rax
0x1800c2ffe  jz      short loc_1800C301E
0x1800c3000  mov     rax, [rax]
0x1800c3003  mov     edx, 7F0h
0x1800c3008  mov     rax, [rax+8]
0x1800c300c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3011  test    eax, eax
0x1800c3013  jz      short loc_1800C301E
0x1800c3015  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c301c  jmp     short loc_1800C302C
0x1800c301e  lea     rcx, qword_1801B07E0; this
0x1800c3025  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c302c  cmp     [rcx+8], r13b
0x1800c3030  jz      short loc_1800C3058
0x1800c3032  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c3037  cmp     [rax+7CCh], r14d
0x1800c303e  jz      short loc_1800C3058
0x1800c3040  mov     r9d, r14d; int
0x1800c3043  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c304a  mov     r8d, 4F1h; int
0x1800c3050  mov     rcx, rax; this
0x1800c3053  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c3058  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c305f  jb      loc_1800C32AB
0x1800c3065  mov     edx, 60h ; '`'
0x1800c306a  jmp     loc_1800C2E3D
0x1800c306f  mov     rcx, [rbp+ppIMFSample]
0x1800c3073  mov     rdx, [r15+230h]
0x1800c307a  mov     rax, [rcx]
0x1800c307d  mov     rax, [rax+120h]
0x1800c3084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3089  mov     r14d, eax
0x1800c308c  test    eax, eax
0x1800c308e  jns     loc_1800C3124
0x1800c3094  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c309b  test    rcx, rcx
0x1800c309e  jnz     short loc_1800C30E1
0x1800c30a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c30a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c30ad  mov     rcx, rax
0x1800c30b0  test    rax, rax
0x1800c30b3  jz      short loc_1800C30D3
0x1800c30b5  mov     rax, [rax]
0x1800c30b8  mov     edx, 7F0h
0x1800c30bd  mov     rax, [rax+8]
0x1800c30c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c30c6  test    eax, eax
0x1800c30c8  jz      short loc_1800C30D3
0x1800c30ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c30d1  jmp     short loc_1800C30E1
0x1800c30d3  lea     rcx, qword_1801B07E0; this
0x1800c30da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c30e1  cmp     [rcx+8], r13b
0x1800c30e5  jz      short loc_1800C310D
0x1800c30e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c30ec  cmp     [rax+7CCh], r14d
0x1800c30f3  jz      short loc_1800C310D
0x1800c30f5  mov     r9d, r14d; int
0x1800c30f8  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c30ff  mov     r8d, 4F4h; int
0x1800c3105  mov     rcx, rax; this
0x1800c3108  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c310d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c3114  jb      loc_1800C32AB
0x1800c311a  mov     edx, 61h ; 'a'
0x1800c311f  jmp     loc_1800C2E3D
0x1800c3124  mov     rcx, [rbp+ppIMFSample]
0x1800c3128  mov     rdx, [rbp+var_20]
0x1800c312c  mov     rax, [rcx]
0x1800c312f  mov     rax, [rax+130h]
0x1800c3136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c313b  mov     r14d, eax
0x1800c313e  test    eax, eax
0x1800c3140  jns     loc_1800C31D6
0x1800c3146  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c314d  test    rcx, rcx
0x1800c3150  jnz     short loc_1800C3193
0x1800c3152  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c3158  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c315f  mov     rcx, rax
0x1800c3162  test    rax, rax
0x1800c3165  jz      short loc_1800C3185
0x1800c3167  mov     rax, [rax]
0x1800c316a  mov     edx, 7F0h
0x1800c316f  mov     rax, [rax+8]
0x1800c3173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3178  test    eax, eax
0x1800c317a  jz      short loc_1800C3185
0x1800c317c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3183  jmp     short loc_1800C3193
0x1800c3185  lea     rcx, qword_1801B07E0; this
0x1800c318c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3193  cmp     [rcx+8], r13b
0x1800c3197  jz      short loc_1800C31BF
0x1800c3199  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c319e  cmp     [rax+7CCh], r14d
0x1800c31a5  jz      short loc_1800C31BF
0x1800c31a7  mov     r9d, r14d; int
0x1800c31aa  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c31b1  mov     r8d, 4F6h; int
0x1800c31b7  mov     rcx, rax; this
0x1800c31ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c31bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c31c6  jb      loc_1800C32AB
0x1800c31cc  mov     edx, 62h ; 'b'
0x1800c31d1  jmp     loc_1800C2E3D
0x1800c31d6  mov     rcx, [rbp+ppIMFSample]
0x1800c31da  lea     rdx, MFSampleExtension_CleanPoint
0x1800c31e1  mov     r8d, 1
0x1800c31e7  mov     rax, [rcx]
0x1800c31ea  mov     rax, [rax+0A8h]
0x1800c31f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c31f6  mov     r14d, eax
0x1800c31f9  test    eax, eax
0x1800c31fb  jns     loc_1800C328D
0x1800c3201  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3208  test    rcx, rcx
0x1800c320b  jnz     short loc_1800C324E
0x1800c320d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c3213  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c321a  mov     rcx, rax
0x1800c321d  test    rax, rax
0x1800c3220  jz      short loc_1800C3240
0x1800c3222  mov     rax, [rax]
0x1800c3225  mov     edx, 7F0h
  ... truncated ...
```
