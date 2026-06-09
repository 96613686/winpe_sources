# CSCEPNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18007e5f0`
- end: `0x18007ea1a`
- name: `?CreateNodeInstance@CSCEPNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `1066`
- prototype: `__int64 __usercall@<rax>(struct CConfigServiceProvider2Impl *@<rcx>, struct IConfigManager2URI *@<rdx>, const struct CSP_NODE_DATA *@<r8>, int@<r9d>, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x180015888`
- `0x18001a4fc`
- `0x180023f1c`
- `0x18002dcc8`
- `0x18003f3a0`
- `0x18003f6f0`
- `0x18007db70`
- `0x18007e4f8`
- `0x18007e5f0`
- `0x180080ba8`
- `0x1800817a8`
- `0x180081918`
- `0x180081a28`
- `0x1800d1fa8`
- `0x1800d20d0`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e720`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e720`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18007e7d0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18007e7d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18007e793`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18007e793`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e800`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e800`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSCEPNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  int v6; // ebx
  unsigned int v10; // ebx
  int v11; // eax
  signed int Instance; // edi
  int v13; // eax
  LSTATUS v14; // eax
  char IsStateSeparationEnabled; // al
  int v16; // ecx
  struct ICSPNode *v17; // rbx
  __int64 Imei; // rax
  CClientCertScepLogger *Logger; // rax
  const unsigned __int16 *v20; // r8
  wil *v21; // rcx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  signed int v26; // [rsp+30h] [rbp-B8h]
  int v27; // [rsp+34h] [rbp-B4h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-B0h] BYREF
  struct ICSPNode *v29; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-A0h] BYREF
  unsigned __int16 *v31; // [rsp+50h] [rbp-98h] BYREF
  __int16 v32; // [rsp+58h] [rbp-90h] BYREF
  char v33; // [rsp+5Ah] [rbp-8Eh]
  __int64 v34; // [rsp+60h] [rbp-88h]
  unsigned __int16 *v35[2]; // [rsp+68h] [rbp-80h] BYREF
  __m128i si128; // [rsp+78h] [rbp-70h]
  _BYTE v37[32]; // [rsp+88h] [rbp-60h] BYREF

  v6 = a4;
  v27 = a4;
  v31 = 0;
  v29 = 0;
  v28 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( !a1 || !a2 || !a3 || !a5 || !a6 )
  {
    Instance = -2147024809;
    goto LABEL_40;
  }
  if ( (unsigned int)(*((_DWORD *)a3 + 3) - 27) > 2 )
  {
    *a5 = 0;
    *a6 = 0;
    v11 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, unsigned int *))(*(_QWORD *)a2 + 136LL))(a2, &v28);
    Instance = v11;
    v26 = v11;
    if ( v28 <= 1 || v11 < 0 )
    {
LABEL_25:
      v16 = *((_DWORD *)a3 + 3);
      if ( v16 )
      {
        if ( v16 == 1 )
        {
          Instance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                       a2,
                       *((unsigned int *)a3 + 2),
                       &v31);
          v26 = Instance;
          if ( Instance < 0 )
            goto LABEL_22;
          Instance = CSCEPNode::ValidateUniqueId(v31);
          v26 = Instance;
          if ( Instance < 0 )
            goto LABEL_22;
          if ( !CSCEPNode::IsUniqueIdPreviouslyProcessed(a1, a2) )
          {
            Instance = -2046820350;
            goto LABEL_44;
          }
        }
        Instance = CSCEPNode::ValidateRegistryContentsForCreateInstance(a1, a2, a3, v6);
        v26 = Instance;
      }
      if ( Instance < 0 )
        goto LABEL_22;
      Instance = ATL::CComObject<CSCEPNode>::CreateInstance(&v29);
      v26 = Instance;
      if ( Instance < 0 )
        goto LABEL_22;
      v17 = v29;
      if ( v29 )
      {
        Instance = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v29 + 136LL))(
                     v29,
                     a1,
                     a2,
                     a3);
        v26 = Instance;
        if ( Instance >= 0 )
        {
          (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v17 + 8LL))(v17);
          *((_DWORD *)v17 + 32) = CSCEPNode::m_fIsCertStore == 0;
          v29 = 0;
          *a5 = v17;
          if ( *((_DWORD *)a3 + 3) == 17 )
            *a6 |= 2u;
          goto LABEL_44;
        }
LABEL_22:
        if ( Instance != -2046820350 )
          goto LABEL_49;
LABEL_44:
        v10 = Instance;
        goto LABEL_45;
      }
      Instance = -2147024882;
LABEL_40:
      v26 = Instance;
LABEL_49:
      try
      {
        *(_OWORD *)v35 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v35[0]) = 0;
        Imei = CellularIdentity::GetImei((char *)a1 + 104, v37);
        std::wstring::operator=(v35, Imei);
        std::wstring::_Tidy_deallocate(v37);
        Logger = CClientCertScepLogger::GetLogger();
        v20 = (const unsigned __int16 *)v35;
        if ( si128.m128i_i64[1] > 7uLL )
          v20 = v35[0];
        CClientCertScepLogger::LogSCEPCspCreateInstance(Logger, Instance, v20, *(const unsigned __int16 **)a3);
        std::wstring::_Tidy_deallocate(v35);
      }
      catch ( ... )
      {
        v23 = wil::ResultFromCaughtException(v21);
        if ( (unsigned int)dword_180155C20 > 3 )
        {
          v27 = v23;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180155C20,
            (unsigned int)&byte_180134A27,
            v24,
            v25,
            (__int64)&v27);
        }
        Instance = v26;
        goto LABEL_44;
      }
      goto LABEL_44;
    }
    v30 = 0;
    Instance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64 *))(*(_QWORD *)a2 + 88LL))(
                 a2,
                 0,
                 &v30);
    v26 = Instance;
    if ( Instance < 0 )
      goto LABEL_22;
    v13 = _o__wcsicmp(v30, L"certificatestore");
    CSCEPNode::m_fIsUser = v13 == 0;
    CSCEPNode::m_fIsCertStore = v13 == 0;
    if ( v13 )
    {
      if ( *((_DWORD *)a1 + 62) != 1 )
      {
        CSCEPNode::m_fIsUser = 0;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(&CSCEPNode::m_hCurrentHive);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &CSCEPNode::m_hCurrentHive,
          0);
        IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
        v14 = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                (LPCWSTR)((unsigned __int64)L"OSData\\" & -(__int64)(IsStateSeparationEnabled != 0)),
                0,
                0xF003Fu,
                &CSCEPNode::m_hCurrentHive);
LABEL_16:
        if ( v14 )
        {
          if ( v14 > 0 )
            Instance = (unsigned __int16)v14 | 0x80070000;
          else
            Instance = v14;
          v26 = Instance;
          goto LABEL_22;
        }
        v6 = v27;
        goto LABEL_25;
      }
      CSCEPNode::m_fIsUser = 1;
    }
    Instance = AutoImpersonate::ImpersonateTargetedUser((AutoImpersonate *)&v32, a1);
    v26 = Instance;
    if ( Instance < 0 )
      goto LABEL_22;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(&CSCEPNode::m_hCurrentHive);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &CSCEPNode::m_hCurrentHive,
      0);
    v14 = RegOpenCurrentUser(0xF003Fu, &CSCEPNode::m_hCurrentHive);
    goto LABEL_16;
  }
  v10 = -2046820350;
LABEL_45:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v32);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v29);
  return v10;
}

```

## disassembly

```asm
0x18007e5f0  push    rbx
0x18007e5f2  push    rsi
0x18007e5f3  push    rdi
0x18007e5f4  push    r12
0x18007e5f6  push    r13
0x18007e5f8  push    r14
0x18007e5fa  push    r15
0x18007e5fc  sub     rsp, 0B0h
0x18007e603  mov     rax, cs:__security_cookie
0x18007e60a  xor     rax, rsp
0x18007e60d  mov     [rsp+0E8h+var_40], rax
0x18007e615  mov     ebx, r9d
0x18007e618  mov     [rsp+0E8h+var_B4], ebx
0x18007e61c  mov     rsi, r8
0x18007e61f  mov     r14, rdx
0x18007e622  mov     r15, rcx
0x18007e625  mov     r13, [rsp+0E8h+arg_20]
0x18007e62d  mov     r12, [rsp+0E8h+arg_28]
0x18007e635  mov     [rsp+0E8h+var_98], 0
0x18007e63e  mov     [rsp+0E8h+var_A8], 0
0x18007e647  mov     [rsp+0E8h+var_B0], 0
0x18007e64f  mov     [rsp+0E8h+var_90], 0
0x18007e656  mov     [rsp+0E8h+var_8E], 0
0x18007e65b  mov     [rsp+0E8h+var_88], 0
0x18007e664  test    rcx, rcx
0x18007e667  jz      loc_18007E945
0x18007e66d  test    rdx, rdx
0x18007e670  jz      loc_18007E945
0x18007e676  test    r8, r8
0x18007e679  jz      loc_18007E945
0x18007e67f  test    r13, r13
0x18007e682  jz      loc_18007E945
0x18007e688  test    r12, r12
0x18007e68b  jz      loc_18007E945
0x18007e691  mov     eax, [r8+0Ch]
0x18007e695  sub     eax, 1Bh
0x18007e698  cmp     eax, 2
0x18007e69b  ja      short loc_18007E6A7
0x18007e69d  mov     ebx, 86000002h
0x18007e6a2  jmp     loc_18007E9DF
0x18007e6a7  mov     qword ptr [r13+0], 0
0x18007e6af  mov     dword ptr [r12], 0
0x18007e6b7  mov     rax, [rdx]
0x18007e6ba  lea     rdx, [rsp+0E8h+var_B0]
0x18007e6bf  mov     rcx, r14
0x18007e6c2  mov     rax, [rax+88h]
0x18007e6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6ce  mov     edi, eax
0x18007e6d0  mov     [rsp+0E8h+var_B8], eax
0x18007e6d4  cmp     [rsp+0E8h+var_B0], 1
0x18007e6d9  jbe     loc_18007E839
0x18007e6df  test    eax, eax
0x18007e6e1  js      loc_18007E839
0x18007e6e7  mov     [rsp+0E8h+var_A0], 0
0x18007e6f0  mov     rax, [r14]
0x18007e6f3  lea     r8, [rsp+0E8h+var_A0]
0x18007e6f8  xor     edx, edx
0x18007e6fa  mov     rcx, r14
0x18007e6fd  mov     rax, [rax+58h]
0x18007e701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e706  mov     edi, eax
0x18007e708  mov     [rsp+0E8h+var_B8], eax
0x18007e70c  test    eax, eax
0x18007e70e  js      loc_18007E823
0x18007e714  lea     rdx, aCertificatesto_0; "certificatestore"
0x18007e71b  mov     rcx, [rsp+0E8h+var_A0]
0x18007e720  call    cs:__imp__o__wcsicmp
0x18007e727  nop     dword ptr [rax+rax+00h]
0x18007e72c  xor     ecx, ecx
0x18007e72e  test    eax, eax
0x18007e730  setz    cl
0x18007e733  mov     cs:?m_fIsUser@CSCEPNode@@0HA, ecx; int CSCEPNode::m_fIsUser
0x18007e739  mov     cs:?m_fIsCertStore@CSCEPNode@@0HA, ecx; int CSCEPNode::m_fIsCertStore
0x18007e73f  test    eax, eax
0x18007e741  jz      short loc_18007E757
0x18007e743  cmp     dword ptr [r15+0F8h], 1
0x18007e74b  jnz     short loc_18007E7AD
0x18007e74d  mov     cs:?m_fIsUser@CSCEPNode@@0HA, 1; int CSCEPNode::m_fIsUser
0x18007e757  mov     rdx, r15; struct CConfigServiceProvider2Impl *
0x18007e75a  lea     rcx, [rsp+0E8h+var_90]; this
0x18007e75f  call    ?ImpersonateTargetedUser@AutoImpersonate@@QEAAJPEAVCConfigServiceProvider2Impl@@@Z; AutoImpersonate::ImpersonateTargetedUser(CConfigServiceProvider2Impl *)
0x18007e764  mov     edi, eax
0x18007e766  mov     [rsp+0E8h+var_B8], eax
0x18007e76a  test    eax, eax
0x18007e76c  js      loc_18007E823
0x18007e772  lea     rbx, ?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x18007e779  mov     rcx, rbx
0x18007e77c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(std::nullptr_t)
0x18007e781  xor     edx, edx
0x18007e783  mov     rcx, rbx
0x18007e786  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007e78b  mov     rdx, rbx; phkResult
0x18007e78e  mov     ecx, 0F003Fh; samDesired
0x18007e793  call    cs:__imp_RegOpenCurrentUser
0x18007e79a  nop     dword ptr [rax+rax+00h]
0x18007e79f  test    eax, eax
0x18007e7a1  jz      loc_18007E835
0x18007e7a7  jg      short loc_18007E80E
0x18007e7a9  mov     edi, eax
0x18007e7ab  jmp     short loc_18007E817
0x18007e7ad  mov     cs:?m_fIsUser@CSCEPNode@@0HA, 0; int CSCEPNode::m_fIsUser
0x18007e7b7  lea     rbx, ?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x18007e7be  mov     rcx, rbx
0x18007e7c1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(std::nullptr_t)
0x18007e7c6  xor     edx, edx
0x18007e7c8  mov     rcx, rbx
0x18007e7cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007e7d0  call    cs:__imp_RtlIsStateSeparationEnabled
0x18007e7d7  nop     dword ptr [rax+rax+00h]
0x18007e7dc  lea     rcx, aOsdata_0; "OSData\\"
0x18007e7e3  neg     al
0x18007e7e5  sbb     rdx, rdx
0x18007e7e8  and     rdx, rcx; lpSubKey
0x18007e7eb  mov     [rsp+0E8h+phkResult], rbx; phkResult
0x18007e7f0  mov     r9d, 0F003Fh; samDesired
0x18007e7f6  xor     r8d, r8d; ulOptions
0x18007e7f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007e800  call    cs:__imp_RegOpenKeyExW
0x18007e807  nop     dword ptr [rax+rax+00h]
0x18007e80c  jmp     short loc_18007E79F
0x18007e80e  movzx   edi, ax
0x18007e811  or      edi, 80070000h
0x18007e817  mov     [rsp+0E8h+var_B8], edi
0x18007e81b  test    edi, edi
0x18007e81d  jns     loc_18007E9DD
0x18007e823  mov     ebx, 86000002h
0x18007e828  cmp     edi, ebx
0x18007e82a  jz      loc_18007E9DD
0x18007e830  jmp     loc_18007E94E
0x18007e835  mov     ebx, [rsp+0E8h+var_B4]
0x18007e839  mov     ecx, [rsi+0Ch]
0x18007e83c  test    ecx, ecx
0x18007e83e  jz      short loc_18007E8AA
0x18007e840  cmp     ecx, 1
0x18007e843  jnz     short loc_18007E893
0x18007e845  mov     rax, [r14]
0x18007e848  lea     r8, [rsp+0E8h+var_98]
0x18007e84d  mov     edx, [rsi+8]
0x18007e850  mov     rcx, r14
0x18007e853  mov     rax, [rax+58h]
0x18007e857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e85c  mov     edi, eax
0x18007e85e  mov     [rsp+0E8h+var_B8], eax
0x18007e862  test    eax, eax
0x18007e864  js      short loc_18007E823
0x18007e866  mov     rcx, [rsp+0E8h+var_98]; unsigned __int16 *
0x18007e86b  call    ?ValidateUniqueId@CSCEPNode@@CAJPEBG@Z; CSCEPNode::ValidateUniqueId(ushort const *)
0x18007e870  mov     edi, eax
0x18007e872  mov     [rsp+0E8h+var_B8], eax
0x18007e876  test    eax, eax
0x18007e878  js      short loc_18007E823
0x18007e87a  mov     rdx, r14; struct IConfigManager2URI *
0x18007e87d  mov     rcx, r15; struct CConfigServiceProvider2Impl *
0x18007e880  call    ?IsUniqueIdPreviouslyProcessed@CSCEPNode@@CA_NPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@@Z; CSCEPNode::IsUniqueIdPreviouslyProcessed(CConfigServiceProvider2Impl *,IConfigManager2URI *)
0x18007e885  test    al, al
0x18007e887  jnz     short loc_18007E893
0x18007e889  mov     edi, 86000002h
0x18007e88e  jmp     loc_18007E9DD
0x18007e893  mov     r9d, ebx; int
0x18007e896  mov     r8, rsi; struct CSP_NODE_DATA *
0x18007e899  mov     rdx, r14; struct IConfigManager2URI *
0x18007e89c  mov     rcx, r15; struct CConfigServiceProvider2Impl *
0x18007e89f  call    ?ValidateRegistryContentsForCreateInstance@CSCEPNode@@CAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@H@Z; CSCEPNode::ValidateRegistryContentsForCreateInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int)
0x18007e8a4  mov     edi, eax
0x18007e8a6  mov     [rsp+0E8h+var_B8], eax
0x18007e8aa  test    edi, edi
0x18007e8ac  js      loc_18007E823
0x18007e8b2  lea     rcx, [rsp+0E8h+var_A8]
0x18007e8b7  call    ?CreateInstance@?$CComObject@VCSCEPNode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSCEPNode>::CreateInstance(ATL::CComObject<CSCEPNode> * *)
0x18007e8bc  mov     edi, eax
0x18007e8be  mov     [rsp+0E8h+var_B8], eax
0x18007e8c2  test    eax, eax
0x18007e8c4  js      loc_18007E823
0x18007e8ca  mov     rbx, [rsp+0E8h+var_A8]
0x18007e8cf  test    rbx, rbx
0x18007e8d2  jnz     short loc_18007E8DB
0x18007e8d4  mov     edi, 8007000Eh
0x18007e8d9  jmp     short loc_18007E94A
0x18007e8db  mov     rax, [rbx]
0x18007e8de  mov     r9, rsi
0x18007e8e1  mov     r8, r14
0x18007e8e4  mov     rdx, r15
0x18007e8e7  mov     rcx, rbx
0x18007e8ea  mov     rax, [rax+88h]
0x18007e8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e8f6  mov     edi, eax
0x18007e8f8  mov     [rsp+0E8h+var_B8], eax
0x18007e8fc  test    eax, eax
0x18007e8fe  js      loc_18007E823
0x18007e904  mov     rax, [rbx]
0x18007e907  mov     rcx, rbx
0x18007e90a  mov     rax, [rax+8]
0x18007e90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e913  xor     eax, eax
0x18007e915  cmp     cs:?m_fIsCertStore@CSCEPNode@@0HA, eax; int CSCEPNode::m_fIsCertStore
0x18007e91b  setz    al
0x18007e91e  mov     [rbx+80h], eax
0x18007e924  mov     [rsp+0E8h+var_A8], 0
0x18007e92d  mov     [r13+0], rbx
0x18007e931  cmp     dword ptr [rsi+0Ch], 11h
0x18007e935  jnz     loc_18007E9DD
0x18007e93b  or      dword ptr [r12], 2
0x18007e940  jmp     loc_18007E9DD
0x18007e945  mov     edi, 80070057h
0x18007e94a  mov     [rsp+0E8h+var_B8], edi
0x18007e94e  xorps   xmm0, xmm0
0x18007e951  movups  xmmword ptr [rsp+0E8h+var_80], xmm0
0x18007e956  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007e95e  movdqu  [rsp+0E8h+var_70], xmm1
0x18007e964  xor     eax, eax
0x18007e966  mov     word ptr [rsp+0E8h+var_80], ax
0x18007e96b  lea     rcx, [r15+68h]
0x18007e96f  lea     rdx, [rsp+0E8h+var_60]
0x18007e977  cmp     cs:?m_fIsCertStore@CSCEPNode@@0HA, eax; int CSCEPNode::m_fIsCertStore
0x18007e97d  jz      short loc_18007E986
0x18007e97f  call    ?GetImei@CellularIdentity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CellularIdentity::GetImei(void)
0x18007e984  jmp     short loc_18007E98B
0x18007e986  call    ?GetImei@CellularIdentity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CellularIdentity::GetImei(void)
0x18007e98b  mov     rdx, rax
0x18007e98e  lea     rcx, [rsp+0E8h+var_80]
0x18007e993  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007e998  lea     rcx, [rsp+0E8h+var_60]
0x18007e9a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e9a5  call    ?GetLogger@CClientCertScepLogger@@SAPEAV1@XZ; CClientCertScepLogger::GetLogger(void)
0x18007e9aa  lea     r8, [rsp+0E8h+var_80]
0x18007e9af  cmp     qword ptr [rsp+0E8h+var_70+8], 7
0x18007e9b8  cmova   r8, [rsp+0E8h+var_80]; unsigned __int16 *
0x18007e9be  mov     r9, [rsi]; unsigned __int16 *
0x18007e9c1  mov     edx, edi; int
0x18007e9c3  mov     rcx, rax; this
0x18007e9c6  call    ?LogSCEPCspCreateInstance@CClientCertScepLogger@@QEAAXJPEBG0@Z; CClientCertScepLogger::LogSCEPCspCreateInstance(long,ushort const *,ushort const *)
0x18007e9cb  nop
0x18007e9cc  lea     rcx, [rsp+0E8h+var_80]
0x18007e9d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e9d6  nop
0x18007e9d7  jmp     short loc_18007E9DD
0x18007e9d9  mov     edi, [rsp+0E8h+var_B8]
0x18007e9dd  mov     ebx, edi
0x18007e9df  lea     rcx, [rsp+0E8h+var_90]; this
0x18007e9e4  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18007e9e9  nop
0x18007e9ea  lea     rcx, [rsp+0E8h+var_A8]
0x18007e9ef  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x18007e9f4  mov     eax, ebx
0x18007e9f6  mov     rcx, [rsp+0E8h+var_40]
0x18007e9fe  xor     rcx, rsp; StackCookie
0x18007ea01  call    __security_check_cookie
0x18007ea06  add     rsp, 0B0h
0x18007ea0d  pop     r15
0x18007ea0f  pop     r14
0x18007ea11  pop     r13
0x18007ea13  pop     r12
0x18007ea15  pop     rdi
0x18007ea16  pop     rsi
0x18007ea17  pop     rbx
0x18007ea18  retn
```
