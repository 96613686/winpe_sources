# mkvparser::ContentEncoding::ParseEncryptionEntry(__int64,__int64,mkvparser::IMkvReader *,mkvparser::ContentEncoding::ContentEncryption *)

- ea: `0x1800a649c`
- end: `0x1800a711a`
- name: `?ParseEncryptionEntry@ContentEncoding@mkvparser@@QEAAJ_J0PEAUIMkvReader@2@PEAUContentEncryption@12@@Z`
- size: `3198`
- prototype: `__int64 __usercall@<rax>(mkvparser::ContentEncoding *__hidden this@<rcx>, __int64@<rdx>, __int64@<r8>, struct mkvparser::IMkvReader *@<r9>, struct mkvparser::ContentEncoding::ContentEncryption *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x1800a3d74`

## callees

- `0x180001ff0`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180087364`
- `0x1800a39a8`
- `0x1800a5fec`
- `0x1800a649c`
- `0x1800adb74`
- `0x1800af7b0`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6575`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a67d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6872`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6907`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a69a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6a43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6ad8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6b72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6c14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6ca9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6d43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6ddd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6e72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6f07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6f9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a7074`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6575`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a67d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6872`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6907`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a69a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6a43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6ad8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6b72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6c14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6ca9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6d43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6ddd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6e72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6f07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6f9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a7074`

## pseudocode

```c
__int64 __fastcall mkvparser::ContentEncoding::ParseEncryptionEntry(
        mkvparser::ContentEncoding *this,
        struct mkvparser::IMkvReader *a2,
        __int64 a3,
        __int64 (__fastcall ***a4)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *),
        struct mkvparser::ContentEncoding::ContentEncryption *a5)
{
  struct mkvparser::ContentEncoding::ContentEncryption *v5; // rdi
  struct mkvparser::IMkvReader *v6; // rbx
  struct mkvparser::IMkvReader *v8; // r14
  __int64 v10; // rdx
  int BinaryData; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  struct mkvparser::IMkvReader *v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  void *v30; // r12
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  void *v39; // r12
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  void *v48; // r12
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  __int64 *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  __int64 *v84; // rcx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 *v90; // rcx
  CallStackTracing *v91; // rax
  struct CallStackContext *v92; // rax
  __int64 *v93; // rcx
  CallStackTracing *v94; // rax
  struct CallStackContext *v95; // rax
  __int64 *v96; // rcx
  CallStackTracing *v97; // rax
  struct CallStackContext *v98; // rax
  __int64 *v99; // rcx
  CallStackTracing *v100; // rax
  struct CallStackContext *v101; // rax
  __int64 *v102; // rcx
  CallStackTracing *v103; // rax
  struct CallStackContext *v104; // rax
  __int64 *v105; // rcx
  CallStackTracing *v106; // rax
  struct CallStackContext *v107; // rax
  __int64 *v108; // rcx
  CallStackTracing *v109; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 *v115; // rcx
  CallStackTracing *v116; // rax
  struct CallStackContext *v117; // rax
  __int64 *v118; // [rsp+20h] [rbp-30h]
  unsigned __int8 v119[8]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v120; // [rsp+38h] [rbp-18h] BYREF
  struct mkvparser::IMkvReader *v121; // [rsp+40h] [rbp-10h]
  __int64 v122; // [rsp+98h] [rbp+48h] BYREF
  struct mkvparser::IMkvReader *v123; // [rsp+A0h] [rbp+50h] BYREF

  v5 = a5;
  v6 = (struct mkvparser::IMkvReader *)((char *)a2 + a3);
  v121 = (struct mkvparser::IMkvReader *)((char *)a2 + a3);
  v8 = a2;
  v123 = a2;
  while ( (__int64)v8 < (__int64)v6 )
  {
    v120 = 0;
    *(_QWORD *)v119 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v122,
      "mkvparser::ContentEncoding::ParseEncryptionEntry",
      5198);
    BinaryData = mkvparser::ParseElementHeader(a4, &v123, v6, &v120, (__int64 *)v119);
    if ( BinaryData < 0 )
    {
      v108 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v109 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12, v13);
        CallStackTracing::s_wpInstance = v109;
        if ( v109 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v109 + 8LL))(v109, 2032) )
        {
          v108 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v108 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v108 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v108);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != BinaryData )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "mkvparser::ContentEncoding::ParseEncryptionEntry",
            5198,
            BinaryData);
      }
      if ( !g_wppLevels )
        goto LABEL_182;
      v59 = 444;
      goto LABEL_181;
    }
    v14 = v123;
    v15 = *(_QWORD *)v119;
    v122 = 0;
    switch ( v120 )
    {
      case 18401LL:
        BinaryData = mkvparser::UnserializeUInt((mkvparser *)a4, v123, *(__int64 *)v119, (__int64)&v122, v118);
        if ( BinaryData < 0 )
        {
          v60 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
            CallStackTracing::s_wpInstance = v61;
            if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
            {
              v60 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v60 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v60 + 8) )
          {
            v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
            if ( *((_DWORD *)v62 + 499) != BinaryData )
              CallStackContext::TraceFailure(v62, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5203, BinaryData);
          }
          if ( g_wppLevels )
          {
            v59 = 445;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        v19 = v122;
        *(_QWORD *)v5 = v122;
        if ( v19 != 5 )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          BinaryData = -1072875842;
          if ( *((_BYTE *)v20 + 8) )
          {
            v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v58 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v58, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5208, -1072875842);
          }
          if ( g_wppLevels )
          {
            v59 = 446;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        break;
      case 18402LL:
        operator delete(*((void **)v5 + 1));
        *((_QWORD *)v5 + 1) = 0;
        *((_QWORD *)v5 + 2) = 0;
        if ( v15 <= 0 )
        {
          v72 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v24, v25);
            CallStackTracing::s_wpInstance = v73;
            if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
            {
              v72 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v72 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          BinaryData = -1072875842;
          if ( *((_BYTE *)v72 + 8) )
          {
            v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
            if ( *((_DWORD *)v74 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v74, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5217, -1072875842);
          }
          if ( g_wppLevels )
          {
            v59 = 447;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        v26 = mkvparser::SafeArrayAlloc<char>(v23, v15);
        v30 = (void *)v26;
        if ( !v26 )
        {
          v69 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
            CallStackTracing::s_wpInstance = v70;
            if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
            {
              v69 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v69 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          BinaryData = -2147024882;
          if ( *((_BYTE *)v69 + 8) )
          {
            v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
            if ( *((_DWORD *)v71 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v71, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5222, -2147024882);
          }
          if ( g_wppLevels )
          {
            v59 = 448;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        BinaryData = mkvparser::ReadBinaryData((mkvparser *)a4, v14, v15, v26);
        if ( BinaryData < 0 )
        {
          operator delete(v30);
          v66 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
            CallStackTracing::s_wpInstance = v67;
            if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
            {
              v66 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v66 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v66 + 8) )
          {
            v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
            if ( *((_DWORD *)v68 + 499) != BinaryData )
              CallStackContext::TraceFailure(v68, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5227, BinaryData);
          }
          if ( g_wppLevels )
          {
            v59 = 449;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        *((_QWORD *)v5 + 1) = v30;
        *((_QWORD *)v5 + 2) = v15;
        break;
      case 18403LL:
        operator delete(*((void **)v5 + 3));
        *((_QWORD *)v5 + 3) = 0;
        *((_QWORD *)v5 + 4) = 0;
        if ( v15 <= 0 )
        {
          v84 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v33, v34);
            CallStackTracing::s_wpInstance = v85;
            if ( v85 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v85 + 8LL))(v85, 2032) )
            {
              v84 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v84 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          BinaryData = -1072875842;
          if ( *((_BYTE *)v84 + 8) )
          {
            v86 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v84);
            if ( *((_DWORD *)v86 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v86, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5239, -1072875842);
          }
          if ( g_wppLevels )
          {
            v59 = 450;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        v35 = mkvparser::SafeArrayAlloc<char>(v32, v15);
        v39 = (void *)v35;
        if ( !v35 )
        {
          v81 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
            CallStackTracing::s_wpInstance = v82;
            if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
            {
              v81 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v81 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          BinaryData = -2147024882;
          if ( *((_BYTE *)v81 + 8) )
          {
            v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
            if ( *((_DWORD *)v83 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v83, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5244, -2147024882);
          }
          if ( g_wppLevels )
          {
            v59 = 451;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        BinaryData = mkvparser::ReadBinaryData((mkvparser *)a4, v14, v15, v35);
        if ( BinaryData < 0 )
        {
          operator delete(v39);
          v78 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v75, v76, v77);
            CallStackTracing::s_wpInstance = v79;
            if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
            {
              v78 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v78 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v78 + 8) )
          {
            v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
            if ( *((_DWORD *)v80 + 499) != BinaryData )
              CallStackContext::TraceFailure(v80, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5249, BinaryData);
          }
          if ( g_wppLevels )
          {
            v59 = 452;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        *((_QWORD *)v5 + 3) = v39;
        *((_QWORD *)v5 + 4) = v15;
        break;
      case 18404LL:
        operator delete(*((void **)v5 + 5));
        *((_QWORD *)v5 + 5) = 0;
        *((_QWORD *)v5 + 6) = 0;
        if ( v15 <= 0 )
        {
          v96 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v97 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v42, v43);
            CallStackTracing::s_wpInstance = v97;
            if ( v97 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v97 + 8LL))(v97, 2032) )
            {
              v96 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v96 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          BinaryData = -1072875842;
          if ( *((_BYTE *)v96 + 8) )
          {
            v98 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v96);
            if ( *((_DWORD *)v98 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v98, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5261, -1072875842);
          }
          if ( g_wppLevels )
          {
            v59 = 453;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        v44 = mkvparser::SafeArrayAlloc<char>(v41, v15);
        v48 = (void *)v44;
        if ( !v44 )
        {
          v93 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v94 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
            CallStackTracing::s_wpInstance = v94;
            if ( v94 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v94 + 8LL))(v94, 2032) )
            {
              v93 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v93 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          BinaryData = -2147024882;
          if ( *((_BYTE *)v93 + 8) )
          {
            v95 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v93);
            if ( *((_DWORD *)v95 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v95, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5266, -2147024882);
          }
          if ( g_wppLevels )
          {
            v59 = 454;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        BinaryData = mkvparser::ReadBinaryData((mkvparser *)a4, v14, v15, v44);
        if ( BinaryData < 0 )
        {
          operator delete(v48);
          v90 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v87, v88, v89);
            CallStackTracing::s_wpInstance = v91;
            if ( v91 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
            {
              v90 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v90 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v90 + 8) )
          {
            v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
            if ( *((_DWORD *)v92 + 499) != BinaryData )
              CallStackContext::TraceFailure(v92, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5271, BinaryData);
          }
          if ( g_wppLevels )
          {
            v59 = 455;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        *((_QWORD *)v5 + 5) = v48;
        *((_QWORD *)v5 + 6) = v15;
        break;
      case 18405LL:
        BinaryData = mkvparser::UnserializeUInt((mkvparser *)a4, v123, *(__int64 *)v119, (__int64)&v122, v118);
        if ( BinaryData < 0 )
        {
          v99 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v100 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
            CallStackTracing::s_wpInstance = v100;
            if ( v100
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v100 + 8LL))(v100, 2032) )
            {
              v99 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v99 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v99 + 8) )
          {
            v101 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v99);
            if ( *((_DWORD *)v101 + 499) != BinaryData )
              CallStackContext::TraceFailure(v101, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5277, BinaryData);
          }
          if ( g_wppLevels )
          {
            v59 = 456;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        *((_QWORD *)v5 + 7) = v122;
        break;
      case 18406LL:
        BinaryData = mkvparser::UnserializeUInt((mkvparser *)a4, v123, *(__int64 *)v119, (__int64)&v122, v118);
        if ( BinaryData < 0 )
        {
          v102 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v103 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
            CallStackTracing::s_wpInstance = v103;
            if ( v103
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v103 + 8LL))(v103, 2032) )
            {
              v102 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v102 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v102 + 8) )
          {
            v104 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v102);
            if ( *((_DWORD *)v104 + 499) != BinaryData )
              CallStackContext::TraceFailure(v104, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5281, BinaryData);
          }
          if ( g_wppLevels )
          {
            v59 = 457;
            goto LABEL_181;
          }
          goto LABEL_182;
        }
        *((_QWORD *)v5 + 8) = v122;
        break;
      case 18407LL:
        BinaryData = mkvparser::ContentEncoding::ParseContentEncAESSettingsEntry(
                       this,
                       (__int64)v123,
                       *(__int64 *)v119,
                       (struct mkvparser::IMkvReader *)a4,
                       (struct mkvparser::ContentEncoding::ContentEncryption *)((char *)v5 + 72));
        if ( BinaryData < 0 )
        {
          v105 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v106 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
            CallStackTracing::s_wpInstance = v106;
            if ( v106
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v106 + 8LL))(v106, 2032) )
            {
              v105 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v105 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v105 + 8) )
          {
            v107 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v105);
            if ( *((_DWORD *)v107 + 499) != BinaryData )
              CallStackContext::TraceFailure(v107, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5285, BinaryData);
          }
          if ( g_wppLevels )
          {
            v59 = 458;
            goto LABEL_181;
          }
LABEL_182:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v122);
          return (unsigned int)BinaryData;
        }
        break;
    }
    v8 = (struct mkvparser::IMkvReader *)((char *)v14 + v15);
    v123 = v8;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v122);
    v6 = v121;
  }
  if ( v8 != v6 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v122,
      "mkvparser::ContentEncoding::ParseEncryptionEntry",
      5293);
    v115 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v116 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v112, v113, v114);
      CallStackTracing::s_wpInstance = v116;
      if ( v116 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v116 + 8LL))(v116, 2032) )
      {
        v115 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v115 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    BinaryData = -1072875842;
    if ( *((_BYTE *)v115 + 8) )
    {
      v117 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v115);
      if ( *((_DWORD *)v117 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v117, "mkvparser::ContentEncoding::ParseEncryptionEntry", 5293, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_182;
    v59 = 459;
LABEL_181:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v59,
      WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids,
      this,
      BinaryData);
    goto LABEL_182;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a649c  mov     [rsp-38h+arg_0], rbx
0x1800a64a1  push    rbp
0x1800a64a2  push    rsi
0x1800a64a3  push    rdi
0x1800a64a4  push    r12
0x1800a64a6  push    r13
0x1800a64a8  push    r14
0x1800a64aa  push    r15
0x1800a64ac  mov     rbp, rsp
0x1800a64af  sub     rsp, 50h
0x1800a64b3  mov     rdi, [rbp+arg_20]
0x1800a64b7  lea     rbx, [rdx+r8]
0x1800a64bb  mov     [rbp+var_10], rbx
0x1800a64bf  mov     r13, r9
0x1800a64c2  mov     r14, rdx
0x1800a64c5  mov     [rbp+arg_10], rdx
0x1800a64c9  mov     r15, rcx
0x1800a64cc  xor     r12d, r12d
0x1800a64cf  cmp     r14, rbx
0x1800a64d2  jge     loc_1800A704A
0x1800a64d8  mov     r8d, 144Eh; int
0x1800a64de  mov     [rbp+var_18], r12
0x1800a64e2  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a64e9  mov     qword ptr [rbp+var_20], r12
0x1800a64ed  lea     rcx, [rbp+arg_8]; this
0x1800a64f1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a64f6  lea     rax, [rbp+var_20]
0x1800a64fa  mov     r8, rbx; __int64 *
0x1800a64fd  lea     r9, [rbp+var_18]; __int64
0x1800a6501  mov     [rsp+50h+var_30], rax; __int64 *
0x1800a6506  lea     rdx, [rbp+arg_10]; struct mkvparser::IMkvReader *
0x1800a650a  mov     rcx, r13; this
0x1800a650d  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x1800a6512  mov     ebx, eax
0x1800a6514  test    eax, eax
0x1800a6516  js      loc_1800A6F90
0x1800a651c  mov     rax, [rbp+var_18]
0x1800a6520  mov     r14, [rbp+arg_10]
0x1800a6524  mov     rsi, qword ptr [rbp+var_20]
0x1800a6528  mov     [rbp+arg_8], r12
0x1800a652c  cmp     rax, 47E1h
0x1800a6532  jnz     loc_1800A65B9
0x1800a6538  lea     r9, [rbp+arg_8]; __int64
0x1800a653c  mov     r8, rsi; __int64
0x1800a653f  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a6542  mov     rcx, r13; this
0x1800a6545  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800a654a  mov     ebx, eax
0x1800a654c  test    eax, eax
0x1800a654e  js      loc_1800A67C9
0x1800a6554  mov     rax, [rbp+arg_8]
0x1800a6558  mov     [rdi], rax
0x1800a655b  cmp     rax, 5
0x1800a655f  jz      loc_1800A675B
0x1800a6565  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a656c  test    rcx, rcx
0x1800a656f  jnz     loc_1800A6782
0x1800a6575  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a657c  nop     dword ptr [rax+rax+00h]
0x1800a6581  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6588  mov     rcx, rax
0x1800a658b  test    rax, rax
0x1800a658e  jz      loc_1800A6774
0x1800a6594  mov     rax, [rax]
0x1800a6597  mov     edx, 7F0h
0x1800a659c  mov     rax, [rax+8]
0x1800a65a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a65a5  test    eax, eax
0x1800a65a7  jz      loc_1800A6774
0x1800a65ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a65b4  jmp     loc_1800A6782
0x1800a65b9  cmp     rax, 47E2h
0x1800a65bf  jnz     short loc_1800A6617
0x1800a65c1  mov     rcx, [rdi+8]; Block
0x1800a65c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a65ca  mov     [rdi+8], r12
0x1800a65ce  mov     [rdi+10h], r12
0x1800a65d2  test    rsi, rsi
0x1800a65d5  jle     loc_1800A6995
0x1800a65db  mov     rdx, rsi
0x1800a65de  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x1800a65e3  mov     r12, rax
0x1800a65e6  test    rax, rax
0x1800a65e9  jz      loc_1800A68FB
0x1800a65ef  mov     r9, rax; __int64
0x1800a65f2  mov     r8, rsi; __int64
0x1800a65f5  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a65f8  mov     rcx, r13; this
0x1800a65fb  call    ?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z; mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)
0x1800a6600  mov     ebx, eax
0x1800a6602  test    eax, eax
0x1800a6604  js      loc_1800A685E
0x1800a660a  mov     [rdi+8], r12
0x1800a660e  mov     [rdi+10h], rsi
0x1800a6612  jmp     loc_1800A66CB
0x1800a6617  cmp     rax, 47E3h
0x1800a661d  jnz     short loc_1800A6672
0x1800a661f  mov     rcx, [rdi+18h]; Block
0x1800a6623  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a6628  mov     [rdi+18h], r12
0x1800a662c  mov     [rdi+20h], r12
0x1800a6630  test    rsi, rsi
0x1800a6633  jle     loc_1800A6B66
0x1800a6639  mov     rdx, rsi
0x1800a663c  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x1800a6641  mov     r12, rax
0x1800a6644  test    rax, rax
0x1800a6647  jz      loc_1800A6ACC
0x1800a664d  mov     r9, rax; __int64
0x1800a6650  mov     r8, rsi; __int64
0x1800a6653  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a6656  mov     rcx, r13; this
0x1800a6659  call    ?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z; mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)
0x1800a665e  mov     ebx, eax
0x1800a6660  test    eax, eax
0x1800a6662  js      loc_1800A6A2F
0x1800a6668  mov     [rdi+18h], r12
0x1800a666c  mov     [rdi+20h], rsi
0x1800a6670  jmp     short loc_1800A66CB
0x1800a6672  cmp     rax, 47E4h
0x1800a6678  jnz     short loc_1800A66D3
0x1800a667a  mov     rcx, [rdi+28h]; Block
0x1800a667e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a6683  mov     [rdi+28h], r12
0x1800a6687  mov     [rdi+30h], r12
0x1800a668b  test    rsi, rsi
0x1800a668e  jle     loc_1800A6D37
0x1800a6694  mov     rdx, rsi
0x1800a6697  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x1800a669c  mov     r12, rax
0x1800a669f  test    rax, rax
0x1800a66a2  jz      loc_1800A6C9D
0x1800a66a8  mov     r9, rax; __int64
0x1800a66ab  mov     r8, rsi; __int64
0x1800a66ae  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a66b1  mov     rcx, r13; this
0x1800a66b4  call    ?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z; mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)
0x1800a66b9  mov     ebx, eax
0x1800a66bb  test    eax, eax
0x1800a66bd  js      loc_1800A6C00
0x1800a66c3  mov     [rdi+28h], r12
0x1800a66c7  mov     [rdi+30h], rsi
0x1800a66cb  xor     r12d, r12d
0x1800a66ce  jmp     loc_1800A675B
0x1800a66d3  cmp     rax, 47E5h
0x1800a66d9  jnz     short loc_1800A6701
0x1800a66db  lea     r9, [rbp+arg_8]; __int64
0x1800a66df  mov     r8, rsi; __int64
0x1800a66e2  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a66e5  mov     rcx, r13; this
0x1800a66e8  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800a66ed  mov     ebx, eax
0x1800a66ef  test    eax, eax
0x1800a66f1  js      loc_1800A6DD1
0x1800a66f7  mov     rax, [rbp+arg_8]
0x1800a66fb  mov     [rdi+38h], rax
0x1800a66ff  jmp     short loc_1800A675B
0x1800a6701  cmp     rax, 47E6h
0x1800a6707  jnz     short loc_1800A672F
0x1800a6709  lea     r9, [rbp+arg_8]; __int64
0x1800a670d  mov     r8, rsi; __int64
0x1800a6710  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a6713  mov     rcx, r13; this
0x1800a6716  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800a671b  mov     ebx, eax
0x1800a671d  test    eax, eax
0x1800a671f  js      loc_1800A6E66
0x1800a6725  mov     rax, [rbp+arg_8]
0x1800a6729  mov     [rdi+40h], rax
0x1800a672d  jmp     short loc_1800A675B
0x1800a672f  cmp     rax, 47E7h
0x1800a6735  jnz     short loc_1800A675B
0x1800a6737  lea     rax, [rdi+48h]
0x1800a673b  mov     r9, r13; struct mkvparser::IMkvReader *
0x1800a673e  mov     r8, rsi; __int64
0x1800a6741  mov     [rsp+50h+var_30], rax; struct mkvparser::ContentEncoding::ContentEncAESSettings *
0x1800a6746  mov     rdx, r14; __int64
0x1800a6749  mov     rcx, r15; this
0x1800a674c  call    ?ParseContentEncAESSettingsEntry@ContentEncoding@mkvparser@@QEAAJ_J0PEAUIMkvReader@2@PEAUContentEncAESSettings@12@@Z; mkvparser::ContentEncoding::ParseContentEncAESSettingsEntry(__int64,__int64,mkvparser::IMkvReader *,mkvparser::ContentEncoding::ContentEncAESSettings *)
0x1800a6751  mov     ebx, eax
0x1800a6753  test    eax, eax
0x1800a6755  js      loc_1800A6EFB
0x1800a675b  add     r14, rsi
0x1800a675e  lea     rcx, [rbp+arg_8]; this
0x1800a6762  mov     [rbp+arg_10], r14
0x1800a6766  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a676b  mov     rbx, [rbp+var_10]
0x1800a676f  jmp     loc_1800A64CF
0x1800a6774  lea     rcx, qword_1800DBF70; this
0x1800a677b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6782  mov     ebx, 0C00D36BEh
0x1800a6787  cmp     [rcx+8], r12b
0x1800a678b  jz      short loc_1800A67B2
0x1800a678d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6792  cmp     [rax+7CCh], ebx
0x1800a6798  jz      short loc_1800A67B2
0x1800a679a  mov     r9d, ebx; int
0x1800a679d  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a67a4  mov     r8d, 1458h; int
0x1800a67aa  mov     rcx, rax; this
0x1800a67ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a67b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a67b9  jb      loc_1800A703A
0x1800a67bf  mov     edx, 1BEh
0x1800a67c4  jmp     loc_1800A701C
0x1800a67c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a67d0  test    rcx, rcx
0x1800a67d3  jnz     short loc_1800A681C
0x1800a67d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a67dc  nop     dword ptr [rax+rax+00h]
0x1800a67e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a67e8  mov     rcx, rax
0x1800a67eb  test    rax, rax
0x1800a67ee  jz      short loc_1800A680E
0x1800a67f0  mov     rax, [rax]
0x1800a67f3  mov     edx, 7F0h
0x1800a67f8  mov     rax, [rax+8]
0x1800a67fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6801  test    eax, eax
0x1800a6803  jz      short loc_1800A680E
0x1800a6805  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a680c  jmp     short loc_1800A681C
0x1800a680e  lea     rcx, qword_1800DBF70; this
0x1800a6815  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a681c  cmp     [rcx+8], r12b
0x1800a6820  jz      short loc_1800A6847
0x1800a6822  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6827  cmp     [rax+7CCh], ebx
0x1800a682d  jz      short loc_1800A6847
0x1800a682f  mov     r9d, ebx; int
0x1800a6832  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a6839  mov     r8d, 1453h; int
0x1800a683f  mov     rcx, rax; this
0x1800a6842  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6847  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a684e  jb      loc_1800A703A
0x1800a6854  mov     edx, 1BDh
0x1800a6859  jmp     loc_1800A701C
0x1800a685e  mov     rcx, r12; Block
0x1800a6861  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a6866  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a686d  test    rcx, rcx
0x1800a6870  jnz     short loc_1800A68B9
0x1800a6872  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a6879  nop     dword ptr [rax+rax+00h]
0x1800a687e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6885  mov     rcx, rax
0x1800a6888  test    rax, rax
0x1800a688b  jz      short loc_1800A68AB
0x1800a688d  mov     rax, [rax]
0x1800a6890  mov     edx, 7F0h
0x1800a6895  mov     rax, [rax+8]
0x1800a6899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a689e  test    eax, eax
0x1800a68a0  jz      short loc_1800A68AB
0x1800a68a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a68a9  jmp     short loc_1800A68B9
0x1800a68ab  lea     rcx, qword_1800DBF70; this
0x1800a68b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a68b9  cmp     byte ptr [rcx+8], 0
0x1800a68bd  jz      short loc_1800A68E4
0x1800a68bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a68c4  cmp     [rax+7CCh], ebx
0x1800a68ca  jz      short loc_1800A68E4
0x1800a68cc  mov     r9d, ebx; int
0x1800a68cf  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a68d6  mov     r8d, 146Bh; int
0x1800a68dc  mov     rcx, rax; this
0x1800a68df  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a68e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a68eb  jb      loc_1800A703A
0x1800a68f1  mov     edx, 1C1h
0x1800a68f6  jmp     loc_1800A701C
0x1800a68fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6902  test    rcx, rcx
0x1800a6905  jnz     short loc_1800A694E
0x1800a6907  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a690e  nop     dword ptr [rax+rax+00h]
0x1800a6913  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a691a  mov     rcx, rax
0x1800a691d  test    rax, rax
0x1800a6920  jz      short loc_1800A6940
0x1800a6922  mov     rax, [rax]
0x1800a6925  mov     edx, 7F0h
0x1800a692a  mov     rax, [rax+8]
0x1800a692e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6933  test    eax, eax
0x1800a6935  jz      short loc_1800A6940
0x1800a6937  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a693e  jmp     short loc_1800A694E
0x1800a6940  lea     rcx, qword_1800DBF70; this
0x1800a6947  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a694e  cmp     byte ptr [rcx+8], 0
0x1800a6952  mov     ebx, 8007000Eh
0x1800a6957  jz      short loc_1800A697E
0x1800a6959  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a695e  cmp     [rax+7CCh], ebx
0x1800a6964  jz      short loc_1800A697E
0x1800a6966  mov     r9d, ebx; int
0x1800a6969  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
  ... truncated ...
```
