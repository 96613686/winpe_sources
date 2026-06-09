# SNISecMSQAGetAccessToken

- ea: `0x100446aac`
- end: `0x1004479dc`
- name: `SNISecMSQAGetAccessToken`
- size: `3888`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *, __int64, unsigned __int16 *, char, MSQAAuthContextCache *, __int64, __int64, __int64, __int64, __int64, unsigned int *, int, int, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x100453f4c`
- `0x100486398`

## callees

- `0x100430824`
- `0x100444028`
- `0x100445a64`
- `0x100446aac`
- `0x100546aa8`
- `0x100547fc3`
- `0x100547fcf`
- `0x100547fdb`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10044759c`
- `KERNEL32!WaitForSingleObject` at `0x10044759c`
- `KERNEL32!GetLastError` at `0x100446ddd`
- `KERNEL32!GetLastError` at `0x100446fce`
- `KERNEL32!GetLastError` at `0x100446ddd`
- `KERNEL32!GetLastError` at `0x100446fce`
- `KERNEL32!CloseHandle` at `0x1004475a5`
- `KERNEL32!CloseHandle` at `0x1004475a5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100447501`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100447508`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100447501`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100447508`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10044758d`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10044758d`

## pseudocode

```c
__int64 __fastcall SNISecMSQAGetAccessToken(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        __int64 a6,
        unsigned __int16 *a7,
        char a8,
        MSQAAuthContextCache *a9,
        __int64 *a10,
        int *a11,
        __int64 *a12,
        int *a13,
        DWORD *a14,
        unsigned int *a15,
        unsigned int a16,
        int a17,
        __int64 a18)
{
  struct _Mtx_internal_imp_t *v19; // rsi
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // r8
  _QWORD *v23; // rdx
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  __int64 v26; // r14
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // r8
  _QWORD *v33; // r8
  _QWORD *v34; // rdx
  _QWORD *v35; // rcx
  void *v36; // rax
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rdx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // rdx
  DWORD v49; // eax
  void *v50; // rbx
  char v51; // bl
  int v52; // eax
  DWORD v53; // eax
  __int64 v54; // r9
  wchar_t *v55; // r8
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rbx
  DWORD v59; // eax
  int *v60; // rcx
  int v61; // eax
  int v62; // eax
  __int64 v63; // rdx
  __int64 v64; // rbx
  int v65; // eax
  __int64 result; // rax
  DWORD LastError; // [rsp+40h] [rbp-C0h] BYREF
  _Mtx_t v68; // [rsp+48h] [rbp-B8h] BYREF
  void *v69; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A0h]
  __int64 v72; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v73; // [rsp+70h] [rbp-90h]
  __int64 v74; // [rsp+78h] [rbp-88h]
  __int64 v75; // [rsp+80h] [rbp-80h]
  __int64 *v76; // [rsp+88h] [rbp-78h]
  int *v77; // [rsp+90h] [rbp-70h]
  __int64 *v78; // [rsp+98h] [rbp-68h]
  int *v79; // [rsp+A0h] [rbp-60h]
  DWORD *v80; // [rsp+A8h] [rbp-58h]
  _QWORD Src[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v82; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v83; // [rsp+C8h] [rbp-38h]
  _QWORD v84[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v86; // [rsp+F0h] [rbp-10h] BYREF
  __m128i v87; // [rsp+100h] [rbp+0h]
  unsigned __int64 v88; // [rsp+110h] [rbp+10h] BYREF
  __m128i v89; // [rsp+120h] [rbp+20h]
  _QWORD v90[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v91; // [rsp+140h] [rbp+40h]
  unsigned __int64 v92; // [rsp+148h] [rbp+48h]
  _QWORD ArgList[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v94; // [rsp+160h] [rbp+60h]
  unsigned __int64 v95; // [rsp+168h] [rbp+68h]
  DWORD *p_LastError; // [rsp+170h] [rbp+70h]
  char v97; // [rsp+178h] [rbp+78h]
  int v98; // [rsp+17Ch] [rbp+7Ch]
  __int64 v99; // [rsp+180h] [rbp+80h]

  v73 = a1;
  v70 = a4;
  v75 = a18;
  *a11 = 0;
  v19 = 0;
  v74 = a2;
  *a13 = 0;
  *a10 = 0;
  *a12 = 0;
  *a14 = -1;
  v78 = a12;
  v20 = -1;
  v72 = a6;
  v77 = a11;
  v80 = a14;
  v76 = a10;
  v79 = a13;
  v69 = 0;
  v68 = 0;
  LOBYTE(v71) = 18;
  *a15 = 1;
  if ( a8 == 4 )
  {
    LastError = MSQAAuthContextCache::getOrCreate(a9, a3, a7, a5, a1, &v69, &v68, a15);
    if ( LastError )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E6410[0] )
        bidTraceW(0, 623616, off_1005E6410[0], LastError);
      goto LABEL_194;
    }
    v19 = v68;
LABEL_7:
    ((void (__fastcall *)(void *, __int64, _QWORD))qword_1005D8FD8)(v69, 1, a16);
    if ( v19 )
    {
      v21 = Mtx_lock_0(v19);
      if ( v21 )
        std::_Throw_C_error(v21);
    }
    v22 = -1;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v84[0]) = 0;
    do
      ++v22;
    while ( *(_WORD *)(v70 + 2 * v22) );
    std::wstring::assign(v84);
    v82 = 0;
    v83 = 15;
    LOBYTE(Src[0]) = 0;
    std::string::_Construct<unsigned short *>(Src);
    v23 = Src;
    if ( v83 >= 0x10 )
      v23 = (_QWORD *)Src[0];
    v24 = ((__int64 (__fastcall *)(void *, _QWORD *, __int64))qword_1005D8FE0)(v69, v23, v72);
    v25 = v83;
    v26 = v24;
    *a15 = 5;
    if ( v25 >= 0x10 )
    {
      v27 = Src[0];
      v28 = Src[0];
      if ( v25 + 1 >= 0x1000 )
      {
        if ( (Src[0] & 0x1F) != 0 )
          goto LABEL_144;
        v27 = *(_QWORD *)(Src[0] - 8LL);
        if ( v27 >= Src[0] )
          goto LABEL_144;
        v28 = Src[0] - v27 - 8;
        if ( v28 > 0x1F )
          goto LABEL_144;
      }
      if ( v27 )
        ((void (__fastcall *)(struct IMalloc *, unsigned __int64, unsigned __int64))g_pMO->lpVtbl[1].Realloc)(
          g_pMO,
          v27,
          v28);
    }
    v82 = 0;
    v83 = 15;
    LOBYTE(Src[0]) = 0;
    if ( si128.m128i_i64[1] < 8uLL )
      goto LABEL_29;
    v29 = v84[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) < 0x1000
        || (v84[0] & 0x1F) == 0 && (v29 = *(_QWORD *)(v84[0] - 8LL), v29 < v84[0]) && v84[0] - v29 - 8 <= 0x1F )
      {
        if ( v29 )
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
LABEL_29:
        LOWORD(v84[0]) = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        if ( !v26 )
        {
          LastError = GetLastError();
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_1005E6420[0] )
              bidTraceW(0, 667648, off_1005E6420[0], LastError);
            v19 = v68;
          }
          if ( v19 )
          {
            v30 = Mtx_unlock_0(v19);
            if ( v30 )
              std::_Throw_C_error(v30);
          }
          goto LABEL_194;
        }
        v49 = ((__int64 (__fastcall *)(__int64))qword_1005D8FF8)(v26);
        LastError = v49;
        *a15 = 17;
        if ( v49 == 1 )
        {
          ArgList[1] = v73;
          v94 = v74;
          p_LastError = &LastError;
          v97 = a8;
          v98 = a17;
          v99 = v75;
          ArgList[0] = v26;
          v95 = (unsigned __int64)a15;
          v50 = (void *)_beginthreadex(0, 0, MSQAThread, ArgList, 0, 0);
          WaitForSingleObject(v50, 0xFFFFFFFF);
          CloseHandle(v50);
        }
        else if ( !LastError )
        {
          v51 = a8;
          if ( a8 != 4 )
          {
            LastError = -894828543;
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_1005E6428[0] )
                bidTraceW(0, 692224, off_1005E6428[0], 3400138753LL);
              v19 = v68;
            }
          }
LABEL_148:
          if ( v19 )
          {
            v52 = Mtx_unlock_0(v19);
            if ( v52 )
              std::_Throw_C_error(v52);
          }
          if ( !LastError )
          {
            if ( v51 == 4 )
            {
              ((void (__fastcall *)(void *, __int64))qword_1005D8FD8)(v69, 2);
              *a15 = 23;
            }
            LODWORD(v68) = 0;
            v53 = ((__int64 (__fastcall *)(__int64, _QWORD, _Mtx_t *))qword_1005D8FE8)(v26, 0, &v68);
            v54 = 2147500037LL;
            *a15 = 9;
            LastError = v53;
            if ( v53 == -2147467259 )
            {
              if ( (bidGblFlags & 2) == 0 || !off_1005E6430[0] )
                goto LABEL_193;
              v55 = off_1005E6430[0];
              v56 = 711680;
              goto LABEL_158;
            }
            v57 = 2LL * (unsigned int)((_DWORD)v68 + 1);
            if ( !is_mul_ok((unsigned int)((_DWORD)v68 + 1), 2u) )
              v57 = -1;
            v58 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 112LL))(gpmo, v57);
            if ( !v58 )
            {
              v54 = 14;
              LastError = 14;
              if ( (bidGblFlags & 2) == 0 || !off_1005E6438[0] )
                goto LABEL_193;
              v55 = off_1005E6438[0];
              v56 = 717824;
              goto LABEL_158;
            }
            v59 = ((__int64 (__fastcall *)(__int64, __int64, _Mtx_t *))qword_1005D8FE8)(v26, v58, &v68);
            *a15 = 8;
            LastError = v59;
            if ( (bidGblFlags & 2) != 0 && off_1005E6440[0] )
              bidTraceW(0, 722944, off_1005E6440[0], LastError);
            if ( LastError )
            {
              ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v58);
              goto LABEL_193;
            }
            v60 = v77;
            *(_WORD *)(v58 + 2LL * (unsigned int)v68) = 0;
            *v76 = v58;
            v61 = 2 * (_DWORD)v68 + 2;
LABEL_192:
            *v60 = v61;
            goto LABEL_193;
          }
          v70 = 0;
          LODWORD(v68) = 0;
          v62 = ((__int64 (__fastcall *)(__int64, _QWORD, _Mtx_t *, __int64 *))qword_1005D8FF0)(v26, 0, &v68, &v70);
          v54 = 2147500037LL;
          *a15 = 11;
          if ( v62 == -2147467259 )
          {
            if ( (bidGblFlags & 2) == 0 || !off_1005E6448[0] )
              goto LABEL_193;
            v55 = off_1005E6448[0];
            v56 = 756736;
          }
          else
          {
            v63 = 2LL * (unsigned int)((_DWORD)v68 + 1);
            if ( !is_mul_ok((unsigned int)((_DWORD)v68 + 1), 2u) )
              v63 = -1;
            v64 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 112LL))(gpmo, v63);
            if ( v64 )
            {
              v65 = ((__int64 (__fastcall *)(__int64, __int64, _Mtx_t *, __int64 *))qword_1005D8FF0)(
                      v26,
                      v64,
                      &v68,
                      &v70);
              *a15 = 10;
              if ( !v65 )
              {
                LastError = v70;
                v71 = v70 >> 56;
                v60 = v79;
                *(_WORD *)(v64 + 2LL * (unsigned int)v68) = 0;
                *v78 = v64;
                v61 = (int)v68;
                goto LABEL_192;
              }
              ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v64);
              if ( (bidGblFlags & 2) == 0 || !off_1005E6458[0] )
                goto LABEL_193;
              v54 = LastError;
              v56 = 772096;
              v55 = off_1005E6458[0];
            }
            else
            {
              v54 = 14;
              LastError = 14;
              if ( (bidGblFlags & 2) == 0 || !off_1005E6450[0] )
                goto LABEL_193;
              v55 = off_1005E6450[0];
              v56 = 759808;
            }
          }
LABEL_158:
          bidTraceW(0, v56, v55, v54);
LABEL_193:
          ((void (__fastcall *)(__int64))qword_1005D9010)(v26);
LABEL_194:
          if ( v69 && a8 != 4 )
            ((void (__fastcall *)(void *))qword_1005D9018)(v69);
          goto LABEL_197;
        }
        v51 = a8;
        goto LABEL_148;
      }
    }
LABEL_144:
    _invalid_parameter_noinfo_noreturn();
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v84[0]) = 0;
  do
    ++v20;
  while ( a3[v20] );
  std::wstring::assign(v84);
  v82 = 0;
  v83 = 15;
  LOBYTE(Src[0]) = 0;
  std::string::_Construct<unsigned short *>(Src);
  v89 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v88) = 0;
  v31 = -1;
  do
    ++v31;
  while ( a7[v31] );
  std::wstring::assign(&v88);
  v94 = 0;
  v95 = 15;
  LOBYTE(ArgList[0]) = 0;
  std::string::_Construct<unsigned short *>(ArgList);
  v32 = -1;
  v87 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v86) = 0;
  do
    ++v32;
  while ( a5[v32] );
  std::wstring::assign(&v86);
  v92 = 15;
  v91 = 0;
  LOBYTE(v90[0]) = 0;
  std::string::_Construct<unsigned short *>(v90);
  v33 = v90;
  v34 = ArgList;
  if ( v92 >= 0x10 )
    v33 = (_QWORD *)v90[0];
  v35 = Src;
  if ( v95 >= 0x10 )
    v34 = (_QWORD *)ArgList[0];
  if ( v83 >= 0x10 )
    v35 = (_QWORD *)Src[0];
  v36 = (void *)qword_1005D8FC8(v35, v34, v33);
  v69 = v36;
  *a15 = 3;
  if ( v36 )
  {
    if ( v92 >= 0x10 )
    {
      v43 = v90[0];
      if ( v92 + 1 >= 0x1000 )
      {
        if ( (v90[0] & 0x1F) != 0 )
          goto LABEL_143;
        v43 = *(_QWORD *)(v90[0] - 8LL);
        if ( v43 >= v90[0] || v90[0] - v43 - 8 > 0x1F )
          goto LABEL_143;
      }
      if ( v43 )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    }
    v91 = 0;
    v92 = 15;
    LOBYTE(v90[0]) = 0;
    if ( v87.m128i_i64[1] >= 8uLL )
    {
      v44 = v86;
      if ( (unsigned __int64)(v87.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_143;
      if ( (unsigned __int64)(2 * (v87.m128i_i64[1] + 1)) >= 0x1000 )
      {
        if ( (v86 & 0x1F) != 0 )
          goto LABEL_143;
        v44 = *(_QWORD *)(v86 - 8);
        if ( v44 >= v86 || v86 - v44 - 8 > 0x1F )
          goto LABEL_143;
      }
      if ( v44 )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    }
    LOWORD(v86) = 0;
    v87 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v95 >= 0x10 )
    {
      v45 = ArgList[0];
      if ( v95 + 1 >= 0x1000 )
      {
        if ( (ArgList[0] & 0x1F) != 0 )
          goto LABEL_143;
        v45 = *(_QWORD *)(ArgList[0] - 8LL);
        if ( v45 >= ArgList[0] || ArgList[0] - v45 - 8 > 0x1F )
          goto LABEL_143;
      }
      if ( v45 )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    }
    v94 = 0;
    v95 = 15;
    LOBYTE(ArgList[0]) = 0;
    if ( v89.m128i_i64[1] >= 8uLL )
    {
      v46 = v88;
      if ( (unsigned __int64)(v89.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_143;
      if ( (unsigned __int64)(2 * (v89.m128i_i64[1] + 1)) >= 0x1000 )
      {
        if ( (v88 & 0x1F) != 0 )
          goto LABEL_143;
        v46 = *(_QWORD *)(v88 - 8);
        if ( v46 >= v88 || v88 - v46 - 8 > 0x1F )
          goto LABEL_143;
      }
      if ( v46 )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    }
    LOWORD(v88) = 0;
    v89 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v83 >= 0x10 )
    {
      v47 = Src[0];
      if ( v83 + 1 >= 0x1000 )
      {
        if ( (Src[0] & 0x1F) != 0 )
          goto LABEL_143;
        v47 = *(_QWORD *)(Src[0] - 8LL);
        if ( v47 >= Src[0] || Src[0] - v47 - 8 > 0x1F )
          goto LABEL_143;
      }
      if ( v47 )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    }
    v82 = 0;
    v83 = 15;
    LOBYTE(Src[0]) = 0;
    if ( si128.m128i_i64[1] < 8uLL )
      goto LABEL_7;
    v48 = v84[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) < 0x1000
        || (v84[0] & 0x1F) == 0 && (v48 = *(_QWORD *)(v84[0] - 8LL), v48 < v84[0]) && v84[0] - v48 - 8 <= 0x1F )
      {
        if ( v48 )
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
        goto LABEL_7;
      }
    }
LABEL_143:
    _invalid_parameter_noinfo_noreturn();
  }
  LastError = GetLastError();
  if ( (bidGblFlags & 2) != 0 && off_1005E6418[0] )
    bidTraceW(0, 645120, off_1005E6418[0], LastError);
  if ( v92 >= 0x10 )
  {
    v37 = v90[0];
    if ( v92 + 1 >= 0x1000 )
    {
      if ( (v90[0] & 0x1F) != 0 )
        goto LABEL_143;
      v37 = *(_QWORD *)(v90[0] - 8LL);
      if ( v37 >= v90[0] || v90[0] - v37 - 8 > 0x1F )
        goto LABEL_143;
    }
    if ( v37 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v91 = 0;
  v92 = 15;
  LOBYTE(v90[0]) = 0;
  if ( v87.m128i_i64[1] >= 8uLL )
  {
    v38 = v86;
    if ( (unsigned __int64)(v87.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_143;
    if ( (unsigned __int64)(2 * (v87.m128i_i64[1] + 1)) >= 0x1000 )
    {
      if ( (v86 & 0x1F) != 0 )
        goto LABEL_143;
      v38 = *(_QWORD *)(v86 - 8);
      if ( v38 >= v86 || v86 - v38 - 8 > 0x1F )
        goto LABEL_143;
    }
    if ( v38 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  LOWORD(v86) = 0;
  v87 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v95 >= 0x10 )
  {
    v39 = ArgList[0];
    if ( v95 + 1 >= 0x1000 )
    {
      if ( (ArgList[0] & 0x1F) != 0 )
        goto LABEL_143;
      v39 = *(_QWORD *)(ArgList[0] - 8LL);
      if ( v39 >= ArgList[0] || ArgList[0] - v39 - 8 > 0x1F )
        goto LABEL_143;
    }
    if ( v39 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v94 = 0;
  v95 = 15;
  LOBYTE(ArgList[0]) = 0;
  if ( v89.m128i_i64[1] >= 8uLL )
  {
    v40 = v88;
    if ( (unsigned __int64)(v89.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_143;
    if ( (unsigned __int64)(2 * (v89.m128i_i64[1] + 1)) >= 0x1000 )
    {
      if ( (v88 & 0x1F) != 0 )
        goto LABEL_143;
      v40 = *(_QWORD *)(v88 - 8);
      if ( v40 >= v88 || v88 - v40 - 8 > 0x1F )
        goto LABEL_143;
    }
    if ( v40 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  LOWORD(v88) = 0;
  v89 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v83 >= 0x10 )
  {
    v41 = Src[0];
    if ( v83 + 1 >= 0x1000 )
    {
      if ( (Src[0] & 0x1F) != 0 )
        goto LABEL_143;
      v41 = *(_QWORD *)(Src[0] - 8LL);
      if ( v41 >= Src[0] || Src[0] - v41 - 8 > 0x1F )
        goto LABEL_143;
    }
    if ( v41 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v82 = 0;
  v83 = 15;
  LOBYTE(Src[0]) = 0;
  if ( si128.m128i_i64[1] < 8uLL )
    goto LABEL_197;
  v42 = v84[0];
  if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_143;
  if ( (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000 )
  {
    if ( (v84[0] & 0x1F) != 0 )
      goto LABEL_143;
    v42 = *(_QWORD *)(v84[0] - 8LL);
    if ( v42 >= v84[0] || v84[0] - v42 - 8 > 0x1F )
      goto LABEL_143;
  }
  if ( v42 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
LABEL_197:
  if ( LastError )
  {
    if ( LastError == -895352829 )
    {
      result = 1;
    }
    else if ( (unsigned __int8)(v71 - 4) <= 1u || (_BYTE)v71 == 15 )
    {
      result = 2;
    }
    else
    {
      result = 3;
    }
  }
  else
  {
    result = 0;
    *a15 = 0;
  }
  *v80 = LastError;
  return result;
}

```

## disassembly

```asm
0x100446aac  push    rbp
0x100446aae  push    rbx
0x100446aaf  push    rsi
0x100446ab0  push    rdi
0x100446ab1  push    r12
0x100446ab3  push    r13
0x100446ab5  push    r14
0x100446ab7  push    r15
0x100446ab9  lea     rbp, [rsp-98h]
0x100446ac1  sub     rsp, 198h
0x100446ac8  mov     rax, cs:__security_cookie
0x100446acf  xor     rax, rsp
0x100446ad2  mov     [rbp+0D0h+var_48], rax
0x100446ad9  mov     rbx, [rbp+0D0h+arg_50]
0x100446ae0  mov     rax, r8
0x100446ae3  mov     r8, [rbp+0D0h+arg_58]
0x100446aea  mov     r12, 7FFFFFFFFFFFFFFFh
0x100446af4  mov     rdi, [rbp+0D0h+arg_68]
0x100446afb  mov     r10, [rbp+0D0h+arg_88]
0x100446b02  mov     r11, [rbp+0D0h+arg_48]
0x100446b09  mov     r13, [rbp+0D0h+arg_70]
0x100446b10  mov     r15, [rbp+0D0h+arg_20]
0x100446b17  mov     r14, [rbp+0D0h+arg_30]
0x100446b1e  mov     [rsp+1D0h+var_160], rcx
0x100446b23  mov     [rsp+1D0h+var_178], r9
0x100446b28  mov     r9, [rbp+0D0h+arg_60]
0x100446b2f  mov     [rbp+0D0h+var_150], r10
0x100446b33  xor     r10d, r10d
0x100446b36  mov     [rbx], r10d
0x100446b39  mov     esi, r10d
0x100446b3c  mov     [rsp+1D0h+var_158], rdx
0x100446b41  mov     rdx, rcx
0x100446b44  mov     rcx, [rbp+0D0h+arg_28]
0x100446b4b  mov     [r9], r10d
0x100446b4e  mov     [r11], r10
0x100446b51  mov     [r8], r10
0x100446b54  or      dword ptr [rdi], 0FFFFFFFFh
0x100446b57  mov     [rbp+0D0h+var_138], r8
0x100446b5b  or      r8, 0FFFFFFFFFFFFFFFFh
0x100446b5f  cmp     [rbp+0D0h+arg_38], 4
0x100446b66  mov     [rsp+1D0h+var_168], rcx
0x100446b6b  mov     rcx, [rbp+0D0h+arg_40]; this
0x100446b72  mov     [rbp+0D0h+var_140], rbx
0x100446b76  lea     ebx, [r10+1Fh]
0x100446b7a  mov     [rbp+0D0h+var_128], rdi
0x100446b7e  mov     edi, 1000h
0x100446b83  mov     [rbp+0D0h+var_148], r11
0x100446b87  mov     [rbp+0D0h+var_130], r9
0x100446b8b  mov     [rsp+1D0h+var_180], r10
0x100446b90  mov     [rsp+1D0h+var_188], r10
0x100446b95  mov     byte ptr [rsp+1D0h+var_170], 12h
0x100446b9a  mov     dword ptr [r13+0], 1
0x100446ba2  jnz     loc_100446E3E
0x100446ba8  mov     [rsp+1D0h+var_198], r13; unsigned int *
0x100446bad  lea     r8, [rsp+1D0h+var_188]
0x100446bb2  mov     [rsp+1D0h+var_1A0], r8; struct std::mutex **
0x100446bb7  mov     r9, r15; unsigned __int16 *
0x100446bba  lea     r8, [rsp+1D0h+var_180]
0x100446bbf  mov     [rsp+1D0h+ThrdAddr], r8; void **
0x100446bc4  mov     r8, r14; unsigned __int16 *
0x100446bc7  mov     qword ptr [rsp+1D0h+InitFlag], rdx; unsigned __int16 *
0x100446bcc  mov     rdx, rax; unsigned __int16 *
0x100446bcf  call    ?getOrCreate@MSQAAuthContextCache@@QEAAKPEBG000AEAPEAXAEAPEAVmutex@std@@AEAK@Z; MSQAAuthContextCache::getOrCreate(ushort const *,ushort const *,ushort const *,ushort const *,void * &,std::mutex * &,ulong &)
0x100446bd4  xor     r15d, r15d
0x100446bd7  mov     [rsp+1D0h+var_190], eax
0x100446bdb  test    eax, eax
0x100446bdd  jz      short loc_100446C19
0x100446bdf  test    byte ptr cs:_bidGblFlags, 2
0x100446be6  jz      loc_10044794E
0x100446bec  mov     rax, cs:off_1005E6410; "<SNISecMSQAGetAccessToken|ERR|SNI> Fail"...
0x100446bf3  test    rax, rax
0x100446bf6  jz      loc_10044794E
0x100446bfc  mov     r9d, [rsp+1D0h+var_190]
0x100446c01  mov     edx, 98400h
0x100446c06  mov     r8, cs:off_1005E6410; "<SNISecMSQAGetAccessToken|ERR|SNI> Fail"...
0x100446c0d  xor     ecx, ecx
0x100446c0f  call    _bidTraceW
0x100446c14  jmp     loc_10044794E
0x100446c19  mov     rsi, [rsp+1D0h+var_188]
0x100446c1e  mov     r14d, 8
0x100446c24  mov     r8d, [rbp+0D0h+arg_78]
0x100446c2b  mov     edx, 1
0x100446c30  mov     rcx, [rsp+1D0h+var_180]
0x100446c35  mov     rax, cs:qword_1005D8FD8
0x100446c3c  call    cs:__guard_dispatch_icall_fptr
0x100446c42  test    rsi, rsi
0x100446c45  jz      short loc_100446C5A
0x100446c47  mov     rcx, rsi; _Mtx_t
0x100446c4a  call    _Mtx_lock_0
0x100446c4f  test    eax, eax
0x100446c51  jz      short loc_100446C5A
0x100446c53  mov     ecx, eax; int
0x100446c55  call    ?_Throw_C_error@std@@YAXH@Z_0; std::_Throw_C_error(int)
0x100446c5a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100446c62  or      r8, 0FFFFFFFFFFFFFFFFh
0x100446c66  mov     rax, [rsp+1D0h+var_178]
0x100446c6b  movdqu  [rbp+0D0h+var_F0], xmm0
0x100446c70  mov     word ptr [rbp+0D0h+var_100], r15w
0x100446c75  inc     r8
0x100446c78  cmp     [rax+r8*2], r15w
0x100446c7d  jnz     short loc_100446C75
0x100446c7f  mov     rdx, rax
0x100446c82  lea     rcx, [rbp+0D0h+var_100]; void *
0x100446c86  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100446c8b  cmp     qword ptr [rbp+0D0h+var_F0+8], r14
0x100446c8f  lea     rcx, [rbp+0D0h+var_100]
0x100446c93  mov     rax, qword ptr [rbp+0D0h+var_F0]
0x100446c97  lea     rdx, [rbp+0D0h+var_100]
0x100446c9b  cmovnb  rcx, [rbp+0D0h+var_100]
0x100446ca0  cmovnb  rdx, [rbp+0D0h+var_100]
0x100446ca5  mov     r9b, [rsp+1D0h+var_18C]
0x100446caa  mov     [rbp+0D0h+var_110], r15
0x100446cae  lea     r8, [rcx+rax*2]
0x100446cb2  mov     [rbp+0D0h+var_108], 0Fh
0x100446cba  lea     rcx, [rbp+0D0h+Src]; Src
0x100446cbe  mov     byte ptr [rbp+0D0h+Src], r15b
0x100446cc2  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100446cc7  cmp     [rbp+0D0h+var_108], 10h
0x100446ccc  lea     rdx, [rbp+0D0h+Src]
0x100446cd0  mov     r8, [rsp+1D0h+var_168]
0x100446cd5  cmovnb  rdx, [rbp+0D0h+Src]
0x100446cda  mov     rcx, [rsp+1D0h+var_180]
0x100446cdf  mov     rax, cs:qword_1005D8FE0
0x100446ce6  call    cs:__guard_dispatch_icall_fptr
0x100446cec  mov     rcx, [rbp+0D0h+var_108]
0x100446cf0  mov     r14, rax
0x100446cf3  mov     dword ptr [r13+0], 5
0x100446cfb  cmp     rcx, 10h
0x100446cff  jb      short loc_100446D4F
0x100446d01  mov     rdx, [rbp+0D0h+Src]
0x100446d05  inc     rcx
0x100446d08  mov     r8, rdx
0x100446d0b  cmp     rcx, rdi
0x100446d0e  jb      short loc_100446D36
0x100446d10  test    bl, r8b
0x100446d13  jnz     loc_100447508
0x100446d19  mov     rdx, [rdx-8]
0x100446d1d  cmp     rdx, r8
0x100446d20  jnb     loc_100447508
0x100446d26  sub     r8, rdx
0x100446d29  sub     r8, 8
0x100446d2d  cmp     r8, rbx
0x100446d30  ja      loc_100447508
0x100446d36  test    rdx, rdx
0x100446d39  jz      short loc_100446D4F
0x100446d3b  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100446d42  mov     rax, [rcx]
0x100446d45  mov     rax, [rax+68h]
0x100446d49  call    cs:__guard_dispatch_icall_fptr
0x100446d4f  mov     rax, qword ptr [rbp+0D0h+var_F0+8]
0x100446d53  mov     [rbp+0D0h+var_110], r15
0x100446d57  mov     [rbp+0D0h+var_108], 0Fh
0x100446d5f  mov     byte ptr [rbp+0D0h+Src], r15b
0x100446d63  cmp     rax, 8
0x100446d67  jb      short loc_100446DC2
0x100446d69  mov     rdx, [rbp+0D0h+var_100]
0x100446d6d  inc     rax
0x100446d70  mov     rcx, rdx
0x100446d73  cmp     rax, r12
0x100446d76  ja      loc_100447508
0x100446d7c  add     rax, rax
0x100446d7f  cmp     rax, rdi
0x100446d82  jb      short loc_100446DA9
0x100446d84  test    bl, cl
0x100446d86  jnz     loc_100447508
0x100446d8c  mov     rdx, [rdx-8]
0x100446d90  cmp     rdx, rcx
0x100446d93  jnb     loc_100447508
0x100446d99  sub     rcx, rdx
0x100446d9c  sub     rcx, 8
0x100446da0  cmp     rcx, rbx
0x100446da3  ja      loc_100447508
0x100446da9  test    rdx, rdx
0x100446dac  jz      short loc_100446DC2
0x100446dae  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100446db5  mov     rax, [rcx]
0x100446db8  mov     rax, [rax+68h]
0x100446dbc  call    cs:__guard_dispatch_icall_fptr
0x100446dc2  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100446dca  mov     word ptr [rbp+0D0h+var_100], r15w
0x100446dcf  movdqu  [rbp+0D0h+var_F0], xmm0
0x100446dd4  test    r14, r14
0x100446dd7  jnz     loc_10044750F
0x100446ddd  call    cs:__imp_GetLastError
0x100446de3  test    byte ptr cs:_bidGblFlags, 2
0x100446dea  mov     [rsp+1D0h+var_190], eax
0x100446dee  jz      short loc_100446E19
0x100446df0  mov     rax, cs:off_1005E6420; "<SNISecMSQAGetAccessToken|ERR|SNI> MSQA"...
0x100446df7  test    rax, rax
0x100446dfa  jz      short loc_100446E14
0x100446dfc  mov     r9d, [rsp+1D0h+var_190]
0x100446e01  mov     edx, 0A3000h
0x100446e06  mov     r8, cs:off_1005E6420; "<SNISecMSQAGetAccessToken|ERR|SNI> MSQA"...
0x100446e0d  xor     ecx, ecx
0x100446e0f  call    _bidTraceW
0x100446e14  mov     rsi, [rsp+1D0h+var_188]
0x100446e19  test    rsi, rsi
0x100446e1c  jz      loc_10044794E
0x100446e22  mov     rcx, rsi; _Mtx_t
0x100446e25  call    _Mtx_unlock_0
0x100446e2a  test    eax, eax
0x100446e2c  jz      loc_10044794E
0x100446e32  mov     ecx, eax; int
0x100446e34  call    ?_Throw_C_error@std@@YAXH@Z_0; std::_Throw_C_error(int)
0x100446e39  jmp     loc_10044794E
0x100446e3e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100446e46  movdqu  [rbp+0D0h+var_F0], xmm0
0x100446e4b  mov     word ptr [rbp+0D0h+var_100], r10w
0x100446e50  inc     r8
0x100446e53  cmp     [rax+r8*2], r10w
0x100446e58  jnz     short loc_100446E50
0x100446e5a  mov     rdx, rax
0x100446e5d  lea     rcx, [rbp+0D0h+var_100]; void *
0x100446e61  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100446e66  cmp     qword ptr [rbp+0D0h+var_F0+8], 8
0x100446e6b  lea     rcx, [rbp+0D0h+var_100]
0x100446e6f  mov     rax, qword ptr [rbp+0D0h+var_F0]
0x100446e73  lea     rdx, [rbp+0D0h+var_100]
0x100446e77  cmovnb  rcx, [rbp+0D0h+var_100]
0x100446e7c  cmovnb  rdx, [rbp+0D0h+var_100]
0x100446e81  mov     r9b, [rsp+1D0h+var_18C]
0x100446e86  and     [rbp+0D0h+var_110], rsi
0x100446e8a  lea     r8, [rcx+rax*2]
0x100446e8e  mov     [rbp+0D0h+var_108], 0Fh
0x100446e96  lea     rcx, [rbp+0D0h+Src]; Src
0x100446e9a  mov     byte ptr [rbp+0D0h+Src], sil
0x100446e9e  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100446ea3  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100446eab  xor     eax, eax
0x100446ead  movdqu  [rbp+0D0h+var_B0], xmm0
0x100446eb2  mov     word ptr [rbp+0D0h+var_C0], ax
0x100446eb6  or      r8, 0FFFFFFFFFFFFFFFFh
0x100446eba  inc     r8
0x100446ebd  cmp     [r14+r8*2], ax
0x100446ec2  jnz     short loc_100446EBA
0x100446ec4  mov     rdx, r14
0x100446ec7  lea     rcx, [rbp+0D0h+var_C0]; void *
0x100446ecb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100446ed0  cmp     qword ptr [rbp+0D0h+var_B0+8], 8
0x100446ed5  lea     rcx, [rbp+0D0h+var_C0]
0x100446ed9  mov     rax, qword ptr [rbp+0D0h+var_B0]
0x100446edd  lea     rdx, [rbp+0D0h+var_C0]
0x100446ee1  cmovnb  rcx, [rbp+0D0h+var_C0]
0x100446ee6  cmovnb  rdx, [rbp+0D0h+var_C0]
0x100446eeb  xor     r14d, r14d
0x100446eee  mov     r9b, [rsp+1D0h+var_18C]
0x100446ef3  mov     [rbp+0D0h+var_70], r14
0x100446ef7  lea     r8, [rcx+rax*2]
0x100446efb  mov     [rbp+0D0h+var_68], 0Fh
0x100446f03  lea     rcx, [rbp+0D0h+ArgList]; Src
0x100446f07  mov     byte ptr [rbp+0D0h+ArgList], r14b
0x100446f0b  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100446f10  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100446f18  or      r8, 0FFFFFFFFFFFFFFFFh
0x100446f1c  movdqu  [rbp+0D0h+var_D0], xmm0
0x100446f21  mov     word ptr [rbp+0D0h+var_E0], r14w
0x100446f26  inc     r8
0x100446f29  cmp     [r15+r8*2], r14w
0x100446f2e  jnz     short loc_100446F26
0x100446f30  mov     rdx, r15
0x100446f33  lea     rcx, [rbp+0D0h+var_E0]; void *
0x100446f37  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100446f3c  mov     rax, qword ptr [rbp+0D0h+var_D0]
0x100446f40  lea     rcx, [rbp+0D0h+var_E0]
0x100446f44  mov     r9b, [rsp+1D0h+var_18C]
0x100446f49  lea     rdx, [rbp+0D0h+var_E0]
0x100446f4d  mov     r14d, 8
0x100446f53  mov     [rbp+0D0h+var_88], 0Fh
0x100446f5b  cmp     qword ptr [rbp+0D0h+var_D0+8], r14
0x100446f5f  cmovnb  rcx, [rbp+0D0h+var_E0]
0x100446f64  cmovnb  rdx, [rbp+0D0h+var_E0]
0x100446f69  xor     r15d, r15d
0x100446f6c  mov     [rbp+0D0h+var_90], r15
0x100446f70  mov     byte ptr [rbp+0D0h+var_A0], r15b
0x100446f74  lea     r8, [rcx+rax*2]
0x100446f78  lea     rcx, [rbp+0D0h+var_A0]; Src
0x100446f7c  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100446f81  cmp     [rbp+0D0h+var_88], 10h
0x100446f86  lea     r8, [rbp+0D0h+var_A0]
0x100446f8a  mov     rax, cs:qword_1005D8FC8
0x100446f91  lea     rdx, [rbp+0D0h+ArgList]
0x100446f95  cmovnb  r8, [rbp+0D0h+var_A0]
0x100446f9a  lea     rcx, [rbp+0D0h+Src]
0x100446f9e  cmp     [rbp+0D0h+var_68], 10h
0x100446fa3  cmovnb  rdx, [rbp+0D0h+ArgList]
0x100446fa8  cmp     [rbp+0D0h+var_108], 10h
0x100446fad  cmovnb  rcx, [rbp+0D0h+Src]
0x100446fb2  call    cs:__guard_dispatch_icall_fptr
0x100446fb8  mov     [rsp+1D0h+var_180], rax
0x100446fbd  mov     dword ptr [r13+0], 3
0x100446fc5  test    rax, rax
0x100446fc8  jnz     loc_10044728B
0x100446fce  call    cs:__imp_GetLastError
0x100446fd4  test    byte ptr cs:_bidGblFlags, 2
0x100446fdb  mov     [rsp+1D0h+var_190], eax
0x100446fdf  jz      short loc_100447005
0x100446fe1  mov     rax, cs:off_1005E6418; "<SNISecMSQAGetAccessToken|ERR|SNI> MSQA"...
0x100446fe8  test    rax, rax
0x100446feb  jz      short loc_100447005
0x100446fed  mov     r9d, [rsp+1D0h+var_190]
  ... truncated ...
```
