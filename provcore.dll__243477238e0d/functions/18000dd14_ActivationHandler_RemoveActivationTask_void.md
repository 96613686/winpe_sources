# ActivationHandler::RemoveActivationTask(void)

- ea: `0x18000dd14`
- end: `0x18000e120`
- name: `?RemoveActivationTask@ActivationHandler@@QEAAXXZ`
- size: `1036`
- prototype: `void __fastcall(ActivationHandler *this)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000db30`
- `0x18002dee4`

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
- `0x18000dd14`
- `0x18000fa6c`
- `0x180010c34`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x180020e70`
- `0x18002108c`
- `0x1800211e0`
- `0x18003bda0`
- `0x18003c2d0`
- `0x18003cb9c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000dddd`
- `OLEAUT32!__imp_VariantInit` at `0x18000dddd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000dd5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000dd5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ActivationHandler::RemoveActivationTask(ActivationHandler *this)
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
      v4 = 44;
LABEL_12:
      WPP_SF_d(v3->Control.Logger, v4, (const _GUID *)&Descriptor.MatchAnyKeyword, Instance);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x2Du, (const _GUID *)&Descriptor.MatchAnyKeyword);
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
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x2Fu, (const _GUID *)&Descriptor.MatchAnyKeyword);
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
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x30u, (const _GUID *)&Descriptor.MatchAnyKeyword, v9);
      }
      goto LABEL_48;
    }
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x31u, (const _GUID *)&Descriptor.MatchAnyKeyword);
    }
    v10 = std::operator+<unsigned short>(&result, L"Microsoft\\Windows\\WCM\\Provisioning\\", &this->m_params.CarrierId);
    v11 = std::operator+<unsigned short>(&v25, v10, L"\\Activate");
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
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x33u, (const _GUID *)&Descriptor.MatchAnyKeyword);
          v17 = WPP_GLOBAL_Control;
        }
        if ( v17 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v17->ReserveSpace[28] & 0x10) != 0 )
          WPP_SF_(v17->Control.Logger, 0x34u, (const _GUID *)&Descriptor.MatchAnyKeyword);
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
        std::wstring::wstring(&ValueName, L"ActivationParams");
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
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x36u, (const _GUID *)&Descriptor.MatchAnyKeyword);
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
      v15 = 53;
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
      v15 = 50;
      v16 = v12;
    }
    WPP_SF_d(v14->Control.Logger, v15, (const _GUID *)&Descriptor.MatchAnyKeyword, v16);
    goto LABEL_47;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    v4 = 46;
    goto LABEL_12;
  }
LABEL_49:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spTaskService);
}

```

## disassembly

```asm
0x18000dd14  push    rbp
0x18000dd16  push    rbx
0x18000dd17  push    rsi
0x18000dd18  push    rdi
0x18000dd19  push    r14
0x18000dd1b  push    r15
0x18000dd1d  lea     rbp, [rsp-48h]
0x18000dd22  sub     rsp, 148h
0x18000dd29  mov     rax, cs:__security_cookie
0x18000dd30  xor     rax, rsp
0x18000dd33  mov     [rbp+70h+var_38], rax
0x18000dd37  mov     r15, this
0x18000dd3a  mov     [rbp+70h+spTaskService.p], 0
0x18000dd42  lea     rax, [rbp+70h+spTaskService]
0x18000dd46  mov     [rsp+170h+ppv], rax; ppv
0x18000dd4b  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18000dd52  xor     edx, edx; pUnkOuter
0x18000dd54  lea     r8d, [rdx+17h]; dwClsContext
0x18000dd58  lea     this, CLSID_TaskScheduler; rclsid
0x18000dd5f  call    cs:__imp_CoCreateInstance
0x18000dd65  test    eax, eax
0x18000dd67  jns     short loc_18000DD9B
0x18000dd69  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18000dd70  mov     this, cs:WPP_GLOBAL_Control
0x18000dd77  cmp     this, rbx
0x18000dd7a  jz      loc_18000E0FB
0x18000dd80  test    byte ptr [this+1Ch], 4
0x18000dd84  jz      loc_18000E0FB
0x18000dd8a  mov     edx, 2Ch ; ','
0x18000dd8f  lea     r8, Descriptor.MatchAnyKeyword
0x18000dd96  jmp     loc_18000DE61
0x18000dd9b  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18000dda2  lea     rdi, Descriptor.MatchAnyKeyword
0x18000dda9  mov     this, cs:WPP_GLOBAL_Control
0x18000ddb0  cmp     this, rbx
0x18000ddb3  jz      short loc_18000DDCC
0x18000ddb5  test    byte ptr [this+1Ch], 10h
0x18000ddb9  jz      short loc_18000DDCC
0x18000ddbb  mov     edx, 2Dh ; '-'; id
0x18000ddc0  mov     r8, rdi; TraceGuid
0x18000ddc3  mov     this, [this+10h]; Logger
0x18000ddc7  call    WPP_SF_
0x18000ddcc  xorps   xmm0, xmm0
0x18000ddcf  xor     eax, eax
0x18000ddd1  movups  xmmword ptr [rbp+70h+vtEmpty.___u0], xmm0
0x18000ddd5  mov     [rbp+70h+vtEmpty.pRecInfo], rax
0x18000ddd9  lea     this, [rbp+70h+vtEmpty]; pvarg
0x18000dddd  call    cs:__imp_VariantInit
0x18000dde3  mov     this, [rbp+70h+spTaskService.p]
0x18000dde7  movups  xmm1, xmmword ptr [rbp+70h+vtEmpty.___u0]
0x18000ddeb  movsd   xmm0, [rbp+70h+vtEmpty.pRecInfo]
0x18000ddf0  movaps  xmmword ptr [rsp+170h+storeKey._Ptr], xmm1
0x18000ddf5  movsd   [rsp+170h+var_120], xmm0
0x18000ddfb  movaps  xmmword ptr [rbp+70h+result._Mypair._Myval2._Bx], xmm1
0x18000ddff  movsd   [rbp+70h+result._Mypair._Myval2._Mysize], xmm0
0x18000de04  movaps  xmmword ptr [rbp+70h+var_D0._Mypair._Myval2._Bx], xmm1
0x18000de08  movsd   [rbp+70h+var_D0._Mypair._Myval2._Mysize], xmm0
0x18000de0d  movaps  xmmword ptr [rsp+170h+ValueName._Mypair._Myval2._Bx], xmm1
0x18000de12  movsd   [rsp+170h+ValueName._Mypair._Myval2._Mysize], xmm0
0x18000de18  mov     rax, [this]
0x18000de1b  lea     rdx, [rsp+170h+storeKey]
0x18000de20  mov     [rsp+170h+ppv], rdx
0x18000de25  lea     r9, [rbp+70h+result]
0x18000de29  lea     r8, [rbp+70h+var_D0]
0x18000de2d  lea     rdx, [rsp+170h+ValueName]
0x18000de32  mov     rax, [rax+50h]
0x18000de36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de3b  test    eax, eax
0x18000de3d  jns     short loc_18000DE72
0x18000de3f  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000de46  cmp     this, rbx
0x18000de49  jz      loc_18000E0FB
0x18000de4f  test    byte ptr [this+1Ch], 4
0x18000de53  jz      loc_18000E0FB
0x18000de59  mov     edx, 2Eh ; '.'; id
0x18000de5e  mov     r8, rdi; TraceGuid
0x18000de61  mov     r9d, eax; _a1
0x18000de64  mov     this, [this+10h]; Logger
0x18000de68  call    WPP_SF_d
0x18000de6d  jmp     loc_18000E0FB
0x18000de72  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000de79  cmp     this, rbx
0x18000de7c  jz      short loc_18000DE95
0x18000de7e  test    byte ptr [this+1Ch], 10h
0x18000de82  jz      short loc_18000DE95
0x18000de84  mov     edx, 2Fh ; '/'; id
0x18000de89  mov     r8, rdi; TraceGuid
0x18000de8c  mov     this, [this+10h]; Logger
0x18000de90  call    WPP_SF_
0x18000de95  mov     [rbp+70h+spFolder.p], 0
0x18000de9d  mov     rsi, [rbp+70h+spTaskService.p]
0x18000dea1  mov     rax, [rsi]
0x18000dea4  mov     r14, [rax+38h]
0x18000dea8  lea     rdx, s; "\\"
0x18000deaf  lea     this, [rsp+170h+storeKey]; this
0x18000deb4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000deb9  nop
0x18000deba  mov     rdx, [rax]
0x18000debd  test    rdx, rdx
0x18000dec0  jz      short loc_18000DEC5
0x18000dec2  mov     rdx, [rdx]
0x18000dec5  lea     r8, [rbp+70h+spFolder]
0x18000dec9  mov     this, rsi
0x18000decc  mov     rax, r14
0x18000decf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ded4  mov     esi, eax
0x18000ded6  lea     this, [rsp+170h+storeKey]; this
0x18000dedb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000dee0  test    esi, esi
0x18000dee2  jns     short loc_18000DF17
0x18000dee4  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000deeb  cmp     this, rbx
0x18000deee  jz      loc_18000E0F1
0x18000def4  test    byte ptr [this+1Ch], 4
0x18000def8  jz      loc_18000E0F1
0x18000defe  mov     edx, 30h ; '0'; id
0x18000df03  mov     r9d, esi; _a1
0x18000df06  mov     r8, rdi; TraceGuid
0x18000df09  mov     this, [this+10h]; Logger
0x18000df0d  call    WPP_SF_d
0x18000df12  jmp     loc_18000E0F1
0x18000df17  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000df1e  cmp     this, rbx
0x18000df21  jz      short loc_18000DF3A
0x18000df23  test    byte ptr [this+1Ch], 10h
0x18000df27  jz      short loc_18000DF3A
0x18000df29  mov     edx, 31h ; '1'; id
0x18000df2e  mov     r8, rdi; TraceGuid
0x18000df31  mov     this, [this+10h]; Logger
0x18000df35  call    WPP_SF_
0x18000df3a  lea     r8, [r15+8]; _Right
0x18000df3e  lea     rdx, _Left; "Microsoft\\Windows\\WCM\\Provisioning\\"
0x18000df45  lea     this, [rbp+70h+result]; result
0x18000df49  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18000df4e  nop
0x18000df4f  lea     r8, aActivate; "\\Activate"
0x18000df56  mov     rdx, rax; _Left
0x18000df59  lea     this, [rbp+70h+var_D0]; result
0x18000df5d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18000df62  nop
0x18000df63  lea     r8, [r15+28h]; _Right
0x18000df67  mov     rdx, rax; _Left
0x18000df6a  lea     this, [rbp+70h+taskPath]; result
0x18000df6e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18000df73  nop
0x18000df74  lea     this, [rbp+70h+var_D0]; this
0x18000df78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000df7d  nop
0x18000df7e  lea     this, [rbp+70h+result]; this
0x18000df82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000df87  lea     rdx, [rbp+70h+taskPath]; Path
0x18000df8b  mov     this, [rbp+70h+spFolder.p]; Folder
0x18000df8f  call    ?DeletePurgeTask@@YAJPEAUITaskFolder@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DeletePurgeTask(ITaskFolder *,std::wstring &)
0x18000df94  mov     esi, eax
0x18000df96  test    eax, eax
0x18000df98  jns     short loc_18000DFC1
0x18000df9a  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000dfa1  cmp     this, rbx
0x18000dfa4  jz      loc_18000E0E7
0x18000dfaa  test    byte ptr [this+1Ch], 4
0x18000dfae  jz      loc_18000E0E7
0x18000dfb4  mov     edx, 32h ; '2'
0x18000dfb9  mov     r9d, eax
0x18000dfbc  jmp     loc_18000E0B5
0x18000dfc1  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000dfc8  cmp     this, rbx
0x18000dfcb  jz      short loc_18000E007
0x18000dfcd  test    byte ptr [this+1Ch], 10h
0x18000dfd1  jz      short loc_18000DFEB
0x18000dfd3  mov     edx, 33h ; '3'; id
0x18000dfd8  mov     r8, rdi; TraceGuid
0x18000dfdb  mov     this, [this+10h]; Logger
0x18000dfdf  call    WPP_SF_
0x18000dfe4  mov     this, cs:WPP_GLOBAL_Control
0x18000dfeb  cmp     this, rbx; __annotation("TMF:",
0x18000dfee  jz      short loc_18000E007
0x18000dff0  test    byte ptr [this+1Ch], 10h
0x18000dff4  jz      short loc_18000E007
0x18000dff6  mov     edx, 34h ; '4'; id
0x18000dffb  mov     r8, rdi; TraceGuid
0x18000dffe  mov     this, [this+10h]; Logger
0x18000e002  call    WPP_SF_
0x18000e007  lea     this, [rsp+170h+revertImpersonate]; this
0x18000e00c  call    ??0AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::AutoRevertImpersonate(void)
0x18000e011  nop
0x18000e012  xorps   xmm0, xmm0
0x18000e015  movups  xmmword ptr [rsp+170h+storeKey._Ptr], xmm0
0x18000e01a  lea     r8, [r15+28h]; SubscriberId
0x18000e01e  lea     rdx, [r15+8]; CarrierId
0x18000e022  lea     this, [rbp+70h+var_B0]; result
0x18000e026  call    ?CreateCarrierSubscriberTasksStore@?$RegistryStore@$00@@SA?AV1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; RegistryStore<1>::CreateCarrierSubscriberTasksStore(std::wstring const &,std::wstring const &)
0x18000e02b  nop
0x18000e02c  mov     rdx, rax; path
0x18000e02f  lea     this, [rsp+170h+storeKey]; result
0x18000e034  call    ?OpenKeyRW@Registry@@YA?AV?$shared_ptr@VKey@Registry@@@std@@AEBVPath@1@@Z; Registry::OpenKeyRW(Registry::Path const &)
0x18000e039  nop
0x18000e03a  lea     this, [rbp+70h+var_B0]; this
0x18000e03e  call    ??1Path@Registry@@QEAA@XZ; Registry::Path::~Path(void)
0x18000e043  mov     r14, [rsp+170h+storeKey._Ptr]
0x18000e048  test    r14, r14
0x18000e04b  jz      short loc_18000E078
0x18000e04d  lea     rdx, aActivationpara; "ActivationParams"
0x18000e054  lea     this, [rsp+170h+ValueName]; this
0x18000e059  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000e05e  lea     rdx, [rsp+170h+ValueName]; ValueName
0x18000e063  mov     this, r14; this
0x18000e066  call    ?DeleteValue@Key@Registry@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Registry::Key::DeleteValue(std::wstring const &)
0x18000e06b  mov     esi, eax
0x18000e06d  lea     this, [rsp+170h+ValueName]; this
0x18000e072  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e077  nop
0x18000e078  mov     this, [rsp+170h+storeKey._Rep]; this
0x18000e07d  test    this, this
0x18000e080  jz      short loc_18000E088
0x18000e082  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e087  nop
0x18000e088  lea     this, [rsp+170h+revertImpersonate]; this
0x18000e08d  call    ??1AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::~AutoRevertImpersonate(void)
0x18000e092  call    ?VerifyUserIsImpersonating@@YAXXZ; VerifyUserIsImpersonating(void)
0x18000e097  test    esi, esi
0x18000e099  jns     short loc_18000E0C3
0x18000e09b  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000e0a2  cmp     this, rbx
0x18000e0a5  jz      short loc_18000E0E7
0x18000e0a7  test    byte ptr [this+1Ch], 4
0x18000e0ab  jz      short loc_18000E0E7
0x18000e0ad  mov     edx, 35h ; '5'; id
0x18000e0b2  mov     r9d, esi; _a1
0x18000e0b5  mov     r8, rdi; TraceGuid
0x18000e0b8  mov     this, [this+10h]; Logger
0x18000e0bc  call    WPP_SF_d
0x18000e0c1  jmp     short loc_18000E0E7
0x18000e0c3  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000e0ca  cmp     this, rbx
0x18000e0cd  jz      short loc_18000E0E7
0x18000e0cf  test    byte ptr [this+1Ch], 10h
0x18000e0d3  jz      short loc_18000E0E7
0x18000e0d5  mov     edx, 36h ; '6'; id
0x18000e0da  mov     r8, rdi; TraceGuid
0x18000e0dd  mov     this, [this+10h]; Logger
0x18000e0e1  call    WPP_SF_
0x18000e0e6  nop
0x18000e0e7  lea     this, [rbp+70h+taskPath]; this
0x18000e0eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e0f0  nop
0x18000e0f1  lea     this, [rbp+70h+spFolder]; this
0x18000e0f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e0fa  nop
0x18000e0fb  lea     this, [rbp+70h+spTaskService]; this
0x18000e0ff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e104  mov     this, [rbp+70h+var_38]
0x18000e108  xor     this, rsp; StackCookie
0x18000e10b  call    __security_check_cookie
0x18000e110  add     rsp, 148h
0x18000e117  pop     r15
0x18000e119  pop     r14
0x18000e11b  pop     rdi
0x18000e11c  pop     rsi
0x18000e11d  pop     rbx
0x18000e11e  pop     rbp
0x18000e11f  retn
```
