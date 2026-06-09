# CSCEPNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x18007de20`
- end: `0x18007e4f0`
- name: `?Add@CSCEPNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `1744`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x180015888`
- `0x18001a4d4`
- `0x18001a4fc`
- `0x180023f1c`
- `0x18003f3a0`
- `0x18003f6f0`
- `0x18007de20`
- `0x18007e4f8`
- `0x180080094`
- `0x180081564`
- `0x180081918`
- `0x180081a28`
- `0x180083694`
- `0x1800837ec`
- `0x180083a20`
- `0x180083acc`
- `0x1800d1fa8`
- `0x1800d2014`
- `0x1800d66e8`
- `0x1800fd1c4`
- `0x1800fd680`
- `0x1800fd71c`
- `0x1800fdb7c`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007e064`
- `OLEAUT32!__imp_SysAllocString` at `0x18007e064`
- `OLEAUT32!__imp_VariantInit` at `0x18007deff`
- `OLEAUT32!__imp_VariantInit` at `0x18007deff`
- `OLEAUT32!__imp_VariantClear` at `0x18007e0e6`
- `OLEAUT32!__imp_VariantClear` at `0x18007e229`
- `OLEAUT32!__imp_VariantClear` at `0x18007e0e6`
- `OLEAUT32!__imp_VariantClear` at `0x18007e229`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007e3e2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007e3e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CSCEPNode::Add(__int64 a1, __int64 a2, unsigned int a3, struct tagVARIANT *a4, _QWORD *a5, int *a6)
{
  __int64 Imei; // rax
  int SCEPRegistryKeyPath; // edi
  const struct CspNodeMapBase *v12; // rcx
  const struct CSP_NODEMAP_ENTRY *NodeMapEntryForURI; // rax
  unsigned __int64 v14; // rdx
  unsigned int *v15; // rsi
  int v16; // r8d
  unsigned __int16 **v17; // rax
  int v18; // r14d
  unsigned __int64 v19; // rdx
  int v20; // r8d
  int v21; // ecx
  unsigned __int16 **v22; // rax
  __int64 v23; // rbx
  unsigned int v24; // eax
  CClientCertScepLogger *Logger; // rax
  const unsigned __int16 *v27; // r8
  struct CConfigServiceProvider2Impl *v28; // [rsp+20h] [rbp-AF8h]
  struct IConfigManager2URI *v29; // [rsp+40h] [rbp-AD8h] BYREF
  unsigned __int16 *v30; // [rsp+48h] [rbp-AD0h] BYREF
  __int64 v31; // [rsp+50h] [rbp-AC8h] BYREF
  __int16 v32; // [rsp+58h] [rbp-AC0h] BYREF
  char v33; // [rsp+5Ah] [rbp-ABEh]
  __int64 v34; // [rsp+60h] [rbp-AB8h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-AB0h] BYREF
  _QWORD *v36; // [rsp+80h] [rbp-A98h]
  unsigned __int16 *v37[2]; // [rsp+88h] [rbp-A90h] BYREF
  __m128i si128; // [rsp+98h] [rbp-A80h]
  struct tagVARIANT v39; // [rsp+B0h] [rbp-A68h] BYREF
  WCHAR SubKey[1280]; // [rsp+D0h] [rbp-A48h] BYREF

  v36 = a5;
  v30 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v29 = 0;
  v31 = 0;
  *(_OWORD *)v37 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v37[0]) = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  Imei = CellularIdentity::GetImei(*(_QWORD *)(a1 + 16) + 104LL, &v39);
  std::wstring::operator=(v37, Imei);
  std::wstring::_Tidy_deallocate(&v39);
  VariantInit(&pvarg);
  SCEPRegistryKeyPath = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                          a2,
                          0,
                          &v30);
  if ( SCEPRegistryKeyPath < 0 )
    goto LABEL_52;
  SCEPRegistryKeyPath = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, struct IConfigManager2URI **))(**(_QWORD **)(a1 + 24) + 168LL))(
                          *(_QWORD *)(a1 + 24),
                          a2,
                          0,
                          0,
                          &v29);
  if ( SCEPRegistryKeyPath < 0 )
    goto LABEL_52;
  v12 = *(const struct CspNodeMapBase **)(*(_QWORD *)(a1 + 16) + 32LL);
  if ( !v12
    || (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v12, v29), (v15 = (unsigned int *)NodeMapEntryForURI) == 0) )
  {
    SCEPRegistryKeyPath = -2046820335;
    goto LABEL_52;
  }
  if ( (unsigned int)(*((_DWORD *)NodeMapEntryForURI + 3) - 27) <= 2 )
  {
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v32);
    std::wstring::_Tidy_deallocate(v37);
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v31);
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v29);
    return 2248146946LL;
  }
  if ( CSCEPNode::m_fIsUser == 1 )
  {
    SCEPRegistryKeyPath = AutoImpersonate::ImpersonateTargetedUser(
                            (AutoImpersonate *)&v32,
                            *(struct CConfigServiceProvider2Impl **)(a1 + 16));
    if ( SCEPRegistryKeyPath < 0 )
      goto LABEL_52;
  }
  if ( a3 == 8 )
  {
    if ( v15[3] == 1 )
    {
      SCEPRegistryKeyPath = CSCEPNode::ValidateUniqueId(v30);
      if ( SCEPRegistryKeyPath < 0 )
        goto LABEL_52;
    }
    SCEPRegistryKeyPath = CSCEPNode::GetSCEPRegistryKeyPath(
                            SubKey,
                            v14,
                            0,
                            v29,
                            *(struct CConfigServiceProvider2Impl **)(a1 + 16),
                            0);
    if ( SCEPRegistryKeyPath < 0 )
      goto LABEL_52;
    if ( (int)CCspSimpleRegHelper::RegKeyExists(CSCEPNode::m_hCurrentHive, SubKey) >= 0 )
      goto LABEL_13;
    SCEPRegistryKeyPath = CCspSimpleRegHelper::CreateRegKey(CSCEPNode::m_hCurrentHive, SubKey, v16);
    if ( SCEPRegistryKeyPath < 0 )
      goto LABEL_52;
    if ( v15[3] == 18 )
    {
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(&Class);
      v17 = v37;
      if ( si128.m128i_i64[1] > 7uLL )
        v17 = (unsigned __int16 **)v37[0];
      v39 = pvarg;
      SCEPRegistryKeyPath = CCspSimpleRegHelper::SetValue(CSCEPNode::m_hCurrentHive, SubKey, L"Enroll", 1, &v39, v17, 1);
      VariantClear(&pvarg);
      if ( SCEPRegistryKeyPath < 0 )
        goto LABEL_52;
    }
    v18 = 1;
    goto LABEL_37;
  }
  if ( v15[4] != a3 )
  {
    SCEPRegistryKeyPath = -2046820351;
    goto LABEL_52;
  }
  v39 = *a4;
  SCEPRegistryKeyPath = CSCEPNode::ValidateNodeValue(v15[3], &v39);
  if ( SCEPRegistryKeyPath < 0 )
    goto LABEL_52;
  v28 = *(struct CConfigServiceProvider2Impl **)(a1 + 16);
  if ( v15[3] != 3 )
  {
    SCEPRegistryKeyPath = CSCEPNode::GetSCEPRegistryKeyPath(SubKey, v19, 1, v29, v28, 0);
    if ( SCEPRegistryKeyPath < 0 )
      goto LABEL_52;
    if ( (int)CCspSimpleRegHelper::GetValueAsVariant(CSCEPNode::m_hCurrentHive, SubKey, v30, a3, &pvarg) >= 0 )
    {
      VariantClear(&pvarg);
LABEL_13:
      SCEPRegistryKeyPath = -2102788094;
      goto LABEL_52;
    }
    if ( v15[3] == 14 || (v21 = 1, v15[3] == 6) )
      v21 = 0;
    v22 = v37;
    if ( si128.m128i_i64[1] > 7uLL )
      v22 = (unsigned __int16 **)v37[0];
    v39 = *a4;
    SCEPRegistryKeyPath = CCspSimpleRegHelper::SetValue(CSCEPNode::m_hCurrentHive, SubKey, v30, a3, &v39, v22, v21);
    v18 = 0;
    if ( SCEPRegistryKeyPath < 0 )
      goto LABEL_52;
    goto LABEL_37;
  }
  SCEPRegistryKeyPath = CSCEPNode::GetSCEPRegistryKeyPath(SubKey, v19, 0, v29, v28, 0);
  if ( SCEPRegistryKeyPath < 0
    || (SCEPRegistryKeyPath = CCspSimpleRegHelper::CreateRegKey(CSCEPNode::m_hCurrentHive, SubKey, v20),
        SCEPRegistryKeyPath < 0) )
  {
LABEL_52:
    Logger = CClientCertScepLogger::GetLogger();
    v27 = (const unsigned __int16 *)v37;
    if ( si128.m128i_i64[1] > 7uLL )
      v27 = v37[0];
    CClientCertScepLogger::LogSCEPCspAddNode(Logger, SCEPRegistryKeyPath, v27, v30);
    goto LABEL_55;
  }
  v39 = *a4;
  SCEPRegistryKeyPath = UtilsWriteChallenge(CSCEPNode::m_hCurrentHive, SubKey, &v39);
  if ( SCEPRegistryKeyPath < 0 )
    goto LABEL_48;
  v18 = 0;
LABEL_37:
  SCEPRegistryKeyPath = ATL::CComObject<CSCEPNode>::CreateInstance(&v31);
  if ( SCEPRegistryKeyPath < 0 )
    goto LABEL_52;
  v23 = v31;
  SCEPRegistryKeyPath = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IConfigManager2URI *, unsigned int *))(*(_QWORD *)v31 + 136LL))(
                          v31,
                          *(_QWORD *)(a1 + 16),
                          v29,
                          v15);
  if ( SCEPRegistryKeyPath >= 0 )
  {
    if ( v18
      && v15[3] == 1
      && ((SCEPRegistryKeyPath = UtilsWriteErrorCodeAndStatus(CSCEPNode::m_hCurrentHive, SubKey, 0),
           SCEPRegistryKeyPath < 0)
       || (SCEPRegistryKeyPath = UtilsWriteRegistryDWORDValue(
                                   CSCEPNode::m_hCurrentHive,
                                   SubKey,
                                   L"LegacyCertStoreCsp",
                                   CSCEPNode::m_fIsCertStore),
           SCEPRegistryKeyPath < 0)
       || (SCEPRegistryKeyPath = UtilsWriteRegistryStringValue(
                                   CSCEPNode::m_hCurrentHive,
                                   SubKey,
                                   L"RespondentServerURL",
                                   (const BYTE *)&Class),
           SCEPRegistryKeyPath < 0)
       || (SCEPRegistryKeyPath = UtilsWriteRegistryStringValue(
                                   CSCEPNode::m_hCurrentHive,
                                   SubKey,
                                   L"CertThumbPrint",
                                   (const BYTE *)&Class),
           SCEPRegistryKeyPath < 0)) )
    {
      RegDeleteKeyW(CSCEPNode::m_hCurrentHive, SubKey);
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
      v31 = 0;
      *v36 = v23;
      v24 = v15[7];
      *a6 = v24;
      if ( v15[3] != 17 )
        goto LABEL_55;
      *a6 = v24 | 2;
    }
  }
LABEL_48:
  if ( SCEPRegistryKeyPath < 0 )
    goto LABEL_52;
LABEL_55:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v32);
  std::wstring::_Tidy_deallocate(v37);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v31);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v29);
  return (unsigned int)SCEPRegistryKeyPath;
}

```

## disassembly

```asm
0x18007de20  push    rbx
0x18007de22  push    rsi
0x18007de23  push    rdi
0x18007de24  push    r12
0x18007de26  push    r13
0x18007de28  push    r14
0x18007de2a  push    r15
0x18007de2c  sub     rsp, 0AE0h
0x18007de33  mov     rax, cs:__security_cookie
0x18007de3a  xor     rax, rsp
0x18007de3d  mov     [rsp+0B18h+var_48], rax
0x18007de45  mov     r12, r9
0x18007de48  mov     r14d, r8d
0x18007de4b  mov     rbx, rdx
0x18007de4e  mov     r15, rcx
0x18007de51  mov     rax, [rsp+0B18h+arg_20]
0x18007de59  mov     [rsp+0B18h+var_A98], rax
0x18007de61  mov     r13, [rsp+0B18h+arg_28]
0x18007de69  xor     esi, esi
0x18007de6b  mov     [rsp+0B18h+var_AD0], rsi
0x18007de70  xorps   xmm0, xmm0
0x18007de73  xor     eax, eax
0x18007de75  movups  xmmword ptr [rsp+0B18h+pvarg], xmm0
0x18007de7a  mov     qword ptr [rsp+0B18h+pvarg+10h], rax
0x18007de7f  mov     [rsp+0B18h+var_AD8], rsi
0x18007de84  mov     [rsp+0B18h+var_AC8], rsi
0x18007de89  movups  xmmword ptr [rsp+0B18h+var_A90], xmm0
0x18007de91  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007de99  movdqu  [rsp+0B18h+var_A80], xmm1
0x18007dea2  mov     word ptr [rsp+0B18h+var_A90], si
0x18007deaa  mov     [rsp+0B18h+var_AC0], si
0x18007deaf  mov     [rsp+0B18h+var_ABE], sil
0x18007deb4  mov     [rsp+0B18h+var_AB8], rsi
0x18007deb9  mov     rcx, [rcx+10h]
0x18007debd  add     rcx, 68h ; 'h'
0x18007dec1  lea     rdx, [rsp+0B18h+var_A68]
0x18007dec9  cmp     cs:?m_fIsCertStore@CSCEPNode@@0HA, esi; int CSCEPNode::m_fIsCertStore
0x18007decf  jz      short loc_18007DED8
0x18007ded1  call    ?GetImei@CellularIdentity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CellularIdentity::GetImei(void)
0x18007ded6  jmp     short loc_18007DEDD
0x18007ded8  call    ?GetImei@CellularIdentity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CellularIdentity::GetImei(void)
0x18007dedd  mov     rdx, rax
0x18007dee0  lea     rcx, [rsp+0B18h+var_A90]
0x18007dee8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007deed  lea     rcx, [rsp+0B18h+var_A68]
0x18007def5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007defa  lea     rcx, [rsp+0B18h+pvarg]; pvarg
0x18007deff  call    cs:__imp_VariantInit
0x18007df06  nop     dword ptr [rax+rax+00h]
0x18007df0b  mov     rax, [rbx]
0x18007df0e  lea     r8, [rsp+0B18h+var_AD0]
0x18007df13  xor     edx, edx
0x18007df15  mov     rcx, rbx
0x18007df18  mov     rax, [rax+58h]
0x18007df1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df21  mov     edi, eax
0x18007df23  test    eax, eax
0x18007df25  js      loc_18007E467
0x18007df2b  mov     rcx, [r15+18h]
0x18007df2f  mov     rax, [rcx]
0x18007df32  lea     rdx, [rsp+0B18h+var_AD8]
0x18007df37  mov     [rsp+0B18h+var_AF8], rdx
0x18007df3c  xor     r9d, r9d
0x18007df3f  xor     r8d, r8d
0x18007df42  mov     rdx, rbx
0x18007df45  mov     rax, [rax+0A8h]
0x18007df4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df51  mov     edi, eax
0x18007df53  test    eax, eax
0x18007df55  js      loc_18007E467
0x18007df5b  mov     rax, [r15+10h]
0x18007df5f  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18007df63  test    rcx, rcx
0x18007df66  jz      loc_18007E462
0x18007df6c  mov     rdx, [rsp+0B18h+var_AD8]; struct IConfigManager2URI *
0x18007df71  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18007df76  mov     rsi, rax
0x18007df79  test    rax, rax
0x18007df7c  jz      loc_18007E462
0x18007df82  mov     ecx, [rax+0Ch]
0x18007df85  sub     ecx, 1Bh
0x18007df88  cmp     ecx, 2
0x18007df8b  jbe     loc_18007E42D
0x18007df91  mov     ebx, 1
0x18007df96  cmp     cs:?m_fIsUser@CSCEPNode@@0HA, ebx; int CSCEPNode::m_fIsUser
0x18007df9c  jnz     short loc_18007DFB6
0x18007df9e  mov     rdx, [r15+10h]; struct CConfigServiceProvider2Impl *
0x18007dfa2  lea     rcx, [rsp+0B18h+var_AC0]; this
0x18007dfa7  call    ?ImpersonateTargetedUser@AutoImpersonate@@QEAAJPEAVCConfigServiceProvider2Impl@@@Z; AutoImpersonate::ImpersonateTargetedUser(CConfigServiceProvider2Impl *)
0x18007dfac  mov     edi, eax
0x18007dfae  test    eax, eax
0x18007dfb0  js      loc_18007E467
0x18007dfb6  cmp     r14d, 8
0x18007dfba  jnz     loc_18007E102
0x18007dfc0  cmp     [rsi+0Ch], ebx
0x18007dfc3  jnz     short loc_18007DFD9
0x18007dfc5  mov     rcx, [rsp+0B18h+var_AD0]; unsigned __int16 *
0x18007dfca  call    ?ValidateUniqueId@CSCEPNode@@CAJPEBG@Z; CSCEPNode::ValidateUniqueId(ushort const *)
0x18007dfcf  mov     edi, eax
0x18007dfd1  test    eax, eax
0x18007dfd3  js      loc_18007E467
0x18007dfd9  mov     [rsp+0B18h+var_AF0], 0; int
0x18007dfe1  mov     rax, [r15+10h]
0x18007dfe5  mov     [rsp+0B18h+var_AF8], rax; struct CConfigServiceProvider2Impl *
0x18007dfea  mov     r9, [rsp+0B18h+var_AD8]; struct IConfigManager2URI *
0x18007dfef  xor     r8d, r8d; int
0x18007dff2  lea     rcx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007dffa  call    ?GetSCEPRegistryKeyPath@CSCEPNode@@CAJPEAG_KHPEAUIConfigManager2URI@@PEAVCConfigServiceProvider2Impl@@H@Z; CSCEPNode::GetSCEPRegistryKeyPath(ushort *,unsigned __int64,int,IConfigManager2URI *,CConfigServiceProvider2Impl *,int)
0x18007dfff  mov     edi, eax
0x18007e001  test    eax, eax
0x18007e003  js      loc_18007E467
0x18007e009  lea     rdx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007e011  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x18007e018  call    ?RegKeyExists@CCspSimpleRegHelper@@SAJPEAUHKEY__@@PEBG@Z; CCspSimpleRegHelper::RegKeyExists(HKEY__ *,ushort const *)
0x18007e01d  test    eax, eax
0x18007e01f  js      short loc_18007E02B
0x18007e021  mov     edi, 82AA0002h
0x18007e026  jmp     loc_18007E467
0x18007e02b  lea     rdx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007e033  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x18007e03a  call    ?CreateRegKey@CCspSimpleRegHelper@@SAJPEAUHKEY__@@PEBGH@Z; CCspSimpleRegHelper::CreateRegKey(HKEY__ *,ushort const *,int)
0x18007e03f  mov     edi, eax
0x18007e041  test    eax, eax
0x18007e043  js      loc_18007E467
0x18007e049  cmp     dword ptr [rsi+0Ch], 12h
0x18007e04d  jnz     loc_18007E0FA
0x18007e053  mov     eax, 8
0x18007e058  mov     word ptr [rsp+0B18h+pvarg], ax
0x18007e05d  lea     rcx, Class; psz
0x18007e064  call    cs:__imp_SysAllocString
0x18007e06b  nop     dword ptr [rax+rax+00h]
0x18007e070  mov     qword ptr [rsp+0B18h+pvarg+8], rax
0x18007e075  lea     rax, [rsp+0B18h+var_A90]
0x18007e07d  cmp     qword ptr [rsp+0B18h+var_A80+8], 7
0x18007e086  cmova   rax, [rsp+0B18h+var_A90]
0x18007e08f  movups  xmm0, xmmword ptr [rsp+0B18h+pvarg]
0x18007e094  movaps  xmmword ptr [rsp+0B18h+var_A68], xmm0
0x18007e09c  movsd   xmm1, qword ptr [rsp+0B18h+pvarg+10h]
0x18007e0a2  movsd   qword ptr [rsp+0B18h+var_A68+10h], xmm1
0x18007e0ab  mov     [rsp+0B18h+var_AE8], ebx
0x18007e0af  mov     qword ptr [rsp+0B18h+var_AF0], rax
0x18007e0b4  lea     rax, [rsp+0B18h+var_A68]
0x18007e0bc  mov     [rsp+0B18h+var_AF8], rax
0x18007e0c1  mov     r9d, ebx
0x18007e0c4  lea     r8, aEnroll_0; "Enroll"
0x18007e0cb  lea     rdx, [rsp+0B18h+SubKey]
0x18007e0d3  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x18007e0da  call    ?SetValue@CCspSimpleRegHelper@@SAJPEAUHKEY__@@PEBG1W4ConfigDataType@@UtagVARIANT@@1H@Z; CCspSimpleRegHelper::SetValue(HKEY__ *,ushort const *,ushort const *,ConfigDataType,tagVARIANT,ushort const *,int)
0x18007e0df  mov     edi, eax
0x18007e0e1  lea     rcx, [rsp+0B18h+pvarg]; pvarg
0x18007e0e6  call    cs:__imp_VariantClear
0x18007e0ed  nop     dword ptr [rax+rax+00h]
0x18007e0f2  test    edi, edi
0x18007e0f4  js      loc_18007E467
0x18007e0fa  mov     r14d, ebx
0x18007e0fd  jmp     loc_18007E2C0
0x18007e102  cmp     [rsi+10h], r14d
0x18007e106  jz      short loc_18007E112
0x18007e108  mov     edi, 86000001h
0x18007e10d  jmp     loc_18007E467
0x18007e112  movups  xmm0, xmmword ptr [r12]
0x18007e117  movaps  xmmword ptr [rsp+0B18h+var_A68], xmm0
0x18007e11f  movsd   xmm1, qword ptr [r12+10h]
0x18007e126  movsd   qword ptr [rsp+0B18h+var_A68+10h], xmm1
0x18007e12f  lea     rdx, [rsp+0B18h+var_A68]; struct tagVARIANT
0x18007e137  mov     ecx, [rsi+0Ch]; unsigned int
0x18007e13a  call    ?ValidateNodeValue@CSCEPNode@@CAJKUtagVARIANT@@@Z; CSCEPNode::ValidateNodeValue(ulong,tagVARIANT)
0x18007e13f  mov     edi, eax
0x18007e141  test    eax, eax
0x18007e143  js      loc_18007E467
0x18007e149  mov     rax, [r15+10h]
0x18007e14d  mov     [rsp+0B18h+var_AF0], 0; int
0x18007e155  mov     r9, [rsp+0B18h+var_AD8]; struct IConfigManager2URI *
0x18007e15a  lea     rcx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007e162  mov     [rsp+0B18h+var_AF8], rax; struct CConfigServiceProvider2Impl *
0x18007e167  cmp     dword ptr [rsi+0Ch], 3
0x18007e16b  jnz     short loc_18007E1E8
0x18007e16d  xor     r8d, r8d; int
0x18007e170  call    ?GetSCEPRegistryKeyPath@CSCEPNode@@CAJPEAG_KHPEAUIConfigManager2URI@@PEAVCConfigServiceProvider2Impl@@H@Z; CSCEPNode::GetSCEPRegistryKeyPath(ushort *,unsigned __int64,int,IConfigManager2URI *,CConfigServiceProvider2Impl *,int)
0x18007e175  mov     edi, eax
0x18007e177  test    eax, eax
0x18007e179  js      loc_18007E467
0x18007e17f  lea     rdx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007e187  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x18007e18e  call    ?CreateRegKey@CCspSimpleRegHelper@@SAJPEAUHKEY__@@PEBGH@Z; CCspSimpleRegHelper::CreateRegKey(HKEY__ *,ushort const *,int)
0x18007e193  mov     edi, eax
0x18007e195  test    eax, eax
0x18007e197  js      loc_18007E467
0x18007e19d  movups  xmm0, xmmword ptr [r12]
0x18007e1a2  movaps  xmmword ptr [rsp+0B18h+var_A68], xmm0
0x18007e1aa  movsd   xmm1, qword ptr [r12+10h]
0x18007e1b1  movsd   qword ptr [rsp+0B18h+var_A68+10h], xmm1
0x18007e1ba  lea     r8, [rsp+0B18h+var_A68]; struct tagVARIANT
0x18007e1c2  lea     rdx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007e1ca  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x18007e1d1  call    ?UtilsWriteChallenge@@YAJPEAUHKEY__@@PEBGUtagVARIANT@@@Z; UtilsWriteChallenge(HKEY__ *,ushort const *,tagVARIANT)
0x18007e1d6  mov     edi, eax
0x18007e1d8  test    eax, eax
0x18007e1da  js      loc_18007E427
0x18007e1e0  xor     r14d, r14d
0x18007e1e3  jmp     loc_18007E2C0
0x18007e1e8  mov     r8d, ebx; int
0x18007e1eb  call    ?GetSCEPRegistryKeyPath@CSCEPNode@@CAJPEAG_KHPEAUIConfigManager2URI@@PEAVCConfigServiceProvider2Impl@@H@Z; CSCEPNode::GetSCEPRegistryKeyPath(ushort *,unsigned __int64,int,IConfigManager2URI *,CConfigServiceProvider2Impl *,int)
0x18007e1f0  mov     edi, eax
0x18007e1f2  test    eax, eax
0x18007e1f4  js      loc_18007E467
0x18007e1fa  lea     rax, [rsp+0B18h+pvarg]
0x18007e1ff  mov     [rsp+0B18h+var_AF8], rax
0x18007e204  mov     r9d, r14d
0x18007e207  mov     r8, [rsp+0B18h+var_AD0]
0x18007e20c  lea     rdx, [rsp+0B18h+SubKey]
0x18007e214  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x18007e21b  call    ?GetValueAsVariant@CCspSimpleRegHelper@@SAJPEAUHKEY__@@PEBG1W4ConfigDataType@@PEAUtagVARIANT@@@Z; CCspSimpleRegHelper::GetValueAsVariant(HKEY__ *,ushort const *,ushort const *,ConfigDataType,tagVARIANT *)
0x18007e220  test    eax, eax
0x18007e222  js      short loc_18007E23A
0x18007e224  lea     rcx, [rsp+0B18h+pvarg]; pvarg
0x18007e229  call    cs:__imp_VariantClear
0x18007e230  nop     dword ptr [rax+rax+00h]
0x18007e235  jmp     loc_18007E021
0x18007e23a  cmp     dword ptr [rsi+0Ch], 0Eh
0x18007e23e  jz      short loc_18007E248
0x18007e240  mov     ecx, ebx
0x18007e242  cmp     dword ptr [rsi+0Ch], 6
0x18007e246  jnz     short loc_18007E24A
0x18007e248  xor     ecx, ecx
0x18007e24a  lea     rax, [rsp+0B18h+var_A90]
0x18007e252  cmp     qword ptr [rsp+0B18h+var_A80+8], 7
0x18007e25b  cmova   rax, [rsp+0B18h+var_A90]
0x18007e264  movups  xmm0, xmmword ptr [r12]
0x18007e269  movaps  xmmword ptr [rsp+0B18h+var_A68], xmm0
0x18007e271  movsd   xmm1, qword ptr [r12+10h]
0x18007e278  movsd   qword ptr [rsp+0B18h+var_A68+10h], xmm1
0x18007e281  mov     [rsp+0B18h+var_AE8], ecx
0x18007e285  mov     qword ptr [rsp+0B18h+var_AF0], rax
0x18007e28a  lea     rax, [rsp+0B18h+var_A68]
0x18007e292  mov     [rsp+0B18h+var_AF8], rax
0x18007e297  mov     r9d, r14d
0x18007e29a  mov     r8, [rsp+0B18h+var_AD0]
0x18007e29f  lea     rdx, [rsp+0B18h+SubKey]
0x18007e2a7  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x18007e2ae  call    ?SetValue@CCspSimpleRegHelper@@SAJPEAUHKEY__@@PEBG1W4ConfigDataType@@UtagVARIANT@@1H@Z; CCspSimpleRegHelper::SetValue(HKEY__ *,ushort const *,ushort const *,ConfigDataType,tagVARIANT,ushort const *,int)
0x18007e2b3  mov     edi, eax
0x18007e2b5  xor     r14d, r14d
0x18007e2b8  test    eax, eax
0x18007e2ba  js      loc_18007E467
0x18007e2c0  lea     rcx, [rsp+0B18h+var_AC8]
0x18007e2c5  call    ?CreateInstance@?$CComObject@VCSCEPNode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSCEPNode>::CreateInstance(ATL::CComObject<CSCEPNode> * *)
0x18007e2ca  mov     edi, eax
0x18007e2cc  test    eax, eax
0x18007e2ce  js      loc_18007E467
0x18007e2d4  mov     rbx, [rsp+0B18h+var_AC8]
0x18007e2d9  mov     rax, [rbx]
0x18007e2dc  mov     r9, rsi
0x18007e2df  mov     r8, [rsp+0B18h+var_AD8]
0x18007e2e4  mov     rdx, [r15+10h]
0x18007e2e8  mov     rcx, rbx
0x18007e2eb  mov     rax, [rax+88h]
0x18007e2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e2f7  mov     edi, eax
0x18007e2f9  test    eax, eax
0x18007e2fb  js      loc_18007E427
0x18007e301  test    r14d, r14d
0x18007e304  jz      loc_18007E3F0
0x18007e30a  cmp     dword ptr [rsi+0Ch], 1
0x18007e30e  jnz     loc_18007E3F0
0x18007e314  lea     rax, [rsp+0B18h+var_A90]
0x18007e31c  cmp     qword ptr [rsp+0B18h+var_A80+8], 7
0x18007e325  cmova   rax, [rsp+0B18h+var_A90]
0x18007e32e  mov     qword ptr [rsp+0B18h+var_AF0], rax
0x18007e333  mov     dword ptr [rsp+0B18h+var_AF8], 20h ; ' '
0x18007e33b  xor     r9d, r9d
0x18007e33e  xor     r8d, r8d
0x18007e341  lea     rdx, [rsp+0B18h+SubKey]
0x18007e349  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x18007e350  call    ?UtilsWriteErrorCodeAndStatus@@YAJPEAUHKEY__@@PEBGHJW4SCEPInstallStatus@@1@Z; UtilsWriteErrorCodeAndStatus(HKEY__ *,ushort const *,int,long,SCEPInstallStatus,ushort const *)
0x18007e355  mov     edi, eax
0x18007e357  test    eax, eax
0x18007e359  js      short loc_18007E3D3
0x18007e35b  mov     r9d, cs:?m_fIsCertStore@CSCEPNode@@0HA; unsigned int
0x18007e362  lea     r8, aLegacycertstor; "LegacyCertStoreCsp"
0x18007e369  lea     rdx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007e371  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x18007e378  call    ?UtilsWriteRegistryDWORDValue@@YAJPEAUHKEY__@@PEBG1K@Z; UtilsWriteRegistryDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x18007e37d  mov     edi, eax
0x18007e37f  test    eax, eax
0x18007e381  js      short loc_18007E3D3
0x18007e383  lea     r9, Class; unsigned __int16 *
0x18007e38a  lea     r8, aRespondentserv_0; "RespondentServerURL"
0x18007e391  lea     rdx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007e399  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x18007e3a0  call    ?UtilsWriteRegistryStringValue@@YAJPEAUHKEY__@@PEBG11@Z; UtilsWriteRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18007e3a5  mov     edi, eax
0x18007e3a7  test    eax, eax
0x18007e3a9  js      short loc_18007E3D3
0x18007e3ab  lea     r9, Class; unsigned __int16 *
0x18007e3b2  lea     r8, aCertthumbprint_0; "CertThumbPrint"
0x18007e3b9  lea     rdx, [rsp+0B18h+SubKey]; unsigned __int16 *
0x18007e3c1  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x18007e3c8  call    ?UtilsWriteRegistryStringValue@@YAJPEAUHKEY__@@PEBG11@Z; UtilsWriteRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18007e3cd  mov     edi, eax
  ... truncated ...
```
