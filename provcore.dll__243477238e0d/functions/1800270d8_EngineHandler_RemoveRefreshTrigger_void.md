# EngineHandler::RemoveRefreshTrigger(void)

- ea: `0x1800270d8`
- end: `0x1800274e4`
- name: `?RemoveRefreshTrigger@EngineHandler@@QEAAXXZ`
- size: `1036`
- prototype: `void __fastcall(EngineHandler *this)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026c70`
- `0x180027020`
- `0x180036d38`

## callees

- `0x180002790`
- `0x180008200`
- `0x180008234`
- `0x180008388`
- `0x18000af94`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x18000d024`
- `0x18000d114`
- `0x18000fa6c`
- `0x180010c34`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x180020e70`
- `0x18002108c`
- `0x1800211e0`
- `0x1800270d8`
- `0x18003bda0`
- `0x18003c2d0`
- `0x18003cb9c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800271a1`
- `OLEAUT32!__imp_VariantInit` at `0x1800271a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027123`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027123`

## string_xrefs

- `0x180027411`: `TaskParams`

## pseudocode

```c
void __fastcall EngineHandler::RemoveRefreshTrigger(EngineHandler *this)
{
  HRESULT Instance; // eax
  WPP_PROJECT_CONTROL_BLOCK *v3; // rcx
  unsigned __int16 v4; // dx
  ITaskService *p; // rsi
  HRESULT (__fastcall *GetFolder)(ITaskService *, wchar_t *, ITaskFolder **); // r14
  wchar_t **v7; // rax
  wchar_t *v8; // rdx
  int v9; // esi
  std::wstring *v10; // rax
  std::wstring *v11; // rax
  int v12; // eax
  int v13; // esi
  WPP_PROJECT_CONTROL_BLOCK *v14; // rcx
  unsigned __int16 v15; // dx
  int v16; // r9d
  WPP_PROJECT_CONTROL_BLOCK *v17; // rcx
  RegistryStore<1> *v18; // rax
  Registry::Key *Ptr; // r14
  AutoRevertImpersonate revertImpersonate; // [rsp+30h] [rbp-D0h] BYREF
  std::shared_ptr<Registry::Key> storeKey; // [rsp+40h] [rbp-C0h] BYREF
  IRecordInfo *pRecInfo; // [rsp+50h] [rbp-B0h]
  std::wstring ValueName; // [rsp+60h] [rbp-A0h] BYREF
  std::wstring result; // [rsp+80h] [rbp-80h] BYREF
  std::wstring v25; // [rsp+A0h] [rbp-60h] BYREF
  RegistryStore<1> v26; // [rsp+C0h] [rbp-40h] BYREF
  ATL::CComPtr<ITaskFolder> spFolder; // [rsp+F0h] [rbp-10h] BYREF
  ATL::CComPtr<ITaskService> spTaskService; // [rsp+F8h] [rbp-8h] BYREF
  tagVARIANT vtEmpty; // [rsp+100h] [rbp+0h] BYREF
  std::wstring taskPath; // [rsp+118h] [rbp+18h] BYREF

  spTaskService.p = 0;
  Instance = CoCreateInstance(
               &CLSID_TaskScheduler,
               0,
               0x17u,
               &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
               (LPVOID *)&spTaskService.p);
  if ( Instance < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      v4 = 28;
LABEL_12:
      WPP_SF_d(v3->Control.Logger, v4, WPP_1aa1d128b86532d91064602d584084ba_Traceguids, Instance);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Du, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
  }
  memset(&vtEmpty, 0, sizeof(vtEmpty));
  VariantInit(&vtEmpty);
  storeKey = (std::shared_ptr<Registry::Key>)vtEmpty.0;
  pRecInfo = vtEmpty.pRecInfo;
  result._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
  result._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
  v25._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
  v25._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
  ValueName._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
  ValueName._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
  Instance = ((__int64 (__fastcall *)(ITaskService *, std::wstring *, std::wstring *, std::wstring *, std::shared_ptr<Registry::Key> *))spTaskService.p->Connect)(
               spTaskService.p,
               &ValueName,
               &v25,
               &result,
               &storeKey);
  if ( Instance >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Fu, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
    }
    spFolder.p = 0;
    p = spTaskService.p;
    GetFolder = spTaskService.p->GetFolder;
    _bstr_t::_bstr_t((_bstr_t *)&storeKey, L"\\");
    v8 = *v7;
    if ( *v7 )
      v8 = *(wchar_t **)v8;
    v9 = GetFolder(p, v8, &spFolder.p);
    _bstr_t::_Free((_bstr_t *)&storeKey);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x20u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids, v9);
      }
      goto LABEL_48;
    }
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x21u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
    }
    v10 = std::operator+<unsigned short>(&result, L"Microsoft\\Windows\\WCM\\Provisioning\\", &this->m_params.CarrierId);
    v11 = std::operator+<unsigned short>(&v25, v10, L"\\");
    std::operator+<unsigned short>(&taskPath, v11, &this->m_params.SubscriberId);
    std::wstring::_Tidy_deallocate(&v25);
    std::wstring::_Tidy_deallocate(&result);
    v12 = DeletePurgeTask(spFolder.p, &taskPath);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x23u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
          v17 = WPP_GLOBAL_Control;
        }
        if ( v17 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v17->ReserveSpace[28] & 0x10) != 0 )
          WPP_SF_(v17->Control.Logger, 0x24u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
      }
      AutoRevertImpersonate::AutoRevertImpersonate(&revertImpersonate);
      storeKey = 0;
      v18 = RegistryStore<1>::CreateCarrierSubscriberTasksStore(
              &v26,
              &this->m_params.CarrierId,
              &this->m_params.SubscriberId);
      Registry::OpenKeyRW(&storeKey, &v18->m_storePath);
      Registry::Path::~Path(&v26.m_storePath);
      Ptr = storeKey._Ptr;
      if ( storeKey._Ptr )
      {
        std::wstring::wstring(&ValueName, L"TaskParams");
        v13 = Registry::Key::DeleteValue(Ptr, &ValueName);
        std::wstring::_Tidy_deallocate(&ValueName);
      }
      if ( storeKey._Rep )
        std::_Ref_count_base::_Decref(storeKey._Rep);
      AutoRevertImpersonate::~AutoRevertImpersonate(&revertImpersonate);
      VerifyUserIsImpersonating();
      if ( v13 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x26u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
        }
        goto LABEL_47;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 4) == 0 )
      {
LABEL_47:
        std::wstring::_Tidy_deallocate(&taskPath);
LABEL_48:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spFolder);
        goto LABEL_49;
      }
      v15 = 37;
      v16 = v13;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 4) == 0 )
      {
        goto LABEL_47;
      }
      v15 = 34;
      v16 = v12;
    }
    WPP_SF_d(v14->Control.Logger, v15, WPP_1aa1d128b86532d91064602d584084ba_Traceguids, v16);
    goto LABEL_47;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    v4 = 30;
    goto LABEL_12;
  }
LABEL_49:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spTaskService);
}

```

## disassembly

```asm
0x1800270d8  push    rbp
0x1800270da  push    rbx
0x1800270db  push    rsi
0x1800270dc  push    rdi
0x1800270dd  push    r14
0x1800270df  push    r15
0x1800270e1  lea     rbp, [rsp-48h]
0x1800270e6  sub     rsp, 148h
0x1800270ed  mov     rax, cs:__security_cookie
0x1800270f4  xor     rax, rsp
0x1800270f7  mov     [rbp+70h+var_38], rax
0x1800270fb  mov     r15, this
0x1800270fe  mov     [rbp+70h+spTaskService.p], 0
0x180027106  lea     rax, [rbp+70h+spTaskService]
0x18002710a  mov     [rsp+170h+ppv], rax; ppv
0x18002710f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180027116  xor     edx, edx; pUnkOuter
0x180027118  lea     r8d, [rdx+17h]; dwClsContext
0x18002711c  lea     this, CLSID_TaskScheduler; rclsid
0x180027123  call    cs:__imp_CoCreateInstance
0x180027129  test    eax, eax
0x18002712b  jns     short loc_18002715F
0x18002712d  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x180027134  mov     this, cs:WPP_GLOBAL_Control
0x18002713b  cmp     this, rbx
0x18002713e  jz      loc_1800274BF
0x180027144  test    byte ptr [this+1Ch], 4
0x180027148  jz      loc_1800274BF
0x18002714e  mov     edx, 1Ch
0x180027153  lea     r8, WPP_1aa1d128b86532d91064602d584084ba_Traceguids
0x18002715a  jmp     loc_180027225
0x18002715f  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x180027166  lea     rdi, WPP_1aa1d128b86532d91064602d584084ba_Traceguids
0x18002716d  mov     this, cs:WPP_GLOBAL_Control
0x180027174  cmp     this, rbx
0x180027177  jz      short loc_180027190
0x180027179  test    byte ptr [this+1Ch], 10h
0x18002717d  jz      short loc_180027190
0x18002717f  mov     edx, 1Dh; id
0x180027184  mov     r8, rdi; TraceGuid
0x180027187  mov     this, [this+10h]; Logger
0x18002718b  call    WPP_SF_
0x180027190  xorps   xmm0, xmm0
0x180027193  xor     eax, eax
0x180027195  movups  xmmword ptr [rbp+70h+vtEmpty.___u0], xmm0
0x180027199  mov     [rbp+70h+vtEmpty.pRecInfo], rax
0x18002719d  lea     this, [rbp+70h+vtEmpty]; pvarg
0x1800271a1  call    cs:__imp_VariantInit
0x1800271a7  mov     this, [rbp+70h+spTaskService.p]
0x1800271ab  movups  xmm1, xmmword ptr [rbp+70h+vtEmpty.___u0]
0x1800271af  movsd   xmm0, [rbp+70h+vtEmpty.pRecInfo]
0x1800271b4  movaps  xmmword ptr [rsp+170h+storeKey._Ptr], xmm1
0x1800271b9  movsd   [rsp+170h+var_120], xmm0
0x1800271bf  movaps  xmmword ptr [rbp+70h+result._Mypair._Myval2._Bx], xmm1
0x1800271c3  movsd   [rbp+70h+result._Mypair._Myval2._Mysize], xmm0
0x1800271c8  movaps  xmmword ptr [rbp+70h+var_D0._Mypair._Myval2._Bx], xmm1
0x1800271cc  movsd   [rbp+70h+var_D0._Mypair._Myval2._Mysize], xmm0
0x1800271d1  movaps  xmmword ptr [rsp+170h+ValueName._Mypair._Myval2._Bx], xmm1
0x1800271d6  movsd   [rsp+170h+ValueName._Mypair._Myval2._Mysize], xmm0
0x1800271dc  mov     rax, [this]
0x1800271df  lea     rdx, [rsp+170h+storeKey]
0x1800271e4  mov     [rsp+170h+ppv], rdx
0x1800271e9  lea     r9, [rbp+70h+result]
0x1800271ed  lea     r8, [rbp+70h+var_D0]
0x1800271f1  lea     rdx, [rsp+170h+ValueName]
0x1800271f6  mov     rax, [rax+50h]
0x1800271fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271ff  test    eax, eax
0x180027201  jns     short loc_180027236
0x180027203  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002720a  cmp     this, rbx
0x18002720d  jz      loc_1800274BF
0x180027213  test    byte ptr [this+1Ch], 4
0x180027217  jz      loc_1800274BF
0x18002721d  mov     edx, 1Eh; id
0x180027222  mov     r8, rdi; TraceGuid
0x180027225  mov     r9d, eax; _a1
0x180027228  mov     this, [this+10h]; Logger
0x18002722c  call    WPP_SF_d
0x180027231  jmp     loc_1800274BF
0x180027236  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002723d  cmp     this, rbx
0x180027240  jz      short loc_180027259
0x180027242  test    byte ptr [this+1Ch], 10h
0x180027246  jz      short loc_180027259
0x180027248  mov     edx, 1Fh; id
0x18002724d  mov     r8, rdi; TraceGuid
0x180027250  mov     this, [this+10h]; Logger
0x180027254  call    WPP_SF_
0x180027259  mov     [rbp+70h+spFolder.p], 0
0x180027261  mov     rsi, [rbp+70h+spTaskService.p]
0x180027265  mov     rax, [rsi]
0x180027268  mov     r14, [rax+38h]
0x18002726c  lea     rdx, s; "\\"
0x180027273  lea     this, [rsp+170h+storeKey]; this
0x180027278  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002727d  nop
0x18002727e  mov     rdx, [rax]
0x180027281  test    rdx, rdx
0x180027284  jz      short loc_180027289
0x180027286  mov     rdx, [rdx]
0x180027289  lea     r8, [rbp+70h+spFolder]
0x18002728d  mov     this, rsi
0x180027290  mov     rax, r14
0x180027293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027298  mov     esi, eax
0x18002729a  lea     this, [rsp+170h+storeKey]; this
0x18002729f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800272a4  test    esi, esi
0x1800272a6  jns     short loc_1800272DB
0x1800272a8  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800272af  cmp     this, rbx
0x1800272b2  jz      loc_1800274B5
0x1800272b8  test    byte ptr [this+1Ch], 4
0x1800272bc  jz      loc_1800274B5
0x1800272c2  mov     edx, 20h ; ' '; id
0x1800272c7  mov     r9d, esi; _a1
0x1800272ca  mov     r8, rdi; TraceGuid
0x1800272cd  mov     this, [this+10h]; Logger
0x1800272d1  call    WPP_SF_d
0x1800272d6  jmp     loc_1800274B5
0x1800272db  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800272e2  cmp     this, rbx
0x1800272e5  jz      short loc_1800272FE
0x1800272e7  test    byte ptr [this+1Ch], 10h
0x1800272eb  jz      short loc_1800272FE
0x1800272ed  mov     edx, 21h ; '!'; id
0x1800272f2  mov     r8, rdi; TraceGuid
0x1800272f5  mov     this, [this+10h]; Logger
0x1800272f9  call    WPP_SF_
0x1800272fe  lea     r8, [r15+8]; _Right
0x180027302  lea     rdx, _Left; "Microsoft\\Windows\\WCM\\Provisioning\\"
0x180027309  lea     this, [rbp+70h+result]; result
0x18002730d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180027312  nop
0x180027313  lea     r8, s; "\\"
0x18002731a  mov     rdx, rax; _Left
0x18002731d  lea     this, [rbp+70h+var_D0]; result
0x180027321  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180027326  nop
0x180027327  lea     r8, [r15+28h]; _Right
0x18002732b  mov     rdx, rax; _Left
0x18002732e  lea     this, [rbp+70h+taskPath]; result
0x180027332  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180027337  nop
0x180027338  lea     this, [rbp+70h+var_D0]; this
0x18002733c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027341  nop
0x180027342  lea     this, [rbp+70h+result]; this
0x180027346  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002734b  lea     rdx, [rbp+70h+taskPath]; Path
0x18002734f  mov     this, [rbp+70h+spFolder.p]; Folder
0x180027353  call    ?DeletePurgeTask@@YAJPEAUITaskFolder@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DeletePurgeTask(ITaskFolder *,std::wstring &)
0x180027358  mov     esi, eax
0x18002735a  test    eax, eax
0x18002735c  jns     short loc_180027385
0x18002735e  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180027365  cmp     this, rbx
0x180027368  jz      loc_1800274AB
0x18002736e  test    byte ptr [this+1Ch], 4
0x180027372  jz      loc_1800274AB
0x180027378  mov     edx, 22h ; '"'
0x18002737d  mov     r9d, eax
0x180027380  jmp     loc_180027479
0x180027385  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002738c  cmp     this, rbx
0x18002738f  jz      short loc_1800273CB
0x180027391  test    byte ptr [this+1Ch], 10h
0x180027395  jz      short loc_1800273AF
0x180027397  mov     edx, 23h ; '#'; id
0x18002739c  mov     r8, rdi; TraceGuid
0x18002739f  mov     this, [this+10h]; Logger
0x1800273a3  call    WPP_SF_
0x1800273a8  mov     this, cs:WPP_GLOBAL_Control
0x1800273af  cmp     this, rbx; __annotation("TMF:",
0x1800273b2  jz      short loc_1800273CB
0x1800273b4  test    byte ptr [this+1Ch], 10h
0x1800273b8  jz      short loc_1800273CB
0x1800273ba  mov     edx, 24h ; '$'; id
0x1800273bf  mov     r8, rdi; TraceGuid
0x1800273c2  mov     this, [this+10h]; Logger
0x1800273c6  call    WPP_SF_
0x1800273cb  lea     this, [rsp+170h+revertImpersonate]; this
0x1800273d0  call    ??0AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::AutoRevertImpersonate(void)
0x1800273d5  nop
0x1800273d6  xorps   xmm0, xmm0
0x1800273d9  movups  xmmword ptr [rsp+170h+storeKey._Ptr], xmm0
0x1800273de  lea     r8, [r15+28h]; SubscriberId
0x1800273e2  lea     rdx, [r15+8]; CarrierId
0x1800273e6  lea     this, [rbp+70h+var_B0]; result
0x1800273ea  call    ?CreateCarrierSubscriberTasksStore@?$RegistryStore@$00@@SA?AV1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; RegistryStore<1>::CreateCarrierSubscriberTasksStore(std::wstring const &,std::wstring const &)
0x1800273ef  nop
0x1800273f0  mov     rdx, rax; path
0x1800273f3  lea     this, [rsp+170h+storeKey]; result
0x1800273f8  call    ?OpenKeyRW@Registry@@YA?AV?$shared_ptr@VKey@Registry@@@std@@AEBVPath@1@@Z; Registry::OpenKeyRW(Registry::Path const &)
0x1800273fd  nop
0x1800273fe  lea     this, [rbp+70h+var_B0]; this
0x180027402  call    ??1Path@Registry@@QEAA@XZ; Registry::Path::~Path(void)
0x180027407  mov     r14, [rsp+170h+storeKey._Ptr]
0x18002740c  test    r14, r14
0x18002740f  jz      short loc_18002743C
0x180027411  lea     rdx, aTaskparams; "TaskParams"
0x180027418  lea     this, [rsp+170h+ValueName]; this
0x18002741d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027422  lea     rdx, [rsp+170h+ValueName]; ValueName
0x180027427  mov     this, r14; this
0x18002742a  call    ?DeleteValue@Key@Registry@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Registry::Key::DeleteValue(std::wstring const &)
0x18002742f  mov     esi, eax
0x180027431  lea     this, [rsp+170h+ValueName]; this
0x180027436  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002743b  nop
0x18002743c  mov     this, [rsp+170h+storeKey._Rep]; this
0x180027441  test    this, this
0x180027444  jz      short loc_18002744C
0x180027446  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002744b  nop
0x18002744c  lea     this, [rsp+170h+revertImpersonate]; this
0x180027451  call    ??1AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::~AutoRevertImpersonate(void)
0x180027456  call    ?VerifyUserIsImpersonating@@YAXXZ; VerifyUserIsImpersonating(void)
0x18002745b  test    esi, esi
0x18002745d  jns     short loc_180027487
0x18002745f  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180027466  cmp     this, rbx
0x180027469  jz      short loc_1800274AB
0x18002746b  test    byte ptr [this+1Ch], 4
0x18002746f  jz      short loc_1800274AB
0x180027471  mov     edx, 25h ; '%'; id
0x180027476  mov     r9d, esi; _a1
0x180027479  mov     r8, rdi; TraceGuid
0x18002747c  mov     this, [this+10h]; Logger
0x180027480  call    WPP_SF_d
0x180027485  jmp     short loc_1800274AB
0x180027487  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002748e  cmp     this, rbx
0x180027491  jz      short loc_1800274AB
0x180027493  test    byte ptr [this+1Ch], 10h
0x180027497  jz      short loc_1800274AB
0x180027499  mov     edx, 26h ; '&'; id
0x18002749e  mov     r8, rdi; TraceGuid
0x1800274a1  mov     this, [this+10h]; Logger
0x1800274a5  call    WPP_SF_
0x1800274aa  nop
0x1800274ab  lea     this, [rbp+70h+taskPath]; this
0x1800274af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800274b4  nop
0x1800274b5  lea     this, [rbp+70h+spFolder]; this
0x1800274b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800274be  nop
0x1800274bf  lea     this, [rbp+70h+spTaskService]; this
0x1800274c3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800274c8  mov     this, [rbp+70h+var_38]
0x1800274cc  xor     this, rsp; StackCookie
0x1800274cf  call    __security_check_cookie
0x1800274d4  add     rsp, 148h
0x1800274db  pop     r15
0x1800274dd  pop     r14
0x1800274df  pop     rdi
0x1800274e0  pop     rsi
0x1800274e1  pop     rbx
0x1800274e2  pop     rbp
0x1800274e3  retn
```
