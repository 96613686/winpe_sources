# MkvMfSourceLib::CreateAndAddChapterCue(mkvparser::Chapters::Atom const *,mkvparser::Chapters::Display const *,IMFTimedTextTrack *,IMFTimedTextCueBuilder *)

- ea: `0x18003ce90`
- end: `0x18003d8b5`
- name: `?CreateAndAddChapterCue@MkvMfSourceLib@@YAJPEBVAtom@Chapters@mkvparser@@PEBVDisplay@34@PEAUIMFTimedTextTrack@@PEAUIMFTimedTextCueBuilder@@@Z`
- size: `2597`
- prototype: `__int64 __fastcall(MkvMfSourceLib *__hidden this, const struct mkvparser::Chapters::Atom *, const struct mkvparser::Chapters::Display *, struct IMFTimedTextTrack *, struct IMFTimedTextCueBuilder *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003d8bc`

## callees

- `0x180001ff0`
- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18003b90c`
- `0x18003b9a0`
- `0x18003ce90`
- `0x18003dea8`
- `0x1800744d8`
- `0x18008867c`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003cf46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d00b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d0d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d1a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d28b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d37f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d464`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d546`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d62a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d6f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d7a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003cf46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d00b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d0d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d1a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d28b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d37f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d464`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d546`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d62a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d6f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d7a5`

## string_xrefs

- `0x18003cef2`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003cfa6`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d06e`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d13b`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d20f`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d2ee`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d3e2`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d4cb`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d5a9`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d68d`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d755`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003d808`: `MkvMfSourceLib::CreateAndAddChapterCue`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall MkvMfSourceLib::CreateAndAddChapterCue(
        MkvMfSourceLib *this,
        LPCCH *a2,
        const struct mkvparser::Chapters::Display *a3,
        struct IMFTimedTextTrack *a4)
{
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rdi
  const char *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v31)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rdx
  int v42; // edi
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  const char *v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, _QWORD); // rbx
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 (__fastcall *v64)(struct IMFTimedTextTrack *, _QWORD, __int64, __int64 *); // rdi
  __int64 v65; // rbx
  unsigned int v66; // eax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 (__fastcall *v73)(const struct mkvparser::Chapters::Display *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  __int64 *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  __int64 v80; // rdx
  __int64 (__fastcall ***v81)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v82)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 *v86; // rcx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r9
  __int64 *v92; // rcx
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  _BYTE v96[8]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v97; // [rsp+38h] [rbp-61h] BYREF
  __int64 v98; // [rsp+40h] [rbp-59h] BYREF
  __int64 (__fastcall ***v99)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-51h] BYREF
  __int64 v100; // [rsp+50h] [rbp-49h] BYREF
  __int64 (__fastcall ***v101)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-41h] BYREF
  void *Block; // [rsp+60h] [rbp-39h] BYREF
  void *v103[3]; // [rsp+68h] [rbp-31h] BYREF
  char v104; // [rsp+80h] [rbp-19h]
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-11h] BYREF
  __int64 v106; // [rsp+A0h] [rbp+7h]

  Block = 0;
  v103[0] = 0;
  v103[1] = &Block;
  v103[2] = v103;
  v104 = 1;
  v101 = 0;
  v100 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v96, "MkvMfSourceLib::CreateAndAddChapterCue", 564);
  v106 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Media.Core.ChapterCue",
    0x1Eu,
    0x1Du);
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::Core::IChapterCue>>(v106, &v101);
  if ( v9 < 0 )
  {
    v106 = 0;
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::CreateAndAddChapterCue", 564, v9);
    }
    if ( g_wppLevels )
    {
      v15 = 83;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids, 0, v9);
      goto LABEL_134;
    }
    goto LABEL_134;
  }
  v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v101;
  v17 = **v101;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
  v9 = v17(v16, &GUID_c7d15e5d_59dc_431f_a0ee_27744323b36d, &v100);
  if ( v9 >= 0 )
  {
    Block = mkvparser::ConvertFromUTF8(*a2, v18);
    if ( !Block )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v9 = -2147024882;
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v29, "MkvMfSourceLib::CreateAndAddChapterCue", 569, -2147024882);
      }
      if ( g_wppLevels )
      {
        v15 = 85;
        goto LABEL_23;
      }
      goto LABEL_134;
    }
    v30 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v101;
    v31 = (*v101)[6];
    v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &Block);
    v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v31)(v30, *(_QWORD *)(v32 + 24));
    v106 = 0;
    if ( v9 < 0 )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != v9 )
          CallStackContext::TraceFailure(v38, "MkvMfSourceLib::CreateAndAddChapterCue", 570, v9);
      }
      if ( g_wppLevels )
      {
        v15 = 86;
        goto LABEL_23;
      }
      goto LABEL_134;
    }
    v39 = *((_QWORD *)this + 2);
    if ( v39 <= 0 )
      v39 = 0;
    v40 = v39 / 100;
    v42 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v100 + 48LL))(v100, v39 / 100);
    if ( v42 < 0 )
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v43, v44);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != v42 )
          CallStackContext::TraceFailure(v47, "MkvMfSourceLib::CreateAndAddChapterCue", 575, v42);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids, 0, v42);
      v9 = v42;
      goto LABEL_134;
    }
    v48 = *((_QWORD *)this + 3) / 100LL - v40;
    if ( *((_QWORD *)this + 3) / 100LL <= v40 )
      v48 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v100 + 64LL))(v100, v48);
    if ( v9 < 0 )
    {
      v52 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != v9 )
          CallStackContext::TraceFailure(v54, "MkvMfSourceLib::CreateAndAddChapterCue", 579, v9);
      }
      if ( g_wppLevels )
      {
        v15 = 88;
        goto LABEL_23;
      }
      goto LABEL_134;
    }
    if ( *(_QWORD *)this )
    {
      v103[0] = mkvparser::ConvertFromUTF8(*(LPCCH *)this, v49);
      v55 = v100;
      v56 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v100 + 80LL);
      v57 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v103);
      v9 = v56(v55, *(_QWORD *)(v57 + 24));
      v106 = 0;
      if ( v9 < 0 )
      {
        v61 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
          CallStackTracing::s_wpInstance = v62;
          if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
          {
            v61 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v61 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v61 + 8) )
        {
          v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
          if ( *((_DWORD *)v63 + 499) != v9 )
            CallStackContext::TraceFailure(v63, "MkvMfSourceLib::CreateAndAddChapterCue", 585, v9);
        }
        if ( g_wppLevels )
        {
          v15 = 89;
          goto LABEL_23;
        }
        goto LABEL_134;
      }
    }
    v97 = 0;
    v64 = *(__int64 (__fastcall **)(struct IMFTimedTextTrack *, _QWORD, __int64, __int64 *))(*(_QWORD *)a4 + 640LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
    v65 = v100;
    v66 = (*(__int64 (__fastcall **)(const struct mkvparser::Chapters::Display *))(*(_QWORD *)a3 + 24LL))(a3);
    v9 = v64(a4, v66, v65, &v97);
    if ( v9 < 0 )
    {
      v70 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
        CallStackTracing::s_wpInstance = v71;
        if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
        {
          v70 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v70 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v70 + 8) )
      {
        v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
        if ( *((_DWORD *)v72 + 499) != v9 )
          CallStackContext::TraceFailure(v72, "MkvMfSourceLib::CreateAndAddChapterCue", 590, v9);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids, 0, v9);
      goto LABEL_133;
    }
    v99 = 0;
    v98 = 0;
    v73 = *(__int64 (__fastcall **)(const struct mkvparser::Chapters::Display *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a3 + 120LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
    v9 = v73(a3, &v99);
    if ( v9 >= 0 )
    {
      v81 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v99;
      v82 = **v99;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
      v9 = v82(v81, &GUID_3fffac44_ad39_4e45_b906_229df6080b66, &v98);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v98 + 24LL))(v98, v97);
        if ( v9 >= 0 )
          goto LABEL_132;
        v92 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v89, v90, v91);
          CallStackTracing::s_wpInstance = v93;
          if ( v93 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
          {
            v92 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v92 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v92 + 8) )
        {
          v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v92);
          if ( *((_DWORD *)v94 + 499) != v9 )
            CallStackContext::TraceFailure(v94, "MkvMfSourceLib::CreateAndAddChapterCue", 597, v9);
        }
        if ( !g_wppLevels )
          goto LABEL_132;
        v80 = 93;
      }
      else
      {
        v86 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v83, v84, v85);
          CallStackTracing::s_wpInstance = v87;
          if ( v87 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
          {
            v86 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v86 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v86 + 8) )
        {
          v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v86);
          if ( *((_DWORD *)v88 + 499) != v9 )
            CallStackContext::TraceFailure(v88, "MkvMfSourceLib::CreateAndAddChapterCue", 596, v9);
        }
        if ( !g_wppLevels )
          goto LABEL_132;
        v80 = 92;
      }
    }
    else
    {
      v77 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74, v75, v76);
        CallStackTracing::s_wpInstance = v78;
        if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
        {
          v77 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v77 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v77 + 8) )
      {
        v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
        if ( *((_DWORD *)v79 + 499) != v9 )
          CallStackContext::TraceFailure(v79, "MkvMfSourceLib::CreateAndAddChapterCue", 595, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_132;
      v80 = 91;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v80, &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids, 0, v9);
LABEL_132:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
LABEL_133:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
    goto LABEL_134;
  }
  v21 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)v23 + 499) != v9 )
      CallStackContext::TraceFailure(v23, "MkvMfSourceLib::CreateAndAddChapterCue", 565, v9);
  }
  if ( g_wppLevels )
  {
    v15 = 84;
    goto LABEL_23;
  }
LABEL_134:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v96);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v101);
  operator delete(Block);
  operator delete(v103[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003ce90  push    rbp
0x18003ce92  push    rbx
0x18003ce93  push    rsi
0x18003ce94  push    rdi
0x18003ce95  push    r12
0x18003ce97  push    r13
0x18003ce99  push    r14
0x18003ce9b  push    r15
0x18003ce9d  lea     rbp, [rsp-1Fh]
0x18003cea2  sub     rsp, 0B8h
0x18003cea9  mov     rax, cs:__security_cookie
0x18003ceb0  xor     rax, rsp
0x18003ceb3  mov     [rbp+57h+var_48], rax
0x18003ceb7  mov     r12, r9
0x18003ceba  mov     rsi, r8
0x18003cebd  mov     r15, rdx
0x18003cec0  mov     r14, rcx
0x18003cec3  xor     r13d, r13d
0x18003cec6  mov     [rbp+57h+Block], r13
0x18003ceca  mov     [rbp+57h+var_88], r13
0x18003cece  lea     rax, [rbp+57h+Block]
0x18003ced2  mov     [rbp+57h+var_80], rax
0x18003ced6  lea     rax, [rbp+57h+var_88]
0x18003ceda  mov     [rbp+57h+var_78], rax
0x18003cede  mov     [rbp+57h+var_70], 1
0x18003cee2  mov     [rbp+57h+var_98], r13
0x18003cee6  mov     [rbp+57h+var_A0], r13
0x18003ceea  mov     edi, 234h
0x18003ceef  mov     r8d, edi; int
0x18003cef2  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003cef9  lea     rcx, [rbp+57h+var_C0]; this
0x18003cefd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003cf02  nop
0x18003cf03  mov     [rbp+57h+var_50], r13
0x18003cf07  lea     r9d, [r13+1Dh]; unsigned int
0x18003cf0b  lea     r8d, [r13+1Eh]; unsigned int
0x18003cf0f  lea     rdx, ?RuntimeClass_Windows_Media_Core_ChapterCue@@3QBGB; "Windows.Media.Core.ChapterCue"
0x18003cf16  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003cf1a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003cf1f  lea     rdx, [rbp+57h+var_98]
0x18003cf23  mov     rcx, [rbp+57h+var_50]
0x18003cf27  call    ??$ActivateInstance@V?$ComPtr@UIChapterCue@Core@Media@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIChapterCue@Core@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::Core::IChapterCue>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::Core::IChapterCue>>)
0x18003cf2c  mov     ebx, eax
0x18003cf2e  test    eax, eax
0x18003cf30  jns     loc_18003CFCC
0x18003cf36  mov     [rbp+57h+var_50], r13
0x18003cf3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cf41  test    rcx, rcx
0x18003cf44  jnz     short loc_18003CF8D
0x18003cf46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003cf4d  nop     dword ptr [rax+rax+00h]
0x18003cf52  mov     rcx, rax
0x18003cf55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cf5c  test    rax, rax
0x18003cf5f  jz      short loc_18003CF7F
0x18003cf61  mov     rax, [rax]
0x18003cf64  mov     edx, 7F0h
0x18003cf69  mov     rax, [rax+8]
0x18003cf6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf72  test    eax, eax
0x18003cf74  jz      short loc_18003CF7F
0x18003cf76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cf7d  jmp     short loc_18003CF8D
0x18003cf7f  lea     rcx, qword_1800DBF70; this
0x18003cf86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cf8d  cmp     [rcx+8], r13b
0x18003cf91  jz      short loc_18003CFB5
0x18003cf93  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003cf98  cmp     [rax+7CCh], ebx
0x18003cf9e  jz      short loc_18003CFB5
0x18003cfa0  mov     r9d, ebx; int
0x18003cfa3  mov     r8d, edi; int
0x18003cfa6  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003cfad  mov     rcx, rax; this
0x18003cfb0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003cfb5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cfbc  jb      loc_18003D862
0x18003cfc2  mov     edx, 53h ; 'S'
0x18003cfc7  jmp     loc_18003D08F
0x18003cfcc  mov     rbx, [rbp+57h+var_98]
0x18003cfd0  mov     rax, [rbx]
0x18003cfd3  mov     rdi, [rax]
0x18003cfd6  lea     rcx, [rbp+57h+var_A0]
0x18003cfda  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cfdf  lea     r8, [rbp+57h+var_A0]
0x18003cfe3  lea     rdx, _GUID_c7d15e5d_59dc_431f_a0ee_27744323b36d
0x18003cfea  mov     rcx, rbx
0x18003cfed  mov     rax, rdi
0x18003cff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cff5  mov     ebx, eax
0x18003cff7  test    eax, eax
0x18003cff9  jns     loc_18003D0B2
0x18003cfff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d006  test    rcx, rcx
0x18003d009  jnz     short loc_18003D052
0x18003d00b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d012  nop     dword ptr [rax+rax+00h]
0x18003d017  mov     rcx, rax
0x18003d01a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d021  test    rax, rax
0x18003d024  jz      short loc_18003D044
0x18003d026  mov     rax, [rax]
0x18003d029  mov     edx, 7F0h
0x18003d02e  mov     rax, [rax+8]
0x18003d032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d037  test    eax, eax
0x18003d039  jz      short loc_18003D044
0x18003d03b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d042  jmp     short loc_18003D052
0x18003d044  lea     rcx, qword_1800DBF70; this
0x18003d04b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d052  cmp     [rcx+8], r13b
0x18003d056  jz      short loc_18003D07D
0x18003d058  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d05d  cmp     [rax+7CCh], ebx
0x18003d063  jz      short loc_18003D07D
0x18003d065  mov     r9d, ebx; int
0x18003d068  mov     r8d, 235h; int
0x18003d06e  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003d075  mov     rcx, rax; this
0x18003d078  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d07d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d084  jb      loc_18003D862
0x18003d08a  mov     edx, 54h ; 'T'
0x18003d08f  mov     [rsp+0F0h+var_D0], ebx
0x18003d093  xor     r9d, r9d
0x18003d096  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003d09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0a4  mov     rcx, [rcx+10h]
0x18003d0a8  call    WPP_SF_qD
0x18003d0ad  jmp     loc_18003D862
0x18003d0b2  mov     rcx, [r15]; lpMultiByteStr
0x18003d0b5  call    ?ConvertFromUTF8@mkvparser@@YAPEAGPEBD@Z; mkvparser::ConvertFromUTF8(char const *)
0x18003d0ba  mov     [rbp+57h+Block], rax
0x18003d0be  test    rax, rax
0x18003d0c1  jnz     loc_18003D161
0x18003d0c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d0ce  test    rcx, rcx
0x18003d0d1  jnz     short loc_18003D11A
0x18003d0d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d0da  nop     dword ptr [rax+rax+00h]
0x18003d0df  mov     rcx, rax
0x18003d0e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d0e9  test    rax, rax
0x18003d0ec  jz      short loc_18003D10C
0x18003d0ee  mov     rax, [rax]
0x18003d0f1  mov     edx, 7F0h
0x18003d0f6  mov     rax, [rax+8]
0x18003d0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0ff  test    eax, eax
0x18003d101  jz      short loc_18003D10C
0x18003d103  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d10a  jmp     short loc_18003D11A
0x18003d10c  lea     rcx, qword_1800DBF70; this
0x18003d113  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d11a  mov     ebx, 8007000Eh
0x18003d11f  cmp     [rcx+8], r13b
0x18003d123  jz      short loc_18003D14A
0x18003d125  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d12a  cmp     [rax+7CCh], ebx
0x18003d130  jz      short loc_18003D14A
0x18003d132  mov     r9d, ebx; int
0x18003d135  mov     r8d, 239h; int
0x18003d13b  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003d142  mov     rcx, rax; this
0x18003d145  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d14a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d151  jb      loc_18003D862
0x18003d157  mov     edx, 55h ; 'U'
0x18003d15c  jmp     loc_18003D08F
0x18003d161  mov     rdi, [rbp+57h+var_98]
0x18003d165  mov     rax, [rdi]
0x18003d168  mov     rbx, [rax+30h]
0x18003d16c  lea     rdx, [rbp+57h+Block]
0x18003d170  lea     rcx, [rbp+57h+hstringHeader]
0x18003d174  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18003d179  nop
0x18003d17a  mov     rdx, [rax+18h]
0x18003d17e  mov     rcx, rdi
0x18003d181  mov     rax, rbx
0x18003d184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d189  mov     ebx, eax
0x18003d18b  mov     [rbp+57h+var_50], r13
0x18003d18f  mov     ecx, eax
0x18003d191  shr     ecx, 1Fh
0x18003d194  test    cl, cl
0x18003d196  jz      loc_18003D235
0x18003d19c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d1a3  test    rcx, rcx
0x18003d1a6  jnz     short loc_18003D1EF
0x18003d1a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d1af  nop     dword ptr [rax+rax+00h]
0x18003d1b4  mov     rcx, rax
0x18003d1b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d1be  test    rax, rax
0x18003d1c1  jz      short loc_18003D1E1
0x18003d1c3  mov     rax, [rax]
0x18003d1c6  mov     edx, 7F0h
0x18003d1cb  mov     rax, [rax+8]
0x18003d1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1d4  test    eax, eax
0x18003d1d6  jz      short loc_18003D1E1
0x18003d1d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d1df  jmp     short loc_18003D1EF
0x18003d1e1  lea     rcx, qword_1800DBF70; this
0x18003d1e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d1ef  cmp     [rcx+8], r13b
0x18003d1f3  jz      short loc_18003D21E
0x18003d1f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d1fa  test    ebx, ebx
0x18003d1fc  jns     short loc_18003D21E
0x18003d1fe  cmp     [rax+7CCh], ebx
0x18003d204  jz      short loc_18003D21E
0x18003d206  mov     r9d, ebx; int
0x18003d209  mov     r8d, 23Ah; int
0x18003d20f  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003d216  mov     rcx, rax; this
0x18003d219  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d21e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d225  jb      loc_18003D862
0x18003d22b  mov     edx, 56h ; 'V'
0x18003d230  jmp     loc_18003D08F
0x18003d235  mov     rcx, [r14+10h]
0x18003d239  test    rcx, rcx
0x18003d23c  cmovle  rcx, r13
0x18003d240  mov     r15, 0A3D70A3D70A3D70Bh
0x18003d24a  mov     rax, r15
0x18003d24d  imul    rcx
0x18003d250  lea     rbx, [rcx+rdx]
0x18003d254  sar     rbx, 6
0x18003d258  mov     rax, rbx
0x18003d25b  shr     rax, 3Fh
0x18003d25f  add     rbx, rax
0x18003d262  mov     rcx, [rbp+57h+var_A0]
0x18003d266  mov     rax, [rcx]
0x18003d269  mov     rdx, rbx
0x18003d26c  mov     rax, [rax+30h]
0x18003d270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d275  mov     edi, eax
0x18003d277  test    eax, eax
0x18003d279  jns     loc_18003D330
0x18003d27f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d286  test    rcx, rcx
0x18003d289  jnz     short loc_18003D2D2
0x18003d28b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d292  nop     dword ptr [rax+rax+00h]
0x18003d297  mov     rcx, rax
0x18003d29a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d2a1  test    rax, rax
0x18003d2a4  jz      short loc_18003D2C4
0x18003d2a6  mov     rax, [rax]
0x18003d2a9  mov     edx, 7F0h
0x18003d2ae  mov     rax, [rax+8]
0x18003d2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2b7  test    eax, eax
0x18003d2b9  jz      short loc_18003D2C4
0x18003d2bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d2c2  jmp     short loc_18003D2D2
0x18003d2c4  lea     rcx, qword_1800DBF70; this
0x18003d2cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d2d2  cmp     [rcx+8], r13b
0x18003d2d6  jz      short loc_18003D2FD
0x18003d2d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d2dd  cmp     [rax+7CCh], edi
0x18003d2e3  jz      short loc_18003D2FD
0x18003d2e5  mov     r9d, edi; int
0x18003d2e8  mov     r8d, 23Fh; int
0x18003d2ee  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003d2f5  mov     rcx, rax; this
0x18003d2f8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d2fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d304  jb      short loc_18003D329
0x18003d306  mov     edx, 57h ; 'W'
0x18003d30b  mov     [rsp+0F0h+var_D0], edi
0x18003d30f  xor     r9d, r9d
0x18003d312  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003d319  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d320  mov     rcx, [rcx+10h]
0x18003d324  call    WPP_SF_qD
0x18003d329  mov     ebx, edi
0x18003d32b  jmp     loc_18003D862
0x18003d330  mov     rax, r15
0x18003d333  imul    qword ptr [r14+18h]
0x18003d337  mov     r9, rdx
0x18003d33a  add     r9, [r14+18h]
0x18003d33e  sar     r9, 6
0x18003d342  mov     rax, r9
0x18003d345  shr     rax, 3Fh
0x18003d349  add     r9, rax
0x18003d34c  mov     rcx, [rbp+57h+var_A0]
0x18003d350  mov     r8, [rcx]
0x18003d353  mov     rdx, r9
0x18003d356  sub     rdx, rbx
0x18003d359  cmp     r9, rbx
0x18003d35c  cmovle  rdx, r13
0x18003d360  mov     rax, [r8+40h]
0x18003d364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d369  mov     ebx, eax
0x18003d36b  test    eax, eax
0x18003d36d  jns     loc_18003D408
  ... truncated ...
```
