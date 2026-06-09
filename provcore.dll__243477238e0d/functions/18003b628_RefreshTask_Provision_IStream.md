# RefreshTask::Provision(IStream *)

- ea: `0x18003b628`
- end: `0x18003b926`
- name: `?Provision@RefreshTask@@AEAAJPEAUIStream@@@Z`
- size: `766`
- prototype: `HRESULT __fastcall(RefreshTask *this, IStream *pStream)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b2d8`

## callees

- `0x180002790`
- `0x18000b2f4`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x18003adcc`
- `0x18003b628`
- `0x18003b92c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b875`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b6c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b6c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RefreshTask::Provision(RefreshTask *this, IStream *pStream)
{
  WPP_PROJECT_CONTROL_BLOCK *v3; // rcx
  int Instance; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v5; // rcx
  wchar_t *SignerDisplayName; // rax
  unsigned __int16 v7; // dx
  const _GUID *v8; // r8
  PROVISIONING_DOCUMENT_SIGNATURE_INFO signatureInfo; // [rsp+30h] [rbp-40h] BYREF
  void *errorOccured; // [rsp+48h] [rbp-28h] BYREF
  ATL::CComPtr<IProvisioningDocument> spDocument; // [rsp+50h] [rbp-20h] BYREF
  ATL::CComPtr<IProvisioningEngine> spEngine; // [rsp+58h] [rbp-18h] BYREF

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  spEngine.p = 0;
  if ( v3 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v3->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_(v3->Control.Logger, 0x19u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
  Instance = CoCreateInstance(
               &CLSID_ProvisioningEngine,
               0,
               4u,
               &GUID_217700e0_1001_11df_adb9_f4ce462d9137,
               (LPVOID *)&spEngine.p);
  if ( Instance >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Au, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
    }
    errorOccured = spEngine.p;
    if ( spEngine.p )
      spEngine.p->AddRef(spEngine.p);
    Instance = AllowImpersonation<IProvisioningDocument>((const ATL::CComPtr<IProvisioningEngine>)&errorOccured);
  }
  spDocument.p = 0;
  if ( Instance < 0 )
    goto LABEL_43;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Bu, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
  }
  Instance = spEngine.p->CreateDocumentFromStream(spEngine.p, pStream, (IProvisioningDocument **)&spDocument);
  if ( Instance < 0 )
    goto LABEL_43;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Cu, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
  }
  errorOccured = spDocument.p;
  if ( spDocument.p )
    spDocument.p->AddRef(spDocument.p);
  Instance = AllowImpersonation<IProvisioningDocument>((const ATL::CComPtr<IProvisioningEngine>)&errorOccured);
  if ( Instance < 0 )
    goto LABEL_43;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Du, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
  }
  memset(&signatureInfo, 0, sizeof(signatureInfo));
  Instance = spDocument.p->GetSignatureInformation(spDocument.p, &signatureInfo);
  if ( Instance < 0 )
    goto LABEL_43;
  if ( !signatureInfo.DocumentIsSigned )
  {
    Instance = -2112421874;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
    {
      goto LABEL_34;
    }
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Eu, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids, -2112421874);
  }
  v5 = WPP_GLOBAL_Control;
LABEL_34:
  SignerDisplayName = signatureInfo.SignerDisplayName;
  if ( signatureInfo.SignerDisplayName )
  {
    if ( v5 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v5->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_S(
        v5->Control.Logger,
        0x1Fu,
        WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids,
        signatureInfo.SignerDisplayName);
      SignerDisplayName = signatureInfo.SignerDisplayName;
    }
    CoTaskMemFree(SignerDisplayName);
    v5 = WPP_GLOBAL_Control;
  }
  if ( Instance >= 0 )
  {
    LODWORD(errorOccured) = 0;
    Instance = spDocument.p->Provision(spDocument.p, (int *)&errorOccured);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_47;
    if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
    {
      WPP_SF_dl(WPP_GLOBAL_Control->Control.Logger, v7, v8, Instance, (int)errorOccured);
LABEL_43:
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( v5 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v5->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v5->Control.Logger, 0x21u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids, Instance);
LABEL_47:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spDocument);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spEngine);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003b628  mov     [rsp-18h+arg_0], rbx
0x18003b62d  mov     [rsp-18h+arg_10], rdi
0x18003b632  push    rbp
0x18003b633  push    r12
0x18003b635  push    r14
0x18003b637  mov     rbp, rsp
0x18003b63a  sub     rsp, 70h
0x18003b63e  mov     rax, cs:__security_cookie
0x18003b645  xor     rax, rsp
0x18003b648  mov     [rbp+var_10], rax
0x18003b64c  mov     rdi, pStream
0x18003b64f  lea     r14, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b656  lea     r12, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids
0x18003b65d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b664  cmp     rcx, r14
0x18003b667  jz      short loc_18003B687
0x18003b669  test    byte ptr [rcx+1Ch], 10h
0x18003b66d  jz      short loc_18003B687
0x18003b66f  mov     edx, 18h; id
0x18003b674  mov     r8, r12; TraceGuid
0x18003b677  mov     rcx, [rcx+10h]; Logger
0x18003b67b  call    WPP_SF_
0x18003b680  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b687  mov     [rbp+spEngine.p], 0
0x18003b68f  cmp     rcx, r14; __annotation("TMF:",
0x18003b692  jz      short loc_18003B6AB
0x18003b694  test    byte ptr [rcx+1Ch], 10h
0x18003b698  jz      short loc_18003B6AB
0x18003b69a  mov     edx, 19h; id
0x18003b69f  mov     r8, r12; TraceGuid
0x18003b6a2  mov     rcx, [rcx+10h]; Logger
0x18003b6a6  call    WPP_SF_
0x18003b6ab  lea     rax, [rbp+spEngine]
0x18003b6af  mov     [rsp+70h+ppv], rax; ppv
0x18003b6b4  lea     r9, _GUID_217700e0_1001_11df_adb9_f4ce462d9137; riid
0x18003b6bb  xor     edx, edx; pUnkOuter
0x18003b6bd  lea     r8d, [pStream+4]; dwClsContext
0x18003b6c1  lea     rcx, CLSID_ProvisioningEngine; rclsid
0x18003b6c8  call    cs:__imp_CoCreateInstance
0x18003b6ce  mov     ebx, eax
0x18003b6d0  test    eax, eax
0x18003b6d2  js      short loc_18003B71C
0x18003b6d4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b6db  cmp     rcx, r14
0x18003b6de  jz      short loc_18003B6F7
0x18003b6e0  test    byte ptr [rcx+1Ch], 10h
0x18003b6e4  jz      short loc_18003B6F7
0x18003b6e6  mov     edx, 1Ah; id
0x18003b6eb  mov     r8, r12; TraceGuid
0x18003b6ee  mov     rcx, [rcx+10h]; Logger
0x18003b6f2  call    WPP_SF_
0x18003b6f7  mov     rcx, [rbp+spEngine.p]
0x18003b6fb  mov     [rbp+errorOccured], rcx
0x18003b6ff  test    rcx, rcx
0x18003b702  jz      short loc_18003B711
0x18003b704  mov     rax, [rcx]
0x18003b707  mov     rax, [rax+8]
0x18003b70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b710  nop
0x18003b711  lea     rcx, [rbp+errorOccured]; spObj
0x18003b715  call    ??$AllowImpersonation@UIProvisioningDocument@@@@YAJV?$CComPtr@UIProvisioningDocument@@@ATL@@@Z; AllowImpersonation<IProvisioningDocument>(ATL::CComPtr<IProvisioningDocument>)
0x18003b71a  mov     ebx, eax
0x18003b71c  mov     [rbp+spDocument.p], 0
0x18003b724  test    ebx, ebx
0x18003b726  js      loc_18003B8C8
0x18003b72c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b733  cmp     rcx, r14
0x18003b736  jz      short loc_18003B74F
0x18003b738  test    byte ptr [rcx+1Ch], 10h
0x18003b73c  jz      short loc_18003B74F
0x18003b73e  mov     edx, 1Bh; id
0x18003b743  mov     r8, r12; TraceGuid
0x18003b746  mov     rcx, [rcx+10h]; Logger
0x18003b74a  call    WPP_SF_
0x18003b74f  mov     rcx, [rbp+spEngine.p]
0x18003b753  mov     rax, [rcx]
0x18003b756  lea     r8, [rbp+spDocument]
0x18003b75a  mov     pStream, rdi
0x18003b75d  mov     rax, [rax+18h]
0x18003b761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b766  mov     ebx, eax
0x18003b768  test    eax, eax
0x18003b76a  js      loc_18003B8C8
0x18003b770  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b777  cmp     rcx, r14
0x18003b77a  jz      short loc_18003B793
0x18003b77c  test    byte ptr [rcx+1Ch], 10h
0x18003b780  jz      short loc_18003B793
0x18003b782  mov     edx, 1Ch; id
0x18003b787  mov     r8, r12; TraceGuid
0x18003b78a  mov     rcx, [rcx+10h]; Logger
0x18003b78e  call    WPP_SF_
0x18003b793  mov     rcx, [rbp+spDocument.p]
0x18003b797  mov     [rbp+errorOccured], rcx
0x18003b79b  test    rcx, rcx
0x18003b79e  jz      short loc_18003B7AD
0x18003b7a0  mov     rax, [rcx]
0x18003b7a3  mov     rax, [rax+8]
0x18003b7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7ac  nop
0x18003b7ad  lea     rcx, [rbp+errorOccured]; spObj
0x18003b7b1  call    ??$AllowImpersonation@UIProvisioningDocument@@@@YAJV?$CComPtr@UIProvisioningDocument@@@ATL@@@Z; AllowImpersonation<IProvisioningDocument>(ATL::CComPtr<IProvisioningDocument>)
0x18003b7b6  mov     ebx, eax
0x18003b7b8  test    eax, eax
0x18003b7ba  js      loc_18003B8C8
0x18003b7c0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b7c7  cmp     rcx, r14
0x18003b7ca  jz      short loc_18003B7E3
0x18003b7cc  test    byte ptr [rcx+1Ch], 10h
0x18003b7d0  jz      short loc_18003B7E3
0x18003b7d2  mov     edx, 1Dh; id
0x18003b7d7  mov     r8, r12; TraceGuid
0x18003b7da  mov     rcx, [rcx+10h]; Logger
0x18003b7de  call    WPP_SF_
0x18003b7e3  xorps   xmm0, xmm0
0x18003b7e6  xor     eax, eax
0x18003b7e8  movups  xmmword ptr [rbp+signatureInfo.DocumentIsSigned], xmm0
0x18003b7ec  mov     [rbp+signatureInfo.SignerDisplayName], rax
0x18003b7f0  mov     rcx, [rbp+spDocument.p]
0x18003b7f4  mov     rax, [rcx]
0x18003b7f7  lea     pStream, [rbp+signatureInfo]
0x18003b7fb  mov     rax, [rax+30h]
0x18003b7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b804  mov     ebx, eax
0x18003b806  test    eax, eax
0x18003b808  js      loc_18003B8C8
0x18003b80e  cmp     [rbp+signatureInfo.DocumentIsSigned], 0
0x18003b812  jnz     short loc_18003B83F
0x18003b814  mov     ebx, 8217000Eh
0x18003b819  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b820  cmp     rcx, r14
0x18003b823  jz      short loc_18003B846
0x18003b825  test    byte ptr [rcx+1Ch], 2
0x18003b829  jz      short loc_18003B846
0x18003b82b  mov     edx, 1Eh; id
0x18003b830  mov     r9d, ebx; _a1
0x18003b833  mov     r8, r12; TraceGuid
0x18003b836  mov     rcx, [rcx+10h]; Logger
0x18003b83a  call    WPP_SF_d
0x18003b83f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b846  mov     rax, [rbp+signatureInfo.SignerDisplayName]
0x18003b84a  test    rax, rax
0x18003b84d  jz      short loc_18003B882
0x18003b84f  cmp     rcx, r14; __annotation("TMF:",
0x18003b852  jz      short loc_18003B872
0x18003b854  test    byte ptr [rcx+1Ch], 10h
0x18003b858  jz      short loc_18003B872
0x18003b85a  mov     edx, 1Fh; id
0x18003b85f  mov     r9, rax; _a1
0x18003b862  mov     r8, r12; TraceGuid
0x18003b865  mov     rcx, [rcx+10h]; Logger
0x18003b869  call    WPP_SF_S
0x18003b86e  mov     rax, [rbp+signatureInfo.SignerDisplayName]
0x18003b872  mov     rcx, rax; pv
0x18003b875  call    cs:__imp_CoTaskMemFree
0x18003b87b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b882  test    ebx, ebx
0x18003b884  js      short loc_18003B8CF
0x18003b886  mov     dword ptr [rbp+errorOccured], 0
0x18003b88d  mov     rcx, [rbp+spDocument.p]
0x18003b891  mov     rax, [rcx]
0x18003b894  lea     pStream, [rbp+errorOccured]
0x18003b898  mov     rax, [rax+18h]
0x18003b89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8a1  mov     ebx, eax
0x18003b8a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b8aa  cmp     rcx, r14
0x18003b8ad  jz      short loc_18003B8EF
0x18003b8af  test    byte ptr [rcx+1Ch], 8
0x18003b8b3  jz      short loc_18003B8CF
0x18003b8b5  mov     eax, dword ptr [rbp+errorOccured]
0x18003b8b8  mov     dword ptr [rsp+70h+ppv], eax; id
0x18003b8bc  mov     r9d, ebx; Logger
0x18003b8bf  mov     rcx, [rcx+10h]; Logger
0x18003b8c3  call    WPP_SF_dl
0x18003b8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b8cf  cmp     rcx, r14; __annotation("TMF:",
0x18003b8d2  jz      short loc_18003B8EF
0x18003b8d4  test    byte ptr [rcx+1Ch], 10h
0x18003b8d8  jz      short loc_18003B8EF
0x18003b8da  mov     edx, 21h ; '!'; id
0x18003b8df  mov     r9d, ebx; _a1
0x18003b8e2  mov     r8, r12; TraceGuid
0x18003b8e5  mov     rcx, [rcx+10h]; Logger
0x18003b8e9  call    WPP_SF_d
0x18003b8ee  nop
0x18003b8ef  lea     rcx, [rbp+spDocument]; this
0x18003b8f3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b8f8  nop
0x18003b8f9  lea     rcx, [rbp+spEngine]; this
0x18003b8fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b902  mov     eax, ebx
0x18003b904  mov     rcx, [rbp+var_10]
0x18003b908  xor     rcx, rsp; StackCookie
0x18003b90b  call    __security_check_cookie
0x18003b910  lea     r11, [rsp+70h+var_s0]
0x18003b915  mov     rbx, [r11+20h]
0x18003b919  mov     rdi, [r11+30h]
0x18003b91d  mov     rsp, r11
0x18003b920  pop     r14
0x18003b922  pop     r12
0x18003b924  pop     rbp
0x18003b925  retn
```
