# ApicFrameToASFNativeBlobEx(uchar const *,ulong,WMT_ATTR_DATATYPE *,uchar *,ulong *)

- ea: `0x18001f8d0`
- end: `0x180020689`
- name: `?ApicFrameToASFNativeBlobEx@@YAJPEBEKPEAW4WMT_ATTR_DATATYPE@@PEAEPEAK@Z`
- size: `3513`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, enum WMT_ATTR_DATATYPE *, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18001ce00`
- `0x18001e690`

## callees

- `0x180010190`
- `0x18001303c`
- `0x18001f8d0`
- `0x180071a44`
- `0x180073b14`
- `0x18010a450`
- `0x1801613bc`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f955`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fb2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f955`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fb2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200fe`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fc95`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fd53`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fe4e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ff5d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fc95`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fd53`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fe4e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ff5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fb76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fb76`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f941`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fb19`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f941`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fb19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001fb95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001fbba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002017a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800201b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800201e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002021d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002025c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001fb95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001fbba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002017a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800201b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800201e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002021d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002025c`

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
  __int64 v19; // r8
  _BYTE *v20; // rcx
  int v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // rcx
  CallStackTracing *v24; // rbx
  GUID *v25; // rdi
  DWORD v26; // esi
  GUID *v27; // rax
  int v28; // eax
  int v29; // eax
  CallStackTracing *v31; // rax
  CallStackTracing *v32; // rax
  int v33; // edi
  unsigned int v34; // r14d
  const unsigned __int8 *v35; // rbp
  const unsigned __int8 *v36; // rcx
  int v37; // eax
  unsigned int v38; // r12d
  __int64 v39; // rcx
  __int64 v40; // r9
  unsigned __int64 v41; // rdx
  __int64 v42; // r8
  const unsigned __int8 *v43; // rax
  unsigned int v44; // r14d
  int cchWideChar; // r13d
  int v46; // r15d
  unsigned int v47; // ebp
  WCHAR *lpWideCharStr; // r12
  int v49; // eax
  const CHAR *v50; // r13
  unsigned __int64 v51; // rbx
  int v52; // edx
  int v53; // edi
  int v54; // eax
  CallStackTracing *v55; // rcx
  __int64 v56; // rax
  CallStackTracing *v57; // rcx
  __int64 v58; // rax
  CallStackTracing *v59; // rax
  CallStackTracing *v60; // rax
  CallStackTracing *v61; // rax
  CallStackTracing *v62; // rax
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  struct CallStackContext *v65; // rax
  struct CallStackContext *v66; // rax
  struct CallStackContext *v67; // rax
  struct CallStackContext *v68; // rax
  struct CallStackContext *v69; // rax
  struct CallStackContext *v70; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v72; // rdx
  unsigned __int8 v73; // [rsp+30h] [rbp-68h]
  const CHAR *Src; // [rsp+38h] [rbp-60h]
  const CHAR *lpMultiByteStr; // [rsp+40h] [rbp-58h]
  const unsigned __int8 *v76; // [rsp+A0h] [rbp+8h]
  const unsigned __int8 *v77; // [rsp+A0h] [rbp+8h]
  unsigned int Size; // [rsp+A8h] [rbp+10h]
  unsigned int Sizea; // [rsp+A8h] [rbp+10h]

  v76 = (const unsigned __int8 *)a1;
  v5 = a3;
  v6 = a2;
  v7 = (const unsigned __int8 *)a1;
  if ( !CallStackTracing::s_wpInstance )
  {
    v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2, a3, a4);
    CallStackTracing::s_wpInstance = v31;
    a1 = v31;
    if ( !v31 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v55 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v55 = CallStackTracing::s_wpInstance;
      }
      v56 = (**(__int64 (__fastcall ***)(CallStackTracing *))v55)(v55);
      if ( v56 )
        v9 = (char *)v56;
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
      goto LABEL_38;
    v15 = 41;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_9186553898a13577d84523ff6f078a03_Traceguids, 0, v14);
    goto LABEL_38;
  }
  if ( !v6 )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2, a3, a4);
      CallStackTracing::s_wpInstance = v59;
      if ( !v59 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v64 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v64 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v64, "ApicFrameToASFNativeBlobEx", 1610, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_38;
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
      v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v17, a3, a4);
      CallStackTracing::s_wpInstance = v60;
      if ( !v60 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v65 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v65 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v65, "ApicFrameToASFNativeBlobEx", 1618, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = 43;
    goto LABEL_14;
  }
  if ( v16 >= 4 )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v17, a3, a4);
      CallStackTracing::s_wpInstance = v61;
      if ( !v61 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v66 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v66 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v66, "ApicFrameToASFNativeBlobEx", 1624, -1072873844);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        &WPP_9186553898a13577d84523ff6f078a03_Traceguids,
        0,
        -1072873844);
    v14 = -1072873844;
    goto LABEL_38;
  }
  v19 = v6 - 1;
  lpMultiByteStr = (const CHAR *)(v7 + 1);
  v20 = v7 + 1;
  v21 = 0;
  if ( v6 != 1 )
  {
    while ( 1 )
    {
      if ( v21 >= (int)(v6 - 2) )
      {
LABEL_29:
        ++v21;
        goto LABEL_30;
      }
      if ( *v20 > 0x7Fu )
        break;
      if ( !*v20 )
        goto LABEL_29;
      ++v21;
      ++v20;
    }
    v21 = 0;
  }
LABEL_30:
  v22 = 0;
  v23 = *v7;
  if ( !*v7 )
    goto LABEL_205;
  v23 = (unsigned int)(v23 - 1);
  if ( !(_DWORD)v23 || (v23 = (unsigned int)(v23 - 1), !(_DWORD)v23) )
  {
    v22 = 2;
    goto LABEL_34;
  }
  if ( (_DWORD)v23 == 1 )
LABEL_205:
    v22 = 1;
LABEL_34:
  if ( (unsigned int)v19 < v21 + (int)v22 + 1 )
    goto LABEL_35;
  v19 = (unsigned int)(v21 + 1);
  if ( (unsigned int)v19 < v21 )
    goto LABEL_35;
  v22 = 0;
  v23 = *v7;
  if ( *v7 )
  {
    v23 = (unsigned int)(v23 - 1);
    if ( !(_DWORD)v23 || (v23 = (unsigned int)(v23 - 1), !(_DWORD)v23) )
    {
      v22 = 2;
      goto LABEL_54;
    }
    if ( (_DWORD)v23 != 1 )
      goto LABEL_54;
  }
  v22 = 1;
LABEL_54:
  if ( v21 + (int)v22 + 1 < (unsigned int)v19 )
  {
LABEL_35:
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v22, v19, a4);
      CallStackTracing::s_wpInstance = v32;
      if ( !v32 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v70 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v70 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v70, "ApicFrameToASFNativeBlobEx", 1643, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = 45;
    goto LABEL_14;
  }
  v33 = 0;
  v34 = v6 - (v21 + 2);
  v35 = &v7[v21 + 2];
  Size = v34;
  Src = (const CHAR *)v35;
  v36 = v35;
  if ( (_BYTE)v16 )
  {
    if ( (unsigned __int8)(v16 - 1) <= 1u && v34 >= 2 )
    {
      if ( (int)(v34 - 2) > 0 )
      {
        do
        {
          if ( !*(_WORD *)v36 )
            break;
          v33 += 2;
          v36 += 2;
        }
        while ( v33 < (int)(v34 - 2) );
      }
      v33 += 2;
    }
  }
  else if ( v34 )
  {
    while ( 1 )
    {
      if ( v33 >= (int)(v34 - 1) )
      {
LABEL_61:
        ++v33;
        goto LABEL_62;
      }
      if ( *v36 > 0x7Fu )
        break;
      if ( !*v36 )
        goto LABEL_61;
      ++v33;
      ++v36;
    }
    v33 = 0;
  }
LABEL_62:
  if ( v34 <= v33 )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v67 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v67 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v67, "ApicFrameToASFNativeBlobEx", 1661, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = 46;
    goto LABEL_14;
  }
  v73 = v7[v19];
  v37 = MultiByteToWideChar(0, 0, (LPCCH)v7 + 1, v21, 0, 0);
  if ( !v21 || v21 > 0 && v7[v21] )
    ++v37;
  v38 = 2 * v37;
  v39 = 65279;
  v40 = 65534;
  if ( !(_BYTE)v16 || (_BYTE)v16 == 3 )
  {
    v41 = (unsigned int)MultiByteToWideChar((_BYTE)v16 != 0 ? 0xFDE9 : 0, 0, (LPCCH)&v7[v21 + 2], v33, 0, 0);
    if ( !v33 || v33 > 0 && (v39 = v33, v35[v33 - 1]) )
      v41 = (unsigned int)(v41 + 1);
  }
  else
  {
    if ( v33 == -1 )
    {
      v72 = -1;
      do
        ++v72;
      while ( *(_WORD *)&v35[2 * v72] );
      v41 = (unsigned int)(v72 + 1);
      v42 = (unsigned int)v41;
    }
    else
    {
      v41 = (unsigned __int64)v33 >> 1;
      v42 = (unsigned int)v41;
      if ( !(_DWORD)v41 || (int)v41 > 0 && *(_WORD *)&v35[2 * (int)v41 - 2] )
        v41 = (unsigned int)(v41 + 1);
      v39 = 65279;
    }
    if ( (_BYTE)v16 == 1 && (_DWORD)v42 )
    {
      v43 = &v7[v21 + 2];
      if ( *(_WORD *)v35 == 0xFEFF )
      {
        v41 = (unsigned int)(v41 - 1);
        if ( (_DWORD)v42 == 1 )
          goto LABEL_83;
        v43 = v35 + 2;
      }
      if ( *(_WORD *)v43 == 0xFFFE )
        v41 = (unsigned int)(v41 - 1);
    }
  }
LABEL_83:
  if ( !v38 || (v44 = 2 * v41) == 0 )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v39, v41, v42, v40);
      CallStackTracing::s_wpInstance = v63;
      if ( !v63 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v69 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v69 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v69, "ApicFrameToASFNativeBlobEx", 1676, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = 47;
    goto LABEL_14;
  }
  cchWideChar = v38 >> 1;
  if ( v38 >> 1 > 0x100 || (v46 = v44 >> 1, v44 >> 1 > 0x400) )
  {
    v14 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v39, v41, v42, v40);
      CallStackTracing::s_wpInstance = v62;
      if ( !v62 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v68 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v68 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v68, "ApicFrameToASFNativeBlobEx", 1690, -1072873844);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_9186553898a13577d84523ff6f078a03_Traceguids,
        0,
        -1072873844);
  }
  else
  {
    Sizea = Size - v33;
    v47 = v38 + v44 + Sizea + 5;
    if ( a4 )
    {
      if ( v47 <= *a5 )
      {
        v77 = &v76[v33 + v21 + 2];
        memset_0(a4, 0, *a5);
        *a4 = v73;
        *(_DWORD *)(a4 + 1) = Sizea;
        lpWideCharStr = (WCHAR *)&a4[v38 + 5];
        v49 = MultiByteToWideChar(0, 0, lpMultiByteStr, v21, (LPWSTR)(a4 + 5), cchWideChar);
        if ( (!v21 || v21 > 0 && lpMultiByteStr[v21 - 1]) && a4 != (unsigned __int8 *)-5LL && v49 < cchWideChar )
          *(_WORD *)&a4[2 * v49 + 5] = 0;
        if ( !(_BYTE)v16 || (_BYTE)v16 == 3 )
        {
          v54 = MultiByteToWideChar((_BYTE)v16 != 0 ? 0xFDE9 : 0, 0, Src, v33, lpWideCharStr, v44 >> 1);
          if ( (!v33 || v33 > 0 && Src[v33 - 1]) && lpWideCharStr && v54 < v46 )
            lpWideCharStr[v54] = 0;
          goto LABEL_112;
        }
        if ( (unsigned __int8)(v16 - 1) > 1u )
        {
          if ( lpWideCharStr )
            *lpWideCharStr = 0;
          goto LABEL_112;
        }
        v50 = Src;
        if ( v33 == -1 )
        {
          v51 = -1;
          do
            ++v51;
          while ( *(_WORD *)&Src[2 * v51] );
          LODWORD(v51) = v51 + 1;
          v52 = v51;
        }
        else
        {
          v51 = (unsigned __int64)v33 >> 1;
          if ( !(_DWORD)v51 || (v52 = (unsigned __int64)v33 >> 1, (int)v51 > 0) && *(_WORD *)&Src[2 * (int)v51 - 2] )
            v52 = v51 + 1;
        }
        if ( (_BYTE)v16 == 1 )
        {
          v53 = 0;
          if ( !(_DWORD)v51
            || *(_WORD *)Src == 0xFEFF && (v50 = Src + 2, --v52, LODWORD(v51) = v51 - 1, !(_DWORD)v51)
            || *(_WORD *)v50 != 0xFFFE )
          {
LABEL_104:
            if ( lpWideCharStr )
            {
              if ( v46 )
              {
                if ( v52 <= v46 )
                {
                  memset_0(lpWideCharStr, 0, 2LL * v52);
                  memcpy_0(lpWideCharStr, v50, 2LL * (int)v51);
                  if ( v53 )
                    ConvertWideCharByteOrder(lpWideCharStr, v51);
                }
              }
            }
LABEL_112:
            memcpy_0(&lpWideCharStr[v44 / 2], v77, Sizea);
            v14 = 0;
            *a5 = v47;
LABEL_113:
            *a3 = WMT_TYPE_BINARY;
            goto LABEL_38;
          }
          v50 += 2;
          LODWORD(v51) = v51 - 1;
          --v52;
        }
        v53 = 1;
        goto LABEL_104;
      }
      v14 = -1072875855;
    }
    else
    {
      v14 = 0;
    }
    *a5 = v47;
    if ( (int)(v14 + 0x80000000) < 0 || v14 == -1072875855 )
      goto LABEL_113;
  }
LABEL_38:
  v24 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v25 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v26 = GetLastError();
    v27 = (GUID *)TlsGetValue(*((_DWORD *)v24 + 3));
    if ( v27 )
    {
      v25 = v27;
    }
    else if ( !GetLastError() )
    {
      v57 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v57 = CallStackTracing::s_wpInstance;
      }
      v58 = (**(__int64 (__fastcall ***)(CallStackTracing *))v57)(v57);
      if ( v58 )
        v25 = (GUID *)v58;
    }
    SetLastError(v26);
    v28 = *(_DWORD *)&v25[124].Data2;
    if ( v28 )
    {
      v29 = v28 - 1;
      *(_DWORD *)&v25[124].Data2 = v29;
      if ( !v29 )
      {
        *(_DWORD *)&v25[124].Data2 = 0;
        *(_QWORD *)&v25[126].Data1 = 0;
        *(_DWORD *)&v25[124].Data4[4] = 0;
        v25[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v25[126].Data4 = 0;
        v25[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18001f8d0  mov     [rsp+arg_18], r9
0x18001f8d5  mov     [rsp+arg_10], r8
0x18001f8da  mov     [rsp+arg_0], rcx
0x18001f8df  push    rbx
0x18001f8e0  push    rdi
0x18001f8e1  push    r13
0x18001f8e3  push    r14
0x18001f8e5  sub     rsp, 78h
0x18001f8e9  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f8f1  mov     rdi, r8
0x18001f8f4  mov     [rsp+98h+var_28], rbp
0x18001f8f9  mov     r14d, edx
0x18001f8fc  mov     [rsp+98h+var_38], r12
0x18001f901  lea     rbp, qword_1801B07E0
0x18001f908  mov     [rsp+98h+var_40], r15
0x18001f90d  mov     r15, rcx
0x18001f910  jz      loc_18001FB95
0x18001f916  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f91d  lea     r12, aApicframetoasf; "ApicFrameToASFNativeBlobEx"
0x18001f924  mov     [rsp+98h+var_30], rsi
0x18001f929  cmp     byte ptr [rbx+8], 0
0x18001f92d  jz      short loc_18001F986
0x18001f92f  lea     rdi, [rbx+0D0h]
0x18001f936  call    cs:__imp_GetLastError
0x18001f93c  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001f93f  mov     esi, eax
0x18001f941  call    cs:__imp_TlsGetValue
0x18001f947  test    rax, rax
0x18001f94a  jz      loc_1800200CD
0x18001f950  mov     rdi, rax
0x18001f953  mov     ecx, esi; dwErrCode
0x18001f955  call    cs:__imp_SetLastError
0x18001f95b  mov     eax, [rdi+7C4h]
0x18001f961  cmp     eax, [rdi+7C8h]
0x18001f967  jnb     short loc_18001F978
0x18001f969  add     rax, rax
0x18001f96c  mov     [rdi+rax*8], r12
0x18001f970  mov     dword ptr [rdi+rax*8+8], 627h
0x18001f978  inc     dword ptr [rdi+7C4h]
0x18001f97e  mov     rdi, [rsp+98h+arg_10]
0x18001f986  xor     r13d, r13d
0x18001f989  test    r15, r15
0x18001f98c  jnz     short loc_18001F9E8
0x18001f98e  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f995  mov     r14d, 80070057h
0x18001f99b  jz      loc_180020153
0x18001f9a1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f9a8  cmp     [rbx+8], r13b
0x18001f9ac  jnz     loc_1800203E0
0x18001f9b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f9b9  jb      loc_18001FAEB
0x18001f9bf  mov     edx, 29h ; ')'
0x18001f9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9cb  lea     r8, WPP_9186553898a13577d84523ff6f078a03_Traceguids
0x18001f9d2  xor     r9d, r9d
0x18001f9d5  mov     dword ptr [rsp+98h+lpWideCharStr], r14d
0x18001f9da  mov     rcx, [rcx+10h]
0x18001f9de  call    WPP_SF_qD
0x18001f9e3  jmp     loc_18001FAEB
0x18001f9e8  test    rdi, rdi
0x18001f9eb  jz      short loc_18001F98E
0x18001f9ed  cmp     [rsp+98h+arg_20], r13
0x18001f9f5  jz      short loc_18001F98E
0x18001f9f7  cmp     r14d, 1
0x18001f9fb  jb      loc_180020167
0x18001fa01  movzx   esi, byte ptr [r15]
0x18001fa05  mov     edx, r13d
0x18001fa08  mov     ecx, esi
0x18001fa0a  test    esi, esi
0x18001fa0c  jz      loc_180020477
0x18001fa12  sub     ecx, 1
0x18001fa15  jz      loc_18002046D
0x18001fa1b  sub     ecx, 1
0x18001fa1e  jz      loc_18002046D
0x18001fa24  cmp     ecx, 1
0x18001fa27  jz      loc_180020477
0x18001fa2d  lea     eax, [rdx+3]
0x18001fa30  cmp     eax, r14d
0x18001fa33  ja      loc_18002019F
0x18001fa39  cmp     esi, 4
0x18001fa3c  jnb     loc_1800201D7
0x18001fa42  lea     r12, [r15+1]
0x18001fa46  mov     [rsp+98h+var_64], r13d
0x18001fa4b  lea     r8d, [r14-1]
0x18001fa4f  mov     [rsp+98h+lpMultiByteStr], r12
0x18001fa54  mov     rcx, r12
0x18001fa57  mov     ebx, r13d
0x18001fa5a  cmp     r8d, 1
0x18001fa5e  jb      loc_18002015D
0x18001fa64  lea     edx, [r8-1]
0x18001fa68  cmp     ebx, edx
0x18001fa6a  jge     short loc_18001FA82
0x18001fa6c  movzx   eax, byte ptr [rcx]
0x18001fa6f  cmp     al, 7Fh
0x18001fa71  ja      loc_1800200C5
0x18001fa77  test    al, al
0x18001fa79  jz      short loc_18001FA82
0x18001fa7b  inc     ebx
0x18001fa7d  inc     rcx
0x18001fa80  jmp     short loc_18001FA68
0x18001fa82  inc     ebx
0x18001fa84  mov     edx, r13d
0x18001fa87  mov     ecx, esi
0x18001fa89  test    esi, esi
0x18001fa8b  jz      loc_180020531
0x18001fa91  sub     ecx, 1
0x18001fa94  jz      loc_180020527
0x18001fa9a  sub     ecx, 1
0x18001fa9d  jz      loc_180020527
0x18001faa3  cmp     ecx, 1
0x18001faa6  jz      loc_180020531
0x18001faac  lea     eax, [rdx+1]
0x18001faaf  add     eax, ebx
0x18001fab1  cmp     r8d, eax
0x18001fab4  jnb     loc_18001FBDF
0x18001faba  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18001fac1  mov     r14d, 0C00D3E8Ch
0x18001fac7  jz      loc_18001FBBA
0x18001facd  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001fad4  cmp     [rbx+8], r13b
0x18001fad8  jnz     loc_1800203AE
0x18001fade  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001fae5  jnb     loc_18002067F
0x18001faeb  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001faf2  mov     r15, [rsp+98h+var_40]
0x18001faf7  mov     r12, [rsp+98h+var_38]
0x18001fafc  mov     rbp, [rsp+98h+var_28]
0x18001fb01  cmp     byte ptr [rbx+8], 0
0x18001fb05  jz      short loc_18001FB82
0x18001fb07  lea     rdi, [rbx+0D0h]
0x18001fb0e  call    cs:__imp_GetLastError
0x18001fb14  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001fb17  mov     esi, eax
0x18001fb19  call    cs:__imp_TlsGetValue
0x18001fb1f  test    rax, rax
0x18001fb22  jz      loc_1800200FE
0x18001fb28  mov     rdi, rax
0x18001fb2b  mov     ecx, esi; dwErrCode
0x18001fb2d  call    cs:__imp_SetLastError
0x18001fb33  mov     eax, [rdi+7C4h]
0x18001fb39  test    eax, eax
0x18001fb3b  jz      short loc_18001FB82
0x18001fb3d  sub     eax, 1
0x18001fb40  mov     [rdi+7C4h], eax
0x18001fb46  jnz     short loc_18001FB82
0x18001fb48  mov     [rdi+7C4h], r13d
0x18001fb4f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001fb56  mov     qword ptr [rdi+7E0h], 0
0x18001fb61  mov     [rdi+7CCh], r13d
0x18001fb68  movups  xmmword ptr [rdi+7D0h], xmm0
0x18001fb6f  mov     [rdi+7E8h], r13d
0x18001fb76  call    cs:__imp_GetCurrentThreadId
0x18001fb7c  mov     [rdi+7C0h], eax
0x18001fb82  mov     rsi, [rsp+98h+var_30]
0x18001fb87  mov     eax, r14d
0x18001fb8a  add     rsp, 78h
0x18001fb8e  pop     r14
0x18001fb90  pop     r13
0x18001fb92  pop     rdi
0x18001fb93  pop     rbx
0x18001fb94  retn
0x18001fb95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001fb9b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001fba2  mov     rcx, rax
0x18001fba5  test    rax, rax
0x18001fba8  jnz     loc_18002040E
0x18001fbae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18001fbb5  jmp     loc_18001F916
0x18001fbba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001fbc0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001fbc7  mov     rcx, rax
0x18001fbca  test    rax, rax
0x18001fbcd  jnz     loc_180020661
0x18001fbd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18001fbda  jmp     loc_18001FACD
0x18001fbdf  lea     r8d, [rbx+1]
0x18001fbe3  cmp     r8d, ebx
0x18001fbe6  jb      loc_18001FABA
0x18001fbec  mov     edx, r13d
0x18001fbef  mov     ecx, esi
0x18001fbf1  test    esi, esi
0x18001fbf3  jz      loc_180020545
0x18001fbf9  sub     ecx, 1
0x18001fbfc  jz      loc_18002053B
0x18001fc02  sub     ecx, 1
0x18001fc05  jz      loc_18002053B
0x18001fc0b  cmp     ecx, 1
0x18001fc0e  jz      loc_180020545
0x18001fc14  lea     eax, [rdx+1]
0x18001fc17  add     eax, ebx
0x18001fc19  cmp     eax, r8d
0x18001fc1c  jb      loc_18001FABA
0x18001fc22  lea     eax, [rbx+2]
0x18001fc25  mov     edi, r13d
0x18001fc28  sub     r14d, eax
0x18001fc2b  mov     ebp, eax
0x18001fc2d  add     rbp, r15
0x18001fc30  mov     dword ptr [rsp+98h+Size], r14d
0x18001fc38  mov     [rsp+98h+Src], rbp
0x18001fc3d  mov     rcx, rbp
0x18001fc40  test    sil, sil
0x18001fc43  jnz     loc_18001FFE3
0x18001fc49  cmp     r14d, 1
0x18001fc4d  jb      short loc_18001FC6F
0x18001fc4f  lea     edx, [r14-1]
0x18001fc53  cmp     edi, edx
0x18001fc55  jge     short loc_18001FC6D
0x18001fc57  movzx   eax, byte ptr [rcx]
0x18001fc5a  cmp     al, 7Fh
0x18001fc5c  ja      loc_18002014B
0x18001fc62  test    al, al
0x18001fc64  jz      short loc_18001FC6D
0x18001fc66  inc     edi
0x18001fc68  inc     rcx
0x18001fc6b  jmp     short loc_18001FC53
0x18001fc6d  inc     edi
0x18001fc6f  cmp     r14d, edi
0x18001fc72  jbe     loc_180020019
0x18001fc78  movzx   eax, byte ptr [r8+r15]
0x18001fc7d  mov     r9d, ebx; cbMultiByte
0x18001fc80  mov     r8, r12; lpMultiByteStr
0x18001fc83  mov     [rsp+98h+cchWideChar], r13d; cchWideChar
0x18001fc88  xor     edx, edx; dwFlags
0x18001fc8a  mov     [rsp+98h+var_68], al
0x18001fc8e  xor     ecx, ecx; CodePage
0x18001fc90  mov     [rsp+98h+lpWideCharStr], r13; lpWideCharStr
0x18001fc95  call    cs:__imp_MultiByteToWideChar
0x18001fc9b  test    ebx, ebx
0x18001fc9d  jz      loc_180020054
0x18001fca3  jle     short loc_18001FCB3
0x18001fca5  movsxd  rcx, ebx
0x18001fca8  cmp     [rcx+r12-1], r13b
0x18001fcad  jnz     loc_180020054
0x18001fcb3  lea     r12d, [rax+rax]
0x18001fcb7  mov     ecx, 0FEFFh
0x18001fcbc  mov     r9d, 0FFFEh
0x18001fcc2  test    sil, sil
0x18001fcc5  jz      short loc_18001FD33
0x18001fcc7  cmp     sil, 1
0x18001fccb  jnz     short loc_18001FD29
0x18001fccd  cmp     edi, 0FFFFFFFFh
0x18001fcd0  jz      loc_180020561
0x18001fcd6  movsxd  rdx, edi
0x18001fcd9  shr     rdx, 1
0x18001fcdc  mov     r8d, edx
0x18001fcdf  test    edx, edx
0x18001fce1  jz      loc_180020062
0x18001fce7  jle     short loc_18001FCF8
0x18001fce9  movsxd  rcx, edx
0x18001fcec  cmp     r13w, [rbp+rcx*2-2]
0x18001fcf2  jnz     loc_180020062
0x18001fcf8  mov     ecx, 0FEFFh
0x18001fcfd  cmp     sil, 1
0x18001fd01  jnz     short loc_18001FD73
0x18001fd03  test    r8d, r8d
0x18001fd06  jz      short loc_18001FD73
0x18001fd08  mov     rax, rbp
0x18001fd0b  cmp     cx, [rbp+0]
0x18001fd0f  jnz     short loc_18001FD1F
0x18001fd11  dec     edx
0x18001fd13  lea     eax, [r8-1]
0x18001fd17  test    eax, eax
0x18001fd19  jz      short loc_18001FD73
0x18001fd1b  lea     rax, [rbp+2]
0x18001fd1f  cmp     r9w, [rax]
0x18001fd23  jnz     short loc_18001FD73
0x18001fd25  dec     edx
0x18001fd27  jmp     short loc_18001FD73
0x18001fd29  cmp     sil, 3
0x18001fd2d  jnz     loc_18002054F
0x18001fd33  movzx   eax, sil
0x18001fd37  mov     [rsp+98h+cchWideChar], r13d; cchWideChar
0x18001fd3c  neg     al
0x18001fd3e  mov     [rsp+98h+lpWideCharStr], r13; lpWideCharStr
0x18001fd43  mov     r9d, edi; cbMultiByte
0x18001fd46  mov     r8, rbp; lpMultiByteStr
0x18001fd49  sbb     ecx, ecx
0x18001fd4b  xor     edx, edx; dwFlags
0x18001fd4d  and     ecx, 0FDE9h; CodePage
0x18001fd53  call    cs:__imp_MultiByteToWideChar
0x18001fd59  mov     edx, eax
0x18001fd5b  test    edi, edi
0x18001fd5d  jz      loc_18002005B
0x18001fd63  jle     short loc_18001FD73
0x18001fd65  movsxd  rcx, edi
0x18001fd68  cmp     [rcx+rbp-1], r13b
0x18001fd6d  jnz     loc_18002005B
0x18001fd73  test    r12d, r12d
0x18001fd76  jz      loc_180020249
0x18001fd7c  lea     r14d, [rdx+rdx]
0x18001fd80  test    r14d, r14d
0x18001fd83  jz      loc_180020249
0x18001fd89  mov     eax, r12d
0x18001fd8c  shr     eax, 1
0x18001fd8e  mov     r13d, eax
0x18001fd91  cmp     eax, 100h
0x18001fd96  ja      loc_180020209
0x18001fd9c  mov     r15d, r14d
0x18001fd9f  shr     r15d, 1
0x18001fda2  cmp     r15d, 400h
  ... truncated ...
```
