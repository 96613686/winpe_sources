# CMRFDeinterlace::AddFrame(uchar *,int,int,unsigned __int64)

- ea: `0x180047348`
- end: `0x1800480f4`
- name: `?AddFrame@CMRFDeinterlace@@QEAAJPEAEHH_K@Z`
- size: `3500`
- prototype: `__int64 __fastcall(CMRFDeinterlace *__hidden this, unsigned __int8 *, int, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x18002a38c`

## callees

- `0x18000a954`
- `0x18000ec20`
- `0x18003ac24`
- `0x1800432c0`
- `0x180047348`
- `0x180059ad0`
- `0x180059c88`
- `0x180059cfc`
- `0x18009e364`
- `0x18009e528`
- `0x18009e5a4`
- `0x18009ebb4`
- `0x18009f254`
- `0x18009f644`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004739d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047439`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800474d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004757e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047617`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800476b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800477d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800478ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004796c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047a0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047b05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047bcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047d05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047e31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047eb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047f3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047fc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004806e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004739d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047439`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800474d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004757e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047617`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800476b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800477d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800478ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004796c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047a0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047b05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047bcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047d05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047e31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047eb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047f3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047fc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004806e`

## string_xrefs

- `0x180047887`: `Invalid input image size for FOURCC_YV12 while copying the V and U channels`

## pseudocode

```c
__int64 __fastcall CMRFDeinterlace::AddFrame(
        CMRFDeinterlace *this,
        unsigned __int8 *a2,
        int a3,
        int a4,
        unsigned __int64 a5)
{
  __int64 v5; // r14
  errno_t v9; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v13; // r8d
  int v14; // r9d
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rsi
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  __int64 v22; // rbp
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  __int64 v25; // r12
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  unsigned __int64 v28; // rcx
  __int64 v29; // rsi
  rsize_t v30; // r10
  int v31; // r13d
  int i; // ebp
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  int v38; // eax
  unsigned __int64 v39; // r14
  rsize_t v40; // r15
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  unsigned __int64 v45; // rcx
  __int64 v46; // r12
  char *v47; // rbp
  char *v48; // r14
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  int v51; // r15d
  __int64 v52; // rdx
  int v53; // eax
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  unsigned int k; // r8d
  unsigned int v57; // ecx
  _BYTE *v58; // rdx
  _BYTE *v59; // r9
  int v60; // r15d
  __int64 v61; // rdx
  unsigned int v62; // eax
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  unsigned int j; // r10d
  unsigned int v66; // ecx
  _BYTE *v67; // r9
  unsigned __int8 *v68; // r8
  unsigned __int8 *v69; // r11
  __int64 v70; // rcx
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  __int64 v73; // rcx
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  __int64 v76; // rcx
  __int64 *v77; // rcx
  CallStackTracing *v78; // rax
  __int64 *v79; // rcx
  CallStackTracing *v80; // rax
  int v81; // ecx
  __int64 *v82; // rcx
  CallStackTracing *v83; // rax
  __int64 v85; // [rsp+20h] [rbp-48h]
  rsize_t v86; // [rsp+70h] [rbp+8h]

  v5 = a4;
  v9 = 0;
  if ( !*(_BYTE *)this )
  {
    v9 = XvpOriginateError<39>("CMRFDeinterlace::AddFrame");
    if ( v9 < 0 )
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( !*((_BYTE *)v10 + 8) )
        return (unsigned int)v9;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v9 )
        return (unsigned int)v9;
      v13 = 262;
LABEL_11:
      v14 = v9;
      goto LABEL_221;
    }
  }
  if ( !a2 )
  {
    v9 = XvpOriginateError<29>("CMRFDeinterlace::AddFrame", 2147500035LL, L"Frame buffer is invalid/null");
    if ( v9 < 0 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( !*((_BYTE *)v15 + 8) )
        return (unsigned int)v9;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v9 )
        return (unsigned int)v9;
      v13 = 268;
      goto LABEL_11;
    }
  }
  if ( *((_DWORD *)this + 7) != a3 || *((_DWORD *)this + 8) != (_DWORD)v5 )
  {
    v9 = XvpOriginateError<20>("CMRFDeinterlace::AddFrame", 2147942487LL, L"Invalid buffer size");
    if ( v9 < 0 )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( !*((_BYTE *)v17 + 8) )
        return (unsigned int)v9;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v9 )
        return (unsigned int)v9;
      v13 = 274;
      goto LABEL_11;
    }
  }
  v19 = *((_DWORD *)this + 9) % 5u;
  if ( (unsigned int)v19 >= 5 )
  {
    v9 = XvpOriginateError<30>("CMRFDeinterlace::AddFrame", 2147549183LL, L"uiFrameIn >=FRAME_BUFFER_SIZE");
    if ( v9 < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( !*((_BYTE *)v20 + 8) )
        return (unsigned int)v9;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v9 )
        return (unsigned int)v9;
      v13 = 283;
      goto LABEL_11;
    }
  }
  v22 = (unsigned int)(2 * v19);
  if ( (unsigned int)v22 >= 0xA )
  {
    v9 = XvpOriginateError<31>("CMRFDeinterlace::AddFrame", 2147549183LL, L"uiFieldIn0 >=FRAME_BUFFER_SIZE");
    if ( v9 < 0 )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( !*((_BYTE *)v23 + 8) )
        return (unsigned int)v9;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v9 )
        return (unsigned int)v9;
      v13 = 288;
      goto LABEL_11;
    }
  }
  v25 = (unsigned int)(v22 + 1);
  if ( (unsigned int)v25 >= 0xA )
  {
    v9 = XvpOriginateError<31>("CMRFDeinterlace::AddFrame", 2147549183LL, L"uiFieldIn1 >=FRAME_BUFFER_SIZE");
    if ( v9 < 0 )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( !*((_BYTE *)v26 + 8) )
        return (unsigned int)v9;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v9 )
        return (unsigned int)v9;
      v14 = v9;
      v13 = 293;
      goto LABEL_221;
    }
  }
  *((_BYTE *)this + v22 + 932) = 0;
  *((_BYTE *)this + v25 + 932) = 0;
  v28 = (unsigned int)(*((_DWORD *)this + 5) * a3);
  v29 = 32 * v19;
  v85 = (unsigned int)v22;
  v30 = *(int *)((char *)this + v29 + 64);
  v86 = v30;
  if ( v30 < v28
    || (v31 = *(_DWORD *)((char *)this + v29 + 56), (_DWORD)v5 != v31)
    || a5 < v28
    || !*(_DWORD *)((char *)this + v29 + 72) )
  {
    v82 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v83 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v83;
      if ( v83 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v83 + 8LL))(v83, 2032) )
      {
        v82 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v82 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( !*((_BYTE *)v82 + 8) )
      return (unsigned int)v9;
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v82);
    if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147418113 )
      return (unsigned int)v9;
    v14 = -2147418113;
    v13 = 310;
LABEL_221:
    CallStackContext::TraceFailure(ThreadRelativeContext, "CMRFDeinterlace::AddFrame", v13, v14);
    return (unsigned int)v9;
  }
  for ( i = 0; i < (int)v5; ++i )
  {
    v9 = memcpy_s(
           (void *const)(*(_QWORD *)((char *)this + v29 + 48) + *(_DWORD *)((char *)this + v29 + 64) * i),
           v30,
           &a2[a5 * i],
           (unsigned int)(*((_DWORD *)this + 5) * a3));
    if ( v9 < 0 )
    {
      v33 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        {
          v14 = v9;
          v13 = 317;
          goto LABEL_221;
        }
      }
      return (unsigned int)v9;
    }
    v30 = v86;
  }
  if ( *((_DWORD *)this + 4) == 842094169 )
  {
    v35 = (unsigned int)(a3 >> 31);
    LODWORD(v35) = a3 % 2;
    if ( a3 / 2 != *(_DWORD *)((char *)this + v29 + 220)
      || a3 / 2 != *(_DWORD *)((char *)this + v29 + 380)
      || (v35 = (unsigned int)((int)v5 >> 31),
          LODWORD(v35) = (int)v5 % 2,
          (int)v5 / 2 != *(_DWORD *)((char *)this + v29 + 216))
      || (int)v5 / 2 != *(_DWORD *)((char *)this + v29 + 376) )
    {
      v9 = XvpOriginateError<76>(
             "CMRFDeinterlace::AddFrame",
             v35,
             L"Invalid input image size for FOURCC_YV12 while copying the V and U channels");
      if ( v9 < 0 )
      {
        v36 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          {
            v14 = v9;
            v13 = 330;
            goto LABEL_221;
          }
        }
        return (unsigned int)v9;
      }
    }
    v38 = v5;
    v39 = a5 * v5;
    v40 = a3 / 2 * (v38 / 2);
    v9 = memcpy_s(
           *(void *const *)((char *)this + v29 + 368),
           (unsigned int)(*(_DWORD *)((char *)this + v29 + 376) * *(_DWORD *)((char *)this + v29 + 380)),
           &a2[v39],
           v40);
    if ( v9 < 0 )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        {
          v14 = v9;
          v13 = 335;
          goto LABEL_221;
        }
      }
      return (unsigned int)v9;
    }
    v9 = memcpy_s(
           *(void *const *)((char *)this + v29 + 208),
           (unsigned int)(*(_DWORD *)((char *)this + v29 + 216) * *(_DWORD *)((char *)this + v29 + 220)),
           &a2[v39 + v40],
           v40);
    if ( v9 < 0 )
    {
      v43 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v43 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        {
          v14 = v9;
          v13 = 338;
          goto LABEL_221;
        }
      }
      return (unsigned int)v9;
    }
    v30 = v86;
  }
  v45 = *((unsigned int *)this + 4);
  v46 = 32 * v25;
  v47 = (char *)this + 32 * v85 + 528;
  v48 = (char *)this + v46 + 528;
  if ( (unsigned int)(v45 - 20) <= 2 )
  {
    v60 = *((_DWORD *)v47 + 3);
    v61 = (unsigned int)((v31 - 1) >> 31);
    if ( (v31 - 1) / 2 >= *((_DWORD *)v47 + 2)
      || (v62 = *((_DWORD *)this + 5), v62 < 3)
      || v60 * v62 > v30
      || v60 != *((_DWORD *)v48 + 3)
      || !*((_DWORD *)v47 + 6)
      || !*((_DWORD *)v48 + 6) )
    {
      LODWORD(v61) = (v31 - 1) % 2;
      v9 = XvpOriginateError<19>("CMRFDeinterlace::AddFrame", v61, L"Invalid Image size");
      if ( v9 < 0 )
      {
        v63 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          {
            v63 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v63 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          {
            v14 = v9;
            v13 = 360;
            goto LABEL_221;
          }
        }
        return (unsigned int)v9;
      }
    }
    for ( j = 0; (int)j < v31; ++j )
    {
      v66 = j >> 1;
      if ( (j & 1) == *((_DWORD *)this + 1) )
      {
        v45 = *((_DWORD *)v47 + 4) * v66;
        v67 = (_BYTE *)(*(_QWORD *)v47 + (int)v45);
      }
      else
      {
        v45 = *((_DWORD *)v48 + 4) * v66;
        v67 = (_BYTE *)(*(_QWORD *)v48 + (int)v45);
      }
      v68 = (unsigned __int8 *)(*(_QWORD *)((char *)this + v29 + 48) + (int)(*(_DWORD *)((char *)this + v29 + 64) * j));
      v69 = &v68[*((_DWORD *)this + 5) * v60];
      while ( v68 < v69 )
      {
        v45 = 66 * (unsigned int)v68[2];
        *v67 = ((unsigned __int16)(66 * v68[2] + 129 * v68[1] + 25 * *v68 + 128) >> 8) + 16;
        v68 += *((unsigned int *)this + 5);
        ++v67;
      }
    }
  }
  else if ( (_DWORD)v45 == 844715353
         || (_DWORD)v45 == 842094169
         || (_DWORD)v45 == 842094158
         || (_DWORD)v45 == 1448433985 )
  {
    v51 = *((_DWORD *)v47 + 3);
    v52 = (unsigned int)((v31 - 1) >> 31);
    if ( (v31 - 1) / 2 >= *((_DWORD *)v47 + 2)
      || (v53 = *((_DWORD *)this + 5)) == 0
      || (unsigned int)(v51 * v53) > v30
      || v51 != *((_DWORD *)v48 + 3)
      || !*((_DWORD *)v47 + 6)
      || !*((_DWORD *)v48 + 6) )
    {
      LODWORD(v52) = (v31 - 1) % 2;
      v9 = XvpOriginateError<19>("CMRFDeinterlace::AddFrame", v52, L"Invalid Image size");
      if ( v9 < 0 )
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          {
            v14 = v9;
            v13 = 401;
            goto LABEL_221;
          }
        }
        return (unsigned int)v9;
      }
    }
    for ( k = 0; (int)k < v31; ++k )
    {
      v57 = k >> 1;
      if ( (k & 1) == *((_DWORD *)this + 1) )
        v58 = (_BYTE *)(*(_QWORD *)v47 + (int)(*((_DWORD *)v47 + 4) * v57));
      else
        v58 = (_BYTE *)(*(_QWORD *)v48 + (int)(*((_DWORD *)v48 + 4) * v57));
      v45 = *(_QWORD *)((char *)this + v29 + 48) + (int)(*(_DWORD *)((char *)this + v29 + 64) * k);
      v59 = (_BYTE *)(v45 + (unsigned int)(*((_DWORD *)this + 5) * v51));
      while ( v45 < (unsigned __int64)v59 )
      {
        *v58 = *(_BYTE *)v45;
        v45 += *((unsigned int *)this + 5);
        ++v58;
      }
    }
  }
  else
  {
    v9 = XvpOriginateError<37>("CMRFDeinterlace::AddFrame");
    if ( v9 < 0 )
    {
      v49 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        {
          v14 = v9;
          v13 = 426;
          goto LABEL_221;
        }
      }
      return (unsigned int)v9;
    }
  }
  if ( !*((_BYTE *)this + 12) )
    goto LABEL_210;
  v9 = CMRFDeinterlace::SimpleHorizSmooth121(v45, v47, (char *)this + 888);
  if ( v9 < 0 )
  {
    v71 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v72;
      if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
      {
        v71 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v71 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v71 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
      {
        v14 = v9;
        v13 = 432;
        goto LABEL_221;
      }
    }
    return (unsigned int)v9;
  }
  v9 = CMRFDeinterlace::SimpleVertSmooth121(v70, (char *)this + 888, v47);
  if ( v9 < 0 )
  {
    v74 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v75;
      if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
      {
        v74 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v74 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v74 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
      {
        v14 = v9;
        v13 = 433;
        goto LABEL_221;
      }
    }
    return (unsigned int)v9;
  }
  v9 = CMRFDeinterlace::SimpleHorizSmooth121(v73, (char *)this + v46 + 528, (char *)this + 888);
  if ( v9 < 0 )
  {
    v77 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v78;
      if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
      {
        v77 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v77 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v77 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
      {
        v14 = v9;
        v13 = 434;
        goto LABEL_221;
      }
    }
    return (unsigned int)v9;
  }
  v9 = CMRFDeinterlace::SimpleVertSmooth121(v76, (char *)this + 888, (char *)this + v46 + 528);
  if ( v9 >= 0 )
  {
LABEL_210:
    ++*((_DWORD *)this + 9);
    v81 = *((_DWORD *)this + 10);
    if ( (unsigned int)(*((_DWORD *)this + 9) - v81) > 5 )
    {
      do
        ++v81;
      while ( (unsigned int)(*((_DWORD *)this + 9) - v81) > 5 );
      *((_DWORD *)this + 10) = v81;
    }
    return (unsigned int)v9;
  }
  v79 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v80;
    if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
    {
      v79 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v79 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v79 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
    {
      v14 = v9;
      v13 = 435;
      goto LABEL_221;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180047348  mov     [rsp+arg_10], rbx
0x18004734d  mov     [rsp+arg_8], rdx
0x180047352  push    rbp
0x180047353  push    rsi
0x180047354  push    rdi
0x180047355  push    r12
0x180047357  push    r13
0x180047359  push    r14
0x18004735b  push    r15
0x18004735d  sub     rsp, 30h
0x180047361  xor     r13d, r13d
0x180047364  movsxd  r14, r9d
0x180047367  lea     r12, aCmrfdeinterlac_5; "CMRFDeinterlace::AddFrame"
0x18004736e  mov     r15d, r8d
0x180047371  mov     rsi, rdx
0x180047374  mov     rdi, rcx
0x180047377  mov     ebx, r13d
0x18004737a  cmp     [rcx], r13b
0x18004737d  jnz     loc_18004740A
0x180047383  mov     rcx, r12
0x180047386  call    ??$XvpOriginateError@$0CH@@@YAJQEADJAEAY0CH@$$CBG@Z; XvpOriginateError<39>(char * const,long,ushort const (&)[39])
0x18004738b  mov     ebx, eax
0x18004738d  test    eax, eax
0x18004738f  jns     short loc_18004740A
0x180047391  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047398  test    rcx, rcx
0x18004739b  jnz     short loc_1800473DE
0x18004739d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800473a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800473aa  mov     rcx, rax
0x1800473ad  test    rax, rax
0x1800473b0  jz      short loc_1800473D0
0x1800473b2  mov     rax, [rax]
0x1800473b5  mov     edx, 7F0h
0x1800473ba  mov     rax, [rax+8]
0x1800473be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473c3  test    eax, eax
0x1800473c5  jz      short loc_1800473D0
0x1800473c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800473ce  jmp     short loc_1800473DE
0x1800473d0  lea     rcx, qword_180153440; this
0x1800473d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800473de  cmp     [rcx+8], r13b
0x1800473e2  jz      loc_1800480DA
0x1800473e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800473ed  cmp     [rax+7CCh], ebx
0x1800473f3  jz      loc_1800480DA
0x1800473f9  mov     r8d, 106h
0x1800473ff  mov     r9d, ebx
0x180047402  mov     rdx, r12
0x180047405  jmp     loc_1800480D2
0x18004740a  test    rsi, rsi
0x18004740d  jnz     loc_1800474A0
0x180047413  lea     r8, aFrameBufferIsI; "Frame buffer is invalid/null"
0x18004741a  mov     edx, 80004003h
0x18004741f  mov     rcx, r12
0x180047422  call    ??$XvpOriginateError@$0BN@@@YAJQEADJAEAY0BN@$$CBG@Z; XvpOriginateError<29>(char * const,long,ushort const (&)[29])
0x180047427  mov     ebx, eax
0x180047429  test    eax, eax
0x18004742b  jns     short loc_1800474A0
0x18004742d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047434  test    rcx, rcx
0x180047437  jnz     short loc_18004747A
0x180047439  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004743f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180047446  mov     rcx, rax
0x180047449  test    rax, rax
0x18004744c  jz      short loc_18004746C
0x18004744e  mov     rax, [rax]
0x180047451  mov     edx, 7F0h
0x180047456  mov     rax, [rax+8]
0x18004745a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004745f  test    eax, eax
0x180047461  jz      short loc_18004746C
0x180047463  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004746a  jmp     short loc_18004747A
0x18004746c  lea     rcx, qword_180153440; this
0x180047473  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004747a  cmp     [rcx+8], r13b
0x18004747e  jz      loc_1800480DA
0x180047484  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047489  cmp     [rax+7CCh], ebx
0x18004748f  jz      loc_1800480DA
0x180047495  mov     r8d, 10Ch
0x18004749b  jmp     loc_1800473FF
0x1800474a0  cmp     [rdi+1Ch], r15d
0x1800474a4  jnz     short loc_1800474B0
0x1800474a6  cmp     [rdi+20h], r14d
0x1800474aa  jz      loc_18004753D
0x1800474b0  lea     r8, aInvalidBufferS; "Invalid buffer size"
0x1800474b7  mov     edx, 80070057h
0x1800474bc  mov     rcx, r12
0x1800474bf  call    ??$XvpOriginateError@$0BE@@@YAJQEADJAEAY0BE@$$CBG@Z; XvpOriginateError<20>(char * const,long,ushort const (&)[20])
0x1800474c4  mov     ebx, eax
0x1800474c6  test    eax, eax
0x1800474c8  jns     short loc_18004753D
0x1800474ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800474d1  test    rcx, rcx
0x1800474d4  jnz     short loc_180047517
0x1800474d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800474dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800474e3  mov     rcx, rax
0x1800474e6  test    rax, rax
0x1800474e9  jz      short loc_180047509
0x1800474eb  mov     rax, [rax]
0x1800474ee  mov     edx, 7F0h
0x1800474f3  mov     rax, [rax+8]
0x1800474f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474fc  test    eax, eax
0x1800474fe  jz      short loc_180047509
0x180047500  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047507  jmp     short loc_180047517
0x180047509  lea     rcx, qword_180153440; this
0x180047510  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047517  cmp     [rcx+8], r13b
0x18004751b  jz      loc_1800480DA
0x180047521  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047526  cmp     [rax+7CCh], ebx
0x18004752c  jz      loc_1800480DA
0x180047532  mov     r8d, 112h
0x180047538  jmp     loc_1800473FF
0x18004753d  mov     esi, [rdi+24h]
0x180047540  mov     eax, 0CCCCCCCDh
0x180047545  mul     esi
0x180047547  shr     edx, 2
0x18004754a  lea     eax, [rdx+rdx*4]
0x18004754d  sub     esi, eax
0x18004754f  cmp     esi, 5
0x180047552  jb      loc_1800475E5
0x180047558  lea     r8, aUiframeinFrame; "uiFrameIn >=FRAME_BUFFER_SIZE"
0x18004755f  mov     edx, 8000FFFFh
0x180047564  mov     rcx, r12
0x180047567  call    ??$XvpOriginateError@$0BO@@@YAJQEADJAEAY0BO@$$CBG@Z; XvpOriginateError<30>(char * const,long,ushort const (&)[30])
0x18004756c  mov     ebx, eax
0x18004756e  test    eax, eax
0x180047570  jns     short loc_1800475E5
0x180047572  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047579  test    rcx, rcx
0x18004757c  jnz     short loc_1800475BF
0x18004757e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047584  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004758b  mov     rcx, rax
0x18004758e  test    rax, rax
0x180047591  jz      short loc_1800475B1
0x180047593  mov     rax, [rax]
0x180047596  mov     edx, 7F0h
0x18004759b  mov     rax, [rax+8]
0x18004759f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475a4  test    eax, eax
0x1800475a6  jz      short loc_1800475B1
0x1800475a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800475af  jmp     short loc_1800475BF
0x1800475b1  lea     rcx, qword_180153440; this
0x1800475b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800475bf  cmp     [rcx+8], r13b
0x1800475c3  jz      loc_1800480DA
0x1800475c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800475ce  cmp     [rax+7CCh], ebx
0x1800475d4  jz      loc_1800480DA
0x1800475da  mov     r8d, 11Bh
0x1800475e0  jmp     loc_1800473FF
0x1800475e5  lea     ebp, [rsi+rsi]
0x1800475e8  cmp     ebp, 0Ah
0x1800475eb  jb      loc_18004767E
0x1800475f1  lea     r8, aUifieldin0Fram; "uiFieldIn0 >=FRAME_BUFFER_SIZE"
0x1800475f8  mov     edx, 8000FFFFh
0x1800475fd  mov     rcx, r12
0x180047600  call    ??$XvpOriginateError@$0BP@@@YAJQEADJAEAY0BP@$$CBG@Z; XvpOriginateError<31>(char * const,long,ushort const (&)[31])
0x180047605  mov     ebx, eax
0x180047607  test    eax, eax
0x180047609  jns     short loc_18004767E
0x18004760b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047612  test    rcx, rcx
0x180047615  jnz     short loc_180047658
0x180047617  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004761d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180047624  mov     rcx, rax
0x180047627  test    rax, rax
0x18004762a  jz      short loc_18004764A
0x18004762c  mov     rax, [rax]
0x18004762f  mov     edx, 7F0h
0x180047634  mov     rax, [rax+8]
0x180047638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004763d  test    eax, eax
0x18004763f  jz      short loc_18004764A
0x180047641  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047648  jmp     short loc_180047658
0x18004764a  lea     rcx, qword_180153440; this
0x180047651  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047658  cmp     [rcx+8], r13b
0x18004765c  jz      loc_1800480DA
0x180047662  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047667  cmp     [rax+7CCh], ebx
0x18004766d  jz      loc_1800480DA
0x180047673  mov     r8d, 120h
0x180047679  jmp     loc_1800473FF
0x18004767e  lea     r12d, [rbp+1]
0x180047682  cmp     r12d, 0Ah
0x180047686  jb      loc_180047720
0x18004768c  lea     r8, aUifieldin1Fram; "uiFieldIn1 >=FRAME_BUFFER_SIZE"
0x180047693  mov     edx, 8000FFFFh
0x180047698  lea     rcx, aCmrfdeinterlac_5; "CMRFDeinterlace::AddFrame"
0x18004769f  call    ??$XvpOriginateError@$0BP@@@YAJQEADJAEAY0BP@$$CBG@Z; XvpOriginateError<31>(char * const,long,ushort const (&)[31])
0x1800476a4  mov     ebx, eax
0x1800476a6  test    eax, eax
0x1800476a8  jns     short loc_180047720
0x1800476aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800476b1  test    rcx, rcx
0x1800476b4  jnz     short loc_1800476F7
0x1800476b6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800476bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800476c3  mov     rcx, rax
0x1800476c6  test    rax, rax
0x1800476c9  jz      short loc_1800476E9
0x1800476cb  mov     rax, [rax]
0x1800476ce  mov     edx, 7F0h
0x1800476d3  mov     rax, [rax+8]
0x1800476d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476dc  test    eax, eax
0x1800476de  jz      short loc_1800476E9
0x1800476e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800476e7  jmp     short loc_1800476F7
0x1800476e9  lea     rcx, qword_180153440; this
0x1800476f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800476f7  cmp     [rcx+8], r13b
0x1800476fb  jz      loc_1800480DA
0x180047701  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047706  cmp     [rax+7CCh], ebx
0x18004770c  jz      loc_1800480DA
0x180047712  mov     r9d, ebx
0x180047715  mov     r8d, 125h
0x18004771b  jmp     loc_1800480CB
0x180047720  mov     [rbp+rdi+3A4h], r13b
0x180047728  mov     ecx, r15d
0x18004772b  mov     [r12+rdi+3A4h], r13b
0x180047733  imul    ecx, [rdi+14h]
0x180047737  shl     rsi, 5
0x18004773b  mov     eax, ebp
0x18004773d  mov     [rsp+68h+var_48], rax
0x180047742  movsxd  r10, dword ptr [rsi+rdi+40h]
0x180047747  mov     [rsp+68h+arg_0], r10
0x18004774c  cmp     r10, rcx
0x18004774f  jb      loc_18004805B
0x180047755  mov     r13d, [rsi+rdi+38h]
0x18004775a  cmp     r14d, r13d
0x18004775d  jnz     loc_180048058
0x180047763  cmp     [rsp+68h+arg_20], rcx
0x18004776b  jb      loc_180048058
0x180047771  cmp     dword ptr [rsi+rdi+48h], 0
0x180047776  jz      loc_180048058
0x18004777c  xor     ebp, ebp
0x18004777e  cmp     ebp, r14d
0x180047781  jge     loc_18004783C
0x180047787  mov     eax, ebp
0x180047789  movsxd  r8, ebp
0x18004778c  imul    r8, [rsp+68h+arg_20]
0x180047795  imul    eax, [rsi+rdi+40h]
0x18004779a  mov     r9d, r15d
0x18004779d  mov     rdx, r10; DestinationSize
0x1800477a0  imul    r9d, [rdi+14h]; SourceSize
0x1800477a5  add     r8, [rsp+68h+arg_8]; Source
0x1800477aa  movsxd  rcx, eax
0x1800477ad  add     rcx, [rsi+rdi+30h]; Destination
0x1800477b2  call    memcpy_s
0x1800477b7  mov     ebx, eax
0x1800477b9  test    eax, eax
0x1800477bb  js      short loc_1800477C6
0x1800477bd  mov     r10, [rsp+68h+arg_0]
0x1800477c2  inc     ebp
0x1800477c4  jmp     short loc_18004777E
0x1800477c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800477cd  test    rcx, rcx
0x1800477d0  jnz     short loc_180047813
0x1800477d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800477d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800477df  mov     rcx, rax
0x1800477e2  test    rax, rax
0x1800477e5  jz      short loc_180047805
0x1800477e7  mov     rax, [rax]
0x1800477ea  mov     edx, 7F0h
0x1800477ef  mov     rax, [rax+8]
0x1800477f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477f8  test    eax, eax
0x1800477fa  jz      short loc_180047805
0x1800477fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047803  jmp     short loc_180047813
0x180047805  lea     rcx, qword_180153440; this
0x18004780c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047813  cmp     byte ptr [rcx+8], 0
0x180047817  jz      loc_1800480DA
0x18004781d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047822  cmp     [rax+7CCh], ebx
0x180047828  jz      loc_1800480DA
0x18004782e  mov     r9d, ebx
0x180047831  mov     r8d, 13Dh
0x180047837  jmp     loc_1800480CB
0x18004783c  cmp     dword ptr [rdi+10h], 32315659h
0x180047843  mov     r8d, 2
0x180047849  jnz     loc_180047A83
0x18004784f  mov     eax, r15d
  ... truncated ...
```
