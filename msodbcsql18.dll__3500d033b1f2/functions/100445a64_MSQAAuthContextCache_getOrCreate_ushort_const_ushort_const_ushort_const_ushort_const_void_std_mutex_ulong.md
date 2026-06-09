# MSQAAuthContextCache::getOrCreate(ushort const *,ushort const *,ushort const *,ushort const *,void * &,std::mutex * &,ulong &)

- ea: `0x100445a64`
- end: `0x1004468cf`
- name: `?getOrCreate@MSQAAuthContextCache@@QEAAKPEBG000AEAPEAXAEAPEAVmutex@std@@AEAK@Z`
- size: `3691`
- prototype: `unsigned int __fastcall(MSQAAuthContextCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void **, struct std::mutex **, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x100446aac`

## callees

- `0x1004306f0`
- `0x1004307a0`
- `0x100430824`
- `0x100431c4c`
- `0x100443e00`
- `0x100444028`
- `0x100444d78`
- `0x100444e4c`
- `0x100445a64`
- `0x100547fab`
- `0x100547fb7`
- `0x100547fc3`
- `0x100547fcf`
- `0x100547fdb`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100445e7c`
- `KERNEL32!GetLastError` at `0x100445e7c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10044636b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10044644d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100446454`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10044651e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100446525`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004465ef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004465f6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004466f2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004466f9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004468ba`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004468c1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004468c8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10044636b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10044644d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100446454`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10044651e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100446525`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004465ef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004465f6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004466f2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004466f9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004468ba`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004468c1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004468c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall MSQAAuthContextCache::getOrCreate(
        MSQAAuthContextCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        void **a6,
        struct std::mutex **a7,
        unsigned int *a8)
{
  int v10; // eax
  unsigned int v11; // esi
  __int64 v12; // rbx
  __int64 v13; // r8
  __int64 v14; // r8
  void *v15; // rcx
  __int64 v16; // rax
  struct std::mutex **v17; // rax
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  _QWORD *v21; // r9
  _QWORD *v22; // r8
  _QWORD *v23; // rdx
  _QWORD *v24; // rcx
  DWORD LastError; // ebx
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rdx
  struct _Mtx_internal_imp_t *v35; // rdi
  struct _Mtx_internal_imp_t *v36; // rbx
  char *v37; // r13
  struct _Mtx_internal_imp_t **v38; // rax
  struct _Mtx_internal_imp_t *v39; // r14
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // rdx
  int v52; // eax
  struct _Mtx_internal_imp_t *v54; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v55[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct std::mutex **v56; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v57; // [rsp+58h] [rbp-A8h]
  __int64 v58; // [rsp+60h] [rbp-A0h]
  void *v59; // [rsp+68h] [rbp-98h]
  unsigned __int64 v60; // [rsp+70h] [rbp-90h] BYREF
  __m128i v61; // [rsp+80h] [rbp-80h]
  unsigned __int64 v62; // [rsp+90h] [rbp-70h] BYREF
  __m128i v63; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v64; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v65; // [rsp+C0h] [rbp-40h]
  _QWORD v66[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v68; // [rsp+E8h] [rbp-18h]
  _QWORD v69[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v70; // [rsp+100h] [rbp+0h]
  unsigned __int64 v71; // [rsp+108h] [rbp+8h]
  _QWORD v72[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v73; // [rsp+120h] [rbp+20h]
  unsigned __int64 v74; // [rsp+128h] [rbp+28h]
  _QWORD v75[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v76; // [rsp+140h] [rbp+40h]
  unsigned __int64 v77; // [rsp+148h] [rbp+48h]
  unsigned __int64 v78; // [rsp+150h] [rbp+50h] BYREF
  __m128i v79; // [rsp+160h] [rbp+60h]
  __int128 v80; // [rsp+170h] [rbp+70h] BYREF
  __m128i v81; // [rsp+180h] [rbp+80h]
  unsigned __int64 v82; // [rsp+190h] [rbp+90h] BYREF
  __m128i si128; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v84; // [rsp+1B0h] [rbp+B0h] BYREF
  __m128i v85; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v86; // [rsp+1D0h] [rbp+D0h]
  __int64 v87; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v88; // [rsp+1E8h] [rbp+E8h]
  _BYTE Src[32]; // [rsp+1F0h] [rbp+F0h] BYREF

  v58 = -2;
  v55[0] = a4;
  v57 = a3;
  v56 = a7;
  v59 = &MSQAAuthContextCache::pLock;
  v10 = Mtx_lock_0((_Mtx_t)&MSQAAuthContextCache::pLock);
  if ( v10 )
    std::_Throw_C_error(v10);
  v88 = 7;
  v11 = 1;
  v87 = 1;
  LODWORD(v86) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v82) = 0;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  std::wstring::assign(&v82);
  v85 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v84) = 0;
  v14 = -1;
  do
    ++v14;
  while ( a5[v14] );
  std::wstring::assign(&v84);
  v15 = (void *)std::operator+<unsigned short>(Src);
  v16 = std::wstring::append(v15);
  v81 = 0;
  v80 = *(_OWORD *)v16;
  v81 = *(__m128i *)(v16 + 16);
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 24) = 7;
  *(_WORD *)v16 = 0;
  std::basic_string<char16_t>::_Tidy_deallocate(Src);
  std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,DNSCacheEntry *,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,DNSCacheEntry *>>,0>>::find(
    this,
    &v54,
    &v80);
  if ( v54 != *(struct _Mtx_internal_imp_t **)this )
  {
    *a6 = (void *)*((_QWORD *)v54 + 8);
    *a8 = 25;
    if ( !*a6 )
      goto LABEL_165;
    std::map<std::wstring,std::unique_ptr<std::mutex>>::_Try_emplace<std::wstring const &,>(
      (char *)this + 16,
      v55,
      &v80);
    v17 = v56;
    *v56 = *(struct std::mutex **)(v55[0] + 64LL);
    *a8 = 26;
    if ( !*v17 )
    {
      v11 = 2;
      goto LABEL_165;
    }
    goto LABEL_164;
  }
  v79 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v78) = 0;
  v18 = -1;
  do
    ++v18;
  while ( a2[v18] );
  std::wstring::assign(&v78);
  v76 = 0;
  v77 = 15;
  LOBYTE(v75[0]) = 0;
  std::string::_Construct<unsigned short *>(v75);
  v65 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v64) = 0;
  v19 = -1;
  do
    ++v19;
  while ( v57[v19] );
  std::wstring::assign(&v64);
  v73 = 0;
  v74 = 15;
  LOBYTE(v72[0]) = 0;
  std::string::_Construct<unsigned short *>(v72);
  v63 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v62) = 0;
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(v55[0] + 2 * v20) );
  std::wstring::assign(&v62);
  v70 = 0;
  v71 = 15;
  LOBYTE(v69[0]) = 0;
  std::string::_Construct<unsigned short *>(v69);
  v61 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v60) = 0;
  do
    ++v12;
  while ( a5[v12] );
  std::wstring::assign(&v60);
  v67 = 0;
  v68 = 15;
  LOBYTE(v66[0]) = 0;
  std::string::_Construct<unsigned short *>(v66);
  v21 = v66;
  if ( v68 >= 0x10 )
    v21 = (_QWORD *)v66[0];
  v22 = v69;
  if ( v71 >= 0x10 )
    v22 = (_QWORD *)v69[0];
  v23 = v72;
  if ( v74 >= 0x10 )
    v23 = (_QWORD *)v72[0];
  v24 = v75;
  if ( v77 >= 0x10 )
    v24 = (_QWORD *)v75[0];
  *a6 = (void *)((__int64 (__fastcall *)(_QWORD *, _QWORD *, _QWORD *, _QWORD *))qword_1005D8FD0)(v24, v23, v22, v21);
  *a8 = 22;
  if ( !*a6 )
  {
    LastError = GetLastError();
    if ( v68 < 0x10 )
    {
LABEL_35:
      v67 = 0;
      v68 = 15;
      LOBYTE(v66[0]) = 0;
      if ( v61.m128i_i64[1] < 8uLL )
      {
LABEL_43:
        v61 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v60) = 0;
        if ( v71 < 0x10 )
        {
LABEL_50:
          v70 = 0;
          v71 = 15;
          LOBYTE(v69[0]) = 0;
          if ( v63.m128i_i64[1] < 8uLL )
          {
LABEL_58:
            v63 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v62) = 0;
            if ( v74 < 0x10 )
            {
LABEL_65:
              v73 = 0;
              v74 = 15;
              LOBYTE(v72[0]) = 0;
              if ( v65.m128i_i64[1] < 8uLL )
              {
LABEL_73:
                v65 = _mm_load_si128((const __m128i *)&_xmm);
                LOWORD(v64) = 0;
                if ( v77 < 0x10 )
                {
LABEL_80:
                  v76 = 0;
                  v77 = 15;
                  LOBYTE(v75[0]) = 0;
                  if ( v79.m128i_i64[1] < 8uLL )
                  {
LABEL_88:
                    v11 = LastError;
                    goto LABEL_165;
                  }
                  v34 = v78;
                  if ( (unsigned __int64)(v79.m128i_i64[1] + 1) <= 0x7FFFFFFFFFFFFFFFLL )
                  {
                    if ( (unsigned __int64)(2 * (v79.m128i_i64[1] + 1)) < 0x1000
                      || (v78 & 0x1F) == 0 && (v34 = *(_QWORD *)(v78 - 8), v34 < v78) && v78 - v34 - 8 <= 0x1F )
                    {
                      if ( v34 )
                        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
                      goto LABEL_88;
                    }
                  }
LABEL_173:
                  _invalid_parameter_noinfo_noreturn();
                }
                v33 = v75[0];
                if ( v77 + 1 < 0x1000
                  || (v75[0] & 0x1F) == 0 && (v33 = *(_QWORD *)(v75[0] - 8LL), v33 < v75[0]) && v75[0] - v33 - 8 <= 0x1F )
                {
                  if ( v33 )
                    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
                  goto LABEL_80;
                }
LABEL_152:
                _invalid_parameter_noinfo_noreturn();
              }
              v32 = v64;
              if ( (unsigned __int64)(v65.m128i_i64[1] + 1) <= 0x7FFFFFFFFFFFFFFFLL )
              {
                if ( (unsigned __int64)(2 * (v65.m128i_i64[1] + 1)) < 0x1000
                  || (v64 & 0x1F) == 0 && (v32 = *(_QWORD *)(v64 - 8), v32 < v64) && v64 - v32 - 8 <= 0x1F )
                {
                  if ( v32 )
                    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
                  goto LABEL_73;
                }
              }
LABEL_153:
              _invalid_parameter_noinfo_noreturn();
            }
            v31 = v72[0];
            if ( v74 + 1 < 0x1000
              || (v72[0] & 0x1F) == 0 && (v31 = *(_QWORD *)(v72[0] - 8LL), v31 < v72[0]) && v72[0] - v31 - 8 <= 0x1F )
            {
              if ( v31 )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
              goto LABEL_65;
            }
LABEL_135:
            _invalid_parameter_noinfo_noreturn();
          }
          v30 = v62;
          if ( (unsigned __int64)(v63.m128i_i64[1] + 1) <= 0x7FFFFFFFFFFFFFFFLL )
          {
            if ( (unsigned __int64)(2 * (v63.m128i_i64[1] + 1)) < 0x1000
              || (v62 & 0x1F) == 0 && (v30 = *(_QWORD *)(v62 - 8), v30 < v62) && v62 - v30 - 8 <= 0x1F )
            {
              if ( v30 )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
              goto LABEL_58;
            }
          }
LABEL_136:
          _invalid_parameter_noinfo_noreturn();
        }
        v29 = v69[0];
        if ( v71 + 1 < 0x1000
          || (v69[0] & 0x1F) == 0 && (v29 = *(_QWORD *)(v69[0] - 8LL), v29 < v69[0]) && v69[0] - v29 - 8 <= 0x1F )
        {
          if ( v29 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
          goto LABEL_50;
        }
LABEL_118:
        _invalid_parameter_noinfo_noreturn();
      }
      v28 = v60;
      if ( (unsigned __int64)(v61.m128i_i64[1] + 1) <= 0x7FFFFFFFFFFFFFFFLL )
      {
        if ( (unsigned __int64)(2 * (v61.m128i_i64[1] + 1)) < 0x1000
          || (v60 & 0x1F) == 0 && (v28 = *(_QWORD *)(v60 - 8), v28 < v60) && v60 - v28 - 8 <= 0x1F )
        {
          if ( v28 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
          goto LABEL_43;
        }
      }
LABEL_119:
      _invalid_parameter_noinfo_noreturn();
    }
    v26 = v66[0];
    v27 = v66[0];
    if ( v68 + 1 < 0x1000
      || (v66[0] & 0x1F) == 0
      && (v26 = *(_QWORD *)(v66[0] - 8LL), v26 < v66[0])
      && (v27 = v66[0] - v26 - 8, v27 <= 0x1F) )
    {
      if ( v26 )
        ((void (__fastcall *)(struct IMalloc *, unsigned __int64, unsigned __int64))g_pMO->lpVtbl[1].Realloc)(
          g_pMO,
          v26,
          v27);
      goto LABEL_35;
    }
LABEL_102:
    _invalid_parameter_noinfo_noreturn();
  }
  std::map<std::wstring,void *>::_Try_emplace<std::wstring const &,>(this, v55, &v80);
  *(_QWORD *)(v55[0] + 64LL) = *a6;
  v35 = (struct _Mtx_internal_imp_t *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(
                                        g_pMO,
                                        80);
  if ( v35 )
    Mtx_init_in_situ_0(v35, 2);
  else
    v35 = 0;
  v36 = v35;
  v54 = v35;
  v37 = (char *)this + 16;
  std::map<std::wstring,std::unique_ptr<std::mutex>>::_Try_emplace<std::wstring const &,>((char *)this + 16, v55, &v80);
  v38 = (struct _Mtx_internal_imp_t **)(v55[0] + 64LL);
  if ( (struct _Mtx_internal_imp_t **)(v55[0] + 64LL) != &v54 )
  {
    v36 = 0;
    v54 = 0;
    v39 = *v38;
    *v38 = v35;
    v35 = 0;
    if ( v39 )
    {
      Mtx_destroy_in_situ_0(v39);
      ((void (__fastcall *)(struct IMalloc *, struct _Mtx_internal_imp_t *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v39);
    }
  }
  if ( v35 )
  {
    Mtx_destroy_in_situ_0(v36);
    ((void (__fastcall *)(struct IMalloc *, struct _Mtx_internal_imp_t *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v36);
  }
  std::map<std::wstring,std::unique_ptr<std::mutex>>::_Try_emplace<std::wstring const &,>(v37, v55, &v80);
  *v56 = *(struct std::mutex **)(v55[0] + 64LL);
  ((void (__fastcall *)(_QWORD, __int64, __int64))qword_1005D8FD8)(*a6, 2, 1);
  *a8 = 23;
  ((void (__fastcall *)(_QWORD, __int64, _QWORD))qword_1005D8FD8)(*a6, 1, 0);
  *a8 = 21;
  if ( v68 >= 0x10 )
  {
    v40 = v66[0];
    if ( v68 + 1 >= 0x1000 )
    {
      if ( (v66[0] & 0x1F) != 0 )
        goto LABEL_102;
      v40 = *(_QWORD *)(v66[0] - 8LL);
      if ( v40 >= v66[0] || v66[0] - v40 - 8 > 0x1F )
        goto LABEL_102;
    }
    if ( v40 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v67 = 0;
  v68 = 15;
  LOBYTE(v66[0]) = 0;
  if ( v61.m128i_i64[1] >= 8uLL )
  {
    v41 = v60;
    if ( (unsigned __int64)(v61.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_119;
    if ( (unsigned __int64)(2 * (v61.m128i_i64[1] + 1)) >= 0x1000 )
    {
      if ( (v60 & 0x1F) != 0 )
        goto LABEL_119;
      v41 = *(_QWORD *)(v60 - 8);
      if ( v41 >= v60 || v60 - v41 - 8 > 0x1F )
        goto LABEL_119;
    }
    if ( v41 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v61 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v60) = 0;
  if ( v71 >= 0x10 )
  {
    v42 = v69[0];
    if ( v71 + 1 >= 0x1000 )
    {
      if ( (v69[0] & 0x1F) != 0 )
        goto LABEL_118;
      v42 = *(_QWORD *)(v69[0] - 8LL);
      if ( v42 >= v69[0] || v69[0] - v42 - 8 > 0x1F )
        goto LABEL_118;
    }
    if ( v42 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v70 = 0;
  v71 = 15;
  LOBYTE(v69[0]) = 0;
  if ( v63.m128i_i64[1] >= 8uLL )
  {
    v43 = v62;
    if ( (unsigned __int64)(v63.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_136;
    if ( (unsigned __int64)(2 * (v63.m128i_i64[1] + 1)) >= 0x1000 )
    {
      if ( (v62 & 0x1F) != 0 )
        goto LABEL_136;
      v43 = *(_QWORD *)(v62 - 8);
      if ( v43 >= v62 || v62 - v43 - 8 > 0x1F )
        goto LABEL_136;
    }
    if ( v43 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v63 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v62) = 0;
  if ( v74 >= 0x10 )
  {
    v44 = v72[0];
    if ( v74 + 1 >= 0x1000 )
    {
      if ( (v72[0] & 0x1F) != 0 )
        goto LABEL_135;
      v44 = *(_QWORD *)(v72[0] - 8LL);
      if ( v44 >= v72[0] || v72[0] - v44 - 8 > 0x1F )
        goto LABEL_135;
    }
    if ( v44 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v73 = 0;
  v74 = 15;
  LOBYTE(v72[0]) = 0;
  if ( v65.m128i_i64[1] >= 8uLL )
  {
    v45 = v64;
    if ( (unsigned __int64)(v65.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_153;
    if ( (unsigned __int64)(2 * (v65.m128i_i64[1] + 1)) >= 0x1000 )
    {
      if ( (v64 & 0x1F) != 0 )
        goto LABEL_153;
      v45 = *(_QWORD *)(v64 - 8);
      if ( v45 >= v64 || v64 - v45 - 8 > 0x1F )
        goto LABEL_153;
    }
    if ( v45 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v65 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v64) = 0;
  if ( v77 >= 0x10 )
  {
    v46 = v75[0];
    if ( v77 + 1 >= 0x1000 )
    {
      if ( (v75[0] & 0x1F) != 0 )
        goto LABEL_152;
      v46 = *(_QWORD *)(v75[0] - 8LL);
      if ( v46 >= v75[0] || v75[0] - v46 - 8 > 0x1F )
        goto LABEL_152;
    }
    if ( v46 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v76 = 0;
  v77 = 15;
  LOBYTE(v75[0]) = 0;
  if ( v79.m128i_i64[1] >= 8uLL )
  {
    v47 = v78;
    if ( (unsigned __int64)(v79.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_173;
    if ( (unsigned __int64)(2 * (v79.m128i_i64[1] + 1)) >= 0x1000 )
    {
      if ( (v78 & 0x1F) != 0 )
        goto LABEL_173;
      v47 = *(_QWORD *)(v78 - 8);
      if ( v47 >= v78 || v78 - v47 - 8 > 0x1F )
        goto LABEL_173;
    }
    if ( v47 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
LABEL_164:
  v11 = 0;
LABEL_165:
  if ( v81.m128i_i64[1] >= 8uLL )
  {
    v48 = v80;
    if ( (unsigned __int64)(v81.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (v81.m128i_i64[1] + 1)) >= 0x1000
      && ((v80 & 0x1F) != 0
       || (v48 = *(_QWORD *)(v80 - 8), v48 >= (unsigned __int64)v80)
       || (unsigned __int64)v80 - v48 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    if ( v48 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v81 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v80) = 0;
  if ( v85.m128i_i64[1] >= 8uLL )
  {
    v49 = v84;
    if ( (unsigned __int64)(v85.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (v85.m128i_i64[1] + 1)) >= 0x1000
      && ((v84 & 0x1F) != 0 || (v49 = *(_QWORD *)(v84 - 8), v49 >= v84) || v84 - v49 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    if ( v49 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v85 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v84) = 0;
  if ( si128.m128i_i64[1] >= 8uLL )
  {
    v50 = v82;
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000
      && ((v82 & 0x1F) != 0 || (v50 = *(_QWORD *)(v82 - 8), v50 >= v82) || v82 - v50 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    if ( v50 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v82) = 0;
  if ( v88 >= 8 )
  {
    v51 = v86;
    if ( v88 + 1 > 0x7FFFFFFFFFFFFFFFLL
      || 2 * (v88 + 1) >= 0x1000
      && ((v86 & 0x1F) != 0 || (v51 = *(_QWORD *)(v86 - 8), v51 >= v86) || v86 - v51 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    if ( v51 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v52 = Mtx_unlock_0((_Mtx_t)&MSQAAuthContextCache::pLock);
  if ( v52 )
    std::_Throw_C_error(v52);
  return v11;
}

```

## disassembly

```asm
0x100445a64  push    rbp
0x100445a66  push    rbx
0x100445a67  push    rsi
0x100445a68  push    rdi
0x100445a69  push    r12
0x100445a6b  push    r13
0x100445a6d  push    r14
0x100445a6f  push    r15
0x100445a71  lea     rbp, [rsp-128h]
0x100445a79  sub     rsp, 228h
0x100445a80  mov     [rsp+260h+var_200], 0FFFFFFFFFFFFFFFEh
0x100445a89  mov     rax, cs:__security_cookie
0x100445a90  xor     rax, rsp
0x100445a93  mov     [rbp+160h+var_50], rax
0x100445a9a  mov     [rsp+260h+var_220], r9
0x100445a9f  mov     [rsp+260h+var_208], r8
0x100445aa4  mov     rdi, rdx
0x100445aa7  mov     r14, rcx
0x100445aaa  mov     r13, [rbp+160h+arg_20]
0x100445ab1  mov     r15, [rbp+160h+arg_28]
0x100445ab8  mov     rax, [rbp+160h+arg_30]
0x100445abf  mov     [rsp+260h+var_210], rax
0x100445ac4  mov     r12, [rbp+160h+arg_38]
0x100445acb  xor     ebx, ebx
0x100445acd  lea     rax, ?pLock@MSQAAuthContextCache@@0Vmutex@std@@A; std::mutex MSQAAuthContextCache::pLock
0x100445ad4  mov     [rsp+260h+var_1F8], rax
0x100445ad9  mov     rcx, rax; _Mtx_t
0x100445adc  call    _Mtx_lock_0
0x100445ae1  test    eax, eax
0x100445ae3  jz      short loc_100445AED
0x100445ae5  mov     ecx, eax; int
0x100445ae7  call    ?_Throw_C_error@std@@YAXH@Z_0; std::_Throw_C_error(int)
0x100445aec  nop
0x100445aed  mov     [rbp+160h+var_78], 7
0x100445af8  mov     esi, 1
0x100445afd  mov     [rbp+160h+var_80], rsi
0x100445b04  mov     dword ptr [rbp+160h+var_90], ebx
0x100445b0a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445b12  movdqu  [rbp+160h+var_C0], xmm0
0x100445b1a  mov     word ptr [rbp+160h+var_D0], bx
0x100445b21  or      rbx, 0FFFFFFFFFFFFFFFFh
0x100445b25  mov     r8, rbx
0x100445b28  xor     ecx, ecx
0x100445b2a  inc     r8
0x100445b2d  cmp     [rdi+r8*2], cx
0x100445b32  jnz     short loc_100445B2A
0x100445b34  mov     rdx, rdi
0x100445b37  lea     rcx, [rbp+160h+var_D0]; void *
0x100445b3e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100445b43  nop
0x100445b44  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445b4c  movdqu  [rbp+160h+var_A0], xmm0
0x100445b54  xor     eax, eax
0x100445b56  mov     word ptr [rbp+160h+var_B0], ax
0x100445b5d  mov     r8, rbx
0x100445b60  inc     r8
0x100445b63  cmp     [r13+r8*2+0], ax
0x100445b69  jnz     short loc_100445B60
0x100445b6b  mov     rdx, r13
0x100445b6e  lea     rcx, [rbp+160h+var_B0]; void *
0x100445b75  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100445b7a  nop
0x100445b7b  lea     r8, [rbp+160h+var_90]
0x100445b82  lea     rdx, [rbp+160h+var_B0]
0x100445b89  lea     rcx, [rbp+160h+Src]; Src
0x100445b90  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x100445b95  nop
0x100445b96  lea     rdx, [rbp+160h+var_D0]
0x100445b9d  cmp     qword ptr [rbp+160h+var_C0+8], 8
0x100445ba5  cmovnb  rdx, [rbp+160h+var_D0]
0x100445bad  mov     r8, qword ptr [rbp+160h+var_C0]
0x100445bb4  mov     rcx, rax; Src
0x100445bb7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x100445bbc  xorps   xmm0, xmm0
0x100445bbf  movdqu  [rbp+160h+var_E0], xmm0
0x100445bc7  movups  xmm0, xmmword ptr [rax]
0x100445bca  movups  [rbp+160h+var_F0], xmm0
0x100445bce  movups  xmm1, xmmword ptr [rax+10h]
0x100445bd2  movups  [rbp+160h+var_E0], xmm1
0x100445bd9  xor     ecx, ecx
0x100445bdb  mov     [rax+10h], rcx
0x100445bdf  mov     qword ptr [rax+18h], 7
0x100445be7  mov     [rax], cx
0x100445bea  lea     rcx, [rbp+160h+Src]
0x100445bf1  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x100445bf6  nop
0x100445bf7  lea     r8, [rbp+160h+var_F0]
0x100445bfb  lea     rdx, [rsp+260h+var_228]
0x100445c00  mov     rcx, r14
0x100445c03  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUDNSCacheEntry@@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUDNSCacheEntry@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUDNSCacheEntry@@@std@@@std@@@std@@@2@AEBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,DNSCacheEntry *,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,DNSCacheEntry *>>,0>>::find(std::basic_string<char16_t> const &)
0x100445c08  mov     rax, [rsp+260h+var_228]
0x100445c0d  cmp     rax, [r14]
0x100445c10  jz      short loc_100445C68
0x100445c12  mov     rcx, [rax+40h]
0x100445c16  mov     [r15], rcx
0x100445c19  mov     dword ptr [r12], 19h
0x100445c21  xor     edi, edi
0x100445c23  cmp     [r15], rdi
0x100445c26  jz      loc_100446689
0x100445c2c  lea     rcx, [r14+10h]
0x100445c30  lea     r8, [rbp+160h+var_F0]
0x100445c34  lea     rdx, [rsp+260h+var_220]
0x100445c39  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@Vmutex@std@@U?$default_delete@Vmutex@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@Vmutex@std@@U?$default_delete@Vmutex@std@@@2@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@Vmutex@std@@U?$default_delete@Vmutex@std@@@2@@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<std::mutex>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x100445c3e  mov     rax, [rsp+260h+var_220]
0x100445c43  mov     rcx, [rax+40h]
0x100445c47  mov     rax, [rsp+260h+var_210]
0x100445c4c  mov     [rax], rcx
0x100445c4f  mov     dword ptr [r12], 1Ah
0x100445c57  cmp     [rax], rdi
0x100445c5a  jnz     loc_100446687
0x100445c60  lea     esi, [rdi+2]
0x100445c63  jmp     loc_100446689
0x100445c68  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445c70  movdqu  [rbp+160h+var_100], xmm0
0x100445c75  xor     eax, eax
0x100445c77  mov     word ptr [rbp+160h+var_110], ax
0x100445c7b  mov     r8, rbx
0x100445c7e  inc     r8
0x100445c81  cmp     [rdi+r8*2], ax
0x100445c86  jnz     short loc_100445C7E
0x100445c88  mov     rdx, rdi
0x100445c8b  lea     rcx, [rbp+160h+var_110]; void *
0x100445c8f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100445c94  nop
0x100445c95  lea     rcx, [rbp+160h+var_110]
0x100445c99  cmp     qword ptr [rbp+160h+var_100+8], 8
0x100445c9e  cmovnb  rcx, [rbp+160h+var_110]
0x100445ca3  mov     rax, qword ptr [rbp+160h+var_100]
0x100445ca7  lea     r8, [rcx+rax*2]
0x100445cab  lea     rdx, [rbp+160h+var_110]
0x100445caf  cmovnb  rdx, [rbp+160h+var_110]
0x100445cb4  xor     edi, edi
0x100445cb6  mov     [rbp+160h+var_120], rdi
0x100445cba  mov     [rbp+160h+var_118], 0Fh
0x100445cc2  mov     byte ptr [rbp+160h+var_130], dil
0x100445cc6  mov     r9b, [rsp+260h+var_230]
0x100445ccb  lea     rcx, [rbp+160h+var_130]; Src
0x100445ccf  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100445cd4  nop
0x100445cd5  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445cdd  movdqu  [rbp+160h+var_1A0], xmm0
0x100445ce2  mov     word ptr [rbp+160h+var_1B0], di
0x100445ce6  mov     r8, rbx
0x100445ce9  mov     rax, [rsp+260h+var_208]
0x100445cee  inc     r8
0x100445cf1  cmp     [rax+r8*2], di
0x100445cf6  jnz     short loc_100445CEE
0x100445cf8  mov     rdx, rax
0x100445cfb  lea     rcx, [rbp+160h+var_1B0]; void *
0x100445cff  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100445d04  nop
0x100445d05  lea     rcx, [rbp+160h+var_1B0]
0x100445d09  cmp     qword ptr [rbp+160h+var_1A0+8], 8
0x100445d0e  cmovnb  rcx, [rbp+160h+var_1B0]
0x100445d13  mov     rax, qword ptr [rbp+160h+var_1A0]
0x100445d17  lea     r8, [rcx+rax*2]
0x100445d1b  lea     rdx, [rbp+160h+var_1B0]
0x100445d1f  cmovnb  rdx, [rbp+160h+var_1B0]
0x100445d24  mov     [rbp+160h+var_140], rdi
0x100445d28  mov     [rbp+160h+var_138], 0Fh
0x100445d30  mov     byte ptr [rbp+160h+var_150], dil
0x100445d34  mov     r9b, [rsp+260h+var_230]
0x100445d39  lea     rcx, [rbp+160h+var_150]; Src
0x100445d3d  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100445d42  nop
0x100445d43  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445d4b  movdqu  [rbp+160h+var_1C0], xmm0
0x100445d50  mov     word ptr [rbp+160h+var_1D0], di
0x100445d54  mov     r8, rbx
0x100445d57  mov     rax, [rsp+260h+var_220]
0x100445d5c  inc     r8
0x100445d5f  cmp     [rax+r8*2], di
0x100445d64  jnz     short loc_100445D5C
0x100445d66  mov     rdx, rax
0x100445d69  lea     rcx, [rbp+160h+var_1D0]; void *
0x100445d6d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100445d72  nop
0x100445d73  lea     rcx, [rbp+160h+var_1D0]
0x100445d77  cmp     qword ptr [rbp+160h+var_1C0+8], 8
0x100445d7c  cmovnb  rcx, [rbp+160h+var_1D0]
0x100445d81  mov     rax, qword ptr [rbp+160h+var_1C0]
0x100445d85  lea     r8, [rcx+rax*2]
0x100445d89  lea     rdx, [rbp+160h+var_1D0]
0x100445d8d  cmovnb  rdx, [rbp+160h+var_1D0]
0x100445d92  mov     [rbp+160h+var_160], rdi
0x100445d96  mov     [rbp+160h+var_158], 0Fh
0x100445d9e  mov     byte ptr [rbp+160h+var_170], dil
0x100445da2  mov     r9b, [rsp+260h+var_230]
0x100445da7  lea     rcx, [rbp+160h+var_170]; Src
0x100445dab  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100445db0  nop
0x100445db1  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445db9  movdqu  [rbp+160h+var_1E0], xmm0
0x100445dbe  mov     word ptr [rsp+260h+var_1F0], di
0x100445dc3  inc     rbx
0x100445dc6  cmp     [r13+rbx*2+0], di
0x100445dcc  jnz     short loc_100445DC3
0x100445dce  mov     r8, rbx
0x100445dd1  mov     rdx, r13
0x100445dd4  lea     rcx, [rsp+260h+var_1F0]; void *
0x100445dd9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100445dde  nop
0x100445ddf  lea     rdx, [rsp+260h+var_1F0]
0x100445de4  cmp     qword ptr [rbp+160h+var_1E0+8], 8
0x100445de9  cmovnb  rdx, [rsp+260h+var_1F0]
0x100445def  lea     rcx, [rsp+260h+var_1F0]
0x100445df4  cmovnb  rcx, [rsp+260h+var_1F0]
0x100445dfa  mov     [rbp+160h+var_180], rdi
0x100445dfe  mov     r13d, 0Fh
0x100445e04  mov     [rbp+160h+var_178], r13
0x100445e08  mov     byte ptr [rbp+160h+var_190], dil
0x100445e0c  mov     rax, qword ptr [rbp+160h+var_1E0]
0x100445e10  lea     r8, [rcx+rax*2]
0x100445e14  mov     r9b, [rsp+260h+var_230]
0x100445e19  lea     rcx, [rbp+160h+var_190]; Src
0x100445e1d  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100445e22  nop
0x100445e23  lea     r9, [rbp+160h+var_190]
0x100445e27  cmp     [rbp+160h+var_178], 10h
0x100445e2c  cmovnb  r9, [rbp+160h+var_190]
0x100445e31  lea     r8, [rbp+160h+var_170]
0x100445e35  cmp     [rbp+160h+var_158], 10h
0x100445e3a  cmovnb  r8, [rbp+160h+var_170]
0x100445e3f  lea     rdx, [rbp+160h+var_150]
0x100445e43  cmp     [rbp+160h+var_138], 10h
0x100445e48  cmovnb  rdx, [rbp+160h+var_150]
0x100445e4d  lea     rcx, [rbp+160h+var_130]
0x100445e51  cmp     [rbp+160h+var_118], 10h
0x100445e56  cmovnb  rcx, [rbp+160h+var_130]
0x100445e5b  mov     rax, cs:qword_1005D8FD0
0x100445e62  call    cs:__guard_dispatch_icall_fptr
0x100445e68  mov     [r15], rax
0x100445e6b  mov     dword ptr [r12], 16h
0x100445e73  cmp     [r15], rdi
0x100445e76  jnz     loc_1004461F8
0x100445e7c  call    cs:__imp_GetLastError
0x100445e82  mov     ebx, eax
0x100445e84  mov     rcx, [rbp+160h+var_178]
0x100445e88  mov     esi, 1000h
0x100445e8d  cmp     rcx, 10h
0x100445e91  jb      short loc_100445EE3
0x100445e93  inc     rcx
0x100445e96  mov     rdx, [rbp+160h+var_190]
0x100445e9a  mov     r8, rdx
0x100445e9d  cmp     rcx, rsi
0x100445ea0  jb      short loc_100445ECA
0x100445ea2  test    r8b, 1Fh
0x100445ea6  jnz     loc_10044636B
0x100445eac  mov     rdx, [rdx-8]
0x100445eb0  cmp     rdx, r8
0x100445eb3  jnb     loc_10044636B
0x100445eb9  sub     r8, rdx
0x100445ebc  sub     r8, 8
0x100445ec0  cmp     r8, 1Fh
0x100445ec4  ja      loc_10044636B
0x100445eca  test    rdx, rdx
0x100445ecd  jz      short loc_100445EE3
0x100445ecf  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100445ed6  mov     rax, [rcx]
0x100445ed9  mov     rax, [rax+68h]
0x100445edd  call    cs:__guard_dispatch_icall_fptr
0x100445ee3  mov     [rbp+160h+var_180], rdi
0x100445ee7  mov     [rbp+160h+var_178], r13
0x100445eeb  mov     byte ptr [rbp+160h+var_190], dil
0x100445eef  mov     rax, qword ptr [rbp+160h+var_1E0+8]
0x100445ef3  mov     r14, 7FFFFFFFFFFFFFFFh
0x100445efd  cmp     rax, 8
0x100445f01  jb      short loc_100445F5F
0x100445f03  inc     rax
0x100445f06  mov     rdx, [rsp+260h+var_1F0]
0x100445f0b  mov     rcx, rdx
0x100445f0e  cmp     rax, r14
0x100445f11  ja      loc_100446454
0x100445f17  add     rax, rax
0x100445f1a  cmp     rax, rsi
0x100445f1d  jb      short loc_100445F46
0x100445f1f  test    cl, 1Fh
0x100445f22  jnz     loc_100446454
0x100445f28  mov     rdx, [rdx-8]
0x100445f2c  cmp     rdx, rcx
0x100445f2f  jnb     loc_100446454
0x100445f35  sub     rcx, rdx
0x100445f38  sub     rcx, 8
0x100445f3c  cmp     rcx, 1Fh
0x100445f40  ja      loc_100446454
0x100445f46  test    rdx, rdx
0x100445f49  jz      short loc_100445F5F
0x100445f4b  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100445f52  mov     rax, [rcx]
0x100445f55  mov     rax, [rax+68h]
0x100445f59  call    cs:__guard_dispatch_icall_fptr
0x100445f5f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445f67  movdqu  [rbp+160h+var_1E0], xmm0
0x100445f6c  mov     word ptr [rsp+260h+var_1F0], di
0x100445f71  mov     rax, [rbp+160h+var_158]
0x100445f75  cmp     rax, 10h
0x100445f79  jb      short loc_100445FCA
0x100445f7b  inc     rax
0x100445f7e  mov     rdx, [rbp+160h+var_170]
0x100445f82  mov     rcx, rdx
  ... truncated ...
```
