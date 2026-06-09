# TextLayout::MapCharacters(RecentFontCache &,unsigned __int64,unsigned __int64)

- ea: `0x18017ab6c`
- end: `0x18017b708`
- name: `?MapCharacters@TextLayout@@AEAA_KAEAVRecentFontCache@@_K1@Z`
- size: `2972`
- prototype: `unsigned __int64 __fastcall(TextLayout *__hidden this, struct RecentFontCache *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18017a7a8`

## callees

- `0x18011ed18`
- `0x180131390`
- `0x180134718`
- `0x180134f04`
- `0x1801372f0`
- `0x180137e50`
- `0x180139230`
- `0x180154068`
- `0x18015d4d4`
- `0x180164568`
- `0x180177f14`
- `0x180177f48`
- `0x180179f60`
- `0x18017a268`
- `0x18017a3bc`
- `0x18017a6c4`
- `0x18017ab6c`
- `0x18017bbec`
- `0x18017ed00`
- `0x18017ee48`
- `0x1801cac68`
- `0x1801ccb18`
- `0x1801d2848`
- `0x1801d53e0`
- `0x1801f2fe4`
- `0x1801f37b0`
- `0x18020c470`
- `0x18020c4ac`
- `0x18020c4e8`
- `0x18020c834`
- `0x180212490`
- `0x18022aca0`
- `0x180330010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18017affb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18017b51e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18017affb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18017b51e`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
unsigned __int64 __fastcall TextLayout::MapCharacters(
        TextLayout *this,
        struct RecentFontCache *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v6; // rdi
  __int64 v7; // r14
  unsigned __int64 v8; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx
  unsigned __int64 v11; // r13
  unsigned __int64 *v12; // rsi
  _QWORD *v13; // rcx
  unsigned __int64 v14; // rax
  struct RunFormat *CurrentValue; // rbx
  unsigned __int64 v16; // r13
  __int16 v17; // r9
  unsigned __int64 v19; // rax
  void *v20; // r11
  void *v21; // rcx
  __int64 v22; // rax
  struct RunFormat *v23; // r10
  _DWORD *v24; // rdx
  __int64 v25; // rcx
  void (__fastcall ***v26)(_QWORD, GUID *, _QWORD *); // rax
  _DWORD *v27; // r9
  _DWORD *v28; // r11
  _DWORD *v29; // r8
  struct FontFallback *SystemFontFallbackWeakRef; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rbx
  struct IDWriteFont *v34; // rdx
  struct RecentFontCache::FontInstance *v35; // rax
  __int64 *v36; // rbx
  __int64 v37; // rcx
  __int64 v38; // r9
  __int64 v39; // r14
  unsigned __int64 v40; // rbx
  int v41; // eax
  _DWORD *v42; // rcx
  int v43; // eax
  struct IDWritePrivateFontFace *FontFace; // rax
  struct IDWritePrivateFontFace *v45; // rbx
  __int64 v46; // rcx
  int v47; // eax
  int v48; // eax
  struct IDWriteFont *v49; // rcx
  int v50; // eax
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // r8
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rcx
  void *v55; // rcx
  struct RecentFontCache::FontInstance *FontInstance; // rax
  struct RecentFontCache::FontInstance *v57; // rbx
  __int64 v58; // rsi
  __int64 v59; // rdx
  _QWORD *v60; // rcx
  unsigned int v62; // ebx
  char32_t v63; // eax
  UcdInternal *v64; // rcx
  char32_t v65; // r10d
  unsigned int Property32; // eax
  _QWORD *v67; // rcx
  unsigned __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rcx
  IndexOutOfRangeException *v71; // rax
  struct IDWriteFont *Font; // rax
  struct IDWriteFont *v73; // rdx
  char v74; // [rsp+80h] [rbp-80h]
  char v75; // [rsp+80h] [rbp-80h]
  unsigned int v76; // [rsp+84h] [rbp-7Ch] BYREF
  void (__fastcall ***v77)(_QWORD, GUID *, void **); // [rsp+88h] [rbp-78h] BYREF
  struct IDWriteFont *v78; // [rsp+90h] [rbp-70h] BYREF
  float v79; // [rsp+98h] [rbp-68h] BYREF
  __int64 v80; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v81; // [rsp+A8h] [rbp-58h] BYREF
  struct RunFormat *v82; // [rsp+B0h] [rbp-50h]
  struct IDWriteFont *v83; // [rsp+B8h] [rbp-48h] BYREF
  RecentFontCache *v84; // [rsp+C0h] [rbp-40h]
  wchar_t v85; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD *v86; // [rsp+D0h] [rbp-30h]
  _DWORD *v87; // [rsp+D8h] [rbp-28h]
  void *v88; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v89; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v90; // [rsp+F8h] [rbp-8h]
  struct IDWriteFont *v91; // [rsp+100h] [rbp+0h]
  void *v92; // [rsp+108h] [rbp+8h]
  __int64 v93; // [rsp+110h] [rbp+10h]
  wchar_t *v94; // [rsp+118h] [rbp+18h]
  _BYTE v95[16]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v96; // [rsp+130h] [rbp+30h]
  wchar_t *v97; // [rsp+160h] [rbp+60h] BYREF
  _BYTE *v98; // [rsp+168h] [rbp+68h]
  void *Block; // [rsp+170h] [rbp+70h]
  int v100; // [rsp+178h] [rbp+78h]
  int v101; // [rsp+180h] [rbp+80h]
  _BYTE v102[168]; // [rsp+188h] [rbp+88h] BYREF

  v84 = a2;
  v6 = 96 * a3;
  v7 = *((_QWORD *)this + 4);
  v8 = *(unsigned int *)(v7 + 96 * a3);
  v9 = (_QWORD *)(v8 + a4);
  if ( v8 + a4 < v8 || (unsigned __int64)v9 > 0xFFFFFFFF )
    goto LABEL_64;
  v10 = (_QWORD *)(*((_QWORD *)this + 3) + 320LL);
  v11 = (unsigned int)v9;
  v12 = (unsigned __int64 *)(*((_QWORD *)this + 3) + 328LL);
  if ( (unsigned __int64)(unsigned int)v9 < *(_QWORD *)(*((_QWORD *)this + 3) + 336LL) )
  {
    *v12 = 0;
    v10[2] = 0;
    v10[3] = 0;
  }
  while ( 1 )
  {
    v13 = *(_QWORD **)(*v10 + 96LL);
    a2 = (struct RecentFontCache *)(v13 + 1);
    v14 = v13 ? 0x4EC4EC4EC4EC4EC5LL * ((__int64)(*(_QWORD *)a2 - *v13) >> 3) : 0LL;
    if ( v14 <= *v12 )
      break;
    if ( !v13 || (v9 = (_QWORD *)*v13, *v12 >= 0x4EC4EC4EC4EC4EC5LL * ((__int64)(*(_QWORD *)a2 - (_QWORD)v9) >> 3)) )
    {
      v71 = IndexOutOfRangeException::IndexOutOfRangeException((IndexOutOfRangeException *)&v77, a2);
      LogAndThrow<IndexOutOfRangeException>(v71, 0x6365766E7572LL, 205);
    }
    v19 = v10[2] + v9[13 * *v12 + 12];
    if ( v19 < v10[2] )
      goto LABEL_64;
    if ( v19 > v11 )
      break;
    v10[2] = v19;
    SafeInt<unsigned __int64,SafeIntExceptionHandler<Exception>>::operator++(v12, a2, 0x4EC4EC4EC4EC4EC5LL);
  }
  v10[3] = v11;
  CurrentValue = (struct RunFormat *)RunIndexer<RunFormat>::GetCurrentValue(
                                       *((_QWORD *)this + 3) + 320LL,
                                       a2,
                                       0x4EC4EC4EC4EC4EC5LL);
  v82 = CurrentValue;
  v16 = 0;
  if ( *(_QWORD *)(v7 + v6 + 72)
    || (*(_BYTE *)(v7 + v6 + 92) & 1) != 0
    || (v17 = *(_WORD *)(v7 + v6 + 44), (v17 & 0x20) != 0)
    || (v17 & 0x10) != 0
    || *(_BYTE *)(*((_QWORD *)this + 3) + 355LL) )
  {
    if ( !*(_QWORD *)(v7 + v6 + 56) )
    {
      FontFace = RecentFontCache::GetFontFace(v84, CurrentValue, 1);
      v45 = FontFace;
      if ( FontFace )
        (*(void (__fastcall **)(struct IDWritePrivateFontFace *))(*(_QWORD *)FontFace + 8LL))(FontFace);
      v46 = *(_QWORD *)(v7 + v6 + 56);
      *(_QWORD *)(v7 + v6 + 56) = v45;
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    return *(unsigned int *)(v7 + v6 + 4);
  }
  v51 = *(unsigned int *)(v7 + v6);
  v52 = v51 + a4;
  if ( v51 + a4 < v51 || v52 > 0xFFFFFFFF )
    goto LABEL_64;
  v9 = (_QWORD *)*((_QWORD *)this + 28);
  if ( v9[3] > 7u )
    v9 = (_QWORD *)*v9;
  a2 = (struct RecentFontCache *)*(unsigned int *)(v7 + v6 + 4);
  if ( a4 > (unsigned __int64)a2 )
LABEL_64:
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v9, a2);
  v94 = (wchar_t *)v9 + (unsigned int)v52;
  v53 = (unsigned int)((_DWORD)a2 - a4);
  v78 = (struct IDWriteFont *)v53;
  v89 = v94;
  v54 = 0;
  v90 = 0;
  v91 = (struct IDWriteFont *)v53;
  v92 = 0;
  if ( (*(_BYTE *)(v7 + v6 + 46) & 1) != 0 || (v17 & 8) != 0 )
  {
    v62 = 0;
    while ( v54 < v53 )
    {
      v63 = TextIterator::operator*((TextIterator *)&v89);
      v65 = v63;
      if ( (*(_BYTE *)(v7 + v6 + 44) & 8) != 0 )
        v62 = NumberSubstitution::MapChar((NumberSubstitution *)(*((_QWORD *)this + 37) + 8LL), v63);
      else
        v62 = v63;
      if ( (*(_BYTE *)(v7 + v6 + 46) & 1) != 0 )
      {
        Property32 = UcdInternal::GetProperty32(v64, v62, v52);
        if ( Property32 )
          v62 = Property32;
      }
      if ( v62 != v65 )
        break;
      v16 += TextIterator::Advance((TextIterator *)&v89);
      v53 = (unsigned __int64)v91;
      v54 = v90;
    }
    if ( v16 )
    {
      v78 = (struct IDWriteFont *)v16;
    }
    else
    {
      v94 = &v85;
      v16 = ConvertUtf32ToUtf16(v62, &v85, v52);
      v78 = (struct IDWriteFont *)TextIterator::Advance((TextIterator *)&v89);
    }
    CurrentValue = v82;
  }
  else
  {
    v16 = (unsigned int)v53;
  }
  v55 = v92;
  if ( v92 )
  {
    if ( (*(_DWORD *)v92)-- == 1 )
      RefCountedArrayImpl::Data::operator delete(v55);
  }
  FontInstance = RecentFontCache::GetFontInstance(v84, CurrentValue);
  v57 = FontInstance;
  v58 = *((_QWORD *)FontInstance + 4);
  if ( v58 )
  {
    if ( *((_BYTE *)FontInstance + 72) && !*((_BYTE *)FontInstance + 73) )
      goto LABEL_98;
  }
  else if ( !*((_BYTE *)FontInstance + 73) )
  {
    RecentFontCache::GetFirstMatchingFont(v84, FontInstance);
    v58 = *((_QWORD *)v57 + 4);
    if ( v58 )
    {
LABEL_98:
      v93 = v58;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 8LL))(v58);
      goto LABEL_99;
    }
    *((_BYTE *)v57 + 73) = 1;
  }
  v93 = 0;
  v58 = 0;
LABEL_99:
  v83 = 0;
  v76 = 0;
  v79 = 1.0;
  v59 = *((_QWORD *)this + 3);
  v60 = (_QWORD *)(v59 + 184);
  if ( *(_QWORD *)(v59 + 208) > 7u )
    v60 = (_QWORD *)*v60;
  if ( v16 > 0xFFFFFFFF )
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v60, v59);
  StackTextAnalysisSource::StackTextAnalysisSource(
    v95,
    v94,
    (unsigned int)v16,
    *(_QWORD *)(v7 + v6 + 80) + 8LL,
    v60,
    *(_DWORD *)(v59 + 104),
    *((_QWORD *)this + 37));
  v21 = v20;
  v88 = v20;
  v22 = *((_QWORD *)this + 3);
  v77 = *(void (__fastcall ****)(_QWORD, GUID *, void **))(v22 + 168);
  v97 = (wchar_t *)v102;
  v98 = v102;
  Block = v20;
  v100 = (int)v20;
  v101 = 20;
  v23 = v82;
  v24 = (_DWORD *)(v22 + 124);
  if ( *(_DWORD *)(*((_QWORD *)v82 + 11) + 4LL) || *v24 != (_DWORD)v20 )
  {
    v74 = 1;
    v87 = (_DWORD *)((char *)v82 + 28);
    v86 = (_DWORD *)((char *)v82 + 32);
    v81 = (_DWORD *)((char *)v82 + 24);
    v25 = *((_QWORD *)v82 + 11);
    v89 = (wchar_t *)(v25 + 8);
    v90 = v25 + 8LL * *(unsigned int *)(v25 + 4) + 8;
    CompleteMissingAxisValues(
      *((_DWORD *)v82 + 6),
      *((_DWORD *)v82 + 8),
      *((_DWORD *)v82 + 7),
      (_DWORD)v82 + 32,
      *v24,
      (__int64)&v89,
      (__int64)&v97);
    v26 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v77;
    if ( v77 )
    {
      (**v77)(v77, &GUID_2397599d_dd0d_4681_bd6a_f4f31eaade77, &v88);
      v21 = v88;
      v23 = v82;
      v29 = v86;
      v27 = v87;
      v28 = v81;
      v26 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v77;
      goto LABEL_23;
    }
    v27 = v87;
    v28 = v81;
    v29 = v86;
    v21 = v88;
    v23 = v82;
  }
  else
  {
    v74 = (char)v20;
    v29 = (_DWORD *)((char *)v82 + 32);
    v27 = (_DWORD *)((char *)v82 + 28);
    v28 = (_DWORD *)((char *)v82 + 24);
    v26 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v77;
  }
  v86 = v29;
  v81 = v28;
  v87 = v27;
LABEL_23:
  v80 = 0;
  if ( v21 )
  {
    v81 = 0;
    v41 = (*(__int64 (__fastcall **)(void *, _BYTE *, _QWORD, _QWORD, _QWORD, __int64, wchar_t *, _DWORD, unsigned int *, float *, _DWORD **))(*(_QWORD *)v21 + 32LL))(
            v21,
            v95,
            0,
            v96,
            *((_QWORD *)v23 + 2),
            *((_QWORD *)v23 + 1) + 8LL,
            v97,
            (v98 - (_BYTE *)v97) >> 3,
            &v76,
            &v79,
            &v81);
    if ( v41 < 0 )
    {
      Exception::Exception((Exception *)&v77, v41, 0);
      LogAndThrow<OSException>(&v77, 0x686370616D6CLL, 1799);
    }
    v42 = v81;
    if ( v81 )
    {
      v43 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v81)(
              v81,
              &GUID_ba6f3da5_0780_4422_9fae_eab429b786b4,
              &v80);
      if ( v43 < 0 )
      {
        Exception::Exception((Exception *)&v77, v43, 0);
        LogAndThrow<OSException>(&v77, 0x686370616D6CLL, 1802);
      }
      v42 = v81;
    }
    if ( v42 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v42 + 16LL))(v42);
  }
  else if ( v26 )
  {
    v47 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, void **), _BYTE *, _QWORD, _QWORD, _QWORD, __int64, _DWORD, _DWORD, _DWORD, unsigned int *, struct IDWriteFont **, float *))(*v26)[3])(
            v77,
            v95,
            0,
            v96,
            *((_QWORD *)v23 + 2),
            *((_QWORD *)v23 + 1) + 8LL,
            *v28,
            *v27,
            *v29,
            &v76,
            &v83,
            &v79);
    LogAndThrowIfFailed<OSException>(v47);
  }
  else
  {
    SystemFontFallbackWeakRef = RecentFontCache::GetSystemFontFallbackWeakRef(v84);
    v89 = v97;
    v90 = (__int64)&v97[4 * ((v98 - (_BYTE *)v97) >> 3)];
    FontFallback::MapCharacters(
      SystemFontFallbackWeakRef,
      v95,
      0,
      v96,
      *((_QWORD *)v82 + 2),
      v58,
      *((_QWORD *)v82 + 1) + 8LL,
      &v89,
      v74,
      *v81,
      *v87,
      *v86,
      &v76,
      &v83,
      &v79);
  }
  v32 = v76;
  if ( v76 > v16 )
  {
    Exception::Exception((Exception *)&v77, -2147024809, 0);
    LogAndThrow<ArgumentOutOfRangeException>(&v77, 0x686370616DLL, 1846);
  }
  if ( v94 == &v85 && v76 )
  {
    if ( (unsigned __int64)v78 > 0xFFFFFFFF )
      goto LABEL_73;
    v32 = (unsigned int)v78;
    v76 = (unsigned int)v78;
    v16 = (unsigned __int64)v78;
  }
  v75 = 0;
  if ( !(_DWORD)v32 )
  {
    v67 = (_QWORD *)*((_QWORD *)this + 28);
    if ( v67[3] > 7u )
      v67 = (_QWORD *)*v67;
    v89 = (wchar_t *)v67 + *(unsigned int *)(v7 + v6);
    v90 = a4;
    v91 = (struct IDWriteFont *)*(unsigned int *)(v7 + v6 + 4);
    v92 = 0;
    v68 = TextIterator::Advance((TextIterator *)&v89);
    if ( v68 > 0xFFFFFFFF )
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v70, v69);
    v76 = v68;
    v75 = 1;
    v16 = *(unsigned int *)(v7 + v6 + 4);
    TextIterator::~TextIterator((TextIterator *)&v89);
    v32 = v76;
  }
  v33 = v80;
  if ( !v80 )
  {
    v34 = v83;
    if ( !v83 )
    {
      Font = RecentFontCache::GetFont(v84, v82, 1);
      ComPtr<IDWriteFont>::ComPtr<IDWriteFont>(&v78, Font);
      v73 = v83;
      v83 = v78;
      v78 = v73;
      ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(&v78);
      v34 = v83;
    }
    v35 = RecentFontCache::GetFontInstance(v84, v34);
    v36 = (__int64 *)((char *)v35 + 24);
    if ( !*((_QWORD *)v35 + 3) )
    {
      v78 = 0;
      v48 = (*(__int64 (__fastcall **)(_QWORD, struct IDWriteFont **))(**((_QWORD **)v35 + 4) + 104LL))(
              *((_QWORD *)v35 + 4),
              &v78);
      if ( v48 < 0 )
      {
        Exception::Exception((Exception *)&v77, v48, 0);
        LogAndThrow<CallbackException>(&v77, 0x74756F79616CLL, 247);
      }
      v49 = v78;
      if ( v78 )
      {
        v50 = (**(__int64 (__fastcall ***)(struct IDWriteFont *, GUID *, __int64 *))v78)(
                v78,
                &GUID_ba6f3da5_0780_4422_9fae_eab429b786b4,
                v36);
        if ( v50 < 0 )
        {
          Exception::Exception((Exception *)&v77, v50, 0);
          LogAndThrow<CallbackException>(&v77, 0x74756F79616CLL, 247);
        }
        v49 = v78;
      }
      if ( v49 )
        (*(void (__fastcall **)(struct IDWriteFont *))(*(_QWORD *)v49 + 16LL))(v49);
    }
    v33 = *v36;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
    v37 = v80;
    v80 = v33;
    if ( v37 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v33 = v80;
    }
    v32 = v76;
  }
  if ( !a4 || !v75 && v33 == *(_QWORD *)(v7 + v6 + 56) )
  {
    if ( (unsigned int)v32 == v16 )
    {
LABEL_43:
      v39 = *((_QWORD *)this + 4);
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
      ComPtr<IDWriteFontFamily>::Deref(v39 + v6 + 56);
      *(_QWORD *)(v39 + v6 + 56) = v80;
      *(float *)(v6 + *((_QWORD *)this + 4) + 48) = v79 * *(float *)(v6 + *((_QWORD *)this + 4) + 48);
      v40 = a4 + v76;
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      free(Block);
      if ( v88 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v88 + 16LL))(v88);
      if ( v83 )
        (*(void (__fastcall **)(struct IDWriteFont *))(*(_QWORD *)v83 + 16LL))(v83);
      if ( v58 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      return v40;
    }
    if ( a4 <= 0xFFFFFFFF )
    {
      v38 = (unsigned int)(a4 + v32);
      if ( (unsigned int)v38 >= (unsigned int)a4 )
      {
        TextLayout::SplitSpan(this, &v78, v6 + *((_QWORD *)this + 4), v38);
        v33 = v80;
        goto LABEL_43;
      }
    }
LABEL_73:
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v32, v31);
  }
  if ( a4 > 0xFFFFFFFF )
    goto LABEL_73;
  TextLayout::SplitSpan(this, &v78, v6 + *((_QWORD *)this + 4), (unsigned int)a4);
  *(_DWORD *)(v6 + *((_QWORD *)this + 4) + 144) = *((_DWORD *)v82 + 9);
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  free(Block);
  if ( v88 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v88 + 16LL))(v88);
  if ( v83 )
    (*(void (__fastcall **)(struct IDWriteFont *))(*(_QWORD *)v83 + 16LL))(v83);
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  return a4;
}

```

## disassembly

```asm
0x18017ab6c  mov     [rsp-8+arg_18], rbx
0x18017ab71  push    rbp
0x18017ab72  push    rsi
0x18017ab73  push    rdi
0x18017ab74  push    r12
0x18017ab76  push    r13
0x18017ab78  push    r14
0x18017ab7a  push    r15
0x18017ab7c  lea     rbp, [rsp-140h]
0x18017ab84  sub     rsp, 240h
0x18017ab8b  mov     rax, cs:__security_cookie
0x18017ab92  xor     rax, rsp
0x18017ab95  mov     [rbp+170h+var_40], rax
0x18017ab9c  mov     r12, r9
0x18017ab9f  mov     [rbp+170h+var_1B0], rdx
0x18017aba3  mov     r15, rcx
0x18017aba6  lea     rdi, [r8+r8*2]
0x18017abaa  shl     rdi, 5
0x18017abae  mov     r14, [rcx+20h]
0x18017abb2  mov     eax, [r14+rdi]
0x18017abb6  lea     rcx, [rax+r9]
0x18017abba  cmp     rcx, rax
0x18017abbd  jb      loc_18017B14C
0x18017abc3  mov     eax, 0FFFFFFFFh
0x18017abc8  cmp     rcx, rax
0x18017abcb  ja      loc_18017B14C
0x18017abd1  mov     rbx, [r15+18h]
0x18017abd5  add     rbx, 140h
0x18017abdc  mov     r13d, ecx
0x18017abdf  lea     rsi, [rbx+8]
0x18017abe3  cmp     r13, [rbx+10h]
0x18017abe7  jnb     short loc_18017AC00
0x18017abe9  mov     qword ptr [rsi], 0
0x18017abf0  mov     qword ptr [rbx+10h], 0
0x18017abf8  mov     qword ptr [rbx+18h], 0
0x18017ac00  mov     r8, 4EC4EC4EC4EC4EC5h
0x18017ac0a  mov     rax, [rbx]
0x18017ac0d  mov     rcx, [rax+60h]
0x18017ac11  lea     rdx, [rcx+8]; void *
0x18017ac15  test    rcx, rcx
0x18017ac18  jz      loc_18017B070
0x18017ac1e  mov     rax, [rdx]
0x18017ac21  sub     rax, [rcx]
0x18017ac24  sar     rax, 3
0x18017ac28  imul    rax, r8
0x18017ac2c  cmp     rax, [rsi]
0x18017ac2f  ja      short loc_18017AC83
0x18017ac31  mov     [rbx+18h], r13
0x18017ac35  mov     rcx, [r15+18h]
0x18017ac39  add     rcx, 140h
0x18017ac40  call    ?GetCurrentValue@?$RunIndexer@VRunFormat@@@@QEBAAEBVRunFormat@@XZ; RunIndexer<RunFormat>::GetCurrentValue(void)
0x18017ac45  mov     rbx, rax
0x18017ac48  mov     [rbp+170h+var_1C0], rax
0x18017ac4c  xor     r13d, r13d
0x18017ac4f  cmp     [r14+rdi+48h], r13
0x18017ac54  jnz     short loc_18017AC6E
0x18017ac56  test    byte ptr [r14+rdi+5Ch], 1
0x18017ac5c  jnz     short loc_18017AC6E
0x18017ac5e  movzx   r9d, word ptr [r14+rdi+2Ch]
0x18017ac64  test    r9b, 20h
0x18017ac68  jz      loc_18017B2D6
0x18017ac6e  cmp     [r14+rdi+38h], r13
0x18017ac73  jz      loc_18017B152
0x18017ac79  mov     eax, [r14+rdi+4]
0x18017ac7e  jmp     loc_18017B046
0x18017ac83  test    rcx, rcx
0x18017ac86  jz      loc_18017B5EB
0x18017ac8c  mov     rcx, [rcx]
0x18017ac8f  mov     rax, [rdx]
0x18017ac92  sub     rax, rcx
0x18017ac95  sar     rax, 3
0x18017ac99  imul    rax, r8
0x18017ac9d  cmp     [rsi], rax
0x18017aca0  jnb     loc_18017B5EB
0x18017aca6  imul    rax, [rsi], 68h ; 'h'
0x18017acaa  mov     rax, [rax+rcx+60h]
0x18017acaf  add     rax, [rbx+10h]
0x18017acb3  cmp     rax, [rbx+10h]
0x18017acb7  jb      loc_18017B14C
0x18017acbd  cmp     rax, r13
0x18017acc0  ja      loc_18017AC31
0x18017acc6  mov     [rbx+10h], rax
0x18017acca  mov     rcx, rsi
0x18017accd  call    ??E?$SafeInt@_KV?$SafeIntExceptionHandler@VException@@@@@@QEAAAEAV0@XZ; SafeInt<unsigned __int64,SafeIntExceptionHandler<Exception>>::operator++(void)
0x18017acd2  jmp     loc_18017AC00
0x18017acd7  mov     eax, 0FFFFFFFFh
0x18017acdc  cmp     r13, rax
0x18017acdf  ja      loc_18017B1D1
0x18017ace5  mov     r9, [r14+rdi+50h]
0x18017acea  add     r9, 8
0x18017acee  mov     r8d, r13d
0x18017acf1  mov     rax, [r15+128h]
0x18017acf8  mov     [rsp+270h+var_240], rax
0x18017acfd  mov     eax, [rdx+68h]
0x18017ad00  mov     dword ptr [rsp+270h+var_248], eax
0x18017ad04  mov     [rsp+270h+var_250], rcx
0x18017ad09  mov     rdx, [rbp+170h+var_158]
0x18017ad0d  lea     rcx, [rbp+170h+var_150]
0x18017ad11  call    ??0StackTextAnalysisSource@@QEAA@PEB_WI00W4DWRITE_READING_DIRECTION@@PEAUIDWriteNumberSubstitution@@@Z; StackTextAnalysisSource::StackTextAnalysisSource(wchar_t const *,uint,wchar_t const *,wchar_t const *,DWRITE_READING_DIRECTION,IDWriteNumberSubstitution *)
0x18017ad16  mov     rcx, r11
0x18017ad19  mov     [rbp+170h+var_190], rcx
0x18017ad1d  mov     rax, [r15+18h]
0x18017ad21  mov     r10, [rax+0A8h]
0x18017ad28  mov     [rbp+170h+var_1E8], r10
0x18017ad2c  lea     rdx, [rbp+170h+var_E8]
0x18017ad33  mov     [rbp+170h+var_110], rdx
0x18017ad37  lea     rdx, [rbp+170h+var_E8]
0x18017ad3e  mov     [rbp+170h+var_108], rdx
0x18017ad42  mov     [rbp+170h+Block], r11
0x18017ad46  mov     [rbp+170h+var_F8], r11d
0x18017ad4a  mov     rbx, 686370616D6Ch
0x18017ad54  mov     [rbp+170h+var_F0], 14h
0x18017ad5e  mov     r10, [rbp+170h+var_1C0]
0x18017ad62  mov     rdx, [r10+58h]
0x18017ad66  mov     r8d, [rdx+4]
0x18017ad6a  lea     rdx, [rax+7Ch]
0x18017ad6e  test    r8d, r8d
0x18017ad71  jz      loc_18017B12A
0x18017ad77  mov     [rbp+170h+var_1F0], 1
0x18017ad7b  lea     r8, [r10+1Ch]
0x18017ad7f  mov     [rbp+170h+var_198], r8
0x18017ad83  lea     r9, [r10+20h]
0x18017ad87  mov     [rbp+170h+var_1A0], r9
0x18017ad8b  lea     r11, [r10+18h]
0x18017ad8f  mov     [rbp+170h+var_1C8], r11
0x18017ad93  mov     rcx, [r10+58h]
0x18017ad97  lea     rax, [rcx+8]
0x18017ad9b  mov     [rbp+170h+var_180], rax
0x18017ad9f  mov     eax, [rcx+4]
0x18017ada2  lea     rcx, [rcx+rax*8]
0x18017ada6  add     rcx, 8
0x18017adaa  mov     [rbp+170h+var_178], rcx
0x18017adae  lea     rax, [rbp+170h+var_110]
0x18017adb2  mov     [rsp+270h+var_240], rax
0x18017adb7  lea     rax, [rbp+170h+var_180]
0x18017adbb  mov     [rsp+270h+var_248], rax
0x18017adc0  mov     eax, [rdx]
0x18017adc2  mov     dword ptr [rsp+270h+var_250], eax
0x18017adc6  movss   xmm3, dword ptr [r10+24h]
0x18017adcc  mov     r8d, [r8]
0x18017adcf  mov     edx, [r9]
0x18017add2  mov     ecx, [r11]
0x18017add5  call    ?CompleteMissingAxisValues@@YAXW4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STRETCH@@W4DWRITE_FONT_STYLE@@MW4DWRITE_AUTOMATIC_FONT_AXES@@V?$array_ref@$$CBUDWRITE_FONT_AXIS_VALUE@@@@AEAV?$ScopedArrayWithFixedBuffer@UDWRITE_FONT_AXIS_VALUE@@@@@Z; CompleteMissingAxisValues(DWRITE_FONT_WEIGHT,DWRITE_FONT_STRETCH,DWRITE_FONT_STYLE,float,DWRITE_AUTOMATIC_FONT_AXES,array_ref<DWRITE_FONT_AXIS_VALUE const>,ScopedArrayWithFixedBuffer<DWRITE_FONT_AXIS_VALUE> &)
0x18017adda  mov     rax, [rbp+170h+var_1E8]
0x18017adde  test    rax, rax
0x18017ade1  jnz     loc_18017B19A
0x18017ade7  mov     r9, [rbp+170h+var_198]
0x18017adeb  mov     r11, [rbp+170h+var_1C8]
0x18017adef  mov     r8, [rbp+170h+var_1A0]
0x18017adf3  mov     rcx, [rbp+170h+var_190]
0x18017adf7  mov     r10, [rbp+170h+var_1C0]
0x18017adfb  mov     [rbp+170h+var_1A0], r8
0x18017adff  mov     [rbp+170h+var_1C8], r11
0x18017ae03  mov     [rbp+170h+var_198], r9
0x18017ae07  mov     [rbp+170h+var_1D0], 0
0x18017ae0f  test    rcx, rcx
0x18017ae12  jnz     loc_18017B077
0x18017ae18  test    rax, rax
0x18017ae1b  jnz     loc_18017B1D7
0x18017ae21  mov     rcx, [rbp+170h+var_1B0]; this
0x18017ae25  call    ?GetSystemFontFallbackWeakRef@RecentFontCache@@QEAAPEAVFontFallback@@XZ; RecentFontCache::GetSystemFontFallbackWeakRef(void)
0x18017ae2a  mov     r10, rax
0x18017ae2d  mov     rdx, [rbp+170h+var_110]
0x18017ae31  mov     [rbp+170h+var_180], rdx
0x18017ae35  mov     rcx, [rbp+170h+var_108]
0x18017ae39  sub     rcx, rdx
0x18017ae3c  sar     rcx, 3
0x18017ae40  lea     rcx, [rdx+rcx*8]
0x18017ae44  mov     [rbp+170h+var_178], rcx
0x18017ae48  mov     rdx, [rbp+170h+var_1C0]
0x18017ae4c  mov     rcx, [rdx+8]
0x18017ae50  add     rcx, 8
0x18017ae54  lea     rax, [rbp+170h+var_1D8]
0x18017ae58  mov     [rsp+270h+var_200], rax
0x18017ae5d  lea     rax, [rbp+170h+var_1B8]
0x18017ae61  mov     [rsp+270h+var_208], rax
0x18017ae66  lea     rax, [rbp+170h+var_1EC]
0x18017ae6a  mov     [rsp+270h+var_210], rax
0x18017ae6f  mov     r9, [rbp+170h+var_1A0]
0x18017ae73  mov     eax, [r9]
0x18017ae76  mov     dword ptr [rsp+270h+var_218], eax
0x18017ae7a  mov     r8, [rbp+170h+var_198]
0x18017ae7e  mov     eax, [r8]
0x18017ae81  mov     dword ptr [rsp+270h+var_220], eax
0x18017ae85  mov     r11, [rbp+170h+var_1C8]
0x18017ae89  mov     eax, [r11]
0x18017ae8c  mov     dword ptr [rsp+270h+var_228], eax
0x18017ae90  mov     al, [rbp+170h+var_1F0]
0x18017ae93  mov     byte ptr [rsp+270h+var_230], al
0x18017ae97  lea     rax, [rbp+170h+var_180]
0x18017ae9b  mov     [rsp+270h+var_238], rax
0x18017aea0  mov     [rsp+270h+var_240], rcx
0x18017aea5  mov     [rsp+270h+var_248], rsi
0x18017aeaa  mov     rax, [rdx+10h]
0x18017aeae  mov     [rsp+270h+var_250], rax
0x18017aeb3  mov     r9d, [rbp+170h+var_140]
0x18017aeb7  xor     r8d, r8d
0x18017aeba  lea     rdx, [rbp+170h+var_150]
0x18017aebe  mov     rcx, r10
0x18017aec1  call    ?MapCharacters@FontFallback@@QEBAXPEAUIDWriteTextAnalysisSource@@IIPEAUIDWriteFontCollection@@PEAUIDWriteFont@@PEB_WV?$array_ref@$$CBUDWRITE_FONT_AXIS_VALUE@@@@_NW4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STYLE@@W4DWRITE_FONT_STRETCH@@PEAIPEAPEAU4@PEAM@Z; FontFallback::MapCharacters(IDWriteTextAnalysisSource *,uint,uint,IDWriteFontCollection *,IDWriteFont *,wchar_t const *,array_ref<DWRITE_FONT_AXIS_VALUE const>,bool,DWRITE_FONT_WEIGHT,DWRITE_FONT_STYLE,DWRITE_FONT_STRETCH,uint *,IDWriteFont * *,float *)
0x18017aec6  mov     ecx, [rbp+170h+var_1EC]
0x18017aec9  cmp     rcx, r13
0x18017aecc  ja      loc_18017B64F
0x18017aed2  lea     rax, [rbp+170h+var_1A8]
0x18017aed6  mov     ebx, 0FFFFFFFFh
0x18017aedb  cmp     [rbp+170h+var_158], rax
0x18017aedf  jz      loc_18017B2B8
0x18017aee5  mov     [rbp+170h+var_1F0], 0
0x18017aee9  test    ecx, ecx
0x18017aeeb  jz      loc_18017B588
0x18017aef1  mov     rbx, [rbp+170h+var_1D0]
0x18017aef5  test    rbx, rbx
0x18017aef8  jnz     short loc_18017AF56
0x18017aefa  mov     rdx, [rbp+170h+var_1B8]; struct IDWriteFont *
0x18017aefe  test    rdx, rdx
0x18017af01  jz      loc_18017B67A
0x18017af07  mov     rcx, [rbp+170h+var_1B0]; this
0x18017af0b  call    ?GetFontInstance@RecentFontCache@@AEAAPEAUFontInstance@1@PEAUIDWriteFont@@@Z; RecentFontCache::GetFontInstance(IDWriteFont *)
0x18017af10  lea     rbx, [rax+18h]
0x18017af14  cmp     qword ptr [rbx], 0
0x18017af18  jz      loc_18017B253
0x18017af1e  mov     rbx, [rbx]
0x18017af21  test    rbx, rbx
0x18017af24  jz      short loc_18017AF36
0x18017af26  mov     rax, [rbx]
0x18017af29  mov     rcx, rbx
0x18017af2c  mov     rax, [rax+8]
0x18017af30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017af35  nop
0x18017af36  mov     rcx, [rbp+170h+var_1D0]
0x18017af3a  mov     [rbp+170h+var_1D0], rbx
0x18017af3e  test    rcx, rcx
0x18017af41  jz      short loc_18017AF53
0x18017af43  mov     rax, [rcx]
0x18017af46  mov     rax, [rax+10h]
0x18017af4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017af4f  mov     rbx, [rbp+170h+var_1D0]
0x18017af53  mov     ecx, [rbp+170h+var_1EC]
0x18017af56  test    r12, r12
0x18017af59  jnz     loc_18017B56E
0x18017af5f  mov     eax, ecx
0x18017af61  cmp     rax, r13
0x18017af64  jz      short loc_18017AF98
0x18017af66  mov     eax, 0FFFFFFFFh
0x18017af6b  cmp     r12, rax
0x18017af6e  ja      loc_18017B24D
0x18017af74  lea     r9d, [r12+rcx]
0x18017af78  cmp     r9d, r12d
0x18017af7b  jb      loc_18017B24D
0x18017af81  mov     r8, [r15+20h]
0x18017af85  add     r8, rdi
0x18017af88  lea     rdx, [rbp+170h+var_1E0]
0x18017af8c  mov     rcx, r15
0x18017af8f  call    ?SplitSpan@TextLayout@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USpan@TextLayout@@@std@@@std@@@std@@V23@I@Z; TextLayout::SplitSpan(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<TextLayout::Span>>>,uint)
0x18017af94  mov     rbx, [rbp+170h+var_1D0]
0x18017af98  mov     r14, [r15+20h]
0x18017af9c  test    rbx, rbx
0x18017af9f  jz      short loc_18017AFB1
0x18017afa1  mov     rax, [rbx]
0x18017afa4  mov     rcx, rbx
0x18017afa7  mov     rax, [rax+8]
0x18017afab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017afb0  nop
0x18017afb1  lea     rcx, [rdi+38h]
0x18017afb5  add     rcx, r14
0x18017afb8  call    ?Deref@?$ComPtr@UIDWriteFontFamily@@@@AEAAXXZ; ComPtr<IDWriteFontFamily>::Deref(void)
0x18017afbd  mov     rax, [rbp+170h+var_1D0]
0x18017afc1  mov     [r14+rdi+38h], rax
0x18017afc6  mov     rax, [r15+20h]
0x18017afca  movss   xmm0, [rbp+170h+var_1D8]
0x18017afcf  mulss   xmm0, dword ptr [rdi+rax+30h]
0x18017afd5  movss   dword ptr [rdi+rax+30h], xmm0
0x18017afdb  mov     ebx, [rbp+170h+var_1EC]
0x18017afde  add     rbx, r12
0x18017afe1  mov     rcx, [rbp+170h+var_1D0]
0x18017afe5  test    rcx, rcx
0x18017afe8  jz      short loc_18017AFF7
0x18017afea  mov     rax, [rcx]
0x18017afed  mov     rax, [rax+10h]
0x18017aff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017aff6  nop
0x18017aff7  mov     rcx, [rbp+170h+Block]; Block
0x18017affb  call    cs:__imp_free
0x18017b001  nop
0x18017b002  mov     rcx, [rbp+170h+var_190]
0x18017b006  test    rcx, rcx
0x18017b009  jz      short loc_18017B018
0x18017b00b  mov     rax, [rcx]
0x18017b00e  mov     rax, [rax+10h]
0x18017b012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017b017  nop
0x18017b018  mov     rcx, [rbp+170h+var_1B8]
0x18017b01c  test    rcx, rcx
0x18017b01f  jz      short loc_18017B02E
0x18017b021  mov     rax, [rcx]
0x18017b024  mov     rax, [rax+10h]
0x18017b028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017b02d  nop
0x18017b02e  test    rsi, rsi
0x18017b031  jz      short loc_18017B043
  ... truncated ...
```
