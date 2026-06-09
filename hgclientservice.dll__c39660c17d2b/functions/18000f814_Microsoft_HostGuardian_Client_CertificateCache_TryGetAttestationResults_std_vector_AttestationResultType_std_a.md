# Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults(std::vector<AttestationResultType,std::allocator<AttestationResultType>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>>>> &)

- ea: `0x18000f814`
- end: `0x18000fe0c`
- name: `?TryGetAttestationResults@CertificateCache@Client@HostGuardian@Microsoft@@QEAA_NV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@AEAV?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@6@@Z`
- size: `1528`
- prototype: `char __fastcall(RTL_SRWLOCK *this, char **, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18000d4d8`

## callees

- `0x180001770`
- `0x180001794`
- `0x180003e30`
- `0x180004274`
- `0x18000977c`
- `0x18000b8b0`
- `0x18000b990`
- `0x18000bedc`
- `0x18000c45c`
- `0x18000c4c8`
- `0x18000e9fc`
- `0x18000eaa4`
- `0x18000ec58`
- `0x18000eef0`
- `0x18000f548`
- `0x18000f814`
- `0x18000fe14`
- `0x180010b3c`
- `0x180010d20`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000f9e1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000fcea`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000fe05`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000f9e1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000fcea`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000fe05`
- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x18000f887`
- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x18000f887`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f879`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f8ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f879`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f8ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f898`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f9cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fd87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fdeb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f898`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f9cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fd87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fdeb`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000f86c`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000f86c`

## pseudocode

```c
char __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults(
        RTL_SRWLOCK *this,
        char **a2,
        __int64 a3,
        _BYTE *a4)
{
  __int64 v5; // r12
  double v8; // xmm0_8
  char *v9; // rcx
  _QWORD *Ptr; // r9
  _BYTE *v11; // rdx
  __int64 *v12; // r8
  int v13; // r10d
  __int64 *v14; // rax
  _QWORD *v15; // rdx
  __int64 *v16; // r8
  int v17; // r10d
  __int64 *v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rax
  char AttestationResultsInternal; // di
  _QWORD *v22; // rax
  int v23; // edi
  _QWORD *v24; // rdx
  __int64 v25; // rcx
  char v26; // r8
  __int64 *v27; // rax
  _QWORD *v28; // rdx
  _DWORD *v29; // rcx
  _BYTE *v30; // r9
  _DWORD *v31; // r8
  char v32; // r10
  _DWORD **v33; // rax
  char v34; // r8
  _QWORD *v35; // rax
  void *v36; // rdi
  const wchar_t *v37; // rdx
  size_t v38; // rsi
  size_t v39; // r12
  const wchar_t *v40; // rcx
  size_t v41; // r8
  int v42; // eax
  void *v43; // rax
  __int64 *v44; // rdi
  __int64 v45; // rsi
  __int64 v46; // rax
  __int64 **v47; // rcx
  __int64 *i; // rax
  __int64 v49; // rdi
  __int64 v50; // rax
  __int64 *j; // rcx
  __time64_t Time; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v54; // [rsp+28h] [rbp-D8h]
  __int128 v55; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v56[12]; // [rsp+40h] [rbp-C0h] BYREF
  int v57; // [rsp+4Ch] [rbp-B4h]
  __int64 v58; // [rsp+50h] [rbp-B0h]
  _BYTE *v59; // [rsp+58h] [rbp-A8h]
  void *v60[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v61[32]; // [rsp+78h] [rbp-88h] BYREF
  char **v62; // [rsp+98h] [rbp-68h]
  RTL_SRWLOCK *v63; // [rsp+A0h] [rbp-60h]
  wchar_t *S1[2]; // [rsp+A8h] [rbp-58h] BYREF
  size_t N; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v66; // [rsp+C0h] [rbp-40h]
  char *v67[5]; // [rsp+D0h] [rbp-30h] BYREF
  char *v68[3]; // [rsp+F8h] [rbp-8h] BYREF
  int v69; // [rsp+110h] [rbp+10h]

  v59 = a4;
  v5 = a3;
  v54 = a3;
  v62 = a2;
  Time = 0;
  _time64(&Time);
  AcquireSRWLockShared(this + 5);
  v8 = _o__difftime64(Time, this->Ptr);
  if ( this != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockShared(this + 5);
  if ( COERCE_DOUBLE(*(_QWORD *)&v8 & _xmm) >= 3600.0 )
    Microsoft::HostGuardian::Client::CertificateCache::RemoveAllInvalidCertificates(this);
  AcquireSRWLockShared(this + 5);
  v63 = this + 5;
  if ( this[2].Ptr )
  {
    v9 = *a2;
    if ( *a2 != a2[1] )
    {
      Ptr = this[1].Ptr;
      do
      {
        v57 = 0;
        v11 = Ptr;
        v12 = (__int64 *)Ptr[1];
        if ( !*((_BYTE *)v12 + 25) )
        {
          v13 = *(_DWORD *)v9;
          do
          {
            if ( *((_DWORD *)v12 + 8) >= v13 )
              v11 = v12;
            v14 = v12 + 2;
            if ( *((_DWORD *)v12 + 8) >= v13 )
              v14 = v12;
            v12 = (__int64 *)*v14;
          }
          while ( !*(_BYTE *)(*v14 + 25) );
        }
        if ( v11[25] || *(_DWORD *)v9 < *((_DWORD *)v11 + 8) || v11 == (_BYTE *)Ptr )
          goto LABEL_101;
        v57 = 0;
        v15 = Ptr;
        v16 = (__int64 *)Ptr[1];
        if ( !*((_BYTE *)v16 + 25) )
        {
          v17 = *(_DWORD *)v9;
          do
          {
            if ( *((_DWORD *)v16 + 8) >= v17 )
              v15 = v16;
            v18 = v16 + 2;
            if ( *((_DWORD *)v16 + 8) >= v17 )
              v18 = v16;
            v16 = (__int64 *)*v18;
          }
          while ( !*(_BYTE *)(*v18 + 25) );
        }
        if ( *((_BYTE *)v15 + 25) || *(_DWORD *)v9 < *((_DWORD *)v15 + 8) )
        {
          std::_Xout_of_range("invalid map<K, T> key");
          __debugbreak();
        }
        if ( !v15[6] )
          goto LABEL_101;
        v9 += 4;
      }
      while ( v9 != a2[1] );
    }
    if ( *(_QWORD *)(v5 + 16) )
    {
      v59 = v61;
      v19 = std::wstring::wstring((__int64)v61, v5);
      v20 = std::vector<enum AttestationResultType>::vector<enum AttestationResultType>(v56, a2);
      AttestationResultsInternal = Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal(
                                     this,
                                     v20,
                                     v19,
                                     a4);
      if ( this != (RTL_SRWLOCK *)-40LL )
        ReleaseSRWLockShared(this + 5);
LABEL_99:
      std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>(a2);
      return AttestationResultsInternal;
    }
    v55 = 0;
    v22 = operator new(0x50u);
    *v22 = v22;
    v22[1] = v22;
    v22[2] = v22;
    *((_WORD *)v22 + 12) = 257;
    *(_QWORD *)&v55 = v22;
    v23 = *(_DWORD *)*a2;
    LODWORD(Time) = v23;
    v24 = this[1].Ptr;
    v25 = v24[1];
    v57 = 0;
    while ( !*(_BYTE *)(v25 + 25) )
    {
      if ( *(_DWORD *)(v25 + 32) >= v23 )
      {
        v26 = 0;
        v24 = (_QWORD *)v25;
      }
      else
      {
        v26 = 1;
      }
      v27 = (__int64 *)(v25 + 16);
      if ( !v26 )
        v27 = (__int64 *)v25;
      v25 = *v27;
    }
    if ( *((_BYTE *)v24 + 25) || v23 < *((_DWORD *)v24 + 8) )
    {
      std::_Xout_of_range("invalid map<K, T> key");
      JUMPOUT(0x18000FE0BLL);
    }
    std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>(
      v60,
      v24 + 5);
    *(_OWORD *)S1 = 0;
    N = 0;
    v66 = 7;
    LOWORD(S1[0]) = 0;
    if ( !this[4].Ptr )
      goto LABEL_80;
    v28 = this[3].Ptr;
    v29 = (_DWORD *)v28[1];
    v57 = 0;
    v30 = v28;
    v31 = v29;
    if ( !*((_BYTE *)v29 + 25) )
    {
      do
      {
        if ( v31[8] >= v23 )
        {
          v32 = 0;
          v30 = v31;
        }
        else
        {
          v32 = 1;
        }
        v33 = (_DWORD **)(v31 + 4);
        if ( !v32 )
          v33 = (_DWORD **)v31;
        v31 = *v33;
      }
      while ( !*((_BYTE *)*v33 + 25) );
    }
    if ( v30[25] || v23 < *((_DWORD *)v30 + 8) || v30 == (_BYTE *)v28 )
      goto LABEL_80;
    v57 = 0;
    while ( !*((_BYTE *)v29 + 25) )
    {
      if ( v29[8] >= v23 )
      {
        v34 = 0;
        v28 = v29;
      }
      else
      {
        v34 = 1;
      }
      v35 = v29 + 4;
      if ( !v34 )
        v35 = v29;
      v29 = (_DWORD *)*v35;
    }
    if ( *((_BYTE *)v28 + 25) || v23 < *((_DWORD *)v28 + 8) )
    {
      std::_Xout_of_range("invalid map<K, T> key");
      __debugbreak();
    }
    std::wstring::operator=(S1, v28 + 5);
    std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(
      v60,
      v56,
      S1);
    v36 = (void *)v58;
    if ( *(_BYTE *)(v58 + 25) )
      goto LABEL_76;
    v37 = (const wchar_t *)(v58 + 32);
    v38 = *(_QWORD *)(v58 + 48);
    if ( *(_QWORD *)(v58 + 56) > 7u )
      v37 = *(const wchar_t **)v37;
    v39 = N;
    v40 = (const wchar_t *)S1;
    if ( v66 > 7 )
      v40 = S1[0];
    v41 = *(_QWORD *)(v58 + 48);
    if ( v38 >= N )
      v41 = N;
    v42 = wmemcmp(v40, v37, v41);
    if ( v42 )
    {
      if ( v42 < 0 )
        goto LABEL_76;
    }
    else if ( v39 < v38 )
    {
LABEL_76:
      v43 = v60[0];
      v36 = v60[0];
      goto LABEL_77;
    }
    v43 = v60[0];
LABEL_77:
    if ( v36 == v43 )
    {
      std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::wstring,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::wstring>>,0>>::erase(
        &this[3],
        &Time);
    }
    else
    {
      Time = (__time64_t)v61;
      v49 = std::wstring::wstring((__int64)v61, (__int64)S1);
      v50 = std::vector<enum AttestationResultType>::vector<enum AttestationResultType>(v56, a2);
      if ( (unsigned __int8)Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal(
                              this,
                              v50,
                              v49,
                              &v55) )
      {
        std::wstring::operator=(v54, S1);
        std::map<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>::operator=(
          v59,
          &v55);
LABEL_96:
        std::wstring::~wstring((char **)S1);
        std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>(v60);
        std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>((void **)&v55);
        if ( this != (RTL_SRWLOCK *)-40LL )
          ReleaseSRWLockShared(this + 5);
        AttestationResultsInternal = 1;
        goto LABEL_99;
      }
    }
    v5 = v54;
LABEL_80:
    v44 = *(__int64 **)v60[0];
    while ( !*((_BYTE *)v44 + 25) )
    {
      std::wstring::wstring((__int64)v67, (__int64)(v44 + 4));
      v67[4] = (char *)v44[8];
      std::vector<unsigned char>::vector<unsigned char>(v68, (__int64)(v44 + 9));
      v69 = *((_DWORD *)v44 + 24);
      std::wstring::operator=(S1, v67);
      v60[2] = v61;
      v45 = std::wstring::wstring((__int64)v61, (__int64)S1);
      v46 = std::vector<enum AttestationResultType>::vector<enum AttestationResultType>(v56, a2);
      if ( (unsigned __int8)Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal(
                              this,
                              v46,
                              v45,
                              &v55) )
      {
        std::wstring::operator=(v5, S1);
        std::map<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>::operator=(
          v59,
          &v55);
        std::vector<unsigned char>::~vector<unsigned char>(v68);
        std::wstring::~wstring(v67);
        goto LABEL_96;
      }
      std::vector<unsigned char>::~vector<unsigned char>(v68);
      std::wstring::~wstring(v67);
      v47 = (__int64 **)v44[2];
      if ( *((_BYTE *)v47 + 25) )
      {
        for ( i = (__int64 *)v44[1]; !*((_BYTE *)i + 25) && v44 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v44 = i;
        v44 = i;
      }
      else
      {
        v44 = (__int64 *)v44[2];
        for ( j = *v47; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v44 = j;
      }
    }
    std::wstring::~wstring((char **)S1);
    std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>(v60);
    std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>((void **)&v55);
  }
LABEL_101:
  if ( this != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockShared(this + 5);
  std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>(a2);
  return 0;
}

```

## disassembly

```asm
0x18000f814  mov     rax, rsp
0x18000f817  mov     [rax+10h], rdx
0x18000f81b  push    rbp
0x18000f81c  push    rbx
0x18000f81d  push    rsi
0x18000f81e  push    rdi
0x18000f81f  push    r12
0x18000f821  push    r13
0x18000f823  push    r14
0x18000f825  push    r15
0x18000f827  lea     rbp, [rsp-48h]
0x18000f82c  sub     rsp, 148h
0x18000f833  movaps  xmmword ptr [rax-58h], xmm6
0x18000f837  mov     rax, cs:__security_cookie
0x18000f83e  xor     rax, rsp
0x18000f841  mov     [rbp+80h+var_60], rax
0x18000f845  mov     rsi, r9
0x18000f848  mov     [rsp+180h+var_128], r9
0x18000f84d  mov     r12, r8
0x18000f850  mov     [rsp+180h+var_158], r8
0x18000f855  mov     r14, rdx
0x18000f858  mov     r15, rcx
0x18000f85b  mov     [rbp+80h+var_E8], rdx
0x18000f85f  xor     r13d, r13d
0x18000f862  mov     [rsp+180h+Time], r13
0x18000f867  lea     rcx, [rsp+180h+Time]; Time
0x18000f86c  call    cs:__imp__time64
0x18000f872  lea     rbx, [r15+28h]
0x18000f876  mov     rcx, rbx; SRWLock
0x18000f879  call    cs:__imp_AcquireSRWLockShared
0x18000f87f  mov     rdx, [r15]
0x18000f882  mov     rcx, [rsp+180h+Time]
0x18000f887  call    cs:__imp__o__difftime64
0x18000f88d  movaps  xmm6, xmm0
0x18000f890  test    rbx, rbx
0x18000f893  jz      short loc_18000F89E
0x18000f895  mov     rcx, rbx; SRWLock
0x18000f898  call    cs:__imp_ReleaseSRWLockShared
0x18000f89e  andps   xmm6, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x18000f8a5  comisd  xmm6, cs:__real@40ac200000000000
0x18000f8ad  jb      short loc_18000F8B7
0x18000f8af  mov     rcx, r15; this
0x18000f8b2  call    ?RemoveAllInvalidCertificates@CertificateCache@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::CertificateCache::RemoveAllInvalidCertificates(void)
0x18000f8b7  mov     rcx, rbx; SRWLock
0x18000f8ba  call    cs:__imp_AcquireSRWLockShared
0x18000f8c0  mov     [rbp+80h+var_E0], rbx
0x18000f8c4  cmp     [r15+10h], r13
0x18000f8c8  jz      loc_18000FDE3
0x18000f8ce  mov     rcx, [r14]
0x18000f8d1  cmp     rcx, [r14+8]
0x18000f8d5  jz      loc_18000F980
0x18000f8db  mov     r9, [r15+8]
0x18000f8df  xor     eax, eax
0x18000f8e1  mov     [rsp+180h+var_134], eax
0x18000f8e5  mov     rdx, r9
0x18000f8e8  mov     r8, [r9+8]
0x18000f8ec  cmp     [r8+19h], r13b
0x18000f8f0  jnz     short loc_18000F90E
0x18000f8f2  mov     r10d, [rcx]
0x18000f8f5  cmp     [r8+20h], r10d
0x18000f8f9  cmovge  rdx, r8
0x18000f8fd  lea     rax, [r8+10h]
0x18000f901  cmovge  rax, r8
0x18000f905  mov     r8, [rax]
0x18000f908  cmp     [r8+19h], r13b
0x18000f90c  jz      short loc_18000F8F5
0x18000f90e  cmp     [rdx+19h], r13b
0x18000f912  jnz     loc_18000FDE3
0x18000f918  mov     eax, [rdx+20h]
0x18000f91b  cmp     [rcx], eax
0x18000f91d  jl      loc_18000FDE3
0x18000f923  cmp     rdx, r9
0x18000f926  jz      loc_18000FDE3
0x18000f92c  xor     eax, eax
0x18000f92e  mov     [rsp+180h+var_134], eax
0x18000f932  mov     rdx, r9
0x18000f935  mov     r8, [r9+8]
0x18000f939  cmp     [r8+19h], r13b
0x18000f93d  jnz     short loc_18000F95B
0x18000f93f  mov     r10d, [rcx]
0x18000f942  cmp     [r8+20h], r10d
0x18000f946  cmovge  rdx, r8
0x18000f94a  lea     rax, [r8+10h]
0x18000f94e  cmovge  rax, r8
0x18000f952  mov     r8, [rax]
0x18000f955  cmp     [r8+19h], r13b
0x18000f959  jz      short loc_18000F942
0x18000f95b  cmp     [rdx+19h], r13b
0x18000f95f  jnz     short loc_18000F9DA
0x18000f961  mov     eax, [rdx+20h]
0x18000f964  cmp     [rcx], eax
0x18000f966  jl      short loc_18000F9DA
0x18000f968  cmp     [rdx+30h], r13
0x18000f96c  jz      loc_18000FDE3
0x18000f972  add     rcx, 4
0x18000f976  cmp     rcx, [r14+8]
0x18000f97a  jnz     loc_18000F8DF
0x18000f980  cmp     [r12+10h], r13
0x18000f985  jz      short loc_18000F9E8
0x18000f987  lea     rax, [rsp+180h+var_108]
0x18000f98c  mov     [rsp+180h+var_128], rax
0x18000f991  mov     rdx, r12
0x18000f994  lea     rcx, [rsp+180h+var_108]
0x18000f999  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f99e  mov     rdi, rax
0x18000f9a1  mov     rdx, r14
0x18000f9a4  lea     rcx, [rsp+180h+var_140]
0x18000f9a9  call    ??0?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<AttestationResultType>::vector<AttestationResultType>(std::vector<AttestationResultType> const &)
0x18000f9ae  nop
0x18000f9af  mov     r9, rsi
0x18000f9b2  mov     r8, rdi
0x18000f9b5  mov     rdx, rax
0x18000f9b8  mov     rcx, r15
0x18000f9bb  call    ?TryGetAttestationResultsInternal@CertificateCache@Client@HostGuardian@Microsoft@@AEAA_NV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@AEAV?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@6@@Z; Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal(std::vector<AttestationResultType>,std::wstring,std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>> &)
0x18000f9c0  mov     dil, al
0x18000f9c3  test    rbx, rbx
0x18000f9c6  jz      loc_18000FD90
0x18000f9cc  mov     rcx, rbx; SRWLock
0x18000f9cf  call    cs:__imp_ReleaseSRWLockShared
0x18000f9d5  jmp     loc_18000FD90
0x18000f9da  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18000f9e1  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000f9e7  int     3; Trap to Debugger
0x18000f9e8  xorps   xmm0, xmm0
0x18000f9eb  movdqu  [rsp+180h+var_150], xmm0
0x18000f9f1  mov     ecx, 50h ; 'P'; Size
0x18000f9f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f9fb  mov     [rax], rax
0x18000f9fe  mov     [rax+8], rax
0x18000fa02  mov     [rax+10h], rax
0x18000fa06  mov     word ptr [rax+18h], 101h
0x18000fa0c  mov     qword ptr [rsp+180h+var_150], rax
0x18000fa11  mov     rax, [r14]
0x18000fa14  mov     edi, [rax]
0x18000fa16  mov     dword ptr [rsp+180h+Time], edi
0x18000fa1a  mov     rdx, [r15+8]
0x18000fa1e  mov     rcx, [rdx+8]
0x18000fa22  xor     eax, eax
0x18000fa24  mov     [rsp+180h+var_134], eax
0x18000fa28  xor     esi, esi
0x18000fa2a  jmp     short loc_18000FA4A
0x18000fa2c  cmp     [rcx+20h], edi
0x18000fa2f  jge     short loc_18000FA36
0x18000fa31  mov     r8b, 1
0x18000fa34  jmp     short loc_18000FA3C
0x18000fa36  mov     r8b, sil
0x18000fa39  mov     rdx, rcx
0x18000fa3c  lea     rax, [rcx+10h]
0x18000fa40  test    r8b, r8b
0x18000fa43  cmovz   rax, rcx
0x18000fa47  mov     rcx, [rax]
0x18000fa4a  cmp     [rcx+19h], sil
0x18000fa4e  jz      short loc_18000FA2C
0x18000fa50  cmp     [rdx+19h], sil
0x18000fa54  jnz     loc_18000FDFE
0x18000fa5a  cmp     edi, [rdx+20h]
0x18000fa5d  jl      loc_18000FDFE
0x18000fa63  add     rdx, 28h ; '('
0x18000fa67  lea     rcx, [rsp+180h+var_120]
0x18000fa6c  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>(std::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>> const &)
0x18000fa71  nop
0x18000fa72  xorps   xmm0, xmm0
0x18000fa75  movups  xmmword ptr [rbp+80h+S1], xmm0
0x18000fa79  mov     [rbp+80h+N], rsi
0x18000fa7d  mov     [rbp+80h+var_C0], 7
0x18000fa85  mov     word ptr [rbp+80h+S1], si
0x18000fa89  cmp     [r15+20h], rsi
0x18000fa8d  jz      loc_18000FBCC
0x18000fa93  mov     rdx, [r15+18h]
0x18000fa97  mov     rcx, [rdx+8]
0x18000fa9b  xor     eax, eax
0x18000fa9d  mov     [rsp+180h+var_134], eax
0x18000faa1  mov     r9, rdx
0x18000faa4  mov     r8, rcx
0x18000faa7  cmp     [rcx+19h], sil
0x18000faab  jnz     short loc_18000FAD2
0x18000faad  cmp     [r8+20h], edi
0x18000fab1  jge     short loc_18000FAB8
0x18000fab3  mov     r10b, 1
0x18000fab6  jmp     short loc_18000FABE
0x18000fab8  mov     r10b, sil
0x18000fabb  mov     r9, r8
0x18000fabe  lea     rax, [r8+10h]
0x18000fac2  test    r10b, r10b
0x18000fac5  cmovz   rax, r8
0x18000fac9  mov     r8, [rax]
0x18000facc  cmp     [r8+19h], sil
0x18000fad0  jz      short loc_18000FAAD
0x18000fad2  cmp     [r9+19h], sil
0x18000fad6  jnz     loc_18000FBCC
0x18000fadc  cmp     edi, [r9+20h]
0x18000fae0  jl      loc_18000FBCC
0x18000fae6  cmp     r9, rdx
0x18000fae9  jz      loc_18000FBCC
0x18000faef  xor     eax, eax
0x18000faf1  mov     [rsp+180h+var_134], eax
0x18000faf5  jmp     short loc_18000FB15
0x18000faf7  cmp     [rcx+20h], edi
0x18000fafa  jge     short loc_18000FB01
0x18000fafc  mov     r8b, 1
0x18000faff  jmp     short loc_18000FB07
0x18000fb01  mov     r8b, sil
0x18000fb04  mov     rdx, rcx
0x18000fb07  lea     rax, [rcx+10h]
0x18000fb0b  test    r8b, r8b
0x18000fb0e  cmovz   rax, rcx
0x18000fb12  mov     rcx, [rax]
0x18000fb15  cmp     [rcx+19h], sil
0x18000fb19  jz      short loc_18000FAF7
0x18000fb1b  cmp     [rdx+19h], sil
0x18000fb1f  jnz     loc_18000FCE3
0x18000fb25  cmp     edi, [rdx+20h]
0x18000fb28  jl      loc_18000FCE3
0x18000fb2e  add     rdx, 28h ; '('
0x18000fb32  lea     rcx, [rbp+80h+S1]
0x18000fb36  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fb3b  lea     r8, [rbp+80h+S1]
0x18000fb3f  lea     rdx, [rsp+180h+var_140]
0x18000fb44  lea     rcx, [rsp+180h+var_120]
0x18000fb49  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000fb4e  mov     rdi, [rsp+180h+var_130]
0x18000fb53  cmp     [rdi+19h], sil
0x18000fb57  jnz     short loc_18000FBA8
0x18000fb59  lea     rdx, [rdi+20h]
0x18000fb5d  mov     rsi, [rdx+10h]
0x18000fb61  cmp     qword ptr [rdx+18h], 7
0x18000fb66  jbe     short loc_18000FB6B
0x18000fb68  mov     rdx, [rdx]; S2
0x18000fb6b  mov     r12, [rbp+80h+N]
0x18000fb6f  lea     rcx, [rbp+80h+S1]
0x18000fb73  cmp     [rbp+80h+var_C0], 7
0x18000fb78  cmova   rcx, [rbp+80h+S1]; S1
0x18000fb7d  mov     r8, rsi
0x18000fb80  cmp     rsi, r12
0x18000fb83  cmovnb  r8, r12; N
0x18000fb87  call    wmemcmp
0x18000fb8c  test    eax, eax
0x18000fb8e  jz      short loc_18000FB98
0x18000fb90  xor     esi, esi
0x18000fb92  test    eax, eax
0x18000fb94  jns     short loc_18000FB9F
0x18000fb96  jmp     short loc_18000FBA8
0x18000fb98  cmp     r12, rsi
0x18000fb9b  jb      short loc_18000FBA6
0x18000fb9d  xor     esi, esi
0x18000fb9f  mov     rax, [rsp+180h+var_120]
0x18000fba4  jmp     short loc_18000FBB0
0x18000fba6  xor     esi, esi
0x18000fba8  mov     rax, [rsp+180h+var_120]
0x18000fbad  mov     rdi, rax
0x18000fbb0  cmp     rdi, rax
0x18000fbb3  jnz     loc_18000FC80
0x18000fbb9  lea     rdx, [rsp+180h+Time]
0x18000fbbe  lea     rcx, [r15+18h]
0x18000fbc2  call    ?erase@?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBW4AttestationResultType@@@Z; std::_Tree<std::_Tmap_traits<AttestationResultType,std::wstring,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::wstring>>,0>>::erase(AttestationResultType const &)
0x18000fbc7  mov     r12, [rsp+180h+var_158]
0x18000fbcc  mov     rdi, [rsp+180h+var_120]
0x18000fbd1  mov     rdi, [rdi]
0x18000fbd4  cmp     [rdi+19h], sil
0x18000fbd8  jnz     loc_18000FDC3
0x18000fbde  lea     rdx, [rdi+20h]
0x18000fbe2  lea     rcx, [rbp+80h+var_B0]
0x18000fbe6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000fbeb  nop
0x18000fbec  mov     rax, [rdi+40h]
0x18000fbf0  mov     [rbp+80h+var_90], rax
0x18000fbf4  lea     rdx, [rdi+48h]
0x18000fbf8  lea     rcx, [rbp+80h+var_88]
0x18000fbfc  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18000fc01  mov     eax, [rdi+60h]
0x18000fc04  mov     [rbp+80h+var_70], eax
0x18000fc07  lea     rdx, [rbp+80h+var_B0]
0x18000fc0b  lea     rcx, [rbp+80h+S1]
0x18000fc0f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fc14  lea     rax, [rsp+180h+var_108]
0x18000fc19  mov     [rsp+180h+var_110], rax
0x18000fc1e  lea     rdx, [rbp+80h+S1]
0x18000fc22  lea     rcx, [rsp+180h+var_108]
0x18000fc27  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000fc2c  mov     rsi, rax
0x18000fc2f  mov     rdx, r14
0x18000fc32  lea     rcx, [rsp+180h+var_140]
0x18000fc37  call    ??0?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<AttestationResultType>::vector<AttestationResultType>(std::vector<AttestationResultType> const &)
0x18000fc3c  nop
0x18000fc3d  lea     r9, [rsp+180h+var_150]
0x18000fc42  mov     r8, rsi
0x18000fc45  mov     rdx, rax
0x18000fc48  mov     rcx, r15
0x18000fc4b  call    ?TryGetAttestationResultsInternal@CertificateCache@Client@HostGuardian@Microsoft@@AEAA_NV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@AEAV?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@6@@Z; Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal(std::vector<AttestationResultType>,std::wstring,std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>> &)
0x18000fc50  xor     esi, esi
0x18000fc52  test    al, al
0x18000fc54  jnz     loc_18000FD30
0x18000fc5a  lea     rcx, [rbp+80h+var_88]
0x18000fc5e  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000fc63  lea     rcx, [rbp+80h+var_B0]
0x18000fc67  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fc6c  mov     rcx, [rdi+10h]
0x18000fc70  cmp     [rcx+19h], sil
0x18000fc74  jz      loc_18000FD0C
0x18000fc7a  mov     rax, [rdi+8]
  ... truncated ...
```
