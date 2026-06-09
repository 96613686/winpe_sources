# NotificationProcessor::TriggerRefreshTask(void)

- ea: `0x18002f1f8`
- end: `0x18002f580`
- name: `?TriggerRefreshTask@NotificationProcessor@@AEBAXXZ`
- size: `904`
- prototype: `void __fastcall(NotificationProcessor *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002e8e0`

## callees

- `0x180002790`
- `0x180008200`
- `0x180008234`
- `0x180008388`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x180010c34`
- `0x180011844`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x180023a70`
- `0x18002f1f8`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002f25c`
- `OLEAUT32!__imp_VariantInit` at `0x18002f25c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f243`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f243`

## string_xrefs

- `0x18002f472`: `NT Authority\Local Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall NotificationProcessor::TriggerRefreshTask(NotificationProcessor *this)
{
  HRESULT Instance; // ebx
  ITaskService *p; // rbx
  HRESULT (__fastcall *GetFolder)(ITaskService *, wchar_t *, ITaskFolder **); // rdi
  wchar_t **v5; // rax
  wchar_t *v6; // rdx
  std::wstring *v7; // rax
  std::wstring *v8; // rax
  ITaskFolder *v9; // rbx
  HRESULT (__fastcall *GetTask)(ITaskFolder *, wchar_t *, IRegisteredTask **); // rdi
  const wchar_t *v11; // rax
  wchar_t **v12; // rax
  wchar_t *v13; // rdx
  IRegisteredTask *v14; // rbx
  HRESULT (__fastcall *RunEx)(IRegisteredTask *, tagVARIANT, int, int, wchar_t *, IRunningTask **); // rdi
  _MCGEN_TRACE_CONTEXT *v16; // rcx
  _bstr_t v17; // [rsp+40h] [rbp-C0h] BYREF
  std::wstring result; // [rsp+50h] [rbp-B0h] BYREF
  std::wstring v19; // [rsp+70h] [rbp-90h] BYREF
  tagVARIANT v20; // [rsp+90h] [rbp-70h] BYREF
  ATL::CComPtr<IRunningTask> spRunningTask; // [rsp+B0h] [rbp-50h] BYREF
  ATL::CComPtr<ITaskService> spTaskService; // [rsp+B8h] [rbp-48h] BYREF
  ATL::CComPtr<IRegisteredTask> spRegTask; // [rsp+C0h] [rbp-40h] BYREF
  ATL::CComPtr<ITaskFolder> spRootFolder; // [rsp+C8h] [rbp-38h] BYREF
  tagVARIANT vtEmpty; // [rsp+D0h] [rbp-30h] BYREF
  std::wstring taskPath; // [rsp+F0h] [rbp-10h] BYREF

  spTaskService.p = 0;
  Instance = CoCreateInstance(
               &CLSID_TaskScheduler,
               0,
               0x17u,
               &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
               (LPVOID *)&spTaskService.p);
  memset(&vtEmpty, 0, sizeof(vtEmpty));
  VariantInit(&vtEmpty);
  if ( Instance >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Au, WPP_08a204a1ff063f8d073d2068da1922b9_Traceguids);
    }
    v20 = vtEmpty;
    result._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
    result._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
    v19._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
    v19._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
    taskPath._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
    taskPath._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
    Instance = ((__int64 (__fastcall *)(ITaskService *, std::wstring *, std::wstring *, std::wstring *, tagVARIANT *))spTaskService.p->Connect)(
                 spTaskService.p,
                 &taskPath,
                 &v19,
                 &result,
                 &v20);
  }
  spRootFolder.p = 0;
  if ( Instance >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Bu, WPP_08a204a1ff063f8d073d2068da1922b9_Traceguids);
    }
    p = spTaskService.p;
    GetFolder = spTaskService.p->GetFolder;
    _bstr_t::_bstr_t((_bstr_t *)&spRunningTask, L"\\");
    v6 = *v5;
    if ( *v5 )
      v6 = *(wchar_t **)v6;
    Instance = GetFolder(p, v6, &spRootFolder.p);
    _bstr_t::_Free((_bstr_t *)&spRunningTask);
  }
  spRegTask.p = 0;
  if ( Instance < 0 )
    goto LABEL_27;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Cu, WPP_08a204a1ff063f8d073d2068da1922b9_Traceguids);
  }
  v7 = std::operator+<unsigned short>(&result, L"Microsoft\\Windows\\WCM\\Provisioning\\", &this->m_carrierId);
  v8 = std::operator+<unsigned short>(&v19, v7, L"\\");
  std::operator+<unsigned short>(&taskPath, v8, &this->m_subscriberId);
  std::wstring::_Tidy_deallocate(&v19);
  std::wstring::_Tidy_deallocate(&result);
  v9 = spRootFolder.p;
  GetTask = spRootFolder.p->GetTask;
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&taskPath._Mypair._Myval2);
  _bstr_t::_bstr_t((_bstr_t *)&spRunningTask, v11);
  v13 = *v12;
  if ( *v12 )
    v13 = *(wchar_t **)v13;
  Instance = GetTask(v9, v13, &spRegTask.p);
  _bstr_t::_Free((_bstr_t *)&spRunningTask);
  std::wstring::_Tidy_deallocate(&taskPath);
  if ( Instance < 0 )
    goto LABEL_27;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Du, WPP_08a204a1ff063f8d073d2068da1922b9_Traceguids);
  }
  spRunningTask.p = 0;
  v14 = spRegTask.p;
  RunEx = spRegTask.p->RunEx;
  _bstr_t::_bstr_t(&v17, L"NT Authority\\Local Service");
  taskPath._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
  taskPath._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
  Instance = ((__int64 (__fastcall *)(IRegisteredTask *, std::wstring *, __int64))RunEx)(v14, &taskPath, 1);
  _bstr_t::_Free(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spRunningTask);
  if ( Instance < 0 )
  {
LABEL_27:
    v16 = (_MCGEN_TRACE_CONTEXT *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x3Fu, WPP_08a204a1ff063f8d073d2068da1922b9_Traceguids, Instance);
    }
  }
  else
  {
    v16 = (_MCGEN_TRACE_CONTEXT *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Eu, WPP_08a204a1ff063f8d073d2068da1922b9_Traceguids);
    }
  }
  if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x10) != 0 )
    McTemplateU0d_EtwEventWriteTransfer(v16, &TriggerRefreshTaskResults, Instance);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spRegTask);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spRootFolder);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spTaskService);
}

```

## disassembly

```asm
0x18002f1f8  push    rbp
0x18002f1fa  push    rbx
0x18002f1fb  push    rsi
0x18002f1fc  push    rdi
0x18002f1fd  push    r12
0x18002f1ff  push    r13
0x18002f201  lea     rbp, [rsp-28h]
0x18002f206  sub     rsp, 128h
0x18002f20d  mov     rax, cs:__security_cookie
0x18002f214  xor     rax, rsp
0x18002f217  mov     [rbp+50h+var_40], rax
0x18002f21b  mov     rsi, this
0x18002f21e  mov     [rbp+50h+spTaskService.p], 0
0x18002f226  lea     rax, [rbp+50h+spTaskService]
0x18002f22a  mov     [rsp+150h+ppv], rax; ppv
0x18002f22f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002f236  xor     edx, edx; pUnkOuter
0x18002f238  lea     r8d, [rdx+17h]; dwClsContext
0x18002f23c  lea     this, CLSID_TaskScheduler; rclsid
0x18002f243  call    cs:__imp_CoCreateInstance
0x18002f249  mov     ebx, eax
0x18002f24b  xorps   xmm0, xmm0
0x18002f24e  xor     eax, eax
0x18002f250  movups  xmmword ptr [rbp+50h+vtEmpty.___u0], xmm0
0x18002f254  mov     [rbp+50h+vtEmpty.pRecInfo], rax
0x18002f258  lea     this, [rbp+50h+vtEmpty]; pvarg
0x18002f25c  call    cs:__imp_VariantInit
0x18002f262  lea     r12, WPP_GLOBAL_Control
0x18002f269  lea     r13, WPP_08a204a1ff063f8d073d2068da1922b9_Traceguids
0x18002f270  test    ebx, ebx
0x18002f272  js      short loc_18002F2F0
0x18002f274  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002f27b  cmp     this, r12
0x18002f27e  jz      short loc_18002F297
0x18002f280  test    byte ptr [this+1Ch], 10h
0x18002f284  jz      short loc_18002F297
0x18002f286  mov     edx, 3Ah ; ':'; id
0x18002f28b  mov     r8, r13; TraceGuid
0x18002f28e  mov     this, [this+10h]; Logger
0x18002f292  call    WPP_SF_
0x18002f297  mov     this, [rbp+50h+spTaskService.p]
0x18002f29b  movups  xmm1, xmmword ptr [rbp+50h+vtEmpty.___u0]
0x18002f29f  movsd   xmm0, [rbp+50h+vtEmpty.pRecInfo]
0x18002f2a4  movaps  [rbp+50h+var_C0], xmm1
0x18002f2a8  movsd   [rbp+50h+var_B0], xmm0
0x18002f2ad  movaps  xmmword ptr [rsp+150h+result._Mypair._Myval2._Bx], xmm1
0x18002f2b2  movsd   [rsp+150h+result._Mypair._Myval2._Mysize], xmm0
0x18002f2b8  movaps  xmmword ptr [rsp+150h+var_E0._Mypair._Myval2._Bx], xmm1
0x18002f2bd  movsd   [rbp+50h+var_E0._Mypair._Myval2._Mysize], xmm0
0x18002f2c2  movaps  xmmword ptr [rbp+50h+taskPath._Mypair._Myval2._Bx], xmm1
0x18002f2c6  movsd   [rbp+50h+taskPath._Mypair._Myval2._Mysize], xmm0
0x18002f2cb  mov     rax, [this]
0x18002f2ce  lea     rdx, [rbp+50h+var_C0]
0x18002f2d2  mov     [rsp+150h+ppv], rdx
0x18002f2d7  lea     r9, [rsp+150h+result]
0x18002f2dc  lea     r8, [rsp+150h+var_E0]
0x18002f2e1  lea     rdx, [rbp+50h+taskPath]
0x18002f2e5  mov     rax, [rax+50h]
0x18002f2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2ee  mov     ebx, eax
0x18002f2f0  mov     [rbp+50h+spRootFolder.p], 0
0x18002f2f8  test    ebx, ebx
0x18002f2fa  js      short loc_18002F360
0x18002f2fc  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002f303  cmp     this, r12
0x18002f306  jz      short loc_18002F31F
0x18002f308  test    byte ptr [this+1Ch], 10h
0x18002f30c  jz      short loc_18002F31F
0x18002f30e  mov     edx, 3Bh ; ';'; id
0x18002f313  mov     r8, r13; TraceGuid
0x18002f316  mov     this, [this+10h]; Logger
0x18002f31a  call    WPP_SF_
0x18002f31f  mov     rbx, [rbp+50h+spTaskService.p]
0x18002f323  mov     rax, [rbx]
0x18002f326  mov     rdi, [rax+38h]
0x18002f32a  lea     rdx, s; "\\"
0x18002f331  lea     this, [rbp+50h+spRunningTask]; this
0x18002f335  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002f33a  nop
0x18002f33b  mov     rdx, [rax]
0x18002f33e  test    rdx, rdx
0x18002f341  jz      short loc_18002F346
0x18002f343  mov     rdx, [rdx]
0x18002f346  lea     r8, [rbp+50h+spRootFolder]
0x18002f34a  mov     this, rbx
0x18002f34d  mov     rax, rdi
0x18002f350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f355  mov     ebx, eax
0x18002f357  lea     this, [rbp+50h+spRunningTask]; this
0x18002f35b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002f360  mov     [rbp+50h+spRegTask.p], 0
0x18002f368  test    ebx, ebx
0x18002f36a  js      loc_18002F508
0x18002f370  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002f377  cmp     this, r12
0x18002f37a  jz      short loc_18002F393
0x18002f37c  test    byte ptr [this+1Ch], 10h
0x18002f380  jz      short loc_18002F393
0x18002f382  mov     edx, 3Ch ; '<'; id
0x18002f387  mov     r8, r13; TraceGuid
0x18002f38a  mov     this, [this+10h]; Logger
0x18002f38e  call    WPP_SF_
0x18002f393  lea     r8, [rsi+30h]; _Right
0x18002f397  lea     rdx, _Left; "Microsoft\\Windows\\WCM\\Provisioning\\"
0x18002f39e  lea     this, [rsp+150h+result]; result
0x18002f3a3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18002f3a8  nop
0x18002f3a9  lea     r8, s; "\\"
0x18002f3b0  mov     rdx, rax; _Left
0x18002f3b3  lea     this, [rsp+150h+var_E0]; result
0x18002f3b8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002f3bd  nop
0x18002f3be  lea     r8, [rsi+50h]; _Right
0x18002f3c2  mov     rdx, rax; _Left
0x18002f3c5  lea     this, [rbp+50h+taskPath]; result
0x18002f3c9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18002f3ce  nop
0x18002f3cf  lea     this, [rsp+150h+var_E0]; this
0x18002f3d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f3d9  nop
0x18002f3da  lea     this, [rsp+150h+result]; this
0x18002f3df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f3e4  mov     rbx, [rbp+50h+spRootFolder.p]
0x18002f3e8  mov     rax, [rbx]
0x18002f3eb  mov     rdi, [rax+68h]
0x18002f3ef  lea     this, [rbp+50h+taskPath]; this
0x18002f3f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f3f8  mov     rdx, rax; s
0x18002f3fb  lea     this, [rbp+50h+spRunningTask]; this
0x18002f3ff  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002f404  nop
0x18002f405  mov     rdx, [rax]
0x18002f408  test    rdx, rdx
0x18002f40b  jz      short loc_18002F410
0x18002f40d  mov     rdx, [rdx]
0x18002f410  lea     r8, [rbp+50h+spRegTask]
0x18002f414  mov     this, rbx
0x18002f417  mov     rax, rdi
0x18002f41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f41f  mov     ebx, eax
0x18002f421  lea     this, [rbp+50h+spRunningTask]; this
0x18002f425  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002f42a  nop
0x18002f42b  lea     this, [rbp+50h+taskPath]; this
0x18002f42f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f434  test    ebx, ebx
0x18002f436  js      loc_18002F508
0x18002f43c  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002f443  cmp     this, r12
0x18002f446  jz      short loc_18002F45F
0x18002f448  test    byte ptr [this+1Ch], 10h
0x18002f44c  jz      short loc_18002F45F
0x18002f44e  mov     edx, 3Dh ; '='; id
0x18002f453  mov     r8, r13; TraceGuid
0x18002f456  mov     this, [this+10h]; Logger
0x18002f45a  call    WPP_SF_
0x18002f45f  mov     [rbp+50h+spRunningTask.p], 0
0x18002f467  mov     rbx, [rbp+50h+spRegTask.p]
0x18002f46b  mov     rax, [rbx]
0x18002f46e  mov     rdi, [rax+68h]
0x18002f472  lea     rdx, aNtAuthorityLoc; "NT Authority\\Local Service"
0x18002f479  lea     this, [rsp+150h+var_110]; this
0x18002f47e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002f483  nop
0x18002f484  mov     this, [rax]
0x18002f487  test    this, this
0x18002f48a  jz      short loc_18002F491
0x18002f48c  mov     rax, [this]
0x18002f48f  jmp     short loc_18002F493
0x18002f491  xor     eax, eax
0x18002f493  movups  xmm0, xmmword ptr [rbp+50h+vtEmpty.___u0]
0x18002f497  movaps  xmmword ptr [rbp+50h+taskPath._Mypair._Myval2._Bx], xmm0
0x18002f49b  movsd   xmm1, [rbp+50h+vtEmpty.pRecInfo]
0x18002f4a0  movsd   [rbp+50h+taskPath._Mypair._Myval2._Mysize], xmm1
0x18002f4a5  lea     this, [rbp+50h+spRunningTask]
0x18002f4a9  mov     [rsp+150h+var_128], this
0x18002f4ae  mov     [rsp+150h+ppv], rax
0x18002f4b3  xor     r9d, r9d
0x18002f4b6  lea     r8d, [r9+1]
0x18002f4ba  lea     rdx, [rbp+50h+taskPath]
0x18002f4be  mov     this, rbx
0x18002f4c1  mov     rax, rdi
0x18002f4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4c9  mov     ebx, eax
0x18002f4cb  lea     this, [rsp+150h+var_110]; this
0x18002f4d0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002f4d5  nop
0x18002f4d6  lea     this, [rbp+50h+spRunningTask]; this
0x18002f4da  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f4df  test    ebx, ebx
0x18002f4e1  js      short loc_18002F508
0x18002f4e3  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002f4ea  cmp     this, r12
0x18002f4ed  jz      short loc_18002F52E
0x18002f4ef  test    byte ptr [this+1Ch], 10h
0x18002f4f3  jz      short loc_18002F52E
0x18002f4f5  mov     edx, 3Eh ; '>'; id
0x18002f4fa  mov     r8, r13; TraceGuid
0x18002f4fd  mov     this, [this+10h]; Logger
0x18002f501  call    WPP_SF_
0x18002f506  jmp     short loc_18002F52E
0x18002f508  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002f50f  cmp     this, r12
0x18002f512  jz      short loc_18002F52E
0x18002f514  test    byte ptr [this+1Ch], 2
0x18002f518  jz      short loc_18002F52E
0x18002f51a  mov     edx, 3Fh ; '?'; id
0x18002f51f  mov     r9d, ebx; _a1
0x18002f522  mov     r8, r13; TraceGuid
0x18002f525  mov     this, [this+10h]; Logger
0x18002f529  call    WPP_SF_d
0x18002f52e  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 10h
0x18002f535  jz      short loc_18002F547
0x18002f537  mov     r8d, ebx; Context
0x18002f53a  lea     rdx, TriggerRefreshTaskResults; _Arg0
0x18002f541  call    McTemplateU0d_EtwEventWriteTransfer
0x18002f546  nop
0x18002f547  lea     this, [rbp+50h+spRegTask]; this
0x18002f54b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f550  nop
0x18002f551  lea     this, [rbp+50h+spRootFolder]; this
0x18002f555  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f55a  nop
0x18002f55b  lea     this, [rbp+50h+spTaskService]; this
0x18002f55f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f564  mov     this, [rbp+50h+var_40]
0x18002f568  xor     this, rsp; StackCookie
0x18002f56b  call    __security_check_cookie
0x18002f570  add     rsp, 128h
0x18002f577  pop     r13
0x18002f579  pop     r12
0x18002f57b  pop     rdi
0x18002f57c  pop     rsi
0x18002f57d  pop     rbx
0x18002f57e  pop     rbp
0x18002f57f  retn
```
