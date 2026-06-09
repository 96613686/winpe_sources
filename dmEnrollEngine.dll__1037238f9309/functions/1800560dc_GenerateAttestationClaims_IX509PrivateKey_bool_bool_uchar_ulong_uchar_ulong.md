# GenerateAttestationClaims(IX509PrivateKey *,bool,bool,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x1800560dc`
- end: `0x180056600`
- name: `?GenerateAttestationClaims@@YAJPEAUIX509PrivateKey@@_N1PEAPEAEPEAK23@Z`
- size: `1316`
- prototype: `__int64 __fastcall(struct IX509PrivateKey *, bool, bool, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b3ac`

## callees

- `0x18000d810`
- `0x180011938`
- `0x1800140d0`
- `0x180016c54`
- `0x18001b308`
- `0x180020cb4`
- `0x18003aabc`
- `0x180055000`
- `0x1800560dc`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800563d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800564d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800563d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800564d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800563ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800564e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800563ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800564e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800561c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056285`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056329`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800561c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056285`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056329`
- `ncrypt!NCryptCreateClaim` at `0x1800563a3`
- `ncrypt!NCryptCreateClaim` at `0x180056442`
- `ncrypt!NCryptCreateClaim` at `0x1800563a3`
- `ncrypt!NCryptCreateClaim` at `0x180056442`
- `ncrypt!NCryptFreeObject` at `0x1800561ba`
- `ncrypt!NCryptFreeObject` at `0x180056276`
- `ncrypt!NCryptFreeObject` at `0x18005631a`
- `ncrypt!NCryptFreeObject` at `0x1800561ba`
- `ncrypt!NCryptFreeObject` at `0x180056276`
- `ncrypt!NCryptFreeObject` at `0x18005631a`
- `ncrypt!NCryptOpenKey` at `0x1800562a1`
- `ncrypt!NCryptOpenKey` at `0x18005634a`
- `ncrypt!NCryptOpenKey` at `0x1800562a1`
- `ncrypt!NCryptOpenKey` at `0x18005634a`
- `ncrypt!NCryptExportKey` at `0x1800564ad`
- `ncrypt!NCryptExportKey` at `0x18005653f`
- `ncrypt!NCryptExportKey` at `0x1800564ad`
- `ncrypt!NCryptExportKey` at `0x18005653f`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800561dd`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800561dd`
- `DMCmnUtils!DmSetWindowsAIKStorageLocationOld` at `0x1800562d4`
- `DMCmnUtils!DmSetWindowsAIKStorageLocationOld` at `0x1800562d4`

## string_xrefs

- `0x1800561f8`: `NCryptOpenStorageProvider`
- `0x1800562c4`: `NCryptOpenKey(dmKey)`
- `0x1800563c6`: `NCryptCreateClaim(size)`
- `0x18005636d`: `NCryptOpenKey(hAIK)`
- `0x18005645f`: `NCryptCreateClaim`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GenerateAttestationClaims(
        struct IX509PrivateKey *a1,
        unsigned __int8 a2,
        char a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  int v9; // r15d
  HRESULT (__stdcall *get_ProviderName)(IX509PrivateKey *, BSTR *); // rbx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  SECURITY_STATUS Claim; // eax
  __int64 v17; // rcx
  const wchar_t *v18; // r8
  HRESULT (__stdcall *get_ContainerName)(IX509PrivateKey *, BSTR *); // rbx
  __int64 v20; // rax
  const WCHAR *v21; // r14
  NCRYPT_HANDLE v22; // rsi
  int v23; // eax
  __int64 v24; // rcx
  HANDLE ProcessHeap; // rax
  void *v26; // rsi
  SECURITY_STATUS v27; // eax
  __int64 v28; // rcx
  const wchar_t *v29; // r8
  DWORD v30; // ebx
  HANDLE v31; // rax
  BYTE *v32; // r14
  SECURITY_STATUS v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rdx
  int dwFlags; // [rsp+20h] [rbp-71h]
  DWORD pcbResult; // [rsp+40h] [rbp-51h] BYREF
  NCRYPT_HANDLE hKey; // [rsp+48h] [rbp-49h] BYREF
  _BYTE v40[4]; // [rsp+50h] [rbp-41h] BYREF
  DWORD dwErrCode; // [rsp+54h] [rbp-3Dh]
  NCRYPT_HANDLE hObject; // [rsp+58h] [rbp-39h] BYREF
  NCRYPT_HANDLE phKey; // [rsp+60h] [rbp-31h] BYREF
  LPCWSTR pszProviderName; // [rsp+68h] [rbp-29h] BYREF
  LPCWSTR pszKeyName; // [rsp+70h] [rbp-21h] BYREF
  _QWORD v46[11]; // [rsp+78h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]
  int v48; // [rsp+E8h] [rbp+57h] BYREF

  v9 = a2;
  v48 = 0;
  v46[0] = "GenerateAttestationClaims";
  v46[1] = &v48;
  hObject = 0;
  phKey = 0;
  hKey = 0;
  pszKeyName = 0;
  pszProviderName = 0;
  v46[2] = 0;
  v46[3] = 0;
  pcbResult = 0;
  get_ProviderName = a1->lpVtbl->get_ProviderName;
  v12 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszProviderName);
  v13 = ((__int64 (__fastcall *)(struct IX509PrivateKey *, __int64))get_ProviderName)(a1, v12);
  v15 = v13;
  v48 = v13;
  if ( v13 < 0 )
  {
    if ( a3 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v14,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"key->get_ProviderName",
        (unsigned int)v13);
      v15 = v48;
    }
    goto LABEL_54;
  }
  hObject = 0;
  Claim = NCryptOpenStorageProvider(&hObject, pszProviderName, 0);
  v48 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v18 = L"NCryptOpenStorageProvider";
LABEL_9:
    McTemplateU0zd_EventWriteTransfer(v17, EnterpriseDiagnosticsTPMFunctionFailure, v18, (unsigned int)Claim);
    Claim = v48;
LABEL_10:
    v15 = Claim;
    goto LABEL_54;
  }
  get_ContainerName = a1->lpVtbl->get_ContainerName;
  v20 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszKeyName);
  Claim = ((__int64 (__fastcall *)(struct IX509PrivateKey *, __int64))get_ContainerName)(a1, v20);
  v48 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v18 = L"key->get_ContainerName";
    goto LABEL_9;
  }
  v21 = pszKeyName;
  v22 = phKey;
  if ( phKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v40);
    NCryptFreeObject(v22);
    if ( !v40[0] )
      SetLastError(dwErrCode);
  }
  phKey = 0;
  Claim = NCryptOpenKey(hObject, &phKey, v21, 0, (32 * v9) | 0x40);
  v48 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v18 = L"NCryptOpenKey(dmKey)";
    goto LABEL_9;
  }
  v23 = DmSetWindowsAIKStorageLocationOld(hObject);
  v48 = v23;
  if ( v23 < 0 && a3 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0zd_EventWriteTransfer(
      v24,
      EnterpriseDiagnosticsTPMFunctionFailure,
      L"SetWindowsAIKStorageLocation",
      (unsigned int)v23);
  hKey = 0;
  Claim = NCryptOpenKey(hObject, &hKey, L"Windows AIK", 0, 0);
  v48 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v18 = L"NCryptOpenKey(hAIK)";
    goto LABEL_9;
  }
  Claim = NCryptCreateClaim(phKey, hKey, 2);
  v48 = Claim;
  if ( Claim < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_10;
    v18 = L"NCryptCreateClaim(size)";
    goto LABEL_9;
  }
  ProcessHeap = GetProcessHeap();
  v26 = HeapAlloc(ProcessHeap, 8u, 0);
  if ( !v26 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)0x8007000ELL,
      0);
    goto LABEL_54;
  }
  v27 = NCryptCreateClaim(phKey, hKey, 2);
  v15 = v27;
  v48 = v27;
  if ( v27 < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_41;
    v29 = L"NCryptCreateClaim";
    goto LABEL_40;
  }
  v27 = NCryptExportKey(hKey, 0, L"RSAPUBLICBLOB", 0, 0, 0, &pcbResult, 0);
  v15 = v27;
  v48 = v27;
  if ( v27 < 0 )
  {
    if ( !a3 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_41;
    v29 = L"NCryptExportKey(hAIK size)";
LABEL_40:
    McTemplateU0zd_EventWriteTransfer(v28, EnterpriseDiagnosticsTPMFunctionFailure, v29, (unsigned int)v27);
    v15 = v48;
LABEL_41:
    MemoryFree(v26);
    goto LABEL_54;
  }
  v30 = pcbResult;
  v31 = GetProcessHeap();
  v32 = (BYTE *)HeapAlloc(v31, 8u, v30);
  if ( !v32 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    goto LABEL_41;
  }
  v33 = NCryptExportKey(hKey, 0, L"RSAPUBLICBLOB", 0, v32, pcbResult, &pcbResult, 0);
  v15 = v33;
  v48 = v33;
  if ( v33 >= 0 )
  {
    *a4 = (unsigned __int8 *)v26;
    *a5 = 0;
    *a6 = v32;
    *a7 = pcbResult;
    v15 = 0;
  }
  else
  {
    if ( a3 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v34,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"NCryptExportKey(hAIK)",
        (unsigned int)v33);
      v15 = v48;
    }
    MemoryFree(v26);
    MemoryFree(v32);
  }
LABEL_54:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&pszProviderName);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&pszKeyName);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v46, v35);
  return v15;
}

```

## disassembly

```asm
0x1800560dc  mov     [rsp-8+arg_10], rbx
0x1800560e1  push    rbp
0x1800560e2  push    rsi
0x1800560e3  push    rdi
0x1800560e4  push    r12
0x1800560e6  push    r13
0x1800560e8  push    r14
0x1800560ea  push    r15
0x1800560ec  lea     rbp, [rsp-0Fh]
0x1800560f1  sub     rsp, 0A0h
0x1800560f8  mov     r12, r9
0x1800560fb  mov     dil, r8b
0x1800560fe  movzx   r15d, dl
0x180056102  mov     r14, rcx
0x180056105  xor     r13d, r13d
0x180056108  mov     [rbp+3Fh+arg_8], r13d
0x18005610c  lea     rax, aGenerateattest; "GenerateAttestationClaims"
0x180056113  mov     [rbp+3Fh+var_58], rax
0x180056117  lea     rax, [rbp+3Fh+arg_8]
0x18005611b  mov     [rbp+3Fh+var_50], rax
0x18005611f  mov     [rbp+3Fh+hObject], r13
0x180056123  mov     [rbp+3Fh+phKey], r13
0x180056127  mov     [rbp+3Fh+hKey], r13
0x18005612b  mov     [rbp+3Fh+pszKeyName], r13
0x18005612f  mov     [rbp+3Fh+pszProviderName], r13
0x180056133  mov     [rbp+3Fh+var_48], r13
0x180056137  mov     [rbp+3Fh+var_40], r13
0x18005613b  mov     [rbp+3Fh+var_90], r13d
0x18005613f  mov     dword ptr [rbp+3Fh+dwBytes], r13d
0x180056143  mov     rax, [rcx]
0x180056146  mov     rbx, [rax+0C8h]
0x18005614d  lea     rcx, [rbp+3Fh+pszProviderName]
0x180056151  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180056156  mov     rdx, rax
0x180056159  mov     rcx, r14
0x18005615c  mov     rax, rbx
0x18005615f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056164  mov     ebx, eax
0x180056166  mov     [rbp+3Fh+arg_8], eax
0x180056169  test    eax, eax
0x18005616b  jns     short loc_1800561A1
0x18005616d  test    dil, dil
0x180056170  jz      loc_1800565A8
0x180056176  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18005617d  jz      loc_1800565A8
0x180056183  mov     r9d, eax
0x180056186  lea     r8, aKeyGetProvider; "key->get_ProviderName"
0x18005618d  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180056194  call    McTemplateU0zd_EventWriteTransfer
0x180056199  mov     ebx, [rbp+3Fh+arg_8]
0x18005619c  jmp     loc_1800565A8
0x1800561a1  mov     rsi, [rbp+3Fh+pszProviderName]
0x1800561a5  mov     rbx, [rbp+3Fh+hObject]
0x1800561a9  test    rbx, rbx
0x1800561ac  jz      short loc_1800561CF
0x1800561ae  lea     rcx, [rbp+3Fh+var_80]; this
0x1800561b2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800561b7  mov     rcx, rbx; hObject
0x1800561ba  call    cs:__imp_NCryptFreeObject
0x1800561c0  cmp     [rbp+3Fh+var_80], r13b
0x1800561c4  jnz     short loc_1800561CF
0x1800561c6  mov     ecx, [rbp+3Fh+dwErrCode]; dwErrCode
0x1800561c9  call    cs:__imp_SetLastError
0x1800561cf  mov     [rbp+3Fh+hObject], r13
0x1800561d3  xor     r8d, r8d; dwFlags
0x1800561d6  mov     rdx, rsi; pszProviderName
0x1800561d9  lea     rcx, [rbp+3Fh+hObject]; phProvider
0x1800561dd  call    cs:__imp_NCryptOpenStorageProvider
0x1800561e3  mov     [rbp+3Fh+arg_8], eax
0x1800561e6  test    eax, eax
0x1800561e8  jns     short loc_180056218
0x1800561ea  test    dil, dil
0x1800561ed  jz      short loc_180056211
0x1800561ef  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800561f6  jz      short loc_180056211
0x1800561f8  lea     r8, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x1800561ff  mov     r9d, eax
0x180056202  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180056209  call    McTemplateU0zd_EventWriteTransfer
0x18005620e  mov     eax, [rbp+3Fh+arg_8]
0x180056211  mov     ebx, eax
0x180056213  jmp     loc_1800565A8
0x180056218  mov     rax, [r14]
0x18005621b  mov     rbx, [rax+78h]
0x18005621f  lea     rcx, [rbp+3Fh+pszKeyName]
0x180056223  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180056228  mov     rdx, rax
0x18005622b  mov     rcx, r14
0x18005622e  mov     rax, rbx
0x180056231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056236  mov     [rbp+3Fh+arg_8], eax
0x180056239  test    eax, eax
0x18005623b  jns     short loc_180056254
0x18005623d  test    dil, dil
0x180056240  jz      short loc_180056211
0x180056242  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180056249  jz      short loc_180056211
0x18005624b  lea     r8, aKeyGetContaine; "key->get_ContainerName"
0x180056252  jmp     short loc_1800561FF
0x180056254  mov     ebx, r15d
0x180056257  shl     ebx, 5
0x18005625a  or      ebx, 40h
0x18005625d  mov     r14, [rbp+3Fh+pszKeyName]
0x180056261  mov     rsi, [rbp+3Fh+phKey]
0x180056265  test    rsi, rsi
0x180056268  jz      short loc_18005628B
0x18005626a  lea     rcx, [rbp+3Fh+var_80]; this
0x18005626e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180056273  mov     rcx, rsi; hObject
0x180056276  call    cs:__imp_NCryptFreeObject
0x18005627c  cmp     [rbp+3Fh+var_80], r13b
0x180056280  jnz     short loc_18005628B
0x180056282  mov     ecx, [rbp+3Fh+dwErrCode]; dwErrCode
0x180056285  call    cs:__imp_SetLastError
0x18005628b  mov     [rbp+3Fh+phKey], r13
0x18005628f  mov     [rsp+0D0h+dwFlags], ebx; dwFlags
0x180056293  xor     r9d, r9d; dwLegacyKeySpec
0x180056296  mov     r8, r14; pszKeyName
0x180056299  lea     rdx, [rbp+3Fh+phKey]; phKey
0x18005629d  mov     rcx, [rbp+3Fh+hObject]; hProvider
0x1800562a1  call    cs:__imp_NCryptOpenKey
0x1800562a7  mov     [rbp+3Fh+arg_8], eax
0x1800562aa  test    eax, eax
0x1800562ac  jns     short loc_1800562D0
0x1800562ae  test    dil, dil
0x1800562b1  jz      loc_180056211
0x1800562b7  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800562be  jz      loc_180056211
0x1800562c4  lea     r8, aNcryptopenkeyD; "NCryptOpenKey(dmKey)"
0x1800562cb  jmp     loc_1800561FF
0x1800562d0  mov     rcx, [rbp+3Fh+hObject]
0x1800562d4  call    cs:__imp_?DmSetWindowsAIKStorageLocationOld@@YAJ_K@Z; DmSetWindowsAIKStorageLocationOld(unsigned __int64)
0x1800562da  mov     [rbp+3Fh+arg_8], eax
0x1800562dd  test    eax, eax
0x1800562df  jns     short loc_180056305
0x1800562e1  test    dil, dil
0x1800562e4  jz      short loc_180056305
0x1800562e6  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800562ed  jz      short loc_180056305
0x1800562ef  mov     r9d, eax
0x1800562f2  lea     r8, aSetwindowsaiks; "SetWindowsAIKStorageLocation"
0x1800562f9  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180056300  call    McTemplateU0zd_EventWriteTransfer
0x180056305  mov     rbx, [rbp+3Fh+hKey]
0x180056309  test    rbx, rbx
0x18005630c  jz      short loc_18005632F
0x18005630e  lea     rcx, [rbp+3Fh+var_80]; this
0x180056312  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180056317  mov     rcx, rbx; hObject
0x18005631a  call    cs:__imp_NCryptFreeObject
0x180056320  cmp     [rbp+3Fh+var_80], r13b
0x180056324  jnz     short loc_18005632F
0x180056326  mov     ecx, [rbp+3Fh+dwErrCode]; dwErrCode
0x180056329  call    cs:__imp_SetLastError
0x18005632f  mov     [rbp+3Fh+hKey], r13
0x180056333  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x180056338  xor     r9d, r9d; dwLegacyKeySpec
0x18005633b  lea     r8, pszKeyName; "Windows AIK"
0x180056342  lea     rdx, [rbp+3Fh+hKey]; phKey
0x180056346  mov     rcx, [rbp+3Fh+hObject]; hProvider
0x18005634a  call    cs:__imp_NCryptOpenKey
0x180056350  mov     [rbp+3Fh+arg_8], eax
0x180056353  test    eax, eax
0x180056355  jns     short loc_180056379
0x180056357  test    dil, dil
0x18005635a  jz      loc_180056211
0x180056360  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180056367  jz      loc_180056211
0x18005636d  lea     r8, aNcryptopenkeyH; "NCryptOpenKey(hAIK)"
0x180056374  jmp     loc_1800561FF
0x180056379  mov     [rsp+0D0h+var_98], r13d
0x18005637e  lea     rax, [rbp+3Fh+dwBytes]
0x180056382  mov     [rsp+0D0h+pcbResult], rax
0x180056387  mov     [rsp+0D0h+cbOutput], r13d
0x18005638c  mov     qword ptr [rsp+0D0h+dwFlags], r13; int
0x180056391  xor     r9d, r9d
0x180056394  lea     r14d, [r9+2]
0x180056398  mov     r8d, r14d
0x18005639b  mov     rdx, [rbp+3Fh+hKey]
0x18005639f  mov     rcx, [rbp+3Fh+phKey]
0x1800563a3  call    cs:__imp_NCryptCreateClaim
0x1800563a9  mov     [rbp+3Fh+arg_8], eax
0x1800563ac  test    eax, eax
0x1800563ae  jns     short loc_1800563D2
0x1800563b0  test    dil, dil
0x1800563b3  jz      loc_180056211
0x1800563b9  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800563c0  jz      loc_180056211
0x1800563c6  lea     r8, aNcryptcreatecl_1; "NCryptCreateClaim(size)"
0x1800563cd  jmp     loc_1800561FF
0x1800563d2  mov     ebx, dword ptr [rbp+3Fh+dwBytes]
0x1800563d5  call    cs:__imp_GetProcessHeap
0x1800563db  mov     r8d, ebx; dwBytes
0x1800563de  mov     r15d, 8
0x1800563e4  mov     edx, r15d; dwFlags
0x1800563e7  mov     rcx, rax; hHeap
0x1800563ea  call    cs:__imp_HeapAlloc
0x1800563f0  mov     rsi, rax
0x1800563f3  test    rax, rax
0x1800563f6  jnz     short loc_18005641A
0x1800563f8  mov     rcx, [rbp+47h]; this
0x1800563fc  mov     ebx, 8007000Eh
0x180056401  mov     r9d, ebx; char *
0x180056404  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18005640b  mov     edx, 5BEh; void *
0x180056410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056415  jmp     loc_1800565A8
0x18005641a  mov     [rsp+0D0h+var_98], r13d
0x18005641f  lea     rax, [rbp+3Fh+dwBytes]
0x180056423  mov     [rsp+0D0h+pcbResult], rax
0x180056428  mov     eax, dword ptr [rbp+3Fh+dwBytes]
0x18005642b  mov     [rsp+0D0h+cbOutput], eax
0x18005642f  mov     qword ptr [rsp+0D0h+dwFlags], rsi
0x180056434  xor     r9d, r9d
0x180056437  mov     r8d, r14d
0x18005643a  mov     rdx, [rbp+3Fh+hKey]
0x18005643e  mov     rcx, [rbp+3Fh+phKey]
0x180056442  call    cs:__imp_NCryptCreateClaim
0x180056448  mov     ebx, eax
0x18005644a  mov     [rbp+3Fh+arg_8], eax
0x18005644d  test    eax, eax
0x18005644f  jns     short loc_180056485
0x180056451  test    dil, dil
0x180056454  jz      short loc_180056478
0x180056456  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18005645d  jz      short loc_180056478
0x18005645f  lea     r8, aNcryptcreatecl_0; "NCryptCreateClaim"
0x180056466  mov     r9d, eax
0x180056469  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180056470  call    McTemplateU0zd_EventWriteTransfer
0x180056475  mov     ebx, [rbp+3Fh+arg_8]
0x180056478  mov     rcx, rsi; void *
0x18005647b  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180056480  jmp     loc_1800565A8
0x180056485  mov     [rsp+0D0h+var_98], r13d; dwFlags
0x18005648a  lea     rax, [rbp+3Fh+var_90]
0x18005648e  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180056493  mov     [rsp+0D0h+cbOutput], r13d; cbOutput
0x180056498  mov     qword ptr [rsp+0D0h+dwFlags], r13; int
0x18005649d  xor     r9d, r9d; pParameterList
0x1800564a0  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x1800564a7  xor     edx, edx; hExportKey
0x1800564a9  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800564ad  call    cs:__imp_NCryptExportKey
0x1800564b3  mov     ebx, eax
0x1800564b5  mov     [rbp+3Fh+arg_8], eax
0x1800564b8  test    eax, eax
0x1800564ba  jns     short loc_1800564D3
0x1800564bc  test    dil, dil
0x1800564bf  jz      short loc_180056478
0x1800564c1  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800564c8  jz      short loc_180056478
0x1800564ca  lea     r8, aNcryptexportke_0; "NCryptExportKey(hAIK size)"
0x1800564d1  jmp     short loc_180056466
0x1800564d3  mov     ebx, [rbp+3Fh+var_90]
0x1800564d6  call    cs:__imp_GetProcessHeap
0x1800564dc  mov     r8d, ebx; dwBytes
0x1800564df  mov     edx, r15d; dwFlags
0x1800564e2  mov     rcx, rax; hHeap
0x1800564e5  call    cs:__imp_HeapAlloc
0x1800564eb  mov     r14, rax
0x1800564ee  test    rax, rax
0x1800564f1  jnz     short loc_180056515
0x1800564f3  mov     rcx, [rbp+47h]; this
0x1800564f7  mov     ebx, 8007000Eh
0x1800564fc  mov     r9d, ebx; char *
0x1800564ff  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180056506  mov     edx, 5E4h; void *
0x18005650b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056510  jmp     loc_180056478
0x180056515  mov     [rsp+0D0h+var_98], r13d; dwFlags
0x18005651a  lea     rax, [rbp+3Fh+var_90]
0x18005651e  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180056523  mov     eax, [rbp+3Fh+var_90]
0x180056526  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x18005652a  mov     qword ptr [rsp+0D0h+dwFlags], r14; pbOutput
0x18005652f  xor     r9d, r9d; pParameterList
0x180056532  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180056539  xor     edx, edx; hExportKey
0x18005653b  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18005653f  call    cs:__imp_NCryptExportKey
0x180056545  mov     ebx, eax
0x180056547  mov     [rbp+3Fh+arg_8], eax
0x18005654a  test    eax, eax
0x18005654c  jns     short loc_180056588
0x18005654e  test    dil, dil
0x180056551  jz      short loc_180056575
0x180056553  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18005655a  jz      short loc_180056575
0x18005655c  mov     r9d, eax
0x18005655f  lea     r8, aNcryptexportke_1; "NCryptExportKey(hAIK)"
0x180056566  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x18005656d  call    McTemplateU0zd_EventWriteTransfer
0x180056572  mov     ebx, [rbp+3Fh+arg_8]
0x180056575  mov     rcx, rsi; void *
0x180056578  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18005657d  nop
0x18005657e  mov     rcx, r14; void *
0x180056581  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180056586  jmp     short loc_1800565A8
  ... truncated ...
```
