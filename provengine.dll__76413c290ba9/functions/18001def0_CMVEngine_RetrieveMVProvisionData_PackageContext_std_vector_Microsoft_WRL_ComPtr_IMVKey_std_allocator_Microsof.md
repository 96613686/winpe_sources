# CMVEngine::RetrieveMVProvisionData(PackageContext *,std::vector<Microsoft::WRL::ComPtr<IMVKey>,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>> const &,__MIDL___MIDL_itf_mvengine_0000_0000_0001,__MIDL___MIDL_itf_mvdatastore_0000_0000_0001,_MVProvisionData * *,ulong *)

- ea: `0x18001def0`
- end: `0x18001e833`
- name: `?RetrieveMVProvisionData@CMVEngine@@AEAAJPEAUPackageContext@@AEBV?$vector@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@W4__MIDL___MIDL_itf_mvdatastore_0000_0000_0001@@PEAPEAU_MVProvisionData@@PEAK@Z`
- size: `2371`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001a6fc`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x18000b030`
- `0x180011654`
- `0x1800139a0`
- `0x18001def0`
- `0x18001fdec`
- `0x180021d8c`
- `0x180021f40`
- `0x1800228e4`
- `0x180030630`
- `0x1800306a0`
- `0x180030c14`
- `0x180030dc0`
- `0x180036598`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001e7fc`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001e7fc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e38c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e5da`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e61b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e655`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e71d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e38c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e5da`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e61b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e655`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e71d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e77e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e77e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e50a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e50a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall CMVEngine::RetrieveMVProvisionData(
        __int64 a1,
        struct PackageContext *a2,
        _QWORD *a3,
        unsigned int a4,
        unsigned int a5,
        _QWORD *a6,
        unsigned int *a7)
{
  __int64 v9; // r13
  unsigned __int64 v10; // rdx
  __int64 *v11; // rcx
  __int64 *v12; // rax
  __int64 *v13; // rbx
  __int64 v14; // rbx
  unsigned __int64 v15; // rdi
  __m128i v16; // xmm6
  unsigned int v17; // edi
  unsigned int v18; // r14d
  _QWORD *v19; // rsi
  __int64 v20; // rcx
  unsigned int v21; // r15d
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD, _QWORD *); // rdi
  int v23; // eax
  unsigned int v24; // r14d
  unsigned int v25; // edi
  __int64 v26; // rcx
  __int64 i; // rax
  unsigned int v29; // ecx
  __int64 v30; // r14
  __int64 v31; // r13
  _DWORD *v32; // r12
  __int64 v33; // r8
  int v34; // eax
  __int64 v35; // r8
  int *v36; // rdx
  int v37; // ecx
  unsigned int j; // edi
  __int64 v39; // rcx
  char *v40; // rdx
  unsigned __int64 v41; // r8
  unsigned __int16 *v42; // rax
  unsigned __int64 v43; // r13
  __int64 v44; // r14
  unsigned __int64 v45; // r12
  unsigned __int16 *v46; // rax
  unsigned int v47; // r14d
  char *v48; // r14
  _QWORD *v49; // rax
  unsigned __int64 v50; // r8
  unsigned int k; // edi
  __int64 v52; // rcx
  unsigned int m; // edi
  __int64 v54; // rcx
  unsigned __int16 **v55; // [rsp+20h] [rbp-198h]
  int v56; // [rsp+20h] [rbp-198h]
  unsigned __int64 *v57; // [rsp+28h] [rbp-190h]
  unsigned int *v58; // [rsp+30h] [rbp-188h]
  unsigned int v59; // [rsp+40h] [rbp-178h] BYREF
  unsigned int v60[4]; // [rsp+48h] [rbp-170h] BYREF
  int v61; // [rsp+58h] [rbp-160h]
  __int64 v62; // [rsp+60h] [rbp-158h]
  __int64 v63; // [rsp+68h] [rbp-150h] BYREF
  struct PackageContext *v64; // [rsp+70h] [rbp-148h]
  __int64 v65; // [rsp+78h] [rbp-140h]
  LPVOID pv[2]; // [rsp+80h] [rbp-138h] BYREF
  __int128 v67; // [rsp+90h] [rbp-128h]
  unsigned __int16 *v68; // [rsp+A0h] [rbp-118h]
  _QWORD *v69; // [rsp+A8h] [rbp-110h]
  unsigned int *v70; // [rsp+B0h] [rbp-108h]
  __int64 v71; // [rsp+B8h] [rbp-100h]
  char v72[16]; // [rsp+C0h] [rbp-F8h] BYREF
  char v73[16]; // [rsp+D0h] [rbp-E8h] BYREF
  void *v74[2]; // [rsp+E0h] [rbp-D8h] BYREF
  __int64 v75; // [rsp+F0h] [rbp-C8h]
  unsigned __int64 v76; // [rsp+F8h] [rbp-C0h]
  const void *Src[2]; // [rsp+100h] [rbp-B8h] BYREF
  __int64 v78; // [rsp+110h] [rbp-A8h]
  unsigned __int64 v79; // [rsp+118h] [rbp-A0h]
  unsigned int *v80; // [rsp+120h] [rbp-98h]
  __int64 v81; // [rsp+128h] [rbp-90h]
  char v82[32]; // [rsp+130h] [rbp-88h] BYREF
  unsigned int *v83; // [rsp+150h] [rbp-68h]
  __int64 v84; // [rsp+158h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v64 = a2;
  v9 = a1;
  v62 = a1;
  v69 = a6;
  v70 = a7;
  *a6 = 0;
  *a7 = 0;
  v10 = *(_QWORD *)a2;
  v11 = *(__int64 **)(a1 + 288);
  v12 = (__int64 *)v11[1];
  v13 = v11;
  if ( *((_BYTE *)v12 + 25) )
    goto LABEL_104;
  do
  {
    if ( v12[4] >= v10 )
    {
      v13 = v12;
      v12 = (__int64 *)*v12;
    }
    else
    {
      v12 = (__int64 *)v12[2];
    }
  }
  while ( !*((_BYTE *)v12 + 25) );
  if ( v13 == v11 || v10 < v13[4] )
  {
LABEL_104:
    std::_Xout_of_range("invalid map<K, T> key");
    return v59;
  }
  v14 = v13[5];
  v71 = v14;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  v67 = 0u;
  v15 = (__int64)(a3[1] - *a3) >> 3;
  if ( v15 > 0xFFFFFFFF )
  {
    v17 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F8,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)0x80070216LL,
      (int)v55);
    goto LABEL_101;
  }
  pv[0] = 0;
  LODWORD(pv[1]) = 0;
  co_array_t<IMVKey *>::allocate((__int64)pv, v15);
  v16 = *(__m128i *)pv;
  if ( !pv[0] )
  {
    v17 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)0x8007000ELL,
      (int)v55);
LABEL_101:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x318,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)v17,
      v56);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    return v17;
  }
  v18 = 0;
  v19 = pv[0];
  while ( v18 < (unsigned int)v15 )
  {
    v20 = *(_QWORD *)(*a3 + 8LL * v18);
    *(_QWORD *)(v16.m128i_i64[0] + 8LL * v18) = v20;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
    ++v18;
  }
  *(_QWORD *)&v67 = v16.m128i_i64[0];
  v21 = _mm_cvtsi128_si32(_mm_srli_si128(v16, 8));
  DWORD2(v67) = v21;
  *(_OWORD *)v60 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)v14 + 48LL);
  FreeProvisionDataArray((__int64)v60);
  *(_OWORD *)v60 = 0;
  v58 = &v60[2];
  v57 = (unsigned __int64 *)v60;
  LODWORD(v55) = v21;
  v23 = v22(v14, a4, a5, v19);
  v24 = v23;
  v61 = v23;
  if ( v23 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, void **))(**(_QWORD **)v64 + 16LL))(*(_QWORD *)v64, v74);
    for ( i = 0; ; i = v59 + 1 )
    {
      v59 = i;
      v29 = v60[2];
      if ( (unsigned int)i >= v60[2] )
        break;
      v30 = v9 + 248;
      v31 = 104 * i;
      v65 = 104 * i;
      v32 = (_DWORD *)(104 * i + *(_QWORD *)v60);
      if ( *v32 == 1 )
      {
        v63 = 104 * i + *(_QWORD *)v60;
        v55 = (unsigned __int16 **)std::_Tree_buy<std::pair<std::wstring const,_MVProvisionData const *>>::_Buynode<unsigned short * const &,_MVProvisionData const *>(
                                     v30,
                                     v32 + 16,
                                     &v63);
        std::_Tree<std::_Tmap_traits<std::wstring,_MVProvisionData const *,wstring_less_no_case,std::allocator<std::pair<std::wstring const,_MVProvisionData const *>>,0>>::_Insert_nohint<std::pair<std::wstring const,_MVProvisionData const *> &,std::_Tree_node<std::pair<std::wstring const,_MVProvisionData const *>,void *> *>(
          v30,
          v72,
          v33,
          v55 + 4);
        v34 = v32[18];
        if ( v34 > *(_DWORD *)(v30 + 32) )
          *(_DWORD *)(v30 + 32) = v34;
      }
      else if ( *v32 == 2 )
      {
        v55 = (unsigned __int16 **)std::_Tree_buy<std::wstring>::_Buynode<unsigned short * const &>(v30 + 16, v32 + 16);
        std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring &,std::_Tree_node<std::wstring,void *> *>(
          v30 + 16,
          v73,
          v35,
          v55 + 4);
      }
      v36 = (int *)((*(_QWORD *)(v62 + 208) + 40LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(v62 + 208) + 44LL) != 0));
      *(_DWORD *)(*(_QWORD *)v60 + v31 + 96) = v36 != 0;
      if ( v36 )
        v37 = *v36;
      else
        v37 = -1;
      *(_DWORD *)(*(_QWORD *)v60 + v31 + 92) = v37;
      if ( *(_DWORD *)(*(_QWORD *)v60 + v31 + 4) == 1 )
      {
        v9 = v62;
      }
      else
      {
        if ( *(_DWORD *)(*(_QWORD *)v60 + v31 + 4) != 2 )
        {
          if ( (unsigned int)dword_18005A000 > 2 )
          {
            v59 = v61;
            v83 = &v59;
            v84 = 4;
            tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F959, 0, 0, 3, v82);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x33C,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
            (const char *)0x80070057LL,
            (int)v55);
          if ( v76 >= 8 )
            operator delete(v74[0]);
          v76 = 7;
          v75 = 0;
          LOWORD(v74[0]) = 0;
          FreeProvisionDataArray((__int64)v60);
          for ( j = 0; j < v21; ++j )
          {
            v39 = v19[j];
            if ( v39 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
              v19[j] = 0;
            }
          }
          CoTaskMemFree(v19);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          return 2147942487LL;
        }
        v40 = (char *)v74;
        if ( v76 >= 8 )
          v40 = (char *)v74[0];
        v79 = 7;
        v78 = 0;
        LOWORD(Src[0]) = 0;
        if ( *(_WORD *)v40 )
        {
          v41 = -1;
          do
            ++v41;
          while ( *(_WORD *)&v40[2 * v41] );
        }
        else
        {
          v41 = 0;
        }
        std::wstring::assign(Src, v40, v41);
        std::wstring::push_back(Src);
        std::wstring::append(Src, *(char **)(*(_QWORD *)v60 + v31 + 40));
        v63 = *(_QWORD *)v60;
        v42 = (unsigned __int16 *)Src;
        if ( v79 >= 8 )
          v42 = (unsigned __int16 *)Src[0];
        v68 = v42;
        v43 = -1;
        do
          ++v43;
        while ( v42[v43] );
        v44 = v65;
        *(_QWORD *)(*(_QWORD *)v60 + v65 + 48) = 0;
        v45 = v43 + 1;
        if ( v43 + 1 < v43 || (pv[0] = 0, !is_mul_ok(v45, 2u)) )
        {
          v47 = -2147024362;
LABEL_74:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x345,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
            (const char *)v47,
            (int)v55);
          if ( v79 >= 8 )
            operator delete((void *)Src[0]);
          v79 = 7;
          v78 = 0;
          LOWORD(Src[0]) = 0;
          if ( v76 >= 8 )
            operator delete(v74[0]);
          v76 = 7;
          v75 = 0;
          LOWORD(v74[0]) = 0;
          FreeProvisionDataArray((__int64)v60);
          for ( k = 0; k < v21; ++k )
          {
            v52 = v19[k];
            if ( v52 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
              v19[k] = 0;
            }
          }
          CoTaskMemFree(v19);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          return v47;
        }
        v46 = (unsigned __int16 *)CoTaskMemAlloc(2 * v45);
        *(_QWORD *)(v63 + v44 + 48) = v46;
        v47 = v46 == 0 ? 0x8007000E : 0;
        if ( !v46 )
          goto LABEL_74;
        StringCchCopyNExW(v46, v43 + 1, v68, v43, v55, v57, (unsigned int)v58);
        v48 = (char *)v74;
        if ( v76 >= 8 )
          v48 = (char *)v74[0];
        v9 = v62;
        v49 = (_QWORD *)std::map<std::wstring,std::wstring>::operator[](v62 + 320, Src);
        if ( *(_WORD *)v48 )
        {
          v50 = -1;
          do
            ++v50;
          while ( *(_WORD *)&v48[2 * v50] );
        }
        else
        {
          v50 = 0;
        }
        std::wstring::assign(v49, v48, v50);
        ProvStateContext::MapProvXmlToPackage(
          *(ProvStateContext **)(v9 + 208),
          *(const unsigned __int16 **)(*(_QWORD *)v60 + v65 + 48),
          v64);
        if ( v79 >= 8 )
          operator delete((void *)Src[0]);
      }
    }
    *v69 = *(_QWORD *)v60;
    *v70 = v29;
    *(_QWORD *)v60 = 0;
    v60[2] = 0;
    if ( v76 >= 8 )
      operator delete(v74[0]);
    v76 = 7;
    v75 = 0;
    LOWORD(v74[0]) = 0;
    FreeProvisionDataArray((__int64)v60);
    for ( m = 0; m < v21; ++m )
    {
      v54 = v19[m];
      if ( v54 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v19[m] = 0;
      }
    }
    CoTaskMemFree(v19);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      v59 = v23;
      v80 = &v59;
      v81 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &unk_18004F288, 0, 0, 3, Src);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x324,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)v24,
      (int)v55);
    FreeProvisionDataArray((__int64)v60);
    v25 = 0;
    if ( v21 )
    {
      do
      {
        v26 = v19[v25];
        if ( v26 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          v19[v25] = 0;
        }
        ++v25;
      }
      while ( v25 < v21 );
      v24 = v61;
    }
    CoTaskMemFree(v19);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    return v24;
  }
}

```

## disassembly

```asm
0x18001def0  mov     rax, rsp
0x18001def3  push    rbx
0x18001def4  push    rsi
0x18001def5  push    rdi
0x18001def6  push    r12
0x18001def8  push    r13
0x18001defa  push    r14
0x18001defc  push    r15
0x18001defe  sub     rsp, 180h
0x18001df05  movaps  xmmword ptr [rax-48h], xmm6
0x18001df09  mov     rax, cs:__security_cookie
0x18001df10  xor     rax, rsp
0x18001df13  mov     [rsp+1B8h+var_58], rax
0x18001df1b  mov     r12d, r9d
0x18001df1e  mov     r15, r8
0x18001df21  mov     rax, rdx
0x18001df24  mov     [rsp+1B8h+var_148], rdx
0x18001df29  mov     r13, rcx
0x18001df2c  mov     [rsp+1B8h+var_158], rcx
0x18001df31  mov     rcx, [rsp+1B8h+arg_28]
0x18001df39  mov     [rsp+1B8h+var_110], rcx
0x18001df41  mov     rdx, [rsp+1B8h+arg_30]
0x18001df49  mov     [rsp+1B8h+var_108], rdx
0x18001df51  xor     esi, esi
0x18001df53  mov     [rcx], rsi
0x18001df56  mov     [rdx], esi
0x18001df58  mov     rdx, [rax]
0x18001df5b  mov     rcx, [r13+120h]
0x18001df62  mov     rax, [rcx+8]
0x18001df66  mov     rbx, rcx
0x18001df69  cmp     [rax+19h], sil
0x18001df6d  jnz     loc_18001E7F5
0x18001df73  cmp     [rax+20h], rdx
0x18001df77  jnb     short loc_18001DF7F
0x18001df79  mov     rax, [rax+10h]
0x18001df7d  jmp     short loc_18001DF85
0x18001df7f  mov     rbx, rax
0x18001df82  mov     rax, [rax]
0x18001df85  cmp     [rax+19h], sil
0x18001df89  jz      short loc_18001DF73
0x18001df8b  cmp     rbx, rcx
0x18001df8e  jz      loc_18001E7F5
0x18001df94  cmp     rdx, [rbx+20h]
0x18001df98  jb      loc_18001E7F5
0x18001df9e  mov     rbx, [rbx+28h]
0x18001dfa2  mov     [rsp+1B8h+var_100], rbx
0x18001dfaa  test    rbx, rbx
0x18001dfad  jz      short loc_18001DFBF
0x18001dfaf  mov     rax, [rbx]
0x18001dfb2  mov     rcx, rbx
0x18001dfb5  mov     rax, [rax+8]
0x18001dfb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfbe  nop
0x18001dfbf  xorps   xmm0, xmm0
0x18001dfc2  movups  [rsp+1B8h+var_128], xmm0
0x18001dfca  mov     dword ptr [rsp+1B8h+var_128+8], esi
0x18001dfd1  mov     qword ptr [rsp+1B8h+var_128], rsi
0x18001dfd9  mov     rdi, [r15+8]
0x18001dfdd  sub     rdi, [r15]
0x18001dfe0  sar     rdi, 3
0x18001dfe4  mov     eax, 0FFFFFFFFh
0x18001dfe9  cmp     rdi, rax
0x18001dfec  ja      loc_18001E79E
0x18001dff2  mov     [rsp+1B8h+pv], rsi
0x18001dffa  mov     dword ptr [rsp+1B8h+pv+8], esi
0x18001e001  mov     rdx, rdi
0x18001e004  lea     rcx, [rsp+1B8h+pv]
0x18001e00c  call    ?allocate@?$co_array_t@PEAUIMVKey@@@@QEAAX_K@Z; co_array_t<IMVKey *>::allocate(unsigned __int64)
0x18001e011  movaps  xmm6, xmmword ptr [rsp+1B8h+pv]
0x18001e019  movaps  xmmword ptr [rsp+1B8h+pv], xmm6
0x18001e021  movq    rax, xmm6
0x18001e026  test    rax, rax
0x18001e029  jnz     short loc_18001E052
0x18001e02b  mov     rcx, [rsp+1B8h]; this
0x18001e033  mov     edi, 8007000Eh
0x18001e038  mov     r9d, edi; char *
0x18001e03b  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001e042  mov     edx, 2FBh; void *
0x18001e047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e04c  nop
0x18001e04d  jmp     loc_18001E7BF
0x18001e052  mov     r14d, esi
0x18001e055  movq    rsi, xmm6
0x18001e05a  cmp     r14d, edi
0x18001e05d  jnb     short loc_18001E07E
0x18001e05f  mov     edx, r14d
0x18001e062  mov     rax, [r15]
0x18001e065  mov     rcx, [rax+rdx*8]
0x18001e069  mov     [rsi+rdx*8], rcx
0x18001e06d  mov     rax, [rcx]
0x18001e070  mov     rax, [rax+8]
0x18001e074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e079  inc     r14d
0x18001e07c  jmp     short loc_18001E05A
0x18001e07e  mov     qword ptr [rsp+1B8h+var_128], rsi
0x18001e086  psrldq  xmm6, 8
0x18001e08b  movd    r15d, xmm6
0x18001e090  mov     dword ptr [rsp+1B8h+var_128+8], r15d
0x18001e098  xorps   xmm0, xmm0
0x18001e09b  movups  xmmword ptr [rsp+1B8h+var_170], xmm0
0x18001e0a0  mov     rax, [rbx]
0x18001e0a3  mov     rdi, [rax+30h]
0x18001e0a7  lea     rcx, [rsp+1B8h+var_170]
0x18001e0ac  call    ?FreeProvisionDataArray@@YAXPEAU?$co_array_t@U_MVProvisionData@@@@@Z; FreeProvisionDataArray(co_array_t<_MVProvisionData> *)
0x18001e0b1  xorps   xmm0, xmm0
0x18001e0b4  movups  xmmword ptr [rsp+1B8h+var_170], xmm0
0x18001e0b9  lea     rax, [rsp+1B8h+var_170+8]
0x18001e0be  mov     qword ptr [rsp+1B8h+var_188], rax; unsigned int
0x18001e0c3  lea     rax, [rsp+1B8h+var_170]
0x18001e0c8  mov     [rsp+1B8h+var_190], rax; unsigned __int64 *
0x18001e0cd  mov     dword ptr [rsp+1B8h+var_198], r15d
0x18001e0d2  mov     r9, rsi
0x18001e0d5  mov     r8d, [rsp+1B8h+arg_20]
0x18001e0dd  mov     edx, r12d
0x18001e0e0  mov     rcx, rbx
0x18001e0e3  mov     rax, rdi
0x18001e0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0eb  mov     r14d, eax
0x18001e0ee  mov     [rsp+1B8h+var_160], eax
0x18001e0f2  xor     r12d, r12d
0x18001e0f5  test    eax, eax
0x18001e0f7  jns     loc_18001E1D2
0x18001e0fd  mov     ecx, cs:dword_18005A000
0x18001e103  cmp     ecx, 2
0x18001e106  jbe     short loc_18001E153
0x18001e108  mov     [rsp+1B8h+var_178], eax
0x18001e10c  lea     rax, [rsp+1B8h+var_178]
0x18001e111  mov     [rsp+1B8h+var_98], rax
0x18001e119  mov     [rsp+1B8h+var_90], 4
0x18001e125  lea     rax, [rsp+1B8h+Src]
0x18001e12d  mov     [rsp+1B8h+var_190], rax
0x18001e132  mov     dword ptr [rsp+1B8h+var_198], 3; int
0x18001e13a  xor     r9d, r9d
0x18001e13d  xor     r8d, r8d
0x18001e140  lea     rdx, unk_18004F288
0x18001e147  lea     rcx, dword_18005A000
0x18001e14e  call    _tlgWriteTransfer_EventWriteTransfer
0x18001e153  mov     rcx, [rsp+1B8h]; this
0x18001e15b  mov     r9d, r14d; char *
0x18001e15e  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001e165  mov     edx, 324h; void *
0x18001e16a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e16f  nop
0x18001e170  lea     rcx, [rsp+1B8h+var_170]
0x18001e175  call    ?FreeProvisionDataArray@@YAXPEAU?$co_array_t@U_MVProvisionData@@@@@Z; FreeProvisionDataArray(co_array_t<_MVProvisionData> *)
0x18001e17a  nop
0x18001e17b  test    rsi, rsi
0x18001e17e  jz      short loc_18001E1BA
0x18001e180  mov     edi, r12d
0x18001e183  test    r15d, r15d
0x18001e186  jz      short loc_18001E1B0
0x18001e188  mov     r14d, edi
0x18001e18b  mov     rcx, [rsi+r14*8]
0x18001e18f  test    rcx, rcx
0x18001e192  jz      short loc_18001E1A4
0x18001e194  mov     rax, [rcx]
0x18001e197  mov     rax, [rax+10h]
0x18001e19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a0  mov     [rsi+r14*8], r12
0x18001e1a4  inc     edi
0x18001e1a6  cmp     edi, r15d
0x18001e1a9  jb      short loc_18001E188
0x18001e1ab  mov     r14d, [rsp+1B8h+var_160]
0x18001e1b0  mov     rcx, rsi; pv
0x18001e1b3  call    cs:__imp_CoTaskMemFree
0x18001e1b9  nop
0x18001e1ba  mov     rax, [rbx]
0x18001e1bd  mov     rcx, rbx
0x18001e1c0  mov     rax, [rax+10h]
0x18001e1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1c9  nop
0x18001e1ca  mov     eax, r14d
0x18001e1cd  jmp     loc_18001E807
0x18001e1d2  mov     rcx, [rsp+1B8h+var_148]
0x18001e1d7  mov     rcx, [rcx]
0x18001e1da  mov     rax, [rcx]
0x18001e1dd  lea     rdx, [rsp+1B8h+var_D8]
0x18001e1e5  mov     rax, [rax+10h]
0x18001e1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ee  nop
0x18001e1ef  mov     eax, r12d
0x18001e1f2  mov     edi, 8007000Eh
0x18001e1f7  mov     [rsp+1B8h+var_178], eax
0x18001e1fb  mov     ecx, [rsp+1B8h+var_170+8]
0x18001e1ff  cmp     eax, ecx
0x18001e201  jnb     loc_18001E6E6
0x18001e207  lea     r14, [r13+0F8h]
0x18001e20e  imul    r13, rax, 68h ; 'h'
0x18001e212  mov     [rsp+1B8h+var_140], r13
0x18001e217  mov     r12, qword ptr [rsp+1B8h+var_170]
0x18001e21c  add     r12, r13
0x18001e21f  cmp     dword ptr [r12], 1
0x18001e224  jnz     short loc_18001E267
0x18001e226  mov     [rsp+1B8h+var_150], r12
0x18001e22b  lea     rdx, [r12+40h]
0x18001e230  lea     r8, [rsp+1B8h+var_150]
0x18001e235  mov     rcx, r14
0x18001e238  call    ??$_Buynode@AEBQEAGPEBU_MVProvisionData@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@std@@PEAX@1@AEBQEAG$$QEAPEBU_MVProvisionData@@@Z; std::_Tree_buy<std::pair<std::wstring const,_MVProvisionData const *>>::_Buynode<ushort * const &,_MVProvisionData const *>(ushort * const &,_MVProvisionData const * &&)
0x18001e23d  lea     r9, [rax+20h]
0x18001e241  mov     [rsp+1B8h+var_198], rax
0x18001e246  lea     rdx, [rsp+1B8h+var_F8]
0x18001e24e  mov     rcx, r14
0x18001e251  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@Uwstring_less_no_case@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_MVProvisionData@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_MVProvisionData const *,wstring_less_no_case,std::allocator<std::pair<std::wstring const,_MVProvisionData const *>>,0>>::_Insert_nohint<std::pair<std::wstring const,_MVProvisionData const *> &,std::_Tree_node<std::pair<std::wstring const,_MVProvisionData const *>,void *> *>(bool,std::pair<std::wstring const,_MVProvisionData const *> &,std::_Tree_node<std::pair<std::wstring const,_MVProvisionData const *>,void *> *)
0x18001e256  mov     eax, [r12+48h]
0x18001e25b  cmp     eax, [r14+20h]
0x18001e25f  jle     short loc_18001E296
0x18001e261  mov     [r14+20h], eax
0x18001e265  jmp     short loc_18001E296
0x18001e267  cmp     dword ptr [r12], 2
0x18001e26c  jnz     short loc_18001E296
0x18001e26e  lea     rdx, [r12+40h]
0x18001e273  lea     rcx, [r14+10h]
0x18001e277  call    ??$_Buynode@AEBQEAG@?$_Tree_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBQEAG@Z; std::_Tree_buy<std::wstring>::_Buynode<ushort * const &>(ushort * const &)
0x18001e27c  lea     r9, [rax+20h]
0x18001e280  mov     [rsp+1B8h+var_198], rax; int
0x18001e285  lea     rdx, [rsp+1B8h+var_E8]
0x18001e28d  lea     rcx, [r14+10h]
0x18001e291  call    ??$_Insert_nohint@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uwstring_less_no_case@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring &,std::_Tree_node<std::wstring,void *> *>(bool,std::wstring &,std::_Tree_node<std::wstring,void *> *)
0x18001e296  mov     rax, [rsp+1B8h+var_158]
0x18001e29b  mov     rax, [rax+0D0h]
0x18001e2a2  mov     ecx, [rax+2Ch]
0x18001e2a5  add     rax, 28h ; '('
0x18001e2a9  neg     ecx
0x18001e2ab  sbb     rdx, rdx
0x18001e2ae  and     rdx, rax
0x18001e2b1  mov     r12d, 0
0x18001e2b7  mov     ecx, r12d
0x18001e2ba  setnz   cl
0x18001e2bd  mov     rax, qword ptr [rsp+1B8h+var_170]
0x18001e2c2  mov     [rax+r13+60h], ecx
0x18001e2c7  test    rdx, rdx
0x18001e2ca  jz      short loc_18001E2D0
0x18001e2cc  mov     ecx, [rdx]
0x18001e2ce  jmp     short loc_18001E2D5
0x18001e2d0  mov     ecx, 0FFFFFFFFh
0x18001e2d5  mov     rax, qword ptr [rsp+1B8h+var_170]
0x18001e2da  mov     [rax+r13+5Ch], ecx
0x18001e2df  mov     rax, qword ptr [rsp+1B8h+var_170]
0x18001e2e4  cmp     dword ptr [rax+r13+4], 1
0x18001e2ea  jz      loc_18001E6D6
0x18001e2f0  cmp     dword ptr [rax+r13+4], 2
0x18001e2f6  jz      loc_18001E412
0x18001e2fc  mov     eax, cs:dword_18005A000
0x18001e302  cmp     eax, 2
0x18001e305  jbe     short loc_18001E356
0x18001e307  mov     eax, [rsp+1B8h+var_160]
0x18001e30b  mov     [rsp+1B8h+var_178], eax
0x18001e30f  lea     rax, [rsp+1B8h+var_178]
0x18001e314  mov     [rsp+1B8h+var_68], rax
0x18001e31c  mov     [rsp+1B8h+var_60], 4
0x18001e328  lea     rax, [rsp+1B8h+var_88]
0x18001e330  mov     [rsp+1B8h+var_190], rax
0x18001e335  mov     dword ptr [rsp+1B8h+var_198], 3; int
0x18001e33d  xor     r9d, r9d
0x18001e340  xor     r8d, r8d
0x18001e343  lea     rdx, byte_18004F959
0x18001e34a  lea     rcx, dword_18005A000
0x18001e351  call    _tlgWriteTransfer_EventWriteTransfer
0x18001e356  mov     rcx, [rsp+1B8h]; this
0x18001e35e  mov     r13d, 80070057h
0x18001e364  mov     r9d, r13d; char *
0x18001e367  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001e36e  mov     edx, 33Ch; void *
0x18001e373  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e378  nop
0x18001e379  cmp     [rsp+1B8h+var_C0], 8
0x18001e382  jb      short loc_18001E392
0x18001e384  mov     rcx, [rsp+1B8h+var_D8]
0x18001e38c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e392  mov     edi, 7
0x18001e397  mov     [rsp+1B8h+var_C0], rdi
0x18001e39f  mov     [rsp+1B8h+var_C8], r12
0x18001e3a7  mov     word ptr [rsp+1B8h+var_D8], r12w
0x18001e3b0  lea     rcx, [rsp+1B8h+var_170]
0x18001e3b5  call    ?FreeProvisionDataArray@@YAXPEAU?$co_array_t@U_MVProvisionData@@@@@Z; FreeProvisionDataArray(co_array_t<_MVProvisionData> *)
0x18001e3ba  nop
0x18001e3bb  test    rsi, rsi
0x18001e3be  jz      short loc_18001E3F5
0x18001e3c0  mov     edi, r12d
0x18001e3c3  test    r15d, r15d
0x18001e3c6  jz      short loc_18001E3EB
0x18001e3c8  mov     r14d, edi
0x18001e3cb  mov     rcx, [rsi+r14*8]
0x18001e3cf  test    rcx, rcx
0x18001e3d2  jz      short loc_18001E3E4
0x18001e3d4  mov     rax, [rcx]
0x18001e3d7  mov     rax, [rax+10h]
0x18001e3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3e0  mov     [rsi+r14*8], r12
0x18001e3e4  inc     edi
0x18001e3e6  cmp     edi, r15d
0x18001e3e9  jb      short loc_18001E3C8
0x18001e3eb  mov     rcx, rsi; pv
0x18001e3ee  call    cs:__imp_CoTaskMemFree
0x18001e3f4  nop
0x18001e3f5  test    rbx, rbx
0x18001e3f8  jz      short loc_18001E40A
0x18001e3fa  mov     rcx, [rbx]
0x18001e3fd  mov     rax, [rcx+10h]
0x18001e401  mov     rcx, rbx
  ... truncated ...
```
