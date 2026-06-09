# CCHlpConfigureNode(std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,ulong>>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::vector<uchar,std::allocator<uchar>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ulong *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &,bool,ulong)

- ea: `0x1800791d0`
- end: `0x1800795ca`
- name: `?CCHlpConfigureNode@@YAKV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@1AEAV?$vector@EV?$allocator@E@std@@@2@11111PEAKAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@_NK@Z`
- size: `1018`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task`

## callees

- `0x180002f50`
- `0x18000335c`
- `0x180003c44`
- `0x18001236c`
- `0x180013ae4`
- `0x18001cc08`
- `0x18001cf54`
- `0x18001ed18`
- `0x180028f30`
- `0x180029410`
- `0x1800294f0`
- `0x180029578`
- `0x180031728`
- `0x18003180c`
- `0x180031c44`
- `0x180031f74`
- `0x180032718`
- `0x180046478`
- `0x1800465e0`
- `0x1800474fc`
- `0x180078c2c`
- `0x180078fc4`
- `0x1800791d0`
- `0x18007ab58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079595`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800794b2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800794b2`

## string_xrefs

- `0x18007959e`: `Failed to start the cluster service on node %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CCHlpConfigureNode(
        wchar_t ***a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        BYTE *a10,
        __int64 *a11,
        int a12,
        unsigned int a13)
{
  wchar_t ***v14; // rsi
  unsigned int v15; // edi
  ClusNode *v16; // r14
  const wchar_t *v17; // rbx
  const wchar_t *v18; // rax
  ClusNode *v19; // rbx
  wchar_t **v20; // r10
  wchar_t *v21; // rdx
  __int64 v22; // r15
  wchar_t *v23; // r14
  const wchar_t *v24; // rax
  unsigned int v25; // edx
  __int64 result; // rax
  __int64 v27; // rbx
  DWORD LastError; // eax
  ClusRtl::ExceptionMsg *v29; // rbx
  wchar_t *v30; // [rsp+60h] [rbp-3B8h] BYREF
  char v31; // [rsp+68h] [rbp-3B0h]
  ClusNode *v32; // [rsp+70h] [rbp-3A8h]
  wchar_t ***v33; // [rsp+78h] [rbp-3A0h]
  __int64 v34; // [rsp+80h] [rbp-398h]
  BYTE *lpData; // [rsp+88h] [rbp-390h]
  __int64 v36; // [rsp+90h] [rbp-388h]
  __int64 v37; // [rsp+98h] [rbp-380h]
  __int64 v38; // [rsp+A0h] [rbp-378h]
  __int64 v39; // [rsp+A8h] [rbp-370h]
  __int64 *v40; // [rsp+B0h] [rbp-368h]
  _QWORD v41[2]; // [rsp+B8h] [rbp-360h] BYREF
  int v42; // [rsp+C8h] [rbp-350h]
  __int64 v43; // [rsp+CCh] [rbp-34Ch]
  int v44; // [rsp+D4h] [rbp-344h]
  __int64 v45; // [rsp+D8h] [rbp-340h]
  int v46[6]; // [rsp+E0h] [rbp-338h] BYREF
  ClusRtl::ExceptionMsg *v47; // [rsp+F8h] [rbp-320h] BYREF
  int v48[2]; // [rsp+100h] [rbp-318h] BYREF
  _BYTE v49[16]; // [rsp+120h] [rbp-2F8h] BYREF
  int v50[16]; // [rsp+130h] [rbp-2E8h] BYREF
  _BYTE v51[32]; // [rsp+170h] [rbp-2A8h] BYREF
  _BYTE v52[32]; // [rsp+190h] [rbp-288h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+1B0h] [rbp-268h] BYREF
  _BYTE v54[272]; // [rsp+2C0h] [rbp-158h] BYREF

  v34 = a3;
  v14 = a1;
  v33 = a1;
  v39 = a6;
  v38 = a7;
  v37 = a8;
  v36 = a9;
  lpData = a10;
  v40 = a11;
  std::wstring::wstring(v52);
  v15 = 0;
  v32 = 0;
  std::wstring::wstring(v51);
  ClusterGlobalData::ClusterGlobalData((ClusterGlobalData *)v49);
  try
  {
    ClusterGlobalData::Initialize((ClusterGlobalData *)v49);
    v20 = *v14;
    v21 = **v14;
    v30 = v21;
    while ( v21 != (wchar_t *)v20 )
    {
      if ( *((_DWORD *)v21 + 16) == a13 )
      {
        std::wstring::operator=(v51, v21 + 16);
        break;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>,std::_Iterator_base0>::operator++(&v30);
      v21 = v30;
    }
    std::vector<_GUID>::vector<_GUID>(v46);
    CCHlpBuildMultiSzNodeMap(v14, v46);
    v41[0] = get_startup_argv_mode;
    v41[1] = 0;
    v42 = 1;
    v43 = 1;
    v44 = 1;
    v45 = 0;
    v16 = (ClusNode *)operator new(0xF0u);
    v30 = (wchar_t *)v16;
    v17 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v51);
    v18 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    v19 = ClusNode::ClusNode(v16, (struct PhaseManager *)v41, v18, v17, v17, a13, (struct ClusterGlobalData *)v49);
    v32 = v19;
    if ( !v19 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        14,
        L"Out of Memory when instantiating cluster node object. ");
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    v22 = 15436;
    std::vector<unsigned char>::vector<unsigned char>(v48, 15436);
    v23 = *(wchar_t **)v48;
    v30 = *(wchar_t **)v48;
    v31 = 0;
    v24 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
    StringCchCopyW(v23 + 7684, 0x21u, v24);
    ClusNode::ConfigureNode(
      (PhaseManager **)v19,
      (__int64)v46,
      (__int64)v50,
      (struct _CLUSTER_CERT *)v23,
      0,
      0,
      0,
      v50[12],
      0,
      lpData,
      0,
      0xEu);
    ClusNode::SetClusterServiceRegistries((__int64)v19, v40, a5, v39, v38, v37, v36);
    if ( !StartServiceW(*((SC_HANDLE *)v19 + 16), 0, 0) )
    {
      v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)v19 + 48);
      LastError = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v54,
        LastError,
        L"Failed to start the cluster service on node %ws",
        v27);
      throw (ClusRtl::ExceptionMsg *)v54;
    }
    do
    {
      *(_BYTE *)v23 = 0;
      v23 = (wchar_t *)((char *)v23 + 1);
      --v22;
    }
    while ( v22 );
    std::vector<unsigned char>::_Tidy(v48);
    std::vector<wchar_t>::_Tidy(v46);
  }
  catch ( ClusRtl::ExceptionMsg *v47 )
  {
    v29 = v47;
    TraceMsg(
      2,
      0,
      L"CCHlpConfigureNode",
      932,
      L"Create cluster helper configure node exception - Error %d. Message: %ws",
      *((_DWORD *)v47 + 64),
      v47);
    LODWORD(v30) = *((_DWORD *)v29 + 64);
    v19 = v32;
    v15 = (unsigned int)v30;
    v14 = v33;
    if ( v32 )
      goto LABEL_12;
LABEL_13:
    ClusterGlobalData::~ClusterGlobalData((ClusterGlobalData *)v49);
    std::wstring::_Tidy_deallocate(v51);
    std::wstring::_Tidy_deallocate(v52);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v14);
    result = v15;
  }
LABEL_12:
  ClusNode::`scalar deleting destructor'(v19, v25);
  goto LABEL_13;
}

```

## disassembly

```asm
0x1800791d0  push    rbx
0x1800791d2  push    rsi
0x1800791d3  push    rdi
0x1800791d4  push    r12
0x1800791d6  push    r13
0x1800791d8  push    r14
0x1800791da  push    r15
0x1800791dc  sub     rsp, 3E0h
0x1800791e3  mov     rax, cs:__security_cookie
0x1800791ea  xor     rax, rsp
0x1800791ed  mov     [rsp+418h+var_48], rax
0x1800791f5  mov     rbx, r9
0x1800791f8  mov     [rsp+418h+var_398], r8
0x180079200  mov     r12, rdx
0x180079203  mov     rsi, rcx
0x180079206  mov     [rsp+418h+var_3A0], rcx
0x18007920b  mov     r13, [rsp+418h+arg_20]
0x180079213  mov     rax, [rsp+418h+arg_28]
0x18007921b  mov     [rsp+418h+var_370], rax
0x180079223  mov     rax, [rsp+418h+arg_30]
0x18007922b  mov     [rsp+418h+var_378], rax
0x180079233  mov     rax, [rsp+418h+arg_38]
0x18007923b  mov     [rsp+418h+var_380], rax
0x180079243  mov     rax, [rsp+418h+arg_40]
0x18007924b  mov     [rsp+418h+var_388], rax
0x180079253  mov     rax, [rsp+418h+arg_48]
0x18007925b  mov     [rsp+418h+var_390], rax
0x180079263  mov     rax, [rsp+418h+arg_50]
0x18007926b  mov     [rsp+418h+var_368], rax
0x180079273  mov     r15d, [rsp+418h+arg_60]
0x18007927b  lea     rcx, [rsp+418h+var_288]
0x180079283  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180079288  nop
0x180079289  xor     edi, edi
0x18007928b  mov     [rsp+418h+var_3A8], rdi
0x180079290  lea     rcx, [rsp+418h+var_2A8]
0x180079298  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007929d  nop
0x18007929e  lea     rcx, [rsp+418h+var_2F8]; this
0x1800792a6  call    ??0ClusterGlobalData@@QEAA@XZ; ClusterGlobalData::ClusterGlobalData(void)
0x1800792ab  nop
0x1800792ac  mov     r8, rbx
0x1800792af  mov     edx, [rsi+8]
0x1800792b2  lea     rcx, [rsp+418h+var_2F8]; this
0x1800792ba  call    ?Initialize@ClusterGlobalData@@QEAAXKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; ClusterGlobalData::Initialize(ulong,std::vector<uchar> &)
0x1800792bf  mov     r10, [rsi]
0x1800792c2  mov     rdx, [r10]
0x1800792c5  mov     [rsp+418h+var_3B8], rdx
0x1800792ca  cmp     rdx, r10
0x1800792cd  jz      short loc_1800792EA
0x1800792cf  cmp     [rdx+40h], r15d
0x1800792d3  jnz     loc_1800793B3
0x1800792d9  add     rdx, 20h ; ' '
0x1800792dd  lea     rcx, [rsp+418h+var_2A8]
0x1800792e5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800792ea  lea     rcx, [rsp+418h+var_338]
0x1800792f2  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800792f7  nop
0x1800792f8  lea     rdx, [rsp+418h+var_338]
0x180079300  mov     rcx, rsi
0x180079303  call    ?CCHlpBuildMultiSzNodeMap@@YAXAEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAV?$vector@_WV?$allocator@_W@std@@@2@@Z; CCHlpBuildMultiSzNodeMap(std::map<std::wstring,ulong> &,std::vector<wchar_t> &)
0x180079308  lea     rax, _get_startup_argv_mode
0x18007930f  mov     [rsp+418h+var_360], rax
0x180079317  mov     [rsp+418h+var_358], rdi
0x18007931f  mov     [rsp+418h+var_350], 1
0x18007932a  mov     [rsp+418h+var_34C], 1
0x180079336  mov     [rsp+418h+var_344], 1
0x180079341  mov     [rsp+418h+var_340], rdi
0x180079349  mov     ecx, 0F0h; Size
0x18007934e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079353  mov     r14, rax
0x180079356  mov     [rsp+418h+var_3B8], rax
0x18007935b  lea     rcx, [rsp+418h+var_2A8]
0x180079363  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180079368  mov     rbx, rax
0x18007936b  mov     rcx, r12
0x18007936e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180079373  lea     rcx, [rsp+418h+var_2F8]
0x18007937b  mov     [rsp+418h+var_3E8], rcx; struct ClusterGlobalData *
0x180079380  mov     [rsp+418h+var_3F0], r15d; unsigned int
0x180079385  mov     [rsp+418h+var_3F8], rbx; wchar_t *
0x18007938a  mov     r9, rbx; wchar_t *
0x18007938d  mov     r8, rax; wchar_t *
0x180079390  lea     rdx, [rsp+418h+var_360]; struct PhaseManager *
0x180079398  mov     rcx, r14; this
0x18007939b  call    ??0ClusNode@@QEAA@AEAVPhaseManager@@PEB_W11KAEAVClusterGlobalData@@@Z; ClusNode::ClusNode(PhaseManager &,wchar_t const *,wchar_t const *,wchar_t const *,ulong,ClusterGlobalData &)
0x1800793a0  mov     rbx, rax
0x1800793a3  mov     [rsp+418h+var_3A8], rax
0x1800793a8  test    rax, rax
0x1800793ab  jz      loc_18007955D
0x1800793b1  jmp     short loc_1800793C7
0x1800793b3  lea     rcx, [rsp+418h+var_3B8]
0x1800793b8  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x1800793bd  mov     rdx, [rsp+418h+var_3B8]
0x1800793c2  jmp     loc_1800792CA
0x1800793c7  mov     r15d, 3C4Ch
0x1800793cd  mov     edx, r15d
0x1800793d0  lea     rcx, [rsp+418h+var_318]
0x1800793d8  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800793dd  nop
0x1800793de  mov     r14, qword ptr [rsp+418h+var_318]
0x1800793e6  mov     [rsp+418h+var_3B8], r14
0x1800793eb  mov     [rsp+418h+var_3B0], dil
0x1800793f0  mov     rcx, [rsp+418h+var_398]
0x1800793f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800793fd  lea     rcx, [r14+3C08h]; wchar_t *
0x180079404  mov     r8, rax; wchar_t *
0x180079407  mov     edx, 21h ; '!'; unsigned __int64
0x18007940c  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180079411  mov     [rsp+418h+var_3C0], 0Eh; __int16
0x180079418  mov     [rsp+418h+var_3C8], dil; char
0x18007941d  mov     rax, [rsp+418h+var_390]
0x180079425  mov     [rsp+418h+lpData], rax; lpData
0x18007942a  mov     [rsp+418h+var_3D8], dil; char
0x18007942f  mov     eax, [rsp+418h+var_2B8]
0x180079436  mov     [rsp+418h+var_3E0], eax; unsigned int
0x18007943a  mov     [rsp+418h+var_3E8], rdi; __int64
0x18007943f  mov     qword ptr [rsp+418h+var_3F0], rdi; __int64
0x180079444  mov     [rsp+418h+var_3F8], rdi; __int64
0x180079449  mov     r9, r14; int
0x18007944c  lea     r8, [rsp+418h+var_2E8]; int
0x180079454  lea     rdx, [rsp+418h+var_338]; int
0x18007945c  mov     rcx, rbx; int
0x18007945f  call    ?ConfigureNode@ClusNode@@QEAAXAEAV?$vector@_WV?$allocator@_W@std@@@std@@AEBV?$vector@EV?$allocator@E@std@@@3@PEAU_CLUSTER_CERT@@222K_NPEAK3G@Z; ClusNode::ConfigureNode(std::vector<wchar_t> &,std::vector<uchar> const &,_CLUSTER_CERT *,_CLUSTER_CERT *,_CLUSTER_CERT *,_CLUSTER_CERT *,ulong,bool,ulong *,bool,ushort)
0x180079464  mov     rax, [rsp+418h+var_388]
0x18007946c  mov     [rsp+418h+var_3E8], rax
0x180079471  mov     rax, [rsp+418h+var_380]
0x180079479  mov     qword ptr [rsp+418h+var_3F0], rax
0x18007947e  mov     rax, [rsp+418h+var_378]
0x180079486  mov     [rsp+418h+var_3F8], rax
0x18007948b  mov     r9, [rsp+418h+var_370]
0x180079493  mov     r8, r13
0x180079496  mov     rdx, [rsp+418h+var_368]
0x18007949e  mov     rcx, rbx
0x1800794a1  call    ?SetClusterServiceRegistries@ClusNode@@QEAAXAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@1111@Z; ClusNode::SetClusterServiceRegistries(std::vector<std::wstring> const &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x1800794a6  xor     r8d, r8d; lpServiceArgVectors
0x1800794a9  xor     edx, edx; dwNumServiceArgs
0x1800794ab  mov     rcx, [rbx+80h]; hService
0x1800794b2  call    cs:__imp_StartServiceW
0x1800794b8  test    eax, eax
0x1800794ba  jz      loc_180079589
0x1800794c0  mov     [r14], dil
0x1800794c3  inc     r14
0x1800794c6  sub     r15, 1
0x1800794ca  jnz     short loc_1800794C0
0x1800794cc  lea     rcx, [rsp+418h+var_318]
0x1800794d4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800794d9  nop
0x1800794da  lea     rcx, [rsp+418h+var_338]
0x1800794e2  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x1800794e7  nop
0x1800794e8  jmp     short loc_1800794FD
0x1800794ea  mov     rbx, [rsp+418h+var_3A8]
0x1800794ef  mov     edi, dword ptr [rsp+418h+var_3B8]
0x1800794f3  mov     rsi, [rsp+418h+var_3A0]
0x1800794f8  test    rbx, rbx
0x1800794fb  jz      short loc_180079506
0x1800794fd  mov     rcx, rbx; this
0x180079500  call    ??_GClusNode@@QEAAPEAXI@Z; ClusNode::`scalar deleting destructor'(uint)
0x180079505  nop
0x180079506  lea     rcx, [rsp+418h+var_2F8]; this
0x18007950e  call    ??1ClusterGlobalData@@QEAA@XZ; ClusterGlobalData::~ClusterGlobalData(void)
0x180079513  nop
0x180079514  lea     rcx, [rsp+418h+var_2A8]
0x18007951c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180079521  nop
0x180079522  lea     rcx, [rsp+418h+var_288]
0x18007952a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007952f  nop
0x180079530  mov     rcx, rsi
0x180079533  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(void)
0x180079538  mov     eax, edi
0x18007953a  mov     rcx, [rsp+418h+var_48]
0x180079542  xor     rcx, rsp; StackCookie
0x180079545  call    __security_check_cookie
0x18007954a  add     rsp, 3E0h
0x180079551  pop     r15
0x180079553  pop     r14
0x180079555  pop     r13
0x180079557  pop     r12
0x180079559  pop     rdi
0x18007955a  pop     rsi
0x18007955b  pop     rbx
0x18007955c  retn
0x18007955d  lea     r8, aOutOfMemoryWhe; "Out of Memory when instantiating cluste"...
0x180079564  lea     edx, [rax+0Eh]; int
0x180079567  lea     rcx, [rsp+418h+pExceptionObject]; this
0x18007956f  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180079574  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18007957b  lea     rcx, [rsp+418h+pExceptionObject]; pExceptionObject
0x180079583  call    _CxxThrowException_0
0x180079589  lea     rcx, [rbx+30h]
0x18007958d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180079592  mov     rbx, rax
0x180079595  call    cs:__imp_GetLastError
0x18007959b  mov     r9, rbx
0x18007959e  lea     r8, aFailedToStartT; "Failed to start the cluster service on "...
0x1800795a5  mov     edx, eax; int
0x1800795a7  lea     rcx, [rsp+418h+var_158]; this
0x1800795af  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800795b4  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x1800795bb  lea     rcx, [rsp+418h+var_158]; pExceptionObject
0x1800795c3  call    _CxxThrowException_0
```
