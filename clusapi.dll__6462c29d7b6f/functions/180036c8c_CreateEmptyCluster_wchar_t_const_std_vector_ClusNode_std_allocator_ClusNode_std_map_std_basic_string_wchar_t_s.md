# CreateEmptyCluster(wchar_t const *,std::vector<ClusNode *,std::allocator<ClusNode *>> &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,ulong>>> &,ClusterGlobalData &,PhaseManager &,ulong,bool,ushort,ulong *)

- ea: `0x180036c8c`
- end: `0x180037270`
- name: `?CreateEmptyCluster@@YAPEAU_HCLUSTER@@PEB_WAEAV?$vector@PEAVClusNode@@V?$allocator@PEAVClusNode@@@std@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@3@AEAVClusterGlobalData@@AEAVPhaseManager@@K_NGPEAK@Z`
- size: `1508`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18003359c`

## callees

- `0x1800012bc`
- `0x1800012f0`
- `0x180002f50`
- `0x180003c44`
- `0x1800144f0`
- `0x18001cc2c`
- `0x18001cf54`
- `0x180028f30`
- `0x180029410`
- `0x1800294f0`
- `0x180029578`
- `0x18003180c`
- `0x18003219c`
- `0x180036c8c`
- `0x180038cdc`
- `0x180038e50`
- `0x18003baf8`
- `0x18003f638`
- `0x180046388`
- `0x1800465e0`
- `0x18006ee70`
- `0x18006f06c`
- `0x18006f22c`
- `0x180078fc4`
- `0x180094538`
- `0x1800a10f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003723b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003723b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800370e8`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800370e8`

## string_xrefs

- `0x180037166`: `Failed to create Cluster Secret`
- `0x180037190`: `Failed to create Cluster Cert`
- `0x1800371bb`: `Failed to create Cluster LM Cert`
- `0x180037244`: `Failed to start the cluster service on node %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CreateEmptyCluster(
        const WCHAR *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        PhaseManager *a5,
        int a6,
        char a7,
        unsigned __int16 a8,
        _DWORD *a9)
{
  __int64 v10; // rdi
  struct _CLUSTER_CERT *v11; // rsi
  struct _CLUSTER_CERT *v12; // rbx
  int RandomBytes; // eax
  const wchar_t *v14; // rax
  int ClusterCert; // eax
  struct _CLUSTER_CERT *v16; // r15
  struct _CLUSTER_CERT *v17; // r12
  unsigned __int16 v18; // r8
  const wchar_t *v19; // rax
  int ClusterLMUSRCert; // eax
  unsigned __int64 v21; // r10
  _QWORD *v22; // rcx
  rsize_t v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rcx
  __int64 v30; // rax
  _QWORD *v31; // rbx
  _QWORD *v32; // r13
  PhaseManager *v33; // rbx
  const WCHAR *v34; // r13
  __int64 v35; // r8
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  struct _CLUSTER_CERT *v40; // rax
  const wchar_t *v41; // rax
  DWORD v43; // eax
  ClusNode **v44; // rax
  const wchar_t *NodeName; // rbx
  DWORD LastError; // eax
  ClusRtl::ExceptionMsg *v47; // rdx
  _QWORD *v48; // [rsp+60h] [rbp-6E8h] BYREF
  BYTE Data[4]; // [rsp+68h] [rbp-6E0h] BYREF
  int v50; // [rsp+6Ch] [rbp-6DCh] BYREF
  unsigned __int64 v51; // [rsp+70h] [rbp-6D8h]
  PhaseManager *v52; // [rsp+78h] [rbp-6D0h]
  __int64 v53; // [rsp+80h] [rbp-6C8h]
  __int128 *p_Destination; // [rsp+88h] [rbp-6C0h] BYREF
  const WCHAR *v55; // [rsp+90h] [rbp-6B8h]
  struct _CLUSTER_CERT *v56; // [rsp+98h] [rbp-6B0h]
  _DWORD *v57; // [rsp+A0h] [rbp-6A8h]
  void *Source[2]; // [rsp+A8h] [rbp-6A0h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-690h]
  int v60[4]; // [rsp+C0h] [rbp-688h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-678h]
  ClusRtl::ExceptionMsg *v62[3]; // [rsp+D8h] [rbp-670h] BYREF
  char v63; // [rsp+F0h] [rbp-658h]
  struct _CLUSTER_CERT *v64; // [rsp+F8h] [rbp-650h]
  struct _CLUSTER_CERT *v65; // [rsp+100h] [rbp-648h]
  char v66; // [rsp+108h] [rbp-640h]
  struct _CLUSTER_CERT *v67[3]; // [rsp+110h] [rbp-638h] BYREF
  struct _CLUSTER_CERT *v68[3]; // [rsp+128h] [rbp-620h] BYREF
  struct _CLUSTER_CERT *v69[3]; // [rsp+140h] [rbp-608h] BYREF
  struct _CLUSTER_CERT *v70[3]; // [rsp+158h] [rbp-5F0h] BYREF
  char v71[16]; // [rsp+170h] [rbp-5D8h] BYREF
  __int128 Destination; // [rsp+180h] [rbp-5C8h] BYREF
  _BYTE v73[32]; // [rsp+190h] [rbp-5B8h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+1B0h] [rbp-598h] BYREF
  _BYTE v75[272]; // [rsp+2C0h] [rbp-488h] BYREF
  _BYTE v76[272]; // [rsp+3D0h] [rbp-378h] BYREF
  _BYTE v77[272]; // [rsp+4E0h] [rbp-268h] BYREF
  _BYTE v78[272]; // [rsp+5F0h] [rbp-158h] BYREF

  try
  {
    v48 = a4;
    v55 = a1;
    v52 = a5;
    v57 = a9;
    v53 = 0;
    *(_OWORD *)Source = 0;
    v59 = 0;
    Destination = 0;
    *a9 = 0;
    *(_OWORD *)v60 = 0;
    v61 = 0;
    CCHlpBuildMultiSzNodeMap(a3, v60);
    *(_DWORD *)Data = a6 | 0x10000000;
    v10 = 15436;
    std::vector<unsigned char>::vector<unsigned char>(v70, 15436);
    std::vector<unsigned char>::vector<unsigned char>(v69, 15436);
    v11 = v70[0];
    v12 = v69[0];
    v56 = v69[0];
    v62[1] = v70[0];
    v62[2] = v69[0];
    v63 = 0;
    RandomBytes = ClRtlGenerateRandomBytes((BYTE *)v70[0] + 15368);
    if ( RandomBytes )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        RandomBytes,
        L"Failed to create Cluster Secret");
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    v14 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(**(_QWORD **)a2 + 48LL);
    ClusterCert = GenerateClusterCert(v14, v11, v12);
    if ( ClusterCert != -2147023151 && ClusterCert )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v75, ClusterCert, L"Failed to create Cluster Cert");
      throw (ClusRtl::ExceptionMsg *)v75;
    }
    std::vector<unsigned char>::vector<unsigned char>(v68, 15436);
    std::vector<unsigned char>::vector<unsigned char>(v67, 15436);
    v16 = v68[0];
    v17 = v67[0];
    v64 = v68[0];
    v65 = v67[0];
    v66 = 0;
    v18 = a8;
    if ( a8 >= 0xCu )
    {
      v19 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(**(_QWORD **)a2 + 48LL);
      ClusterLMUSRCert = GenerateClusterLMUSRCert(v19, v16, v17);
      if ( ClusterLMUSRCert )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v76,
          ClusterLMUSRCert,
          L"Failed to create Cluster LM Cert");
        throw (ClusRtl::ExceptionMsg *)v76;
      }
      v18 = a8;
    }
    v21 = 0;
    while ( 1 )
    {
      v51 = v21;
      v22 = *(_QWORD **)a2;
      if ( v21 >= (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3 )
        break;
      ClusNode::ConfigureNode(
        (PhaseManager **)v22[v21],
        (__int64)v60,
        (__int64)(v48 + 2),
        v11,
        v12,
        v16,
        v17,
        *((_DWORD *)v48 + 16),
        a7,
        Data,
        0,
        v18);
      std::vector<unsigned char>::operator=(Source, v48 + 2);
      if ( (void *)((char *)Source[1] - (char *)Source[0]) == (void *)16 )
      {
        memcpy_s_0(&Destination, (const rsize_t)Source[0], Source[0], v23);
      }
      else
      {
        std::wstring::wstring(v73, Source[0]);
        Destination = *(_OWORD *)cxl::Guid::Guid(v71, v73);
        std::wstring::_Tidy_deallocate(v73);
      }
      if ( (unsigned int)dword_18011D048 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(v25, v24, v26) )
        {
          v29 = *(_QWORD *)(*(_QWORD *)a2 + 8 * v51);
          v50 = *(_DWORD *)(v29 + 112);
          p_Destination = &Destination;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v29,
            (unsigned int)&dword_18010612C,
            v27,
            v28,
            (__int64)&p_Destination,
            (__int64)&v50);
        }
      }
      v21 = v51 + 1;
      v18 = a8;
    }
    v30 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*v22 + 48LL);
    PhaseManager::StartPhase(a5, 105, v30);
    v31 = *(_QWORD **)a2;
    while ( 1 )
    {
      v32 = v31;
      v48 = v31;
      if ( v31 == *(_QWORD **)(a2 + 8) )
        break;
      if ( !StartServiceW(*(SC_HANDLE *)(*v31 + 128LL), 0, 0) )
      {
        v44 = (ClusNode **)std::unique_ptr<cxl::Exception>::operator->(&v48);
        NodeName = ClusNode::GetNodeName(*v44);
        LastError = GetLastError();
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v78,
          LastError,
          L"Failed to start the cluster service on node %ws",
          NodeName);
        throw (ClusRtl::ExceptionMsg *)v78;
      }
      ++v31;
      if ( v32 + 1 != *(_QWORD **)(a2 + 8) )
      {
        v41 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*v31 + 48LL);
        PhaseManager::ContinuePhase(v52, v41, 0, ClusterSetupPhaseInformational);
      }
    }
    v33 = v52;
    PhaseManager::EndPhase(v52, 0, ClusterSetupPhaseInformational);
    v34 = v55;
    PhaseManager::StartPhase(v33, 200, v55);
    v36 = WaitForNodeUp(v33, 0, v35, a2);
    v53 = v36;
    if ( !v36 )
    {
      if ( !v34 )
        v34 = &base;
      v43 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v77,
        v43,
        L"Failed to get cluster handle for cluster %ws as no node is UP.",
        v34);
      throw (ClusRtl::ExceptionMsg *)v77;
    }
    PhaseManager::EndPhase(v52, 0, ClusterSetupPhaseInformational);
    v37 = 15436;
    do
    {
      *(_BYTE *)v16 = 0;
      v16 = (struct _CLUSTER_CERT *)((char *)v16 + 1);
      --v37;
    }
    while ( v37 );
    v38 = 15436;
    do
    {
      *(_BYTE *)v17 = 0;
      v17 = (struct _CLUSTER_CERT *)((char *)v17 + 1);
      --v38;
    }
    while ( v38 );
    std::vector<unsigned char>::_Tidy(v67);
    std::vector<unsigned char>::_Tidy(v68);
    v39 = 15436;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (struct _CLUSTER_CERT *)((char *)v11 + 1);
      --v39;
    }
    while ( v39 );
    v40 = v56;
    do
    {
      *(_BYTE *)v40 = 0;
      v40 = (struct _CLUSTER_CERT *)((char *)v40 + 1);
      --v10;
    }
    while ( v10 );
    std::vector<unsigned char>::_Tidy(v69);
    std::vector<unsigned char>::_Tidy(v70);
    std::vector<wchar_t>::_Tidy(v60);
  }
  catch ( ClusRtl::ExceptionMsg *v62 )
  {
    v47 = v62[0];
    *v57 = *((_DWORD *)v62[0] + 64);
    TraceMsg(
      2,
      0,
      L"CreateEmptyCluster",
      1776,
      L"Create cluster exception - Error %d. Message: %ws",
      *((_DWORD *)v47 + 64),
      v47);
    v36 = v53;
  }
  std::vector<unsigned char>::_Tidy(Source);
  return v36;
}

```

## disassembly

```asm
0x180036c8c  push    rbx
0x180036c8e  push    rsi
0x180036c8f  push    rdi
0x180036c90  push    r12
0x180036c92  push    r13
0x180036c94  push    r14
0x180036c96  push    r15
0x180036c98  sub     rsp, 710h
0x180036c9f  mov     rax, cs:__security_cookie
0x180036ca6  xor     rax, rsp
0x180036ca9  mov     [rsp+748h+var_48], rax
0x180036cb1  mov     [rsp+748h+var_6E8], r9
0x180036cb6  mov     r14, rdx
0x180036cb9  mov     [rsp+748h+var_6B8], rcx
0x180036cc1  mov     r13, [rsp+748h+arg_20]
0x180036cc9  mov     [rsp+748h+var_6D0], r13
0x180036cce  mov     rax, [rsp+748h+arg_40]
0x180036cd6  mov     [rsp+748h+var_6A8], rax
0x180036cde  xor     r15d, r15d
0x180036ce1  mov     [rsp+748h+var_6C8], r15
0x180036ce9  xorps   xmm0, xmm0
0x180036cec  movdqu  xmmword ptr [rsp+748h+Source], xmm0
0x180036cf5  mov     [rsp+748h+var_690], r15
0x180036cfd  movups  [rsp+748h+Destination], xmm0
0x180036d05  mov     [rax], r15d
0x180036d08  movdqu  xmmword ptr [rsp+748h+var_688], xmm0
0x180036d11  mov     [rsp+748h+var_678], r15
0x180036d19  lea     rdx, [rsp+748h+var_688]
0x180036d21  mov     rcx, r8
0x180036d24  call    ?CCHlpBuildMultiSzNodeMap@@YAXAEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAV?$vector@_WV?$allocator@_W@std@@@2@@Z; CCHlpBuildMultiSzNodeMap(std::map<std::wstring,ulong> &,std::vector<wchar_t> &)
0x180036d29  mov     eax, [rsp+748h+arg_28]
0x180036d30  bts     eax, 1Ch
0x180036d34  mov     dword ptr [rsp+748h+Data], eax
0x180036d38  mov     edi, 3C4Ch
0x180036d3d  mov     edx, edi
0x180036d3f  lea     rcx, [rsp+748h+var_5F0]
0x180036d47  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180036d4c  nop
0x180036d4d  mov     edx, edi
0x180036d4f  lea     rcx, [rsp+748h+var_608]
0x180036d57  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180036d5c  nop
0x180036d5d  mov     rsi, [rsp+748h+var_5F0]
0x180036d65  mov     rbx, [rsp+748h+var_608]
0x180036d6d  mov     [rsp+748h+var_6B0], rbx
0x180036d75  mov     [rsp+748h+var_668], rsi
0x180036d7d  mov     [rsp+748h+var_660], rbx
0x180036d85  mov     [rsp+748h+var_658], r15b
0x180036d8d  lea     rcx, [rsi+3C08h]; pbBuffer
0x180036d94  lea     edx, [r15+20h]
0x180036d98  call    ClRtlGenerateRandomBytes
0x180036d9d  test    eax, eax
0x180036d9f  jnz     loc_180037166
0x180036da5  mov     rax, [r14]
0x180036da8  mov     rcx, [rax]
0x180036dab  add     rcx, 30h ; '0'
0x180036daf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036db4  mov     r8, rbx; struct _CLUSTER_CERT *
0x180036db7  mov     rdx, rsi; struct _CLUSTER_CERT *
0x180036dba  mov     rcx, rax; wchar_t *
0x180036dbd  call    ?GenerateClusterCert@@YAJPEB_WPEAU_CLUSTER_CERT@@1@Z; GenerateClusterCert(wchar_t const *,_CLUSTER_CERT *,_CLUSTER_CERT *)
0x180036dc2  cmp     eax, 800706D1h
0x180036dc7  jz      short loc_180036DD1
0x180036dc9  test    eax, eax
0x180036dcb  jnz     loc_180037190
0x180036dd1  mov     rdx, rdi
0x180036dd4  lea     rcx, [rsp+748h+var_620]
0x180036ddc  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180036de1  nop
0x180036de2  mov     rdx, rdi
0x180036de5  lea     rcx, [rsp+748h+var_638]
0x180036ded  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180036df2  nop
0x180036df3  mov     r15, [rsp+748h+var_620]
0x180036dfb  mov     r12, [rsp+748h+var_638]
0x180036e03  mov     [rsp+748h+var_650], r15
0x180036e0b  mov     [rsp+748h+var_648], r12
0x180036e13  mov     [rsp+748h+var_640], 0
0x180036e1b  movzx   r8d, [rsp+748h+arg_38]
0x180036e24  cmp     r8w, 0Ch
0x180036e29  jb      short loc_180036E59
0x180036e2b  mov     rax, [r14]
0x180036e2e  mov     rcx, [rax]
0x180036e31  add     rcx, 30h ; '0'
0x180036e35  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036e3a  mov     r8, r12; struct _CLUSTER_CERT *
0x180036e3d  mov     rdx, r15; struct _CLUSTER_CERT *
0x180036e40  mov     rcx, rax; wchar_t *
0x180036e43  call    ?GenerateClusterLMUSRCert@@YAJPEB_WPEAU_CLUSTER_CERT@@1@Z; GenerateClusterLMUSRCert(wchar_t const *,_CLUSTER_CERT *,_CLUSTER_CERT *)
0x180036e48  test    eax, eax
0x180036e4a  jnz     loc_1800371BB
0x180036e50  movzx   r8d, [rsp+748h+arg_38]
0x180036e59  xor     r10d, r10d
0x180036e5c  mov     [rsp+748h+var_6D8], r10
0x180036e61  mov     rcx, [r14]
0x180036e64  mov     rax, [r14+8]
0x180036e68  sub     rax, rcx
0x180036e6b  sar     rax, 3
0x180036e6f  cmp     r10, rax
0x180036e72  jnb     loc_180036FBC
0x180036e78  mov     r9, [rsp+748h+var_6E8]
0x180036e7d  lea     rdx, [r9+10h]
0x180036e81  mov     [rsp+748h+var_6F0], r8w; __int16
0x180036e87  mov     [rsp+748h+var_6F8], 0; char
0x180036e8c  lea     rax, [rsp+748h+Data]
0x180036e91  mov     [rsp+748h+lpData], rax; lpData
0x180036e96  mov     al, [rsp+748h+arg_30]
0x180036e9d  mov     [rsp+748h+var_708], al; char
0x180036ea1  mov     eax, [r9+40h]
0x180036ea5  mov     [rsp+748h+var_710], eax; unsigned int
0x180036ea9  mov     [rsp+748h+var_718], r12; __int64
0x180036eae  mov     [rsp+748h+var_720], r15; __int64
0x180036eb3  mov     [rsp+748h+var_728], rbx; __int64
0x180036eb8  mov     r9, rsi; int
0x180036ebb  mov     r8, rdx; int
0x180036ebe  lea     rdx, [rsp+748h+var_688]; int
0x180036ec6  mov     rcx, [rcx+r10*8]; int
0x180036eca  call    ?ConfigureNode@ClusNode@@QEAAXAEAV?$vector@_WV?$allocator@_W@std@@@std@@AEBV?$vector@EV?$allocator@E@std@@@3@PEAU_CLUSTER_CERT@@222K_NPEAK3G@Z; ClusNode::ConfigureNode(std::vector<wchar_t> &,std::vector<uchar> const &,_CLUSTER_CERT *,_CLUSTER_CERT *,_CLUSTER_CERT *,_CLUSTER_CERT *,ulong,bool,ulong *,bool,ushort)
0x180036ecf  mov     rdx, [rsp+748h+var_6E8]
0x180036ed4  add     rdx, 10h
0x180036ed8  lea     rcx, [rsp+748h+Source]
0x180036ee0  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x180036ee5  mov     rax, [rsp+748h+Source+8]
0x180036eed  mov     rdx, [rsp+748h+Source]; DestinationSize
0x180036ef5  sub     rax, rdx
0x180036ef8  cmp     rax, 10h
0x180036efc  jnz     short loc_180036F10
0x180036efe  mov     r8, rdx; Source
0x180036f01  lea     rcx, [rsp+748h+Destination]; Destination
0x180036f09  call    memcpy_s_0
0x180036f0e  jmp     short loc_180036F4C
0x180036f10  lea     rcx, [rsp+748h+var_5B8]
0x180036f18  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180036f1d  nop
0x180036f1e  lea     rdx, [rsp+748h+var_5B8]
0x180036f26  lea     rcx, [rsp+748h+var_5D8]
0x180036f2e  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x180036f33  movups  xmm0, xmmword ptr [rax]
0x180036f36  movdqu  [rsp+748h+Destination], xmm0
0x180036f3f  lea     rcx, [rsp+748h+var_5B8]
0x180036f47  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036f4c  mov     eax, cs:dword_18011D048
0x180036f52  cmp     eax, 5
0x180036f55  jbe     short loc_180036FA6
0x180036f57  call    _tlgKeywordOn
0x180036f5c  test    al, al
0x180036f5e  jz      short loc_180036FA6
0x180036f60  mov     rax, [r14]
0x180036f63  mov     rcx, [rsp+748h+var_6D8]
0x180036f68  mov     rcx, [rax+rcx*8]
0x180036f6c  mov     eax, [rcx+70h]
0x180036f6f  mov     [rsp+748h+var_6DC], eax
0x180036f73  lea     rax, [rsp+748h+Destination]
0x180036f7b  mov     [rsp+748h+var_6C0], rax
0x180036f83  lea     rax, [rsp+748h+var_6DC]
0x180036f88  mov     [rsp+748h+var_720], rax
0x180036f8d  lea     rax, [rsp+748h+var_6C0]
0x180036f95  mov     [rsp+748h+var_728], rax
0x180036f9a  lea     rdx, dword_18010612C
0x180036fa1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180036fa6  mov     r10, [rsp+748h+var_6D8]
0x180036fab  inc     r10
0x180036fae  movzx   r8d, [rsp+748h+arg_38]
0x180036fb7  jmp     loc_180036E5C
0x180036fbc  mov     rcx, [rcx]
0x180036fbf  add     rcx, 30h ; '0'
0x180036fc3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036fc8  mov     r8, rax
0x180036fcb  mov     edx, 69h ; 'i'
0x180036fd0  mov     rcx, r13
0x180036fd3  call    ?StartPhase@PhaseManager@@QEAAXW4_CLUSTER_SETUP_PHASE@@PEB_WW4Enum@CancelAllowed@@@Z; PhaseManager::StartPhase(_CLUSTER_SETUP_PHASE,wchar_t const *,CancelAllowed::Enum)
0x180036fd8  mov     rbx, [r14]
0x180036fdb  mov     r13, rbx
0x180036fde  mov     rax, rbx
0x180036fe1  mov     [rsp+748h+var_6E8], rbx
0x180036fe6  xor     edx, edx; unsigned int
0x180036fe8  cmp     rax, [r14+8]
0x180036fec  jnz     loc_1800370DB
0x180036ff2  lea     r8d, [rdx+1]; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x180036ff6  mov     rbx, [rsp+748h+var_6D0]
0x180036ffb  mov     rcx, rbx; this
0x180036ffe  call    ?EndPhase@PhaseManager@@QEAAXKW4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::EndPhase(ulong,_CLUSTER_SETUP_PHASE_SEVERITY)
0x180037003  mov     r13, [rsp+748h+var_6B8]
0x18003700b  mov     r8, r13
0x18003700e  mov     edx, 0C8h
0x180037013  mov     rcx, rbx
0x180037016  call    ?StartPhase@PhaseManager@@QEAAXW4_CLUSTER_SETUP_PHASE@@PEB_WW4Enum@CancelAllowed@@@Z; PhaseManager::StartPhase(_CLUSTER_SETUP_PHASE,wchar_t const *,CancelAllowed::Enum)
0x18003701b  mov     r9, r14
0x18003701e  xor     edx, edx
0x180037020  mov     rcx, rbx
0x180037023  call    ?WaitForNodeUp@@YAPEAU_HCLUSTER@@AEAVPhaseManager@@PEAU1@PEAU_HCHANGE@@AEBV?$vector@PEAVClusNode@@V?$allocator@PEAVClusNode@@@std@@@std@@@Z; WaitForNodeUp(PhaseManager &,_HCLUSTER *,_HCHANGE *,std::vector<ClusNode *> const &)
0x180037028  mov     rbx, rax
0x18003702b  mov     [rsp+748h+var_6C8], rax
0x180037033  xor     r14d, r14d
0x180037036  test    rax, rax
0x180037039  jz      loc_1800371E5
0x18003703f  mov     r13d, 1
0x180037045  mov     r8d, r13d; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x180037048  xor     edx, edx; unsigned int
0x18003704a  mov     rcx, [rsp+748h+var_6D0]; this
0x18003704f  call    ?EndPhase@PhaseManager@@QEAAXKW4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::EndPhase(ulong,_CLUSTER_SETUP_PHASE_SEVERITY)
0x180037054  nop
0x180037055  mov     rax, rdi
0x180037058  mov     [r15], r14b
0x18003705b  add     r15, r13
0x18003705e  sub     rax, r13
0x180037061  jnz     short loc_180037058
0x180037063  mov     rax, rdi
0x180037066  mov     [r12], r14b
0x18003706a  add     r12, r13
0x18003706d  sub     rax, r13
0x180037070  jnz     short loc_180037066
0x180037072  lea     rcx, [rsp+748h+var_638]
0x18003707a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003707f  nop
0x180037080  lea     rcx, [rsp+748h+var_620]
0x180037088  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003708d  nop
0x18003708e  mov     rax, rdi
0x180037091  mov     [rsi], r14b
0x180037094  add     rsi, r13
0x180037097  sub     rax, r13
0x18003709a  jnz     short loc_180037091
0x18003709c  mov     rax, [rsp+748h+var_6B0]
0x1800370a4  mov     [rax], r14b
0x1800370a7  add     rax, r13
0x1800370aa  sub     rdi, r13
0x1800370ad  jnz     short loc_1800370A4
0x1800370af  lea     rcx, [rsp+748h+var_608]
0x1800370b7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800370bc  nop
0x1800370bd  lea     rcx, [rsp+748h+var_5F0]
0x1800370c5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800370ca  nop
0x1800370cb  lea     rcx, [rsp+748h+var_688]
0x1800370d3  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x1800370d8  nop
0x1800370d9  jmp     short loc_180037133
0x1800370db  mov     rcx, [rbx]
0x1800370de  xor     r8d, r8d; lpServiceArgVectors
0x1800370e1  mov     rcx, [rcx+80h]; hService
0x1800370e8  call    cs:__imp_StartServiceW
0x1800370ee  test    eax, eax
0x1800370f0  jz      loc_180037226
0x1800370f6  lea     rbx, [r13+8]
0x1800370fa  cmp     rbx, [r14+8]
0x1800370fe  jz      loc_180036FDB
0x180037104  mov     rcx, [rbx]
0x180037107  add     rcx, 30h ; '0'
0x18003710b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180037110  mov     r9d, 1; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x180037116  xor     r8d, r8d; unsigned int
0x180037119  mov     rdx, rax; wchar_t *
0x18003711c  mov     rcx, [rsp+748h+var_6D0]; this
0x180037121  call    ?ContinuePhase@PhaseManager@@QEAAXPEB_WKW4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::ContinuePhase(wchar_t const *,ulong,_CLUSTER_SETUP_PHASE_SEVERITY)
0x180037126  jmp     loc_180036FDB
0x18003712b  mov     rbx, [rsp+748h+var_6C8]
0x180037133  lea     rcx, [rsp+748h+Source]
0x18003713b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180037140  mov     rax, rbx
0x180037143  mov     rcx, [rsp+748h+var_48]
0x18003714b  xor     rcx, rsp; StackCookie
0x18003714e  call    __security_check_cookie
0x180037153  add     rsp, 710h
0x18003715a  pop     r15
0x18003715c  pop     r14
0x18003715e  pop     r13
0x180037160  pop     r12
0x180037162  pop     rdi
0x180037163  pop     rsi
0x180037164  pop     rbx
0x180037165  retn
0x180037166  lea     r8, aFailedToCreate_9; "Failed to create Cluster Secret"
0x18003716d  mov     edx, eax; int
0x18003716f  lea     rcx, [rsp+748h+pExceptionObject]; this
0x180037177  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18003717c  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180037183  lea     rcx, [rsp+748h+pExceptionObject]; pExceptionObject
0x18003718b  call    _CxxThrowException_0
0x180037190  lea     r8, aFailedToCreate_13; "Failed to create Cluster Cert"
0x180037197  mov     edx, eax; int
0x180037199  lea     rcx, [rsp+748h+var_488]; this
0x1800371a1  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800371a6  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x1800371ad  lea     rcx, [rsp+748h+var_488]; pExceptionObject
0x1800371b5  call    _CxxThrowException_0
0x1800371bb  lea     r8, aFailedToCreate_24; "Failed to create Cluster LM Cert"
0x1800371c2  mov     edx, eax; int
0x1800371c4  lea     rcx, [rsp+748h+var_378]; this
0x1800371cc  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800371d1  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x1800371d8  lea     rcx, [rsp+748h+var_378]; pExceptionObject
0x1800371e0  call    _CxxThrowException_0
0x1800371e5  lea     rax, base
0x1800371ec  test    r13, r13
0x1800371ef  cmovz   r13, rax
0x1800371f3  call    cs:__imp_GetLastError
0x1800371f9  mov     edx, eax; int
0x1800371fb  mov     r9, r13
0x1800371fe  lea     r8, aFailedToGetClu_4; "Failed to get cluster handle for cluste"...
  ... truncated ...
```
