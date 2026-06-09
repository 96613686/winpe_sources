# CAC3MediaSourcePlugin::ParseHeader(unsigned __int64,IMFMediaBuffer *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x1800d8870`
- end: `0x1800d9007`
- name: `?ParseHeader@CAC3MediaSourcePlugin@@UEAAJ_KPEAUIMFMediaBuffer@@0PEA_KPEAH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(CAC3MediaSourcePlugin *this, unsigned __int64, struct IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180015238`
- `0x180018b90`
- `0x1800370f0`
- `0x18003b91c`
- `0x180057dd8`
- `0x180073b14`
- `0x1800c0568`
- `0x1800d8870`
- `0x1801099f0`
- `0x18012faf0`
- `0x180130c90`
- `0x180130ce0`
- `0x180147efc`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8945`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d89ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8aba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8b6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8c34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8ce8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8db9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8e86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8f3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8945`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d89ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8aba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8b6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8c34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8ce8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8db9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8e86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8f3d`

## string_xrefs

- `0x1800d88b5`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d899c`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d8a41`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d8b11`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d8bc5`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d8c8b`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d8d3f`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d8e10`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d8edd`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800d8f94`: `CAC3MediaSourcePlugin::ParseHeader`

## pseudocode

```c
__int64 __fastcall CAC3MediaSourcePlugin::ParseHeader(
        CAC3MediaSourcePlugin *this,
        unsigned __int64 a2,
        struct IMFMediaBuffer *a3,
        unsigned __int64 a4,
        unsigned __int64 *a5,
        int *a6)
{
  __int64 v10; // rdx
  int AvailableBufferSize; // ebx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  unsigned __int64 *v20; // rcx
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  _BYTE v51[4]; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v52; // [rsp+34h] [rbp-75h] BYREF
  unsigned __int64 *v53; // [rsp+38h] [rbp-71h]
  __int64 v54; // [rsp+40h] [rbp-69h] BYREF
  int v55; // [rsp+48h] [rbp-61h]
  __int16 v56; // [rsp+4Ch] [rbp-5Dh]
  __int64 v57; // [rsp+50h] [rbp-59h]
  int v58; // [rsp+58h] [rbp-51h]
  __int64 v59; // [rsp+60h] [rbp-49h] BYREF
  int v60; // [rsp+68h] [rbp-41h]
  __int16 v61; // [rsp+6Ch] [rbp-3Dh]
  __int64 v62; // [rsp+70h] [rbp-39h]
  int v63; // [rsp+78h] [rbp-31h]
  __int64 v64; // [rsp+80h] [rbp-29h] BYREF
  int v65; // [rsp+88h] [rbp-21h]
  __int16 v66; // [rsp+8Ch] [rbp-1Dh]
  __int64 v67; // [rsp+90h] [rbp-19h]
  int v68; // [rsp+98h] [rbp-11h]
  unsigned __int8 v69[8]; // [rsp+A0h] [rbp-9h] BYREF
  int v70; // [rsp+A8h] [rbp-1h]

  v53 = a5;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v51, "CAC3MediaSourcePlugin::ParseHeader", 704);
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v52 = 0;
  *(_QWORD *)v69 = 0;
  v70 = 0;
  *((_QWORD *)this + 69) = a2;
  CSourcePluginBufferReader::SetFileLength((CAC3MediaSourcePlugin *)((char *)this + 40), a2);
  *((_QWORD *)this + 64) = 0;
  AvailableBufferSize = CSourcePluginBufferReader::AddBuffer((CAC3MediaSourcePlugin *)((char *)this + 40), a4, a3);
  if ( AvailableBufferSize < 0 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != AvailableBufferSize )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAC3MediaSourcePlugin::ParseHeader",
          716,
          AvailableBufferSize);
    }
    if ( g_wppLevels )
    {
      v15 = 39;
LABEL_107:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
        (char *)this - 8,
        AvailableBufferSize);
      goto LABEL_108;
    }
    goto LABEL_108;
  }
  AvailableBufferSize = CSourcePluginBufferReader::GetAvailableBufferSize(
                          (CAC3MediaSourcePlugin *)((char *)this + 40),
                          &v52);
  if ( AvailableBufferSize >= 0 )
  {
    if ( v52 < 0x18 )
    {
LABEL_24:
      v20 = v53;
      AvailableBufferSize = 0;
      *a6 = 1;
      *v20 = *((_QWORD *)this + 65);
      goto LABEL_108;
    }
    AvailableBufferSize = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 40), v69, 0xCu);
    if ( AvailableBufferSize < 0 )
    {
      v22 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
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
        if ( *((_DWORD *)v24 + 499) != AvailableBufferSize )
          CallStackContext::TraceFailure(v24, "CAC3MediaSourcePlugin::ParseHeader", 730, AvailableBufferSize);
      }
      if ( g_wppLevels )
      {
        v15 = 41;
        goto LABEL_107;
      }
      goto LABEL_108;
    }
    CAC3FrameHeader::Parse((CAC3FrameHeader *)&v59, v69);
    if ( (unsigned int)CAC3FrameHeader::IsValidFrameHeader((CAC3FrameHeader *)&v59) )
    {
      if ( v52 < (unsigned int)WORD2(v59) + 12 )
        goto LABEL_24;
      *((_QWORD *)this + 64) = WORD2(v59);
      AvailableBufferSize = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 40), v69, 0xCu);
      if ( AvailableBufferSize < 0 )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v31 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v33 + 499) != AvailableBufferSize )
            CallStackContext::TraceFailure(v33, "CAC3MediaSourcePlugin::ParseHeader", 753, AvailableBufferSize);
        }
        if ( g_wppLevels )
        {
          v15 = 44;
          goto LABEL_107;
        }
        goto LABEL_108;
      }
      CAC3FrameHeader::Parse((CAC3FrameHeader *)&v54, v69);
      if ( (unsigned int)CAC3FrameHeader::IsValidFrameHeader((CAC3FrameHeader *)&v54) )
      {
        if ( (unsigned __int16)(WORD1(v59) - 11) <= 5u || (unsigned __int16)(WORD1(v54) - 11) <= 5u )
        {
          v64 = 0;
          v65 = 0;
          v66 = 0;
          v67 = 0;
          v68 = 0;
          AvailableBufferSize = CAC3MediaSourcePlugin::GetAc3HeaderForMediaType(
                                  (CAC3MediaSourcePlugin *)((char *)this - 8),
                                  (const struct CAC3FrameHeader *)&v59,
                                  (const struct CAC3FrameHeader *)&v54,
                                  (struct CAC3FrameHeader *)&v64,
                                  v53,
                                  a6);
          if ( AvailableBufferSize >= 0 )
          {
            if ( !*a6 )
            {
              CSourcePluginBufferReader::RemoveAllBuffers((CAC3MediaSourcePlugin *)((char *)this + 40));
              AvailableBufferSize = CAC3MediaSourcePlugin::BuildPresentationDescriptor(
                                      (CAC3MediaSourcePlugin *)((char *)this - 8),
                                      (struct CAC3FrameHeader *)&v64);
              if ( AvailableBufferSize < 0 )
              {
                v47 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                  CallStackTracing::s_wpInstance = v48;
                  if ( v48
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                  {
                    v47 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v47 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v47 + 8) )
                {
                  v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                  if ( *((_DWORD *)v49 + 499) != AvailableBufferSize )
                    CallStackContext::TraceFailure(v49, "CAC3MediaSourcePlugin::ParseHeader", 774, AvailableBufferSize);
                }
                if ( g_wppLevels )
                {
                  v15 = 47;
                  goto LABEL_107;
                }
              }
            }
          }
          else
          {
            v43 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
              CallStackTracing::s_wpInstance = v44;
              if ( v44
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
              {
                v43 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v43 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v43 + 8) )
            {
              v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
              if ( *((_DWORD *)v45 + 499) != AvailableBufferSize )
                CallStackContext::TraceFailure(v45, "CAC3MediaSourcePlugin::ParseHeader", 767, AvailableBufferSize);
            }
            if ( g_wppLevels )
            {
              v15 = 46;
              goto LABEL_107;
            }
          }
        }
        else
        {
          CSourcePluginBufferReader::RemoveAllBuffers((CAC3MediaSourcePlugin *)((char *)this + 40));
          AvailableBufferSize = CAC3MediaSourcePlugin::BuildPresentationDescriptor(
                                  (CAC3MediaSourcePlugin *)((char *)this - 8),
                                  (struct CAC3FrameHeader *)&v59);
          if ( AvailableBufferSize < 0 )
          {
            v39 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
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
                CallStackContext::TraceFailure(v41, "CAC3MediaSourcePlugin::ParseHeader", 779, AvailableBufferSize);
            }
            if ( g_wppLevels )
            {
              v15 = 48;
              goto LABEL_107;
            }
          }
        }
        goto LABEL_108;
      }
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      AvailableBufferSize = -1072875842;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
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
        if ( *((_DWORD *)v37 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v37, "CAC3MediaSourcePlugin::ParseHeader", 760, -1072875842);
      }
      if ( !g_wppLevels )
        goto LABEL_108;
      v29 = 45;
    }
    else
    {
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      AvailableBufferSize = -1072875842;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v28, "CAC3MediaSourcePlugin::ParseHeader", 737, -1072875842);
      }
      if ( !g_wppLevels )
        goto LABEL_108;
      v29 = 42;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v29,
      WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
      (char *)this - 8,
      -1072875842);
    goto LABEL_108;
  }
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
    if ( *((_DWORD *)v19 + 499) != AvailableBufferSize )
      CallStackContext::TraceFailure(v19, "CAC3MediaSourcePlugin::ParseHeader", 718, AvailableBufferSize);
  }
  if ( g_wppLevels )
  {
    v15 = 40;
    goto LABEL_107;
  }
LABEL_108:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
  return (unsigned int)AvailableBufferSize;
}

```

## disassembly

```asm
0x1800d8870  mov     [rsp-8+arg_8], rbx
0x1800d8875  push    rbp
0x1800d8876  push    rsi
0x1800d8877  push    rdi
0x1800d8878  push    r12
0x1800d887a  push    r13
0x1800d887c  push    r14
0x1800d887e  push    r15
0x1800d8880  lea     rbp, [rsp-17h]
0x1800d8885  sub     rsp, 0C0h
0x1800d888c  mov     rax, cs:__security_cookie
0x1800d8893  xor     rax, rsp
0x1800d8896  mov     [rbp+47h+var_40], rax
0x1800d889a  mov     rax, [rbp+47h+arg_20]
0x1800d889e  mov     rdi, r8
0x1800d88a1  mov     r12, [rbp+47h+arg_28]
0x1800d88a5  mov     rbx, rdx
0x1800d88a8  mov     r13, rcx
0x1800d88ab  mov     [rbp+47h+var_B8], rax
0x1800d88af  mov     r8d, 2C0h; int
0x1800d88b5  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800d88bc  lea     rcx, [rbp+47h+var_C0]; this
0x1800d88c0  mov     rsi, r9
0x1800d88c3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d88c8  xor     ecx, ecx
0x1800d88ca  lea     r15, [r13+28h]
0x1800d88ce  xor     eax, eax
0x1800d88d0  mov     [rbp+47h+var_90], rcx
0x1800d88d4  mov     [rbp+47h+var_88], ecx
0x1800d88d7  lea     r14, [r13-8]
0x1800d88db  mov     [rbp+47h+var_84], cx
0x1800d88df  mov     rdx, rbx; unsigned __int64
0x1800d88e2  mov     [rbp+47h+var_80], rcx
0x1800d88e6  mov     [rbp+47h+var_78], ecx
0x1800d88e9  mov     [rbp+47h+var_B0], rcx
0x1800d88ed  mov     [rbp+47h+var_A8], ecx
0x1800d88f0  mov     [rbp+47h+var_A4], cx
0x1800d88f4  mov     [rbp+47h+var_A0], rcx
0x1800d88f8  mov     [rbp+47h+var_98], ecx
0x1800d88fb  mov     [rbp+47h+var_BC], ecx
0x1800d88fe  mov     rcx, r15; this
0x1800d8901  mov     qword ptr [rbp+47h+var_50], rax
0x1800d8905  mov     [rbp+47h+var_48], eax
0x1800d8908  mov     [r14+230h], rbx
0x1800d890f  call    ?SetFileLength@CSourcePluginBufferReader@@QEAAX_K@Z; CSourcePluginBufferReader::SetFileLength(unsigned __int64)
0x1800d8914  mov     r8, rdi; struct IMFMediaBuffer *
0x1800d8917  mov     qword ptr [r13+200h], 0
0x1800d8922  mov     rdx, rsi; unsigned __int64
0x1800d8925  mov     rcx, r15; this
0x1800d8928  call    ?AddBuffer@CSourcePluginBufferReader@@QEAAJ_KPEAUIMFMediaBuffer@@@Z; CSourcePluginBufferReader::AddBuffer(unsigned __int64,IMFMediaBuffer *)
0x1800d892d  xor     esi, esi
0x1800d892f  mov     ebx, eax
0x1800d8931  test    eax, eax
0x1800d8933  jns     loc_1800D89C8
0x1800d8939  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8940  test    rcx, rcx
0x1800d8943  jnz     short loc_1800D8986
0x1800d8945  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d894b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8952  mov     rcx, rax
0x1800d8955  test    rax, rax
0x1800d8958  jz      short loc_1800D8978
0x1800d895a  mov     rax, [rax]
0x1800d895d  mov     edx, 7F0h
0x1800d8962  mov     rax, [rax+8]
0x1800d8966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d896b  test    eax, eax
0x1800d896d  jz      short loc_1800D8978
0x1800d896f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8976  jmp     short loc_1800D8986
0x1800d8978  lea     rcx, qword_1801B07E0; this
0x1800d897f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8986  cmp     [rcx+8], sil
0x1800d898a  jz      short loc_1800D89B1
0x1800d898c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d8991  cmp     [rax+7CCh], ebx
0x1800d8997  jz      short loc_1800D89B1
0x1800d8999  mov     r9d, ebx; int
0x1800d899c  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800d89a3  mov     r8d, 2CCh; int
0x1800d89a9  mov     rcx, rax; this
0x1800d89ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d89b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d89b8  jb      loc_1800D8FD5
0x1800d89be  mov     edx, 27h ; '''
0x1800d89c3  jmp     loc_1800D8FB7
0x1800d89c8  lea     rdx, [rbp+47h+var_BC]; unsigned int *
0x1800d89cc  mov     rcx, r15; this
0x1800d89cf  call    ?GetAvailableBufferSize@CSourcePluginBufferReader@@QEAAJPEAK@Z; CSourcePluginBufferReader::GetAvailableBufferSize(ulong *)
0x1800d89d4  mov     ebx, eax
0x1800d89d6  test    eax, eax
0x1800d89d8  jns     loc_1800D8A6D
0x1800d89de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d89e5  test    rcx, rcx
0x1800d89e8  jnz     short loc_1800D8A2B
0x1800d89ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d89f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d89f7  mov     rcx, rax
0x1800d89fa  test    rax, rax
0x1800d89fd  jz      short loc_1800D8A1D
0x1800d89ff  mov     rax, [rax]
0x1800d8a02  mov     edx, 7F0h
0x1800d8a07  mov     rax, [rax+8]
0x1800d8a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8a10  test    eax, eax
0x1800d8a12  jz      short loc_1800D8A1D
0x1800d8a14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8a1b  jmp     short loc_1800D8A2B
0x1800d8a1d  lea     rcx, qword_1801B07E0; this
0x1800d8a24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8a2b  cmp     [rcx+8], sil
0x1800d8a2f  jz      short loc_1800D8A56
0x1800d8a31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d8a36  cmp     [rax+7CCh], ebx
0x1800d8a3c  jz      short loc_1800D8A56
0x1800d8a3e  mov     r9d, ebx; int
0x1800d8a41  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800d8a48  mov     r8d, 2CEh; int
0x1800d8a4e  mov     rcx, rax; this
0x1800d8a51  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d8a56  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d8a5d  jb      loc_1800D8FD5
0x1800d8a63  mov     edx, 28h ; '('
0x1800d8a68  jmp     loc_1800D8FB7
0x1800d8a6d  cmp     [rbp+47h+var_BC], 18h
0x1800d8a71  jnb     short loc_1800D8A90
0x1800d8a73  mov     rcx, [rbp+47h+var_B8]
0x1800d8a77  mov     ebx, esi
0x1800d8a79  mov     dword ptr [r12], 1
0x1800d8a81  mov     rax, [r13+208h]
0x1800d8a88  mov     [rcx], rax
0x1800d8a8b  jmp     loc_1800D8FD5
0x1800d8a90  mov     edi, 0Ch
0x1800d8a95  lea     rdx, [rbp+47h+var_50]; unsigned __int8 *
0x1800d8a99  mov     r8d, edi; unsigned int
0x1800d8a9c  mov     rcx, r15; this
0x1800d8a9f  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800d8aa4  mov     ebx, eax
0x1800d8aa6  test    eax, eax
0x1800d8aa8  jns     loc_1800D8B3D
0x1800d8aae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8ab5  test    rcx, rcx
0x1800d8ab8  jnz     short loc_1800D8AFB
0x1800d8aba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d8ac0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8ac7  mov     rcx, rax
0x1800d8aca  test    rax, rax
0x1800d8acd  jz      short loc_1800D8AED
0x1800d8acf  mov     rax, [rax]
0x1800d8ad2  mov     edx, 7F0h
0x1800d8ad7  mov     rax, [rax+8]
0x1800d8adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8ae0  test    eax, eax
0x1800d8ae2  jz      short loc_1800D8AED
0x1800d8ae4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8aeb  jmp     short loc_1800D8AFB
0x1800d8aed  lea     rcx, qword_1801B07E0; this
0x1800d8af4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8afb  cmp     [rcx+8], sil
0x1800d8aff  jz      short loc_1800D8B26
0x1800d8b01  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d8b06  cmp     [rax+7CCh], ebx
0x1800d8b0c  jz      short loc_1800D8B26
0x1800d8b0e  mov     r9d, ebx; int
0x1800d8b11  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800d8b18  mov     r8d, 2DAh; int
0x1800d8b1e  mov     rcx, rax; this
0x1800d8b21  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d8b26  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d8b2d  jb      loc_1800D8FD5
0x1800d8b33  mov     edx, 29h ; ')'
0x1800d8b38  jmp     loc_1800D8FB7
0x1800d8b3d  lea     rdx, [rbp+47h+var_50]; unsigned __int8 *
0x1800d8b41  lea     rcx, [rbp+47h+var_90]; this
0x1800d8b45  call    ?Parse@CAC3FrameHeader@@QEAAXPEAE@Z; CAC3FrameHeader::Parse(uchar *)
0x1800d8b4a  lea     rcx, [rbp+47h+var_90]; this
0x1800d8b4e  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x1800d8b53  test    eax, eax
0x1800d8b55  jnz     loc_1800D8BF5
0x1800d8b5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8b62  mov     edi, 0C00D36BEh
0x1800d8b67  mov     ebx, edi
0x1800d8b69  test    rcx, rcx
0x1800d8b6c  jnz     short loc_1800D8BAF
0x1800d8b6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d8b74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8b7b  mov     rcx, rax
0x1800d8b7e  test    rax, rax
0x1800d8b81  jz      short loc_1800D8BA1
0x1800d8b83  mov     rax, [rax]
0x1800d8b86  mov     edx, 7F0h
0x1800d8b8b  mov     rax, [rax+8]
0x1800d8b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8b94  test    eax, eax
0x1800d8b96  jz      short loc_1800D8BA1
0x1800d8b98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8b9f  jmp     short loc_1800D8BAF
0x1800d8ba1  lea     rcx, qword_1801B07E0; this
0x1800d8ba8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8baf  cmp     [rcx+8], sil
0x1800d8bb3  jz      short loc_1800D8BDA
0x1800d8bb5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d8bba  cmp     [rax+7CCh], edi
0x1800d8bc0  jz      short loc_1800D8BDA
0x1800d8bc2  mov     r9d, edi; int
0x1800d8bc5  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800d8bcc  mov     r8d, 2E1h; int
0x1800d8bd2  mov     rcx, rax; this
0x1800d8bd5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d8bda  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d8be1  jb      loc_1800D8FD5
0x1800d8be7  mov     edx, 2Ah ; '*'
0x1800d8bec  mov     dword ptr [rsp+0F0h+var_D0], edi
0x1800d8bf0  jmp     loc_1800D8FBB
0x1800d8bf5  movzx   eax, word ptr [rbp+47h+var_90+4]
0x1800d8bf9  add     eax, edi
0x1800d8bfb  cmp     [rbp+47h+var_BC], eax
0x1800d8bfe  jb      loc_1800D8A73
0x1800d8c04  movzx   eax, word ptr [rbp+47h+var_90+4]
0x1800d8c08  lea     rdx, [rbp+47h+var_50]; unsigned __int8 *
0x1800d8c0c  mov     r8d, edi; unsigned int
0x1800d8c0f  mov     [r13+200h], rax
0x1800d8c16  mov     rcx, r15; this
0x1800d8c19  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800d8c1e  mov     ebx, eax
0x1800d8c20  test    eax, eax
0x1800d8c22  jns     loc_1800D8CB7
0x1800d8c28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8c2f  test    rcx, rcx
0x1800d8c32  jnz     short loc_1800D8C75
0x1800d8c34  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d8c3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8c41  mov     rcx, rax
0x1800d8c44  test    rax, rax
0x1800d8c47  jz      short loc_1800D8C67
0x1800d8c49  mov     rax, [rax]
0x1800d8c4c  mov     edx, 7F0h
0x1800d8c51  mov     rax, [rax+8]
0x1800d8c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8c5a  test    eax, eax
0x1800d8c5c  jz      short loc_1800D8C67
0x1800d8c5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8c65  jmp     short loc_1800D8C75
0x1800d8c67  lea     rcx, qword_1801B07E0; this
0x1800d8c6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8c75  cmp     [rcx+8], sil
0x1800d8c79  jz      short loc_1800D8CA0
0x1800d8c7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d8c80  cmp     [rax+7CCh], ebx
0x1800d8c86  jz      short loc_1800D8CA0
0x1800d8c88  mov     r9d, ebx; int
0x1800d8c8b  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800d8c92  mov     r8d, 2F1h; int
0x1800d8c98  mov     rcx, rax; this
0x1800d8c9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d8ca0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d8ca7  jb      loc_1800D8FD5
0x1800d8cad  mov     edx, 2Ch ; ','
0x1800d8cb2  jmp     loc_1800D8FB7
0x1800d8cb7  lea     rdx, [rbp+47h+var_50]; unsigned __int8 *
0x1800d8cbb  lea     rcx, [rbp+47h+var_B0]; this
0x1800d8cbf  call    ?Parse@CAC3FrameHeader@@QEAAXPEAE@Z; CAC3FrameHeader::Parse(uchar *)
0x1800d8cc4  lea     rcx, [rbp+47h+var_B0]; this
0x1800d8cc8  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x1800d8ccd  test    eax, eax
0x1800d8ccf  jnz     loc_1800D8D6B
0x1800d8cd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8cdc  mov     edi, 0C00D36BEh
0x1800d8ce1  mov     ebx, edi
0x1800d8ce3  test    rcx, rcx
0x1800d8ce6  jnz     short loc_1800D8D29
0x1800d8ce8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d8cee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8cf5  mov     rcx, rax
0x1800d8cf8  test    rax, rax
0x1800d8cfb  jz      short loc_1800D8D1B
0x1800d8cfd  mov     rax, [rax]
0x1800d8d00  mov     edx, 7F0h
0x1800d8d05  mov     rax, [rax+8]
0x1800d8d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8d0e  test    eax, eax
0x1800d8d10  jz      short loc_1800D8D1B
0x1800d8d12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8d19  jmp     short loc_1800D8D29
0x1800d8d1b  lea     rcx, qword_1801B07E0; this
0x1800d8d22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d8d29  cmp     [rcx+8], sil
0x1800d8d2d  jz      short loc_1800D8D54
0x1800d8d2f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d8d34  cmp     [rax+7CCh], edi
0x1800d8d3a  jz      short loc_1800D8D54
0x1800d8d3c  mov     r9d, edi; int
0x1800d8d3f  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800d8d46  mov     r8d, 2F8h; int
0x1800d8d4c  mov     rcx, rax; this
0x1800d8d4f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d8d54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d8d5b  jb      loc_1800D8FD5
0x1800d8d61  mov     edx, 2Dh ; '-'
0x1800d8d66  jmp     loc_1800D8BEC
  ... truncated ...
```
