# FetchLocalAikCertOld(IX509PrivateKey *,bool,uchar * *,ulong *)

- ea: `0x180055bb8`
- end: `0x180055ec2`
- name: `?FetchLocalAikCertOld@@YAJPEAUIX509PrivateKey@@_NPEAPEAEPEAK@Z`
- size: `778`
- prototype: `__int64 __fastcall(struct IX509PrivateKey *, bool, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b3ac`

## callees

- `0x18000d810`
- `0x180011938`
- `0x1800140d0`
- `0x180016c54`
- `0x18001aec8`
- `0x18001b308`
- `0x180020cb4`
- `0x18003aabc`
- `0x180055000`
- `0x180055bb8`
- `0x180070930`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055dd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055dd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055de7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055de7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055d39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055d39`
- `ncrypt!NCryptFreeObject` at `0x180055c82`
- `ncrypt!NCryptFreeObject` at `0x180055d2a`
- `ncrypt!NCryptFreeObject` at `0x180055c82`
- `ncrypt!NCryptFreeObject` at `0x180055d2a`
- `ncrypt!NCryptGetProperty` at `0x180055da8`
- `ncrypt!NCryptGetProperty` at `0x180055e34`
- `ncrypt!NCryptGetProperty` at `0x180055da8`
- `ncrypt!NCryptGetProperty` at `0x180055e34`
- `ncrypt!NCryptOpenKey` at `0x180055d5a`
- `ncrypt!NCryptOpenKey` at `0x180055d5a`
- `ncrypt!NCryptOpenStorageProvider` at `0x180055ca5`
- `ncrypt!NCryptOpenStorageProvider` at `0x180055ca5`
- `DMCmnUtils!DmSetWindowsAIKStorageLocationOld` at `0x180055ce4`
- `DMCmnUtils!DmSetWindowsAIKStorageLocationOld` at `0x180055ce4`

## string_xrefs

- `0x180055cc0`: `NCryptOpenStorageProvider`
- `0x180055d7d`: `NCryptOpenKey(hAIK)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FetchLocalAikCertOld(struct IX509PrivateKey *a1, char a2, unsigned __int8 **a3, unsigned int *a4)
{
  HRESULT (__stdcall *get_ProviderName)(IX509PrivateKey *, BSTR *); // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  SECURITY_STATUS Property; // eax
  __int64 v14; // rcx
  const wchar_t *v15; // r8
  int v16; // eax
  __int64 v17; // rcx
  CEnrollmentLogger *Logger; // rax
  DWORD v19; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v21; // rdi
  SECURITY_STATUS v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  int dwFlags; // [rsp+20h] [rbp-50h]
  DWORD pcbResult; // [rsp+30h] [rbp-40h] BYREF
  NCRYPT_HANDLE phKey; // [rsp+38h] [rbp-38h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR pszProviderName; // [rsp+48h] [rbp-28h] BYREF
  __int64 v31; // [rsp+58h] [rbp-18h]
  _QWORD v32[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v34; // [rsp+A0h] [rbp+30h] BYREF

  v34 = 0;
  v32[0] = "FetchLocalAikCertOld";
  v32[1] = &v34;
  hObject = 0;
  phKey = 0;
  pszProviderName = 0;
  v31 = 0;
  pcbResult = 0;
  get_ProviderName = a1->lpVtbl->get_ProviderName;
  v9 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszProviderName);
  v10 = ((__int64 (__fastcall *)(struct IX509PrivateKey *, __int64))get_ProviderName)(a1, v9);
  v12 = v10;
  v34 = v10;
  if ( v10 < 0 )
  {
    if ( a2 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v11,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"key->get_ProviderName",
        (unsigned int)v10);
      v12 = v34;
    }
    goto LABEL_31;
  }
  hObject = 0;
  Property = NCryptOpenStorageProvider(&hObject, pszProviderName, 0);
  v34 = Property;
  if ( Property < 0 )
  {
    if ( !a2 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_11;
    v15 = L"NCryptOpenStorageProvider";
    goto LABEL_9;
  }
  v16 = DmSetWindowsAIKStorageLocationOld(hObject);
  v34 = v16;
  if ( v16 < 0 && a2 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0zd_EventWriteTransfer(
      v17,
      EnterpriseDiagnosticsTPMFunctionFailure,
      L"SetWindowsAIKStorageLocation",
      (unsigned int)v16);
  phKey = 0;
  Property = NCryptOpenKey(hObject, &phKey, L"Windows AIK", 0, 0);
  v34 = Property;
  if ( Property < 0 )
  {
    if ( !a2 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_11;
    v15 = L"NCryptOpenKey(hAIK)";
LABEL_9:
    McTemplateU0zd_EventWriteTransfer(v14, EnterpriseDiagnosticsTPMFunctionFailure, v15, (unsigned int)Property);
    goto LABEL_10;
  }
  Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
  v34 = Property;
  if ( Property < 0 )
  {
    if ( !a2 )
      goto LABEL_11;
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogAikCertificateNotFound(Logger, v34);
LABEL_10:
    Property = v34;
LABEL_11:
    v12 = Property;
    goto LABEL_31;
  }
  v19 = pcbResult;
  ProcessHeap = GetProcessHeap();
  v21 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v19);
  if ( v21 )
  {
    v22 = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", v21, pcbResult, &pcbResult, 0);
    v12 = v22;
    v34 = v22;
    if ( v22 >= 0 )
    {
      *a3 = v21;
      *a4 = pcbResult;
      v12 = 0;
    }
    else
    {
      if ( a2 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        McTemplateU0zd_EventWriteTransfer(
          v23,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"NCryptGetProperty(hAIK Cert)",
          (unsigned int)v22);
        v12 = v34;
      }
      MemoryFree(v21);
    }
  }
  else
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x696,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
  }
LABEL_31:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&pszProviderName);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v32, v24);
  return v12;
}

```

## disassembly

```asm
0x180055bb8  mov     [rsp-28h+arg_8], rbx
0x180055bbd  mov     [rsp-28h+arg_10], rsi
0x180055bc2  push    rbp
0x180055bc3  push    rdi
0x180055bc4  push    r12
0x180055bc6  push    r14
0x180055bc8  push    r15
0x180055bca  mov     rbp, rsp
0x180055bcd  sub     rsp, 70h
0x180055bd1  mov     r14, r9
0x180055bd4  mov     r15, r8
0x180055bd7  mov     sil, dl
0x180055bda  mov     rdi, rcx
0x180055bdd  xor     r12d, r12d
0x180055be0  mov     [rbp+arg_0], r12d
0x180055be4  lea     rax, aFetchlocalaikc_0; "FetchLocalAikCertOld"
0x180055beb  mov     [rbp+var_10], rax
0x180055bef  lea     rax, [rbp+arg_0]
0x180055bf3  mov     [rbp+var_8], rax
0x180055bf7  mov     [rbp+hObject], r12
0x180055bfb  mov     [rbp+phKey], r12
0x180055bff  mov     [rbp+pszProviderName], r12
0x180055c03  mov     [rbp+var_18], r12
0x180055c07  mov     [rbp+pcbResult], r12d
0x180055c0b  mov     rax, [rcx]
0x180055c0e  mov     rbx, [rax+0C8h]
0x180055c15  lea     rcx, [rbp+pszProviderName]
0x180055c19  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180055c1e  mov     rdx, rax
0x180055c21  mov     rcx, rdi
0x180055c24  mov     rax, rbx
0x180055c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c2c  mov     ebx, eax
0x180055c2e  mov     [rbp+arg_0], eax
0x180055c31  test    eax, eax
0x180055c33  jns     short loc_180055C69
0x180055c35  test    sil, sil
0x180055c38  jz      loc_180055E80
0x180055c3e  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180055c45  jz      loc_180055E80
0x180055c4b  mov     r9d, eax
0x180055c4e  lea     r8, aKeyGetProvider; "key->get_ProviderName"
0x180055c55  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180055c5c  call    McTemplateU0zd_EventWriteTransfer
0x180055c61  mov     ebx, [rbp+arg_0]
0x180055c64  jmp     loc_180055E80
0x180055c69  mov     rdi, [rbp+pszProviderName]
0x180055c6d  mov     rbx, [rbp+hObject]
0x180055c71  test    rbx, rbx
0x180055c74  jz      short loc_180055C97
0x180055c76  lea     rcx, [rbp+var_20]; this
0x180055c7a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180055c7f  mov     rcx, rbx; hObject
0x180055c82  call    cs:__imp_NCryptFreeObject
0x180055c88  cmp     [rbp+var_20], r12b
0x180055c8c  jnz     short loc_180055C97
0x180055c8e  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x180055c91  call    cs:__imp_SetLastError
0x180055c97  mov     [rbp+hObject], r12
0x180055c9b  xor     r8d, r8d; dwFlags
0x180055c9e  mov     rdx, rdi; pszProviderName
0x180055ca1  lea     rcx, [rbp+hObject]; phProvider
0x180055ca5  call    cs:__imp_NCryptOpenStorageProvider
0x180055cab  mov     [rbp+arg_0], eax
0x180055cae  test    eax, eax
0x180055cb0  jns     short loc_180055CE0
0x180055cb2  test    sil, sil
0x180055cb5  jz      short loc_180055CD9
0x180055cb7  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180055cbe  jz      short loc_180055CD9
0x180055cc0  lea     r8, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x180055cc7  mov     r9d, eax
0x180055cca  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180055cd1  call    McTemplateU0zd_EventWriteTransfer
0x180055cd6  mov     eax, [rbp+arg_0]
0x180055cd9  mov     ebx, eax
0x180055cdb  jmp     loc_180055E80
0x180055ce0  mov     rcx, [rbp+hObject]
0x180055ce4  call    cs:__imp_?DmSetWindowsAIKStorageLocationOld@@YAJ_K@Z; DmSetWindowsAIKStorageLocationOld(unsigned __int64)
0x180055cea  mov     [rbp+arg_0], eax
0x180055ced  test    eax, eax
0x180055cef  jns     short loc_180055D15
0x180055cf1  test    sil, sil
0x180055cf4  jz      short loc_180055D15
0x180055cf6  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180055cfd  jz      short loc_180055D15
0x180055cff  mov     r9d, eax
0x180055d02  lea     r8, aSetwindowsaiks; "SetWindowsAIKStorageLocation"
0x180055d09  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180055d10  call    McTemplateU0zd_EventWriteTransfer
0x180055d15  mov     rbx, [rbp+phKey]
0x180055d19  test    rbx, rbx
0x180055d1c  jz      short loc_180055D3F
0x180055d1e  lea     rcx, [rbp+var_20]; this
0x180055d22  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180055d27  mov     rcx, rbx; hObject
0x180055d2a  call    cs:__imp_NCryptFreeObject
0x180055d30  cmp     [rbp+var_20], r12b
0x180055d34  jnz     short loc_180055D3F
0x180055d36  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x180055d39  call    cs:__imp_SetLastError
0x180055d3f  mov     [rbp+phKey], r12
0x180055d43  mov     [rsp+70h+dwFlags], r12d; dwFlags
0x180055d48  xor     r9d, r9d; dwLegacyKeySpec
0x180055d4b  lea     r8, pszKeyName; "Windows AIK"
0x180055d52  lea     rdx, [rbp+phKey]; phKey
0x180055d56  mov     rcx, [rbp+hObject]; hProvider
0x180055d5a  call    cs:__imp_NCryptOpenKey
0x180055d60  mov     [rbp+arg_0], eax
0x180055d63  test    eax, eax
0x180055d65  jns     short loc_180055D89
0x180055d67  test    sil, sil
0x180055d6a  jz      loc_180055CD9
0x180055d70  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180055d77  jz      loc_180055CD9
0x180055d7d  lea     r8, aNcryptopenkeyH; "NCryptOpenKey(hAIK)"
0x180055d84  jmp     loc_180055CC7
0x180055d89  mov     [rsp+70h+var_48], r12d; dwFlags
0x180055d8e  lea     rax, [rbp+pcbResult]
0x180055d92  mov     qword ptr [rsp+70h+dwFlags], rax; int
0x180055d97  xor     r9d, r9d; cbOutput
0x180055d9a  xor     r8d, r8d; pbOutput
0x180055d9d  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180055da4  mov     rcx, [rbp+phKey]; hObject
0x180055da8  call    cs:__imp_NCryptGetProperty
0x180055dae  mov     [rbp+arg_0], eax
0x180055db1  test    eax, eax
0x180055db3  jns     short loc_180055DD3
0x180055db5  test    sil, sil
0x180055db8  jz      loc_180055CD9
0x180055dbe  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180055dc3  mov     edx, [rbp+arg_0]; int
0x180055dc6  mov     rcx, rax; this
0x180055dc9  call    ?LogAikCertificateNotFound@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAikCertificateNotFound(long)
0x180055dce  jmp     loc_180055CD6
0x180055dd3  mov     ebx, [rbp+pcbResult]
0x180055dd6  call    cs:__imp_GetProcessHeap
0x180055ddc  mov     r8d, ebx; dwBytes
0x180055ddf  mov     edx, 8; dwFlags
0x180055de4  mov     rcx, rax; hHeap
0x180055de7  call    cs:__imp_HeapAlloc
0x180055ded  mov     rdi, rax
0x180055df0  test    rax, rax
0x180055df3  jnz     short loc_180055E14
0x180055df5  mov     rcx, [rbp+28h]; this
0x180055df9  mov     ebx, 8007000Eh
0x180055dfe  mov     r9d, ebx; char *
0x180055e01  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180055e08  mov     edx, 696h; void *
0x180055e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055e12  jmp     short loc_180055E80
0x180055e14  mov     [rsp+70h+var_48], r12d; dwFlags
0x180055e19  lea     rax, [rbp+pcbResult]
0x180055e1d  mov     qword ptr [rsp+70h+dwFlags], rax; pcbResult
0x180055e22  mov     r9d, [rbp+pcbResult]; cbOutput
0x180055e26  mov     r8, rdi; pbOutput
0x180055e29  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180055e30  mov     rcx, [rbp+phKey]; hObject
0x180055e34  call    cs:__imp_NCryptGetProperty
0x180055e3a  mov     ebx, eax
0x180055e3c  mov     [rbp+arg_0], eax
0x180055e3f  test    eax, eax
0x180055e41  jns     short loc_180055E74
0x180055e43  test    sil, sil
0x180055e46  jz      short loc_180055E6A
0x180055e48  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180055e4f  jz      short loc_180055E6A
0x180055e51  mov     r9d, eax
0x180055e54  lea     r8, aNcryptgetprope_0; "NCryptGetProperty(hAIK Cert)"
0x180055e5b  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180055e62  call    McTemplateU0zd_EventWriteTransfer
0x180055e67  mov     ebx, [rbp+arg_0]
0x180055e6a  mov     rcx, rdi; void *
0x180055e6d  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180055e72  jmp     short loc_180055E80
0x180055e74  mov     [r15], rdi
0x180055e77  mov     eax, [rbp+pcbResult]
0x180055e7a  mov     [r14], eax
0x180055e7d  mov     ebx, r12d
0x180055e80  lea     rcx, [rbp+pszProviderName]
0x180055e84  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055e89  nop
0x180055e8a  lea     rcx, [rbp+phKey]
0x180055e8e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180055e93  nop
0x180055e94  lea     rcx, [rbp+hObject]
0x180055e98  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180055e9d  nop
0x180055e9e  lea     rcx, [rbp+var_10]; this
0x180055ea2  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180055ea7  mov     eax, ebx
0x180055ea9  lea     r11, [rsp+70h+var_s0]
0x180055eae  mov     rbx, [r11+38h]
0x180055eb2  mov     rsi, [r11+40h]
0x180055eb6  mov     rsp, r11
0x180055eb9  pop     r15
0x180055ebb  pop     r14
0x180055ebd  pop     r12
0x180055ebf  pop     rdi
0x180055ec0  pop     rbp
0x180055ec1  retn
```
