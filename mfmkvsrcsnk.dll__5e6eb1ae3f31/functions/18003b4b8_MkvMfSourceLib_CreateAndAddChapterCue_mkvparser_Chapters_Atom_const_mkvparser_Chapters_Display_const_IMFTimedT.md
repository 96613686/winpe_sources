# MkvMfSourceLib::CreateAndAddChapterCue(mkvparser::Chapters::Atom const *,mkvparser::Chapters::Display const *,IMFTimedTextTrack *,IMFTimedTextCueBuilder *)

- ea: `0x18003b4b8`
- end: `0x18003be9a`
- name: `?CreateAndAddChapterCue@MkvMfSourceLib@@YAJPEBVAtom@Chapters@mkvparser@@PEBVDisplay@34@PEAUIMFTimedTextTrack@@PEAUIMFTimedTextCueBuilder@@@Z`
- size: `2530`
- prototype: `__int64 __fastcall(MkvMfSourceLib *__hidden this, const struct mkvparser::Chapters::Atom *, const struct mkvparser::Chapters::Display *, struct IMFTimedTextTrack *, struct IMFTimedTextCueBuilder *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003bea0`

## callees

- `0x180001fd0`
- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180039f58`
- `0x180039fb8`
- `0x18003b4b8`
- `0x18003c478`
- `0x180071330`
- `0x180084b34`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b56e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b62d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b6ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b7be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b89b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b989`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ba68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bb44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bc22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bce4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bd91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b56e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b62d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b6ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b7be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b89b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b989`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ba68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bb44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bc22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bce4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bd91`

## string_xrefs

- `0x18003b51a`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003b5c8`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003b68a`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003b751`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003b81f`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003b8f8`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003b9e6`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003bac9`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003bba1`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003bc7f`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003bd41`: `MkvMfSourceLib::CreateAndAddChapterCue`
- `0x18003bdee`: `MkvMfSourceLib::CreateAndAddChapterCue`

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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v36 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v45 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v52 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v61 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v70 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v92 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v86 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v77 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v21 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18003b4b8  push    rbp
0x18003b4ba  push    rbx
0x18003b4bb  push    rsi
0x18003b4bc  push    rdi
0x18003b4bd  push    r12
0x18003b4bf  push    r13
0x18003b4c1  push    r14
0x18003b4c3  push    r15
0x18003b4c5  lea     rbp, [rsp-1Fh]
0x18003b4ca  sub     rsp, 0B8h
0x18003b4d1  mov     rax, cs:__security_cookie
0x18003b4d8  xor     rax, rsp
0x18003b4db  mov     [rbp+57h+var_48], rax
0x18003b4df  mov     r12, r9
0x18003b4e2  mov     rsi, r8
0x18003b4e5  mov     r15, rdx
0x18003b4e8  mov     r14, rcx
0x18003b4eb  xor     r13d, r13d
0x18003b4ee  mov     [rbp+57h+Block], r13
0x18003b4f2  mov     [rbp+57h+var_88], r13
0x18003b4f6  lea     rax, [rbp+57h+Block]
0x18003b4fa  mov     [rbp+57h+var_80], rax
0x18003b4fe  lea     rax, [rbp+57h+var_88]
0x18003b502  mov     [rbp+57h+var_78], rax
0x18003b506  mov     [rbp+57h+var_70], 1
0x18003b50a  mov     [rbp+57h+var_98], r13
0x18003b50e  mov     [rbp+57h+var_A0], r13
0x18003b512  mov     edi, 234h
0x18003b517  mov     r8d, edi; int
0x18003b51a  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003b521  lea     rcx, [rbp+57h+var_C0]; this
0x18003b525  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b52a  nop
0x18003b52b  mov     [rbp+57h+var_50], r13
0x18003b52f  lea     r9d, [r13+1Dh]; unsigned int
0x18003b533  lea     r8d, [r13+1Eh]; unsigned int
0x18003b537  lea     rdx, ?RuntimeClass_Windows_Media_Core_ChapterCue@@3QBGB; "Windows.Media.Core.ChapterCue"
0x18003b53e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003b542  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b547  lea     rdx, [rbp+57h+var_98]
0x18003b54b  mov     rcx, [rbp+57h+var_50]
0x18003b54f  call    ??$ActivateInstance@V?$ComPtr@UIChapterCue@Core@Media@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIChapterCue@Core@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::Core::IChapterCue>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::Core::IChapterCue>>)
0x18003b554  mov     ebx, eax
0x18003b556  test    eax, eax
0x18003b558  jns     loc_18003B5EE
0x18003b55e  mov     [rbp+57h+var_50], r13
0x18003b562  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b569  test    rcx, rcx
0x18003b56c  jnz     short loc_18003B5AF
0x18003b56e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b574  mov     rcx, rax
0x18003b577  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b57e  test    rax, rax
0x18003b581  jz      short loc_18003B5A1
0x18003b583  mov     rax, [rax]
0x18003b586  mov     edx, 7F0h
0x18003b58b  mov     rax, [rax+8]
0x18003b58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b594  test    eax, eax
0x18003b596  jz      short loc_18003B5A1
0x18003b598  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b59f  jmp     short loc_18003B5AF
0x18003b5a1  lea     rcx, qword_1800D6F70; this
0x18003b5a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b5af  cmp     [rcx+8], r13b
0x18003b5b3  jz      short loc_18003B5D7
0x18003b5b5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b5ba  cmp     [rax+7CCh], ebx
0x18003b5c0  jz      short loc_18003B5D7
0x18003b5c2  mov     r9d, ebx; int
0x18003b5c5  mov     r8d, edi; int
0x18003b5c8  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003b5cf  mov     rcx, rax; this
0x18003b5d2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b5d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003b5de  jb      loc_18003BE48
0x18003b5e4  mov     edx, 53h ; 'S'
0x18003b5e9  jmp     loc_18003B6AB
0x18003b5ee  mov     rbx, [rbp+57h+var_98]
0x18003b5f2  mov     rax, [rbx]
0x18003b5f5  mov     rdi, [rax]
0x18003b5f8  lea     rcx, [rbp+57h+var_A0]
0x18003b5fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b601  lea     r8, [rbp+57h+var_A0]
0x18003b605  lea     rdx, _GUID_c7d15e5d_59dc_431f_a0ee_27744323b36d
0x18003b60c  mov     rcx, rbx
0x18003b60f  mov     rax, rdi
0x18003b612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b617  mov     ebx, eax
0x18003b619  test    eax, eax
0x18003b61b  jns     loc_18003B6CE
0x18003b621  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b628  test    rcx, rcx
0x18003b62b  jnz     short loc_18003B66E
0x18003b62d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b633  mov     rcx, rax
0x18003b636  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b63d  test    rax, rax
0x18003b640  jz      short loc_18003B660
0x18003b642  mov     rax, [rax]
0x18003b645  mov     edx, 7F0h
0x18003b64a  mov     rax, [rax+8]
0x18003b64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b653  test    eax, eax
0x18003b655  jz      short loc_18003B660
0x18003b657  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b65e  jmp     short loc_18003B66E
0x18003b660  lea     rcx, qword_1800D6F70; this
0x18003b667  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b66e  cmp     [rcx+8], r13b
0x18003b672  jz      short loc_18003B699
0x18003b674  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b679  cmp     [rax+7CCh], ebx
0x18003b67f  jz      short loc_18003B699
0x18003b681  mov     r9d, ebx; int
0x18003b684  mov     r8d, 235h; int
0x18003b68a  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003b691  mov     rcx, rax; this
0x18003b694  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b699  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003b6a0  jb      loc_18003BE48
0x18003b6a6  mov     edx, 54h ; 'T'
0x18003b6ab  mov     [rsp+0F0h+var_D0], ebx
0x18003b6af  xor     r9d, r9d
0x18003b6b2  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003b6b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6c0  mov     rcx, [rcx+10h]
0x18003b6c4  call    WPP_SF_qD
0x18003b6c9  jmp     loc_18003BE48
0x18003b6ce  mov     rcx, [r15]; lpMultiByteStr
0x18003b6d1  call    ?ConvertFromUTF8@mkvparser@@YAPEAGPEBD@Z; mkvparser::ConvertFromUTF8(char const *)
0x18003b6d6  mov     [rbp+57h+Block], rax
0x18003b6da  test    rax, rax
0x18003b6dd  jnz     loc_18003B777
0x18003b6e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b6ea  test    rcx, rcx
0x18003b6ed  jnz     short loc_18003B730
0x18003b6ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b6f5  mov     rcx, rax
0x18003b6f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b6ff  test    rax, rax
0x18003b702  jz      short loc_18003B722
0x18003b704  mov     rax, [rax]
0x18003b707  mov     edx, 7F0h
0x18003b70c  mov     rax, [rax+8]
0x18003b710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b715  test    eax, eax
0x18003b717  jz      short loc_18003B722
0x18003b719  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b720  jmp     short loc_18003B730
0x18003b722  lea     rcx, qword_1800D6F70; this
0x18003b729  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b730  mov     ebx, 8007000Eh
0x18003b735  cmp     [rcx+8], r13b
0x18003b739  jz      short loc_18003B760
0x18003b73b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b740  cmp     [rax+7CCh], ebx
0x18003b746  jz      short loc_18003B760
0x18003b748  mov     r9d, ebx; int
0x18003b74b  mov     r8d, 239h; int
0x18003b751  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003b758  mov     rcx, rax; this
0x18003b75b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b760  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003b767  jb      loc_18003BE48
0x18003b76d  mov     edx, 55h ; 'U'
0x18003b772  jmp     loc_18003B6AB
0x18003b777  mov     rdi, [rbp+57h+var_98]
0x18003b77b  mov     rax, [rdi]
0x18003b77e  mov     rbx, [rax+30h]
0x18003b782  lea     rdx, [rbp+57h+Block]
0x18003b786  lea     rcx, [rbp+57h+hstringHeader]
0x18003b78a  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18003b78f  nop
0x18003b790  mov     rdx, [rax+18h]
0x18003b794  mov     rcx, rdi
0x18003b797  mov     rax, rbx
0x18003b79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b79f  mov     ebx, eax
0x18003b7a1  mov     [rbp+57h+var_50], r13
0x18003b7a5  mov     ecx, eax
0x18003b7a7  shr     ecx, 1Fh
0x18003b7aa  test    cl, cl
0x18003b7ac  jz      loc_18003B845
0x18003b7b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b7b9  test    rcx, rcx
0x18003b7bc  jnz     short loc_18003B7FF
0x18003b7be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b7c4  mov     rcx, rax
0x18003b7c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b7ce  test    rax, rax
0x18003b7d1  jz      short loc_18003B7F1
0x18003b7d3  mov     rax, [rax]
0x18003b7d6  mov     edx, 7F0h
0x18003b7db  mov     rax, [rax+8]
0x18003b7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7e4  test    eax, eax
0x18003b7e6  jz      short loc_18003B7F1
0x18003b7e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b7ef  jmp     short loc_18003B7FF
0x18003b7f1  lea     rcx, qword_1800D6F70; this
0x18003b7f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b7ff  cmp     [rcx+8], r13b
0x18003b803  jz      short loc_18003B82E
0x18003b805  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b80a  test    ebx, ebx
0x18003b80c  jns     short loc_18003B82E
0x18003b80e  cmp     [rax+7CCh], ebx
0x18003b814  jz      short loc_18003B82E
0x18003b816  mov     r9d, ebx; int
0x18003b819  mov     r8d, 23Ah; int
0x18003b81f  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003b826  mov     rcx, rax; this
0x18003b829  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b82e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003b835  jb      loc_18003BE48
0x18003b83b  mov     edx, 56h ; 'V'
0x18003b840  jmp     loc_18003B6AB
0x18003b845  mov     rcx, [r14+10h]
0x18003b849  test    rcx, rcx
0x18003b84c  cmovle  rcx, r13
0x18003b850  mov     r15, 0A3D70A3D70A3D70Bh
0x18003b85a  mov     rax, r15
0x18003b85d  imul    rcx
0x18003b860  lea     rbx, [rcx+rdx]
0x18003b864  sar     rbx, 6
0x18003b868  mov     rax, rbx
0x18003b86b  shr     rax, 3Fh
0x18003b86f  add     rbx, rax
0x18003b872  mov     rcx, [rbp+57h+var_A0]
0x18003b876  mov     rax, [rcx]
0x18003b879  mov     rdx, rbx
0x18003b87c  mov     rax, [rax+30h]
0x18003b880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b885  mov     edi, eax
0x18003b887  test    eax, eax
0x18003b889  jns     loc_18003B93A
0x18003b88f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b896  test    rcx, rcx
0x18003b899  jnz     short loc_18003B8DC
0x18003b89b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b8a1  mov     rcx, rax
0x18003b8a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b8ab  test    rax, rax
0x18003b8ae  jz      short loc_18003B8CE
0x18003b8b0  mov     rax, [rax]
0x18003b8b3  mov     edx, 7F0h
0x18003b8b8  mov     rax, [rax+8]
0x18003b8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8c1  test    eax, eax
0x18003b8c3  jz      short loc_18003B8CE
0x18003b8c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b8cc  jmp     short loc_18003B8DC
0x18003b8ce  lea     rcx, qword_1800D6F70; this
0x18003b8d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b8dc  cmp     [rcx+8], r13b
0x18003b8e0  jz      short loc_18003B907
0x18003b8e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b8e7  cmp     [rax+7CCh], edi
0x18003b8ed  jz      short loc_18003B907
0x18003b8ef  mov     r9d, edi; int
0x18003b8f2  mov     r8d, 23Fh; int
0x18003b8f8  lea     rdx, aMkvmfsourcelib_63; "MkvMfSourceLib::CreateAndAddChapterCue"
0x18003b8ff  mov     rcx, rax; this
0x18003b902  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b907  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003b90e  jb      short loc_18003B933
0x18003b910  mov     edx, 57h ; 'W'
0x18003b915  mov     [rsp+0F0h+var_D0], edi
0x18003b919  xor     r9d, r9d
0x18003b91c  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003b923  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b92a  mov     rcx, [rcx+10h]
0x18003b92e  call    WPP_SF_qD
0x18003b933  mov     ebx, edi
0x18003b935  jmp     loc_18003BE48
0x18003b93a  mov     rax, r15
0x18003b93d  imul    qword ptr [r14+18h]
0x18003b941  mov     r9, rdx
0x18003b944  add     r9, [r14+18h]
0x18003b948  sar     r9, 6
0x18003b94c  mov     rax, r9
0x18003b94f  shr     rax, 3Fh
0x18003b953  add     r9, rax
0x18003b956  mov     rcx, [rbp+57h+var_A0]
0x18003b95a  mov     r8, [rcx]
0x18003b95d  mov     rdx, r9
0x18003b960  sub     rdx, rbx
0x18003b963  cmp     r9, rbx
0x18003b966  cmovle  rdx, r13
0x18003b96a  mov     rax, [r8+40h]
0x18003b96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b973  mov     ebx, eax
0x18003b975  test    eax, eax
0x18003b977  jns     loc_18003BA0C
0x18003b97d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b984  test    rcx, rcx
0x18003b987  jnz     short loc_18003B9CA
0x18003b989  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b98f  mov     rcx, rax
  ... truncated ...
```
