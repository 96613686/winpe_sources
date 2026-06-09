# CMPEGFrame::DeSerializeFrameBody(uchar const *,ulong,unsigned __int64 *)

- ea: `0x18004c430`
- end: `0x18004d413`
- name: `?DeSerializeFrameBody@CMPEGFrame@@UEAAJPEBEKPEA_K@Z`
- size: `4067`
- prototype: `__int64 __fastcall(CMPEGFrame *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x18004c430`
- `0x18004d41c`
- `0x1800651d4`
- `0x180071a44`
- `0x180073b14`
- `0x1801095a8`
- `0x180115a1c`
- `0x1801723d4`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c4c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c5e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c683`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c76b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c830`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c8cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c9b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ca52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cb34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cbcf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ccb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cd54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ce58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cef3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d005`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d0bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d1e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d2ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d358`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c4c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c5e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c683`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c76b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c830`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c8cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c9b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ca52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cb34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cbcf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ccb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cd54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ce58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cef3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d005`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d0bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d1e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d2ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d358`

## string_xrefs

- `0x18004c73a`: `InfoXingVBRICMPEGFrame::OnHeaderRead`
- `0x18004c46c`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004c63e`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004c6dd`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004c7c5`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004c88a`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004c925`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004ca11`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004caac`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004cb8e`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004cc29`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004cd0d`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004cdae`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004ceb2`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004cf4d`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004d05f`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004d116`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004d241`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004d305`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18004d3b2`: `CMPEGFrame::DeSerializeFrameBody`

## pseudocode

```c
__int64 __fastcall CMPEGFrame::DeSerializeFrameBody(
        __int64 this,
        const unsigned __int8 *a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  wchar_t *v4; // rbx
  unsigned __int64 v6; // r15
  CMPEGFrame *v8; // rsi
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  unsigned int v11; // ebp
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdi
  __int16 v15; // ax
  int v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rbp
  int v21; // edi
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  unsigned int v38; // ecx
  int v39; // r8d
  unsigned __int64 v40; // rcx
  __int64 v41; // r8
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  unsigned int v46; // edx
  int v47; // ecx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rax
  unsigned int v53; // edx
  int v54; // ecx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // r8
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 v64; // rax
  unsigned int v65; // edx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  int v70; // eax
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  unsigned int v73; // eax
  void *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r9
  wchar_t *v78; // rbx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  unsigned int v84; // [rsp+20h] [rbp-58h]
  _BYTE v85[4]; // [rsp+30h] [rbp-48h] BYREF
  _DWORD Buf1[17]; // [rsp+34h] [rbp-44h] BYREF

  v4 = (wchar_t *)CallStackTracing::s_wpInstance;
  v6 = (unsigned int)a3;
  v8 = (CMPEGFrame *)this;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
    this = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)this < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      this *= 2;
      *((_QWORD *)ThreadRelativeContext + this) = "CMPEGFrame::DeSerializeFrameBody";
      *((_DWORD *)ThreadRelativeContext + 2 * this + 2) = 441;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v4 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  v10 = *((unsigned int *)v8 + 18);
  if ( (_DWORD)v10 )
  {
    if ( (unsigned int)v6 < 2 )
    {
      v11 = -1072875842;
      if ( !v4 )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10, a3, a4);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v4 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v4 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v4 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
        if ( *((_DWORD *)v13 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v13, "CMPEGFrame::DeSerializeFrameBody", 449, -1072875842);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids,
          v8,
          -1072875842);
      goto LABEL_259;
    }
    this = *(unsigned __int16 *)a2;
    LODWORD(v14) = 2;
    *((_DWORD *)v8 + 29) -= 2;
    *((_WORD *)v8 + 56) = this;
    v15 = (unsigned __int8)this << 8;
    LOWORD(this) = BYTE1(this);
    *((_WORD *)v8 + 56) = this | v15;
    v11 = 0;
  }
  else
  {
    v11 = 0;
    LODWORD(v14) = 0;
  }
  v16 = *((_DWORD *)v8 + 34);
  if ( v16 == 10 )
  {
    v18 = 32;
    if ( *((_DWORD *)v8 + 23) == 3 )
      v18 = 17;
    v17 = v18;
  }
  else
  {
    if ( v16 != 20 && v16 != 25 )
      goto LABEL_220;
    v17 = 17;
    if ( *((_DWORD *)v8 + 23) == 3 )
      v17 = 9;
  }
  v19 = (unsigned int)(v17 - 2);
  if ( !(_DWORD)v10 )
    v19 = (unsigned int)v17;
  v20 = (unsigned int)(v14 + v19 + 4);
  if ( (unsigned int)v20 < (unsigned int)v14 )
  {
    v21 = -2147024362;
    v11 = -2147024362;
    if ( !v4 )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v17, v10, a3, a4);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v23 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v23, "CMPEGFrame::DeSerializeFrameBody", 515, -2147024362);
    }
    if ( g_wppLevels )
    {
      v24 = 28;
LABEL_43:
      v84 = v21;
LABEL_258:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids, v8, v84);
      goto LABEL_259;
    }
    goto LABEL_259;
  }
  if ( (unsigned int)v6 >= (unsigned int)v20 )
  {
    Buf1[0] = *(_DWORD *)&a2[v19 + (unsigned int)v14];
    if ( !memcmp_0(Buf1, "XingVBRICMPEGFrame::OnHeaderRead", 4u) )
    {
      if ( g_wppLevels >= 8u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids);
        v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      v14 = (unsigned int)(v20 + 4);
      if ( (unsigned int)v14 < (unsigned int)v20 )
      {
        v21 = -2147024362;
        v11 = -2147024362;
        if ( !v4 )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27, v29, v30);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v35 + 499) != -2147024362 )
            CallStackContext::TraceFailure(v35, "CMPEGFrame::DeSerializeFrameBody", 546, -2147024362);
        }
        if ( g_wppLevels )
        {
          v24 = 31;
          goto LABEL_43;
        }
        goto LABEL_259;
      }
      if ( (unsigned int)v6 < (unsigned int)v14 )
      {
        v21 = -1072875842;
        v11 = -1072875842;
        if ( !v4 )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27, v29, v30);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v37 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v37, "CMPEGFrame::DeSerializeFrameBody", 549, -1072875842);
        }
        if ( g_wppLevels )
        {
          v24 = 32;
          goto LABEL_43;
        }
        goto LABEL_259;
      }
      v38 = *(_DWORD *)&a2[v20];
      *((_DWORD *)v8 + 43) = v38;
      v38 >>= 16;
      v39 = (unsigned __int8)v38 | (*((unsigned __int8 *)v8 + 172) << 16) | *((_WORD *)v8 + 86) & 0xFF00;
      v40 = v38 >> 8;
      v41 = (unsigned int)v40 | (v39 << 8);
      *((_DWORD *)v8 + 43) = v41;
      if ( (v41 & 1) != 0 )
      {
        v30 = (unsigned int)(v20 + 8);
        if ( (unsigned int)v30 < (unsigned int)v14 )
        {
          v21 = -2147024362;
          v11 = -2147024362;
          if ( !v4 )
          {
            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40, v27, v41, v30);
            CallStackTracing::s_wpInstance = v42;
            if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v43 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v43, "CMPEGFrame::DeSerializeFrameBody", 561, -2147024362);
          }
          if ( g_wppLevels )
          {
            v24 = 33;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        if ( (unsigned int)v6 < (unsigned int)v30 )
        {
          v21 = -1072875842;
          v11 = -1072875842;
          if ( !v4 )
          {
            v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40, v27, v41, v30);
            CallStackTracing::s_wpInstance = v44;
            if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v45 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v45, "CMPEGFrame::DeSerializeFrameBody", 564, -1072875842);
          }
          if ( g_wppLevels )
          {
            v24 = 34;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        v46 = *(_DWORD *)&a2[v14];
        LODWORD(v14) = v20 + 8;
        *((_DWORD *)v8 + 42) = v46;
        v46 >>= 16;
        v47 = (unsigned __int8)v46 | (*((unsigned __int8 *)v8 + 168) << 16) | *((_WORD *)v8 + 84) & 0xFF00;
        v27 = v46 >> 8;
        v40 = (unsigned int)v27 | (v47 << 8);
        *((_DWORD *)v8 + 42) = v40;
      }
      if ( (v41 & 2) != 0 )
      {
        v30 = (unsigned int)(v14 + 4);
        if ( (unsigned int)v30 < (unsigned int)v14 )
        {
          v21 = -2147024362;
          v11 = -2147024362;
          if ( !v4 )
          {
            v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40, v27, v41, v30);
            CallStackTracing::s_wpInstance = v48;
            if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v49 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v49, "CMPEGFrame::DeSerializeFrameBody", 574, -2147024362);
          }
          if ( g_wppLevels )
          {
            v24 = 35;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        if ( (unsigned int)v6 < (unsigned int)v30 )
        {
          v21 = -1072875842;
          v11 = -1072875842;
          if ( !v4 )
          {
            v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40, v27, v41, v30);
            CallStackTracing::s_wpInstance = v50;
            if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v51 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v51, "CMPEGFrame::DeSerializeFrameBody", 577, -1072875842);
          }
          if ( g_wppLevels )
          {
            v24 = 36;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        v52 = (unsigned int)v14;
        LODWORD(v14) = v14 + 4;
        v53 = *(_DWORD *)&a2[v52];
        *((_DWORD *)v8 + 44) = v53;
        v53 >>= 16;
        v54 = (unsigned __int8)v53 | (*((unsigned __int8 *)v8 + 176) << 16) | *((_WORD *)v8 + 88) & 0xFF00;
        v27 = v53 >> 8;
        v40 = (unsigned int)v27 | (v54 << 8);
        *((_DWORD *)v8 + 44) = v40;
      }
      if ( (v41 & 4) != 0 )
      {
        v30 = (unsigned int)(v14 + 100);
        if ( (unsigned int)v30 < (unsigned int)v14 )
        {
          v21 = -2147024362;
          v11 = -2147024362;
          if ( !v4 )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40, v27, v41, v30);
            CallStackTracing::s_wpInstance = v55;
            if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v56 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v56, "CMPEGFrame::DeSerializeFrameBody", 587, -2147024362);
          }
          if ( g_wppLevels )
          {
            v24 = 37;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        v27 = (unsigned int)v14;
        v40 = (unsigned int)v14 + 100LL;
        if ( v6 < v40 )
        {
          v21 = -1072875842;
          v11 = -1072875842;
          if ( !v4 )
          {
            v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40, v27, v41, v30);
            CallStackTracing::s_wpInstance = v57;
            if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v58 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v58, "CMPEGFrame::DeSerializeFrameBody", 590, -1072875842);
          }
          if ( g_wppLevels )
          {
            v24 = 38;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        LODWORD(v14) = v14 + 100;
        *(_OWORD *)((char *)v8 + 180) = *(_OWORD *)&a2[v27];
        *(_OWORD *)((char *)v8 + 196) = *(_OWORD *)&a2[v27 + 16];
        *(_OWORD *)((char *)v8 + 212) = *(_OWORD *)&a2[v27 + 32];
        *(_OWORD *)((char *)v8 + 228) = *(_OWORD *)&a2[v27 + 48];
        *(_OWORD *)((char *)v8 + 244) = *(_OWORD *)&a2[v27 + 64];
        *(_OWORD *)((char *)v8 + 260) = *(_OWORD *)&a2[v27 + 80];
        *((_DWORD *)v8 + 69) = *(_DWORD *)&a2[v27 + 96];
      }
      if ( (v41 & 8) != 0 )
      {
        v59 = (unsigned int)(v14 + 4);
        if ( (unsigned int)v59 < (unsigned int)v14 )
        {
          v21 = -2147024362;
          v11 = -2147024362;
          if ( !v4 )
          {
            v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40, v27, v59, v30);
            CallStackTracing::s_wpInstance = v60;
            if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v61 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v61, "CMPEGFrame::DeSerializeFrameBody", 599, -2147024362);
          }
          if ( g_wppLevels )
          {
            v24 = 39;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        if ( (unsigned int)v6 < (unsigned int)v59 )
        {
          v21 = -1072875842;
          v11 = -1072875842;
          if ( !v4 )
          {
            v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40, v27, v59, v30);
            CallStackTracing::s_wpInstance = v62;
            if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v63 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v63, "CMPEGFrame::DeSerializeFrameBody", 602, -1072875842);
          }
          if ( g_wppLevels )
          {
            v24 = 40;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        v64 = (unsigned int)v14;
        LODWORD(v14) = v14 + 4;
        v65 = *(_DWORD *)&a2[v64];
        *((_DWORD *)v8 + 70) = v65;
        *((_DWORD *)v8 + 70) = HIBYTE(v65)
                             | ((BYTE2(v65) | (*((unsigned __int8 *)v8 + 280) << 16) | *((_WORD *)v8 + 140) & 0xFF00) << 8);
      }
      CMPEGFrame::ValidateXingHeader(v8);
      *((_DWORD *)v8 + 41) = 1;
      if ( g_wppLevels >= 8u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids);
      v4 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else if ( !memcmp_0(Buf1, "InfoXingVBRICMPEGFrame::OnHeaderRead", 4u) )
    {
      LODWORD(v14) = v14 + 116;
      if ( (unsigned int)v6 < (unsigned int)v14 )
      {
        v21 = -1072875842;
        v11 = -1072875842;
        if ( !v4 )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v31, a3, a4);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v33 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v33, "CMPEGFrame::DeSerializeFrameBody", 624, -1072875842);
        }
        if ( g_wppLevels )
        {
          v24 = 43;
          goto LABEL_43;
        }
        goto LABEL_259;
      }
    }
    v10 = (unsigned int)(v14 + 4);
    if ( (unsigned int)v10 < (unsigned int)v14 )
    {
      v21 = -2147024362;
      v11 = -2147024362;
      if ( !v4 )
      {
        v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10, a3, a4);
        CallStackTracing::s_wpInstance = v66;
        if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
        {
          v4 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v4 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v4 + 8) )
      {
        v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
        if ( *((_DWORD *)v67 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v67, "CMPEGFrame::DeSerializeFrameBody", 631, -2147024362);
      }
      if ( g_wppLevels )
      {
        v24 = 44;
        goto LABEL_43;
      }
      goto LABEL_259;
    }
    if ( (unsigned int)v6 >= (unsigned int)v10
      && (this = *(unsigned int *)&a2[(unsigned int)v14], (_DWORD)this == *(_DWORD *)"LAME") )
    {
      LODWORD(v14) = v14 + 24;
      if ( (int)v10 + 20 < (unsigned int)v10 )
      {
        v21 = -2147024362;
        v11 = -2147024362;
        if ( !v4 )
        {
          v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10, a3, a4);
          CallStackTracing::s_wpInstance = v68;
          if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v69 + 499) != -2147024362 )
            CallStackContext::TraceFailure(v69, "CMPEGFrame::DeSerializeFrameBody", 652, -2147024362);
        }
        if ( g_wppLevels )
        {
          v24 = 45;
          goto LABEL_43;
        }
        goto LABEL_259;
      }
      v11 = 0;
      if ( (unsigned int)v6 >= (unsigned int)v14 )
      {
        *((_DWORD *)v8 + 72) = (a2[v10 + 18] >> 4) | (16 * a2[v10 + 17]);
        this = a2[v10 + 19] | ((unsigned __int8)(a2[v10 + 18] & 0xF) << 8);
        *((_DWORD *)v8 + 71) = 1;
        *((_DWORD *)v8 + 73) = this;
        if ( g_wppLevels >= 8u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids);
          v4 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
      }
      else
      {
        LODWORD(v14) = v10;
      }
    }
    else
    {
      v11 = 0;
    }
LABEL_220:
    if ( (unsigned int)v6 > 0x20 )
    {
      v70 = CMPEGFrame::ParseVbriIfPresent(v8, a2 + 32, (int)v6 - 32, 1);
      v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      v11 = v70;
      if ( v70 < 0 )
      {
        if ( !CallStackTracing::s_wpInstance )
        {
          v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10, a3, a4);
          CallStackTracing::s_wpInstance = v71;
          if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v72 + 499) != v11 )
            CallStackContext::TraceFailure(v72, "CMPEGFrame::DeSerializeFrameBody", 672, v11);
        }
        if ( !g_wppLevels )
          goto LABEL_259;
        v24 = 47;
        goto LABEL_257;
      }
    }
    v73 = *((_DWORD *)v8 + 29);
    if ( v73 >= (unsigned int)v14 )
    {
      if ( v73 > (unsigned int)v14 )
      {
        v74 = operator new(v73 - (unsigned int)v14);
        *((_QWORD *)v8 + 43) = v74;
        if ( !v74 )
        {
          v78 = (wchar_t *)CallStackTracing::s_wpInstance;
          v11 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v75, v76, v77);
            CallStackTracing::s_wpInstance = v79;
            if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
            {
              v78 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v78 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v78 + 8) )
          {
            v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
            if ( *((_DWORD *)v80 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v80, "CMPEGFrame::DeSerializeFrameBody", 680, -2147024882);
          }
          if ( !g_wppLevels )
            goto LABEL_259;
          v24 = 48;
          goto LABEL_257;
        }
        memcpy_0(v74, &a2[(unsigned int)v14], (unsigned int)(*((_DWORD *)v8 + 29) - v14));
      }
      *a4 = *((unsigned int *)v8 + 29);
      goto LABEL_259;
    }
    v11 = -2147418113;
    if ( !v4 )
    {
      v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10, a3, a4);
      CallStackTracing::s_wpInstance = v81;
      if ( v81 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
      {
        v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v82 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v82, "CMPEGFrame::DeSerializeFrameBody", 687, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_259;
    v24 = 49;
LABEL_257:
    v84 = v11;
    goto LABEL_258;
  }
  v21 = -1072875842;
  v11 = -1072875842;
  if ( !v4 )
  {
    v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v17, v10, a3, a4);
    CallStackTracing::s_wpInstance = v25;
    if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
    {
      v4 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v4 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
    if ( *((_DWORD *)v26 + 499) != -1072875842 )
      CallStackContext::TraceFailure(v26, "CMPEGFrame::DeSerializeFrameBody", 518, -1072875842);
  }
  if ( g_wppLevels )
  {
    v24 = 29;
    goto LABEL_43;
  }
LABEL_259:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v85);
  return v11;
}

```

## disassembly

```asm
0x18004c430  mov     [rsp+arg_10], rbx
0x18004c435  push    rbp
0x18004c436  push    rsi
0x18004c437  push    rdi
0x18004c438  push    r12
0x18004c43a  push    r13
0x18004c43c  push    r14
0x18004c43e  push    r15
0x18004c440  sub     rsp, 40h
0x18004c444  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c44b  mov     r13, r9
0x18004c44e  mov     r15d, r8d
0x18004c451  mov     r12, rdx
0x18004c454  mov     rsi, rcx
0x18004c457  test    rbx, rbx
0x18004c45a  jnz     short loc_18004C468
0x18004c45c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004c461  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c468  cmp     byte ptr [rbx+8], 0
0x18004c46c  lea     r14, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x18004c473  jz      short loc_18004C4A7
0x18004c475  mov     rcx, rbx; this
0x18004c478  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c47d  mov     ecx, [rax+7C4h]
0x18004c483  cmp     ecx, [rax+7C8h]
0x18004c489  jnb     short loc_18004C49A
0x18004c48b  add     rcx, rcx
0x18004c48e  mov     [rax+rcx*8], r14
0x18004c492  mov     dword ptr [rax+rcx*8+8], 1B9h
0x18004c49a  inc     dword ptr [rax+7C4h]
0x18004c4a0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c4a7  mov     edx, [rsi+48h]
0x18004c4aa  test    edx, edx
0x18004c4ac  jz      loc_18004C57D
0x18004c4b2  cmp     r15d, 2
0x18004c4b6  jnb     loc_18004C555
0x18004c4bc  mov     edi, 0C00D36BEh
0x18004c4c1  mov     ebp, edi
0x18004c4c3  test    rbx, rbx
0x18004c4c6  jnz     short loc_18004C509
0x18004c4c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c4ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c4d5  mov     rcx, rax
0x18004c4d8  test    rax, rax
0x18004c4db  jz      short loc_18004C4FB
0x18004c4dd  mov     rax, [rax]
0x18004c4e0  mov     edx, 7F0h
0x18004c4e5  mov     rax, [rax+8]
0x18004c4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4ee  test    eax, eax
0x18004c4f0  jz      short loc_18004C4FB
0x18004c4f2  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c4f9  jmp     short loc_18004C509
0x18004c4fb  lea     rbx, qword_1801B07E0
0x18004c502  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c509  cmp     byte ptr [rbx+8], 0
0x18004c50d  jz      short loc_18004C533
0x18004c50f  mov     rcx, rbx; this
0x18004c512  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c517  cmp     [rax+7CCh], edi
0x18004c51d  jz      short loc_18004C533
0x18004c51f  mov     r9d, edi; int
0x18004c522  mov     r8d, 1C1h; int
0x18004c528  mov     rdx, r14; char *
0x18004c52b  mov     rcx, rax; this
0x18004c52e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c533  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c53a  jb      loc_18004D3EF
0x18004c540  mov     edx, 1Bh
0x18004c545  mov     [rsp+78h+var_58], edi
0x18004c549  lea     r8, WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids
0x18004c550  jmp     loc_18004D3DC
0x18004c555  movzx   ecx, word ptr [r12]
0x18004c55a  mov     edi, 2
0x18004c55f  add     dword ptr [rsi+74h], 0FFFFFFFEh
0x18004c563  movzx   eax, cl
0x18004c566  mov     [rsi+70h], cx
0x18004c56a  shl     ax, 8
0x18004c56e  shr     cx, 8
0x18004c572  or      ax, cx
0x18004c575  mov     [rsi+70h], ax
0x18004c579  xor     ebp, ebp
0x18004c57b  jmp     short loc_18004C581
0x18004c57d  xor     ebp, ebp
0x18004c57f  xor     edi, edi
0x18004c581  mov     eax, [rsi+88h]
0x18004c587  lea     r14, WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids
0x18004c58e  cmp     eax, 0Ah
0x18004c591  jz      short loc_18004C5B2
0x18004c593  cmp     eax, 14h
0x18004c596  jz      short loc_18004C5A1
0x18004c598  cmp     eax, 19h
0x18004c59b  jnz     loc_18004D1B3
0x18004c5a1  cmp     dword ptr [rsi+5Ch], 3
0x18004c5a5  mov     ecx, 11h
0x18004c5aa  lea     eax, [rcx-8]
0x18004c5ad  cmovz   ecx, eax
0x18004c5b0  jmp     short loc_18004C5C3
0x18004c5b2  cmp     dword ptr [rsi+5Ch], 3
0x18004c5b6  mov     eax, 20h ; ' '
0x18004c5bb  lea     ecx, [rax-0Fh]
0x18004c5be  cmovz   eax, ecx
0x18004c5c1  mov     ecx, eax
0x18004c5c3  test    edx, edx
0x18004c5c5  lea     eax, [rcx-2]
0x18004c5c8  cmovz   eax, ecx
0x18004c5cb  lea     ebp, [rax+4]
0x18004c5ce  add     ebp, edi
0x18004c5d0  cmp     ebp, edi
0x18004c5d2  jnb     loc_18004C66E
0x18004c5d8  mov     edi, 80070216h
0x18004c5dd  mov     ebp, edi
0x18004c5df  test    rbx, rbx
0x18004c5e2  jnz     short loc_18004C625
0x18004c5e4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c5ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c5f1  mov     rcx, rax
0x18004c5f4  test    rax, rax
0x18004c5f7  jz      short loc_18004C617
0x18004c5f9  mov     rax, [rax]
0x18004c5fc  mov     edx, 7F0h
0x18004c601  mov     rax, [rax+8]
0x18004c605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c60a  test    eax, eax
0x18004c60c  jz      short loc_18004C617
0x18004c60e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c615  jmp     short loc_18004C625
0x18004c617  lea     rbx, qword_1801B07E0
0x18004c61e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c625  cmp     byte ptr [rbx+8], 0
0x18004c629  jz      short loc_18004C653
0x18004c62b  mov     rcx, rbx; this
0x18004c62e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c633  cmp     [rax+7CCh], edi
0x18004c639  jz      short loc_18004C653
0x18004c63b  mov     r9d, edi; int
0x18004c63e  lea     rdx, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x18004c645  mov     r8d, 203h; int
0x18004c64b  mov     rcx, rax; this
0x18004c64e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c653  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c65a  jb      loc_18004D3EF
0x18004c660  mov     edx, 1Ch
0x18004c665  mov     [rsp+78h+var_58], edi
0x18004c669  jmp     loc_18004D3D9
0x18004c66e  cmp     r15d, ebp
0x18004c671  jnb     loc_18004C709
0x18004c677  mov     edi, 0C00D36BEh
0x18004c67c  mov     ebp, edi
0x18004c67e  test    rbx, rbx
0x18004c681  jnz     short loc_18004C6C4
0x18004c683  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c689  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c690  mov     rcx, rax
0x18004c693  test    rax, rax
0x18004c696  jz      short loc_18004C6B6
0x18004c698  mov     rax, [rax]
0x18004c69b  mov     edx, 7F0h
0x18004c6a0  mov     rax, [rax+8]
0x18004c6a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6a9  test    eax, eax
0x18004c6ab  jz      short loc_18004C6B6
0x18004c6ad  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c6b4  jmp     short loc_18004C6C4
0x18004c6b6  lea     rbx, qword_1801B07E0
0x18004c6bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c6c4  cmp     byte ptr [rbx+8], 0
0x18004c6c8  jz      short loc_18004C6F2
0x18004c6ca  mov     rcx, rbx; this
0x18004c6cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c6d2  cmp     [rax+7CCh], edi
0x18004c6d8  jz      short loc_18004C6F2
0x18004c6da  mov     r9d, edi; int
0x18004c6dd  lea     rdx, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x18004c6e4  mov     r8d, 206h; int
0x18004c6ea  mov     rcx, rax; this
0x18004c6ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c6f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c6f9  jb      loc_18004D3EF
0x18004c6ff  mov     edx, 1Dh
0x18004c704  jmp     loc_18004C665
0x18004c709  mov     ecx, edi
0x18004c70b  lea     rdx, aInfoxingvbricm+4; Buf2
0x18004c712  add     rax, r12
0x18004c715  mov     r8d, 4; Size
0x18004c71b  mov     ecx, [rcx+rax]
0x18004c71e  mov     [rsp+78h+Buf1], ecx
0x18004c722  lea     rcx, [rsp+78h+Buf1]; Buf1
0x18004c727  call    memcmp_0
0x18004c72c  test    eax, eax
0x18004c72e  jz      loc_18004C7F1
0x18004c734  mov     r8d, 4; Size
0x18004c73a  lea     rdx, aInfoxingvbricm; "InfoXingVBRICMPEGFrame::OnHeaderRead"
0x18004c741  lea     rcx, [rsp+78h+Buf1]; Buf1
0x18004c746  call    memcmp_0
0x18004c74b  test    eax, eax
0x18004c74d  jnz     loc_18004CFEE
0x18004c753  add     edi, 74h ; 't'
0x18004c756  cmp     r15d, edi
0x18004c759  jnb     loc_18004CFEE
0x18004c75f  mov     edi, 0C00D36BEh
0x18004c764  mov     ebp, edi
0x18004c766  test    rbx, rbx
0x18004c769  jnz     short loc_18004C7AC
0x18004c76b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c771  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c778  mov     rcx, rax
0x18004c77b  test    rax, rax
0x18004c77e  jz      short loc_18004C79E
0x18004c780  mov     rax, [rax]
0x18004c783  mov     edx, 7F0h
0x18004c788  mov     rax, [rax+8]
0x18004c78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c791  test    eax, eax
0x18004c793  jz      short loc_18004C79E
0x18004c795  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c79c  jmp     short loc_18004C7AC
0x18004c79e  lea     rbx, qword_1801B07E0
0x18004c7a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c7ac  cmp     byte ptr [rbx+8], 0
0x18004c7b0  jz      short loc_18004C7DA
0x18004c7b2  mov     rcx, rbx; this
0x18004c7b5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c7ba  cmp     [rax+7CCh], edi
0x18004c7c0  jz      short loc_18004C7DA
0x18004c7c2  mov     r9d, edi; int
0x18004c7c5  lea     rdx, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x18004c7cc  mov     r8d, 270h; int
0x18004c7d2  mov     rcx, rax; this
0x18004c7d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c7da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c7e1  jb      loc_18004D3EF
0x18004c7e7  mov     edx, 2Bh ; '+'
0x18004c7ec  jmp     loc_18004C665
0x18004c7f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18004c7f8  jb      short loc_18004C819
0x18004c7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c801  mov     edx, 1Eh
0x18004c806  mov     r8, r14
0x18004c809  mov     rcx, [rcx+10h]
0x18004c80d  call    WPP_SF_
0x18004c812  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c819  lea     edi, [rbp+4]
0x18004c81c  cmp     edi, ebp
0x18004c81e  jnb     loc_18004C8B6
0x18004c824  mov     edi, 80070216h
0x18004c829  mov     ebp, edi
0x18004c82b  test    rbx, rbx
0x18004c82e  jnz     short loc_18004C871
0x18004c830  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c836  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c83d  mov     rcx, rax
0x18004c840  test    rax, rax
0x18004c843  jz      short loc_18004C863
0x18004c845  mov     rax, [rax]
0x18004c848  mov     edx, 7F0h
0x18004c84d  mov     rax, [rax+8]
0x18004c851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c856  test    eax, eax
0x18004c858  jz      short loc_18004C863
0x18004c85a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c861  jmp     short loc_18004C871
0x18004c863  lea     rbx, qword_1801B07E0
0x18004c86a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c871  cmp     byte ptr [rbx+8], 0
0x18004c875  jz      short loc_18004C89F
0x18004c877  mov     rcx, rbx; this
0x18004c87a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c87f  cmp     [rax+7CCh], edi
0x18004c885  jz      short loc_18004C89F
0x18004c887  mov     r9d, edi; int
0x18004c88a  lea     rdx, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x18004c891  mov     r8d, 222h; int
0x18004c897  mov     rcx, rax; this
0x18004c89a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c89f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c8a6  jb      loc_18004D3EF
0x18004c8ac  mov     edx, 1Fh
0x18004c8b1  jmp     loc_18004C665
0x18004c8b6  cmp     r15d, edi
0x18004c8b9  jnb     loc_18004C951
0x18004c8bf  mov     edi, 0C00D36BEh
0x18004c8c4  mov     ebp, edi
0x18004c8c6  test    rbx, rbx
0x18004c8c9  jnz     short loc_18004C90C
0x18004c8cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c8d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c8d8  mov     rcx, rax
0x18004c8db  test    rax, rax
0x18004c8de  jz      short loc_18004C8FE
0x18004c8e0  mov     rax, [rax]
0x18004c8e3  mov     edx, 7F0h
0x18004c8e8  mov     rax, [rax+8]
0x18004c8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8f1  test    eax, eax
0x18004c8f3  jz      short loc_18004C8FE
0x18004c8f5  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c8fc  jmp     short loc_18004C90C
0x18004c8fe  lea     rbx, qword_1801B07E0
0x18004c905  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
