# CMPEGFrame::DeSerializeFrameBody(uchar const *,ulong,unsigned __int64 *)

- ea: `0x18004fe90`
- end: `0x180050ee6`
- name: `?DeSerializeFrameBody@CMPEGFrame@@UEAAJPEBEKPEA_K@Z`
- size: `4182`
- prototype: `__int64 __fastcall(CMPEGFrame *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x18004fe90`
- `0x180050eec`
- `0x1800660a8`
- `0x180077708`
- `0x180079680`
- `0x180110a94`
- `0x18011cbac`
- `0x18017b734`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ff28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005004a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800500ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800501dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800502a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005043b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800504dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800505c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050665`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005074f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800507f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050900`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800509a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ab9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050b76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ca7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050d71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050e24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ff28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005004a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800500ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800501dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800502a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005043b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800504dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800505c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050665`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005074f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800507f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050900`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800509a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ab9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050b76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ca7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050d71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050e24`

## string_xrefs

- `0x18004fecc`: `CMPEGFrame::DeSerializeFrameBody`
- `0x1800500aa`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18005014f`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18005023d`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050308`: `CMPEGFrame::DeSerializeFrameBody`
- `0x1800503a9`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18005049b`: `CMPEGFrame::DeSerializeFrameBody`
- `0x18005053c`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050624`: `CMPEGFrame::DeSerializeFrameBody`
- `0x1800506c5`: `CMPEGFrame::DeSerializeFrameBody`
- `0x1800507af`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050856`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050960`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050a01`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050b19`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050bd6`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050d07`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050dd1`: `CMPEGFrame::DeSerializeFrameBody`
- `0x180050e84`: `CMPEGFrame::DeSerializeFrameBody`

## pseudocode

```c
__int64 __fastcall CMPEGFrame::DeSerializeFrameBody(
        __int64 this,
        const unsigned __int8 *a2,
        unsigned int a3,
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
  __int64 v29; // rdx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  unsigned int v36; // ecx
  int v37; // r8d
  unsigned __int64 v38; // rcx
  int v39; // r8d
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  unsigned int v44; // edx
  int v45; // ecx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rax
  unsigned int v51; // edx
  int v52; // ecx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rax
  unsigned int v62; // edx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  int v67; // eax
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  unsigned int v70; // eax
  void *v71; // rax
  __int64 v72; // rdx
  wchar_t *v73; // rbx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  unsigned int v79; // [rsp+20h] [rbp-58h]
  _BYTE v80[4]; // [rsp+30h] [rbp-48h] BYREF
  _DWORD Buf1[17]; // [rsp+34h] [rbp-44h] BYREF

  v4 = (wchar_t *)CallStackTracing::s_wpInstance;
  v6 = a3;
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
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v4 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v4 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v17, v10);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v79 = v21;
LABEL_258:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids, v8, v79);
      goto LABEL_259;
    }
    goto LABEL_259;
  }
  if ( (unsigned int)v6 >= (unsigned int)v20 )
  {
    Buf1[0] = *(_DWORD *)&a2[v19 + (unsigned int)v14];
    if ( !memcmp_0(Buf1, "XingVBRI", 4u) )
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
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v33 + 499) != -2147024362 )
            CallStackContext::TraceFailure(v33, "CMPEGFrame::DeSerializeFrameBody", 546, -2147024362);
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
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v35 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v35, "CMPEGFrame::DeSerializeFrameBody", 549, -1072875842);
        }
        if ( g_wppLevels )
        {
          v24 = 32;
          goto LABEL_43;
        }
        goto LABEL_259;
      }
      v36 = *(_DWORD *)&a2[v20];
      *((_DWORD *)v8 + 43) = v36;
      v36 >>= 16;
      v37 = (unsigned __int8)v36 | (*((unsigned __int8 *)v8 + 172) << 16) | *((_WORD *)v8 + 86) & 0xFF00;
      v38 = v36 >> 8;
      v39 = v38 | (v37 << 8);
      *((_DWORD *)v8 + 43) = v39;
      if ( (v39 & 1) != 0 )
      {
        if ( (int)v20 + 8 < (unsigned int)(v20 + 4) )
        {
          v21 = -2147024362;
          v11 = -2147024362;
          if ( !v4 )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v27);
            CallStackTracing::s_wpInstance = v40;
            if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v41 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v41, "CMPEGFrame::DeSerializeFrameBody", 561, -2147024362);
          }
          if ( g_wppLevels )
          {
            v24 = 33;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        if ( (unsigned int)v6 < (int)v20 + 8 )
        {
          v21 = -1072875842;
          v11 = -1072875842;
          if ( !v4 )
          {
            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v27);
            CallStackTracing::s_wpInstance = v42;
            if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v43 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v43, "CMPEGFrame::DeSerializeFrameBody", 564, -1072875842);
          }
          if ( g_wppLevels )
          {
            v24 = 34;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        v44 = *(_DWORD *)&a2[v14];
        LODWORD(v14) = v20 + 8;
        *((_DWORD *)v8 + 42) = v44;
        v44 >>= 16;
        v45 = (unsigned __int8)v44 | (*((unsigned __int8 *)v8 + 168) << 16) | *((_WORD *)v8 + 84) & 0xFF00;
        v27 = v44 >> 8;
        v38 = (unsigned int)v27 | (v45 << 8);
        *((_DWORD *)v8 + 42) = v38;
      }
      if ( (v39 & 2) != 0 )
      {
        if ( (int)v14 + 4 < (unsigned int)v14 )
        {
          v21 = -2147024362;
          v11 = -2147024362;
          if ( !v4 )
          {
            v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v27);
            CallStackTracing::s_wpInstance = v46;
            if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v47 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v47, "CMPEGFrame::DeSerializeFrameBody", 574, -2147024362);
          }
          if ( g_wppLevels )
          {
            v24 = 35;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        if ( (unsigned int)v6 < (int)v14 + 4 )
        {
          v21 = -1072875842;
          v11 = -1072875842;
          if ( !v4 )
          {
            v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v27);
            CallStackTracing::s_wpInstance = v48;
            if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v49 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v49, "CMPEGFrame::DeSerializeFrameBody", 577, -1072875842);
          }
          if ( g_wppLevels )
          {
            v24 = 36;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        v50 = (unsigned int)v14;
        LODWORD(v14) = v14 + 4;
        v51 = *(_DWORD *)&a2[v50];
        *((_DWORD *)v8 + 44) = v51;
        v51 >>= 16;
        v52 = (unsigned __int8)v51 | (*((unsigned __int8 *)v8 + 176) << 16) | *((_WORD *)v8 + 88) & 0xFF00;
        v27 = v51 >> 8;
        v38 = (unsigned int)v27 | (v52 << 8);
        *((_DWORD *)v8 + 44) = v38;
      }
      if ( (v39 & 4) != 0 )
      {
        if ( (int)v14 + 100 < (unsigned int)v14 )
        {
          v21 = -2147024362;
          v11 = -2147024362;
          if ( !v4 )
          {
            v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v27);
            CallStackTracing::s_wpInstance = v53;
            if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v54 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v54, "CMPEGFrame::DeSerializeFrameBody", 587, -2147024362);
          }
          if ( g_wppLevels )
          {
            v24 = 37;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        v27 = (unsigned int)v14;
        v38 = (unsigned int)v14 + 100LL;
        if ( v6 < v38 )
        {
          v21 = -1072875842;
          v11 = -1072875842;
          if ( !v4 )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v27);
            CallStackTracing::s_wpInstance = v55;
            if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v56 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v56, "CMPEGFrame::DeSerializeFrameBody", 590, -1072875842);
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
      if ( (v39 & 8) != 0 )
      {
        if ( (int)v14 + 4 < (unsigned int)v14 )
        {
          v21 = -2147024362;
          v11 = -2147024362;
          if ( !v4 )
          {
            v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v27);
            CallStackTracing::s_wpInstance = v57;
            if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v58 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v58, "CMPEGFrame::DeSerializeFrameBody", 599, -2147024362);
          }
          if ( g_wppLevels )
          {
            v24 = 39;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        if ( (unsigned int)v6 < (int)v14 + 4 )
        {
          v21 = -1072875842;
          v11 = -1072875842;
          if ( !v4 )
          {
            v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v27);
            CallStackTracing::s_wpInstance = v59;
            if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)v60 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v60, "CMPEGFrame::DeSerializeFrameBody", 602, -1072875842);
          }
          if ( g_wppLevels )
          {
            v24 = 40;
            goto LABEL_43;
          }
          goto LABEL_259;
        }
        v61 = (unsigned int)v14;
        LODWORD(v14) = v14 + 4;
        v62 = *(_DWORD *)&a2[v61];
        *((_DWORD *)v8 + 70) = v62;
        *((_DWORD *)v8 + 70) = HIBYTE(v62)
                             | ((BYTE2(v62) | (*((unsigned __int8 *)v8 + 280) << 16) | *((_WORD *)v8 + 140) & 0xFF00) << 8);
      }
      CMPEGFrame::ValidateXingHeader(v8);
      *((_DWORD *)v8 + 41) = 1;
      if ( g_wppLevels >= 8u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids);
      v4 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else if ( !memcmp_0(Buf1, "InfoXingVBRI", 4u) )
    {
      LODWORD(v14) = v14 + 116;
      if ( (unsigned int)v6 < (unsigned int)v14 )
      {
        v21 = -1072875842;
        v11 = -1072875842;
        if ( !v4 )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v29);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v31 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v31, "CMPEGFrame::DeSerializeFrameBody", 624, -1072875842);
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
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10);
        CallStackTracing::s_wpInstance = v63;
        if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
        {
          v4 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v4 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v4 + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
        if ( *((_DWORD *)v64 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v64, "CMPEGFrame::DeSerializeFrameBody", 631, -2147024362);
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
          v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10);
          CallStackTracing::s_wpInstance = v65;
          if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v66 + 499) != -2147024362 )
            CallStackContext::TraceFailure(v66, "CMPEGFrame::DeSerializeFrameBody", 652, -2147024362);
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
      v67 = CMPEGFrame::ParseVbriIfPresent(v8, a2 + 32, (int)v6 - 32, 1);
      v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      v11 = v67;
      if ( v67 < 0 )
      {
        if ( !CallStackTracing::s_wpInstance )
        {
          v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10);
          CallStackTracing::s_wpInstance = v68;
          if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
          {
            v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v4 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v4 + 8) )
        {
          v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
          if ( *((_DWORD *)v69 + 499) != v11 )
            CallStackContext::TraceFailure(v69, "CMPEGFrame::DeSerializeFrameBody", 672, v11);
        }
        if ( !g_wppLevels )
          goto LABEL_259;
        v24 = 47;
        goto LABEL_257;
      }
    }
    v70 = *((_DWORD *)v8 + 29);
    if ( v70 >= (unsigned int)v14 )
    {
      if ( v70 > (unsigned int)v14 )
      {
        v71 = operator new(v70 - (unsigned int)v14);
        *((_QWORD *)v8 + 43) = v71;
        if ( !v71 )
        {
          v73 = (wchar_t *)CallStackTracing::s_wpInstance;
          v11 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72);
            CallStackTracing::s_wpInstance = v74;
            if ( v74 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
            {
              v73 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v73 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v73 + 8) )
          {
            v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
            if ( *((_DWORD *)v75 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v75, "CMPEGFrame::DeSerializeFrameBody", 680, -2147024882);
          }
          if ( !g_wppLevels )
            goto LABEL_259;
          v24 = 48;
          goto LABEL_257;
        }
        memcpy_0(v71, &a2[(unsigned int)v14], (unsigned int)(*((_DWORD *)v8 + 29) - v14));
      }
      *a4 = *((unsigned int *)v8 + 29);
      goto LABEL_259;
    }
    v11 = -2147418113;
    if ( !v4 )
    {
      v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, v10);
      CallStackTracing::s_wpInstance = v76;
      if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
      {
        v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v77 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v77, "CMPEGFrame::DeSerializeFrameBody", 687, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_259;
    v24 = 49;
LABEL_257:
    v79 = v11;
    goto LABEL_258;
  }
  v21 = -1072875842;
  v11 = -1072875842;
  if ( !v4 )
  {
    v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v17, v10);
    CallStackTracing::s_wpInstance = v25;
    if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
    {
      v4 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v4 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v80);
  return v11;
}

```

## disassembly

```asm
0x18004fe90  mov     [rsp+arg_10], rbx
0x18004fe95  push    rbp
0x18004fe96  push    rsi
0x18004fe97  push    rdi
0x18004fe98  push    r12
0x18004fe9a  push    r13
0x18004fe9c  push    r14
0x18004fe9e  push    r15
0x18004fea0  sub     rsp, 40h
0x18004fea4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004feab  mov     r13, r9
0x18004feae  mov     r15d, r8d
0x18004feb1  mov     r12, rdx
0x18004feb4  mov     rsi, rcx
0x18004feb7  test    rbx, rbx
0x18004feba  jnz     short loc_18004FEC8
0x18004febc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004fec1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fec8  cmp     byte ptr [rbx+8], 0
0x18004fecc  lea     r14, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x18004fed3  jz      short loc_18004FF07
0x18004fed5  mov     rcx, rbx; this
0x18004fed8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fedd  mov     ecx, [rax+7C4h]
0x18004fee3  cmp     ecx, [rax+7C8h]
0x18004fee9  jnb     short loc_18004FEFA
0x18004feeb  add     rcx, rcx
0x18004feee  mov     [rax+rcx*8], r14
0x18004fef2  mov     dword ptr [rax+rcx*8+8], 1B9h
0x18004fefa  inc     dword ptr [rax+7C4h]
0x18004ff00  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff07  mov     edx, [rsi+48h]
0x18004ff0a  test    edx, edx
0x18004ff0c  jz      loc_18004FFE3
0x18004ff12  cmp     r15d, 2
0x18004ff16  jnb     loc_18004FFBB
0x18004ff1c  mov     edi, 0C00D36BEh
0x18004ff21  mov     ebp, edi
0x18004ff23  test    rbx, rbx
0x18004ff26  jnz     short loc_18004FF6F
0x18004ff28  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ff2f  nop     dword ptr [rax+rax+00h]
0x18004ff34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff3b  mov     rcx, rax
0x18004ff3e  test    rax, rax
0x18004ff41  jz      short loc_18004FF61
0x18004ff43  mov     rax, [rax]
0x18004ff46  mov     edx, 7F0h
0x18004ff4b  mov     rax, [rax+8]
0x18004ff4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff54  test    eax, eax
0x18004ff56  jz      short loc_18004FF61
0x18004ff58  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff5f  jmp     short loc_18004FF6F
0x18004ff61  lea     rbx, qword_1801B97E0
0x18004ff68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff6f  cmp     byte ptr [rbx+8], 0
0x18004ff73  jz      short loc_18004FF99
0x18004ff75  mov     rcx, rbx; this
0x18004ff78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ff7d  cmp     [rax+7CCh], edi
0x18004ff83  jz      short loc_18004FF99
0x18004ff85  mov     r9d, edi; int
0x18004ff88  mov     r8d, 1C1h; int
0x18004ff8e  mov     rdx, r14; char *
0x18004ff91  mov     rcx, rax; this
0x18004ff94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ff99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004ffa0  jb      loc_180050EC1
0x18004ffa6  mov     edx, 1Bh
0x18004ffab  mov     [rsp+78h+var_58], edi
0x18004ffaf  lea     r8, WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids
0x18004ffb6  jmp     loc_180050EAE
0x18004ffbb  movzx   ecx, word ptr [r12]
0x18004ffc0  mov     edi, 2
0x18004ffc5  add     dword ptr [rsi+74h], 0FFFFFFFEh
0x18004ffc9  movzx   eax, cl
0x18004ffcc  mov     [rsi+70h], cx
0x18004ffd0  shl     ax, 8
0x18004ffd4  shr     cx, 8
0x18004ffd8  or      ax, cx
0x18004ffdb  mov     [rsi+70h], ax
0x18004ffdf  xor     ebp, ebp
0x18004ffe1  jmp     short loc_18004FFE7
0x18004ffe3  xor     ebp, ebp
0x18004ffe5  xor     edi, edi
0x18004ffe7  mov     eax, [rsi+88h]
0x18004ffed  lea     r14, WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids
0x18004fff4  cmp     eax, 0Ah
0x18004fff7  jz      short loc_180050018
0x18004fff9  cmp     eax, 14h
0x18004fffc  jz      short loc_180050007
0x18004fffe  cmp     eax, 19h
0x180050001  jnz     loc_180050C73
0x180050007  cmp     dword ptr [rsi+5Ch], 3
0x18005000b  mov     ecx, 11h
0x180050010  lea     eax, [rcx-8]
0x180050013  cmovz   ecx, eax
0x180050016  jmp     short loc_180050029
0x180050018  cmp     dword ptr [rsi+5Ch], 3
0x18005001c  mov     eax, 20h ; ' '
0x180050021  lea     ecx, [rax-0Fh]
0x180050024  cmovz   eax, ecx
0x180050027  mov     ecx, eax
0x180050029  test    edx, edx
0x18005002b  lea     eax, [rcx-2]
0x18005002e  cmovz   eax, ecx
0x180050031  lea     ebp, [rax+4]
0x180050034  add     ebp, edi
0x180050036  cmp     ebp, edi
0x180050038  jnb     loc_1800500DA
0x18005003e  mov     edi, 80070216h
0x180050043  mov     ebp, edi
0x180050045  test    rbx, rbx
0x180050048  jnz     short loc_180050091
0x18005004a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050051  nop     dword ptr [rax+rax+00h]
0x180050056  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005005d  mov     rcx, rax
0x180050060  test    rax, rax
0x180050063  jz      short loc_180050083
0x180050065  mov     rax, [rax]
0x180050068  mov     edx, 7F0h
0x18005006d  mov     rax, [rax+8]
0x180050071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050076  test    eax, eax
0x180050078  jz      short loc_180050083
0x18005007a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050081  jmp     short loc_180050091
0x180050083  lea     rbx, qword_1801B97E0
0x18005008a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050091  cmp     byte ptr [rbx+8], 0
0x180050095  jz      short loc_1800500BF
0x180050097  mov     rcx, rbx; this
0x18005009a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005009f  cmp     [rax+7CCh], edi
0x1800500a5  jz      short loc_1800500BF
0x1800500a7  mov     r9d, edi; int
0x1800500aa  lea     rdx, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x1800500b1  mov     r8d, 203h; int
0x1800500b7  mov     rcx, rax; this
0x1800500ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800500bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800500c6  jb      loc_180050EC1
0x1800500cc  mov     edx, 1Ch
0x1800500d1  mov     [rsp+78h+var_58], edi
0x1800500d5  jmp     loc_180050EAB
0x1800500da  cmp     r15d, ebp
0x1800500dd  jnb     loc_18005017B
0x1800500e3  mov     edi, 0C00D36BEh
0x1800500e8  mov     ebp, edi
0x1800500ea  test    rbx, rbx
0x1800500ed  jnz     short loc_180050136
0x1800500ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800500f6  nop     dword ptr [rax+rax+00h]
0x1800500fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050102  mov     rcx, rax
0x180050105  test    rax, rax
0x180050108  jz      short loc_180050128
0x18005010a  mov     rax, [rax]
0x18005010d  mov     edx, 7F0h
0x180050112  mov     rax, [rax+8]
0x180050116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005011b  test    eax, eax
0x18005011d  jz      short loc_180050128
0x18005011f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050126  jmp     short loc_180050136
0x180050128  lea     rbx, qword_1801B97E0
0x18005012f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050136  cmp     byte ptr [rbx+8], 0
0x18005013a  jz      short loc_180050164
0x18005013c  mov     rcx, rbx; this
0x18005013f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050144  cmp     [rax+7CCh], edi
0x18005014a  jz      short loc_180050164
0x18005014c  mov     r9d, edi; int
0x18005014f  lea     rdx, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x180050156  mov     r8d, 206h; int
0x18005015c  mov     rcx, rax; this
0x18005015f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050164  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005016b  jb      loc_180050EC1
0x180050171  mov     edx, 1Dh
0x180050176  jmp     loc_1800500D1
0x18005017b  mov     ecx, edi
0x18005017d  lea     rdx, aInfoxingvbri+4; Buf2
0x180050184  add     rax, r12
0x180050187  mov     r8d, 4; Size
0x18005018d  mov     ecx, [rcx+rax]
0x180050190  mov     [rsp+78h+Buf1], ecx
0x180050194  lea     rcx, [rsp+78h+Buf1]; Buf1
0x180050199  call    memcmp_0
0x18005019e  test    eax, eax
0x1800501a0  jz      loc_180050269
0x1800501a6  mov     r8d, 4; Size
0x1800501ac  lea     rdx, aInfoxingvbri; "InfoXingVBRI"
0x1800501b3  lea     rcx, [rsp+78h+Buf1]; Buf1
0x1800501b8  call    memcmp_0
0x1800501bd  test    eax, eax
0x1800501bf  jnz     loc_180050AA2
0x1800501c5  add     edi, 74h ; 't'
0x1800501c8  cmp     r15d, edi
0x1800501cb  jnb     loc_180050AA2
0x1800501d1  mov     edi, 0C00D36BEh
0x1800501d6  mov     ebp, edi
0x1800501d8  test    rbx, rbx
0x1800501db  jnz     short loc_180050224
0x1800501dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800501e4  nop     dword ptr [rax+rax+00h]
0x1800501e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800501f0  mov     rcx, rax
0x1800501f3  test    rax, rax
0x1800501f6  jz      short loc_180050216
0x1800501f8  mov     rax, [rax]
0x1800501fb  mov     edx, 7F0h
0x180050200  mov     rax, [rax+8]
0x180050204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050209  test    eax, eax
0x18005020b  jz      short loc_180050216
0x18005020d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050214  jmp     short loc_180050224
0x180050216  lea     rbx, qword_1801B97E0
0x18005021d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050224  cmp     byte ptr [rbx+8], 0
0x180050228  jz      short loc_180050252
0x18005022a  mov     rcx, rbx; this
0x18005022d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050232  cmp     [rax+7CCh], edi
0x180050238  jz      short loc_180050252
0x18005023a  mov     r9d, edi; int
0x18005023d  lea     rdx, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x180050244  mov     r8d, 270h; int
0x18005024a  mov     rcx, rax; this
0x18005024d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050252  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050259  jb      loc_180050EC1
0x18005025f  mov     edx, 2Bh ; '+'
0x180050264  jmp     loc_1800500D1
0x180050269  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180050270  jb      short loc_180050291
0x180050272  mov     rcx, cs:WPP_GLOBAL_Control
0x180050279  mov     edx, 1Eh
0x18005027e  mov     r8, r14
0x180050281  mov     rcx, [rcx+10h]
0x180050285  call    WPP_SF_
0x18005028a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050291  lea     edi, [rbp+4]
0x180050294  cmp     edi, ebp
0x180050296  jnb     loc_180050334
0x18005029c  mov     edi, 80070216h
0x1800502a1  mov     ebp, edi
0x1800502a3  test    rbx, rbx
0x1800502a6  jnz     short loc_1800502EF
0x1800502a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800502af  nop     dword ptr [rax+rax+00h]
0x1800502b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800502bb  mov     rcx, rax
0x1800502be  test    rax, rax
0x1800502c1  jz      short loc_1800502E1
0x1800502c3  mov     rax, [rax]
0x1800502c6  mov     edx, 7F0h
0x1800502cb  mov     rax, [rax+8]
0x1800502cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502d4  test    eax, eax
0x1800502d6  jz      short loc_1800502E1
0x1800502d8  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800502df  jmp     short loc_1800502EF
0x1800502e1  lea     rbx, qword_1801B97E0
0x1800502e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800502ef  cmp     byte ptr [rbx+8], 0
0x1800502f3  jz      short loc_18005031D
0x1800502f5  mov     rcx, rbx; this
0x1800502f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800502fd  cmp     [rax+7CCh], edi
0x180050303  jz      short loc_18005031D
0x180050305  mov     r9d, edi; int
0x180050308  lea     rdx, aCmpegframeDese_0; "CMPEGFrame::DeSerializeFrameBody"
0x18005030f  mov     r8d, 222h; int
0x180050315  mov     rcx, rax; this
0x180050318  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005031d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050324  jb      loc_180050EC1
0x18005032a  mov     edx, 1Fh
0x18005032f  jmp     loc_1800500D1
0x180050334  cmp     r15d, edi
0x180050337  jnb     loc_1800503D5
0x18005033d  mov     edi, 0C00D36BEh
0x180050342  mov     ebp, edi
0x180050344  test    rbx, rbx
0x180050347  jnz     short loc_180050390
0x180050349  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050350  nop     dword ptr [rax+rax+00h]
0x180050355  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005035c  mov     rcx, rax
0x18005035f  test    rax, rax
0x180050362  jz      short loc_180050382
0x180050364  mov     rax, [rax]
0x180050367  mov     edx, 7F0h
0x18005036c  mov     rax, [rax+8]
0x180050370  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
