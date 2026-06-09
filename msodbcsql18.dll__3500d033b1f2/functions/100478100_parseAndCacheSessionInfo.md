# parseAndCacheSessionInfo

- ea: `0x100478100`
- end: `0x100478944`
- name: `parseAndCacheSessionInfo`
- size: `2116`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100473cc0`
- `0x100474030`
- `0x100474510`

## callees

- `0x10040126c`
- `0x10040128c`
- `0x100407940`
- `0x100431464`
- `0x100472728`
- `0x10047278c`
- `0x100473210`
- `0x1004734f0`
- `0x1004754dc`
- `0x10047648c`
- `0x100476654`
- `0x10047699c`
- `0x100477f34`
- `0x100478100`
- `0x100478f30`
- `0x100546cf5`
- `0x100546d0d`
- `0x100546d19`
- `0x100546d25`
- `0x100546d31`
- `0x100546d3d`
- `0x10054811c`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100478575`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004786cb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004788f1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004788f8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100478575`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004786cb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004788f1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004788f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall parseAndCacheSessionInfo(
        void (__fastcall **a1)(_QWORD, _QWORD, _QWORD),
        UCHAR *a2,
        unsigned int a3,
        void *a4,
        UCHAR *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v9; // r14
  __int64 v10; // r15
  _QWORD *result; // rax
  _QWORD *v12; // rsi
  __int64 v13; // r12
  ULONG cbSignature; // r13d
  int v15; // edi
  NTSTATUS v16; // eax
  UCHAR *v17; // rax
  int v18; // edi
  NTSTATUS v19; // eax
  int v20; // edi
  int v21; // edi
  _WORD *v22; // rdi
  _QWORD *v23; // r13
  _WORD *v24; // rax
  __int64 i; // r8
  _WORD *v26; // rax
  __int64 j; // r8
  void **v28; // rdx
  void *v29; // rdx
  _WORD *v30; // rax
  __int64 k; // r8
  _QWORD *v32; // rdx
  void *v33; // rcx
  __int64 CacheLock; // rax
  _QWORD *v35; // rdi
  _QWORD *v36; // rax
  void *v37; // rax
  void *v38; // rcx
  _QWORD *v39; // rdi
  _QWORD *v40; // rax
  void *v41; // rax
  void *v42; // rcx
  __int64 v43; // rax
  void *v44; // rcx
  unsigned int v45; // [rsp+40h] [rbp-1F8h]
  PUCHAR v46; // [rsp+48h] [rbp-1F0h] BYREF
  unsigned int v47; // [rsp+50h] [rbp-1E8h]
  ulong pExceptionObject; // [rsp+58h] [rbp-1E0h] BYREF
  NTSTATUS v49; // [rsp+5Ch] [rbp-1DCh] BYREF
  NTSTATUS v50; // [rsp+60h] [rbp-1D8h] BYREF
  void *v51; // [rsp+68h] [rbp-1D0h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-1C8h] BYREF
  BCRYPT_KEY_HANDLE hPubKey; // [rsp+78h] [rbp-1C0h] BYREF
  BCRYPT_SECRET_HANDLE phAgreedSecret; // [rsp+80h] [rbp-1B8h] BYREF
  __int64 v55; // [rsp+88h] [rbp-1B0h]
  ULONG pcbResult; // [rsp+90h] [rbp-1A8h] BYREF
  ulong v57; // [rsp+94h] [rbp-1A4h] BYREF
  const WCHAR *pPaddingInfo; // [rsp+98h] [rbp-1A0h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+A0h] [rbp-198h]
  PUCHAR pbInput; // [rsp+A8h] [rbp-190h]
  __int64 v61; // [rsp+B0h] [rbp-188h]
  __int64 v62; // [rsp+B8h] [rbp-180h]
  void (__fastcall **v63)(_QWORD, _QWORD, _QWORD); // [rsp+C0h] [rbp-178h]
  __int64 v64; // [rsp+C8h] [rbp-170h]
  __int64 v65; // [rsp+D0h] [rbp-168h]
  __int64 v66; // [rsp+D8h] [rbp-160h]
  _QWORD v67[2]; // [rsp+E0h] [rbp-158h] BYREF
  BCryptBufferDesc pParameterList; // [rsp+F0h] [rbp-148h] BYREF
  __int64 v69; // [rsp+100h] [rbp-138h]
  int v70; // [rsp+108h] [rbp-130h] BYREF
  int v71; // [rsp+118h] [rbp-120h] BYREF
  void *v72[2]; // [rsp+128h] [rbp-110h] BYREF
  __m128i v73; // [rsp+138h] [rbp-100h]
  _QWORD v74[2]; // [rsp+148h] [rbp-F0h] BYREF
  __m128i v75; // [rsp+158h] [rbp-E0h]
  _QWORD v76[2]; // [rsp+168h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+178h] [rbp-C0h]
  _QWORD v78[2]; // [rsp+188h] [rbp-B0h] BYREF
  __int128 v79; // [rsp+198h] [rbp-A0h]
  _QWORD *v80; // [rsp+1A8h] [rbp-90h]
  _QWORD *v81; // [rsp+1B0h] [rbp-88h] BYREF
  unsigned __int64 v82; // [rsp+1B8h] [rbp-80h] BYREF
  __int128 v83; // [rsp+1C8h] [rbp-70h]
  UCHAR pbHash[32]; // [rsp+1D8h] [rbp-60h] BYREF

  v69 = -2;
  hKey = a4;
  v63 = a1;
  pbInput = a5;
  v9 = a6;
  v64 = a6;
  v61 = a7;
  v65 = a7;
  v10 = a8;
  v66 = a8;
  v62 = a9;
  v55 = a9;
  v46 = a2;
  v47 = a3;
  phKey = 0;
  hPubKey = 0;
  phAgreedSecret = 0;
  result = operator new[](0x30u);
  v12 = result;
  v51 = result;
  if ( result )
  {
    try
    {
      *result = (unsigned int)read4(&v46);
      *v12 |= (unsigned __int64)(unsigned int)read4(&v46) << 32;
      *((_DWORD *)v12 + 2) = 32;
      v13 = (unsigned int)read4(&v46);
      cbSignature = read4(&v46);
      if ( (unsigned int)v13 + cbSignature > v47 )
      {
        pExceptionObject = -2146893023;
        throw &pExceptionObject;
      }
      v15 = 306;
      if ( a8 )
      {
        _mm_lfence();
        hasha256(v46, v13, pbHash);
        pPaddingInfo = L"SHA256";
        v16 = BCryptVerifySignature_0(hKey, &pPaddingInfo, pbHash, 0x20u, &v46[v13], cbSignature, 2u);
        if ( v16 )
        {
          v49 = v16;
          throw (ulong *)&v49;
        }
        v15 = 307;
      }
      v67[0] = 14;
      v67[1] = L"SHA256";
      pParameterList.ulVersion = 0;
      pParameterList.cBuffers = 1;
      pParameterList.pBuffers = (PBCryptBuffer)v67;
      v17 = pbInput;
      *(_DWORD *)pbInput = 877347653;
      v18 = v15 + 1;
      v19 = BCryptImportKeyPair_0(hAlgorithm, 0, L"ECCPRIVATEBLOB", &phKey, v17, 0x98u, 0);
      if ( v19
        || (_mm_lfence(),
            v20 = v18 + 1,
            (v19 = BCryptImportKeyPair_0(hAlgorithm, 0, L"ECCPUBLICBLOB", &hPubKey, v46, v13, 0)) != 0)
        || (v21 = v20 + 1, (v19 = BCryptSecretAgreement_0(phKey, hPubKey, &phAgreedSecret, 0)) != 0)
        || (v45 = v21 + 1,
            (v19 = BCryptDeriveKey_0(phAgreedSecret, L"HASH", &pParameterList, (PUCHAR)v12 + 12, 0x20u, &pcbResult, 0)) != 0) )
      {
        v50 = v19;
        throw (ulong *)&v50;
      }
    }
    catch ( ulong v57 )
    {
      (*v63)(v63, v45, v57);
      operator delete[](v51);
      v51 = 0;
      v12 = 0;
      v9 = v64;
      v22 = (_WORD *)v65;
      v10 = v66;
      v23 = (_QWORD *)v55;
      goto LABEL_13;
    }
    v22 = (_WORD *)v61;
    v23 = (_QWORD *)v62;
LABEL_13:
    BCryptDestroyKey_0(phKey);
    BCryptDestroyKey_0(hPubKey);
    BCryptDestroySecret_0(phAgreedSecret);
    if ( !v12 )
      return v12;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v76[0]) = 0;
    v24 = (_WORD *)v9;
    for ( i = 0; *v24; ++v24 )
      ++i;
    std::basic_string<char16_t>::assign(v76, v9, i);
    v73 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v72[0]) = 0;
    v26 = v22;
    for ( j = 0; *v26; ++v26 )
      ++j;
    std::basic_string<char16_t>::assign(v72, v22, j);
    v28 = v72;
    if ( v73.m128i_i64[1] >= 8uLL )
      v28 = (void **)v72[0];
    std::basic_string<char16_t>::append(v76, v28, v73.m128i_i64[0]);
    if ( v73.m128i_i64[1] >= 8uLL )
    {
      v29 = v72[0];
      if ( (unsigned __int64)(v73.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
        || (unsigned __int64)(2 * (v73.m128i_i64[1] + 1)) >= 0x1000
        && (((__int64)v72[0] & 0x1F) != 0
         || (v29 = (void *)*((_QWORD *)v72[0] - 1), v29 >= v72[0])
         || (unsigned __int64)((char *)v72[0] - (char *)v29 - 8) > 0x1F) )
      {
        _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v29);
    }
    if ( v10 )
    {
      v75 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v74[0]) = 0;
      v30 = (_WORD *)v10;
      for ( k = 0; *v30; ++v30 )
        ++k;
      std::basic_string<char16_t>::assign(v74, v10, k);
      v32 = v74;
      if ( v75.m128i_i64[1] >= 8uLL )
        v32 = (_QWORD *)v74[0];
      std::basic_string<char16_t>::append(v76, v32, v75.m128i_i64[0]);
      if ( v75.m128i_i64[1] >= 8uLL )
      {
        v33 = (void *)v74[0];
        if ( (unsigned __int64)(v75.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
          || (unsigned __int64)(2 * (v75.m128i_i64[1] + 1)) >= 0x1000
          && ((v74[0] & 0x1F) != 0
           || (v33 = *(void **)(v74[0] - 8LL), (unsigned __int64)v33 >= v74[0])
           || (unsigned __int64)(v74[0] - (_QWORD)v33 - 8LL) > 0x1F) )
        {
          _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v33);
      }
    }
    CacheLock = GetCacheLock();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)CacheLock + 8LL))(CacheLock);
    v79 = 0;
    std::basic_string<char16_t>::_Construct_lv_contents(v78, v76);
    v80 = v12;
    v35 = *(_QWORD **)&`Instance<std::map<std::basic_string<char16_t>,EnclaveSession *>>::operator()'::`2'::s_var;
    if ( !*(_QWORD *)&`Instance<std::map<std::basic_string<char16_t>,EnclaveSession *>>::operator()'::`2'::s_var )
    {
      v36 = operator new(0x10u);
      v35 = v36;
      v55 = (__int64)v36;
      if ( v36 )
      {
        *v36 = 0;
        v36[1] = 0;
        *v36 = std::_Tree_comp_alloc<std::_Tmap_traits<EnclaveSession *,std::basic_string<char16_t>,std::less<EnclaveSession *>,std::allocator<std::pair<EnclaveSession * const,std::basic_string<char16_t>>>,0>>::_Buyheadnode(v36);
      }
      else
      {
        v35 = 0;
      }
      *(_QWORD *)&`Instance<std::map<std::basic_string<char16_t>,EnclaveSession *>>::operator()'::`2'::s_var = v35;
    }
    v37 = (void *)std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<char16_t>,EnclaveSession *,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,EnclaveSession *>>,0>>::_Buynode<std::pair<std::basic_string<char16_t>,EnclaveSession *>>(
                    v35,
                    v78);
    std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,EnclaveSession *,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,EnclaveSession *>>,0>>::_Insert_nohint<std::pair<std::basic_string<char16_t> const,EnclaveSession *> &,std::_Tree_node<std::pair<std::basic_string<char16_t> const,EnclaveSession *>,void *> *>(
      (int)v35,
      (int)&v70,
      0,
      (_DWORD)v37 + 32,
      v37);
    if ( *((_QWORD *)&v79 + 1) >= 8u )
    {
      v38 = (void *)v78[0];
      if ( (unsigned __int64)(*((_QWORD *)&v79 + 1) + 1LL) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_73;
      if ( (unsigned __int64)(2 * (*((_QWORD *)&v79 + 1) + 1LL)) >= 0x1000 )
      {
        if ( (v78[0] & 0x1F) != 0 )
          goto LABEL_73;
        v38 = *(void **)(v78[0] - 8LL);
        if ( (unsigned __int64)v38 >= v78[0] || (unsigned __int64)(v78[0] - (_QWORD)v38 - 8LL) > 0x1F )
          goto LABEL_73;
      }
      operator delete(v38);
    }
    v81 = v12;
    v83 = 0;
    std::basic_string<char16_t>::_Construct_lv_contents(&v82, v76);
    v39 = *(_QWORD **)&`Instance<std::map<EnclaveSession *,std::basic_string<char16_t>>>::operator()'::`2'::s_var;
    if ( !*(_QWORD *)&`Instance<std::map<EnclaveSession *,std::basic_string<char16_t>>>::operator()'::`2'::s_var )
    {
      v40 = operator new(0x10u);
      v39 = v40;
      v55 = (__int64)v40;
      if ( v40 )
      {
        *v40 = 0;
        v40[1] = 0;
        *v40 = std::_Tree_comp_alloc<std::_Tmap_traits<EnclaveSession *,std::basic_string<char16_t>,std::less<EnclaveSession *>,std::allocator<std::pair<EnclaveSession * const,std::basic_string<char16_t>>>,0>>::_Buyheadnode(v40);
      }
      else
      {
        v39 = 0;
      }
      *(_QWORD *)&`Instance<std::map<EnclaveSession *,std::basic_string<char16_t>>>::operator()'::`2'::s_var = v39;
    }
    v41 = (void *)std::_Tree_comp_alloc<std::_Tmap_traits<EnclaveSession *,std::basic_string<char16_t>,std::less<EnclaveSession *>,std::allocator<std::pair<EnclaveSession * const,std::basic_string<char16_t>>>,0>>::_Buynode<std::pair<EnclaveSession *,std::basic_string<char16_t>>>(
                    v39,
                    &v81);
    std::_Tree<std::_Tmap_traits<EnclaveSession *,std::basic_string<char16_t>,std::less<EnclaveSession *>,std::allocator<std::pair<EnclaveSession * const,std::basic_string<char16_t>>>,0>>::_Insert_nohint<std::pair<EnclaveSession * const,std::basic_string<char16_t>> &,std::_Tree_node<std::pair<EnclaveSession * const,std::basic_string<char16_t>>,void *> *>(
      (int)v39,
      (int)&v71,
      0,
      (_DWORD)v41 + 32,
      v41);
    if ( *((_QWORD *)&v83 + 1) < 8u )
      goto LABEL_65;
    v42 = (void *)v82;
    if ( (unsigned __int64)(*((_QWORD *)&v83 + 1) + 1LL) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( (unsigned __int64)(2 * (*((_QWORD *)&v83 + 1) + 1LL)) < 0x1000
        || (v82 & 0x1F) == 0
        && (v42 = *(void **)(v82 - 8), (unsigned __int64)v42 < v82)
        && v82 - (unsigned __int64)v42 - 8 <= 0x1F )
      {
        operator delete(v42);
LABEL_65:
        *v23 = ++qword_1005D9410;
        v43 = GetCacheLock();
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 24LL))(v43);
        if ( si128.m128i_i64[1] >= 8uLL )
        {
          v44 = (void *)v76[0];
          if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
            || (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000
            && ((v76[0] & 0x1F) != 0
             || (v44 = *(void **)(v76[0] - 8LL), (unsigned __int64)v44 >= v76[0])
             || (unsigned __int64)(v76[0] - (_QWORD)v44 - 8LL) > 0x1F) )
          {
            _invalid_parameter_noinfo_noreturn();
          }
          operator delete(v44);
        }
        return v12;
      }
    }
LABEL_73:
    _invalid_parameter_noinfo_noreturn();
  }
  return result;
}

```

## disassembly

```asm
0x100478100  push    rbx
0x100478102  push    rsi
0x100478103  push    rdi
0x100478104  push    r12
0x100478106  push    r13
0x100478108  push    r14
0x10047810a  push    r15
0x10047810c  sub     rsp, 200h
0x100478113  mov     [rsp+238h+var_138], 0FFFFFFFFFFFFFFFEh
0x10047811f  mov     rax, cs:__security_cookie
0x100478126  xor     rax, rsp
0x100478129  mov     [rsp+238h+var_40], rax
0x100478131  mov     [rsp+238h+hKey], r9
0x100478139  mov     [rsp+238h+var_178], rcx
0x100478141  mov     rax, [rsp+238h+arg_20]
0x100478149  mov     [rsp+238h+pbInput], rax
0x100478151  mov     r14, [rsp+238h+arg_28]
0x100478159  mov     [rsp+238h+var_170], r14
0x100478161  mov     rax, [rsp+238h+arg_30]
0x100478169  mov     [rsp+238h+var_188], rax
0x100478171  mov     [rsp+238h+var_168], rax
0x100478179  mov     r15, [rsp+238h+arg_38]
0x100478181  mov     [rsp+238h+var_160], r15
0x100478189  mov     rax, [rsp+238h+arg_40]
0x100478191  mov     [rsp+238h+var_180], rax
0x100478199  mov     [rsp+238h+var_1B0], rax
0x1004781a1  mov     [rsp+238h+var_1F0], rdx
0x1004781a6  mov     [rsp+238h+var_1E8], r8d
0x1004781ab  xor     ebx, ebx
0x1004781ad  mov     [rsp+238h+phKey], rbx
0x1004781b2  mov     [rsp+238h+hPubKey], rbx
0x1004781b7  mov     [rsp+238h+phAgreedSecret], rbx
0x1004781bf  lea     ecx, [rbx+30h]; unsigned __int64
0x1004781c2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1004781c7  mov     rsi, rax
0x1004781ca  mov     [rsp+238h+var_1D0], rax
0x1004781cf  test    rax, rax
0x1004781d2  jz      loc_1004788CE
0x1004781d8  mov     [rsp+238h+var_1F8], 12Dh
0x1004781e0  lea     rcx, [rsp+238h+var_1F0]
0x1004781e5  call    read4
0x1004781ea  mov     eax, eax
0x1004781ec  mov     [rsi], rax
0x1004781ef  mov     [rsp+238h+var_1F8], 12Eh
0x1004781f7  lea     rcx, [rsp+238h+var_1F0]
0x1004781fc  call    read4
0x100478201  mov     eax, eax
0x100478203  shl     rax, 20h
0x100478207  or      [rsi], rax
0x10047820a  mov     [rsp+238h+var_1F8], 12Fh
0x100478212  mov     dword ptr [rsi+8], 20h ; ' '
0x100478219  lea     rcx, [rsp+238h+var_1F0]
0x10047821e  call    read4
0x100478223  mov     r12d, eax
0x100478226  mov     [rsp+238h+var_1F8], 130h
0x10047822e  lea     rcx, [rsp+238h+var_1F0]
0x100478233  call    read4
0x100478238  mov     r13d, eax
0x10047823b  mov     [rsp+238h+var_1F8], 131h
0x100478243  lea     ecx, [r12+rax]
0x100478247  cmp     ecx, [rsp+238h+var_1E8]
0x10047824b  ja      loc_1004788FF
0x100478251  mov     edi, 132h
0x100478256  mov     [rsp+238h+var_1F8], edi
0x10047825a  test    r15, r15
0x10047825d  jz      short loc_1004782D0
0x10047825f  lfence
0x100478262  lea     r8, [rsp+238h+pbHash]; pbOutput
0x10047826a  mov     edx, r12d; cbInput
0x10047826d  mov     rcx, [rsp+238h+var_1F0]; pbInput
0x100478272  call    hasha256
0x100478277  lea     rax, aSha256; "SHA256"
0x10047827e  mov     [rsp+238h+pPaddingInfo], rax
0x100478286  mov     rax, r12
0x100478289  add     rax, [rsp+238h+var_1F0]
0x10047828e  mov     [rsp+238h+dwFlags], 2; dwFlags
0x100478296  mov     [rsp+238h+cbSignature], r13d; cbSignature
0x10047829b  mov     [rsp+238h+pbSignature], rax; pbSignature
0x1004782a0  mov     r9d, 20h ; ' '; cbHash
0x1004782a6  lea     r8, [rsp+238h+pbHash]; pbHash
0x1004782ae  lea     rdx, [rsp+238h+pPaddingInfo]; pPaddingInfo
0x1004782b6  mov     rcx, [rsp+238h+hKey]; hKey
0x1004782be  call    BCryptVerifySignature_0
0x1004782c3  test    eax, eax
0x1004782c5  jnz     loc_100478918
0x1004782cb  mov     edi, 133h
0x1004782d0  lea     rax, aSha256; "SHA256"
0x1004782d7  mov     [rsp+238h+var_158], 0Eh
0x1004782e3  mov     [rsp+238h+var_150], rax
0x1004782eb  mov     [rsp+238h+pParameterList.ulVersion], ebx
0x1004782f2  mov     [rsp+238h+pParameterList.cBuffers], 1
0x1004782fd  lea     rax, [rsp+238h+var_158]
0x100478305  mov     [rsp+238h+pParameterList.pBuffers], rax
0x10047830d  mov     rax, [rsp+238h+pbInput]
0x100478315  mov     dword ptr [rax], 344B4345h
0x10047831b  inc     edi
0x10047831d  mov     [rsp+238h+var_1F8], edi
0x100478321  mov     [rsp+238h+dwFlags], ebx; dwFlags
0x100478325  mov     [rsp+238h+cbSignature], 98h; cbInput
0x10047832d  mov     [rsp+238h+pbSignature], rax; pbInput
0x100478332  lea     r9, [rsp+238h+phKey]; phKey
0x100478337  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x10047833e  xor     edx, edx; hImportKey
0x100478340  mov     rcx, cs:hAlgorithm; hAlgorithm
0x100478347  call    BCryptImportKeyPair_0
0x10047834c  test    eax, eax
0x10047834e  jnz     loc_10047892D
0x100478354  lfence
0x100478357  inc     edi
0x100478359  mov     [rsp+238h+var_1F8], edi
0x10047835d  mov     [rsp+238h+dwFlags], ebx; dwFlags
0x100478361  mov     [rsp+238h+cbSignature], r12d; cbInput
0x100478366  mov     rax, [rsp+238h+var_1F0]
0x10047836b  mov     [rsp+238h+pbSignature], rax; pbInput
0x100478370  lea     r9, [rsp+238h+hPubKey]; phKey
0x100478375  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x10047837c  xor     edx, edx; hImportKey
0x10047837e  mov     rcx, cs:hAlgorithm; hAlgorithm
0x100478385  call    BCryptImportKeyPair_0
0x10047838a  test    eax, eax
0x10047838c  jnz     loc_10047892D
0x100478392  inc     edi
0x100478394  mov     [rsp+238h+var_1F8], edi
0x100478398  xor     r9d, r9d; dwFlags
0x10047839b  lea     r8, [rsp+238h+phAgreedSecret]; phAgreedSecret
0x1004783a3  mov     rdx, [rsp+238h+hPubKey]; hPubKey
0x1004783a8  mov     rcx, [rsp+238h+phKey]; hPrivKey
0x1004783ad  call    BCryptSecretAgreement_0
0x1004783b2  test    eax, eax
0x1004783b4  jnz     loc_10047892D
0x1004783ba  inc     edi
0x1004783bc  mov     [rsp+238h+var_1F8], edi
0x1004783c0  lea     r9, [rsi+0Ch]; pbDerivedKey
0x1004783c4  mov     [rsp+238h+dwFlags], ebx; dwFlags
0x1004783c8  lea     rax, [rsp+238h+pcbResult]
0x1004783d0  mov     qword ptr [rsp+238h+cbSignature], rax; pcbResult
0x1004783d5  mov     dword ptr [rsp+238h+pbSignature], 20h ; ' '; cbDerivedKey
0x1004783dd  lea     r8, [rsp+238h+pParameterList]; pParameterList
0x1004783e5  lea     rdx, pwszKDF; "HASH"
0x1004783ec  mov     rcx, [rsp+238h+phAgreedSecret]; hSharedSecret
0x1004783f4  call    BCryptDeriveKey_0
0x1004783f9  test    eax, eax
0x1004783fb  jnz     loc_10047892D
0x100478401  mov     rdi, [rsp+238h+var_188]
0x100478409  mov     r13, [rsp+238h+var_180]
0x100478411  jmp     short loc_10047843A
0x100478413  xor     ebx, ebx
0x100478415  mov     rsi, [rsp+238h+var_1D0]
0x10047841a  mov     r14, [rsp+238h+var_170]
0x100478422  mov     rdi, [rsp+238h+var_168]
0x10047842a  mov     r15, [rsp+238h+var_160]
0x100478432  mov     r13, [rsp+238h+var_1B0]
0x10047843a  mov     rcx, [rsp+238h+phKey]; hKey
0x10047843f  call    BCryptDestroyKey_0
0x100478444  mov     rcx, [rsp+238h+hPubKey]; hKey
0x100478449  call    BCryptDestroyKey_0
0x10047844e  mov     rcx, [rsp+238h+phAgreedSecret]; hSecret
0x100478456  call    BCryptDestroySecret_0
0x10047845b  test    rsi, rsi
0x10047845e  jz      loc_1004788CB
0x100478464  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x10047846c  movdqu  [rsp+238h+var_C0], xmm0
0x100478475  mov     word ptr [rsp+238h+var_D0], bx
0x10047847d  mov     rax, r14
0x100478480  mov     r8, rbx
0x100478483  cmp     [r14], bx
0x100478487  jz      short loc_100478495
0x100478489  inc     r8
0x10047848c  lea     rax, [rax+2]
0x100478490  cmp     [rax], bx
0x100478493  jnz     short loc_100478489
0x100478495  mov     rdx, r14
0x100478498  lea     rcx, [rsp+238h+var_D0]
0x1004784a0  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x1004784a5  nop
0x1004784a6  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1004784ae  movdqu  [rsp+238h+var_100], xmm0
0x1004784b7  mov     word ptr [rsp+238h+var_110], bx
0x1004784bf  mov     rax, rdi
0x1004784c2  mov     r8, rbx
0x1004784c5  cmp     [rdi], bx
0x1004784c8  jz      short loc_1004784D6
0x1004784ca  inc     r8
0x1004784cd  lea     rax, [rax+2]
0x1004784d1  cmp     [rax], bx
0x1004784d4  jnz     short loc_1004784CA
0x1004784d6  mov     rdx, rdi
0x1004784d9  lea     rcx, [rsp+238h+var_110]
0x1004784e1  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x1004784e6  nop
0x1004784e7  lea     rdx, [rsp+238h+var_110]
0x1004784ef  cmp     qword ptr [rsp+238h+var_100+8], 8
0x1004784f8  cmovnb  rdx, [rsp+238h+var_110]
0x100478501  mov     r8, qword ptr [rsp+238h+var_100]
0x100478509  lea     rcx, [rsp+238h+var_D0]
0x100478511  call    ?append@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::append(char16_t const * const,unsigned __int64)
0x100478516  nop
0x100478517  mov     rax, qword ptr [rsp+238h+var_100+8]
0x10047851f  mov     r12, 7FFFFFFFFFFFFFFFh
0x100478529  cmp     rax, 8
0x10047852d  jb      short loc_10047857C
0x10047852f  inc     rax
0x100478532  mov     rdx, [rsp+238h+var_110]
0x10047853a  mov     rcx, rdx
0x10047853d  cmp     rax, r12
0x100478540  ja      short loc_100478575
0x100478542  add     rax, rax
0x100478545  mov     r14d, 1000h
0x10047854b  cmp     rax, r14
0x10047854e  jb      short loc_10047856B
0x100478550  test    cl, 1Fh
0x100478553  jnz     short loc_100478575
0x100478555  mov     rdx, [rdx-8]
0x100478559  cmp     rdx, rcx
0x10047855c  jnb     short loc_100478575
0x10047855e  sub     rcx, rdx
0x100478561  sub     rcx, 8
0x100478565  cmp     rcx, 1Fh
0x100478569  ja      short loc_100478575
0x10047856b  mov     rcx, rdx; void *
0x10047856e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100478573  jmp     short loc_100478582
0x100478575  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x10047857c  mov     r14d, 1000h
0x100478582  test    r15, r15
0x100478585  jz      loc_100478652
0x10047858b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100478593  movdqu  [rsp+238h+var_E0], xmm0
0x10047859c  mov     word ptr [rsp+238h+var_F0], bx
0x1004785a4  mov     rax, r15
0x1004785a7  mov     r8, rbx
0x1004785aa  cmp     [r15], bx
0x1004785ae  jz      short loc_1004785BC
0x1004785b0  inc     r8
0x1004785b3  lea     rax, [rax+2]
0x1004785b7  cmp     [rax], bx
0x1004785ba  jnz     short loc_1004785B0
0x1004785bc  mov     rdx, r15
0x1004785bf  lea     rcx, [rsp+238h+var_F0]
0x1004785c7  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x1004785cc  nop
0x1004785cd  lea     rdx, [rsp+238h+var_F0]
0x1004785d5  cmp     qword ptr [rsp+238h+var_E0+8], 8
0x1004785de  cmovnb  rdx, [rsp+238h+var_F0]
0x1004785e7  mov     r8, qword ptr [rsp+238h+var_E0]
0x1004785ef  lea     rcx, [rsp+238h+var_D0]
0x1004785f7  call    ?append@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::append(char16_t const * const,unsigned __int64)
0x1004785fc  nop
0x1004785fd  mov     rax, qword ptr [rsp+238h+var_E0+8]
0x100478605  cmp     rax, 8
0x100478609  jb      short loc_100478652
0x10047860b  inc     rax
0x10047860e  mov     rcx, [rsp+238h+var_F0]
0x100478616  mov     rdx, rcx
0x100478619  cmp     rax, r12
0x10047861c  ja      loc_1004786CB
0x100478622  add     rax, rax
0x100478625  cmp     rax, r14
0x100478628  jb      short loc_10047864D
0x10047862a  test    dl, 1Fh
0x10047862d  jnz     loc_1004786CB
0x100478633  mov     rcx, [rcx-8]; void *
0x100478637  cmp     rcx, rdx
0x10047863a  jnb     loc_1004786CB
0x100478640  sub     rdx, rcx
0x100478643  sub     rdx, 8
0x100478647  cmp     rdx, 1Fh
0x10047864b  ja      short loc_1004786CB
0x10047864d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100478652  call    GetCacheLock
0x100478657  mov     rdx, rax
0x10047865a  mov     rcx, [rax]
0x10047865d  mov     rax, [rcx+8]
0x100478661  mov     rcx, rdx
0x100478664  call    cs:__guard_dispatch_icall_fptr
0x10047866a  xorps   xmm0, xmm0
0x10047866d  movdqu  [rsp+238h+var_A0], xmm0
0x100478676  lea     rdx, [rsp+238h+var_D0]
0x10047867e  lea     rcx, [rsp+238h+var_B0]
0x100478686  call    ?_Construct_lv_contents@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXAEBV12@@Z; std::basic_string<char16_t>::_Construct_lv_contents(std::basic_string<char16_t> const &)
0x10047868b  mov     [rsp+238h+var_90], rsi
0x100478693  mov     rdi, cs:?s_var@?1???R?$Instance@V?$map@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUEnclaveSession@@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUEnclaveSession@@@std@@@2@@std@@@@QEAAAEAV?$map@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUEnclaveSession@@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUEnclaveSession@@@std@@@2@@std@@XZ@4PEAV23@EA; std::map<std::basic_string<char16_t>,EnclaveSession *> * `Instance<std::map<std::basic_string<char16_t>,EnclaveSession *>>::operator()(void)'::`2'::s_var
0x10047869a  test    rdi, rdi
0x10047869d  jnz     short loc_1004786DC
0x10047869f  lea     ecx, [rdi+10h]; unsigned __int64
0x1004786a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1004786a7  mov     rdi, rax
0x1004786aa  mov     [rsp+238h+var_1B0], rax
0x1004786b2  test    rax, rax
0x1004786b5  jz      short loc_1004786D2
0x1004786b7  mov     [rax], rbx
0x1004786ba  mov     [rax+8], rbx
0x1004786be  mov     rcx, rax
0x1004786c1  call    ?_Buyheadnode@?$_Tree_comp_alloc@V?$_Tmap_traits@PEAUEnclaveSession@@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$less@PEAUEnclaveSession@@@3@V?$allocator@U?$pair@QEAUEnclaveSession@@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@std@@@3@$0A@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAUEnclaveSession@@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@std@@PEAX@2@XZ; std::_Tree_comp_alloc<std::_Tmap_traits<EnclaveSession *,std::basic_string<char16_t>,std::less<EnclaveSession *>,std::allocator<std::pair<EnclaveSession * const,std::basic_string<char16_t>>>,0>>::_Buyheadnode(void)
0x1004786c6  mov     [rdi], rax
0x1004786c9  jmp     short loc_1004786D5
0x1004786cb  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004786d2  mov     rdi, rbx
0x1004786d5  mov     cs:?s_var@?1???R?$Instance@V?$map@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUEnclaveSession@@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUEnclaveSession@@@std@@@2@@std@@@@QEAAAEAV?$map@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUEnclaveSession@@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUEnclaveSession@@@std@@@2@@std@@XZ@4PEAV23@EA, rdi; std::map<std::basic_string<char16_t>,EnclaveSession *> * `Instance<std::map<std::basic_string<char16_t>,EnclaveSession *>>::operator()(void)'::`2'::s_var
0x1004786dc  lea     rdx, [rsp+238h+var_B0]
  ... truncated ...
```
