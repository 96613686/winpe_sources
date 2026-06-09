# LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete(long,_GUID const &,ulong,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800b39b0`
- end: `0x1800b420e`
- name: `?OnEs10bGetUiccInfo1Complete@DownloadInstance@Lpd@LPA@@UEAAXJAEBU_GUID@@KAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV56@@Z`
- size: `2142`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001010`
- `0x180005d6c`
- `0x18000ebd0`
- `0x18005f8e4`
- `0x1800602e0`
- `0x180060320`
- `0x1800709e4`
- `0x1800715d0`
- `0x1800716c0`
- `0x180071994`
- `0x180071a8c`
- `0x18007516c`
- `0x1800815e0`
- `0x180084030`
- `0x180088a58`
- `0x180097824`
- `0x18009a764`
- `0x18009b9b4`
- `0x1800a30e0`
- `0x1800a5af8`
- `0x1800a7414`
- `0x1800a83e8`
- `0x1800b1768`
- `0x1800b39b0`
- `0x1800c424c`
- `0x1800d98b4`
- `0x1800dd380`
- `0x180101010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b3db2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b3db2`

## string_xrefs

- `0x1800b39e7`: `LpaServiceLpd`
- `0x1800b3e03`: `LpaServiceLpd`
- `0x1800b3e30`: `LpaServiceLpd`
- `0x1800b3e45`: `LpaServiceLpd`
- `0x1800b4163`: `LpaServiceLpd`
- `0x1800b39e0`: `LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete`
- `0x1800b3df8`: `LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete`
- `0x1800b3e37`: `LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete`
- `0x1800b3e4c`: `LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete`
- `0x1800b3f91`: `LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete`
- `0x1800b4157`: `LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        unsigned __int8 **a5,
        __int64 *a6)
{
  signed int BitValueInBitString; // edi
  int v8; // r15d
  std::_Ref_count_base **v9; // rax
  __int16 *v10; // rdx
  unsigned __int8 **v11; // r13
  __int64 *v12; // r12
  int v13; // ecx
  size_t v14; // r8
  unsigned int *v15; // r9
  LPA::Util *v16; // rcx
  unsigned int *v17; // r9
  __int64 v18; // r11
  unsigned int *v19; // r9
  __int64 v20; // r11
  __int64 v21; // rsi
  __int64 v22; // r8
  __int64 v23; // rbx
  _QWORD *v24; // rcx
  _QWORD *v25; // rax
  unsigned __int64 v26; // rax
  int v27; // ebx
  const void *v28; // rdx
  const void **v29; // r12
  char *v30; // r15
  __int64 v31; // rax
  __int128 v32; // xmm6
  __int128 v33; // xmm7
  __int128 v34; // xmm8
  _QWORD *v35; // rax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64, _QWORD, __int64 *, __int64); // rbx
  _QWORD *v42; // rax
  __int64 *v43; // rax
  int v44; // ecx
  _DWORD *v45; // rax
  int v46; // r8d
  int v47; // r9d
  char *v49; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v50; // [rsp+28h] [rbp-D8h]
  int *v51; // [rsp+30h] [rbp-D0h]
  int *v52; // [rsp+38h] [rbp-C8h]
  std::_Ref_count_base **v53; // [rsp+40h] [rbp-C0h]
  int v54; // [rsp+60h] [rbp-A0h] BYREF
  int v55; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 v56[4]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v57; // [rsp+70h] [rbp-90h]
  std::_Ref_count_base *v58[2]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v59; // [rsp+88h] [rbp-78h]
  const char *v60; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v61; // [rsp+98h] [rbp-68h]
  __int128 v62; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-48h]
  _OWORD v64[9]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v65; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v66; // [rsp+198h] [rbp+98h] BYREF

  BitValueInBitString = a2;
  v8 = 0;
  if ( a2 < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_7;
    v60 = "OnEs10bGetUiccInfo1";
    v55 = *(_DWORD *)(a1 + 904);
    v54 = 2;
    v58[0] = (std::_Ref_count_base *)"LpaServiceLpd";
    v53 = (std::_Ref_count_base **)&v60;
    v52 = &v55;
    v51 = &v54;
    v9 = v58;
    v10 = (__int16 *)byte_180130A21;
  }
  else
  {
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_7;
    v58[0] = (std::_Ref_count_base *)"OnEs10bGetUiccInfo1";
    v54 = *(_DWORD *)(a1 + 904);
    v55 = 2;
    v60 = "LpaServiceLpd";
    v53 = v58;
    v52 = &v54;
    v51 = &v55;
    v9 = (std::_Ref_count_base **)&v60;
    v10 = &word_180130A86;
  }
  v66 = BitValueInBitString;
  LODWORD(v65) = 5;
  *(_QWORD *)v56 = "LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    (unsigned int)"LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete",
    (_DWORD)v10,
    a3,
    a4,
    (__int64)v9,
    (__int64)v56,
    (__int64)v51,
    (__int64)v52,
    (__int64)v53,
    (__int64)&v65,
    (__int64)&v66);
LABEL_7:
  v62 = 0;
  v63 = 0;
  if ( BitValueInBitString < 0 )
    goto LABEL_64;
  v11 = a5;
  BitValueInBitString = LPA::Util::CheckSizeAgainstRange(
                          (LPA::Util *)(a5[1] - *a5),
                          3u,
                          3u,
                          (unsigned __int64)"LpaServiceLpd",
                          L"vEuiccSvn",
                          v50);
  if ( BitValueInBitString < 0 )
    goto LABEL_64;
  v65 = 0;
  v12 = a6;
  if ( *(_DWORD *)off_180151DE8((int)&v60, 0, (int)asn_DEF_EUICCInfo1, (int)&v65, *a6, a6[1] - *a6, 0) )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      v60 = "LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete";
      *(_QWORD *)v56 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)byte_180130971,
        v14,
        (_DWORD)v15,
        (__int64)v56,
        (__int64)&v60);
    }
  }
  else
  {
    v16 = *(LPA::Util **)(v65 + 144);
    if ( v16 )
    {
      v66 = 0;
      if ( (int)LPA::Util::GetBitValueInBitString(v16, (const struct BIT_STRING_s *)4, (unsigned int)&v66, v15) >= 0 )
        *(_BYTE *)(a1 + 128) = v66 != 0;
      v66 = 0;
      if ( (int)LPA::Util::GetBitValueInBitString(
                  *(LPA::Util **)(v18 + 144),
                  (const struct BIT_STRING_s *)0x10,
                  (unsigned int)&v66,
                  v17) >= 0 )
        *(_BYTE *)(a1 + 129) = v66 != 0;
      v66 = 0;
      BitValueInBitString = LPA::Util::GetBitValueInBitString(
                              *(LPA::Util **)(v20 + 144),
                              (const struct BIT_STRING_s *)0xF,
                              (unsigned int)&v66,
                              v19);
      if ( BitValueInBitString >= 0 )
        *(_BYTE *)(a1 + 130) = v66 != 0;
    }
    v21 = v65;
    if ( *(int *)(v65 + 48) > 0 )
    {
      do
      {
        v22 = *(_QWORD *)(*(_QWORD *)(v21 + 40) + 8LL * v8);
        v60 = (const char *)(*(_QWORD *)v22 + *(int *)(v22 + 8));
        if ( *(_QWORD *)(a1 + 832) == 0x666666666666666LL )
          std::_Xlength_error("list too long");
        v23 = *(_QWORD *)(a1 + 824);
        std::_List_node_emplace_op2<std::allocator<std::_List_node<std::vector<unsigned char>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::vector<unsigned char>,void *>>>(
          v56,
          a1 + 824,
          v22,
          &v60);
        ++*(_QWORD *)(a1 + 832);
        v24 = *(_QWORD **)(v23 + 8);
        *v57 = v23;
        v57[1] = v24;
        v25 = v57;
        v57 = 0;
        *(_QWORD *)(v23 + 8) = v25;
        *v24 = v25;
        std::_List_node_emplace_op2<std::allocator<std::_List_node<std::vector<unsigned char>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::vector<unsigned char>,void *>>>(v56);
        ++v8;
      }
      while ( v8 < *(_DWORD *)(v21 + 48) );
    }
    if ( *(_QWORD *)(a1 + 488) != *(_QWORD *)(a1 + 496) )
    {
      *(_OWORD *)v58 = 0;
      v59 = 0;
      v26 = *(int *)(v21 + 52);
      v60 = (const char *)v26;
      if ( v26 )
      {
        if ( v26 > 0xAAAAAAAAAAAAAAALL )
          std::vector<std::shared_ptr<pplx::details::_Task_impl<int>>>::_Xlength();
        std::vector<std::vector<unsigned char>>::_Reallocate<0>(v58, &v60);
      }
      v27 = 0;
      if ( *(int *)(v21 + 48) > 0 )
      {
        do
        {
          v28 = *(const void **)(a1 + 488);
          v14 = *(_QWORD *)(a1 + 496) - (_QWORD)v28;
          LODWORD(v16) = v27;
          v29 = *(const void ***)(*(_QWORD *)(v21 + 40) + 8LL * v27);
          if ( *((_DWORD *)v29 + 2) >= (int)v14 )
          {
            v30 = (char *)*v29;
            if ( !memcmp_0(*v29, v28, v14) )
            {
              v60 = &v30[*((int *)v29 + 2)];
              if ( v58[1] == v59 )
              {
                std::vector<std::vector<unsigned char>>::_Emplace_reallocate<unsigned char * &,unsigned char *>(
                  v58,
                  v58[1],
                  v29,
                  &v60);
              }
              else
              {
                std::vector<unsigned char>::vector<unsigned char>(v58[1], v30);
                v58[1] = (std::_Ref_count_base *)((char *)v58[1] + 24);
              }
            }
          }
          ++v27;
        }
        while ( v27 < *(_DWORD *)(v21 + 48) );
        v12 = a6;
      }
      if ( v58[0] == v58[1] )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v60 = "LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete";
          *(_QWORD *)v56 = "LpaServiceLpd";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)v16,
            (unsigned int)byte_1801309E1,
            v14,
            (_DWORD)v15,
            (__int64)v56,
            (__int64)&v60);
        }
        BitValueInBitString = -2147023728;
      }
      if ( BitValueInBitString >= 0 )
      {
        LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete_::_63_::LpaEuiccCiPkIdListForVerification::LpaEuiccCiPkIdListForVerification(
          v64,
          v58);
        v31 = v65;
        v32 = *(_OWORD *)(v65 + 40);
        v33 = *(_OWORD *)(v65 + 56);
        v34 = *(_OWORD *)(v65 + 72);
        *(_OWORD *)(v65 + 40) = v64[0];
        *(_OWORD *)(v31 + 56) = v64[1];
        *(_OWORD *)(v31 + 72) = v64[2];
        std::vector<unsigned char>::_Resize<std::_Value_init_tag>(&v62, v12[1] - *v12, &v66);
        v35 = (_QWORD *)der_encode_to_buffer(
                          (unsigned int)&v60,
                          (unsigned int)asn_DEF_EUICCInfo1,
                          v65,
                          v62,
                          *((_QWORD *)&v62 + 1) - v62);
        if ( *v35 == -1 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v60 = "LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete";
            *(_QWORD *)v56 = "LpaServiceLpd";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v36,
              (unsigned int)byte_1801309A9,
              v37,
              v38,
              (__int64)v56,
              (__int64)&v60);
          }
          BitValueInBitString = -2147024809;
        }
        else
        {
          std::vector<unsigned char>::_Resize<std::_Value_init_tag>(&v62, *v35, &v66);
        }
        v39 = v65;
        *(_OWORD *)(v65 + 40) = v32;
        *(_OWORD *)(v39 + 56) = v33;
        *(_OWORD *)(v39 + 72) = v34;
        LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete_::_63_::LpaEuiccCiPkIdListForVerification::_LpaEuiccCiPkIdListForVerification(v64);
      }
      if ( v58[0] )
      {
        std::_Destroy_range<std::allocator<std::vector<unsigned char>>>(v58[0], v58[1]);
        std::_Deallocate<16>(v58[0], (struct std::nothrow_t *)(8 * ((v59 - v58[0]) >> 3)));
      }
    }
  }
  if ( v65 )
    ((void (__fastcall *)(char **, __int64, _QWORD))off_180151DD0)(asn_DEF_EUICCInfo1, v65, 0);
  if ( BitValueInBitString < 0 )
    goto LABEL_64;
  LODWORD(v49) = (*v11)[2];
  swprintf_s<12>(a1 + 134, L"%u.%u.%u", **v11, (*v11)[1], v49);
  swprintf_s<22>(a1 + 182, L"%s%s", L"gsma/rsp/v", a1 + 134);
  std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 24, &v60);
  if ( v60 )
  {
    v40 = *((_QWORD *)v60 + 7);
    v41 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *, __int64))(*(_QWORD *)(v40 + 8) + 16LL);
    v42 = (_QWORD *)std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 8, v58);
    v43 = std::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>(
            (__int64 *)v56,
            v42);
    BitValueInBitString = v41(v40 + 8, a1 + 876, *(unsigned int *)(a1 + 1028), v43, a1 + 912);
    if ( v58[1] )
      std::_Ref_count_base::_Decref(v58[1]);
    if ( BitValueInBitString < 0 )
    {
      v44 = *(_DWORD *)(a1 + 1016);
      v45 = (_DWORD *)(a1 + 1020);
      if ( (v44 & 1) == 0 || !*v45 )
      {
        *(_DWORD *)(a1 + 1016) = v44 | 1;
        *v45 = 1;
      }
    }
  }
  else
  {
    BitValueInBitString = -2147418113;
  }
  if ( v61 )
    std::_Ref_count_base::_Decref(v61);
  if ( BitValueInBitString < 0 )
  {
LABEL_64:
    LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(a1 - 8, (unsigned int)BitValueInBitString, 0);
  }
  else
  {
    std::vector<std::shared_ptr<pplx::details::_Task_impl<int>>>::swap(a1 + 536, v12);
    std::vector<std::shared_ptr<pplx::details::_Task_impl<int>>>::swap(a1 + 560, &v62);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v66 = *(_DWORD *)(a1 + 912);
      LODWORD(v65) = 2;
      v60 = "WaitEs10bGetEuiccChallenge";
      v55 = *(_DWORD *)(a1 + 904);
      v54 = 2;
      *(_QWORD *)v56 = "LPA::Lpd::DownloadInstance::OnEs10bGetUiccInfo1Complete";
      v58[0] = (std::_Ref_count_base *)"LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        2,
        (unsigned int)byte_18013090D,
        v46,
        v47,
        (__int64)v58,
        (__int64)v56,
        (__int64)&v54,
        (__int64)&v55,
        (__int64)&v60,
        (__int64)&v65,
        (__int64)&v66);
    }
  }
  return std::vector<unsigned char>::_Tidy(&v62);
}

```

## disassembly

```asm
0x1800b39b0  mov     rax, rsp
0x1800b39b3  mov     [rax+18h], rbx
0x1800b39b7  push    rbp
0x1800b39b8  push    rsi
0x1800b39b9  push    rdi
0x1800b39ba  push    r12
0x1800b39bc  push    r13
0x1800b39be  push    r14
0x1800b39c0  push    r15
0x1800b39c2  lea     rbp, [rsp-50h]
0x1800b39c7  sub     rsp, 150h
0x1800b39ce  movaps  xmmword ptr [rax-48h], xmm6
0x1800b39d2  movaps  xmmword ptr [rax-58h], xmm7
0x1800b39d6  movaps  xmmword ptr [rax-68h], xmm8
0x1800b39db  mov     edi, edx
0x1800b39dd  mov     r14, rcx
0x1800b39e0  lea     rcx, aLpaLpdDownload_15; "LPA::Lpd::DownloadInstance::OnEs10bGetU"...
0x1800b39e7  lea     rbx, aLpaservicelpd; "LpaServiceLpd"
0x1800b39ee  xor     r15d, r15d
0x1800b39f1  mov     eax, cs:CallbackContext
0x1800b39f7  test    edx, edx
0x1800b39f9  js      short loc_1800B3A74
0x1800b39fb  cmp     eax, 4
0x1800b39fe  jbe     loc_1800B3B0A
0x1800b3a04  lea     rax, aOnes10bgetuicc; "OnEs10bGetUiccInfo1"
0x1800b3a0b  mov     [rsp+180h+var_108], rax
0x1800b3a10  mov     eax, [r14+388h]
0x1800b3a17  mov     [rsp+180h+var_120], eax
0x1800b3a1b  mov     [rsp+180h+var_11C], 2
0x1800b3a23  mov     [rbp+80h+var_F0], rbx
0x1800b3a27  lea     rax, [rbp+80h+arg_8]
0x1800b3a2e  mov     [rsp+180h+var_130], rax
0x1800b3a33  lea     rax, [rbp+80h+arg_0]
0x1800b3a3a  mov     [rsp+180h+var_138], rax
0x1800b3a3f  lea     rax, [rsp+180h+var_108]
0x1800b3a44  mov     [rsp+180h+var_140], rax
0x1800b3a49  lea     rax, [rsp+180h+var_120]
0x1800b3a4e  mov     [rsp+180h+var_148], rax
0x1800b3a53  lea     rax, [rsp+180h+var_11C]
0x1800b3a58  mov     [rsp+180h+var_150], rax
0x1800b3a5d  lea     rax, [rsp+180h+var_118]
0x1800b3a62  mov     [rsp+180h+var_158], rax
0x1800b3a67  lea     rax, [rbp+80h+var_F0]
0x1800b3a6b  lea     rdx, word_180130A86
0x1800b3a72  jmp     short loc_1800B3AEB
0x1800b3a74  cmp     eax, 2
0x1800b3a77  jbe     loc_1800B3B0A
0x1800b3a7d  lea     rax, aOnes10bgetuicc; "OnEs10bGetUiccInfo1"
0x1800b3a84  mov     [rbp+80h+var_F0], rax
0x1800b3a88  mov     eax, [r14+388h]
0x1800b3a8f  mov     [rsp+180h+var_11C], eax
0x1800b3a93  mov     [rsp+180h+var_120], 2
0x1800b3a9b  mov     [rsp+180h+var_108], rbx
0x1800b3aa0  lea     rax, [rbp+80h+arg_8]
0x1800b3aa7  mov     [rsp+180h+var_130], rax
0x1800b3aac  lea     rax, [rbp+80h+arg_0]
0x1800b3ab3  mov     [rsp+180h+var_138], rax
0x1800b3ab8  lea     rax, [rbp+80h+var_F0]
0x1800b3abc  mov     [rsp+180h+var_140], rax
0x1800b3ac1  lea     rax, [rsp+180h+var_11C]
0x1800b3ac6  mov     [rsp+180h+var_148], rax
0x1800b3acb  lea     rax, [rsp+180h+var_120]
0x1800b3ad0  mov     [rsp+180h+var_150], rax
0x1800b3ad5  lea     rax, [rsp+180h+var_118]
0x1800b3ada  mov     [rsp+180h+var_158], rax; unsigned __int16 *
0x1800b3adf  lea     rax, [rsp+180h+var_108]
0x1800b3ae4  lea     rdx, byte_180130A21
0x1800b3aeb  mov     [rsp+180h+var_160], rax
0x1800b3af0  mov     [rbp+80h+arg_8], edi
0x1800b3af6  mov     dword ptr [rbp+80h+arg_0], 5
0x1800b3b00  mov     qword ptr [rsp+180h+var_118], rcx
0x1800b3b05  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b3b0a  xorps   xmm0, xmm0
0x1800b3b0d  movdqu  [rbp+80h+var_D8], xmm0
0x1800b3b12  mov     [rbp+80h+var_C8], r15
0x1800b3b16  test    edi, edi
0x1800b3b18  js      loc_1800B41C6
0x1800b3b1e  mov     r13, [rbp+80h+arg_20]
0x1800b3b25  mov     rcx, [r13+8]
0x1800b3b29  sub     rcx, [r13+0]; this
0x1800b3b2d  lea     rax, aVeuiccsvn; "vEuiccSvn"
0x1800b3b34  mov     [rsp+180h+var_160], rax; char *
0x1800b3b39  mov     r9, rbx; unsigned __int64
0x1800b3b3c  mov     esi, 3
0x1800b3b41  mov     r8d, esi; unsigned __int64
0x1800b3b44  mov     edx, esi; unsigned __int64
0x1800b3b46  call    ?CheckSizeAgainstRange@Util@LPA@@YAJ_K00PEBDPEBG@Z; LPA::Util::CheckSizeAgainstRange(unsigned __int64,unsigned __int64,unsigned __int64,char const *,ushort const *)
0x1800b3b4b  mov     edi, eax
0x1800b3b4d  test    eax, eax
0x1800b3b4f  js      loc_1800B41C6
0x1800b3b55  mov     [rbp+80h+arg_0], r15
0x1800b3b5c  mov     r12, [rbp+80h+arg_28]
0x1800b3b63  mov     rdx, [r12]
0x1800b3b67  mov     rcx, [r12+8]
0x1800b3b6c  sub     rcx, rdx
0x1800b3b6f  mov     dword ptr [rsp+180h+var_150], r15d
0x1800b3b74  mov     [rsp+180h+var_158], rcx
0x1800b3b79  mov     [rsp+180h+var_160], rdx
0x1800b3b7e  lea     r9, [rbp+80h+arg_0]
0x1800b3b85  lea     r8, asn_DEF_EUICCInfo1
0x1800b3b8c  xor     edx, edx
0x1800b3b8e  lea     rcx, [rbp+80h+var_F0]
0x1800b3b92  mov     rax, cs:off_180151DE8
0x1800b3b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b9e  cmp     [rax], r15d
0x1800b3ba1  jnz     loc_1800B3F87
0x1800b3ba7  mov     r11, [rbp+80h+arg_0]
0x1800b3bae  mov     rcx, [r11+90h]; this
0x1800b3bb5  test    rcx, rcx
0x1800b3bb8  jz      loc_1800B3C53
0x1800b3bbe  mov     [rbp+80h+arg_8], r15d
0x1800b3bc5  lea     r8, [rbp+80h+arg_8]; unsigned int
0x1800b3bcc  lea     edx, [rsi+1]; struct BIT_STRING_s *
0x1800b3bcf  call    ?GetBitValueInBitString@Util@LPA@@YAJAEBUBIT_STRING_s@@KAEAK@Z; LPA::Util::GetBitValueInBitString(BIT_STRING_s const &,ulong,ulong &)
0x1800b3bd4  test    eax, eax
0x1800b3bd6  js      short loc_1800B3BE9
0x1800b3bd8  cmp     [rbp+80h+arg_8], r15d
0x1800b3bdf  setnz   al
0x1800b3be2  mov     [r14+80h], al
0x1800b3be9  mov     [rbp+80h+arg_8], r15d
0x1800b3bf0  lea     r8, [rbp+80h+arg_8]; unsigned int
0x1800b3bf7  mov     edx, 10h; struct BIT_STRING_s *
0x1800b3bfc  mov     rcx, [r11+90h]; this
0x1800b3c03  call    ?GetBitValueInBitString@Util@LPA@@YAJAEBUBIT_STRING_s@@KAEAK@Z; LPA::Util::GetBitValueInBitString(BIT_STRING_s const &,ulong,ulong &)
0x1800b3c08  test    eax, eax
0x1800b3c0a  js      short loc_1800B3C1D
0x1800b3c0c  cmp     [rbp+80h+arg_8], r15d
0x1800b3c13  setnz   al
0x1800b3c16  mov     [r14+81h], al
0x1800b3c1d  mov     [rbp+80h+arg_8], r15d
0x1800b3c24  lea     r8, [rbp+80h+arg_8]; unsigned int
0x1800b3c2b  mov     edx, 0Fh; struct BIT_STRING_s *
0x1800b3c30  mov     rcx, [r11+90h]; this
0x1800b3c37  call    ?GetBitValueInBitString@Util@LPA@@YAJAEBUBIT_STRING_s@@KAEAK@Z; LPA::Util::GetBitValueInBitString(BIT_STRING_s const &,ulong,ulong &)
0x1800b3c3c  mov     edi, eax
0x1800b3c3e  test    eax, eax
0x1800b3c40  js      short loc_1800B3C53
0x1800b3c42  cmp     [rbp+80h+arg_8], r15d
0x1800b3c49  setnz   al
0x1800b3c4c  mov     [r14+82h], al
0x1800b3c53  mov     rsi, [rbp+80h+arg_0]
0x1800b3c5a  cmp     dword ptr [rsi+30h], 0
0x1800b3c5e  jle     loc_1800B3CF1
0x1800b3c64  movsxd  rcx, r15d
0x1800b3c67  mov     rax, [rsi+28h]
0x1800b3c6b  mov     r8, [rax+rcx*8]
0x1800b3c6f  movsxd  rax, dword ptr [r8+8]
0x1800b3c73  add     rax, [r8]
0x1800b3c76  mov     [rbp+80h+var_F0], rax
0x1800b3c7a  mov     rax, 666666666666666h
0x1800b3c84  cmp     [r14+340h], rax
0x1800b3c8b  jz      loc_1800B3DAB
0x1800b3c91  lea     rdx, [r14+338h]
0x1800b3c98  mov     rbx, [rdx]
0x1800b3c9b  lea     r9, [rbp+80h+var_F0]
0x1800b3c9f  lea     rcx, [rsp+180h+var_118]
0x1800b3ca4  call    ??$?0AEAPEAEPEAE@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$vector@EV?$allocator@E@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$vector@EV?$allocator@E@std@@@std@@PEAX@std@@@1@AEAPEAE$$QEAPEAE@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::vector<uchar>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::vector<uchar>,void *>>>(std::allocator<std::_List_node<std::vector<uchar>,void *>> &,uchar * &,uchar * &&)
0x1800b3ca9  inc     qword ptr [r14+340h]
0x1800b3cb0  mov     rcx, [rbx+8]
0x1800b3cb4  mov     rax, [rsp+180h+var_110]
0x1800b3cb9  mov     [rax], rbx
0x1800b3cbc  mov     rax, [rsp+180h+var_110]
0x1800b3cc1  mov     [rax+8], rcx
0x1800b3cc5  mov     rax, [rsp+180h+var_110]
0x1800b3cca  mov     [rsp+180h+var_110], 0
0x1800b3cd3  mov     [rbx+8], rax
0x1800b3cd7  mov     [rcx], rax
0x1800b3cda  lea     rcx, [rsp+180h+var_118]
0x1800b3cdf  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$vector@EV?$allocator@E@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::vector<uchar>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::vector<uchar>,void *>>>(void)
0x1800b3ce4  inc     r15d
0x1800b3ce7  cmp     r15d, [rsi+30h]
0x1800b3ceb  jl      loc_1800B3C64
0x1800b3cf1  mov     rax, [r14+1F0h]
0x1800b3cf8  xor     r15d, r15d
0x1800b3cfb  cmp     [r14+1E8h], rax
0x1800b3d02  jz      loc_1800B3FC0
0x1800b3d08  xorps   xmm0, xmm0
0x1800b3d0b  movdqu  xmmword ptr [rsp+180h+var_108], xmm0
0x1800b3d11  mov     [rbp+80h+var_F8], r15
0x1800b3d15  movsxd  rax, dword ptr [rsi+34h]
0x1800b3d19  mov     [rbp+80h+var_F0], rax
0x1800b3d1d  test    rax, rax
0x1800b3d20  jz      short loc_1800B3D43
0x1800b3d22  mov     rcx, 0AAAAAAAAAAAAAAAh
0x1800b3d2c  cmp     rax, rcx
0x1800b3d2f  ja      loc_1800B4208
0x1800b3d35  lea     rdx, [rbp+80h+var_F0]
0x1800b3d39  lea     rcx, [rsp+180h+var_108]
0x1800b3d3e  call    ??$_Reallocate@$0A@@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::vector<uchar>>::_Reallocate<0>(unsigned __int64 &)
0x1800b3d43  mov     ebx, r15d
0x1800b3d46  cmp     [rsi+30h], r15d
0x1800b3d4a  jle     loc_1800B3DE2
0x1800b3d50  mov     rdx, [r14+1E8h]; Buf2
0x1800b3d57  mov     r8, [r14+1F0h]
0x1800b3d5e  sub     r8, rdx; Size
0x1800b3d61  movsxd  rcx, ebx
0x1800b3d64  mov     rax, [rsi+28h]
0x1800b3d68  mov     r12, [rax+rcx*8]
0x1800b3d6c  cmp     [r12+8], r8d
0x1800b3d71  jl      short loc_1800B3DCD
0x1800b3d73  mov     r15, [r12]
0x1800b3d77  mov     rcx, r15; Buf1
0x1800b3d7a  call    memcmp_0
0x1800b3d7f  test    eax, eax
0x1800b3d81  jnz     short loc_1800B3DCD
0x1800b3d83  movsxd  r8, dword ptr [r12+8]
0x1800b3d88  add     r8, r15
0x1800b3d8b  mov     [rbp+80h+var_F0], r8
0x1800b3d8f  mov     rax, [rbp+80h+var_108+8]
0x1800b3d93  cmp     rax, [rbp+80h+var_F8]
0x1800b3d97  jz      short loc_1800B3DB9
0x1800b3d99  mov     rdx, r15
0x1800b3d9c  mov     rcx, rax
0x1800b3d9f  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x1800b3da4  add     [rbp+80h+var_108+8], 18h
0x1800b3da9  jmp     short loc_1800B3DCD
0x1800b3dab  lea     rcx, aListTooLong; "list too long"
0x1800b3db2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b3db9  lea     r9, [rbp+80h+var_F0]
0x1800b3dbd  mov     r8, r12
0x1800b3dc0  mov     rdx, rax
0x1800b3dc3  lea     rcx, [rsp+180h+var_108]
0x1800b3dc8  call    ??$_Emplace_reallocate@AEAPEAEPEAE@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAPEAV?$vector@EV?$allocator@E@std@@@1@QEAV21@AEAPEAE$$QEAPEAE@Z; std::vector<std::vector<uchar>>::_Emplace_reallocate<uchar * &,uchar *>(std::vector<uchar> * const,uchar * &,uchar * &&)
0x1800b3dcd  inc     ebx
0x1800b3dcf  cmp     ebx, [rsi+30h]
0x1800b3dd2  jl      loc_1800B3D50
0x1800b3dd8  mov     r12, [rbp+80h+arg_28]
0x1800b3ddf  xor     r15d, r15d
0x1800b3de2  mov     rax, [rbp+80h+var_108+8]
0x1800b3de6  cmp     [rsp+180h+var_108], rax
0x1800b3deb  jnz     short loc_1800B3E45
0x1800b3ded  mov     eax, cs:CallbackContext
0x1800b3df3  cmp     eax, 2
0x1800b3df6  jbe     short loc_1800B3E30
0x1800b3df8  lea     rsi, aLpaLpdDownload_15; "LPA::Lpd::DownloadInstance::OnEs10bGetU"...
0x1800b3dff  mov     [rbp+80h+var_F0], rsi
0x1800b3e03  lea     rbx, aLpaservicelpd; "LpaServiceLpd"
0x1800b3e0a  mov     qword ptr [rsp+180h+var_118], rbx
0x1800b3e0f  lea     rax, [rbp+80h+var_F0]
0x1800b3e13  mov     [rsp+180h+var_158], rax
0x1800b3e18  lea     rax, [rsp+180h+var_118]
0x1800b3e1d  mov     [rsp+180h+var_160], rax
0x1800b3e22  lea     rdx, byte_1801309E1
0x1800b3e29  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800b3e2e  jmp     short loc_1800B3E3E
0x1800b3e30  lea     rbx, aLpaservicelpd; "LpaServiceLpd"
0x1800b3e37  lea     rsi, aLpaLpdDownload_15; "LPA::Lpd::DownloadInstance::OnEs10bGetU"...
0x1800b3e3e  mov     edi, 80070490h
0x1800b3e43  jmp     short loc_1800B3E53
0x1800b3e45  lea     rbx, aLpaservicelpd; "LpaServiceLpd"
0x1800b3e4c  lea     rsi, aLpaLpdDownload_15; "LPA::Lpd::DownloadInstance::OnEs10bGetU"...
0x1800b3e53  test    edi, edi
0x1800b3e55  js      loc_1800B3F47
0x1800b3e5b  lea     rdx, [rsp+180h+var_108]
0x1800b3e60  lea     rcx, [rbp+80h+var_C0]
0x1800b3e64  call    _LPA__Lpd__DownloadInstance__OnEs10bGetUiccInfo1Complete____63___LpaEuiccCiPkIdListForVerification__LpaEuiccCiPkIdListForVerification
0x1800b3e69  nop
0x1800b3e6a  mov     rax, [rbp+80h+arg_0]
0x1800b3e71  movups  xmm6, xmmword ptr [rax+28h]
0x1800b3e75  movups  xmm7, xmmword ptr [rax+38h]
0x1800b3e79  movups  xmm8, xmmword ptr [rax+48h]
0x1800b3e7e  movaps  xmm0, [rbp+80h+var_C0]
0x1800b3e82  movups  xmmword ptr [rax+28h], xmm0
0x1800b3e86  movaps  xmm1, [rbp+80h+var_B0]
0x1800b3e8a  movups  xmmword ptr [rax+38h], xmm1
0x1800b3e8e  movaps  xmm0, [rbp+80h+var_A0]
0x1800b3e92  movups  xmmword ptr [rax+48h], xmm0
0x1800b3e96  mov     rdx, [r12+8]
0x1800b3e9b  sub     rdx, [r12]
0x1800b3e9f  lea     r8, [rbp+80h+arg_8]
0x1800b3ea6  lea     rcx, [rbp+80h+var_D8]
0x1800b3eaa  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b3eaf  mov     r9, qword ptr [rbp+80h+var_D8]
0x1800b3eb3  mov     rax, qword ptr [rbp+80h+var_D8+8]
0x1800b3eb7  sub     rax, r9
0x1800b3eba  mov     [rsp+180h+var_160], rax
0x1800b3ebf  mov     r8, [rbp+80h+arg_0]
0x1800b3ec6  lea     rdx, asn_DEF_EUICCInfo1
0x1800b3ecd  lea     rcx, [rbp+80h+var_F0]
0x1800b3ed1  call    der_encode_to_buffer
0x1800b3ed6  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800b3eda  jz      short loc_1800B3EF1
0x1800b3edc  lea     r8, [rbp+80h+arg_8]
0x1800b3ee3  mov     rdx, [rax]
0x1800b3ee6  lea     rcx, [rbp+80h+var_D8]
0x1800b3eea  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b3eef  jmp     short loc_1800B3F29
0x1800b3ef1  mov     eax, cs:CallbackContext
0x1800b3ef7  cmp     eax, 2
0x1800b3efa  jbe     short loc_1800B3F24
0x1800b3efc  mov     [rbp+80h+var_F0], rsi
0x1800b3f00  mov     qword ptr [rsp+180h+var_118], rbx
0x1800b3f05  lea     rax, [rbp+80h+var_F0]
0x1800b3f09  mov     [rsp+180h+var_158], rax
0x1800b3f0e  lea     rax, [rsp+180h+var_118]
0x1800b3f13  mov     [rsp+180h+var_160], rax
0x1800b3f18  lea     rdx, byte_1801309A9
0x1800b3f1f  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800b3f24  mov     edi, 80070057h
0x1800b3f29  mov     rax, [rbp+80h+arg_0]
  ... truncated ...
```
