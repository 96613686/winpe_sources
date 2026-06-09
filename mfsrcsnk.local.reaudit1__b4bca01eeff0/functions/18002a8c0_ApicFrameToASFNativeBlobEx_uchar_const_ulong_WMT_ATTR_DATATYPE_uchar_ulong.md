# ApicFrameToASFNativeBlobEx(uchar const *,ulong,WMT_ATTR_DATATYPE *,uchar *,ulong *)

- ea: `0x18002a8c0`
- end: `0x18002b6c5`
- name: `?ApicFrameToASFNativeBlobEx@@YAJPEBEKPEAW4WMT_ATTR_DATATYPE@@PEAEPEAK@Z`
- size: `3589`
- prototype: `__int64 __fastcall(CallStackTracing *, __int64, enum WMT_ATTR_DATATYPE *, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180027d10`
- `0x180029610`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18002a8c0`
- `0x180077708`
- `0x180079680`
- `0x180111960`
- `0x18016a1c4`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ab45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ab45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b134`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002aca5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002ad69`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002ae6a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002af83`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002aca5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002ad69`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002ae6a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002af83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab94`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a937`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ab2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a937`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ab2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002abba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b1b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b1f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b22c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b26b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b2b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002abba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b1b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b1f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b22c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b26b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b2b0`

## pseudocode

```c
__int64 __fastcall ApicFrameToASFNativeBlobEx(
        CallStackTracing *a1,
        __int64 a2,
        enum WMT_ATTR_DATATYPE *a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  enum WMT_ATTR_DATATYPE *v5; // rdi
  unsigned int v6; // r14d
  const unsigned __int8 *v7; // r15
  CallStackTracing *v8; // rbx
  char *v9; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // r14d
  __int64 v15; // rdx
  unsigned int v16; // esi
  __int64 v17; // rdx
  __int64 v18; // rcx
  _BYTE *v19; // rcx
  int v20; // ebx
  int v21; // edx
  CallStackTracing *v22; // rbx
  GUID *v23; // rdi
  DWORD v24; // esi
  GUID *v25; // rax
  int v26; // eax
  int v27; // eax
  CallStackTracing *v29; // rax
  __int64 v30; // r8
  int v31; // edx
  int v32; // edi
  unsigned int v33; // r14d
  const unsigned __int8 *v34; // rbp
  const unsigned __int8 *v35; // rcx
  int v36; // eax
  unsigned int v37; // r12d
  __int64 v38; // rcx
  unsigned __int64 v39; // rdx
  int v40; // r8d
  const unsigned __int8 *v41; // rax
  unsigned int v42; // r14d
  int cchWideChar; // r13d
  int v44; // r15d
  unsigned int v45; // ebp
  WCHAR *lpWideCharStr; // r12
  int v47; // eax
  const CHAR *v48; // r13
  unsigned __int64 v49; // rbx
  int v50; // edx
  int v51; // edi
  int v52; // eax
  CallStackTracing *v53; // rcx
  __int64 v54; // rax
  CallStackTracing *v55; // rcx
  __int64 v56; // rax
  CallStackTracing *v57; // rax
  CallStackTracing *v58; // rax
  CallStackTracing *v59; // rax
  CallStackTracing *v60; // rax
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  struct CallStackContext *v63; // rax
  struct CallStackContext *v64; // rax
  struct CallStackContext *v65; // rax
  struct CallStackContext *v66; // rax
  struct CallStackContext *v67; // rax
  struct CallStackContext *v68; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v70; // rdx
  unsigned __int8 v71; // [rsp+30h] [rbp-68h]
  const CHAR *Src; // [rsp+38h] [rbp-60h]
  const CHAR *lpMultiByteStr; // [rsp+40h] [rbp-58h]
  const unsigned __int8 *v74; // [rsp+A0h] [rbp+8h]
  const unsigned __int8 *v75; // [rsp+A0h] [rbp+8h]
  unsigned int Size; // [rsp+A8h] [rbp+10h]
  unsigned int Sizea; // [rsp+A8h] [rbp+10h]

  v74 = (const unsigned __int8 *)a1;
  v5 = a3;
  v6 = a2;
  v7 = (const unsigned __int8 *)a1;
  if ( !CallStackTracing::s_wpInstance )
  {
    v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2);
    CallStackTracing::s_wpInstance = v29;
    a1 = v29;
    if ( !v29 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
  }
  v8 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v9 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v8 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v53 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v53 = CallStackTracing::s_wpInstance;
      }
      v54 = (**(__int64 (__fastcall ***)(CallStackTracing *))v53)(v53);
      if ( v54 )
        v9 = (char *)v54;
    }
    SetLastError(LastError);
    v12 = *((unsigned int *)v9 + 497);
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[8 * v13] = "ApicFrameToASFNativeBlobEx";
      *(_DWORD *)&v9[8 * v13 + 8] = 1575;
    }
    ++*((_DWORD *)v9 + 497);
    v5 = a3;
  }
  if ( !v7 || !v5 || !a5 )
  {
    v14 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "ApicFrameToASFNativeBlobEx", 1602, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v15 = 41;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_9186553898a13577d84523ff6f078a03_Traceguids, 0, v14);
    goto LABEL_39;
  }
  if ( !v6 )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2);
      CallStackTracing::s_wpInstance = v57;
      if ( !v57 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v62 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v62 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v62, "ApicFrameToASFNativeBlobEx", 1610, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v15 = 42;
    goto LABEL_14;
  }
  v16 = *v7;
  v17 = 0;
  v18 = *v7;
  if ( *v7 )
  {
    v18 = (unsigned int)(v18 - 1);
    if ( !(_DWORD)v18 || (v18 = (unsigned int)(v18 - 1), !(_DWORD)v18) )
    {
      v17 = 2;
      goto LABEL_22;
    }
    if ( (_DWORD)v18 != 1 )
      goto LABEL_22;
  }
  v17 = 1;
LABEL_22:
  if ( (int)v17 + 3 > v6 )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v17);
      CallStackTracing::s_wpInstance = v58;
      if ( !v58 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v63 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v63 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v63, "ApicFrameToASFNativeBlobEx", 1618, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v15 = 43;
    goto LABEL_14;
  }
  if ( v16 >= 4 )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v17);
      CallStackTracing::s_wpInstance = v59;
      if ( !v59 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v64 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v64 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v64, "ApicFrameToASFNativeBlobEx", 1624, -1072873844);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        WPP_9186553898a13577d84523ff6f078a03_Traceguids,
        0,
        -1072873844);
    v14 = -1072873844;
    goto LABEL_39;
  }
  lpMultiByteStr = (const CHAR *)(v7 + 1);
  v19 = v7 + 1;
  v20 = 0;
  if ( v6 != 1 )
  {
    while ( 1 )
    {
      if ( v20 >= (int)(v6 - 2) )
      {
LABEL_29:
        ++v20;
        goto LABEL_30;
      }
      if ( *v19 > 0x7Fu )
        break;
      if ( !*v19 )
        goto LABEL_29;
      ++v20;
      ++v19;
    }
    v20 = 0;
  }
LABEL_30:
  v21 = 0;
  if ( !*v7 )
    goto LABEL_204;
  if ( v16 == 1 || v16 == 2 )
  {
    v21 = 2;
    goto LABEL_34;
  }
  if ( v16 == 3 )
LABEL_204:
    v21 = 1;
LABEL_34:
  if ( v6 - 1 < v20 + v21 + 1 )
    goto LABEL_35;
  v30 = (unsigned int)(v20 + 1);
  if ( (unsigned int)v30 < v20 )
    goto LABEL_35;
  v31 = 0;
  if ( *v7 )
  {
    if ( v16 == 1 || v16 == 2 )
    {
      v31 = 2;
      goto LABEL_53;
    }
    if ( v16 != 3 )
      goto LABEL_53;
  }
  v31 = 1;
LABEL_53:
  if ( v20 + v31 + 1 < (unsigned int)v30 )
  {
LABEL_35:
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v68 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v68 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v68, "ApicFrameToASFNativeBlobEx", 1643, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v15 = 45;
    goto LABEL_14;
  }
  v32 = 0;
  v33 = v6 - (v20 + 2);
  v34 = &v7[v20 + 2];
  Size = v33;
  Src = (const CHAR *)v34;
  v35 = v34;
  if ( (_BYTE)v16 )
  {
    if ( (unsigned __int8)(v16 - 1) <= 1u && v33 >= 2 )
    {
      if ( (int)(v33 - 2) > 0 )
      {
        do
        {
          if ( !*(_WORD *)v35 )
            break;
          v32 += 2;
          v35 += 2;
        }
        while ( v32 < (int)(v33 - 2) );
      }
      v32 += 2;
    }
  }
  else if ( v33 )
  {
    while ( 1 )
    {
      if ( v32 >= (int)(v33 - 1) )
      {
LABEL_60:
        ++v32;
        goto LABEL_61;
      }
      if ( *v35 > 0x7Fu )
        break;
      if ( !*v35 )
        goto LABEL_60;
      ++v32;
      ++v35;
    }
    v32 = 0;
  }
LABEL_61:
  if ( v33 <= v32 )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v65 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v65 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v65, "ApicFrameToASFNativeBlobEx", 1661, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v15 = 46;
    goto LABEL_14;
  }
  v71 = v7[v30];
  v36 = MultiByteToWideChar(0, 0, (LPCCH)v7 + 1, v20, 0, 0);
  if ( !v20 || v20 > 0 && v7[v20] )
    ++v36;
  v37 = 2 * v36;
  v38 = 65279;
  if ( !(_BYTE)v16 || (_BYTE)v16 == 3 )
  {
    v39 = (unsigned int)MultiByteToWideChar((_BYTE)v16 != 0 ? 0xFDE9 : 0, 0, (LPCCH)&v7[v20 + 2], v32, 0, 0);
    if ( !v32 || v32 > 0 && (v38 = v32, v34[v32 - 1]) )
      v39 = (unsigned int)(v39 + 1);
  }
  else
  {
    if ( v32 == -1 )
    {
      v70 = -1;
      do
        ++v70;
      while ( *(_WORD *)&v34[2 * v70] );
      v39 = (unsigned int)(v70 + 1);
      v40 = v39;
    }
    else
    {
      v39 = (unsigned __int64)v32 >> 1;
      v40 = v39;
      if ( !(_DWORD)v39 || (int)v39 > 0 && *(_WORD *)&v34[2 * (int)v39 - 2] )
        v39 = (unsigned int)(v39 + 1);
      v38 = 65279;
    }
    if ( (_BYTE)v16 == 1 && v40 )
    {
      v41 = &v7[v20 + 2];
      if ( *(_WORD *)v34 == 0xFEFF )
      {
        v39 = (unsigned int)(v39 - 1);
        if ( v40 == 1 )
          goto LABEL_82;
        v41 = v34 + 2;
      }
      if ( *(_WORD *)v41 == 0xFFFE )
        v39 = (unsigned int)(v39 - 1);
    }
  }
LABEL_82:
  if ( !v37 || (v42 = 2 * v39) == 0 )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v39);
      CallStackTracing::s_wpInstance = v61;
      if ( !v61 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v67 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v67 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v67, "ApicFrameToASFNativeBlobEx", 1676, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v15 = 47;
    goto LABEL_14;
  }
  cchWideChar = v37 >> 1;
  if ( v37 >> 1 > 0x100 || (v44 = v42 >> 1, v42 >> 1 > 0x400) )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v39);
      CallStackTracing::s_wpInstance = v60;
      if ( !v60 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v66 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v66 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v66, "ApicFrameToASFNativeBlobEx", 1690, -1072873844);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        WPP_9186553898a13577d84523ff6f078a03_Traceguids,
        0,
        -1072873844);
  }
  else
  {
    Sizea = Size - v32;
    v45 = v37 + v42 + Sizea + 5;
    if ( a4 )
    {
      if ( v45 <= *a5 )
      {
        v75 = &v74[v32 + v20 + 2];
        memset_0(a4, 0, *a5);
        *a4 = v71;
        *(_DWORD *)(a4 + 1) = Sizea;
        lpWideCharStr = (WCHAR *)&a4[v37 + 5];
        v47 = MultiByteToWideChar(0, 0, lpMultiByteStr, v20, (LPWSTR)(a4 + 5), cchWideChar);
        if ( (!v20 || v20 > 0 && lpMultiByteStr[v20 - 1]) && a4 != (unsigned __int8 *)-5LL && v47 < cchWideChar )
          *(_WORD *)&a4[2 * v47 + 5] = 0;
        if ( !(_BYTE)v16 || (_BYTE)v16 == 3 )
        {
          v52 = MultiByteToWideChar((_BYTE)v16 != 0 ? 0xFDE9 : 0, 0, Src, v32, lpWideCharStr, v42 >> 1);
          if ( (!v32 || v32 > 0 && Src[v32 - 1]) && lpWideCharStr && v52 < v44 )
            lpWideCharStr[v52] = 0;
          goto LABEL_111;
        }
        if ( (unsigned __int8)(v16 - 1) > 1u )
        {
          if ( lpWideCharStr )
            *lpWideCharStr = 0;
          goto LABEL_111;
        }
        v48 = Src;
        if ( v32 == -1 )
        {
          v49 = -1;
          do
            ++v49;
          while ( *(_WORD *)&Src[2 * v49] );
          LODWORD(v49) = v49 + 1;
          v50 = v49;
        }
        else
        {
          v49 = (unsigned __int64)v32 >> 1;
          if ( !(_DWORD)v49 || (v50 = (unsigned __int64)v32 >> 1, (int)v49 > 0) && *(_WORD *)&Src[2 * (int)v49 - 2] )
            v50 = v49 + 1;
        }
        if ( (_BYTE)v16 == 1 )
        {
          v51 = 0;
          if ( !(_DWORD)v49
            || *(_WORD *)Src == 0xFEFF && (v48 = Src + 2, --v50, LODWORD(v49) = v49 - 1, !(_DWORD)v49)
            || *(_WORD *)v48 != 0xFFFE )
          {
LABEL_103:
            if ( lpWideCharStr )
            {
              if ( v44 )
              {
                if ( v50 <= v44 )
                {
                  memset_0(lpWideCharStr, 0, 2LL * v50);
                  memcpy_0(lpWideCharStr, v48, 2LL * (int)v49);
                  if ( v51 )
                    ConvertWideCharByteOrder(lpWideCharStr, v49);
                }
              }
            }
LABEL_111:
            memcpy_0(&lpWideCharStr[v42 / 2], v75, Sizea);
            v14 = 0;
            *a5 = v45;
LABEL_112:
            *a3 = WMT_TYPE_BINARY;
            goto LABEL_39;
          }
          v48 += 2;
          LODWORD(v49) = v49 - 1;
          --v50;
        }
        v51 = 1;
        goto LABEL_103;
      }
      v14 = -1072875855;
    }
    else
    {
      v14 = 0;
    }
    *a5 = v45;
    if ( (int)(v14 + 0x80000000) < 0 || v14 == -1072875855 )
      goto LABEL_112;
  }
LABEL_39:
  v22 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v23 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v24 = GetLastError();
    v25 = (GUID *)TlsGetValue(*((_DWORD *)v22 + 3));
    if ( v25 )
    {
      v23 = v25;
    }
    else if ( !GetLastError() )
    {
      v55 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v55 = CallStackTracing::s_wpInstance;
      }
      v56 = (**(__int64 (__fastcall ***)(CallStackTracing *))v55)(v55);
      if ( v56 )
        v23 = (GUID *)v56;
    }
    SetLastError(v24);
    v26 = *(_DWORD *)&v23[124].Data2;
    if ( v26 )
    {
      v27 = v26 - 1;
      *(_DWORD *)&v23[124].Data2 = v27;
      if ( !v27 )
      {
        *(_DWORD *)&v23[124].Data2 = 0;
        *(_QWORD *)&v23[126].Data1 = 0;
        *(_DWORD *)&v23[124].Data4[4] = 0;
        v23[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v23[126].Data4 = 0;
        v23[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18002a8c0  mov     [rsp+arg_18], r9
0x18002a8c5  mov     [rsp+arg_10], r8
0x18002a8ca  mov     [rsp+arg_0], rcx
0x18002a8cf  push    rbx
0x18002a8d0  push    rdi
0x18002a8d1  push    r13
0x18002a8d3  push    r14
0x18002a8d5  sub     rsp, 78h
0x18002a8d9  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8e1  mov     rdi, r8
0x18002a8e4  mov     [rsp+98h+var_28], rbp
0x18002a8e9  mov     r14d, edx
0x18002a8ec  mov     [rsp+98h+var_38], r12
0x18002a8f1  lea     rbp, qword_1801B97E0
0x18002a8f8  mov     [rsp+98h+var_40], r15
0x18002a8fd  mov     r15, rcx
0x18002a900  jz      loc_18002ABBA
0x18002a906  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a90d  lea     r12, aApicframetoasf; "ApicFrameToASFNativeBlobEx"
0x18002a914  mov     [rsp+98h+var_30], rsi
0x18002a919  cmp     byte ptr [rbx+8], 0
0x18002a91d  jz      short loc_18002A988
0x18002a91f  lea     rdi, [rbx+0D0h]
0x18002a926  call    cs:__imp_GetLastError
0x18002a92d  nop     dword ptr [rax+rax+00h]
0x18002a932  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002a935  mov     esi, eax
0x18002a937  call    cs:__imp_TlsGetValue
0x18002a93e  nop     dword ptr [rax+rax+00h]
0x18002a943  test    rax, rax
0x18002a946  jz      loc_18002B0FD
0x18002a94c  mov     rdi, rax
0x18002a94f  mov     ecx, esi; dwErrCode
0x18002a951  call    cs:__imp_SetLastError
0x18002a958  nop     dword ptr [rax+rax+00h]
0x18002a95d  mov     eax, [rdi+7C4h]
0x18002a963  cmp     eax, [rdi+7C8h]
0x18002a969  jnb     short loc_18002A97A
0x18002a96b  add     rax, rax
0x18002a96e  mov     [rdi+rax*8], r12
0x18002a972  mov     dword ptr [rdi+rax*8+8], 627h
0x18002a97a  inc     dword ptr [rdi+7C4h]
0x18002a980  mov     rdi, [rsp+98h+arg_10]
0x18002a988  xor     r13d, r13d
0x18002a98b  test    r15, r15
0x18002a98e  jnz     short loc_18002A9EA
0x18002a990  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a997  mov     r14d, 80070057h
0x18002a99d  jz      loc_18002B18F
0x18002a9a3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a9aa  cmp     [rbx+8], r13b
0x18002a9ae  jnz     loc_18002B43A
0x18002a9b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002a9bb  jb      loc_18002AAF3
0x18002a9c1  mov     edx, 29h ; ')'
0x18002a9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9cd  lea     r8, WPP_9186553898a13577d84523ff6f078a03_Traceguids
0x18002a9d4  xor     r9d, r9d
0x18002a9d7  mov     dword ptr [rsp+98h+lpWideCharStr], r14d
0x18002a9dc  mov     rcx, [rcx+10h]
0x18002a9e0  call    WPP_SF_qD
0x18002a9e5  jmp     loc_18002AAF3
0x18002a9ea  test    rdi, rdi
0x18002a9ed  jz      short loc_18002A990
0x18002a9ef  cmp     [rsp+98h+arg_20], r13
0x18002a9f7  jz      short loc_18002A990
0x18002a9f9  cmp     r14d, 1
0x18002a9fd  jb      loc_18002B1A3
0x18002aa03  movzx   esi, byte ptr [r15]
0x18002aa07  mov     edx, r13d
0x18002aa0a  mov     ecx, esi
0x18002aa0c  test    esi, esi
0x18002aa0e  jz      loc_18002B4D1
0x18002aa14  sub     ecx, 1
0x18002aa17  jz      loc_18002B4C7
0x18002aa1d  sub     ecx, 1
0x18002aa20  jz      loc_18002B4C7
0x18002aa26  cmp     ecx, 1
0x18002aa29  jz      loc_18002B4D1
0x18002aa2f  lea     eax, [rdx+3]
0x18002aa32  cmp     eax, r14d
0x18002aa35  ja      loc_18002B1E1
0x18002aa3b  cmp     esi, 4
0x18002aa3e  jnb     loc_18002B21F
0x18002aa44  lea     r12, [r15+1]
0x18002aa48  mov     [rsp+98h+var_64], r13d
0x18002aa4d  lea     r8d, [r14-1]
0x18002aa51  mov     [rsp+98h+lpMultiByteStr], r12
0x18002aa56  mov     rcx, r12
0x18002aa59  mov     ebx, r13d
0x18002aa5c  cmp     r8d, 1
0x18002aa60  jb      loc_18002B199
0x18002aa66  lea     edx, [r8-1]
0x18002aa6a  nop     word ptr [rax+rax+00h]
0x18002aa70  cmp     ebx, edx
0x18002aa72  jge     short loc_18002AA8A
0x18002aa74  movzx   eax, byte ptr [rcx]
0x18002aa77  cmp     al, 7Fh
0x18002aa79  ja      loc_18002B0F5
0x18002aa7f  test    al, al
0x18002aa81  jz      short loc_18002AA8A
0x18002aa83  inc     ebx
0x18002aa85  inc     rcx
0x18002aa88  jmp     short loc_18002AA70
0x18002aa8a  inc     ebx
0x18002aa8c  mov     edx, r13d
0x18002aa8f  mov     ecx, esi
0x18002aa91  test    esi, esi
0x18002aa93  jz      loc_18002B58B
0x18002aa99  sub     ecx, 1
0x18002aa9c  jz      loc_18002B581
0x18002aaa2  sub     ecx, 1
0x18002aaa5  jz      loc_18002B581
0x18002aaab  cmp     ecx, 1
0x18002aaae  jz      loc_18002B58B
0x18002aab4  lea     eax, [rdx+1]
0x18002aab7  add     eax, ebx
0x18002aab9  cmp     r8d, eax
0x18002aabc  jnb     loc_18002ABEF
0x18002aac2  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aac9  mov     r14d, 0C00D3E8Ch
0x18002aacf  jz      loc_18002ABE5
0x18002aad5  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aadc  cmp     [rbx+8], r13b
0x18002aae0  jnz     loc_18002B408
0x18002aae6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002aaed  jnb     loc_18002B6BB
0x18002aaf3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aafa  mov     r15, [rsp+98h+var_40]
0x18002aaff  mov     r12, [rsp+98h+var_38]
0x18002ab04  mov     rbp, [rsp+98h+var_28]
0x18002ab09  cmp     byte ptr [rbx+8], 0
0x18002ab0d  jz      loc_18002ABA6
0x18002ab13  lea     rdi, [rbx+0D0h]
0x18002ab1a  call    cs:__imp_GetLastError
0x18002ab21  nop     dword ptr [rax+rax+00h]
0x18002ab26  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002ab29  mov     esi, eax
0x18002ab2b  call    cs:__imp_TlsGetValue
0x18002ab32  nop     dword ptr [rax+rax+00h]
0x18002ab37  test    rax, rax
0x18002ab3a  jz      loc_18002B134
0x18002ab40  mov     rdi, rax
0x18002ab43  mov     ecx, esi; dwErrCode
0x18002ab45  call    cs:__imp_SetLastError
0x18002ab4c  nop     dword ptr [rax+rax+00h]
0x18002ab51  mov     eax, [rdi+7C4h]
0x18002ab57  test    eax, eax
0x18002ab59  jz      short loc_18002ABA6
0x18002ab5b  sub     eax, 1
0x18002ab5e  mov     [rdi+7C4h], eax
0x18002ab64  jnz     short loc_18002ABA6
0x18002ab66  mov     [rdi+7C4h], r13d
0x18002ab6d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002ab74  mov     qword ptr [rdi+7E0h], 0
0x18002ab7f  mov     [rdi+7CCh], r13d
0x18002ab86  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002ab8d  mov     [rdi+7E8h], r13d
0x18002ab94  call    cs:__imp_GetCurrentThreadId
0x18002ab9b  nop     dword ptr [rax+rax+00h]
0x18002aba0  mov     [rdi+7C0h], eax
0x18002aba6  mov     rsi, [rsp+98h+var_30]
0x18002abab  mov     eax, r14d
0x18002abae  add     rsp, 78h
0x18002abb2  pop     r14
0x18002abb4  pop     r13
0x18002abb6  pop     rdi
0x18002abb7  pop     rbx
0x18002abb8  retn
0x18002abba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002abc1  nop     dword ptr [rax+rax+00h]
0x18002abc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002abcd  mov     rcx, rax
0x18002abd0  test    rax, rax
0x18002abd3  jnz     loc_18002B468
0x18002abd9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002abe0  jmp     loc_18002A906
0x18002abe5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002abea  jmp     loc_18002AAD5
0x18002abef  lea     r8d, [rbx+1]
0x18002abf3  cmp     r8d, ebx
0x18002abf6  jb      loc_18002AAC2
0x18002abfc  mov     edx, r13d
0x18002abff  mov     ecx, esi
0x18002ac01  test    esi, esi
0x18002ac03  jz      loc_18002B59F
0x18002ac09  sub     ecx, 1
0x18002ac0c  jz      loc_18002B595
0x18002ac12  sub     ecx, 1
0x18002ac15  jz      loc_18002B595
0x18002ac1b  cmp     ecx, 1
0x18002ac1e  jz      loc_18002B59F
0x18002ac24  lea     eax, [rdx+1]
0x18002ac27  add     eax, ebx
0x18002ac29  cmp     eax, r8d
0x18002ac2c  jb      loc_18002AAC2
0x18002ac32  lea     eax, [rbx+2]
0x18002ac35  mov     edi, r13d
0x18002ac38  sub     r14d, eax
0x18002ac3b  mov     ebp, eax
0x18002ac3d  add     rbp, r15
0x18002ac40  mov     dword ptr [rsp+98h+Size], r14d
0x18002ac48  mov     [rsp+98h+Src], rbp
0x18002ac4d  mov     rcx, rbp
0x18002ac50  test    sil, sil
0x18002ac53  jnz     loc_18002B00F
0x18002ac59  cmp     r14d, 1
0x18002ac5d  jb      short loc_18002AC7F
0x18002ac5f  lea     edx, [r14-1]
0x18002ac63  cmp     edi, edx
0x18002ac65  jge     short loc_18002AC7D
0x18002ac67  movzx   eax, byte ptr [rcx]
0x18002ac6a  cmp     al, 7Fh
0x18002ac6c  ja      loc_18002B187
0x18002ac72  test    al, al
0x18002ac74  jz      short loc_18002AC7D
0x18002ac76  inc     edi
0x18002ac78  inc     rcx
0x18002ac7b  jmp     short loc_18002AC63
0x18002ac7d  inc     edi
0x18002ac7f  cmp     r14d, edi
0x18002ac82  jbe     loc_18002B049
0x18002ac88  movzx   eax, byte ptr [r8+r15]
0x18002ac8d  mov     r9d, ebx; cbMultiByte
0x18002ac90  mov     r8, r12; lpMultiByteStr
0x18002ac93  mov     [rsp+98h+cchWideChar], r13d; cchWideChar
0x18002ac98  xor     edx, edx; dwFlags
0x18002ac9a  mov     [rsp+98h+var_68], al
0x18002ac9e  xor     ecx, ecx; CodePage
0x18002aca0  mov     [rsp+98h+lpWideCharStr], r13; lpWideCharStr
0x18002aca5  call    cs:__imp_MultiByteToWideChar
0x18002acac  nop     dword ptr [rax+rax+00h]
0x18002acb1  test    ebx, ebx
0x18002acb3  jz      loc_18002B084
0x18002acb9  jle     short loc_18002ACC9
0x18002acbb  movsxd  rcx, ebx
0x18002acbe  cmp     [rcx+r12-1], r13b
0x18002acc3  jnz     loc_18002B084
0x18002acc9  lea     r12d, [rax+rax]
0x18002accd  mov     ecx, 0FEFFh
0x18002acd2  mov     r9d, 0FFFEh
0x18002acd8  test    sil, sil
0x18002acdb  jz      short loc_18002AD49
0x18002acdd  cmp     sil, 1
0x18002ace1  jnz     short loc_18002AD3F
0x18002ace3  cmp     edi, 0FFFFFFFFh
0x18002ace6  jz      loc_18002B5BB
0x18002acec  movsxd  rdx, edi
0x18002acef  shr     rdx, 1
0x18002acf2  mov     r8d, edx
0x18002acf5  test    edx, edx
0x18002acf7  jz      loc_18002B092
0x18002acfd  jle     short loc_18002AD0E
0x18002acff  movsxd  rcx, edx
0x18002ad02  cmp     r13w, [rbp+rcx*2-2]
0x18002ad08  jnz     loc_18002B092
0x18002ad0e  mov     ecx, 0FEFFh
0x18002ad13  cmp     sil, 1
0x18002ad17  jnz     short loc_18002AD8F
0x18002ad19  test    r8d, r8d
0x18002ad1c  jz      short loc_18002AD8F
0x18002ad1e  mov     rax, rbp
0x18002ad21  cmp     cx, [rbp+0]
0x18002ad25  jnz     short loc_18002AD35
0x18002ad27  dec     edx
0x18002ad29  lea     eax, [r8-1]
0x18002ad2d  test    eax, eax
0x18002ad2f  jz      short loc_18002AD8F
0x18002ad31  lea     rax, [rbp+2]
0x18002ad35  cmp     r9w, [rax]
0x18002ad39  jnz     short loc_18002AD8F
0x18002ad3b  dec     edx
0x18002ad3d  jmp     short loc_18002AD8F
0x18002ad3f  cmp     sil, 3
0x18002ad43  jnz     loc_18002B5A9
0x18002ad49  movzx   eax, sil
0x18002ad4d  mov     [rsp+98h+cchWideChar], r13d; cchWideChar
0x18002ad52  neg     al
0x18002ad54  mov     [rsp+98h+lpWideCharStr], r13; lpWideCharStr
0x18002ad59  mov     r9d, edi; cbMultiByte
0x18002ad5c  mov     r8, rbp; lpMultiByteStr
0x18002ad5f  sbb     ecx, ecx
0x18002ad61  xor     edx, edx; dwFlags
0x18002ad63  and     ecx, 0FDE9h; CodePage
0x18002ad69  call    cs:__imp_MultiByteToWideChar
0x18002ad70  nop     dword ptr [rax+rax+00h]
0x18002ad75  mov     edx, eax
0x18002ad77  test    edi, edi
0x18002ad79  jz      loc_18002B08B
0x18002ad7f  jle     short loc_18002AD8F
0x18002ad81  movsxd  rcx, edi
0x18002ad84  cmp     [rcx+rbp-1], r13b
0x18002ad89  jnz     loc_18002B08B
0x18002ad8f  test    r12d, r12d
0x18002ad92  jz      loc_18002B29D
0x18002ad98  lea     r14d, [rdx+rdx]
0x18002ad9c  test    r14d, r14d
0x18002ad9f  jz      loc_18002B29D
0x18002ada5  mov     eax, r12d
0x18002ada8  shr     eax, 1
  ... truncated ...
```
