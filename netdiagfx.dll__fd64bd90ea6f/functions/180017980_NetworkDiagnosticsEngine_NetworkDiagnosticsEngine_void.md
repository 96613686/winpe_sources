# NetworkDiagnosticsEngine::NetworkDiagnosticsEngine(void)

- ea: `0x180017980`
- end: `0x180017ae7`
- name: `??0NetworkDiagnosticsEngine@@AEAA@XZ`
- size: `359`
- prototype: `NetworkDiagnosticsEngine *__fastcall(NetworkDiagnosticsEngine *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b3a8`

## callees

- `0x1800017f4`
- `0x180014b7c`
- `0x180015d90`
- `0x1800165e4`
- `0x180016664`
- `0x180017980`
- `0x18001cf30`
- `0x18001f510`
- `0x1800205b0`
- `0x180024a38`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180017aa9`
- `KERNEL32!InitializeCriticalSection` at `0x180017aa9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017ac8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017ac8`

## pseudocode

```c
NetworkDiagnosticsEngine *__fastcall NetworkDiagnosticsEngine::NetworkDiagnosticsEngine(NetworkDiagnosticsEngine *this)
{
  _QWORD *v2; // rax
  CHelperMetaDataStore *v3; // r14
  CHelperInfoContainer *v4; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,NetworkIncident *>>>::_Buyheadnode();
  *((_QWORD *)this + 3) = 0;
  v2 = operator new(0x50u);
  v3 = (CHelperMetaDataStore *)v2;
  if ( v2 )
  {
    v4 = (CHelperInfoContainer *)(v2 + 1);
    std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *>::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *>(v2 + 1);
    std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *>::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *>((char *)v4 + 16);
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 0;
    *((_QWORD *)v3 + 8) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,tagHELPER_ATTRIBUTE *>>>::_Buyheadnode();
    *(_QWORD *)v3 = L"SYSTEM\\CurrentControlSet\\Control\\NetDiagFx";
    CHelperInfoContainer::LoadHelperInfosFromRegistry(v4, L"SYSTEM\\CurrentControlSet\\Control\\NetDiagFx");
    CHelperMetaDataStore::LoadAllExtHelperInfosFromRegistry(v3);
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 5) = v3;
  v5 = operator new(0x48u);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
    *((_DWORD *)v5 + 4) = 17;
    v5[4] = 0xFFFFFFFFLL;
    v5[5] = 0;
    *((_DWORD *)v5 + 12) = 0;
    *((_DWORD *)v5 + 13) = 10;
    v5[7] = 0;
    v5[8] = 0;
    *((_DWORD *)v5 + 5) = 1061158912;
    *((_DWORD *)v5 + 6) = 1048576000;
    *((_DWORD *)v5 + 7) = 1074790400;
    ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::UpdateRehashThresholds(v5);
    ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::InitHashTable(
      v7,
      101);
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 6) = v6;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CoCreateInstance(&CLSID_NDFHelperClassRegistry, 0, 1u, &GUID_4551bfb6_b18e_4195_b812_051f47ff74ba, (LPVOID *)this + 3);
  *((_QWORD *)this + 4) = SQMSessionCleanupUtil::CreateUtil();
  return this;
}

```

## disassembly

```asm
0x180017980  mov     [rsp+arg_0], rcx
0x180017985  push    rbx
0x180017986  push    rbp
0x180017987  push    rsi
0x180017988  push    rdi
0x180017989  push    r14
0x18001798b  push    r15
0x18001798d  sub     rsp, 38h
0x180017991  mov     rsi, rcx
0x180017994  xor     ebp, ebp
0x180017996  mov     [rcx], rbp
0x180017999  mov     [rcx+8], rbp
0x18001799d  mov     [rcx+10h], rbp
0x1800179a1  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,NetworkIncident *>>>::_Buyheadnode(void)
0x1800179a6  mov     [rsi+8], rax
0x1800179aa  lea     r15, [rsi+18h]
0x1800179ae  mov     [r15], rbp
0x1800179b1  lea     ecx, [rbp+50h]; Size
0x1800179b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800179b9  mov     r14, rax
0x1800179bc  mov     [rsp+68h+arg_8], rax
0x1800179c1  test    rax, rax
0x1800179c4  jz      short loc_180017A26
0x1800179c6  mov     [rsp+68h+arg_10], rax
0x1800179ce  lea     rdi, [rax+8]
0x1800179d2  mov     [rsp+68h+arg_18], rdi
0x1800179da  mov     rcx, rdi
0x1800179dd  call    ??0?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@@5@@std@@QEAA@XZ; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *>::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *>(void)
0x1800179e2  nop
0x1800179e3  lea     rcx, [rdi+10h]
0x1800179e7  call    ??0?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@@5@@std@@QEAA@XZ; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *>::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *>(void)
0x1800179ec  mov     [rdi+20h], rbp
0x1800179f0  mov     [rdi+28h], rbp
0x1800179f4  mov     [rdi+30h], rbp
0x1800179f8  mov     [r14+40h], rbp
0x1800179fc  mov     [r14+48h], rbp
0x180017a00  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,tagHELPER_ATTRIBUTE *>>>::_Buyheadnode(void)
0x180017a05  mov     [r14+40h], rax
0x180017a09  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Net"...
0x180017a10  mov     [r14], rdx
0x180017a13  mov     rcx, rdi; this
0x180017a16  call    ?LoadHelperInfosFromRegistry@CHelperInfoContainer@@QEAAJPEBG@Z; CHelperInfoContainer::LoadHelperInfosFromRegistry(ushort const *)
0x180017a1b  mov     rcx, r14; this
0x180017a1e  call    ?LoadAllExtHelperInfosFromRegistry@CHelperMetaDataStore@@AEAAJXZ; CHelperMetaDataStore::LoadAllExtHelperInfosFromRegistry(void)
0x180017a23  nop
0x180017a24  jmp     short loc_180017A29
0x180017a26  mov     r14, rbp
0x180017a29  mov     [rsi+28h], r14
0x180017a2d  mov     ecx, 48h ; 'H'; Size
0x180017a32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017a37  mov     rbx, rax
0x180017a3a  mov     [rsp+68h+arg_8], rax
0x180017a3f  test    rax, rax
0x180017a42  jz      short loc_180017A9E
0x180017a44  mov     [rax], rbp
0x180017a47  mov     [rax+8], rbp
0x180017a4b  mov     dword ptr [rax+10h], 11h
0x180017a52  mov     eax, 0FFFFFFFFh
0x180017a57  mov     [rbx+20h], rax
0x180017a5b  mov     [rbx+28h], rbp
0x180017a5f  mov     [rbx+30h], ebp
0x180017a62  mov     dword ptr [rbx+34h], 0Ah
0x180017a69  mov     [rbx+38h], rbp
0x180017a6d  mov     [rbx+40h], rbp
0x180017a71  mov     dword ptr [rbx+14h], 3F400000h
0x180017a78  mov     dword ptr [rbx+18h], 3E800000h
0x180017a7f  mov     dword ptr [rbx+1Ch], 40100000h
0x180017a86  mov     rcx, rbx
0x180017a89  call    ?UpdateRehashThresholds@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@AEAAXXZ; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::UpdateRehashThresholds(void)
0x180017a8e  nop
0x180017a8f  xor     r8d, r8d
0x180017a92  lea     edx, [r8+65h]
0x180017a96  call    ?InitHashTable@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::InitHashTable(uint,bool)
0x180017a9b  nop
0x180017a9c  jmp     short loc_180017AA1
0x180017a9e  mov     rbx, rbp
0x180017aa1  mov     [rsi+30h], rbx
0x180017aa5  lea     rcx, [rsi+40h]; lpCriticalSection
0x180017aa9  call    cs:__imp_InitializeCriticalSection
0x180017aaf  mov     [rsp+68h+ppv], r15; ppv
0x180017ab4  lea     r9, _GUID_4551bfb6_b18e_4195_b812_051f47ff74ba; riid
0x180017abb  xor     edx, edx; pUnkOuter
0x180017abd  lea     r8d, [rdx+1]; dwClsContext
0x180017ac1  lea     rcx, CLSID_NDFHelperClassRegistry; rclsid
0x180017ac8  call    cs:__imp_CoCreateInstance
0x180017ace  call    ?CreateUtil@SQMSessionCleanupUtil@@SAPEAV1@XZ; SQMSessionCleanupUtil::CreateUtil(void)
0x180017ad3  mov     [rsi+20h], rax
0x180017ad7  mov     rax, rsi
0x180017ada  add     rsp, 38h
0x180017ade  pop     r15
0x180017ae0  pop     r14
0x180017ae2  pop     rdi
0x180017ae3  pop     rsi
0x180017ae4  pop     rbp
0x180017ae5  pop     rbx
0x180017ae6  retn
```
