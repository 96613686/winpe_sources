# CAC3MediaSourcePlugin::GetNextSample(ulong *,ulong *,IMFSample * *,IMFMediaType * *)

- ea: `0x1800c8bd0`
- end: `0x1800c91ce`
- name: `?GetNextSample@CAC3MediaSourcePlugin@@UEAAJPEAK0PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z`
- size: `1534`
- prototype: `__int64 __fastcall(CAC3MediaSourcePlugin *__hidden this, unsigned int *, unsigned int *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180030e8c`
- `0x180035c44`
- `0x180036c30`
- `0x180079680`
- `0x1800ace8c`
- `0x1800c8bd0`
- `0x180110ed0`
- `0x180138f28`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8c7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8d5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8e0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8ec3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8f7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c9036`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c90f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8c7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8d5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8e0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8ec3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c8f7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c9036`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c90f7`
- `MFPlat!MFCreateSample` at `0x1800c8d37`
- `MFPlat!MFCreateSample` at `0x1800c8d37`

## string_xrefs

- `0x1800c8c02`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c8cdc`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c8db8`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c8e6a`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c8f21`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c8fdc`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c9094`: `CAC3MediaSourcePlugin::GetNextSample`
- `0x1800c9155`: `CAC3MediaSourcePlugin::GetNextSample`

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
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  struct IMFSample *v40; // rcx
  _BYTE v42[4]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v43; // [rsp+34h] [rbp-34h] BYREF
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v45; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v46; // [rsp+48h] [rbp-20h] BYREF

  AvailableBufferSize = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v42, "CAC3MediaSourcePlugin::GetNextSample", 1229);
  *a2 = 0;
  *a3 = 1;
  *a4 = 0;
  *a5 = 0;
  v10 = (char *)this - 16;
  v45 = 0;
  v43 = 0;
  v46 = 0;
  ppIMFSample = 0;
  if ( (unsigned int)CAC3MediaSourcePlugin::FindNextFrameHeader(
                       (CAC3MediaSourcePlugin *)((char *)this - 16),
                       &v45,
                       &v46) )
  {
    AvailableBufferSize = CSourcePluginBufferReader::GetAvailableBufferSize(
                            (CAC3MediaSourcePlugin *)((char *)this + 32),
                            &v43);
    if ( AvailableBufferSize >= 0 )
    {
      if ( v43 < v45 )
        goto LABEL_83;
      AvailableBufferSize = MFCreateSample(&ppIMFSample);
      if ( AvailableBufferSize >= 0 )
      {
        AvailableBufferSize = CSourcePluginBufferReader::ReadSampleData(
                                (CAC3MediaSourcePlugin *)((char *)this + 32),
                                ppIMFSample,
                                v45);
        if ( AvailableBufferSize >= 0 )
        {
          if ( v10[584]
            && (AvailableBufferSize = anonymous_namespace_::SetSubSampleMapping(ppIMFSample), AvailableBufferSize < 0) )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
              {
                v25 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v25 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v25 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != AvailableBufferSize )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CAC3MediaSourcePlugin::GetNextSample",
                  1265,
                  AvailableBufferSize);
            }
            if ( g_wppLevels )
            {
              v15 = 96;
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
                                      v46);
              if ( AvailableBufferSize >= 0 )
              {
                AvailableBufferSize = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                                        ppIMFSample,
                                        &MFSampleExtension_CleanPoint,
                                        1);
                if ( AvailableBufferSize >= 0 )
                {
                  v40 = ppIMFSample;
                  *((_QWORD *)this + 70) = v46 + *((_QWORD *)v10 + 72);
                  *a4 = v40;
                  ppIMFSample = 0;
                  goto LABEL_83;
                }
                v37 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
                  CallStackTracing::s_wpInstance = v38;
                  if ( v38
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                  {
                    v37 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v37 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v37 + 8) )
                {
                  v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                  if ( *((_DWORD *)v39 + 499) != AvailableBufferSize )
                    CallStackContext::TraceFailure(
                      v39,
                      "CAC3MediaSourcePlugin::GetNextSample",
                      1272,
                      AvailableBufferSize);
                }
                if ( g_wppLevels )
                {
                  v15 = 99;
                  goto LABEL_13;
                }
              }
              else
              {
                v33 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
                  CallStackTracing::s_wpInstance = v34;
                  if ( v34
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
                  v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                  if ( *((_DWORD *)v35 + 499) != AvailableBufferSize )
                    CallStackContext::TraceFailure(
                      v35,
                      "CAC3MediaSourcePlugin::GetNextSample",
                      1270,
                      AvailableBufferSize);
                }
                if ( g_wppLevels )
                {
                  v15 = 98;
                  goto LABEL_13;
                }
              }
            }
            else
            {
              v29 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
                CallStackTracing::s_wpInstance = v30;
                if ( v30
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
                {
                  v29 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v29 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v29 + 8) )
              {
                v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
                if ( *((_DWORD *)v31 + 499) != AvailableBufferSize )
                  CallStackContext::TraceFailure(v31, "CAC3MediaSourcePlugin::GetNextSample", 1268, AvailableBufferSize);
              }
              if ( g_wppLevels )
              {
                v15 = 97;
                goto LABEL_13;
              }
            }
          }
        }
        else
        {
          v21 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v21 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
            if ( *((_DWORD *)v23 + 499) != AvailableBufferSize )
              CallStackContext::TraceFailure(v23, "CAC3MediaSourcePlugin::GetNextSample", 1261, AvailableBufferSize);
          }
          if ( g_wppLevels )
          {
            v15 = 95;
            goto LABEL_13;
          }
        }
      }
      else
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
          if ( *((_DWORD *)v19 + 499) != AvailableBufferSize )
            CallStackContext::TraceFailure(v19, "CAC3MediaSourcePlugin::GetNextSample", 1259, AvailableBufferSize);
        }
        if ( g_wppLevels )
        {
          v15 = 94;
          goto LABEL_13;
        }
      }
    }
    else
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
        if ( *((_DWORD *)v14 + 499) != AvailableBufferSize )
          CallStackContext::TraceFailure(v14, "CAC3MediaSourcePlugin::GetNextSample", 1252, AvailableBufferSize);
      }
      if ( g_wppLevels )
      {
        v15 = 93;
LABEL_13:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
          (char *)this - 16,
          AvailableBufferSize);
      }
    }
  }
LABEL_83:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v42);
  return (unsigned int)AvailableBufferSize;
}

```

## disassembly

```asm
0x1800c8bd0  push    rbp
0x1800c8bd2  push    rbx
0x1800c8bd3  push    rsi
0x1800c8bd4  push    rdi
0x1800c8bd5  push    r12
0x1800c8bd7  push    r13
0x1800c8bd9  push    r14
0x1800c8bdb  push    r15
0x1800c8bdd  mov     rbp, rsp
0x1800c8be0  sub     rsp, 68h
0x1800c8be4  mov     rax, cs:__security_cookie
0x1800c8beb  xor     rax, rsp
0x1800c8bee  mov     [rbp+var_18], rax
0x1800c8bf2  mov     rbx, [rbp+arg_20]
0x1800c8bf6  mov     rsi, r8
0x1800c8bf9  mov     rdi, rdx
0x1800c8bfc  mov     r15, rcx
0x1800c8bff  xor     r13d, r13d
0x1800c8c02  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c8c09  mov     r8d, 4CDh; int
0x1800c8c0f  lea     rcx, [rbp+var_38]; this
0x1800c8c13  mov     r14d, r13d
0x1800c8c16  mov     r12, r9
0x1800c8c19  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c8c1e  mov     [rdi], r13d
0x1800c8c21  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800c8c25  mov     dword ptr [rsi], 1
0x1800c8c2b  lea     rdx, [rbp+var_28]; unsigned int *
0x1800c8c2f  mov     [r12], r13
0x1800c8c33  mov     [rbx], r13
0x1800c8c36  lea     rbx, [r15-10h]
0x1800c8c3a  mov     rcx, rbx; this
0x1800c8c3d  mov     [rbp+var_28], r13d
0x1800c8c41  mov     [rbp+var_34], r13d
0x1800c8c45  mov     [rbp+var_20], r13
0x1800c8c49  mov     [rbp+ppIMFSample], r13
0x1800c8c4d  call    ?FindNextFrameHeader@CAC3MediaSourcePlugin@@AEAAHPEAKPEA_K@Z; CAC3MediaSourcePlugin::FindNextFrameHeader(ulong *,unsigned __int64 *)
0x1800c8c52  test    eax, eax
0x1800c8c54  jz      loc_1800C919B
0x1800c8c5a  lea     rdx, [rbp+var_34]; unsigned int *
0x1800c8c5e  lea     rcx, [r15+20h]; this
0x1800c8c62  call    ?GetAvailableBufferSize@CSourcePluginBufferReader@@QEAAJPEAK@Z; CSourcePluginBufferReader::GetAvailableBufferSize(ulong *)
0x1800c8c67  mov     r14d, eax
0x1800c8c6a  test    eax, eax
0x1800c8c6c  jns     loc_1800C8D27
0x1800c8c72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8c79  test    rcx, rcx
0x1800c8c7c  jnz     short loc_1800C8CC5
0x1800c8c7e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c8c85  nop     dword ptr [rax+rax+00h]
0x1800c8c8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8c91  mov     rcx, rax
0x1800c8c94  test    rax, rax
0x1800c8c97  jz      short loc_1800C8CB7
0x1800c8c99  mov     rax, [rax]
0x1800c8c9c  mov     edx, 7F0h
0x1800c8ca1  mov     rax, [rax+8]
0x1800c8ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8caa  test    eax, eax
0x1800c8cac  jz      short loc_1800C8CB7
0x1800c8cae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8cb5  jmp     short loc_1800C8CC5
0x1800c8cb7  lea     rcx, qword_1801B97E0; this
0x1800c8cbe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8cc5  cmp     [rcx+8], r13b
0x1800c8cc9  jz      short loc_1800C8CF1
0x1800c8ccb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c8cd0  cmp     [rax+7CCh], r14d
0x1800c8cd7  jz      short loc_1800C8CF1
0x1800c8cd9  mov     r9d, r14d; int
0x1800c8cdc  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c8ce3  mov     r8d, 4E4h; int
0x1800c8ce9  mov     rcx, rax; this
0x1800c8cec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c8cf1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c8cf8  jb      loc_1800C919B
0x1800c8cfe  mov     edx, 5Dh ; ']'
0x1800c8d03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8d0a  lea     r8, WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids
0x1800c8d11  mov     r9, rbx
0x1800c8d14  mov     [rsp+68h+var_48], r14d
0x1800c8d19  mov     rcx, [rcx+10h]
0x1800c8d1d  call    WPP_SF_qD
0x1800c8d22  jmp     loc_1800C919B
0x1800c8d27  mov     eax, [rbp+var_28]
0x1800c8d2a  cmp     [rbp+var_34], eax
0x1800c8d2d  jb      loc_1800C919B
0x1800c8d33  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x1800c8d37  call    cs:__imp_MFCreateSample
0x1800c8d3e  nop     dword ptr [rax+rax+00h]
0x1800c8d43  mov     r14d, eax
0x1800c8d46  test    eax, eax
0x1800c8d48  jns     loc_1800C8DE4
0x1800c8d4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8d55  test    rcx, rcx
0x1800c8d58  jnz     short loc_1800C8DA1
0x1800c8d5a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c8d61  nop     dword ptr [rax+rax+00h]
0x1800c8d66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8d6d  mov     rcx, rax
0x1800c8d70  test    rax, rax
0x1800c8d73  jz      short loc_1800C8D93
0x1800c8d75  mov     rax, [rax]
0x1800c8d78  mov     edx, 7F0h
0x1800c8d7d  mov     rax, [rax+8]
0x1800c8d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8d86  test    eax, eax
0x1800c8d88  jz      short loc_1800C8D93
0x1800c8d8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8d91  jmp     short loc_1800C8DA1
0x1800c8d93  lea     rcx, qword_1801B97E0; this
0x1800c8d9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8da1  cmp     [rcx+8], r13b
0x1800c8da5  jz      short loc_1800C8DCD
0x1800c8da7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c8dac  cmp     [rax+7CCh], r14d
0x1800c8db3  jz      short loc_1800C8DCD
0x1800c8db5  mov     r9d, r14d; int
0x1800c8db8  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c8dbf  mov     r8d, 4EBh; int
0x1800c8dc5  mov     rcx, rax; this
0x1800c8dc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c8dcd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c8dd4  jb      loc_1800C919B
0x1800c8dda  mov     edx, 5Eh ; '^'
0x1800c8ddf  jmp     loc_1800C8D03
0x1800c8de4  mov     r8d, [rbp+var_28]; unsigned int
0x1800c8de8  lea     rcx, [r15+20h]; this
0x1800c8dec  mov     rdx, [rbp+ppIMFSample]; struct IMFSample *
0x1800c8df0  call    ?ReadSampleData@CSourcePluginBufferReader@@QEAAJPEAUIMFSample@@K@Z; CSourcePluginBufferReader::ReadSampleData(IMFSample *,ulong)
0x1800c8df5  mov     r14d, eax
0x1800c8df8  test    eax, eax
0x1800c8dfa  jns     loc_1800C8E96
0x1800c8e00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8e07  test    rcx, rcx
0x1800c8e0a  jnz     short loc_1800C8E53
0x1800c8e0c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c8e13  nop     dword ptr [rax+rax+00h]
0x1800c8e18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8e1f  mov     rcx, rax
0x1800c8e22  test    rax, rax
0x1800c8e25  jz      short loc_1800C8E45
0x1800c8e27  mov     rax, [rax]
0x1800c8e2a  mov     edx, 7F0h
0x1800c8e2f  mov     rax, [rax+8]
0x1800c8e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8e38  test    eax, eax
0x1800c8e3a  jz      short loc_1800C8E45
0x1800c8e3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8e43  jmp     short loc_1800C8E53
0x1800c8e45  lea     rcx, qword_1801B97E0; this
0x1800c8e4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8e53  cmp     [rcx+8], r13b
0x1800c8e57  jz      short loc_1800C8E7F
0x1800c8e59  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c8e5e  cmp     [rax+7CCh], r14d
0x1800c8e65  jz      short loc_1800C8E7F
0x1800c8e67  mov     r9d, r14d; int
0x1800c8e6a  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c8e71  mov     r8d, 4EDh; int
0x1800c8e77  mov     rcx, rax; this
0x1800c8e7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c8e7f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c8e86  jb      loc_1800C919B
0x1800c8e8c  mov     edx, 5Fh ; '_'
0x1800c8e91  jmp     loc_1800C8D03
0x1800c8e96  cmp     [rbx+248h], r13b
0x1800c8e9d  jz      loc_1800C8F4D
0x1800c8ea3  mov     rcx, [rbp+ppIMFSample]
0x1800c8ea7  call    _anonymous_namespace___SetSubSampleMapping
0x1800c8eac  mov     r14d, eax
0x1800c8eaf  test    eax, eax
0x1800c8eb1  jns     loc_1800C8F4D
0x1800c8eb7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8ebe  test    rcx, rcx
0x1800c8ec1  jnz     short loc_1800C8F0A
0x1800c8ec3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c8eca  nop     dword ptr [rax+rax+00h]
0x1800c8ecf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8ed6  mov     rcx, rax
0x1800c8ed9  test    rax, rax
0x1800c8edc  jz      short loc_1800C8EFC
0x1800c8ede  mov     rax, [rax]
0x1800c8ee1  mov     edx, 7F0h
0x1800c8ee6  mov     rax, [rax+8]
0x1800c8eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8eef  test    eax, eax
0x1800c8ef1  jz      short loc_1800C8EFC
0x1800c8ef3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8efa  jmp     short loc_1800C8F0A
0x1800c8efc  lea     rcx, qword_1801B97E0; this
0x1800c8f03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8f0a  cmp     [rcx+8], r13b
0x1800c8f0e  jz      short loc_1800C8F36
0x1800c8f10  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c8f15  cmp     [rax+7CCh], r14d
0x1800c8f1c  jz      short loc_1800C8F36
0x1800c8f1e  mov     r9d, r14d; int
0x1800c8f21  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c8f28  mov     r8d, 4F1h; int
0x1800c8f2e  mov     rcx, rax; this
0x1800c8f31  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c8f36  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c8f3d  jb      loc_1800C919B
0x1800c8f43  mov     edx, 60h ; '`'
0x1800c8f48  jmp     loc_1800C8D03
0x1800c8f4d  mov     rcx, [rbp+ppIMFSample]
0x1800c8f51  mov     rdx, [r15+230h]
0x1800c8f58  mov     rax, [rcx]
0x1800c8f5b  mov     rax, [rax+120h]
0x1800c8f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8f67  mov     r14d, eax
0x1800c8f6a  test    eax, eax
0x1800c8f6c  jns     loc_1800C9008
0x1800c8f72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8f79  test    rcx, rcx
0x1800c8f7c  jnz     short loc_1800C8FC5
0x1800c8f7e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c8f85  nop     dword ptr [rax+rax+00h]
0x1800c8f8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8f91  mov     rcx, rax
0x1800c8f94  test    rax, rax
0x1800c8f97  jz      short loc_1800C8FB7
0x1800c8f99  mov     rax, [rax]
0x1800c8f9c  mov     edx, 7F0h
0x1800c8fa1  mov     rax, [rax+8]
0x1800c8fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8faa  test    eax, eax
0x1800c8fac  jz      short loc_1800C8FB7
0x1800c8fae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8fb5  jmp     short loc_1800C8FC5
0x1800c8fb7  lea     rcx, qword_1801B97E0; this
0x1800c8fbe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8fc5  cmp     [rcx+8], r13b
0x1800c8fc9  jz      short loc_1800C8FF1
0x1800c8fcb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c8fd0  cmp     [rax+7CCh], r14d
0x1800c8fd7  jz      short loc_1800C8FF1
0x1800c8fd9  mov     r9d, r14d; int
0x1800c8fdc  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c8fe3  mov     r8d, 4F4h; int
0x1800c8fe9  mov     rcx, rax; this
0x1800c8fec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c8ff1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c8ff8  jb      loc_1800C919B
0x1800c8ffe  mov     edx, 61h ; 'a'
0x1800c9003  jmp     loc_1800C8D03
0x1800c9008  mov     rcx, [rbp+ppIMFSample]
0x1800c900c  mov     rdx, [rbp+var_20]
0x1800c9010  mov     rax, [rcx]
0x1800c9013  mov     rax, [rax+130h]
0x1800c901a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c901f  mov     r14d, eax
0x1800c9022  test    eax, eax
0x1800c9024  jns     loc_1800C90C0
0x1800c902a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c9031  test    rcx, rcx
0x1800c9034  jnz     short loc_1800C907D
0x1800c9036  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c903d  nop     dword ptr [rax+rax+00h]
0x1800c9042  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c9049  mov     rcx, rax
0x1800c904c  test    rax, rax
0x1800c904f  jz      short loc_1800C906F
0x1800c9051  mov     rax, [rax]
0x1800c9054  mov     edx, 7F0h
0x1800c9059  mov     rax, [rax+8]
0x1800c905d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9062  test    eax, eax
0x1800c9064  jz      short loc_1800C906F
0x1800c9066  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c906d  jmp     short loc_1800C907D
0x1800c906f  lea     rcx, qword_1801B97E0; this
0x1800c9076  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c907d  cmp     [rcx+8], r13b
0x1800c9081  jz      short loc_1800C90A9
0x1800c9083  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c9088  cmp     [rax+7CCh], r14d
0x1800c908f  jz      short loc_1800C90A9
0x1800c9091  mov     r9d, r14d; int
0x1800c9094  lea     rdx, aCac3mediasourc_12; "CAC3MediaSourcePlugin::GetNextSample"
0x1800c909b  mov     r8d, 4F6h; int
0x1800c90a1  mov     rcx, rax; this
0x1800c90a4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c90a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c90b0  jb      loc_1800C919B
0x1800c90b6  mov     edx, 62h ; 'b'
0x1800c90bb  jmp     loc_1800C8D03
0x1800c90c0  mov     rcx, [rbp+ppIMFSample]
0x1800c90c4  lea     rdx, MFSampleExtension_CleanPoint
0x1800c90cb  mov     r8d, 1
0x1800c90d1  mov     rax, [rcx]
0x1800c90d4  mov     rax, [rax+0A8h]
0x1800c90db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c90e0  mov     r14d, eax
0x1800c90e3  test    eax, eax
0x1800c90e5  jns     loc_1800C917D
0x1800c90eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c90f2  test    rcx, rcx
0x1800c90f5  jnz     short loc_1800C913E
  ... truncated ...
```
