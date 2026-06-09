# LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800b57d4`
- end: `0x1800b6730`
- name: `?OnEs9OrEs11InitiateAuthentication@DownloadInstance@Lpd@LPA@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@5@11111@Z`
- size: `3932`
- prototype: ``
- caller_count: `1`
- callee_count: `39`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bd950`

## callees

- `0x180001010`
- `0x1800010f0`
- `0x180001f1c`
- `0x180005d6c`
- `0x180006730`
- `0x18000df90`
- `0x18000e46c`
- `0x18000ebd0`
- `0x18000ebf4`
- `0x18005cd64`
- `0x18005fc4c`
- `0x18005fe70`
- `0x18006540c`
- `0x18006543c`
- `0x1800709e4`
- `0x180071320`
- `0x1800715d0`
- `0x180071610`
- `0x180071994`
- `0x180071a8c`
- `0x18007516c`
- `0x180076d0c`
- `0x1800815e0`
- `0x1800839ac`
- `0x1800a2e30`
- `0x1800b02fc`
- `0x1800b03cc`
- `0x1800b062c`
- `0x1800b076c`
- `0x1800b1768`
- `0x1800b57d4`
- `0x1800b7288`
- `0x1800b74c8`
- `0x1800c3410`
- `0x1800d8710`
- `0x1800d91ec`
- `0x1800d9de8`
- `0x1800eab30`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5d6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5d6e`

## string_xrefs

- `0x1800b5852`: `LpaServiceLpd`
- `0x1800b5a7c`: `LpaServiceLpd`
- `0x1800b5b94`: `LpaServiceLpd`
- `0x1800b5bd0`: `LpaServiceLpd`
- `0x1800b5d9a`: `LpaServiceLpd`
- `0x1800b66d4`: `LpaServiceLpd`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication(
        __int64 a1,
        __int64 a2,
        const char *a3,
        __int64 a4,
        const char *a5,
        __int64 a6,
        __int64 *a7,
        _QWORD *a8)
{
  __int64 v8; // r15
  int v10; // edi
  __int64 *v11; // r13
  char v12; // r12
  const char *v13; // rdx
  int X509ExtensionValueFromAsn1CertVector; // esi
  char v15; // al
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rdi
  _QWORD *v20; // rax
  __int64 v21; // r15
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r15
  __int64 v25; // rbx
  __int64 v26; // rax
  bool v27; // zf
  __int64 v28; // rbx
  __int64 v29; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  int X509ExtensionValueFromAsn1Cert; // ebx
  int v37; // r8d
  int v38; // r9d
  __int64 *v39; // rdx
  __int64 v40; // rax
  bool v41; // bl
  HLOCAL v42; // rdi
  const void *v43; // rcx
  int v45; // r8d
  int v46; // r9d
  __int64 v47; // rdi
  __int64 v48; // rax
  unsigned int v49; // edi
  char v50; // r15
  char v51; // si
  char v52; // r12
  int GsmaTS26Version; // eax
  char v54; // r13
  _QWORD *v55; // rbx
  __int64 i; // rdx
  _QWORD *v57; // rax
  _QWORD *v58; // rax
  _QWORD *v59; // rax
  char v60; // r10
  _QWORD *v61; // rax
  char v62; // r11
  _QWORD *v63; // rax
  _QWORD *v64; // rax
  unsigned int v65; // r9d
  char *v66; // r8
  char *v67; // r8
  char *v68; // r8
  char *v69; // r8
  char *v70; // r8
  char *v71; // r8
  char v72; // r15
  __int64 v73; // rsi
  _QWORD *v74; // rdi
  __int64 v75; // r9
  __int64 v76; // rax
  unsigned int *v77; // r10
  unsigned int *j; // r9
  unsigned int v79; // ecx
  int v80; // r8d
  __int64 v81; // r8
  _QWORD *v82; // rcx
  __int64 v83; // rdx
  __int64 v84; // rax
  __int64 v85; // rcx
  unsigned int EuiccFormFactorType; // eax
  __int64 v87; // rdx
  __int64 v88; // r8
  _QWORD *v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rcx
  __int64 *v92; // r12
  int v93; // ecx
  int v94; // r8d
  int v95; // r9d
  _QWORD *v96; // r13
  int v97; // ecx
  int v98; // r8d
  int v99; // r9d
  __int64 v100; // rsi
  __int64 (__fastcall *v101)(__int64, __int64, _QWORD, HLOCAL *, const char **, __int64, __int64, const char *, const char *, __int64, __int64 *, _QWORD *, __int128 *, __int128 *, char, __int64 *, __int64); // rdi
  _QWORD *v102; // rax
  __int64 *v103; // rax
  const char **v104; // r8
  int v105; // ecx
  unsigned int *v106; // [rsp+20h] [rbp-F0h]
  __int64 v107; // [rsp+28h] [rbp-E8h]
  char v108; // [rsp+90h] [rbp-80h] BYREF
  char v109; // [rsp+91h] [rbp-7Fh]
  HLOCAL hMem; // [rsp+98h] [rbp-78h] BYREF
  char v111; // [rsp+A0h] [rbp-70h]
  char v112[3]; // [rsp+A1h] [rbp-6Fh] BYREF
  unsigned int v113; // [rsp+A4h] [rbp-6Ch] BYREF
  int v114; // [rsp+A8h] [rbp-68h] BYREF
  char v115; // [rsp+ACh] [rbp-64h] BYREF
  bool v116; // [rsp+ADh] [rbp-63h]
  unsigned int v117[2]; // [rsp+B0h] [rbp-60h] BYREF
  const char *v118; // [rsp+B8h] [rbp-58h] BYREF
  const char *v119; // [rsp+C0h] [rbp-50h] BYREF
  const char *v120; // [rsp+C8h] [rbp-48h] BYREF
  __int16 v121; // [rsp+D0h] [rbp-40h]
  __int64 v122; // [rsp+D8h] [rbp-38h] BYREF
  _QWORD *v123; // [rsp+E0h] [rbp-30h] BYREF
  const char *v124; // [rsp+E8h] [rbp-28h] BYREF
  const char *v125; // [rsp+F0h] [rbp-20h] BYREF
  __int64 *v126; // [rsp+F8h] [rbp-18h] BYREF
  __int16 v127; // [rsp+100h] [rbp-10h]
  const char *v128; // [rsp+108h] [rbp-8h] BYREF
  std::_Ref_count_base *v129; // [rsp+110h] [rbp+0h]
  std::_Ref_count_base *v130[2]; // [rsp+118h] [rbp+8h] BYREF
  __int64 v131; // [rsp+128h] [rbp+18h]
  __int64 v132; // [rsp+130h] [rbp+20h]
  __int64 v133; // [rsp+138h] [rbp+28h]
  __int128 v134; // [rsp+140h] [rbp+30h] BYREF
  __int64 v135; // [rsp+150h] [rbp+40h]
  __int128 v136; // [rsp+158h] [rbp+48h] BYREF
  __int64 v137; // [rsp+168h] [rbp+58h]
  __int128 v138; // [rsp+170h] [rbp+60h] BYREF
  __int64 v139; // [rsp+180h] [rbp+70h]
  __int64 v140; // [rsp+188h] [rbp+78h]

  v132 = a4;
  v124 = a3;
  v8 = a2;
  v122 = a2;
  v125 = a5;
  v10 = a6;
  v133 = a6;
  v11 = a7;
  v126 = a7;
  v123 = a8;
  v12 = 0;
  v13 = "LpaServiceLpd";
  if ( (unsigned int)CallbackContext > 4 )
  {
    v114 = 0;
    v113 = 6;
    v119 = "OnEs9OrEs11InitiateAuthentication";
    LODWORD(hMem) = *(_DWORD *)(a1 + 912);
    v117[0] = 2;
    v120 = "LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication";
    v118 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)"LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication",
      (unsigned int)byte_180131BD5,
      (_DWORD)a3,
      a4,
      (__int64)&v118,
      (__int64)&v120,
      (__int64)v117,
      (__int64)&hMem,
      (__int64)&v119,
      (__int64)&v113,
      (__int64)&v114);
  }
  X509ExtensionValueFromAsn1CertVector = 0;
  std::shared_ptr<pplx::cancellation_token_source>::reset(a1 + 104, v13);
  if ( *(_BYTE *)(a1 + 120) )
  {
    X509ExtensionValueFromAsn1CertVector = -2147467260;
    if ( (*(_BYTE *)(a1 + 1024) & 1) == 0 || !*(_DWORD *)(a1 + 1028) )
    {
      *(_DWORD *)(a1 + 1024) |= 1u;
      *(_DWORD *)(a1 + 1028) = 9;
    }
  }
  v116 = LPA::Lpd::DownloadInstance::m_fEnableLpaV3Support;
  if ( !LPA::Lpd::DownloadInstance::m_fEnableLpaV3Support || (v15 = 1, !*(_BYTE *)(a1 + 136)) )
    v15 = 0;
  v109 = v15;
  v136 = 0;
  v137 = 0;
  if ( X509ExtensionValueFromAsn1CertVector < 0 )
    goto LABEL_64;
  if ( *(_QWORD *)(a1 + 352) || v15 )
  {
    hMem = 0;
    v117[0] = 0;
    X509ExtensionValueFromAsn1CertVector = LPA::Lpd::DownloadInstance::GetX509ExtensionValueFromAsn1CertVector(
                                             "2.5.29.17",
                                             (char *)0xC,
                                             v117);
    if ( X509ExtensionValueFromAsn1CertVector >= 0 )
    {
      v19 = 0;
      v20 = hMem;
      if ( *(_DWORD *)hMem )
      {
        while ( 1 )
        {
          v21 = v20[1];
          if ( *(_DWORD *)(v21 + 24 * v19) == 9 )
          {
            v22 = *(_QWORD *)(v21 + 24 * v19 + 8);
            if ( v22 )
            {
              v23 = -1;
              do
                ++v23;
              while ( *(_BYTE *)(v22 + v23) );
              std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(&v136, v22, v23);
              v24 = *(_QWORD *)(v21 + 24 * v19 + 8);
              v25 = -1;
              do
                ++v25;
              while ( *(_BYTE *)(v24 + v25) );
              v26 = std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 336);
              v27 = (unsigned int)std::_Traits_compare<std::char_traits<char>>(v26, *(_QWORD *)(a1 + 352), v24, v25) == 0;
              v20 = hMem;
              if ( v27 )
                break;
            }
          }
          v19 = (unsigned int)(v19 + 1);
          if ( (unsigned int)v19 >= *(_DWORD *)v20 )
            goto LABEL_25;
        }
        v12 = 1;
LABEL_25:
        v11 = v126;
        v8 = v122;
      }
      LocalFree(v20);
      hMem = 0;
      v10 = v133;
    }
    if ( !*(_QWORD *)(a1 + 352) || v12 )
    {
      if ( X509ExtensionValueFromAsn1CertVector >= 0 )
        goto LABEL_34;
    }
    else
    {
      X509ExtensionValueFromAsn1CertVector = -2147418113;
    }
    if ( (unsigned int)CallbackContext > 2 )
    {
      v118 = "2.5.29.17";
      v120 = "LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication";
      v119 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (unsigned int)byte_180131B79,
        v17,
        v18,
        (__int64)&v119,
        (__int64)&v120,
        (__int64)&v118);
    }
  }
  if ( X509ExtensionValueFromAsn1CertVector < 0 )
  {
LABEL_64:
    if ( (*(_BYTE *)(a1 + 1024) & 1) == 0 || !*(_DWORD *)(a1 + 1028) )
    {
      *(_DWORD *)(a1 + 1024) |= 1u;
      *(_DWORD *)(a1 + 1028) = 1;
    }
    LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(a1, X509ExtensionValueFromAsn1CertVector, 0);
    return std::vector<unsigned char>::_Tidy(&v136);
  }
LABEL_34:
  v138 = 0;
  v139 = 0;
  v140 = 15;
  LOBYTE(v138) = 0;
  v108 = 0;
  *(_OWORD *)v130 = 0;
  v131 = 0;
  v134 = 0;
  v135 = 0;
  X509ExtensionValueFromAsn1CertVector = LPA::Lpd::DownloadInstance::ParseServerSigned1(
                                           v10,
                                           (unsigned int)&v138,
                                           (unsigned int)&v108,
                                           (unsigned int)v130,
                                           (__int64)&v134);
  if ( X509ExtensionValueFromAsn1CertVector >= 0 )
  {
    if ( (std::_Ref_count_base *)(v130[1] - v130[0]) > (std::_Ref_count_base *)2 )
    {
      LODWORD(v107) = *((unsigned __int8 *)v130[0] + 2);
      LODWORD(v106) = *((unsigned __int8 *)v130[0] + 1);
      StringCchPrintfW((unsigned __int16 *)(a1 + 166), 0xCu, L"%u.%u.%u", *(unsigned __int8 *)v130[0], v106, v107);
    }
    v28 = std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 240);
    v29 = std::_String_val<std::_Simple_types<char>>::_Myptr(&v138);
    if ( (unsigned int)std::_Traits_compare<std::char_traits<char>>(v28, *(_QWORD *)(a1 + 256), v29, v139) )
    {
      X509ExtensionValueFromAsn1CertVector = -2147418113;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v118 = "LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication";
        v120 = "LpaServiceLpd";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v30,
          (unsigned int)&unk_180131B40,
          v31,
          v32,
          (__int64)&v120,
          (__int64)&v118);
      }
    }
    else
    {
      *(_BYTE *)(a1 + 140) = v108;
    }
  }
  std::vector<unsigned char>::_Tidy(&v134);
  std::vector<unsigned char>::_Tidy(v130);
  std::string::_Tidy_deallocate(&v138);
  if ( X509ExtensionValueFromAsn1CertVector < 0 )
    goto LABEL_64;
  if ( *(_QWORD *)(a1 + 496) == *(_QWORD *)(a1 + 504) )
    goto LABEL_69;
  hMem = 0;
  v113 = 0;
  v33 = *v11;
  v34 = v11[1];
  if ( *v11 == v34 )
  {
    X509ExtensionValueFromAsn1Cert = LPA::Lpd::DownloadInstance::GetX509ExtensionValueFromAsn1CertVector(
                                       "2.5.29.35",
                                       (char *)0x1F,
                                       &v113);
    goto LABEL_56;
  }
  *(_QWORD *)v117 = 0;
  if ( *(_DWORD *)off_1801540E8((int)v130, 0, (int)asn_DEF_CertificateChain, (int)v117, v33, v34 - v33, 0) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v118 = "LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication";
      v120 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v35,
        (unsigned int)&unk_180131B08,
        v37,
        v38,
        (__int64)&v120,
        (__int64)&v118);
    }
    X509ExtensionValueFromAsn1Cert = -2147024809;
    goto LABEL_49;
  }
  v39 = *(__int64 **)v117;
  v35 = **(_QWORD **)v117;
  if ( **(_QWORD **)v117 )
  {
    v40 = *(int *)(*(_QWORD *)v117 + 8LL);
    if ( (int)v40 >= 1 )
    {
      X509ExtensionValueFromAsn1Cert = LPA::Lpd::DownloadInstance::GetX509ExtensionValueFromAsn1Cert(
                                         "2.5.29.35",
                                         (const char *)0x1F,
                                         *(const struct Certificate **)(v35 + 8 * v40 - 8),
                                         &hMem,
                                         &v113);
LABEL_49:
      v39 = *(__int64 **)v117;
      goto LABEL_54;
    }
  }
  X509ExtensionValueFromAsn1Cert = -2147418113;
LABEL_54:
  if ( v39 )
    ((void (__fastcall *)(char **, __int64 *, _QWORD))off_1801540D0)(asn_DEF_CertificateChain, v39, 0);
LABEL_56:
  if ( X509ExtensionValueFromAsn1Cert < 0 )
    goto LABEL_61;
  v41 = 0;
  v42 = hMem;
  v43 = (const void *)*((_QWORD *)hMem + 1);
  if ( v43 && *(_DWORD *)hMem >= (unsigned int)(*(_DWORD *)(a1 + 504) - *(_DWORD *)(a1 + 496)) )
    v41 = memcmp_0(v43, *(const void **)(a1 + 496), *(_QWORD *)(a1 + 504) - *(_QWORD *)(a1 + 496)) == 0;
  LocalFree(v42);
  hMem = 0;
  if ( !v41 )
  {
LABEL_61:
    if ( (unsigned int)CallbackContext > 2 )
    {
      v118 = "2.5.29.35";
      v120 = "LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication";
      v119 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v35,
        (unsigned int)&dword_180131AA4,
        v37,
        v38,
        (__int64)&v119,
        (__int64)&v120,
        (__int64)&v118);
    }
    X509ExtensionValueFromAsn1CertVector = -2147418113;
    goto LABEL_64;
  }
LABEL_69:
  std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 32, v130);
  v128 = (const char *)v130[0];
  if ( v130[0] )
  {
    v134 = 0;
    v135 = 0;
    std::wstring::operator=(a1 + 432, v8);
    if ( *(_QWORD *)(a1 + 320) )
    {
      v47 = std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 304);
      v48 = std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 304);
      std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(&v134, v47, v48 + *(_QWORD *)(a1 + 320) - v47);
    }
    X509ExtensionValueFromAsn1CertVector = LPA::Lpd::DownloadInstance::ParseTransactionIdString(a1 + 432, a1 + 520);
    if ( X509ExtensionValueFromAsn1CertVector >= 0 )
    {
      v49 = 0;
      v113 = 0;
      v114 = 0;
      v108 = 0;
      v50 = *(_BYTE *)(a1 + 1044);
      v51 = *(_BYTE *)(a1 + 1046);
      v52 = *(_BYTE *)(a1 + 1048);
      v115 = *(_BYTE *)(a1 + 1050);
      v112[0] = *(_BYTE *)(a1 + 1052);
      v111 = *(_BYTE *)(a1 + 1054);
      GsmaTS26Version = NfcUtilsGetGsmaTS26Version(&v113, &v114, &v108);
      v54 = v108;
      if ( GsmaTS26Version < 0 )
        v54 = 0;
      v55 = operator new(0x250u);
      memset_0(v55, 0, 0x220u);
      v55[68] = 0;
      v55[69] = 0;
      v55[70] = 0;
      v55[71] = 0;
      v55[72] = 0;
      v55[73] = 0;
      hMem = v55;
      i = 1;
      if ( v50 )
      {
        v49 = 1;
        *v55 = v55 + 18;
      }
      if ( v51 )
      {
        v57 = &v55[5 * v49++ + 18];
        v55[1] = v57;
      }
      if ( v52 )
      {
        v58 = &v55[5 * v49++ + 18];
        v55[5] = v58;
      }
      if ( v54 )
      {
        v59 = &v55[5 * v49++ + 18];
        v55[6] = v59;
      }
      v60 = v115;
      if ( v115 )
      {
        v61 = &v55[5 * v49++ + 18];
        v55[8] = v61;
      }
      v62 = v112[0];
      if ( v112[0] )
      {
        v63 = &v55[5 * v49++ + 18];
        v55[9] = v63;
      }
      if ( v111 )
      {
        v64 = &v55[5 * v49++ + 18];
        v55[10] = v64;
      }
      if ( v109 )
      {
        v55[11] = &v55[5 * v49 + 18];
        v55[12] = v55 + 58;
        v55[13] = v55 + 63;
      }
      v65 = 0;
      if ( v50 )
      {
        *(_DWORD *)(*v55 + 8LL) = 3;
        v65 = 1;
        *(_QWORD *)*v55 = (char *)hMem + 520;
        for ( i = 0; i != 2; ++i )
          *(_BYTE *)(i + *(_QWORD *)*v55) = *(_BYTE *)(i + a1 + 1044);
      }
      if ( v51 )
      {
        *(_DWORD *)(v55[1] + 8LL) = 3;
        v66 = (char *)hMem + 2 * v65 + v65 + 520;
        ++v65;
        *(_QWORD *)v55[1] = v66;
        for ( i = 0; i != 2; ++i )
          *(_BYTE *)(i + *(_QWORD *)v55[1]) = *(_BYTE *)(i + a1 + 1046);
      }
      if ( v52 )
      {
        *(_DWORD *)(v55[5] + 8LL) = 3;
        v67 = (char *)hMem + 2 * v65 + v65 + 520;
        ++v65;
        *(_QWORD *)v55[5] = v67;
        for ( i = 0; i != 2; ++i )
          *(_BYTE *)(i + *(_QWORD *)v55[5]) = *(_BYTE *)(i + a1 + 1048);
      }
      if ( v54 )
      {
        *(_DWORD *)(v55[6] + 8LL) = 3;
        i = v65;
        v68 = (char *)hMem + 2 * v65 + v65 + 520;
        ++v65;
        *(_QWORD *)v55[6] = v68;
        **(_BYTE **)v55[6] = v113;
        *(_BYTE *)(*(_QWORD *)v55[6] + 1LL) = v114;
      }
      if ( v60 )
      {
        *(_DWORD *)(v55[8] + 8LL) = 3;
        v69 = (char *)hMem + 2 * v65 + v65 + 520;
        ++v65;
        *(_QWORD *)v55[8] = v69;
        for ( i = 0; i != 2; ++i )
          *(_BYTE *)(i + *(_QWORD *)v55[8]) = *(_BYTE *)(a1 + i + 1050);
      }
      if ( v62 )
      {
        *(_DWORD *)(v55[9] + 8LL) = 3;
        v70 = (char *)hMem + 2 * v65 + v65 + 520;
        ++v65;
        *(_QWORD *)v55[9] = v70;
        for ( i = 0; i != 2; ++i )
          *(_BYTE *)(i + *(_QWORD *)v55[9]) = *(_BYTE *)(i + a1 + 1052);
      }
      if ( v111 )
      {
        *(_DWORD *)(v55[10] + 8LL) = 3;
        v71 = (char *)hMem + 2 * v65 + v65 + 520;
        ++v65;
        *(_QWORD *)v55[10] = v71;
        for ( i = 0; i != 2; ++i )
          *(_BYTE *)(i + *(_QWORD *)v55[10]) = *(_BYTE *)(i + a1 + 1054);
      }
      v72 = v109;
      if ( v109 )
      {
        *(_DWORD *)(v55[11] + 8LL) = 3;
        *(_QWORD *)v55[11] = (char *)hMem + 2 * v65 + v65 + 520;
        **(_BYTE **)v55[11] = 3;
        *(_BYTE *)(*(_QWORD *)v55[11] + 1LL) = 1;
        v114 = 4;
        v73 = v55[12];
        v74 = hMem;
        std::vector<unsigned long>::vector<unsigned long>(&v138, &v114, &v115);
        LOBYTE(v75) = 0;
        std::_Sort_unchecked<unsigned long *,std::less<void>>(
          v138,
          *((_QWORD *)&v138 + 1),
          (__int64)(*((_QWORD *)&v138 + 1) - v138) >> 2,
          v75);
        v76 = v74[71];
        if ( v76 != v74[72] )
          v74[72] = v76;
        std::vector<unsigned char>::_Resize<std::_Value_init_tag>(
          v74 + 71,
          (unsigned int)((*(_DWORD *)(*((_QWORD *)&v138 + 1) - 4LL) >> 3) + 1),
          v112);
        v77 = (unsigned int *)*((_QWORD *)&v138 + 1);
        for ( j = (unsigned int *)v138; j != v77; ++j )
        {
          v79 = *j;
          v80 = 7 - (*j & 7);
          *(_DWORD *)(v73 + 12) = v80;
          *(_BYTE *)(((unsigned __int64)v79 >> 3) + v74[71]) |= 1 << v80;
        }
        std::vector<unsigned long>::_Tidy(&v138);
        v81 = v55[12];
        v82 = hMem;
        *(_DWORD *)(v81 + 8) = *((_DWORD *)hMem + 144) - *((_DWORD *)hMem + 142);
        v83 = v82[71];
        v84 = v82[72];
        v85 = 0;
        if ( v84 != v83 )
          v85 = v83;
        *(_QWORD *)v81 = v85;
        EuiccFormFactorType = LPA::Lpd::DownloadInstance::GetEuiccFormFactorType(a1);
        LPA::Util::NativeToAsn1IntegerVector<enum EuiccFormFactorType>(EuiccFormFactorType, v87, (char *)hMem + 544);
        v88 = v55[13];
        v89 = hMem;
        *(_DWORD *)(v88 + 8) = *((_DWORD *)hMem + 138) - *((_DWORD *)hMem + 136);
        i = v89[68];
        v90 = v89[69];
        v91 = 0;
        if ( v90 != i )
          v91 = i;
        *(_QWORD *)v88 = v91;
      }
      v92 = v126;
      if ( v126[1] != *v126
        && !*(_BYTE *)(a1 + 137)
        && (unsigned int)dword_18015A5E0 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18015A5E0, 0x800000000000LL) )
      {
        v126 = (__int64 *)(a1 + 166);
        v127 = 24;
        *(_QWORD *)&v138 = a1 + 142;
        WORD4(v138) = 24;
        v117[0] = 16;
        v118 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 240);
        v120 = (const char *)16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
          v93,
          (unsigned int)byte_180131A39,
          v94,
          v95,
          (__int64)&v120,
          (__int64)&v118,
          (__int64)v117,
          (__int64)&v138,
          (__int64)&v126);
      }
      v96 = v123;
      if ( v123[1] != *v123
        && !*(_BYTE *)(a1 + 138)
        && (unsigned int)dword_18015A5E0 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18015A5E0, 0x800000000000LL) )
      {
        *(_QWORD *)&v138 = a1 + 166;
        WORD4(v138) = 24;
        v120 = (const char *)(a1 + 142);
        v121 = 24;
        v117[0] = 15;
        v123 = (_QWORD *)std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 240);
        v118 = (const char *)16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
          v97,
          (unsigned int)&word_1801319CE,
          v98,
          v99,
          (__int64)&v118,
          (__int64)&v123,
          (__int64)v117,
          (__int64)&v120,
          (__int64)&v138);
      }
      LPA::Lpd::DownloadInstance::GetLpaRspCapability(&v119, i);
      std::make_unique<LPA::LpaRspCapability,,0>(&v122);
      v100 = *((_QWORD *)v128 + 7);
      v101 = **(__int64 (__fastcall ***)(__int64, __int64, _QWORD, HLOCAL *, const char **, __int64, __int64, const char *, const char *, __int64, __int64 *, _QWORD *, __int128 *, __int128 *, char, __int64 *, __int64))(v100 + 8);
      v102 = (_QWORD *)std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 16, &v128);
      v103 = std::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>(
               (__int64 *)&v138,
               v102);
      v104 = (const char **)&v122;
      if ( v116 )
        v104 = &v119;
      X509ExtensionValueFromAsn1CertVector = v101(
                                               v100 + 8,
                                               a1 + 884,
                                               *(unsigned int *)(a1 + 1036),
                                               &hMem,
                                               v104,
                                               a1 + 784,
                                               v133,
                                               v125,
                                               v124,
                                               v132,
                                               v92,
                                               v96,
                                               &v134,
                                               &v136,
                                               v72,
                                               v103,
                                               a1 + 920);
      if ( v129 )
        std::_Ref_count_base::_Decref(v129);
      std::unique_ptr<LPA::LpaRspCapability>::~unique_ptr<LPA::LpaRspCapability>(&v122);
      std::unique_ptr<LPA::LpaRspCapability>::~unique_ptr<LPA::LpaRspCapability>(&v119);
      std::unique_ptr<LPA::LpaDeviceCapabilities>::~unique_ptr<LPA::LpaDeviceCapabilities>(&hMem);
    }
    std::vector<unsigned char>::_Tidy(&v134);
  }
  else
  {
    X509ExtensionValueFromAsn1CertVector = -2147418113;
  }
  v105 = (int)v130[1];
  if ( v130[1] )
    std::_Ref_count_base::_Decref(v130[1]);
  if ( X509ExtensionValueFromAsn1CertVector < 0 )
    goto LABEL_64;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v117[0] = *(_DWORD *)(a1 + 920);
    LODWORD(hMem) = 5;
    v125 = "WaitEs10bAuthenticateServer";
    v114 = *(_DWORD *)(a1 + 912);
    v113 = 2;
    v124 = "LPA::Lpd::DownloadInstance::OnEs9OrEs11InitiateAuthentication";
    v128 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v105,
      (unsigned int)word_18013196A,
      v45,
      v46,
      (__int64)&v128,
      (__int64)&v124,
      (__int64)&v113,
      (__int64)&v114,
      (__int64)&v125,
      (__int64)&hMem,
      (__int64)v117);
  }
  return std::vector<unsigned char>::_Tidy(&v136);
}

```

## disassembly

```asm
0x1800b57d4  push    rbp
0x1800b57d6  push    rbx
0x1800b57d7  push    rsi
0x1800b57d8  push    rdi
0x1800b57d9  push    r12
0x1800b57db  push    r13
0x1800b57dd  push    r14
0x1800b57df  push    r15
0x1800b57e1  lea     rbp, [rsp-98h]
0x1800b57e9  sub     rsp, 1A8h
0x1800b57f0  mov     rax, cs:__security_cookie
0x1800b57f7  xor     rax, rsp
0x1800b57fa  mov     [rbp+0D0h+var_50], rax
0x1800b5801  mov     rbx, r9
0x1800b5804  mov     [rbp+0D0h+var_B0], rbx
0x1800b5808  mov     [rbp+0D0h+var_F8], r8
0x1800b580c  mov     r15, rdx
0x1800b580f  mov     [rbp+0D0h+var_108], rdx
0x1800b5813  mov     r14, rcx
0x1800b5816  mov     rax, [rbp+0D0h+arg_20]
0x1800b581d  mov     [rbp+0D0h+var_F0], rax
0x1800b5821  mov     rdi, [rbp+0D0h+arg_28]
0x1800b5828  mov     [rbp+0D0h+var_A8], rdi
0x1800b582c  mov     r13, [rbp+0D0h+arg_30]
0x1800b5833  mov     [rbp+0D0h+var_E8], r13
0x1800b5837  mov     rax, [rbp+0D0h+arg_38]
0x1800b583e  mov     [rbp+0D0h+var_100], rax
0x1800b5842  xor     r12d, r12d
0x1800b5845  mov     eax, cs:CallbackContext
0x1800b584b  lea     rcx, aLpaLpdDownload_19; "LPA::Lpd::DownloadInstance::OnEs9OrEs11"...
0x1800b5852  lea     rdx, aLpaservicelpd; "LpaServiceLpd"
0x1800b5859  cmp     eax, 4
0x1800b585c  jbe     short loc_1800B58D8
0x1800b585e  mov     [rbp+0D0h+var_138], r12d
0x1800b5862  mov     [rbp+0D0h+var_13C], 6
0x1800b5869  lea     rax, aOnes9ores11ini; "OnEs9OrEs11InitiateAuthentication"
0x1800b5870  mov     [rbp+0D0h+var_120], rax
0x1800b5874  mov     eax, [r14+390h]
0x1800b587b  mov     dword ptr [rbp+0D0h+hMem], eax
0x1800b587e  mov     [rbp+0D0h+var_130], 2
0x1800b5885  mov     [rbp+0D0h+var_118], rcx
0x1800b5889  mov     [rbp+0D0h+var_128], rdx
0x1800b588d  lea     rax, [rbp+0D0h+var_138]
0x1800b5891  mov     [rsp+1E0h+var_190], rax
0x1800b5896  lea     rax, [rbp+0D0h+var_13C]
0x1800b589a  mov     [rsp+1E0h+var_198], rax
0x1800b589f  lea     rax, [rbp+0D0h+var_120]
0x1800b58a3  mov     [rsp+1E0h+var_1A0], rax
0x1800b58a8  lea     rax, [rbp+0D0h+hMem]
0x1800b58ac  mov     [rsp+1E0h+var_1A8], rax
0x1800b58b1  lea     rax, [rbp+0D0h+var_130]
0x1800b58b5  mov     [rsp+1E0h+var_1B0], rax
0x1800b58ba  lea     rax, [rbp+0D0h+var_118]
0x1800b58be  mov     [rsp+1E0h+var_1B8], rax
0x1800b58c3  lea     rax, [rbp+0D0h+var_128]
0x1800b58c7  mov     [rsp+1E0h+var_1C0], rax
0x1800b58cc  lea     rdx, byte_180131BD5
0x1800b58d3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b58d8  mov     esi, r12d
0x1800b58db  lea     rcx, [r14+68h]
0x1800b58df  call    ?reset@?$shared_ptr@Vcancellation_token_source@pplx@@@std@@QEAAXXZ; std::shared_ptr<pplx::cancellation_token_source>::reset(void)
0x1800b58e4  mov     edx, 1
0x1800b58e9  cmp     [r14+78h], r12b
0x1800b58ed  jz      short loc_1800B5920
0x1800b58ef  mov     esi, 80004004h
0x1800b58f4  mov     ecx, [r14+400h]
0x1800b58fb  mov     eax, ecx
0x1800b58fd  and     eax, edx
0x1800b58ff  test    al, al
0x1800b5901  jz      short loc_1800B590C
0x1800b5903  cmp     [r14+404h], r12d
0x1800b590a  jnz     short loc_1800B5920
0x1800b590c  or      ecx, edx
0x1800b590e  mov     [r14+400h], ecx
0x1800b5915  mov     dword ptr [r14+404h], 9
0x1800b5920  mov     al, cs:?m_fEnableLpaV3Support@DownloadInstance@Lpd@LPA@@0_NA; bool LPA::Lpd::DownloadInstance::m_fEnableLpaV3Support
0x1800b5926  mov     [rbp+0D0h+var_133], al
0x1800b5929  test    al, al
0x1800b592b  jz      short loc_1800B5938
0x1800b592d  cmp     [r14+88h], r12b
0x1800b5934  mov     al, dl
0x1800b5936  jnz     short loc_1800B593B
0x1800b5938  mov     al, r12b
0x1800b593b  mov     [rbp+0D0h+var_14F], al
0x1800b593e  xorps   xmm0, xmm0
0x1800b5941  movdqu  [rbp+0D0h+var_88], xmm0
0x1800b5946  mov     [rbp+0D0h+var_78], r12
0x1800b594a  test    esi, esi
0x1800b594c  js      loc_1800B5DD1
0x1800b5952  cmp     [r14+160h], r12
0x1800b5959  jnz     short loc_1800B5963
0x1800b595b  test    al, al
0x1800b595d  jz      loc_1800B5AAE
0x1800b5963  mov     [rbp+0D0h+hMem], r12
0x1800b5967  mov     [rbp+0D0h+var_130], r12d
0x1800b596b  lea     rax, [rbp+0D0h+var_130]
0x1800b596f  mov     [rsp+1E0h+var_1C0], rax; unsigned int *
0x1800b5974  lea     r9, [rbp+0D0h+hMem]
0x1800b5978  mov     r8, rbx
0x1800b597b  mov     edx, 0Ch; char *
0x1800b5980  lea     rbx, a252917; "2.5.29.17"
0x1800b5987  mov     rcx, rbx; char *
0x1800b598a  call    ?GetX509ExtensionValueFromAsn1CertVector@DownloadInstance@Lpd@LPA@@CAJPEBD0AEBV?$vector@EV?$allocator@E@std@@@std@@PEAPEAXAEAK@Z; LPA::Lpd::DownloadInstance::GetX509ExtensionValueFromAsn1CertVector(char const *,char const *,std::vector<uchar> const &,void * *,ulong &)
0x1800b598f  mov     esi, eax
0x1800b5991  test    eax, eax
0x1800b5993  js      loc_1800B5A42
0x1800b5999  xor     edi, edi
0x1800b599b  mov     rax, [rbp+0D0h+hMem]
0x1800b599f  cmp     [rax], edi
0x1800b59a1  jbe     loc_1800B5A2D
0x1800b59a7  lea     rbx, [rdi+rdi*2]
0x1800b59ab  mov     r15, [rax+8]
0x1800b59af  cmp     dword ptr [r15+rbx*8], 9
0x1800b59b4  jnz     short loc_1800B5A13
0x1800b59b6  mov     rdx, [r15+rbx*8+8]
0x1800b59bb  test    rdx, rdx
0x1800b59be  jz      short loc_1800B5A13
0x1800b59c0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b59c4  inc     r8
0x1800b59c7  cmp     byte ptr [rdx+r8], 0
0x1800b59cc  jnz     short loc_1800B59C4
0x1800b59ce  lea     rcx, [rbp+0D0h+var_88]
0x1800b59d2  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x1800b59d7  lea     r13, [r14+150h]
0x1800b59de  mov     r15, [r15+rbx*8+8]
0x1800b59e3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b59e7  inc     rbx
0x1800b59ea  cmp     byte ptr [r15+rbx], 0
0x1800b59ef  jnz     short loc_1800B59E7
0x1800b59f1  mov     rcx, r13
0x1800b59f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800b59f9  mov     r9, rbx
0x1800b59fc  mov     r8, r15
0x1800b59ff  mov     rdx, [r13+10h]
0x1800b5a03  mov     rcx, rax
0x1800b5a06  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800b5a0b  test    eax, eax
0x1800b5a0d  mov     rax, [rbp+0D0h+hMem]
0x1800b5a11  jz      short loc_1800B5A1B
0x1800b5a13  inc     edi
0x1800b5a15  cmp     edi, [rax]
0x1800b5a17  jb      short loc_1800B59A7
0x1800b5a19  jmp     short loc_1800B5A1E
0x1800b5a1b  mov     r12b, 1
0x1800b5a1e  lea     rbx, a252917; "2.5.29.17"
0x1800b5a25  mov     r13, [rbp+0D0h+var_E8]
0x1800b5a29  mov     r15, [rbp+0D0h+var_108]
0x1800b5a2d  mov     rcx, rax; hMem
0x1800b5a30  call    cs:__imp_LocalFree
0x1800b5a36  mov     [rbp+0D0h+hMem], 0
0x1800b5a3e  mov     rdi, [rbp+0D0h+var_A8]
0x1800b5a42  cmp     qword ptr [r14+160h], 0
0x1800b5a4a  jz      short loc_1800B5A5B
0x1800b5a4c  test    r12b, r12b
0x1800b5a4f  jnz     short loc_1800B5A5B
0x1800b5a51  mov     esi, 8000FFFFh
0x1800b5a56  xor     r12d, r12d
0x1800b5a59  jmp     short loc_1800B5A62
0x1800b5a5b  xor     r12d, r12d
0x1800b5a5e  test    esi, esi
0x1800b5a60  jns     short loc_1800B5AB6
0x1800b5a62  mov     eax, cs:CallbackContext
0x1800b5a68  cmp     eax, 2
0x1800b5a6b  jbe     short loc_1800B5AAE
0x1800b5a6d  mov     [rbp+0D0h+var_128], rbx
0x1800b5a71  lea     rax, aLpaLpdDownload_19; "LPA::Lpd::DownloadInstance::OnEs9OrEs11"...
0x1800b5a78  mov     [rbp+0D0h+var_118], rax
0x1800b5a7c  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b5a83  mov     [rbp+0D0h+var_120], rax
0x1800b5a87  lea     rax, [rbp+0D0h+var_128]
0x1800b5a8b  mov     [rsp+1E0h+var_1B0], rax
0x1800b5a90  lea     rax, [rbp+0D0h+var_118]
0x1800b5a94  mov     [rsp+1E0h+var_1B8], rax
0x1800b5a99  lea     rax, [rbp+0D0h+var_120]
0x1800b5a9d  mov     [rsp+1E0h+var_1C0], rax
0x1800b5aa2  lea     rdx, byte_180131B79
0x1800b5aa9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800b5aae  test    esi, esi
0x1800b5ab0  js      loc_1800B5DD1
0x1800b5ab6  xorps   xmm0, xmm0
0x1800b5ab9  movups  [rbp+0D0h+var_70], xmm0
0x1800b5abd  mov     [rbp+0D0h+var_60], r12
0x1800b5ac1  mov     [rbp+0D0h+var_58], 0Fh
0x1800b5ac9  mov     byte ptr [rbp+0D0h+var_70], r12b
0x1800b5acd  mov     [rbp+0D0h+var_150], r12b
0x1800b5ad1  movdqu  xmmword ptr [rbp+0D0h+var_C8], xmm0
0x1800b5ad6  mov     [rbp+0D0h+var_B8], r12
0x1800b5ada  movdqu  [rbp+0D0h+var_A0], xmm0
0x1800b5adf  mov     [rbp+0D0h+var_90], r12
0x1800b5ae3  lea     rax, [rbp+0D0h+var_A0]
0x1800b5ae7  mov     [rsp+1E0h+var_1C0], rax
0x1800b5aec  lea     r9, [rbp+0D0h+var_C8]
0x1800b5af0  lea     r8, [rbp+0D0h+var_150]
0x1800b5af4  lea     rdx, [rbp+0D0h+var_70]
0x1800b5af8  mov     rcx, rdi
0x1800b5afb  call    ?ParseServerSigned1@DownloadInstance@Lpd@LPA@@CAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@AEA_NAEAV45@3@Z; LPA::Lpd::DownloadInstance::ParseServerSigned1(std::vector<uchar> const &,std::string &,bool &,std::vector<uchar> &,std::vector<uchar> &)
0x1800b5b00  mov     esi, eax
0x1800b5b02  test    eax, eax
0x1800b5b04  js      loc_1800B5BC9
0x1800b5b0a  mov     rax, [rbp+0D0h+var_C8+8]
0x1800b5b0e  mov     rcx, [rbp+0D0h+var_C8]
0x1800b5b12  sub     rax, rcx
0x1800b5b15  cmp     rax, 2
0x1800b5b19  jbe     short loc_1800B5B47
0x1800b5b1b  movzx   eax, byte ptr [rcx+2]
0x1800b5b1f  movzx   edx, byte ptr [rcx+1]
0x1800b5b23  movzx   r9d, byte ptr [rcx]
0x1800b5b27  lea     rcx, [r14+0A6h]; unsigned __int16 *
0x1800b5b2e  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x1800b5b32  mov     dword ptr [rsp+1E0h+var_1C0], edx
0x1800b5b36  lea     r8, aUUU; "%u.%u.%u"
0x1800b5b3d  mov     edx, 0Ch; unsigned __int64
0x1800b5b42  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b5b47  lea     rdi, [r14+0F0h]
0x1800b5b4e  mov     rcx, rdi
0x1800b5b51  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800b5b56  mov     rbx, rax
0x1800b5b59  lea     rcx, [rbp+0D0h+var_70]
0x1800b5b5d  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800b5b62  mov     r8, rax
0x1800b5b65  mov     r9, [rbp+0D0h+var_60]
0x1800b5b69  mov     rdx, [rdi+10h]
0x1800b5b6d  mov     rcx, rbx
0x1800b5b70  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800b5b75  test    eax, eax
0x1800b5b77  jz      short loc_1800B5BBF
0x1800b5b79  mov     esi, 8000FFFFh
0x1800b5b7e  mov     eax, cs:CallbackContext
0x1800b5b84  cmp     eax, 2
0x1800b5b87  jbe     short loc_1800B5BC9
0x1800b5b89  lea     rbx, aLpaLpdDownload_19; "LPA::Lpd::DownloadInstance::OnEs9OrEs11"...
0x1800b5b90  mov     [rbp+0D0h+var_128], rbx
0x1800b5b94  lea     rdi, aLpaservicelpd; "LpaServiceLpd"
0x1800b5b9b  mov     [rbp+0D0h+var_118], rdi
0x1800b5b9f  lea     rax, [rbp+0D0h+var_128]
0x1800b5ba3  mov     [rsp+1E0h+var_1B8], rax
0x1800b5ba8  lea     rax, [rbp+0D0h+var_118]
0x1800b5bac  mov     [rsp+1E0h+var_1C0], rax
0x1800b5bb1  lea     rdx, unk_180131B40
0x1800b5bb8  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800b5bbd  jmp     short loc_1800B5BD7
0x1800b5bbf  mov     al, [rbp+0D0h+var_150]
0x1800b5bc2  mov     [r14+8Ch], al
0x1800b5bc9  lea     rbx, aLpaLpdDownload_19; "LPA::Lpd::DownloadInstance::OnEs9OrEs11"...
0x1800b5bd0  lea     rdi, aLpaservicelpd; "LpaServiceLpd"
0x1800b5bd7  lea     rcx, [rbp+0D0h+var_A0]
0x1800b5bdb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800b5be0  nop
0x1800b5be1  lea     rcx, [rbp+0D0h+var_C8]
0x1800b5be5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800b5bea  nop
0x1800b5beb  lea     rcx, [rbp+0D0h+var_70]
0x1800b5bef  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b5bf4  test    esi, esi
0x1800b5bf6  js      loc_1800B5DD1
0x1800b5bfc  mov     rax, [r14+1F8h]
0x1800b5c03  cmp     [r14+1F0h], rax
0x1800b5c0a  jz      loc_1800B5E38
0x1800b5c10  mov     [rbp+0D0h+hMem], r12
0x1800b5c14  mov     [rbp+0D0h+var_13C], r12d
0x1800b5c18  mov     rcx, [r13+0]
0x1800b5c1c  mov     rax, [r13+8]
0x1800b5c20  cmp     rcx, rax
0x1800b5c23  jnz     short loc_1800B5C51
0x1800b5c25  lea     rax, [rbp+0D0h+var_13C]
0x1800b5c29  mov     [rsp+1E0h+var_1C0], rax; unsigned int *
0x1800b5c2e  lea     r9, [rbp+0D0h+hMem]
0x1800b5c32  mov     r8, [rbp+0D0h+var_B0]
0x1800b5c36  mov     edx, 1Fh; char *
0x1800b5c3b  lea     rsi, a252935; "2.5.29.35"
0x1800b5c42  mov     rcx, rsi; char *
0x1800b5c45  call    ?GetX509ExtensionValueFromAsn1CertVector@DownloadInstance@Lpd@LPA@@CAJPEBD0AEBV?$vector@EV?$allocator@E@std@@@std@@PEAPEAXAEAK@Z; LPA::Lpd::DownloadInstance::GetX509ExtensionValueFromAsn1CertVector(char const *,char const *,std::vector<uchar> const &,void * *,ulong &)
0x1800b5c4a  mov     ebx, eax
0x1800b5c4c  jmp     loc_1800B5D24
0x1800b5c51  mov     qword ptr [rbp+0D0h+var_130], r12
0x1800b5c55  sub     rax, rcx
0x1800b5c58  mov     dword ptr [rsp+1E0h+var_1B0], r12d
0x1800b5c5d  mov     [rsp+1E0h+var_1B8], rax
0x1800b5c62  mov     [rsp+1E0h+var_1C0], rcx
0x1800b5c67  lea     r9, [rbp+0D0h+var_130]
0x1800b5c6b  lea     r8, asn_DEF_CertificateChain
0x1800b5c72  xor     edx, edx
0x1800b5c74  lea     rcx, [rbp+0D0h+var_C8]
0x1800b5c78  mov     rax, cs:off_1801540E8
0x1800b5c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5c84  lea     rsi, a252935; "2.5.29.35"
0x1800b5c8b  cmp     [rax], r12d
0x1800b5c8e  jz      short loc_1800B5CCC
0x1800b5c90  mov     eax, cs:CallbackContext
0x1800b5c96  cmp     eax, 4
0x1800b5c99  jbe     short loc_1800B5CC1
0x1800b5c9b  mov     [rbp+0D0h+var_128], rbx
0x1800b5c9f  mov     [rbp+0D0h+var_118], rdi
0x1800b5ca3  lea     rax, [rbp+0D0h+var_128]
0x1800b5ca7  mov     [rsp+1E0h+var_1B8], rax
0x1800b5cac  lea     rax, [rbp+0D0h+var_118]
0x1800b5cb0  mov     [rsp+1E0h+var_1C0], rax
0x1800b5cb5  lea     rdx, unk_180131B08
0x1800b5cbc  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800b5cc1  mov     ebx, 80070057h
  ... truncated ...
```
