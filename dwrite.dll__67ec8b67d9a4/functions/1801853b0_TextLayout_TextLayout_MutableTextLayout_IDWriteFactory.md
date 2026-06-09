# TextLayout::TextLayout(MutableTextLayout *,IDWriteFactory *)

- ea: `0x1801853b0`
- end: `0x180185e5e`
- name: `??0TextLayout@@QEAA@PEAVMutableTextLayout@@PEAUIDWriteFactory@@@Z`
- size: `2734`
- prototype: `TextLayout *__fastcall(TextLayout *__hidden this, struct MutableTextLayout *, struct IDWriteFactory *)`
- caller_count: `1`
- callee_count: `48`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18018530c`

## callees

- `0x18011ed18`
- `0x18011ef30`
- `0x180131c1c`
- `0x180133acc`
- `0x180154068`
- `0x18015ead4`
- `0x18015fd5c`
- `0x18016200c`
- `0x1801644d0`
- `0x18016708c`
- `0x180167110`
- `0x180175718`
- `0x180176870`
- `0x180177f48`
- `0x180179e40`
- `0x18017a170`
- `0x18017a268`
- `0x18017a3bc`
- `0x18017a5c4`
- `0x18017bbec`
- `0x18017bc7c`
- `0x18017bccc`
- `0x1801853b0`
- `0x180185e64`
- `0x1801869bc`
- `0x180187418`
- `0x1801c2608`
- `0x1801c8ed0`
- `0x1801cb7b8`
- `0x1801cd8e0`
- `0x1801cf0b4`
- `0x1801d9d4c`
- `0x1801da78c`
- `0x1801ef8d4`
- `0x1801efaac`
- `0x1801f2fe4`
- `0x1801f37b0`
- `0x1801f6b50`
- `0x1801fc958`
- `0x1801fca34`
- `0x1801fca78`
- `0x180201b08`
- `0x180212490`
- `0x180212f4c`
- `0x18021deb8`
- `0x18023e6d4`
- `0x180251c48`
- `0x180330010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801856dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801856dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801856fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801856fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
TextLayout *__fastcall TextLayout::TextLayout(
        TextLayout *this,
        struct MutableTextLayout *a2,
        struct IDWriteFactory *a3)
{
  __int64 *v6; // r13
  char *v7; // rbx
  unsigned __int64 v8; // rbx
  __int64 v9; // r14
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  wchar_t *v15; // rax
  struct _RTL_CRITICAL_SECTION *v16; // rax
  struct _RTL_CRITICAL_SECTION *v17; // rbx
  _QWORD *v18; // r8
  unsigned int v19; // esi
  __int64 v20; // rcx
  struct _RTL_CRITICAL_SECTION *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  char v24; // dl
  int v25; // ecx
  struct _RTL_CRITICAL_SECTION *v26; // r12
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 CurrentValue; // r14
  int v30; // ebx
  int RunLength; // eax
  unsigned __int64 v32; // rcx
  int v33; // r9d
  _QWORD *v34; // rdx
  __int16 v35; // r12
  struct RecentFontCache::FontInstance *FontInstance; // rax
  struct RecentFontCache::FontInstance *v37; // rbx
  __int64 v38; // rsi
  unsigned __int64 v39; // rcx
  int v40; // eax
  char v41; // cl
  __int16 v42; // si
  __int64 v43; // rbx
  __int64 v44; // rbx
  __int16 v45; // dx
  __int16 v46; // ax
  __int64 v47; // rbx
  __int64 v48; // rdx
  __int64 v49; // r8
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rcx
  __int64 v52; // rdx
  unsigned __int64 v53; // rax
  __int64 v54; // rcx
  unsigned __int64 v55; // rbx
  __int64 v56; // rsi
  __int64 v57; // rdx
  unsigned __int64 v58; // rcx
  size_t v59; // rbx
  __int64 v60; // rax
  __int64 v61; // r8
  unsigned __int64 v62; // rdx
  unsigned __int64 v63; // rcx
  __int64 v64; // rax
  __int64 *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  unsigned int v69; // edx
  size_t v71; // rbx
  const struct RunFormat *v72; // rax
  char v73; // cl
  __int64 v74; // rax
  struct IDWritePrivateFontFace *FontFace; // rax
  struct IDWritePrivateFontFace *v76; // rsi
  __int64 v77; // rcx
  unsigned int v78; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v79; // [rsp+28h] [rbp-D8h] BYREF
  char v80[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v81; // [rsp+34h] [rbp-CCh]
  int v82; // [rsp+38h] [rbp-C8h]
  struct _RTL_CRITICAL_SECTION *v83; // [rsp+40h] [rbp-C0h]
  struct MutableTextLayout *v84; // [rsp+48h] [rbp-B8h]
  struct IDWriteFactory *v85; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v86; // [rsp+58h] [rbp-A8h] BYREF
  FontFallback *v87; // [rsp+60h] [rbp-A0h]
  int v88; // [rsp+68h] [rbp-98h]
  _QWORD v89[2]; // [rsp+70h] [rbp-90h] BYREF
  char v90; // [rsp+80h] [rbp-80h]
  char v91; // [rsp+88h] [rbp-78h]
  unsigned int v92; // [rsp+8Ch] [rbp-74h]
  _DWORD v93[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v94; // [rsp+98h] [rbp-68h]
  __int128 v95; // [rsp+A0h] [rbp-60h]
  __int64 v96; // [rsp+B0h] [rbp-50h]
  int v97; // [rsp+B8h] [rbp-48h]
  __int16 v98; // [rsp+BCh] [rbp-44h]
  __int16 v99; // [rsp+BEh] [rbp-42h]
  int v100; // [rsp+C0h] [rbp-40h]
  __int64 v101; // [rsp+C8h] [rbp-38h]
  __int128 v102; // [rsp+D0h] [rbp-30h]
  volatile signed __int32 *v103; // [rsp+E0h] [rbp-20h]
  __int64 v104; // [rsp+E8h] [rbp-18h]
  TextLayout *v105; // [rsp+F0h] [rbp-10h]
  _QWORD v106[3]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v107[4]; // [rsp+110h] [rbp+10h] BYREF

  v84 = a2;
  v105 = this;
  *(_QWORD *)this = &TextLayout::`vftable'{for `IDWriteTextAnalysisSource1'};
  *((_QWORD *)this + 1) = &TextLayout::`vftable'{for `IDWriteTextAnalysisSink1'};
  *((_QWORD *)this + 2) = &TextLayout::`vftable'{for `IDWritePrivateTextAnalysisSource'};
  *((_QWORD *)this + 3) = a2;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 32);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 56);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 80);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 104);
  v6 = (__int64 *)((char *)this + 128);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 128);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 152);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 176);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 200);
  v7 = (char *)a2 + 24;
  *((_QWORD *)this + 28) = v7;
  *((_DWORD *)this + 72) = 2139095039;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_BYTE *)this + 320) &= 0xFCu;
  *((_QWORD *)this + 41) = 0;
  if ( (((unsigned __int8)(*(_DWORD *)(*((_QWORD *)this + 3) + 100LL) >> 1)
       ^ (unsigned __int8)(*(_DWORD *)(*((_QWORD *)this + 3) + 104LL) >> 1))
      & 1) != 0 )
  {
    Exception::Exception((Exception *)&v78, -2003283957, 0);
    LogAndThrow<OSException>(&v78, 0x74756F79616CLL, 274);
  }
  v8 = *((_QWORD *)v7 + 2);
  v9 = *((_QWORD *)this + 20);
  v10 = *((_QWORD *)this + 19);
  v11 = (v9 - v10) >> 1;
  if ( v8 < v11 )
  {
    v12 = v10 + 2 * v8;
    goto LABEL_7;
  }
  if ( v8 > v11 )
  {
    if ( v8 > (*((_QWORD *)this + 21) - v10) >> 1 )
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 152, v8, v80);
      goto LABEL_8;
    }
    v71 = 2 * (v8 - v11);
    memset_0(*((void **)this + 20), 0, v71);
    v12 = v71 + v9;
LABEL_7:
    *((_QWORD *)this + 20) = v12;
  }
LABEL_8:
  v13 = *(_QWORD *)(*((_QWORD *)this + 28) + 16LL);
  if ( v13 > 0xFFFFFFFF )
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v13, v10);
  v14 = ((unsigned int)(3 * v13) >> 1) + 16;
  v79 = v14;
  if ( v14 > (__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 7)) >> 1 )
    std::vector<unsigned short>::_Reallocate<0>((char *)this + 56, &v79);
  v79 = v14;
  if ( v14 > (__int64)(*((_QWORD *)this + 12) - *((_QWORD *)this + 10)) >> 2 )
    std::vector<float>::_Reallocate<0>((char *)this + 80, &v79);
  TextLayout::InitializeTextMetrics(this);
  LocaleNameFromLCID(v107, 1024, 0);
  v15 = (wchar_t *)StartOf<std::wstring>(v107);
  LanguageTagImpl::ValidateAndNormalize(v15, v107[2]);
  v16 = (struct _RTL_CRITICAL_SECTION *)operator new(0x48u);
  v17 = v16;
  v83 = v16;
  v18 = v107;
  if ( v107[3] > 7u )
    v18 = (_QWORD *)v107[0];
  NumberSubstitution::NumberSubstitution(&v16->LockCount, 0, v18, 0);
  v17->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ComObject<DWriteNumberSubstitution,DeleteOnZeroReference>::`vftable';
  v19 = 0;
  LODWORD(v17[1].LockSemaphore) = 0;
  ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))ComObject<DWriteNumberSubstitution,DeleteOnZeroReference>::AddRef)(v17);
  v20 = *((_QWORD *)this + 37);
  *((_QWORD *)this + 37) = v17;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v21 = (struct _RTL_CRITICAL_SECTION *)operator new(0x28u);
  v83 = v21;
  *(_OWORD *)&v21->DebugInfo = 0;
  *(_OWORD *)&v21->OwningThread = 0;
  v21->OwningThread = 0;
  v21->LockSemaphore = (HANDLE)0x4000;
  v21->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ComObject<DWriteTextAnalyzer,DeleteOnZeroReference>::`vftable'{for `IDWriteTextAnalyzer2'};
  *(_QWORD *)&v21->LockCount = &ComObject<DWriteTextAnalyzer,DeleteOnZeroReference>::`vftable'{for `IDWritePrivateTextAnalyzer'};
  HIDWORD(v21->SpinCount) = 0;
  ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))ComObject<DWriteTextAnalyzer,DeleteOnZeroReference>::AddRef)(v21);
  v22 = *((_QWORD *)this + 38);
  *((_QWORD *)this + 38) = v21;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = *((_QWORD *)this + 3);
  LOBYTE(v22) = *(_BYTE *)(v23 + 353);
  v81 = v22;
  v24 = *(_BYTE *)(v23 + 355);
  v25 = *(_DWORD *)(v23 + 124);
  v85 = a3;
  v86 = 0;
  v87 = 0;
  v88 = v25;
  v90 = 0;
  v89[0] = v89;
  v89[1] = v89;
  v91 = v24;
  v92 = 0;
  if ( !v24 )
  {
    v83 = &RecentFontCache::globalLock_;
    EnterCriticalSection(&RecentFontCache::globalLock_);
    v92 = RecentFontCache::globalInvalidCount_;
    RecentFontCache::FontList::operator=(v89);
    LeaveCriticalSection(&RecentFontCache::globalLock_);
  }
  v78 = 0;
  v26 = (struct _RTL_CRITICAL_SECTION *)((char *)v84 + 320);
  v83 = (struct _RTL_CRITICAL_SECTION *)((char *)v84 + 320);
  do
  {
    RunIndexer<RunFormat>::SetPosition(*((_QWORD *)this + 3) + 320LL, v19);
    CurrentValue = RunIndexer<RunFormat>::GetCurrentValue(*((_QWORD *)this + 3) + 320LL, v27, v28);
    v30 = *((_DWORD *)v84 + 84);
    RunLength = RunIndexer<RunFormat>::GetRunLength(v26);
    v32 = (unsigned int)(RunLength + v30);
    v33 = RunLength + v30 - v19;
    v82 = v33;
    v34 = (_QWORD *)*((_QWORD *)this + 28);
    if ( v32 < v34[2] )
    {
      v74 = v34[3] > 7u ? *v34 : *((_QWORD *)this + 28);
      if ( (*(_WORD *)(v74 + 2 * v32) & 0xFC00) == 0xDC00 && (_DWORD)v32 )
      {
        if ( v34[3] > 7u )
          v34 = (_QWORD *)*v34;
        if ( (*((_WORD *)v34 + (unsigned int)(v32 - 1)) & 0xFC00) != 0xDC00 )
          v82 = ++v33;
      }
    }
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v35 = v98 & 0xC080;
    v98 &= 0xC080u;
    v99 = 0;
    v100 = 1098907648;
    v101 = 0;
    v102 = 0;
    v104 = 0;
    v93[0] = v19;
    v93[1] = v33;
    _InterlockedIncrement(*(volatile signed __int32 **)CurrentValue);
    DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)&DWrite::RefString::empty_);
    v103 = *(volatile signed __int32 **)CurrentValue;
    FontInstance = RecentFontCache::GetFontInstance((RecentFontCache *)&v85, (const struct RunFormat *)CurrentValue);
    v37 = FontInstance;
    v38 = *((_QWORD *)FontInstance + 3);
    if ( v38 )
    {
      if ( !*((_BYTE *)FontInstance + 72) || *((_BYTE *)FontInstance + 73) )
        goto LABEL_80;
    }
    else
    {
      if ( !*((_QWORD *)FontInstance + 4) )
      {
        if ( *((_BYTE *)FontInstance + 73) )
          goto LABEL_80;
        RecentFontCache::GetFirstMatchingFont((RecentFontCache *)&v85, FontInstance);
        if ( !*((_QWORD *)v37 + 4) )
        {
          *((_BYTE *)v37 + 73) = 1;
LABEL_80:
          v38 = 0;
          goto LABEL_30;
        }
      }
      v79 = 0;
      (*(void (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)v37 + 4) + 104LL))(*((_QWORD *)v37 + 4), &v79);
      v39 = v79;
      if ( v79 || (*((_BYTE *)v37 + 73) = 1, (v39 = v79) != 0) )
      {
        v40 = (**(__int64 (__fastcall ***)(unsigned __int64, GUID *, __int64))v39)(
                v39,
                &GUID_ba6f3da5_0780_4422_9fae_eab429b786b4,
                (__int64)v37 + 24);
        if ( v40 < 0 )
        {
          Exception::Exception((Exception *)&v78, v40, 0);
          LogAndThrow<OSException>(&v78, 1128682092, 3171);
        }
        v39 = v79;
      }
      v38 = *((_QWORD *)v37 + 3);
      if ( v39 )
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
LABEL_30:
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
    v101 = v38;
    if ( v38 )
      v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 56LL))(v38);
    else
      v41 = 0;
    v100 = *(_DWORD *)(CurrentValue + 36);
    v42 = (4 * (*(_BYTE *)(CurrentValue + 81) & 1))
        | v35 & 0xFFE8
        | (16 * (v41 & 1))
        | (2 * (*(_BYTE *)(CurrentValue + 80) & 1)) & 0xFB;
    v98 = v42;
    v43 = *(_QWORD *)(CurrentValue + 64);
    if ( v43 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v43 + 8LL))(*(_QWORD *)(CurrentValue + 64));
    *(_QWORD *)&v102 = v43;
    v44 = *(_QWORD *)(CurrentValue + 72);
    if ( v44 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v44 + 8LL))(*(_QWORD *)(CurrentValue + 72));
    *((_QWORD *)&v102 + 1) = v44;
    v45 = v42 & 0xFD7F | (*(_QWORD *)(CurrentValue + 56) != 0 ? 0x80 : 0) | ((*(_BYTE *)(CurrentValue + 82) & 1) << 9);
    v98 = v45;
    if ( *(float *)(CurrentValue + 40) == 0.0
      && *(float *)(CurrentValue + 44) == 0.0
      && *(float *)(CurrentValue + 48) == 0.0 )
    {
      v46 = 0;
    }
    else
    {
      v46 = 1024;
    }
    v98 = v46 | v45 & 0xFBFF;
    LODWORD(v47) = (unsigned __int8)v81;
    if ( ((v46 | v45) & 0x80u) != 0 )
      LODWORD(v47) = 1;
    v81 = v47;
    if ( *((_QWORD *)this + 5) == *((_QWORD *)this + 6) )
    {
      std::vector<TextLayout::Span>::_Emplace_reallocate<TextLayout::Span const &>(
        (char *)this + 32,
        *((_QWORD *)this + 5),
        v93);
    }
    else
    {
      TextLayout::Span::Span(*((TextLayout::Span **)this + 5), (const struct TextLayout::Span *)v93);
      *((_QWORD *)this + 5) += 96LL;
    }
    v78 += v82;
    v19 = v78;
    TextLayout::Span::~Span((TextLayout::Span *)v93);
    v50 = *(_QWORD *)(*((_QWORD *)this + 28) + 16LL);
    v26 = v83;
  }
  while ( v78 < v50 );
  if ( !v50 )
  {
    v47 = *((_QWORD *)this + 4);
    if ( *(_QWORD *)(v47 + 72) )
    {
      *(_QWORD *)(v47 + 72) = 0;
      ComPtr<IDWriteInlineObject>::Deref();
    }
    v72 = (const struct RunFormat *)RunIndexer<RunFormat>::GetCurrentValue(*((_QWORD *)this + 3) + 320LL, v48, v49);
    if ( !*(_QWORD *)(v47 + 56) )
    {
      FontFace = RecentFontCache::GetFontFace((RecentFontCache *)&v85, v72, 1);
      v76 = FontFace;
      if ( FontFace )
        (*(void (__fastcall **)(struct IDWritePrivateFontFace *))(*(_QWORD *)FontFace + 8LL))(FontFace);
      v77 = *(_QWORD *)(v47 + 56);
      *(_QWORD *)(v47 + 56) = v76;
      if ( v77 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    }
    v73 = *(_BYTE *)(*((_QWORD *)this + 3) + 104LL) & 1;
    *(_BYTE *)(v47 + 46) = v73;
    *(_BYTE *)(v47 + 47) = v73;
    LOBYTE(v47) = v81;
  }
  v51 = *(_QWORD *)(*((_QWORD *)this + 28) + 16LL);
  v52 = *((_QWORD *)this + 5);
  v53 = *(unsigned int *)(v52 - 96);
  if ( v53 > v51 || (v51 -= v53, v51 > 0xFFFFFFFF) )
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v51, v52);
  *(_DWORD *)(v52 - 92) = v51;
  TextLayout::AnalyzeText(this, (struct RecentFontCache *)&v85, v47);
  TextLayout::DetermineLineHeights(this);
  TextLayout::TrimLines(this);
  TextLayout::DetermineOpticalAlignment(this);
  TextLayout::ResetLinesTrailingSpace(this);
  TextLayout::JustifyLines(this);
  TextLayout::RebaseClusterMaps(this);
  TextLayout::AlignVertically(this);
  TextLayout::AlignHorizontally(this);
  TextLayout::ReorientTextMetricsToWorld(this);
  v54 = *((_QWORD *)this + 37);
  *((_QWORD *)this + 37) = 0;
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  v55 = (__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 1;
  v56 = *((_QWORD *)this + 11);
  v57 = *((_QWORD *)this + 10);
  v58 = (v56 - v57) >> 2;
  if ( v55 < v58 )
  {
    v60 = v57 + 4 * v55;
LABEL_57:
    *((_QWORD *)this + 11) = v60;
  }
  else if ( v55 > v58 )
  {
    if ( v55 <= (*((_QWORD *)this + 12) - v57) >> 2 )
    {
      v59 = 4 * (v55 - v58);
      memset_0(*((void **)this + 11), 0, v59);
      v60 = v59 + v56;
      goto LABEL_57;
    }
    std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(
      (char *)this + 80,
      (__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 1);
  }
  v61 = *((_QWORD *)this + 13);
  v62 = (__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 1;
  if ( (*((_QWORD *)this + 14) - v61) >> 3 < v62 )
    v62 = (*((_QWORD *)this + 14) - v61) >> 3;
  v63 = (*((_QWORD *)this + 14) - v61) >> 3;
  if ( v62 < v63 )
  {
    v64 = v61 + 8 * v62;
  }
  else
  {
    if ( v62 <= v63 )
      goto LABEL_66;
    if ( v62 > (*((_QWORD *)this + 15) - v61) >> 3 )
    {
      std::vector<DWRITE_GLYPH_OFFSET>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 104);
      goto LABEL_66;
    }
    v64 = std::_Uninitialized_value_construct_n<std::allocator<DWRITE_FONT_AXIS_VALUE_FIXED>>(
            *((_QWORD *)this + 14),
            v62 - v63);
  }
  *((_QWORD *)this + 14) = v64;
LABEL_66:
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v106);
  if ( v65 != v6 )
  {
    v66 = *v65;
    *v65 = *v6;
    *v6 = v66;
    v67 = v65[1];
    v65[1] = *((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = v67;
    v68 = v65[2];
    v65[2] = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v68;
  }
  if ( v106[0] )
    std::_Deallocate<16>(v106[0], 2 * ((__int64)(v106[2] - v106[0]) >> 1));
  RecentFontCache::SaveToGlobalCache((RecentFontCache *)&v85);
  List<RecentFontCache::FontList,RecentFontCache::FontInstance>::DeleteElements(v89);
  if ( v87 )
    FontFallback::`scalar deleting destructor'(v87, v69);
  ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(&v86);
  std::wstring::_Tidy_deallocate(v107);
  return this;
}

```

## disassembly

```asm
0x1801853b0  mov     rax, rsp
0x1801853b3  mov     [rax+18h], rbx
0x1801853b7  push    rbp
0x1801853b8  push    rsi
0x1801853b9  push    rdi
0x1801853ba  push    r12
0x1801853bc  push    r13
0x1801853be  push    r14
0x1801853c0  push    r15
0x1801853c2  lea     rbp, [rsp-50h]
0x1801853c7  sub     rsp, 150h
0x1801853ce  movaps  xmmword ptr [rax-48h], xmm6
0x1801853d2  mov     rax, cs:__security_cookie
0x1801853d9  xor     rax, rsp
0x1801853dc  mov     [rbp+80h+var_50], rax
0x1801853e0  mov     r12, r8
0x1801853e3  mov     rbx, rdx
0x1801853e6  mov     [rsp+180h+var_138], rdx
0x1801853eb  mov     rdi, rcx
0x1801853ee  mov     [rbp+80h+var_90], rcx
0x1801853f2  lea     rax, ??_7TextLayout@@6BIDWriteTextAnalysisSource1@@@; const TextLayout::`vftable'{for `IDWriteTextAnalysisSource1'}
0x1801853f9  mov     [rcx], rax
0x1801853fc  lea     rax, ??_7TextLayout@@6BIDWriteTextAnalysisSink1@@@; const TextLayout::`vftable'{for `IDWriteTextAnalysisSink1'}
0x180185403  mov     [rcx+8], rax
0x180185407  lea     rax, ??_7TextLayout@@6BIDWritePrivateTextAnalysisSource@@@; const TextLayout::`vftable'{for `IDWritePrivateTextAnalysisSource'}
0x18018540e  mov     [rcx+10h], rax
0x180185412  mov     [rcx+18h], rdx
0x180185416  add     rcx, 20h ; ' '; void *
0x18018541a  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18018541f  nop
0x180185420  lea     rcx, [rdi+38h]; void *
0x180185424  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180185429  nop
0x18018542a  lea     r15, [rdi+50h]
0x18018542e  mov     rcx, r15; void *
0x180185431  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180185436  nop
0x180185437  lea     rcx, [rdi+68h]; void *
0x18018543b  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180185440  nop
0x180185441  lea     r13, [rdi+80h]
0x180185448  mov     rcx, r13; void *
0x18018544b  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180185450  nop
0x180185451  lea     rsi, [rdi+98h]
0x180185458  mov     rcx, rsi; void *
0x18018545b  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180185460  nop
0x180185461  lea     rcx, [rdi+0B0h]; void *
0x180185468  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18018546d  nop
0x18018546e  lea     rcx, [rdi+0C8h]; void *
0x180185475  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18018547a  nop
0x18018547b  add     rbx, 18h
0x18018547f  mov     [rdi+0E0h], rbx
0x180185486  mov     dword ptr [rdi+120h], 7F7FFFFFh
0x180185490  xor     r8d, r8d
0x180185493  mov     [rdi+128h], r8
0x18018549a  mov     [rdi+130h], r8
0x1801854a1  and     byte ptr [rdi+140h], 0FCh
0x1801854a8  mov     [rdi+148h], r8
0x1801854af  mov     rax, [rdi+18h]
0x1801854b3  mov     edx, [rax+68h]
0x1801854b6  shr     edx, 1
0x1801854b8  mov     ecx, [rax+64h]
0x1801854bb  shr     ecx, 1
0x1801854bd  xor     dl, cl
0x1801854bf  test    dl, 1
0x1801854c2  jnz     loc_180185DE5
0x1801854c8  mov     rbx, [rbx+10h]
0x1801854cc  mov     r14, [rsi+8]
0x1801854d0  mov     rdx, [rsi]
0x1801854d3  mov     rcx, r14
0x1801854d6  sub     rcx, rdx
0x1801854d9  sar     rcx, 1
0x1801854dc  cmp     rbx, rcx
0x1801854df  jb      short loc_180185508
0x1801854e1  jbe     short loc_180185510
0x1801854e3  mov     rax, [rsi+10h]
0x1801854e7  sub     rax, rdx
0x1801854ea  sar     rax, 1
0x1801854ed  cmp     rbx, rax
0x1801854f0  jbe     loc_180185C96
0x1801854f6  lea     r8, [rsp+180h+var_150]
0x1801854fb  mov     rdx, rbx
0x1801854fe  mov     rcx, rsi
0x180185501  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180185506  jmp     short loc_180185510
0x180185508  lea     rax, [rdx+rbx*2]
0x18018550c  mov     [rsi+8], rax
0x180185510  mov     rax, [rdi+0E0h]
0x180185517  mov     rcx, [rax+10h]
0x18018551b  mov     eax, 0FFFFFFFFh
0x180185520  cmp     rcx, rax
0x180185523  ja      loc_180185D75
0x180185529  lea     ebx, [rcx+rcx*2]
0x18018552c  shr     ebx, 1
0x18018552e  add     ebx, 10h
0x180185531  mov     [rsp+180h+var_158], rbx
0x180185536  lea     rcx, [rdi+38h]
0x18018553a  mov     rax, [rcx+10h]
0x18018553e  sub     rax, [rcx]
0x180185541  sar     rax, 1
0x180185544  cmp     rbx, rax
0x180185547  jbe     short loc_180185553
0x180185549  lea     rdx, [rsp+180h+var_158]
0x18018554e  call    ??$_Reallocate@$0A@@?$vector@GV?$allocator@G@std@@@std@@AEAAXAEA_K@Z; std::vector<ushort>::_Reallocate<0>(unsigned __int64 &)
0x180185553  mov     [rsp+180h+var_158], rbx
0x180185558  mov     rax, [r15+10h]
0x18018555c  sub     rax, [r15]
0x18018555f  sar     rax, 2
0x180185563  cmp     rbx, rax
0x180185566  jbe     short loc_180185575
0x180185568  lea     rdx, [rsp+180h+var_158]
0x18018556d  mov     rcx, r15
0x180185570  call    ??$_Reallocate@$0A@@?$vector@MV?$allocator@M@std@@@std@@AEAAXAEA_K@Z; std::vector<float>::_Reallocate<0>(unsigned __int64 &)
0x180185575  mov     rcx, rdi; this
0x180185578  call    ?InitializeTextMetrics@TextLayout@@AEAAXXZ; TextLayout::InitializeTextMetrics(void)
0x18018557d  xor     r8d, r8d
0x180185580  mov     edx, 400h
0x180185585  lea     rcx, [rbp+80h+var_70]
0x180185589  call    ?LocaleNameFromLCID@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H_N@Z; LocaleNameFromLCID(int,bool)
0x18018558e  nop
0x18018558f  lea     rcx, [rbp+80h+var_70]
0x180185593  call    ??$StartOf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@YAPEA_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; StartOf<std::wstring>(std::wstring &)
0x180185598  mov     rdx, [rbp+80h+var_60]; unsigned __int64
0x18018559c  mov     rcx, rax; wchar_t *
0x18018559f  call    ?ValidateAndNormalize@LanguageTagImpl@@SAXPEA_W_K@Z; LanguageTagImpl::ValidateAndNormalize(wchar_t *,unsigned __int64)
0x1801855a4  nop
0x1801855a5  mov     ecx, 48h ; 'H'; Size
0x1801855aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801855af  mov     rbx, rax
0x1801855b2  mov     [rsp+180h+var_140], rax
0x1801855b7  lea     r8, [rbp+80h+var_70]
0x1801855bb  cmp     [rbp+80h+var_58], 7
0x1801855c0  cmova   r8, [rbp+80h+var_70]
0x1801855c5  lea     rcx, [rax+8]
0x1801855c9  xor     r9d, r9d
0x1801855cc  xor     edx, edx
0x1801855ce  call    ??0NumberSubstitution@@QEAA@W4DWRITE_NUMBER_SUBSTITUTION_METHOD@@PEB_W_N@Z; NumberSubstitution::NumberSubstitution(DWRITE_NUMBER_SUBSTITUTION_METHOD,wchar_t const *,bool)
0x1801855d3  lea     rax, ??_7?$ComObject@VDWriteNumberSubstitution@@UDeleteOnZeroReference@@@@6B@; const ComObject<DWriteNumberSubstitution,DeleteOnZeroReference>::`vftable'
0x1801855da  mov     [rbx], rax
0x1801855dd  xor     esi, esi
0x1801855df  mov     [rbx+40h], esi
0x1801855e2  mov     rcx, rbx
0x1801855e5  mov     rax, cs:off_1803343B0
0x1801855ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801855f1  nop
0x1801855f2  mov     rcx, [rdi+128h]
0x1801855f9  mov     [rdi+128h], rbx
0x180185600  test    rcx, rcx
0x180185603  jz      short loc_180185612
0x180185605  mov     rax, [rcx]
0x180185608  mov     rax, [rax+10h]
0x18018560c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185611  nop
0x180185612  mov     ecx, 28h ; '('; Size
0x180185617  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018561c  mov     rbx, rax
0x18018561f  mov     [rsp+180h+var_140], rax
0x180185624  xorps   xmm0, xmm0
0x180185627  movups  xmmword ptr [rax], xmm0
0x18018562a  movups  xmmword ptr [rax+10h], xmm0
0x18018562e  mov     [rax+10h], rsi
0x180185632  mov     qword ptr [rax+18h], 4000h
0x18018563a  lea     rax, ??_7?$ComObject@VDWriteTextAnalyzer@@UDeleteOnZeroReference@@@@6BIDWriteTextAnalyzer2@@@; const ComObject<DWriteTextAnalyzer,DeleteOnZeroReference>::`vftable'{for `IDWriteTextAnalyzer2'}
0x180185641  mov     [rbx], rax
0x180185644  lea     rax, ??_7?$ComObject@VDWriteTextAnalyzer@@UDeleteOnZeroReference@@@@6BIDWritePrivateTextAnalyzer@@@; const ComObject<DWriteTextAnalyzer,DeleteOnZeroReference>::`vftable'{for `IDWritePrivateTextAnalyzer'}
0x18018564b  mov     [rbx+8], rax
0x18018564f  mov     [rbx+24h], esi
0x180185652  mov     rcx, rbx
0x180185655  mov     rax, cs:off_180334210
0x18018565c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185661  nop
0x180185662  mov     rcx, [rdi+130h]
0x180185669  mov     [rdi+130h], rbx
0x180185670  test    rcx, rcx
0x180185673  jz      short loc_180185682
0x180185675  mov     rax, [rcx]
0x180185678  mov     rax, [rax+10h]
0x18018567c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185681  nop
0x180185682  mov     rax, [rdi+18h]
0x180185686  mov     cl, [rax+161h]
0x18018568c  mov     [rsp+180h+var_14C], ecx
0x180185690  mov     dl, [rax+163h]
0x180185696  mov     ecx, [rax+7Ch]
0x180185699  mov     [rsp+180h+var_130], r12
0x18018569e  mov     [rsp+180h+var_128], rsi
0x1801856a3  mov     [rsp+180h+var_120], rsi
0x1801856a8  mov     [rsp+180h+var_118], ecx
0x1801856ac  mov     [rbp+80h+var_100], sil
0x1801856b0  lea     rax, [rsp+180h+var_110]
0x1801856b5  mov     [rsp+180h+var_110], rax
0x1801856ba  lea     rax, [rsp+180h+var_110]
0x1801856bf  mov     [rsp+180h+var_108], rax
0x1801856c4  mov     [rbp+80h+var_F8], dl
0x1801856c7  mov     [rbp+80h+var_F4], esi
0x1801856ca  test    dl, dl
0x1801856cc  jnz     short loc_180185702
0x1801856ce  lea     rbx, ?globalLock_@RecentFontCache@@0VLock@@A; Lock RecentFontCache::globalLock_
0x1801856d5  mov     [rsp+180h+var_140], rbx
0x1801856da  mov     rcx, rbx; lpCriticalSection
0x1801856dd  call    cs:__imp_EnterCriticalSection
0x1801856e3  nop
0x1801856e4  mov     eax, cs:?globalInvalidCount_@RecentFontCache@@0IA; uint RecentFontCache::globalInvalidCount_
0x1801856ea  mov     [rbp+80h+var_F4], eax
0x1801856ed  lea     rcx, [rsp+180h+var_110]
0x1801856f2  call    ??4FontList@RecentFontCache@@QEAAXAEBV01@@Z; RecentFontCache::FontList::operator=(RecentFontCache::FontList const &)
0x1801856f7  nop
0x1801856f8  mov     rcx, rbx; lpCriticalSection
0x1801856fb  call    cs:__imp_LeaveCriticalSection
0x180185701  nop
0x180185702  mov     [rsp+180h+var_160], esi
0x180185706  mov     r12, [rsp+180h+var_138]
0x18018570b  add     r12, 140h
0x180185712  mov     [rsp+180h+var_140], r12
0x180185717  xorps   xmm6, xmm6
0x18018571a  mov     edx, esi
0x18018571c  mov     rcx, [rdi+18h]
0x180185720  add     rcx, 140h
0x180185727  call    ?SetPosition@?$RunIndexer@VRunFormat@@@@QEAAX_K@Z; RunIndexer<RunFormat>::SetPosition(unsigned __int64)
0x18018572c  mov     rcx, [rdi+18h]
0x180185730  add     rcx, 140h
0x180185737  call    ?GetCurrentValue@?$RunIndexer@VRunFormat@@@@QEBAAEBVRunFormat@@XZ; RunIndexer<RunFormat>::GetCurrentValue(void)
0x18018573c  mov     r14, rax
0x18018573f  mov     rax, [rsp+180h+var_138]
0x180185744  mov     ebx, [rax+150h]
0x18018574a  mov     rcx, r12
0x18018574d  call    ?GetRunLength@?$RunIndexer@VRunFormat@@@@QEBA_KXZ; RunIndexer<RunFormat>::GetRunLength(void)
0x180185752  lea     ecx, [rax+rbx]
0x180185755  mov     r9d, ecx
0x180185758  sub     r9d, esi
0x18018575b  mov     [rsp+180h+var_148], r9d
0x180185760  mov     rdx, [rdi+0E0h]
0x180185767  mov     r8d, ecx
0x18018576a  cmp     r8, [rdx+10h]
0x18018576e  jb      loc_180185D10
0x180185774  xor     r8d, r8d
0x180185777  mov     [rbp+80h+var_E8], 0
0x18018577f  xorps   xmm0, xmm0
0x180185782  movaps  [rbp+80h+var_E0], xmm0
0x180185786  mov     [rbp+80h+var_D0], 0
0x18018578e  mov     [rbp+80h+var_C8], 0
0x180185795  mov     eax, 0C080h
0x18018579a  movzx   r12d, [rbp+80h+var_C4]
0x18018579f  and     r12w, ax
0x1801857a3  mov     [rbp+80h+var_C4], r12w
0x1801857a8  mov     [rbp+80h+var_C2], 0
0x1801857ae  mov     [rbp+80h+var_C0], 41800000h
0x1801857b5  mov     [rbp+80h+var_B8], r8
0x1801857b9  movdqa  [rbp+80h+var_B0], xmm0
0x1801857be  mov     [rbp+80h+var_98], 0
0x1801857c6  mov     [rbp+80h+var_F0], esi
0x1801857c9  mov     [rbp+80h+var_EC], r9d
0x1801857cd  mov     rax, [r14]
0x1801857d0  lock inc dword ptr [rax]
0x1801857d3  lea     rcx, ?empty_@RefString@DWrite@@0UData@12@A; struct DWrite::RefString::Data *
0x1801857da  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1801857df  mov     rax, [r14]
0x1801857e2  mov     [rbp+80h+var_A0], rax
0x1801857e6  mov     rdx, r14; struct RunFormat *
0x1801857e9  lea     rcx, [rsp+180h+var_130]; this
0x1801857ee  call    ?GetFontInstance@RecentFontCache@@AEAAPEAUFontInstance@1@AEBVRunFormat@@@Z; RecentFontCache::GetFontInstance(RunFormat const &)
0x1801857f3  mov     rbx, rax
0x1801857f6  mov     rsi, [rax+18h]
0x1801857fa  test    rsi, rsi
0x1801857fd  jnz     loc_180185C40
0x180185803  cmp     [rax+20h], rsi
0x180185807  jz      loc_180185C63
0x18018580d  mov     [rsp+180h+var_158], 0
0x180185816  mov     rcx, [rbx+20h]
0x18018581a  mov     rax, [rcx]
0x18018581d  lea     rdx, [rsp+180h+var_158]
0x180185822  mov     rax, [rax+68h]
0x180185826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018582b  mov     rcx, [rsp+180h+var_158]
0x180185830  test    rcx, rcx
0x180185833  jz      loc_180185DCE
0x180185839  mov     rax, [rcx]
0x18018583c  lea     r8, [rbx+18h]
0x180185840  lea     rdx, _GUID_ba6f3da5_0780_4422_9fae_eab429b786b4
0x180185847  mov     rax, [rax]
0x18018584a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018584f  test    eax, eax
0x180185851  js      loc_180185E39
0x180185857  mov     rcx, [rsp+180h+var_158]
0x18018585c  mov     rsi, [rbx+18h]
0x180185860  test    rcx, rcx
0x180185863  jz      short loc_180185872
0x180185865  mov     rax, [rcx]
0x180185868  mov     rax, [rax+10h]
0x18018586c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185871  nop
0x180185872  test    rsi, rsi
0x180185875  jz      short loc_180185887
0x180185877  mov     rax, [rsi]
0x18018587a  mov     rcx, rsi
0x18018587d  mov     rax, [rax+8]
  ... truncated ...
```
