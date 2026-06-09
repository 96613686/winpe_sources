# LPA::EnterpriseManager::SetAddProfileResult(long,LPA_ERROR_DETAILS const *,ulong,LPA::LPAESIMINSLOTINTERNAL)

- ea: `0x18007d420`
- end: `0x18007d8c5`
- name: `?SetAddProfileResult@EnterpriseManager@LPA@@UEAAXJPEBULPA_ERROR_DETAILS@@KW4LPAESIMINSLOTINTERNAL@2@@Z`
- size: `1189`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017c8`
- `0x1800018b4`
- `0x180001f1c`
- `0x1800031fc`
- `0x18000df90`
- `0x18000ebf4`
- `0x180071344`
- `0x180071840`
- `0x180075974`
- `0x180077f20`
- `0x18007cc64`
- `0x18007d420`
- `0x18007f114`
- `0x18007f838`
- `0x180080214`
- `0x180080a28`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18007d61e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18007d61e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18007d6ab`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18007d6ab`

## string_xrefs

- `0x18007d4a6`: `LpaServiceEnterpriseManager`
- `0x18007d4f3`: `LpaServiceEnterpriseManager`
- `0x18007d674`: `LpaServiceEnterpriseManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LPA::EnterpriseManager::SetAddProfileResult(__int64 a1, int a2, __int64 a3, int a4, int a5)
{
  LPA::EnterpriseManager **v9; // rsi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  LPA::EnterpriseManager *v13; // rbx
  __int64 result; // rax
  __int64 v15; // rsi
  int v16; // r13d
  unsigned int v17; // r12d
  unsigned int v18; // r15d
  __int64 v19; // rdi
  const BYTE *v20; // rax
  LPA::EnterpriseManager *v21; // rdi
  __int64 v22; // r15
  const unsigned __int16 *v23; // rdx
  LPA::EnterpriseManager *v24; // rcx
  int v25; // edi
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // rax
  __int64 v29; // rcx
  struct _SECURITY_ATTRIBUTES *v30; // rdi
  struct _SECURITY_ATTRIBUTES *v31; // rsi
  struct _SECURITY_ATTRIBUTES *v32; // rax
  unsigned __int16 *v33; // rdx
  unsigned __int16 (*v34)[33]; // r8
  int v35; // eax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  struct _SECURITY_ATTRIBUTES *v39; // [rsp+20h] [rbp-100h]
  struct _SECURITY_ATTRIBUTES *v40; // [rsp+38h] [rbp-E8h]
  bool v41; // [rsp+A0h] [rbp-80h]
  char v42; // [rsp+A1h] [rbp-7Fh]
  char v43; // [rsp+A2h] [rbp-7Eh]
  int v44; // [rsp+A4h] [rbp-7Ch] BYREF
  int v45; // [rsp+A8h] [rbp-78h] BYREF
  LPA::EnterpriseManager *v46; // [rsp+B0h] [rbp-70h] BYREF
  const char *v47; // [rsp+B8h] [rbp-68h] BYREF
  int v48; // [rsp+C0h] [rbp-60h] BYREF
  int v49; // [rsp+C4h] [rbp-5Ch] BYREF
  int v50; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+D0h] [rbp-50h] BYREF
  const unsigned __int16 *v52; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v53; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v54; // [rsp+E8h] [rbp-38h] BYREF
  const unsigned __int16 *v55; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v56; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v57; // [rsp+100h] [rbp-20h] BYREF
  unsigned __int16 *v58; // [rsp+108h] [rbp-18h] BYREF
  const unsigned __int16 *v59; // [rsp+110h] [rbp-10h] BYREF
  __int64 v60; // [rsp+118h] [rbp-8h]
  unsigned __int16 v61[33]; // [rsp+120h] [rbp+0h] BYREF
  int v62; // [rsp+1D8h] [rbp+B8h] BYREF

  v62 = a4;
  v44 = a2;
  v47 = (const char *)a1;
  v9 = (LPA::EnterpriseManager **)(a1 + 112);
  v60 = a1 + 112;
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    a1 + 112,
    &v46,
    &v62);
  v13 = v46;
  if ( *v9 == v46 )
  {
    result = (unsigned int)CallbackContext;
    if ( (unsigned int)CallbackContext > 3 )
    {
      v44 = a4;
      v45 = a2;
      v46 = (LPA::EnterpriseManager *)"LPA::EnterpriseManager::SetAddProfileResult";
      v47 = "LpaServiceEnterpriseManager";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               v10,
               (unsigned int)byte_18012C1A1,
               v11,
               v12,
               (__int64)&v47,
               (__int64)&v46,
               (__int64)&v45,
               (__int64)&v44);
    }
    return result;
  }
  v15 = *((_QWORD *)v46 + 5);
  if ( !v15 )
  {
    result = (unsigned int)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v45 = a4;
      v44 = a2;
      v46 = (LPA::EnterpriseManager *)"LPA::EnterpriseManager::SetAddProfileResult";
      v47 = "LpaServiceEnterpriseManager";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               0,
               (unsigned int)byte_18012C153,
               v11,
               v12,
               (__int64)&v47,
               (__int64)&v46,
               (__int64)&v44,
               (__int64)&v45);
    }
    return result;
  }
  v42 = 1;
  v41 = 1;
  v16 = *(_DWORD *)(v15 + 216);
  v43 = *(_BYTE *)(v15 + 176);
  if ( a2 >= 0 )
  {
    v17 = 2;
    v18 = 0;
  }
  else
  {
    v17 = 4;
    if ( !*(_BYTE *)(a1 + 128) )
    {
      v18 = 14;
LABEL_15:
      v41 = 0;
LABEL_16:
      if ( v16 )
        v42 = 0;
      goto LABEL_20;
    }
    if ( a3 && (*(_BYTE *)a3 & 1) != 0 )
    {
      v18 = *(_DWORD *)(a3 + 4);
      if ( ((v18 - 12) & 0xFFFFFFFD) == 0 )
      {
        if ( (unsigned int)--v16 >= 2 )
          goto LABEL_16;
        goto LABEL_15;
      }
    }
    else
    {
      v18 = 13;
    }
  }
LABEL_20:
  v46 = (LPA::EnterpriseManager *)(v47 - 8);
  v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15 + 144);
  v20 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15 + 112);
  v39 = (struct _SECURITY_ATTRIBUTES *)v19;
  v21 = v46;
  LPA::EnterpriseManager::SetProfileDetailsToRegistry(
    v46,
    (CommonUtil *)v15,
    (CommonUtil *)(v15 + 66),
    v20,
    v39,
    v17,
    v18);
  v22 = *((_QWORD *)v13 + 5);
  if ( v42 )
  {
    v23 = 0;
    if ( !*(_BYTE *)(v22 + 220) )
      v23 = (const unsigned __int16 *)*((_QWORD *)v13 + 5);
    LPA::EnterpriseManager::DeleteStagedProfileDetailsFromRegistry(
      v21,
      (const unsigned __int16 (*)[33])v23,
      (unsigned __int16 (*)[21])(v22 + 66));
    v25 = RoInitialize(1);
    LODWORD(v46) = v25;
    if ( v25 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v45 = v25;
        v46 = (LPA::EnterpriseManager *)"LPA::EnterpriseManager::SetAddProfileResult";
        v47 = "LpaServiceEnterpriseManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v24,
          (unsigned int)word_18012C11A,
          v26,
          v27,
          (__int64)&v47,
          (__int64)&v46,
          (__int64)&v45);
      }
    }
    else
    {
      if ( v17 == 2 && !v43 )
        LPA::EnterpriseManager::ShowProfileAvailableToast(v24);
      v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v13 + 5) + 184LL);
      LPA::EnterpriseManager::NotifyMdmServer(v29, v28, v17);
    }
    if ( v25 >= 0 )
      RoUninitialize();
  }
  else
  {
    v30 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22 + 184);
    v31 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22 + 144);
    v32 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22 + 112);
    v33 = 0;
    if ( !*(_BYTE *)(v22 + 220) )
      v33 = (unsigned __int16 *)v22;
    LODWORD(v40) = v16;
    LPA::EnterpriseManager::SetStagedProfileDetailsToRegistry(
      v46,
      (unsigned __int16 (*)[33])v33,
      (unsigned __int16 (*)[21])(v22 + 66),
      v32,
      v31,
      *(_BYTE *)(v22 + 176),
      v30,
      v40,
      v41);
  }
  v61[0] = 0;
  memset_0(&v61[1], 0, 0x40u);
  CommonUtil::WritePiiFilteredEsimIdToBuffer(*((CommonUtil **)v13 + 5), (const unsigned __int16 (*)[33])v61, v34);
  if ( (unsigned int)dword_18015A5E0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015A5E0, 0x800000000000LL) )
  {
    v52 = &qword_1801130E8;
    v53 = &qword_1801130E8;
    v45 = a5;
    v54 = &qword_1801130E8;
    v55 = &qword_1801130E8;
    v56 = &qword_1801130E8;
    if ( a3 && (*(_BYTE *)a3 & 1) != 0 )
      v35 = *(_DWORD *)(a3 + 4);
    else
      v35 = 0;
    v48 = v35;
    v49 = 1;
    v57 = &qword_1801130E8;
    v58 = v61;
    v59 = &qword_1801130E8;
    v50 = 2;
    LODWORD(v47) = v62;
    LODWORD(v46) = 1;
    v51 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v13 + 5) + 112LL);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v36,
      (unsigned int)&unk_18012C038,
      v37,
      v38,
      (__int64)&v51,
      (__int64)&v46,
      (__int64)&v44,
      (__int64)&v47,
      (__int64)&v50,
      (__int64)&v59,
      (__int64)&v58,
      (__int64)&v57,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)&v54,
      (__int64)&v45,
      (__int64)&v53,
      (__int64)&v52);
  }
  return std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>>,0>(
           v60,
           &v51,
           v13);
}

```

## disassembly

```asm
0x18007d420  mov     [rsp-8+arg_8], rbx
0x18007d425  mov     [rsp-8+arg_18], r9d
0x18007d42a  push    rbp
0x18007d42b  push    rsi
0x18007d42c  push    rdi
0x18007d42d  push    r12
0x18007d42f  push    r13
0x18007d431  push    r14
0x18007d433  push    r15
0x18007d435  lea     rbp, [rsp-60h]
0x18007d43a  sub     rsp, 180h
0x18007d441  mov     rax, cs:__security_cookie
0x18007d448  xor     rax, rsp
0x18007d44b  mov     [rbp+90h+var_40], rax
0x18007d44f  mov     r12d, r9d
0x18007d452  mov     r14, r8
0x18007d455  mov     edi, edx
0x18007d457  mov     [rbp+90h+var_10C], edx
0x18007d45a  mov     r15, rcx
0x18007d45d  mov     [rbp+90h+var_F8], rcx
0x18007d461  lea     rsi, [rcx+70h]
0x18007d465  mov     [rbp+90h+var_98], rsi
0x18007d469  lea     r8, [rbp+90h+arg_18]
0x18007d470  lea     rdx, [rbp+90h+var_100]
0x18007d474  mov     rcx, rsi
0x18007d477  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x18007d47c  mov     rbx, [rbp+90h+var_100]
0x18007d480  cmp     [rsi], rbx
0x18007d483  jnz     short loc_18007D4C7
0x18007d485  mov     eax, cs:CallbackContext
0x18007d48b  cmp     eax, 3
0x18007d48e  jbe     loc_18007D89E
0x18007d494  mov     [rbp+90h+var_10C], r12d
0x18007d498  mov     [rbp+90h+var_108], edi
0x18007d49b  lea     rax, aLpaEnterprisem_3; "LPA::EnterpriseManager::SetAddProfileRe"...
0x18007d4a2  mov     [rbp+90h+var_100], rax
0x18007d4a6  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007d4ad  mov     [rbp+90h+var_F8], rax
0x18007d4b1  lea     rax, [rbp+90h+var_10C]
0x18007d4b5  mov     [rsp+1B0h+var_178], rax
0x18007d4ba  lea     rax, [rbp+90h+var_108]
0x18007d4be  lea     rdx, byte_18012C1A1
0x18007d4c5  jmp     short loc_18007D512
0x18007d4c7  mov     rsi, [rbx+28h]
0x18007d4cb  xor     ecx, ecx
0x18007d4cd  test    rsi, rsi
0x18007d4d0  jnz     short loc_18007D533
0x18007d4d2  mov     eax, cs:CallbackContext
0x18007d4d8  cmp     eax, 2
0x18007d4db  jbe     loc_18007D89E
0x18007d4e1  mov     [rbp+90h+var_108], r12d
0x18007d4e5  mov     [rbp+90h+var_10C], edi
0x18007d4e8  lea     rax, aLpaEnterprisem_3; "LPA::EnterpriseManager::SetAddProfileRe"...
0x18007d4ef  mov     [rbp+90h+var_100], rax
0x18007d4f3  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007d4fa  mov     [rbp+90h+var_F8], rax
0x18007d4fe  lea     rax, [rbp+90h+var_108]
0x18007d502  mov     [rsp+1B0h+var_178], rax
0x18007d507  lea     rax, [rbp+90h+var_10C]
0x18007d50b  lea     rdx, byte_18012C153
0x18007d512  mov     [rsp+1B0h+var_180], rax
0x18007d517  lea     rax, [rbp+90h+var_100]
0x18007d51b  mov     qword ptr [rsp+1B0h+var_188], rax
0x18007d520  lea     rax, [rbp+90h+var_F8]
0x18007d524  mov     [rsp+1B0h+var_190], rax
0x18007d529  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007d52e  jmp     loc_18007D89E
0x18007d533  mov     [rbp+90h+var_10F], 1
0x18007d537  mov     [rbp+90h+var_110], 1
0x18007d53b  mov     r13d, [rsi+0D8h]
0x18007d542  mov     al, [rsi+0B0h]
0x18007d548  mov     [rbp+90h+var_10E], al
0x18007d54b  test    edi, edi
0x18007d54d  jns     short loc_18007D5A0
0x18007d54f  mov     r12d, 4
0x18007d555  cmp     [r15+80h], cl
0x18007d55c  jnz     short loc_18007D565
0x18007d55e  lea     r15d, [r12+0Ah]
0x18007d563  jmp     short loc_18007D58B
0x18007d565  test    r14, r14
0x18007d568  jz      short loc_18007D598
0x18007d56a  test    byte ptr [r14], 1
0x18007d56e  jz      short loc_18007D598
0x18007d570  mov     r15d, [r14+4]
0x18007d574  lea     eax, [r15-0Ch]
0x18007d578  test    eax, 0FFFFFFFDh
0x18007d57d  jnz     short loc_18007D5A9
0x18007d57f  lea     eax, [r13-1]
0x18007d583  mov     r13d, eax
0x18007d586  cmp     eax, 2
0x18007d589  jnb     short loc_18007D58E
0x18007d58b  mov     [rbp+90h+var_110], cl
0x18007d58e  test    r13d, r13d
0x18007d591  jz      short loc_18007D5A9
0x18007d593  mov     [rbp+90h+var_10F], cl
0x18007d596  jmp     short loc_18007D5A9
0x18007d598  mov     r15d, 0Dh
0x18007d59e  jmp     short loc_18007D5A9
0x18007d5a0  mov     r12d, 2
0x18007d5a6  mov     r15d, ecx
0x18007d5a9  mov     rax, [rbp+90h+var_F8]
0x18007d5ad  add     rax, 0FFFFFFFFFFFFFFF8h
0x18007d5b1  mov     [rbp+90h+var_100], rax
0x18007d5b5  lea     rcx, [rsi+90h]
0x18007d5bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007d5c1  mov     rdi, rax
0x18007d5c4  lea     rcx, [rsi+70h]
0x18007d5c8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007d5cd  lea     r8, [rsi+42h]
0x18007d5d1  mov     dword ptr [rsp+1B0h+var_180], r15d
0x18007d5d6  mov     dword ptr [rsp+1B0h+var_188], r12d
0x18007d5db  mov     [rsp+1B0h+var_190], rdi
0x18007d5e0  mov     r9, rax
0x18007d5e3  mov     rdx, rsi
0x18007d5e6  mov     rdi, [rbp+90h+var_100]
0x18007d5ea  mov     rcx, rdi
0x18007d5ed  call    ?SetProfileDetailsToRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEAY0BF@$$CBGPEBG2W4LPAENTERPRISEPROFILESTATE@@W4LPAERROR@@@Z; LPA::EnterpriseManager::SetProfileDetailsToRegistry(ushort const (&)[33],ushort const (&)[21],ushort const *,ushort const *,LPAENTERPRISEPROFILESTATE,LPAERROR)
0x18007d5f2  mov     r15, [rbx+28h]
0x18007d5f6  cmp     [rbp+90h+var_10F], 0
0x18007d5fa  jz      loc_18007D6B3
0x18007d600  xor     edx, edx
0x18007d602  cmp     [r15+0DCh], dl
0x18007d609  cmovz   rdx, r15; unsigned __int16 (*)[33]
0x18007d60d  lea     r8, [r15+42h]; unsigned __int16 (*)[21]
0x18007d611  mov     rcx, rdi; this
0x18007d614  call    ?DeleteStagedProfileDetailsFromRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAY0BF@$$CBG@Z; LPA::EnterpriseManager::DeleteStagedProfileDetailsFromRegistry(ushort const (*)[33],ushort const (&)[21])
0x18007d619  mov     ecx, 1
0x18007d61e  call    cs:__imp_RoInitialize
0x18007d624  mov     edi, eax
0x18007d626  mov     dword ptr [rbp+90h+var_100], eax
0x18007d629  test    eax, eax
0x18007d62b  js      short loc_18007D65B
0x18007d62d  cmp     r12d, 2
0x18007d631  jnz     short loc_18007D63E
0x18007d633  cmp     [rbp+90h+var_10E], 0
0x18007d637  jnz     short loc_18007D63E
0x18007d639  call    ?ShowProfileAvailableToast@EnterpriseManager@LPA@@AEAAXXZ; LPA::EnterpriseManager::ShowProfileAvailableToast(void)
0x18007d63e  mov     rcx, [rbx+28h]
0x18007d642  add     rcx, 0B8h
0x18007d649  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007d64e  mov     r8d, r12d
0x18007d651  mov     rdx, rax
0x18007d654  call    ?NotifyMdmServer@EnterpriseManager@LPA@@AEAAXPEBGW4LPAENTERPRISEPROFILESTATE@@@Z; LPA::EnterpriseManager::NotifyMdmServer(ushort const *,LPAENTERPRISEPROFILESTATE)
0x18007d659  jmp     short loc_18007D6A7
0x18007d65b  mov     eax, cs:CallbackContext
0x18007d661  cmp     eax, 2
0x18007d664  jbe     short loc_18007D6A7
0x18007d666  mov     [rbp+90h+var_108], edi
0x18007d669  lea     rax, aLpaEnterprisem_3; "LPA::EnterpriseManager::SetAddProfileRe"...
0x18007d670  mov     [rbp+90h+var_100], rax
0x18007d674  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007d67b  mov     [rbp+90h+var_F8], rax
0x18007d67f  lea     rax, [rbp+90h+var_108]
0x18007d683  mov     [rsp+1B0h+var_180], rax
0x18007d688  lea     rax, [rbp+90h+var_100]
0x18007d68c  mov     qword ptr [rsp+1B0h+var_188], rax
0x18007d691  lea     rax, [rbp+90h+var_F8]
0x18007d695  mov     [rsp+1B0h+var_190], rax
0x18007d69a  lea     rdx, word_18012C11A
0x18007d6a1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007d6a6  nop
0x18007d6a7  test    edi, edi
0x18007d6a9  js      short loc_18007D718
0x18007d6ab  call    cs:__imp_RoUninitialize
0x18007d6b1  jmp     short loc_18007D718
0x18007d6b3  lea     rcx, [r15+0B8h]
0x18007d6ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007d6bf  mov     rdi, rax
0x18007d6c2  lea     rcx, [r15+90h]
0x18007d6c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007d6ce  mov     rsi, rax
0x18007d6d1  lea     rcx, [r15+70h]
0x18007d6d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007d6da  xor     edx, edx
0x18007d6dc  cmp     [r15+0DCh], dl
0x18007d6e3  cmovz   rdx, r15; unsigned __int16 (*)[33]
0x18007d6e7  mov     cl, [rbp+90h+var_110]
0x18007d6ea  mov     [rsp+1B0h+var_170], cl; bool
0x18007d6ee  mov     dword ptr [rsp+1B0h+var_178], r13d; struct _SECURITY_ATTRIBUTES *
0x18007d6f3  mov     [rsp+1B0h+var_180], rdi; struct _SECURITY_ATTRIBUTES *
0x18007d6f8  mov     cl, [r15+0B0h]
0x18007d6ff  mov     [rsp+1B0h+var_188], cl; bool
0x18007d703  mov     [rsp+1B0h+var_190], rsi; struct _SECURITY_ATTRIBUTES *
0x18007d708  mov     r9, rax; unsigned __int16 *
0x18007d70b  lea     r8, [r15+42h]; unsigned __int16 (*)[21]
0x18007d70f  mov     rcx, [rbp+90h+var_100]; this
0x18007d713  call    ?SetStagedProfileDetailsToRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAY0BF@$$CBGPEBG2_N2K3@Z; LPA::EnterpriseManager::SetStagedProfileDetailsToRegistry(ushort const (*)[33],ushort const (&)[21],ushort const *,ushort const *,bool,ushort const *,ulong,bool)
0x18007d718  xor     eax, eax
0x18007d71a  mov     [rbp+90h+var_90], ax
0x18007d71e  xor     edx, edx; Val
0x18007d720  lea     r8d, [rax+40h]; Size
0x18007d724  lea     rcx, [rbp+90h+var_90+2]; void *
0x18007d728  call    memset_0
0x18007d72d  lea     rdx, [rbp+90h+var_90]; unsigned __int16 (*)[33]
0x18007d731  mov     rcx, [rbx+28h]; this
0x18007d735  call    ?WritePiiFilteredEsimIdToBuffer@CommonUtil@@YAXPEAY0CB@$$CBGAEAY0CB@G@Z; CommonUtil::WritePiiFilteredEsimIdToBuffer(ushort const (*)[33],ushort (&)[33])
0x18007d73a  mov     eax, cs:dword_18015A5E0
0x18007d740  cmp     eax, 5
0x18007d743  jbe     loc_18007D88E
0x18007d749  mov     rdx, 800000000000h
0x18007d753  lea     rcx, dword_18015A5E0
0x18007d75a  call    _tlgKeywordOn
0x18007d75f  test    al, al
0x18007d761  jz      loc_18007D88E
0x18007d767  lea     rcx, qword_1801130E8
0x18007d76e  mov     [rbp+90h+var_D8], rcx
0x18007d772  mov     [rbp+90h+var_D0], rcx
0x18007d776  mov     eax, [rbp+90h+arg_20]
0x18007d77c  mov     [rbp+90h+var_108], eax
0x18007d77f  mov     [rbp+90h+var_C8], rcx
0x18007d783  mov     [rbp+90h+var_C0], rcx
0x18007d787  mov     [rbp+90h+var_B8], rcx
0x18007d78b  test    r14, r14
0x18007d78e  jz      short loc_18007D79C
0x18007d790  test    byte ptr [r14], 1
0x18007d794  jz      short loc_18007D79C
0x18007d796  mov     eax, [r14+4]
0x18007d79a  jmp     short loc_18007D79E
0x18007d79c  xor     eax, eax
0x18007d79e  mov     [rbp+90h+var_F0], eax
0x18007d7a1  mov     [rbp+90h+var_EC], 1
0x18007d7a8  mov     [rbp+90h+var_B0], rcx
0x18007d7ac  lea     rax, [rbp+90h+var_90]
0x18007d7b0  mov     [rbp+90h+var_A8], rax
0x18007d7b4  mov     [rbp+90h+var_A0], rcx
0x18007d7b8  mov     [rbp+90h+var_E8], 2
0x18007d7bf  mov     eax, [rbp+90h+arg_18]
0x18007d7c5  mov     dword ptr [rbp+90h+var_F8], eax
0x18007d7c8  mov     eax, [rbp+90h+var_10C]
0x18007d7cb  mov     [rbp+90h+var_10C], eax
0x18007d7ce  mov     dword ptr [rbp+90h+var_100], 1
0x18007d7d5  mov     rcx, [rbx+28h]
0x18007d7d9  add     rcx, 70h ; 'p'
0x18007d7dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007d7e2  mov     [rbp+90h+var_E0], rax
0x18007d7e6  lea     rax, [rbp+90h+var_D8]
0x18007d7ea  mov     [rsp+1B0h+var_118], rax
0x18007d7f2  lea     rax, [rbp+90h+var_D0]
0x18007d7f6  mov     [rsp+1B0h+var_120], rax
0x18007d7fe  lea     rax, [rbp+90h+var_108]
0x18007d802  mov     [rsp+1B0h+var_128], rax
0x18007d80a  lea     rax, [rbp+90h+var_C8]
0x18007d80e  mov     [rsp+1B0h+var_130], rax
0x18007d816  lea     rax, [rbp+90h+var_C0]
0x18007d81a  mov     [rsp+1B0h+var_138], rax
0x18007d81f  lea     rax, [rbp+90h+var_B8]
0x18007d823  mov     [rsp+1B0h+var_140], rax
0x18007d828  lea     rax, [rbp+90h+var_F0]
0x18007d82c  mov     [rsp+1B0h+var_148], rax
0x18007d831  lea     rax, [rbp+90h+var_EC]
0x18007d835  mov     [rsp+1B0h+var_150], rax
0x18007d83a  lea     rax, [rbp+90h+var_B0]
0x18007d83e  mov     [rsp+1B0h+var_158], rax
0x18007d843  lea     rax, [rbp+90h+var_A8]
0x18007d847  mov     [rsp+1B0h+var_160], rax
0x18007d84c  lea     rax, [rbp+90h+var_A0]
0x18007d850  mov     [rsp+1B0h+var_168], rax
0x18007d855  lea     rax, [rbp+90h+var_E8]
0x18007d859  mov     qword ptr [rsp+1B0h+var_170], rax
0x18007d85e  lea     rax, [rbp+90h+var_F8]
0x18007d862  mov     [rsp+1B0h+var_178], rax
0x18007d867  lea     rax, [rbp+90h+var_10C]
0x18007d86b  mov     [rsp+1B0h+var_180], rax
0x18007d870  lea     rax, [rbp+90h+var_100]
0x18007d874  mov     qword ptr [rsp+1B0h+var_188], rax
0x18007d879  lea     rax, [rbp+90h+var_E0]
0x18007d87d  mov     [rsp+1B0h+var_190], rax
0x18007d882  lea     rdx, unk_18012C038
0x18007d889  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U1@U1@U1@U2@U2@U1@U1@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@44433344333433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18007d88e  mov     r8, rbx
0x18007d891  lea     rdx, [rbp+90h+var_E0]
0x18007d895  mov     rcx, [rbp+90h+var_98]
0x18007d899  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>>)
0x18007d89e  mov     rcx, [rbp+90h+var_40]
0x18007d8a2  xor     rcx, rsp; StackCookie
0x18007d8a5  call    __security_check_cookie
0x18007d8aa  mov     rbx, [rsp+1B0h+arg_8]
0x18007d8b2  add     rsp, 180h
0x18007d8b9  pop     r15
0x18007d8bb  pop     r14
0x18007d8bd  pop     r13
0x18007d8bf  pop     r12
0x18007d8c1  pop     rdi
0x18007d8c2  pop     rsi
0x18007d8c3  pop     rbp
0x18007d8c4  retn
```
