# mkvparser::ContentEncoding::ParseEncryptionEntry(__int64,__int64,mkvparser::IMkvReader *,mkvparser::ContentEncoding::ContentEncryption *)

- ea: `0x1800a1b98`
- end: `0x1800a27b1`
- name: `?ParseEncryptionEntry@ContentEncoding@mkvparser@@QEAAJ_J0PEAUIMkvReader@2@PEAUContentEncryption@12@@Z`
- size: `3097`
- prototype: `__int64 __usercall@<rax>(mkvparser::ContentEncoding *__hidden this@<rcx>, __int64@<rdx>, __int64@<r8>, struct mkvparser::IMkvReader *@<r9>, struct mkvparser::ContentEncoding::ContentEncryption *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x18009f58c`

## callees

- `0x180001fd0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x18008385c`
- `0x18009f1d8`
- `0x1800a1710`
- `0x1800a1b98`
- `0x1800a8f04`
- `0x1800aaa7c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1c6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1ec7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1f5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1fed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2081`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a211d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a21ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2240`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a22dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a236b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a23ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2493`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2522`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a25b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2712`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1c6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1ec7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1f5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1fed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2081`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a211d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a21ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2240`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a22dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a236b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a23ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2493`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2522`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a25b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a2712`

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
  void *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  void *v30; // r12
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  void *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  void *v39; // r12
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  void *v44; // rax
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
          v108 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v60 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v20 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v72 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v30 = v26;
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
              v69 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        BinaryData = mkvparser::ReadBinaryData((mkvparser *)a4, v14, v15, (__int64)v26);
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
              v66 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v84 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v39 = v35;
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
              v81 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        BinaryData = mkvparser::ReadBinaryData((mkvparser *)a4, v14, v15, (__int64)v35);
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
              v78 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v96 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v48 = v44;
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
              v93 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        BinaryData = mkvparser::ReadBinaryData((mkvparser *)a4, v14, v15, (__int64)v44);
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
              v90 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v99 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v102 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v105 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v115 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800a1b98  mov     [rsp-38h+arg_0], rbx
0x1800a1b9d  push    rbp
0x1800a1b9e  push    rsi
0x1800a1b9f  push    rdi
0x1800a1ba0  push    r12
0x1800a1ba2  push    r13
0x1800a1ba4  push    r14
0x1800a1ba6  push    r15
0x1800a1ba8  mov     rbp, rsp
0x1800a1bab  sub     rsp, 50h
0x1800a1baf  mov     rdi, [rbp+arg_20]
0x1800a1bb3  lea     rbx, [rdx+r8]
0x1800a1bb7  mov     [rbp+var_10], rbx
0x1800a1bbb  mov     r13, r9
0x1800a1bbe  mov     r14, rdx
0x1800a1bc1  mov     [rbp+arg_10], rdx
0x1800a1bc5  mov     r15, rcx
0x1800a1bc8  xor     r12d, r12d
0x1800a1bcb  cmp     r14, rbx
0x1800a1bce  jge     loc_1800A26E8
0x1800a1bd4  mov     r8d, 144Eh; int
0x1800a1bda  mov     [rbp+var_18], r12
0x1800a1bde  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a1be5  mov     qword ptr [rbp+var_20], r12
0x1800a1be9  lea     rcx, [rbp+arg_8]; this
0x1800a1bed  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a1bf2  lea     rax, [rbp+var_20]
0x1800a1bf6  mov     r8, rbx; __int64 *
0x1800a1bf9  lea     r9, [rbp+var_18]; __int64
0x1800a1bfd  mov     [rsp+50h+var_30], rax; __int64 *
0x1800a1c02  lea     rdx, [rbp+arg_10]; struct mkvparser::IMkvReader *
0x1800a1c06  mov     rcx, r13; this
0x1800a1c09  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x1800a1c0e  mov     ebx, eax
0x1800a1c10  test    eax, eax
0x1800a1c12  js      loc_1800A2634
0x1800a1c18  mov     rax, [rbp+var_18]
0x1800a1c1c  mov     r14, [rbp+arg_10]
0x1800a1c20  mov     rsi, qword ptr [rbp+var_20]
0x1800a1c24  mov     [rbp+arg_8], r12
0x1800a1c28  cmp     rax, 47E1h
0x1800a1c2e  jnz     short loc_1800A1CAB
0x1800a1c30  lea     r9, [rbp+arg_8]; __int64
0x1800a1c34  mov     r8, rsi; __int64
0x1800a1c37  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a1c3a  mov     rcx, r13; this
0x1800a1c3d  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800a1c42  mov     ebx, eax
0x1800a1c44  test    eax, eax
0x1800a1c46  js      loc_1800A1EBB
0x1800a1c4c  mov     rax, [rbp+arg_8]
0x1800a1c50  mov     [rdi], rax
0x1800a1c53  cmp     rax, 5
0x1800a1c57  jz      loc_1800A1E4D
0x1800a1c5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1c64  test    rcx, rcx
0x1800a1c67  jnz     loc_1800A1E74
0x1800a1c6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1c73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1c7a  mov     rcx, rax
0x1800a1c7d  test    rax, rax
0x1800a1c80  jz      loc_1800A1E66
0x1800a1c86  mov     rax, [rax]
0x1800a1c89  mov     edx, 7F0h
0x1800a1c8e  mov     rax, [rax+8]
0x1800a1c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c97  test    eax, eax
0x1800a1c99  jz      loc_1800A1E66
0x1800a1c9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ca6  jmp     loc_1800A1E74
0x1800a1cab  cmp     rax, 47E2h
0x1800a1cb1  jnz     short loc_1800A1D09
0x1800a1cb3  mov     rcx, [rdi+8]; Block
0x1800a1cb7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a1cbc  mov     [rdi+8], r12
0x1800a1cc0  mov     [rdi+10h], r12
0x1800a1cc4  test    rsi, rsi
0x1800a1cc7  jle     loc_1800A2075
0x1800a1ccd  mov     rdx, rsi
0x1800a1cd0  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x1800a1cd5  mov     r12, rax
0x1800a1cd8  test    rax, rax
0x1800a1cdb  jz      loc_1800A1FE1
0x1800a1ce1  mov     r9, rax; __int64
0x1800a1ce4  mov     r8, rsi; __int64
0x1800a1ce7  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a1cea  mov     rcx, r13; this
0x1800a1ced  call    ?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z; mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)
0x1800a1cf2  mov     ebx, eax
0x1800a1cf4  test    eax, eax
0x1800a1cf6  js      loc_1800A1F4A
0x1800a1cfc  mov     [rdi+8], r12
0x1800a1d00  mov     [rdi+10h], rsi
0x1800a1d04  jmp     loc_1800A1DBD
0x1800a1d09  cmp     rax, 47E3h
0x1800a1d0f  jnz     short loc_1800A1D64
0x1800a1d11  mov     rcx, [rdi+18h]; Block
0x1800a1d15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a1d1a  mov     [rdi+18h], r12
0x1800a1d1e  mov     [rdi+20h], r12
0x1800a1d22  test    rsi, rsi
0x1800a1d25  jle     loc_1800A2234
0x1800a1d2b  mov     rdx, rsi
0x1800a1d2e  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x1800a1d33  mov     r12, rax
0x1800a1d36  test    rax, rax
0x1800a1d39  jz      loc_1800A21A0
0x1800a1d3f  mov     r9, rax; __int64
0x1800a1d42  mov     r8, rsi; __int64
0x1800a1d45  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a1d48  mov     rcx, r13; this
0x1800a1d4b  call    ?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z; mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)
0x1800a1d50  mov     ebx, eax
0x1800a1d52  test    eax, eax
0x1800a1d54  js      loc_1800A2109
0x1800a1d5a  mov     [rdi+18h], r12
0x1800a1d5e  mov     [rdi+20h], rsi
0x1800a1d62  jmp     short loc_1800A1DBD
0x1800a1d64  cmp     rax, 47E4h
0x1800a1d6a  jnz     short loc_1800A1DC5
0x1800a1d6c  mov     rcx, [rdi+28h]; Block
0x1800a1d70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a1d75  mov     [rdi+28h], r12
0x1800a1d79  mov     [rdi+30h], r12
0x1800a1d7d  test    rsi, rsi
0x1800a1d80  jle     loc_1800A23F3
0x1800a1d86  mov     rdx, rsi
0x1800a1d89  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x1800a1d8e  mov     r12, rax
0x1800a1d91  test    rax, rax
0x1800a1d94  jz      loc_1800A235F
0x1800a1d9a  mov     r9, rax; __int64
0x1800a1d9d  mov     r8, rsi; __int64
0x1800a1da0  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a1da3  mov     rcx, r13; this
0x1800a1da6  call    ?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z; mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)
0x1800a1dab  mov     ebx, eax
0x1800a1dad  test    eax, eax
0x1800a1daf  js      loc_1800A22C8
0x1800a1db5  mov     [rdi+28h], r12
0x1800a1db9  mov     [rdi+30h], rsi
0x1800a1dbd  xor     r12d, r12d
0x1800a1dc0  jmp     loc_1800A1E4D
0x1800a1dc5  cmp     rax, 47E5h
0x1800a1dcb  jnz     short loc_1800A1DF3
0x1800a1dcd  lea     r9, [rbp+arg_8]; __int64
0x1800a1dd1  mov     r8, rsi; __int64
0x1800a1dd4  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a1dd7  mov     rcx, r13; this
0x1800a1dda  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800a1ddf  mov     ebx, eax
0x1800a1de1  test    eax, eax
0x1800a1de3  js      loc_1800A2487
0x1800a1de9  mov     rax, [rbp+arg_8]
0x1800a1ded  mov     [rdi+38h], rax
0x1800a1df1  jmp     short loc_1800A1E4D
0x1800a1df3  cmp     rax, 47E6h
0x1800a1df9  jnz     short loc_1800A1E21
0x1800a1dfb  lea     r9, [rbp+arg_8]; __int64
0x1800a1dff  mov     r8, rsi; __int64
0x1800a1e02  mov     rdx, r14; struct mkvparser::IMkvReader *
0x1800a1e05  mov     rcx, r13; this
0x1800a1e08  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800a1e0d  mov     ebx, eax
0x1800a1e0f  test    eax, eax
0x1800a1e11  js      loc_1800A2516
0x1800a1e17  mov     rax, [rbp+arg_8]
0x1800a1e1b  mov     [rdi+40h], rax
0x1800a1e1f  jmp     short loc_1800A1E4D
0x1800a1e21  cmp     rax, 47E7h
0x1800a1e27  jnz     short loc_1800A1E4D
0x1800a1e29  lea     rax, [rdi+48h]
0x1800a1e2d  mov     r9, r13; struct mkvparser::IMkvReader *
0x1800a1e30  mov     r8, rsi; __int64
0x1800a1e33  mov     [rsp+50h+var_30], rax; struct mkvparser::ContentEncoding::ContentEncAESSettings *
0x1800a1e38  mov     rdx, r14; __int64
0x1800a1e3b  mov     rcx, r15; this
0x1800a1e3e  call    ?ParseContentEncAESSettingsEntry@ContentEncoding@mkvparser@@QEAAJ_J0PEAUIMkvReader@2@PEAUContentEncAESSettings@12@@Z; mkvparser::ContentEncoding::ParseContentEncAESSettingsEntry(__int64,__int64,mkvparser::IMkvReader *,mkvparser::ContentEncoding::ContentEncAESSettings *)
0x1800a1e43  mov     ebx, eax
0x1800a1e45  test    eax, eax
0x1800a1e47  js      loc_1800A25A5
0x1800a1e4d  add     r14, rsi
0x1800a1e50  lea     rcx, [rbp+arg_8]; this
0x1800a1e54  mov     [rbp+arg_10], r14
0x1800a1e58  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a1e5d  mov     rbx, [rbp+var_10]
0x1800a1e61  jmp     loc_1800A1BCB
0x1800a1e66  lea     rcx, qword_1800D6F70; this
0x1800a1e6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1e74  mov     ebx, 0C00D36BEh
0x1800a1e79  cmp     [rcx+8], r12b
0x1800a1e7d  jz      short loc_1800A1EA4
0x1800a1e7f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1e84  cmp     [rax+7CCh], ebx
0x1800a1e8a  jz      short loc_1800A1EA4
0x1800a1e8c  mov     r9d, ebx; int
0x1800a1e8f  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a1e96  mov     r8d, 1458h; int
0x1800a1e9c  mov     rcx, rax; this
0x1800a1e9f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1ea4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a1eab  jb      loc_1800A26D8
0x1800a1eb1  mov     edx, 1BEh
0x1800a1eb6  jmp     loc_1800A26BA
0x1800a1ebb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ec2  test    rcx, rcx
0x1800a1ec5  jnz     short loc_1800A1F08
0x1800a1ec7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1ecd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ed4  mov     rcx, rax
0x1800a1ed7  test    rax, rax
0x1800a1eda  jz      short loc_1800A1EFA
0x1800a1edc  mov     rax, [rax]
0x1800a1edf  mov     edx, 7F0h
0x1800a1ee4  mov     rax, [rax+8]
0x1800a1ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1eed  test    eax, eax
0x1800a1eef  jz      short loc_1800A1EFA
0x1800a1ef1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ef8  jmp     short loc_1800A1F08
0x1800a1efa  lea     rcx, qword_1800D6F70; this
0x1800a1f01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1f08  cmp     [rcx+8], r12b
0x1800a1f0c  jz      short loc_1800A1F33
0x1800a1f0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1f13  cmp     [rax+7CCh], ebx
0x1800a1f19  jz      short loc_1800A1F33
0x1800a1f1b  mov     r9d, ebx; int
0x1800a1f1e  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a1f25  mov     r8d, 1453h; int
0x1800a1f2b  mov     rcx, rax; this
0x1800a1f2e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1f33  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a1f3a  jb      loc_1800A26D8
0x1800a1f40  mov     edx, 1BDh
0x1800a1f45  jmp     loc_1800A26BA
0x1800a1f4a  mov     rcx, r12; Block
0x1800a1f4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a1f52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1f59  test    rcx, rcx
0x1800a1f5c  jnz     short loc_1800A1F9F
0x1800a1f5e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1f64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1f6b  mov     rcx, rax
0x1800a1f6e  test    rax, rax
0x1800a1f71  jz      short loc_1800A1F91
0x1800a1f73  mov     rax, [rax]
0x1800a1f76  mov     edx, 7F0h
0x1800a1f7b  mov     rax, [rax+8]
0x1800a1f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f84  test    eax, eax
0x1800a1f86  jz      short loc_1800A1F91
0x1800a1f88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1f8f  jmp     short loc_1800A1F9F
0x1800a1f91  lea     rcx, qword_1800D6F70; this
0x1800a1f98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1f9f  cmp     byte ptr [rcx+8], 0
0x1800a1fa3  jz      short loc_1800A1FCA
0x1800a1fa5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1faa  cmp     [rax+7CCh], ebx
0x1800a1fb0  jz      short loc_1800A1FCA
0x1800a1fb2  mov     r9d, ebx; int
0x1800a1fb5  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a1fbc  mov     r8d, 146Bh; int
0x1800a1fc2  mov     rcx, rax; this
0x1800a1fc5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1fca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a1fd1  jb      loc_1800A26D8
0x1800a1fd7  mov     edx, 1C1h
0x1800a1fdc  jmp     loc_1800A26BA
0x1800a1fe1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1fe8  test    rcx, rcx
0x1800a1feb  jnz     short loc_1800A202E
0x1800a1fed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1ff3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ffa  mov     rcx, rax
0x1800a1ffd  test    rax, rax
0x1800a2000  jz      short loc_1800A2020
0x1800a2002  mov     rax, [rax]
0x1800a2005  mov     edx, 7F0h
0x1800a200a  mov     rax, [rax+8]
0x1800a200e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2013  test    eax, eax
0x1800a2015  jz      short loc_1800A2020
0x1800a2017  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a201e  jmp     short loc_1800A202E
0x1800a2020  lea     rcx, qword_1800D6F70; this
0x1800a2027  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a202e  cmp     byte ptr [rcx+8], 0
0x1800a2032  mov     ebx, 8007000Eh
0x1800a2037  jz      short loc_1800A205E
0x1800a2039  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a203e  cmp     [rax+7CCh], ebx
0x1800a2044  jz      short loc_1800A205E
0x1800a2046  mov     r9d, ebx; int
0x1800a2049  lea     rdx, aMkvparserConte; "mkvparser::ContentEncoding::ParseEncryp"...
0x1800a2050  mov     r8d, 1466h; int
0x1800a2056  mov     rcx, rax; this
0x1800a2059  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a205e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
