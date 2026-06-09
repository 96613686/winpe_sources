# Microsoft::HostGuardian::Client::HgServiceController::QueryAttestationResults(wchar_t * const,uint,AttestationResultType *,bool,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)

- ea: `0x18000d4d8`
- end: `0x18000dab2`
- name: `?QueryAttestationResults@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXQEA_WIPEAW4AttestationResultType@@_NPEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z`
- size: `1498`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServiceController *this, wchar_t *const, unsigned int, enum AttestationResultType *, bool, enum ShsAttestationFlag *, wchar_t **, unsigned int *, struct AttestationResult **)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aa40`

## callees

- `0x180001770`
- `0x180001794`
- `0x180002e55`
- `0x180003d0c`
- `0x180003e24`
- `0x180004274`
- `0x1800073c4`
- `0x1800077a0`
- `0x180008760`
- `0x18000a84c`
- `0x18000b78c`
- `0x18000b990`
- `0x18000be5c`
- `0x18000bedc`
- `0x18000bf50`
- `0x18000c4c8`
- `0x18000ca70`
- `0x18000cdbc`
- `0x18000d4d8`
- `0x18000e078`
- `0x18000e7b4`
- `0x18000f814`
- `0x180014ed8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000d8af`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d8af`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d6cd`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d6cd`

## string_xrefs

- `0x18000da58`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000daa0`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000d8d0`: `Found all requested certificates in cache, using them...`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::QueryAttestationResults(
        Microsoft::HostGuardian::Client::HgServiceController *this,
        wchar_t *const a2,
        unsigned int a3,
        enum AttestationResultType *a4,
        bool a5,
        enum ShsAttestationFlag *a6,
        wchar_t **a7,
        unsigned int *a8,
        struct AttestationResult **a9)
{
  Microsoft::HostGuardian::Client::HgServiceController *v9; // r15
  enum ShsAttestationFlag *v10; // r12
  wchar_t **v11; // rsi
  unsigned int *v12; // r13
  struct AttestationResult **v13; // r11
  __int64 v14; // r14
  unsigned __int64 v15; // rbx
  _QWORD *v16; // rax
  void *v17; // rax
  void *v18; // rcx
  size_t v19; // r8
  enum AttestationResultType *v20; // r14
  _DWORD *v21; // r8
  _DWORD *v22; // r10
  __int64 v23; // r9
  __int64 v24; // rcx
  char v25; // al
  UINT v26; // eax
  _QWORD *v27; // rax
  Microsoft::HostGuardian::Client::CertificateCache *v28; // rbx
  BSTR *j; // rcx
  __int64 v30; // r8
  BSTR *v31; // rbx
  BSTR i; // rax
  const char *v33; // r9
  struct AttestationResult **v34; // rbx
  const OLECHAR *v35; // rcx
  BSTR v36; // rax
  _QWORD *v37; // rax
  struct AttestationResult *v38; // rax
  struct AttestationResult *v39; // rdx
  struct AttestationResult *v40; // rcx
  struct AttestationResult *k; // rcx
  unsigned int v42; // eax
  const char *v43; // rdx
  int v44; // [rsp+20h] [rbp-128h]
  struct AttestationResult **v46; // [rsp+48h] [rbp-100h] BYREF
  __int64 v47; // [rsp+50h] [rbp-F8h]
  void *Src; // [rsp+58h] [rbp-F0h] BYREF
  BSTR **v49; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v50; // [rsp+68h] [rbp-E0h]
  BSTR pbstr; // [rsp+70h] [rbp-D8h]
  struct AttestationResult **v52; // [rsp+78h] [rbp-D0h]
  __int128 v53; // [rsp+80h] [rbp-C8h] BYREF
  char *v54; // [rsp+90h] [rbp-B8h]
  BSTR *v55; // [rsp+98h] [rbp-B0h]
  unsigned int *v56; // [rsp+A0h] [rbp-A8h] BYREF
  struct AttestationResult ***v57; // [rsp+A8h] [rbp-A0h]
  Microsoft::HostGuardian::Client::HgServiceController *v58; // [rsp+B0h] [rbp-98h]
  enum ShsAttestationFlag *v59; // [rsp+B8h] [rbp-90h]
  OLECHAR *psz[2]; // [rsp+C0h] [rbp-88h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-78h]
  unsigned __int64 v62; // [rsp+D8h] [rbp-70h]
  _BYTE v63[16]; // [rsp+E0h] [rbp-68h] BYREF
  const wchar_t *v64; // [rsp+F0h] [rbp-58h]
  __int64 v65; // [rsp+F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  Src = a4;
  pbstr = a2;
  v9 = this;
  v58 = this;
  v10 = a6;
  v59 = a6;
  v11 = a7;
  v55 = a7;
  v12 = a8;
  v56 = a8;
  v13 = a9;
  v52 = a9;
  v46 = a9;
  v14 = a3;
  v53 = 0;
  v54 = 0;
  if ( a3 )
  {
    v15 = 4LL * a3;
    if ( v15 )
    {
      if ( v15 < 0x1000 )
      {
        v16 = operator new(4LL * a3);
      }
      else
      {
        if ( v15 + 39 < v15 )
          __scrt_throw_std_bad_array_new_length();
        v17 = operator new(v15 + 39);
        v18 = v17;
        if ( !v17 )
          __fastfail(5u);
        v16 = (_QWORD *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v16 - 1) = v18;
      }
    }
    else
    {
      v16 = 0;
    }
    *(_QWORD *)&v53 = v16;
    v54 = (char *)v16 + v15;
    v19 = 4 * v14;
    v20 = (enum AttestationResultType *)Src;
    memmove_0(v16, Src, v19);
    *((_QWORD *)&v53 + 1) = v54;
    Src = 0;
    std::_Tidy_guard<std::vector<enum AttestationResultType>>::~_Tidy_guard<std::vector<enum AttestationResultType>>(&Src);
    v13 = v52;
  }
  else
  {
    v20 = a4;
  }
  if ( (_QWORD)v53 != *((_QWORD *)&v53 + 1) )
  {
    v21 = (_DWORD *)v53;
    while ( 1 )
    {
      v22 = (_DWORD *)v53;
      v23 = 0;
      do
      {
        v24 = v23 + 1;
        if ( *v22 != *v21 )
          v24 = v23;
        v23 = v24;
        ++v22;
      }
      while ( v22 != *((_DWORD **)&v53 + 1) );
      if ( v24 > 1 )
        break;
      if ( ++v21 == *((_DWORD **)&v53 + 1) )
      {
        v25 = 0;
        goto LABEL_22;
      }
    }
  }
  v25 = 1;
LABEL_22:
  if ( v25 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)0x80070057LL,
      v44);
  if ( a5 )
  {
    Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues(v9, pbstr, a3, v20, a6, a7, a8, v13);
  }
  else
  {
    v26 = SysStringLen(pbstr);
    *(_OWORD *)psz = 0;
    v61 = 0;
    v62 = 0;
    std::wstring::_Construct<1,wchar_t const *>(psz, pbstr, v26);
    v49 = 0;
    v50 = 0;
    v27 = operator new(0x50u);
    *v27 = v27;
    v27[1] = v27;
    v27[2] = v27;
    *((_WORD *)v27 + 12) = 257;
    v49 = (BSTR **)v27;
    v28 = (Microsoft::HostGuardian::Client::CertificateCache *)*((_QWORD *)v9 + 17);
    std::vector<enum AttestationResultType>::vector<enum AttestationResultType>(v63, &v53);
    if ( (unsigned __int8)Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults(v28) )
    {
      v31 = *v49;
      while ( !*((_BYTE *)v31 + 25) )
      {
        if ( (unsigned int)Microsoft::HostGuardian::Client::Utilities::GetDurationStatus((FILETIME)v31[5]) != 1 )
        {
          try
          {
            Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues(
              v9,
              pbstr,
              a3,
              v20,
              a6,
              a7,
              a8,
              v52);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x67,
              (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
              v33);
            j = v55;
            if ( v55 )
              SysFreeString(*v55);
            if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
            {
              v64 = L"Failed to retrieve new certificates, continue use cached certificates...";
              v65 = 146;
              McGenEventWrite_EventWriteTransfer(j, ServiceDebugInformational, v30, 2, v63);
            }
            v9 = v58;
            v11 = v55;
            v10 = v59;
            v12 = v56;
            v34 = v46;
            goto LABEL_41;
          }
          std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>((void **)&v49);
          std::wstring::~wstring((char **)psz);
          std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>((char **)&v53);
          return;
        }
        j = (BSTR *)v31[2];
        if ( *((_BYTE *)j + 25) )
        {
          for ( i = v31[1]; !*((_BYTE *)i + 25) && v31 == *((BSTR **)i + 2); i = (BSTR)*((_QWORD *)i + 1) )
            v31 = (BSTR *)i;
          v31 = (BSTR *)i;
        }
        else
        {
          v31 = (BSTR *)v31[2];
          for ( j = (BSTR *)*j; !*((_BYTE *)j + 25); j = (BSTR *)*j )
            v31 = j;
        }
      }
      v34 = v52;
LABEL_41:
      if ( v11 && v61 )
      {
        v35 = (const OLECHAR *)psz;
        if ( v62 > 7 )
          v35 = psz[0];
        v36 = SysAllocString(v35);
        *v11 = v36;
        if ( !v36 )
        {
          std::wstring::c_str(psz);
          v42 = wil::verify_hresult<long>(2147942414LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x76,
            (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
            (const char *)v42,
            (int)"Unable to set identifier to %ws.",
            v43);
        }
      }
      if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
      {
        v64 = L"Found all requested certificates in cache, using them...";
        v65 = 114;
        McGenEventWrite_EventWriteTransfer(j, ServiceDebugInformational, v30, 2, v63);
      }
      v46 = 0;
      v47 = 0;
      v56 = (unsigned int *)&v46;
      v57 = &v46;
      v37 = operator new(0x50u);
      *v37 = v37;
      v37[1] = v37;
      v37[2] = v37;
      *((_WORD *)v37 + 12) = 257;
      v46 = (struct AttestationResult **)v37;
      v38 = (struct AttestationResult *)std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::_Copy_nodes<0>(
                                          (__int64 *)&v46,
                                          (__int64)v49[1],
                                          (__int64)v37);
      v46[1] = v38;
      v47 = v50;
      v39 = v46[1];
      if ( *((_BYTE *)v39 + 25) )
      {
        *v46 = (struct AttestationResult *)v46;
        v46[2] = (struct AttestationResult *)v46;
      }
      else
      {
        v40 = *(struct AttestationResult **)v39;
        if ( !*(_BYTE *)(*(_QWORD *)v39 + 25LL) )
        {
          do
          {
            v39 = v40;
            v40 = *(struct AttestationResult **)v40;
          }
          while ( !*((_BYTE *)v40 + 25) );
        }
        *v46 = v39;
        for ( k = v46[1]; !*(_BYTE *)(*((_QWORD *)k + 2) + 25LL); k = (struct AttestationResult *)*((_QWORD *)k + 2) )
          ;
        v46[2] = k;
      }
      v57 = 0;
      std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>>>(&v56);
      Microsoft::HostGuardian::Client::HgServiceController::CertMapToResults((__int64)v9, (void **)&v46, v12, v34);
      *(_DWORD *)v10 = *((_DWORD *)*v49 + 18);
    }
    else
    {
      Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues(v9, pbstr, a3, v20, a6, a7, a8, v52);
    }
    std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>((void **)&v49);
    std::wstring::~wstring((char **)psz);
  }
  std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>((char **)&v53);
}

```

## disassembly

```asm
0x18000d4d8  push    rbx
0x18000d4da  push    rsi
0x18000d4db  push    rdi
0x18000d4dc  push    r12
0x18000d4de  push    r13
0x18000d4e0  push    r14
0x18000d4e2  push    r15
0x18000d4e4  sub     rsp, 110h
0x18000d4eb  mov     rax, cs:__security_cookie
0x18000d4f2  xor     rax, rsp
0x18000d4f5  mov     [rsp+148h+var_48], rax
0x18000d4fd  mov     [rsp+148h+Src], r9
0x18000d502  mov     [rsp+148h+var_108], r8d
0x18000d507  mov     [rsp+148h+pbstr], rdx
0x18000d50c  mov     r15, rcx
0x18000d50f  mov     [rsp+148h+var_98], rcx
0x18000d517  mov     r12, [rsp+148h+arg_28]
0x18000d51f  mov     [rsp+148h+var_90], r12
0x18000d527  mov     rsi, [rsp+148h+arg_30]
0x18000d52f  mov     [rsp+148h+var_B0], rsi
0x18000d537  mov     r13, [rsp+148h+arg_38]
0x18000d53f  mov     [rsp+148h+var_A8], r13
0x18000d547  mov     r11, [rsp+148h+arg_40]
0x18000d54f  mov     [rsp+148h+var_D0], r11
0x18000d554  mov     [rsp+148h+var_100], r11
0x18000d559  mov     r14d, r8d
0x18000d55c  xorps   xmm0, xmm0
0x18000d55f  movdqu  [rsp+148h+var_C8], xmm0
0x18000d568  xor     edi, edi
0x18000d56a  mov     [rsp+148h+var_B8], rdi
0x18000d572  test    r8d, r8d
0x18000d575  jz      loc_18000D62F
0x18000d57b  mov     rax, 3FFFFFFFFFFFFFFFh
0x18000d585  cmp     r14, rax
0x18000d588  ja      loc_18000DA46
0x18000d58e  lea     rbx, ds:0[r14*4]
0x18000d596  test    rbx, rbx
0x18000d599  jnz     short loc_18000D5A0
0x18000d59b  mov     rax, rdi
0x18000d59e  jmp     short loc_18000D5DE
0x18000d5a0  cmp     rbx, 1000h
0x18000d5a7  jb      short loc_18000D5D6
0x18000d5a9  lea     rcx, [rbx+27h]; Size
0x18000d5ad  cmp     rcx, rbx
0x18000d5b0  jbe     loc_18000DA4C
0x18000d5b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d5bb  mov     rcx, rax
0x18000d5be  test    rax, rax
0x18000d5c1  jnz     short loc_18000D5C8
0x18000d5c3  lea     ecx, [rax+5]
0x18000d5c6  int     29h; Win8: RtlFailFast(ecx)
0x18000d5c8  add     rax, 27h ; '''
0x18000d5cc  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000d5d0  mov     [rax-8], rcx
0x18000d5d4  jmp     short loc_18000D5DE
0x18000d5d6  mov     rcx, rbx; Size
0x18000d5d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d5de  mov     qword ptr [rsp+148h+var_C8], rax
0x18000d5e6  mov     qword ptr [rsp+148h+var_C8+8], rax
0x18000d5ee  add     rbx, rax
0x18000d5f1  mov     [rsp+148h+var_B8], rbx
0x18000d5f9  lea     r8, ds:0[r14*4]; Size
0x18000d601  mov     r14, [rsp+148h+Src]
0x18000d606  mov     rdx, r14; Src
0x18000d609  mov     rcx, rax; void *
0x18000d60c  call    memmove_0
0x18000d611  mov     qword ptr [rsp+148h+var_C8+8], rbx
0x18000d619  mov     [rsp+148h+Src], rdi
0x18000d61e  lea     rcx, [rsp+148h+Src]
0x18000d623  call    ??1?$_Tidy_guard@V?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<AttestationResultType>>::~_Tidy_guard<std::vector<AttestationResultType>>(void)
0x18000d628  mov     r11, [rsp+148h+var_D0]
0x18000d62d  jmp     short loc_18000D632
0x18000d62f  mov     r14, r9
0x18000d632  mov     rdx, qword ptr [rsp+148h+var_C8]
0x18000d63a  mov     rax, qword ptr [rsp+148h+var_C8+8]
0x18000d642  cmp     rdx, rax
0x18000d645  jz      short loc_18000D67E
0x18000d647  mov     r8, rdx
0x18000d64a  mov     r10, rdx
0x18000d64d  mov     r9, rdi
0x18000d650  mov     ebx, [r8]
0x18000d653  lea     rcx, [r9+1]
0x18000d657  cmp     [r10], ebx
0x18000d65a  cmovnz  rcx, r9
0x18000d65e  mov     r9, rcx
0x18000d661  add     r10, 4
0x18000d665  cmp     r10, rax
0x18000d668  jnz     short loc_18000D653
0x18000d66a  cmp     rcx, 1
0x18000d66e  jg      short loc_18000D67E
0x18000d670  add     r8, 4
0x18000d674  cmp     r8, rax
0x18000d677  jnz     short loc_18000D64A
0x18000d679  mov     al, dil
0x18000d67c  jmp     short loc_18000D680
0x18000d67e  mov     al, 1
0x18000d680  mov     rcx, [rsp+148h]; this
0x18000d688  test    al, al
0x18000d68a  jnz     loc_18000DA52
0x18000d690  cmp     [rsp+148h+arg_20], dil
0x18000d698  jz      short loc_18000D6C8
0x18000d69a  mov     [rsp+148h+var_110], r11; struct AttestationResult **
0x18000d69f  mov     [rsp+148h+var_118], r13; unsigned int *
0x18000d6a4  mov     [rsp+148h+var_120], rsi; wchar_t **
0x18000d6a9  mov     [rsp+148h+var_128], r12; enum ShsAttestationFlag *
0x18000d6ae  mov     r9, r14; enum AttestationResultType *
0x18000d6b1  mov     r8d, [rsp+148h+var_108]; unsigned int
0x18000d6b6  mov     rdx, [rsp+148h+pbstr]; wchar_t *
0x18000d6bb  mov     rcx, r15; this
0x18000d6be  call    ?AttestForAllValues@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXQEA_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues(wchar_t * const,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)
0x18000d6c3  jmp     loc_18000DA16
0x18000d6c8  mov     rcx, [rsp+148h+pbstr]; pbstr
0x18000d6cd  call    cs:__imp_SysStringLen
0x18000d6d3  mov     r8d, eax
0x18000d6d6  xorps   xmm0, xmm0
0x18000d6d9  movups  xmmword ptr [rsp+148h+psz], xmm0
0x18000d6e1  mov     [rsp+148h+var_78], rdi
0x18000d6e9  mov     [rsp+148h+var_70], rdi
0x18000d6f1  mov     rdx, [rsp+148h+pbstr]
0x18000d6f6  lea     rcx, [rsp+148h+psz]
0x18000d6fe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d703  nop
0x18000d704  mov     [rsp+148h+var_E8], rdi
0x18000d709  mov     [rsp+148h+var_E0], rdi
0x18000d70e  mov     ecx, 50h ; 'P'; Size
0x18000d713  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d718  mov     [rax], rax
0x18000d71b  mov     [rax+8], rax
0x18000d71f  mov     [rax+10h], rax
0x18000d723  mov     word ptr [rax+18h], 101h
0x18000d729  mov     [rsp+148h+var_E8], rax
0x18000d72e  mov     rbx, [r15+88h]
0x18000d735  lea     rdx, [rsp+148h+var_C8]
0x18000d73d  lea     rcx, [rsp+148h+var_68]
0x18000d745  call    ??0?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<AttestationResultType>::vector<AttestationResultType>(std::vector<AttestationResultType> const &)
0x18000d74a  lea     r9, [rsp+148h+var_E8]
0x18000d74f  lea     r8, [rsp+148h+psz]
0x18000d757  mov     rdx, rax
0x18000d75a  mov     rcx, rbx; this
0x18000d75d  call    ?TryGetAttestationResults@CertificateCache@Client@HostGuardian@Microsoft@@QEAA_NV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@AEAV?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@6@@Z; Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults(std::vector<AttestationResultType>,std::wstring &,std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>> &)
0x18000d762  test    al, al
0x18000d764  jnz     short loc_18000D799
0x18000d766  mov     rbx, [rsp+148h+var_D0]
0x18000d76b  mov     [rsp+148h+var_110], rbx; struct AttestationResult **
0x18000d770  mov     [rsp+148h+var_118], r13; unsigned int *
0x18000d775  mov     [rsp+148h+var_120], rsi; wchar_t **
0x18000d77a  mov     [rsp+148h+var_128], r12; enum ShsAttestationFlag *
0x18000d77f  mov     r9, r14; enum AttestationResultType *
0x18000d782  mov     r8d, [rsp+148h+var_108]; unsigned int
0x18000d787  mov     rdx, [rsp+148h+pbstr]; wchar_t *
0x18000d78c  mov     rcx, r15; this
0x18000d78f  call    ?AttestForAllValues@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXQEA_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues(wchar_t * const,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)
0x18000d794  jmp     loc_18000D9FD
0x18000d799  mov     rbx, [rsp+148h+var_E8]
0x18000d79e  mov     rbx, [rbx]
0x18000d7a1  cmp     [rbx+19h], dil
0x18000d7a5  jnz     loc_18000D881
0x18000d7ab  mov     rcx, [rbx+28h]
0x18000d7af  call    ?GetDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@U_FILETIME@@@Z; Microsoft::HostGuardian::Client::Utilities::GetDurationStatus(_FILETIME)
0x18000d7b4  cmp     eax, 1
0x18000d7b7  jnz     short loc_18000D7FE
0x18000d7b9  mov     rcx, [rbx+10h]
0x18000d7bd  cmp     [rcx+19h], dil
0x18000d7c1  jz      short loc_18000D7E1
0x18000d7c3  mov     rax, [rbx+8]
0x18000d7c7  jmp     short loc_18000D7D6
0x18000d7c9  cmp     rbx, [rax+10h]
0x18000d7cd  jnz     short loc_18000D7DC
0x18000d7cf  mov     rbx, rax
0x18000d7d2  mov     rax, [rax+8]
0x18000d7d6  cmp     [rax+19h], dil
0x18000d7da  jz      short loc_18000D7C9
0x18000d7dc  mov     rbx, rax
0x18000d7df  jmp     short loc_18000D7A1
0x18000d7e1  mov     rbx, rcx
0x18000d7e4  mov     rcx, [rcx]
0x18000d7e7  cmp     [rcx+19h], dil
0x18000d7eb  jnz     short loc_18000D7A1
0x18000d7ed  mov     rbx, rcx
0x18000d7f0  mov     rax, [rcx]
0x18000d7f3  mov     rcx, rax
0x18000d7f6  cmp     [rax+19h], dil
0x18000d7fa  jz      short loc_18000D7ED
0x18000d7fc  jmp     short loc_18000D7A1
0x18000d7fe  mov     rbx, [rsp+148h+var_D0]
0x18000d803  mov     [rsp+148h+var_110], rbx; struct AttestationResult **
0x18000d808  mov     [rsp+148h+var_118], r13; unsigned int *
0x18000d80d  mov     [rsp+148h+var_120], rsi; wchar_t **
0x18000d812  mov     [rsp+148h+var_128], r12; enum ShsAttestationFlag *
0x18000d817  mov     r9, r14; enum AttestationResultType *
0x18000d81a  mov     r8d, [rsp+148h+var_108]; unsigned int
0x18000d81f  mov     rdx, [rsp+148h+pbstr]; wchar_t *
0x18000d824  mov     rcx, r15; this
0x18000d827  call    ?AttestForAllValues@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXQEA_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues(wchar_t * const,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)
0x18000d82c  nop
0x18000d82d  lea     rcx, [rsp+148h+var_E8]
0x18000d832  call    ??1?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18000d837  nop
0x18000d838  lea     rcx, [rsp+148h+psz]
0x18000d840  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d845  nop
0x18000d846  lea     rcx, [rsp+148h+var_C8]
0x18000d84e  call    ??1?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@XZ; std::vector<AttestationResultType>::~vector<AttestationResultType>(void)
0x18000d853  jmp     loc_18000DA23
0x18000d858  xor     edi, edi
0x18000d85a  mov     r15, [rsp+148h+var_98]
0x18000d862  mov     rsi, [rsp+148h+var_B0]
0x18000d86a  mov     r12, [rsp+148h+var_90]
0x18000d872  mov     r13, [rsp+148h+var_A8]
0x18000d87a  mov     rbx, [rsp+148h+var_100]
0x18000d87f  jmp     short loc_18000D886
0x18000d881  mov     rbx, [rsp+148h+var_D0]
0x18000d886  test    rsi, rsi
0x18000d889  jz      short loc_18000D8C1
0x18000d88b  cmp     [rsp+148h+var_78], rdi
0x18000d893  jz      short loc_18000D8C1
0x18000d895  lea     rcx, [rsp+148h+psz]
0x18000d89d  cmp     [rsp+148h+var_70], 7
0x18000d8a6  cmova   rcx, [rsp+148h+psz]; psz
0x18000d8af  call    cs:__imp_SysAllocString
0x18000d8b5  mov     [rsi], rax
0x18000d8b8  test    rax, rax
0x18000d8bb  jz      loc_18000DA6A
0x18000d8c1  mov     r9d, 2
0x18000d8c7  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, r9b
0x18000d8ce  jz      short loc_18000D904
0x18000d8d0  lea     rax, aFoundAllReques; "Found all requested certificates in cac"...
0x18000d8d7  mov     [rsp+148h+var_58], rax
0x18000d8df  mov     [rsp+148h+var_50], 72h ; 'r'
0x18000d8eb  lea     rax, [rsp+148h+var_68]
0x18000d8f3  mov     [rsp+148h+var_128], rax
0x18000d8f8  lea     rdx, ServiceDebugInformational
0x18000d8ff  call    McGenEventWrite_EventWriteTransfer
0x18000d904  mov     [rsp+148h+var_100], rdi
0x18000d909  mov     [rsp+148h+var_F8], rdi
0x18000d90e  lea     rax, [rsp+148h+var_100]
0x18000d913  mov     [rsp+148h+var_A8], rax
0x18000d91b  lea     rax, [rsp+148h+var_100]
0x18000d920  mov     [rsp+148h+var_A0], rax
0x18000d928  mov     ecx, 50h ; 'P'; Size
0x18000d92d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d932  mov     [rax], rax
0x18000d935  mov     [rax+8], rax
0x18000d939  mov     [rax+10h], rax
0x18000d93d  mov     word ptr [rax+18h], 101h
0x18000d943  mov     [rsp+148h+var_100], rax
0x18000d948  mov     r8, rax
0x18000d94b  mov     rdx, [rsp+148h+var_E8]
0x18000d950  mov     rdx, [rdx+8]
0x18000d954  lea     rcx, [rsp+148h+var_100]
0x18000d959  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,void *> *,std::_Tree_node<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,void *> *)
0x18000d95e  mov     rcx, [rsp+148h+var_100]
0x18000d963  mov     [rcx+8], rax
0x18000d967  mov     rax, [rsp+148h+var_E0]
0x18000d96c  mov     [rsp+148h+var_F8], rax
0x18000d971  mov     r8, [rsp+148h+var_100]
0x18000d976  mov     rdx, [r8+8]
0x18000d97a  cmp     [rdx+19h], dil
0x18000d97e  jnz     short loc_18000D9BA
0x18000d980  mov     rcx, [rdx]
0x18000d983  cmp     [rcx+19h], dil
0x18000d987  jnz     short loc_18000D998
0x18000d989  mov     rdx, rcx
0x18000d98c  mov     rax, [rcx]
0x18000d98f  mov     rcx, rax
0x18000d992  cmp     [rax+19h], dil
0x18000d996  jz      short loc_18000D989
0x18000d998  mov     [r8], rdx
0x18000d99b  mov     rdx, [rsp+148h+var_100]
0x18000d9a0  mov     rcx, [rdx+8]
0x18000d9a4  jmp     short loc_18000D9AA
0x18000d9a6  mov     rcx, [rcx+10h]
0x18000d9aa  mov     rax, [rcx+10h]
0x18000d9ae  cmp     [rax+19h], dil
0x18000d9b2  jz      short loc_18000D9A6
0x18000d9b4  mov     [rdx+10h], rcx
0x18000d9b8  jmp     short loc_18000D9C6
0x18000d9ba  mov     [r8], r8
0x18000d9bd  mov     rax, [rsp+148h+var_100]
0x18000d9c2  mov     [rax+10h], rax
0x18000d9c6  mov     [rsp+148h+var_A0], rdi
0x18000d9ce  lea     rcx, [rsp+148h+var_A8]
0x18000d9d6  call    ??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>>>(void)
0x18000d9db  mov     r9, rbx
0x18000d9de  mov     r8, r13
0x18000d9e1  lea     rdx, [rsp+148h+var_100]
0x18000d9e6  mov     rcx, r15
0x18000d9e9  call    ?CertMapToResults@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXV?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@std@@PEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::CertMapToResults(std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,uint *,AttestationResult * *)
0x18000d9ee  mov     rax, [rsp+148h+var_E8]
0x18000d9f3  mov     rcx, [rax]
0x18000d9f6  mov     eax, [rcx+48h]
0x18000d9f9  mov     [r12], eax
0x18000d9fd  lea     rcx, [rsp+148h+var_E8]
0x18000da02  call    ??1?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18000da07  nop
0x18000da08  lea     rcx, [rsp+148h+psz]
0x18000da10  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000da15  nop
0x18000da16  lea     rcx, [rsp+148h+var_C8]
0x18000da1e  call    ??1?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@XZ; std::vector<AttestationResultType>::~vector<AttestationResultType>(void)
  ... truncated ...
```
