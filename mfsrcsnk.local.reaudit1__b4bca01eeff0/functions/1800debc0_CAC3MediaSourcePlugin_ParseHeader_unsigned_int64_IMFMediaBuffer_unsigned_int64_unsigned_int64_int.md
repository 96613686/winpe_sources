# CAC3MediaSourcePlugin::ParseHeader(unsigned __int64,IMFMediaBuffer *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x1800debc0`
- end: `0x1800df38e`
- name: `?ParseHeader@CAC3MediaSourcePlugin@@UEAAJ_KPEAUIMFMediaBuffer@@0PEA_KPEAH@Z`
- size: `1998`
- prototype: `int(CAC3MediaSourcePlugin *__hidden this, unsigned __int64, struct IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180030e8c`
- `0x180034d10`
- `0x180035bb0`
- `0x18005b030`
- `0x180079680`
- `0x1800c6300`
- `0x1800debc0`
- `0x180110ed0`
- `0x180137030`
- `0x180138280`
- `0x1801382d0`
- `0x180150088`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dec95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ded40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dee16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800deed0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800def9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df056`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df12d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df200`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df2bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dec95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ded40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dee16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800deed0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800def9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df056`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df12d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df200`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df2bd`

## string_xrefs

- `0x1800dec05`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800decf2`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800ded9d`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800dee73`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800def2d`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800deff9`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800df0b3`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800df18a`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800df25d`: `CAC3MediaSourcePlugin::ParseHeader`
- `0x1800df31a`: `CAC3MediaSourcePlugin::ParseHeader`

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
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v22 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v31 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v47 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v43 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v39 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v35 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v26 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v17 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800debc0  mov     [rsp-8+arg_8], rbx
0x1800debc5  push    rbp
0x1800debc6  push    rsi
0x1800debc7  push    rdi
0x1800debc8  push    r12
0x1800debca  push    r13
0x1800debcc  push    r14
0x1800debce  push    r15
0x1800debd0  lea     rbp, [rsp-17h]
0x1800debd5  sub     rsp, 0C0h
0x1800debdc  mov     rax, cs:__security_cookie
0x1800debe3  xor     rax, rsp
0x1800debe6  mov     [rbp+47h+var_40], rax
0x1800debea  mov     rax, [rbp+47h+arg_20]
0x1800debee  mov     rdi, r8
0x1800debf1  mov     r12, [rbp+47h+arg_28]
0x1800debf5  mov     rbx, rdx
0x1800debf8  mov     r13, rcx
0x1800debfb  mov     [rbp+47h+var_B8], rax
0x1800debff  mov     r8d, 2C0h; int
0x1800dec05  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800dec0c  lea     rcx, [rbp+47h+var_C0]; this
0x1800dec10  mov     rsi, r9
0x1800dec13  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800dec18  xor     ecx, ecx
0x1800dec1a  lea     r15, [r13+28h]
0x1800dec1e  xor     eax, eax
0x1800dec20  mov     [rbp+47h+var_90], rcx
0x1800dec24  mov     [rbp+47h+var_88], ecx
0x1800dec27  lea     r14, [r13-8]
0x1800dec2b  mov     [rbp+47h+var_84], cx
0x1800dec2f  mov     rdx, rbx; unsigned __int64
0x1800dec32  mov     [rbp+47h+var_80], rcx
0x1800dec36  mov     [rbp+47h+var_78], ecx
0x1800dec39  mov     [rbp+47h+var_B0], rcx
0x1800dec3d  mov     [rbp+47h+var_A8], ecx
0x1800dec40  mov     [rbp+47h+var_A4], cx
0x1800dec44  mov     [rbp+47h+var_A0], rcx
0x1800dec48  mov     [rbp+47h+var_98], ecx
0x1800dec4b  mov     [rbp+47h+var_BC], ecx
0x1800dec4e  mov     rcx, r15; this
0x1800dec51  mov     qword ptr [rbp+47h+var_50], rax
0x1800dec55  mov     [rbp+47h+var_48], eax
0x1800dec58  mov     [r14+230h], rbx
0x1800dec5f  call    ?SetFileLength@CSourcePluginBufferReader@@QEAAX_K@Z; CSourcePluginBufferReader::SetFileLength(unsigned __int64)
0x1800dec64  mov     r8, rdi; struct IMFMediaBuffer *
0x1800dec67  mov     qword ptr [r13+200h], 0
0x1800dec72  mov     rdx, rsi; unsigned __int64
0x1800dec75  mov     rcx, r15; this
0x1800dec78  call    ?AddBuffer@CSourcePluginBufferReader@@QEAAJ_KPEAUIMFMediaBuffer@@@Z; CSourcePluginBufferReader::AddBuffer(unsigned __int64,IMFMediaBuffer *)
0x1800dec7d  xor     esi, esi
0x1800dec7f  mov     ebx, eax
0x1800dec81  test    eax, eax
0x1800dec83  jns     loc_1800DED1E
0x1800dec89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dec90  test    rcx, rcx
0x1800dec93  jnz     short loc_1800DECDC
0x1800dec95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dec9c  nop     dword ptr [rax+rax+00h]
0x1800deca1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800deca8  mov     rcx, rax
0x1800decab  test    rax, rax
0x1800decae  jz      short loc_1800DECCE
0x1800decb0  mov     rax, [rax]
0x1800decb3  mov     edx, 7F0h
0x1800decb8  mov     rax, [rax+8]
0x1800decbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800decc1  test    eax, eax
0x1800decc3  jz      short loc_1800DECCE
0x1800decc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800deccc  jmp     short loc_1800DECDC
0x1800decce  lea     rcx, qword_1801B97E0; this
0x1800decd5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800decdc  cmp     [rcx+8], sil
0x1800dece0  jz      short loc_1800DED07
0x1800dece2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dece7  cmp     [rax+7CCh], ebx
0x1800deced  jz      short loc_1800DED07
0x1800decef  mov     r9d, ebx; int
0x1800decf2  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800decf9  mov     r8d, 2CCh; int
0x1800decff  mov     rcx, rax; this
0x1800ded02  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ded07  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ded0e  jb      loc_1800DF35B
0x1800ded14  mov     edx, 27h ; '''
0x1800ded19  jmp     loc_1800DF33D
0x1800ded1e  lea     rdx, [rbp+47h+var_BC]; unsigned int *
0x1800ded22  mov     rcx, r15; this
0x1800ded25  call    ?GetAvailableBufferSize@CSourcePluginBufferReader@@QEAAJPEAK@Z; CSourcePluginBufferReader::GetAvailableBufferSize(ulong *)
0x1800ded2a  mov     ebx, eax
0x1800ded2c  test    eax, eax
0x1800ded2e  jns     loc_1800DEDC9
0x1800ded34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ded3b  test    rcx, rcx
0x1800ded3e  jnz     short loc_1800DED87
0x1800ded40  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ded47  nop     dword ptr [rax+rax+00h]
0x1800ded4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ded53  mov     rcx, rax
0x1800ded56  test    rax, rax
0x1800ded59  jz      short loc_1800DED79
0x1800ded5b  mov     rax, [rax]
0x1800ded5e  mov     edx, 7F0h
0x1800ded63  mov     rax, [rax+8]
0x1800ded67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ded6c  test    eax, eax
0x1800ded6e  jz      short loc_1800DED79
0x1800ded70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ded77  jmp     short loc_1800DED87
0x1800ded79  lea     rcx, qword_1801B97E0; this
0x1800ded80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ded87  cmp     [rcx+8], sil
0x1800ded8b  jz      short loc_1800DEDB2
0x1800ded8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ded92  cmp     [rax+7CCh], ebx
0x1800ded98  jz      short loc_1800DEDB2
0x1800ded9a  mov     r9d, ebx; int
0x1800ded9d  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800deda4  mov     r8d, 2CEh; int
0x1800dedaa  mov     rcx, rax; this
0x1800dedad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dedb2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dedb9  jb      loc_1800DF35B
0x1800dedbf  mov     edx, 28h ; '('
0x1800dedc4  jmp     loc_1800DF33D
0x1800dedc9  cmp     [rbp+47h+var_BC], 18h
0x1800dedcd  jnb     short loc_1800DEDEC
0x1800dedcf  mov     rcx, [rbp+47h+var_B8]
0x1800dedd3  mov     ebx, esi
0x1800dedd5  mov     dword ptr [r12], 1
0x1800deddd  mov     rax, [r13+208h]
0x1800dede4  mov     [rcx], rax
0x1800dede7  jmp     loc_1800DF35B
0x1800dedec  mov     edi, 0Ch
0x1800dedf1  lea     rdx, [rbp+47h+var_50]; unsigned __int8 *
0x1800dedf5  mov     r8d, edi; unsigned int
0x1800dedf8  mov     rcx, r15; this
0x1800dedfb  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800dee00  mov     ebx, eax
0x1800dee02  test    eax, eax
0x1800dee04  jns     loc_1800DEE9F
0x1800dee0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dee11  test    rcx, rcx
0x1800dee14  jnz     short loc_1800DEE5D
0x1800dee16  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dee1d  nop     dword ptr [rax+rax+00h]
0x1800dee22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dee29  mov     rcx, rax
0x1800dee2c  test    rax, rax
0x1800dee2f  jz      short loc_1800DEE4F
0x1800dee31  mov     rax, [rax]
0x1800dee34  mov     edx, 7F0h
0x1800dee39  mov     rax, [rax+8]
0x1800dee3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dee42  test    eax, eax
0x1800dee44  jz      short loc_1800DEE4F
0x1800dee46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dee4d  jmp     short loc_1800DEE5D
0x1800dee4f  lea     rcx, qword_1801B97E0; this
0x1800dee56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dee5d  cmp     [rcx+8], sil
0x1800dee61  jz      short loc_1800DEE88
0x1800dee63  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dee68  cmp     [rax+7CCh], ebx
0x1800dee6e  jz      short loc_1800DEE88
0x1800dee70  mov     r9d, ebx; int
0x1800dee73  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800dee7a  mov     r8d, 2DAh; int
0x1800dee80  mov     rcx, rax; this
0x1800dee83  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dee88  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dee8f  jb      loc_1800DF35B
0x1800dee95  mov     edx, 29h ; ')'
0x1800dee9a  jmp     loc_1800DF33D
0x1800dee9f  lea     rdx, [rbp+47h+var_50]; unsigned __int8 *
0x1800deea3  lea     rcx, [rbp+47h+var_90]; this
0x1800deea7  call    ?Parse@CAC3FrameHeader@@QEAAXPEAE@Z; CAC3FrameHeader::Parse(uchar *)
0x1800deeac  lea     rcx, [rbp+47h+var_90]; this
0x1800deeb0  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x1800deeb5  test    eax, eax
0x1800deeb7  jnz     loc_1800DEF5D
0x1800deebd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800deec4  mov     edi, 0C00D36BEh
0x1800deec9  mov     ebx, edi
0x1800deecb  test    rcx, rcx
0x1800deece  jnz     short loc_1800DEF17
0x1800deed0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800deed7  nop     dword ptr [rax+rax+00h]
0x1800deedc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800deee3  mov     rcx, rax
0x1800deee6  test    rax, rax
0x1800deee9  jz      short loc_1800DEF09
0x1800deeeb  mov     rax, [rax]
0x1800deeee  mov     edx, 7F0h
0x1800deef3  mov     rax, [rax+8]
0x1800deef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deefc  test    eax, eax
0x1800deefe  jz      short loc_1800DEF09
0x1800def00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800def07  jmp     short loc_1800DEF17
0x1800def09  lea     rcx, qword_1801B97E0; this
0x1800def10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800def17  cmp     [rcx+8], sil
0x1800def1b  jz      short loc_1800DEF42
0x1800def1d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800def22  cmp     [rax+7CCh], edi
0x1800def28  jz      short loc_1800DEF42
0x1800def2a  mov     r9d, edi; int
0x1800def2d  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800def34  mov     r8d, 2E1h; int
0x1800def3a  mov     rcx, rax; this
0x1800def3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800def42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800def49  jb      loc_1800DF35B
0x1800def4f  mov     edx, 2Ah ; '*'
0x1800def54  mov     dword ptr [rsp+0F0h+var_D0], edi
0x1800def58  jmp     loc_1800DF341
0x1800def5d  movzx   eax, word ptr [rbp+47h+var_90+4]
0x1800def61  add     eax, edi
0x1800def63  cmp     [rbp+47h+var_BC], eax
0x1800def66  jb      loc_1800DEDCF
0x1800def6c  movzx   eax, word ptr [rbp+47h+var_90+4]
0x1800def70  lea     rdx, [rbp+47h+var_50]; unsigned __int8 *
0x1800def74  mov     r8d, edi; unsigned int
0x1800def77  mov     [r13+200h], rax
0x1800def7e  mov     rcx, r15; this
0x1800def81  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800def86  mov     ebx, eax
0x1800def88  test    eax, eax
0x1800def8a  jns     loc_1800DF025
0x1800def90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800def97  test    rcx, rcx
0x1800def9a  jnz     short loc_1800DEFE3
0x1800def9c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800defa3  nop     dword ptr [rax+rax+00h]
0x1800defa8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800defaf  mov     rcx, rax
0x1800defb2  test    rax, rax
0x1800defb5  jz      short loc_1800DEFD5
0x1800defb7  mov     rax, [rax]
0x1800defba  mov     edx, 7F0h
0x1800defbf  mov     rax, [rax+8]
0x1800defc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800defc8  test    eax, eax
0x1800defca  jz      short loc_1800DEFD5
0x1800defcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800defd3  jmp     short loc_1800DEFE3
0x1800defd5  lea     rcx, qword_1801B97E0; this
0x1800defdc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800defe3  cmp     [rcx+8], sil
0x1800defe7  jz      short loc_1800DF00E
0x1800defe9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800defee  cmp     [rax+7CCh], ebx
0x1800deff4  jz      short loc_1800DF00E
0x1800deff6  mov     r9d, ebx; int
0x1800deff9  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800df000  mov     r8d, 2F1h; int
0x1800df006  mov     rcx, rax; this
0x1800df009  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800df00e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800df015  jb      loc_1800DF35B
0x1800df01b  mov     edx, 2Ch ; ','
0x1800df020  jmp     loc_1800DF33D
0x1800df025  lea     rdx, [rbp+47h+var_50]; unsigned __int8 *
0x1800df029  lea     rcx, [rbp+47h+var_B0]; this
0x1800df02d  call    ?Parse@CAC3FrameHeader@@QEAAXPEAE@Z; CAC3FrameHeader::Parse(uchar *)
0x1800df032  lea     rcx, [rbp+47h+var_B0]; this
0x1800df036  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x1800df03b  test    eax, eax
0x1800df03d  jnz     loc_1800DF0DF
0x1800df043  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800df04a  mov     edi, 0C00D36BEh
0x1800df04f  mov     ebx, edi
0x1800df051  test    rcx, rcx
0x1800df054  jnz     short loc_1800DF09D
0x1800df056  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800df05d  nop     dword ptr [rax+rax+00h]
0x1800df062  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800df069  mov     rcx, rax
0x1800df06c  test    rax, rax
0x1800df06f  jz      short loc_1800DF08F
0x1800df071  mov     rax, [rax]
0x1800df074  mov     edx, 7F0h
0x1800df079  mov     rax, [rax+8]
0x1800df07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df082  test    eax, eax
0x1800df084  jz      short loc_1800DF08F
0x1800df086  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800df08d  jmp     short loc_1800DF09D
0x1800df08f  lea     rcx, qword_1801B97E0; this
0x1800df096  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800df09d  cmp     [rcx+8], sil
0x1800df0a1  jz      short loc_1800DF0C8
0x1800df0a3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800df0a8  cmp     [rax+7CCh], edi
0x1800df0ae  jz      short loc_1800DF0C8
0x1800df0b0  mov     r9d, edi; int
0x1800df0b3  lea     rdx, aCac3mediasourc_4; "CAC3MediaSourcePlugin::ParseHeader"
0x1800df0ba  mov     r8d, 2F8h; int
  ... truncated ...
```
