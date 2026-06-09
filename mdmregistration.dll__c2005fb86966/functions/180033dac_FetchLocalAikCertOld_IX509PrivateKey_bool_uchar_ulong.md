# FetchLocalAikCertOld(IX509PrivateKey *,bool,uchar * *,ulong *)

- ea: `0x180033dac`
- end: `0x18003417d`
- name: `?FetchLocalAikCertOld@@YAJPEAUIX509PrivateKey@@_NPEAPEAEPEAK@Z`
- size: `977`
- prototype: `__int64 __fastcall(struct IX509PrivateKey *, bool, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x18000b0f4`
- `0x180012fcc`
- `0x1800141b0`
- `0x180033dac`
- `0x180041410`
- `0x1800414fc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034051`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034051`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800340fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800340fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003403a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800340e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003403a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800340e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033e76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033f7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033e76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033f7d`
- `DMCmnUtils!DmSetWindowsAIKStorageLocationOld` at `0x180033f1e`
- `DMCmnUtils!DmSetWindowsAIKStorageLocationOld` at `0x180033f1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180033ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003411e`
- `OLEAUT32!__imp_SysFreeString` at `0x180033ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003411e`
- `ncrypt!NCryptGetProperty` at `0x180034004`
- `ncrypt!NCryptGetProperty` at `0x1800340aa`
- `ncrypt!NCryptGetProperty` at `0x180034004`
- `ncrypt!NCryptGetProperty` at `0x1800340aa`
- `ncrypt!NCryptFreeObject` at `0x180033e68`
- `ncrypt!NCryptFreeObject` at `0x180033eef`
- `ncrypt!NCryptFreeObject` at `0x180033f09`
- `ncrypt!NCryptFreeObject` at `0x180033f6f`
- `ncrypt!NCryptFreeObject` at `0x180034134`
- `ncrypt!NCryptFreeObject` at `0x18003414a`
- `ncrypt!NCryptFreeObject` at `0x180033e68`
- `ncrypt!NCryptFreeObject` at `0x180033eef`
- `ncrypt!NCryptFreeObject` at `0x180033f09`
- `ncrypt!NCryptFreeObject` at `0x180033f6f`
- `ncrypt!NCryptFreeObject` at `0x180034134`
- `ncrypt!NCryptFreeObject` at `0x18003414a`
- `ncrypt!NCryptOpenKey` at `0x180033fab`
- `ncrypt!NCryptOpenKey` at `0x180033fab`
- `ncrypt!NCryptOpenStorageProvider` at `0x180033e94`
- `ncrypt!NCryptOpenStorageProvider` at `0x180033e94`

## string_xrefs

- `0x180033eb7`: `NCryptOpenStorageProvider`
- `0x180033fd6`: `NCryptOpenKey(hAIK)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FetchLocalAikCertOld(struct IX509PrivateKey *a1, char a2, unsigned __int8 **a3, unsigned int *a4)
{
  SECURITY_STATUS v7; // eax
  __int64 v8; // rcx
  SECURITY_STATUS Property; // ebx
  const wchar_t *v10; // r8
  int v11; // eax
  __int64 v12; // rcx
  CEnrollmentLogger *Logger; // rax
  DWORD v14; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v16; // rsi
  SECURITY_STATUS v17; // eax
  __int64 v18; // rcx
  HANDLE v19; // rax
  int dwFlags; // [rsp+20h] [rbp-50h]
  DWORD pcbResult; // [rsp+30h] [rbp-40h] BYREF
  NCRYPT_HANDLE phKey; // [rsp+38h] [rbp-38h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR pszProviderName[2]; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v28; // [rsp+A0h] [rbp+30h] BYREF

  v28 = 0;
  v26[0] = "FetchLocalAikCertOld";
  v26[1] = &v28;
  hObject = 0;
  phKey = 0;
  pszProviderName[1] = 0;
  pcbResult = 0;
  pszProviderName[0] = 0;
  v7 = ((__int64 (__fastcall *)(struct IX509PrivateKey *, LPCWSTR *))a1->lpVtbl->get_ProviderName)(a1, pszProviderName);
  Property = v7;
  v28 = v7;
  if ( v7 < 0 )
  {
    if ( !a2 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_11;
    v10 = L"key->get_ProviderName";
    goto LABEL_9;
  }
  hObject = 0;
  v7 = NCryptOpenStorageProvider(&hObject, pszProviderName[0], 0);
  Property = v7;
  v28 = v7;
  if ( v7 < 0 )
  {
    if ( !a2 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_11;
    v10 = L"NCryptOpenStorageProvider";
    goto LABEL_9;
  }
  v11 = DmSetWindowsAIKStorageLocationOld(hObject);
  v28 = v11;
  if ( v11 < 0 && a2 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0zd_EventWriteTransfer(
      v12,
      EnterpriseDiagnosticsTPMFunctionFailure,
      L"SetWindowsAIKStorageLocation",
      (unsigned int)v11);
  phKey = 0;
  v7 = NCryptOpenKey(hObject, &phKey, L"Windows AIK", 0, 0);
  Property = v7;
  v28 = v7;
  if ( v7 < 0 )
  {
    if ( !a2 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_11;
    v10 = L"NCryptOpenKey(hAIK)";
LABEL_9:
    McTemplateU0zd_EventWriteTransfer(v8, EnterpriseDiagnosticsTPMFunctionFailure, v10, (unsigned int)v7);
    goto LABEL_10;
  }
  Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
  v28 = Property;
  if ( Property < 0 )
  {
    if ( !a2 )
      goto LABEL_11;
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogAikCertificateNotFound(Logger, v28);
LABEL_10:
    Property = v28;
LABEL_11:
    if ( pszProviderName[0] )
      SysFreeString((BSTR)pszProviderName[0]);
    if ( phKey )
      NCryptFreeObject(phKey);
    if ( hObject )
      NCryptFreeObject(hObject);
    goto LABEL_42;
  }
  v14 = pcbResult;
  ProcessHeap = GetProcessHeap();
  v16 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v14);
  if ( !v16 )
  {
    Property = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x696,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    goto LABEL_11;
  }
  v17 = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", v16, pcbResult, &pcbResult, 0);
  Property = v17;
  v28 = v17;
  if ( v17 < 0 )
  {
    if ( a2 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v18,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"NCryptGetProperty(hAIK Cert)",
        (unsigned int)v17);
      Property = v28;
    }
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v16);
    goto LABEL_11;
  }
  *a3 = v16;
  *a4 = pcbResult;
  if ( pszProviderName[0] )
    SysFreeString((BSTR)pszProviderName[0]);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( hObject )
    NCryptFreeObject(hObject);
  Property = 0;
LABEL_42:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v26);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180033dac  mov     [rsp-28h+arg_8], rbx
0x180033db1  mov     [rsp-28h+arg_10], rsi
0x180033db6  push    rbp
0x180033db7  push    rdi
0x180033db8  push    r12
0x180033dba  push    r14
0x180033dbc  push    r15
0x180033dbe  mov     rbp, rsp
0x180033dc1  sub     rsp, 70h
0x180033dc5  mov     r15, r9
0x180033dc8  mov     r12, r8
0x180033dcb  mov     dil, dl
0x180033dce  mov     [rbp+arg_0], 0
0x180033dd5  lea     rax, aFetchlocalaikc_0; "FetchLocalAikCertOld"
0x180033ddc  mov     [rbp+var_18], rax
0x180033de0  lea     rax, [rbp+arg_0]
0x180033de4  mov     [rbp+var_10], rax
0x180033de8  mov     [rbp+hObject], 0
0x180033df0  mov     [rbp+phKey], 0
0x180033df8  mov     [rbp+var_20], 0
0x180033e00  mov     [rbp+pcbResult], 0
0x180033e07  mov     [rbp+pszProviderName], 0
0x180033e0f  mov     rax, [rcx]
0x180033e12  lea     rdx, [rbp+pszProviderName]
0x180033e16  mov     rax, [rax+0C8h]
0x180033e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e22  mov     ebx, eax
0x180033e24  mov     [rbp+arg_0], eax
0x180033e27  test    eax, eax
0x180033e29  jns     short loc_180033E4A
0x180033e2b  test    dil, dil
0x180033e2e  jz      loc_180033ED0
0x180033e34  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180033e3b  jz      loc_180033ED0
0x180033e41  lea     r8, aKeyGetProvider; "key->get_ProviderName"
0x180033e48  jmp     short loc_180033EBE
0x180033e4a  mov     r14, [rbp+pszProviderName]
0x180033e4e  mov     rsi, [rbp+hObject]
0x180033e52  test    rsi, rsi
0x180033e55  jz      short loc_180033E82
0x180033e57  call    cs:__imp_GetLastError
0x180033e5e  nop     dword ptr [rax+rax+00h]
0x180033e63  mov     ebx, eax
0x180033e65  mov     rcx, rsi; hObject
0x180033e68  call    cs:__imp_NCryptFreeObject
0x180033e6f  nop     dword ptr [rax+rax+00h]
0x180033e74  mov     ecx, ebx; dwErrCode
0x180033e76  call    cs:__imp_SetLastError
0x180033e7d  nop     dword ptr [rax+rax+00h]
0x180033e82  mov     [rbp+hObject], 0
0x180033e8a  xor     r8d, r8d; dwFlags
0x180033e8d  mov     rdx, r14; pszProviderName
0x180033e90  lea     rcx, [rbp+hObject]; phProvider
0x180033e94  call    cs:__imp_NCryptOpenStorageProvider
0x180033e9b  nop     dword ptr [rax+rax+00h]
0x180033ea0  mov     ebx, eax
0x180033ea2  mov     [rbp+arg_0], eax
0x180033ea5  test    eax, eax
0x180033ea7  jns     short loc_180033F1A
0x180033ea9  test    dil, dil
0x180033eac  jz      short loc_180033ED0
0x180033eae  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180033eb5  jz      short loc_180033ED0
0x180033eb7  lea     r8, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x180033ebe  mov     r9d, eax
0x180033ec1  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180033ec8  call    McTemplateU0zd_EventWriteTransfer
0x180033ecd  mov     ebx, [rbp+arg_0]
0x180033ed0  mov     rcx, [rbp+pszProviderName]; bstrString
0x180033ed4  test    rcx, rcx
0x180033ed7  jz      short loc_180033EE6
0x180033ed9  call    cs:__imp_SysFreeString
0x180033ee0  nop     dword ptr [rax+rax+00h]
0x180033ee5  nop
0x180033ee6  mov     rcx, [rbp+phKey]; hObject
0x180033eea  test    rcx, rcx
0x180033eed  jz      short loc_180033EFC
0x180033eef  call    cs:__imp_NCryptFreeObject
0x180033ef6  nop     dword ptr [rax+rax+00h]
0x180033efb  nop
0x180033efc  mov     rcx, [rbp+hObject]; hObject
0x180033f00  test    rcx, rcx
0x180033f03  jz      loc_180034158
0x180033f09  call    cs:__imp_NCryptFreeObject
0x180033f10  nop     dword ptr [rax+rax+00h]
0x180033f15  jmp     loc_180034158
0x180033f1a  mov     rcx, [rbp+hObject]
0x180033f1e  call    cs:__imp_?DmSetWindowsAIKStorageLocationOld@@YAJ_K@Z; DmSetWindowsAIKStorageLocationOld(unsigned __int64)
0x180033f25  nop     dword ptr [rax+rax+00h]
0x180033f2a  mov     [rbp+arg_0], eax
0x180033f2d  test    eax, eax
0x180033f2f  jns     short loc_180033F55
0x180033f31  test    dil, dil
0x180033f34  jz      short loc_180033F55
0x180033f36  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180033f3d  jz      short loc_180033F55
0x180033f3f  mov     r9d, eax
0x180033f42  lea     r8, aSetwindowsaiks; "SetWindowsAIKStorageLocation"
0x180033f49  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180033f50  call    McTemplateU0zd_EventWriteTransfer
0x180033f55  mov     rsi, [rbp+phKey]
0x180033f59  test    rsi, rsi
0x180033f5c  jz      short loc_180033F89
0x180033f5e  call    cs:__imp_GetLastError
0x180033f65  nop     dword ptr [rax+rax+00h]
0x180033f6a  mov     ebx, eax
0x180033f6c  mov     rcx, rsi; hObject
0x180033f6f  call    cs:__imp_NCryptFreeObject
0x180033f76  nop     dword ptr [rax+rax+00h]
0x180033f7b  mov     ecx, ebx; dwErrCode
0x180033f7d  call    cs:__imp_SetLastError
0x180033f84  nop     dword ptr [rax+rax+00h]
0x180033f89  mov     [rbp+phKey], 0
0x180033f91  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180033f99  xor     r9d, r9d; dwLegacyKeySpec
0x180033f9c  lea     r8, pszKeyName; "Windows AIK"
0x180033fa3  lea     rdx, [rbp+phKey]; phKey
0x180033fa7  mov     rcx, [rbp+hObject]; hProvider
0x180033fab  call    cs:__imp_NCryptOpenKey
0x180033fb2  nop     dword ptr [rax+rax+00h]
0x180033fb7  mov     ebx, eax
0x180033fb9  mov     [rbp+arg_0], eax
0x180033fbc  test    eax, eax
0x180033fbe  jns     short loc_180033FE2
0x180033fc0  test    dil, dil
0x180033fc3  jz      loc_180033ED0
0x180033fc9  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180033fd0  jz      loc_180033ED0
0x180033fd6  lea     r8, aNcryptopenkeyH; "NCryptOpenKey(hAIK)"
0x180033fdd  jmp     loc_180033EBE
0x180033fe2  mov     [rsp+70h+var_48], 0; dwFlags
0x180033fea  lea     rax, [rbp+pcbResult]
0x180033fee  mov     qword ptr [rsp+70h+dwFlags], rax; int
0x180033ff3  xor     r9d, r9d; cbOutput
0x180033ff6  xor     r8d, r8d; pbOutput
0x180033ff9  lea     rdx, pszProperty; "SmartCardKeyCertificate"
0x180034000  mov     rcx, [rbp+phKey]; hObject
0x180034004  call    cs:__imp_NCryptGetProperty
0x18003400b  nop     dword ptr [rax+rax+00h]
0x180034010  mov     ebx, eax
0x180034012  mov     [rbp+arg_0], eax
0x180034015  test    eax, eax
0x180034017  jns     short loc_180034037
0x180034019  test    dil, dil
0x18003401c  jz      loc_180033ED0
0x180034022  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180034027  mov     edx, [rbp+arg_0]; int
0x18003402a  mov     rcx, rax; this
0x18003402d  call    ?LogAikCertificateNotFound@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAikCertificateNotFound(long)
0x180034032  jmp     loc_180033ECD
0x180034037  mov     ebx, [rbp+pcbResult]
0x18003403a  call    cs:__imp_GetProcessHeap
0x180034041  nop     dword ptr [rax+rax+00h]
0x180034046  mov     r8d, ebx; dwBytes
0x180034049  mov     edx, 8; dwFlags
0x18003404e  mov     rcx, rax; hHeap
0x180034051  call    cs:__imp_HeapAlloc
0x180034058  nop     dword ptr [rax+rax+00h]
0x18003405d  mov     rsi, rax
0x180034060  test    rax, rax
0x180034063  jnz     short loc_180034087
0x180034065  mov     rcx, [rbp+28h]; this
0x180034069  mov     ebx, 8007000Eh
0x18003406e  mov     r9d, ebx; char *
0x180034071  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180034078  mov     edx, 696h; void *
0x18003407d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034082  jmp     loc_180033ED0
0x180034087  mov     [rsp+70h+var_48], 0; dwFlags
0x18003408f  lea     rax, [rbp+pcbResult]
0x180034093  mov     qword ptr [rsp+70h+dwFlags], rax; pcbResult
0x180034098  mov     r9d, [rbp+pcbResult]; cbOutput
0x18003409c  mov     r8, rsi; pbOutput
0x18003409f  lea     rdx, pszProperty; "SmartCardKeyCertificate"
0x1800340a6  mov     rcx, [rbp+phKey]; hObject
0x1800340aa  call    cs:__imp_NCryptGetProperty
0x1800340b1  nop     dword ptr [rax+rax+00h]
0x1800340b6  mov     ebx, eax
0x1800340b8  mov     [rbp+arg_0], eax
0x1800340bb  test    eax, eax
0x1800340bd  jns     short loc_18003410B
0x1800340bf  test    dil, dil
0x1800340c2  jz      short loc_1800340E6
0x1800340c4  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800340cb  jz      short loc_1800340E6
0x1800340cd  mov     r9d, eax
0x1800340d0  lea     r8, aNcryptgetprope_0; "NCryptGetProperty(hAIK Cert)"
0x1800340d7  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x1800340de  call    McTemplateU0zd_EventWriteTransfer
0x1800340e3  mov     ebx, [rbp+arg_0]
0x1800340e6  call    cs:__imp_GetProcessHeap
0x1800340ed  nop     dword ptr [rax+rax+00h]
0x1800340f2  mov     rcx, rax; hHeap
0x1800340f5  mov     r8, rsi; lpMem
0x1800340f8  xor     edx, edx; dwFlags
0x1800340fa  call    cs:__imp_HeapFree
0x180034101  nop     dword ptr [rax+rax+00h]
0x180034106  jmp     loc_180033ED0
0x18003410b  mov     [r12], rsi
0x18003410f  mov     eax, [rbp+pcbResult]
0x180034112  mov     [r15], eax
0x180034115  mov     rcx, [rbp+pszProviderName]; bstrString
0x180034119  test    rcx, rcx
0x18003411c  jz      short loc_18003412B
0x18003411e  call    cs:__imp_SysFreeString
0x180034125  nop     dword ptr [rax+rax+00h]
0x18003412a  nop
0x18003412b  mov     rcx, [rbp+phKey]; hObject
0x18003412f  test    rcx, rcx
0x180034132  jz      short loc_180034141
0x180034134  call    cs:__imp_NCryptFreeObject
0x18003413b  nop     dword ptr [rax+rax+00h]
0x180034140  nop
0x180034141  mov     rcx, [rbp+hObject]; hObject
0x180034145  test    rcx, rcx
0x180034148  jz      short loc_180034156
0x18003414a  call    cs:__imp_NCryptFreeObject
0x180034151  nop     dword ptr [rax+rax+00h]
0x180034156  xor     ebx, ebx
0x180034158  lea     rcx, [rbp+var_18]; this
0x18003415c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180034161  mov     eax, ebx
0x180034163  lea     r11, [rsp+70h+var_s0]
0x180034168  mov     rbx, [r11+38h]
0x18003416c  mov     rsi, [r11+40h]
0x180034170  mov     rsp, r11
0x180034173  pop     r15
0x180034175  pop     r14
0x180034177  pop     r12
0x180034179  pop     rdi
0x18003417a  pop     rbp
0x18003417b  retn
```
