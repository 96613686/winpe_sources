# CallerCanAccessClipboardData(IDataObject *,bool *)

- ea: `0x180037d28`
- end: `0x180037ef1`
- name: `?CallerCanAccessClipboardData@@YAJPEAUIDataObject@@PEA_N@Z`
- size: `457`
- prototype: `HRESULT __fastcall(IDataObject *dataObject, bool *result)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009c20`

## callees

- `0x18001217c`
- `0x180037d28`
- `0x180049dd4`
- `0x180049edc`
- `0x18004a1c0`
- `0x18008798c`
- `0x1800879ac`
- `0x180088884`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037e4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037e4b`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180037d76`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180037d76`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsUIPolicyEvaluationEnabledForThread` at `0x180037d57`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsUIPolicyEvaluationEnabledForThread` at `0x180037d57`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180037d43`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180037d43`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccessForContext` at `0x180037e95`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccessForContext` at `0x180037e95`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetEnterpriseIdForClipboard` at `0x180037e02`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetEnterpriseIdForClipboard` at `0x180037e02`

## string_xrefs

- `0x180037d8c`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180037e1d`: `com\ole32\ole232\clipbrd\clipapi.cpp`

## pseudocode

```c
__int64 __fastcall CallerCanAccessClipboardData(IDataObject *dataObject, bool *result)
{
  HRESULT ContextForWindow; // eax
  unsigned int v5; // ebx
  wchar_t *m_ptr; // rbx
  HRESULT EnterpriseIdForClipboard; // eax
  unsigned int v8; // edx
  DWORD CurrentProcessId; // eax
  wil::last_error_context v11; // [rsp+40h] [rbp-40h] BYREF
  CallerCanAccessClipboardData::__l5::AUDIT_CALLBACK_CONTEXT callbackContext; // [rsp+48h] [rbp-38h] BYREF
  EDP_REQUEST_ACCESS_OPTIONS options; // [rsp+50h] [rbp-30h] BYREF
  void *retaddr; // [rsp+98h] [rbp+18h]
  EDP_POLICY_RESULT edpResult; // [rsp+A8h] [rbp+28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > sourceEnterpriseId; // [rsp+B0h] [rbp+30h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > > edpContext; // [rsp+B8h] [rbp+38h] BYREF

  *result = 1;
  if ( !(unsigned int)EdpGetIsManaged() || !(unsigned int)EdpIsUIPolicyEvaluationEnabledForThread() )
    return 0;
  edpContext.m_ptr = 0;
  ContextForWindow = EdpGetContextForWindow(0, &edpContext);
  v5 = ContextForWindow;
  if ( ContextForWindow >= 0 )
  {
    if ( (edpContext.m_ptr->contextStates & 1) != 0
      || (edpContext.m_ptr->contextStates & 2) != 0 && edpContext.m_ptr->allowedEnterpriseIdCount )
    {
      v5 = 0;
      goto LABEL_19;
    }
    sourceEnterpriseId.m_ptr = 0;
    if ( GetDataObjectEnterpriseId(dataObject, &sourceEnterpriseId.m_ptr) < 0 )
    {
      m_ptr = sourceEnterpriseId.m_ptr;
      if ( sourceEnterpriseId.m_ptr )
      {
        wil::last_error_context::last_error_context(&v11);
        wil::details::FreeProcessHeap(m_ptr);
        wil::last_error_context::~last_error_context(&v11);
      }
      sourceEnterpriseId.m_ptr = 0;
      EnterpriseIdForClipboard = EdpGetEnterpriseIdForClipboard(&sourceEnterpriseId);
      v5 = EnterpriseIdForClipboard;
      if ( EnterpriseIdForClipboard < 0 )
      {
        v8 = 2625;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          v8,
          "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
          EnterpriseIdForClipboard);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceEnterpriseId);
        goto LABEL_19;
      }
    }
    memset(&options, 0, sizeof(options));
    CurrentProcessId = GetCurrentProcessId();
    edpResult = EdpPolicyResult_Unknown;
    options.processIdForClipboardConsentCache = CurrentProcessId;
    options.overrideOption = EDP_REQUEST_ACCESS_OVERRIDE_NO_DIALOG;
    callbackContext.dataObject = dataObject;
    EnterpriseIdForClipboard = EdpRequestAccessForContext(
                                 0,
                                 sourceEnterpriseId.m_ptr,
                                 edpContext.m_ptr,
                                 lambda_2aa60daf810bf981192e67453d2e1fb5_::_lambda_invoker_cdecl_,
                                 &callbackContext,
                                 &options,
                                 &edpResult);
    v5 = EnterpriseIdForClipboard;
    if ( EnterpriseIdForClipboard < 0 )
    {
      v8 = 2655;
      goto LABEL_13;
    }
    *result = edpResult == EdpPolicyResult_Allowed;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceEnterpriseId);
    wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&edpContext);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0xA2Du, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", ContextForWindow);
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&edpContext);
  return v5;
}

```

## disassembly

```asm
0x180037d28  mov     [rsp-18h+arg_0], rbx
0x180037d2d  push    rbp
0x180037d2e  push    rsi
0x180037d2f  push    rdi
0x180037d30  mov     rbp, rsp
0x180037d33  sub     rsp, 80h
0x180037d3a  mov     rdi, result
0x180037d3d  mov     byte ptr [result], 1
0x180037d40  mov     rsi, dataObject
0x180037d43  call    cs:__imp_EdpGetIsManaged
0x180037d4a  nop     dword ptr [rax+rax+00h]
0x180037d4f  test    eax, eax
0x180037d51  jz      loc_180037ECC
0x180037d57  call    cs:__imp_EdpIsUIPolicyEvaluationEnabledForThread
0x180037d5e  nop     dword ptr [rax+rax+00h]
0x180037d63  test    eax, eax
0x180037d65  jz      loc_180037ECC
0x180037d6b  and     [rbp+edpContext.m_ptr], 0
0x180037d70  lea     result, [rbp+edpContext]
0x180037d74  xor     ecx, ecx
0x180037d76  call    cs:__imp_EdpGetContextForWindow
0x180037d7d  nop     dword ptr [rax+rax+00h]
0x180037d82  mov     ebx, eax
0x180037d84  test    eax, eax
0x180037d86  jns     short loc_180037DA5
0x180037d88  mov     dataObject, [rbp+18h]; callerReturnAddress
0x180037d8c  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180037d93  mov     r9d, eax; hr
0x180037d96  mov     edx, 0A2Dh; lineNumber
0x180037d9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037da0  jmp     loc_180037EE4
0x180037da5  mov     rax, [rbp+edpContext.m_ptr]
0x180037da9  test    byte ptr [rax], 1
0x180037dac  jnz     loc_180037EE2
0x180037db2  test    byte ptr [rax], 2
0x180037db5  jz      short loc_180037DC1
0x180037db7  cmp     dword ptr [rax+4], 0
0x180037dbb  ja      loc_180037EE2
0x180037dc1  and     [rbp+sourceEnterpriseId.m_ptr], 0
0x180037dc6  lea     result, [rbp+sourceEnterpriseId]; ppEnterpriseId
0x180037dca  mov     dataObject, rsi; dataObject
0x180037dcd  call    ?GetDataObjectEnterpriseId@@YAJPEAUIDataObject@@PEAPEAG@Z; GetDataObjectEnterpriseId(IDataObject *,ushort * *)
0x180037dd2  test    eax, eax
0x180037dd4  jns     short loc_180037E3A
0x180037dd6  mov     rbx, [rbp+sourceEnterpriseId.m_ptr]
0x180037dda  test    rbx, rbx
0x180037ddd  jz      short loc_180037DF9
0x180037ddf  lea     dataObject, [rbp+var_40]; this
0x180037de3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180037de8  mov     dataObject, rbx; p
0x180037deb  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180037df0  lea     dataObject, [rbp+var_40]; this
0x180037df4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180037df9  and     [rbp+sourceEnterpriseId.m_ptr], 0
0x180037dfe  lea     dataObject, [rbp+sourceEnterpriseId]
0x180037e02  call    cs:__imp_EdpGetEnterpriseIdForClipboard
0x180037e09  nop     dword ptr [rax+rax+00h]
0x180037e0e  mov     ebx, eax
0x180037e10  test    eax, eax
0x180037e12  jns     short loc_180037E3A
0x180037e14  mov     edx, 0A41h; lineNumber
0x180037e19  mov     dataObject, [rbp+18h]; callerReturnAddress
0x180037e1d  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180037e24  mov     r9d, eax; hr
0x180037e27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e2c  lea     dataObject, [rbp+sourceEnterpriseId]; this
0x180037e30  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037e35  jmp     loc_180037EE4
0x180037e3a  xorps   xmm0, xmm0
0x180037e3d  xor     eax, eax
0x180037e3f  movups  xmmword ptr [rbp+options.processIdForClipboardConsentCache], xmm0
0x180037e43  mov     qword ptr [rbp+options.sourceEnterpriseIdOption], rax
0x180037e47  movups  xmmword ptr [rbp+options.dialogOverrideBodyText], xmm0
0x180037e4b  call    cs:__imp_GetCurrentProcessId
0x180037e52  nop     dword ptr [rax+rax+00h]
0x180037e57  mov     r8, [rbp+edpContext.m_ptr]
0x180037e5b  lea     r9, _lambda_2aa60daf810bf981192e67453d2e1fb5____lambda_invoker_cdecl_
0x180037e62  mov     result, [rbp+sourceEnterpriseId.m_ptr]
0x180037e66  xor     ecx, ecx
0x180037e68  and     [rbp+edpResult], 0
0x180037e6c  mov     [rbp+options.processIdForClipboardConsentCache], eax
0x180037e6f  lea     rax, [rbp+edpResult]
0x180037e73  mov     [rsp+80h+var_50], rax
0x180037e78  lea     rax, [rbp+options]
0x180037e7c  mov     [rsp+80h+var_58], rax
0x180037e81  lea     rax, [rbp+callbackContext]
0x180037e85  mov     [rsp+80h+var_60], rax
0x180037e8a  mov     [rbp+options.overrideOption], 4
0x180037e91  mov     [rbp+callbackContext.dataObject], rsi
0x180037e95  call    cs:__imp_EdpRequestAccessForContext
0x180037e9c  nop     dword ptr [rax+rax+00h]
0x180037ea1  mov     ebx, eax
0x180037ea3  test    eax, eax
0x180037ea5  jns     short loc_180037EB1
0x180037ea7  mov     edx, 0A5Fh
0x180037eac  jmp     loc_180037E19
0x180037eb1  cmp     [rbp+edpResult], 1
0x180037eb5  lea     dataObject, [rbp+sourceEnterpriseId]; this
0x180037eb9  setz    al
0x180037ebc  mov     [rdi], al
0x180037ebe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037ec3  lea     dataObject, [rbp+edpContext]; this
0x180037ec7  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x180037ecc  xor     eax, eax
0x180037ece  mov     rbx, [rsp+80h+arg_0]
0x180037ed6  add     rsp, 80h
0x180037edd  pop     rdi
0x180037ede  pop     rsi
0x180037edf  pop     rbp
0x180037ee0  retn
0x180037ee2  xor     ebx, ebx
0x180037ee4  lea     dataObject, [rbp+edpContext]; this
0x180037ee8  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x180037eed  mov     eax, ebx
0x180037eef  jmp     short loc_180037ECE
```
