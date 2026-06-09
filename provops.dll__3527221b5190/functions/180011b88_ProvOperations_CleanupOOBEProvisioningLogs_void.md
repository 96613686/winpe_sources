# ProvOperations::CleanupOOBEProvisioningLogs(void)

- ea: `0x180011b88`
- end: `0x180011da8`
- name: `?CleanupOOBEProvisioningLogs@ProvOperations@@QEAAXXZ`
- size: `544`
- prototype: `void __fastcall(ProvOperations *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180010b40`

## callees

- `0x18000d0fc`
- `0x18000d604`
- `0x180011b88`
- `0x1800120bc`
- `0x180012e94`
- `0x180014434`
- `0x18001862c`
- `0x18001b3c8`
- `0x1800225e8`
- `0x180033e9a`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d4f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180011ced`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180011ced`

## pseudocode

```c
void __fastcall ProvOperations::CleanupOOBEProvisioningLogs(ProvOperations *this)
{
  TraceLoggingCorrelationVector *v2; // rcx
  WCHAR *v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // r8
  signed int LastError; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  wil *v9; // rcx
  signed int v10; // [rsp+30h] [rbp-238h] BYREF
  char *v11; // [rsp+38h] [rbp-230h] BYREF
  _QWORD v12[3]; // [rsp+40h] [rbp-228h] BYREF
  char v13; // [rsp+58h] [rbp-210h]
  void **v14; // [rsp+60h] [rbp-208h] BYREF
  int v15; // [rsp+68h] [rbp-200h] BYREF
  char v16; // [rsp+6Ch] [rbp-1FCh]
  int v17; // [rsp+90h] [rbp-1D8h] BYREF
  const char *v18; // [rsp+98h] [rbp-1D0h]
  __int64 v19; // [rsp+A0h] [rbp-1C8h]
  char v20; // [rsp+A8h] [rbp-1C0h]
  int v21; // [rsp+B0h] [rbp-1B8h]
  _BYTE v22[168]; // [rsp+B8h] [rbp-1B0h] BYREF
  int v23; // [rsp+160h] [rbp-108h]
  __int64 v24; // [rsp+168h] [rbp-100h]
  int *v25; // [rsp+170h] [rbp-F8h]
  __int64 v26; // [rsp+178h] [rbp-F0h]
  __int64 v27; // [rsp+180h] [rbp-E8h]
  void ***v28; // [rsp+188h] [rbp-E0h]
  __int64 v29; // [rsp+190h] [rbp-D8h]
  int v30; // [rsp+198h] [rbp-D0h]
  int *v31; // [rsp+1A0h] [rbp-C8h]
  char v32; // [rsp+1A8h] [rbp-C0h]
  LPCWSTR lpFileName; // [rsp+1B0h] [rbp-B8h] BYREF
  char Destination[144]; // [rsp+1C0h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v10 = 0;
  v15 = 0;
  v16 = 0;
  v20 = 0;
  v17 = 0;
  v18 = "ProvOpsCleanupOOBEProvisioningLogs";
  v19 = 0;
  v21 = 0;
  *(_OWORD *)&v22[152] = 0;
  memset_0(v22, 0, 0x98u);
  v23 = 1;
  v24 = 0;
  v25 = &v15;
  v26 = 0;
  v27 = 0;
  v28 = &v14;
  v29 = 0;
  v30 = 0;
  v31 = &v17;
  v32 = 0;
  v14 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::StartActivity((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs *)&v14);
  v11 = Destination;
  v2 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 7);
  if ( v2 )
    TraceLoggingCorrelationVector::ToString(v2, Destination);
  try
  {
    v12[0] = &v10;
    v12[1] = &v14;
    v12[2] = &v11;
    v13 = 1;
    lpFileName = 0;
    ProvOperations::GetOOBEProvisioningLogsPath((unsigned __int16 **)&lpFileName);
    v3 = (WCHAR *)lpFileName;
    if ( DeleteFileW(lpFileName) )
    {
      if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(v4, "L", v5, 1);
      Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::ProvOpsCleanupOOBEProvisioningLogsSucceeded(v11);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 2 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v10 = LastError;
      }
    }
    if ( v3 )
      CoTaskMemFree(v3);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x42E, v7, v8);
    v10 = wil::ResultFromCaughtException(v9);
  }
  wil::details::ScopeExitFn__lambda_d915d29a2f81576fbc230da2674011e6___::_ScopeExitFn__lambda_d915d29a2f81576fbc230da2674011e6___(v12);
  v14 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v14);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v14);
}

```

## disassembly

```asm
0x180011b88  mov     r11, rsp
0x180011b8b  mov     [r11+10h], rbx
0x180011b8f  mov     [r11+18h], rsi
0x180011b93  push    rdi
0x180011b94  sub     rsp, 260h
0x180011b9b  mov     rax, cs:__security_cookie
0x180011ba2  xor     rax, rsp
0x180011ba5  mov     [rsp+268h+var_18], rax
0x180011bad  mov     rbx, rcx
0x180011bb0  xor     esi, esi
0x180011bb2  mov     [rsp+268h+var_238], esi
0x180011bb6  mov     [rsp+268h+var_200], esi
0x180011bba  mov     [rsp+268h+var_1FC], sil
0x180011bbf  mov     [rsp+268h+var_1C0], sil
0x180011bc7  mov     [rsp+268h+var_1D8], esi
0x180011bce  lea     rax, aProvopscleanup; "ProvOpsCleanupOOBEProvisioningLogs"
0x180011bd5  mov     [r11-1D0h], rax
0x180011bdc  mov     [r11-1C8h], rsi
0x180011be3  mov     [rsp+268h+var_1B8], esi
0x180011bea  xorps   xmm0, xmm0
0x180011bed  movdqa  [rsp+268h+var_118], xmm0
0x180011bf6  xor     edx, edx; Val
0x180011bf8  mov     r8d, 98h; Size
0x180011bfe  lea     rcx, [r11-1B0h]; void *
0x180011c05  call    memset_0
0x180011c0a  mov     [rsp+268h+var_108], 1
0x180011c15  xor     eax, eax
0x180011c17  mov     [rsp+268h+var_100], rax
0x180011c1f  lea     rax, [rsp+268h+var_200]
0x180011c24  mov     [rsp+268h+var_F8], rax
0x180011c2c  mov     [rsp+268h+var_F0], rsi
0x180011c34  mov     [rsp+268h+var_E8], rsi
0x180011c3c  lea     rax, [rsp+268h+var_208]
0x180011c41  mov     [rsp+268h+var_E0], rax
0x180011c49  mov     [rsp+268h+var_D8], rsi
0x180011c51  mov     [rsp+268h+var_D0], esi
0x180011c58  lea     rax, [rsp+268h+var_1D8]
0x180011c60  mov     [rsp+268h+var_C8], rax
0x180011c68  mov     [rsp+268h+var_C0], sil
0x180011c70  lea     rdi, ??_7ProvOpsCleanupOOBEProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::`vftable'
0x180011c77  mov     [rsp+268h+var_208], rdi
0x180011c7c  lea     rcx, [rsp+268h+var_208]; this
0x180011c81  call    ?StartActivity@ProvOpsCleanupOOBEProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::StartActivity(void)
0x180011c86  nop
0x180011c87  lea     rax, [rsp+268h+Destination]
0x180011c8f  mov     [rsp+268h+var_230], rax
0x180011c94  mov     rcx, [rbx+38h]; this
0x180011c98  test    rcx, rcx
0x180011c9b  jz      short loc_180011CAA
0x180011c9d  lea     rdx, [rsp+268h+Destination]; Destination
0x180011ca5  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180011caa  lea     rax, [rsp+268h+var_238]
0x180011caf  mov     [rsp+268h+var_228], rax
0x180011cb4  lea     rax, [rsp+268h+var_208]
0x180011cb9  mov     [rsp+268h+var_220], rax
0x180011cbe  lea     rax, [rsp+268h+var_230]
0x180011cc3  mov     [rsp+268h+var_218], rax
0x180011cc8  mov     [rsp+268h+var_210], 1
0x180011ccd  mov     [rsp+268h+lpFileName], rsi
0x180011cd5  lea     rcx, [rsp+268h+lpFileName]; unsigned __int16 **
0x180011cdd  call    ?GetOOBEProvisioningLogsPath@ProvOperations@@SAJPEAPEAG@Z; ProvOperations::GetOOBEProvisioningLogsPath(ushort * *)
0x180011ce2  mov     rbx, [rsp+268h+lpFileName]
0x180011cea  mov     rcx, rbx; lpFileName
0x180011ced  call    cs:__imp_DeleteFileW
0x180011cf3  test    eax, eax
0x180011cf5  jnz     short loc_180011D14
0x180011cf7  call    cs:__imp_GetLastError
0x180011cfd  cmp     eax, 2
0x180011d00  jz      short loc_180011D47
0x180011d02  test    eax, eax
0x180011d04  jle     short loc_180011D0E
0x180011d06  movzx   eax, ax
0x180011d09  or      eax, 80070000h
0x180011d0e  mov     [rsp+268h+var_238], eax
0x180011d12  jmp     short loc_180011D47
0x180011d14  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x180011d1b  jz      short loc_180011D3C
0x180011d1d  lea     rax, [rsp+268h+lpFileName]
0x180011d25  mov     [rsp+268h+var_248], rax
0x180011d2a  mov     r9d, 1
0x180011d30  lea     rdx, ProvOpsCleanupOOBEProvisioningLogsSucceeded; "L"
0x180011d37  call    McGenEventWrite_EventWriteTransfer
0x180011d3c  mov     rcx, [rsp+268h+var_230]; char *
0x180011d41  call    ?ProvOpsCleanupOOBEProvisioningLogsSucceeded@ProvOpsCleanupOOBEProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@SAXPEBD@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::ProvOpsCleanupOOBEProvisioningLogsSucceeded(char const *)
0x180011d46  nop
0x180011d47  test    rbx, rbx
0x180011d4a  jz      short loc_180011D56
0x180011d4c  mov     rcx, rbx; pv
0x180011d4f  call    cs:__imp_CoTaskMemFree
0x180011d55  nop
0x180011d56  jmp     short loc_180011D5F
0x180011d58  lea     rdi, ??_7ProvOpsCleanupOOBEProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::`vftable'
0x180011d5f  lea     rcx, [rsp+268h+var_228]
0x180011d64  call    wil__details__ScopeExitFn__lambda_d915d29a2f81576fbc230da2674011e6______ScopeExitFn__lambda_d915d29a2f81576fbc230da2674011e6___
0x180011d69  nop
0x180011d6a  mov     [rsp+268h+var_208], rdi
0x180011d6f  lea     rcx, [rsp+268h+var_208]
0x180011d74  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011d79  lea     rcx, [rsp+268h+var_208]
0x180011d7e  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011d83  mov     rcx, [rsp+268h+var_18]
0x180011d8b  xor     rcx, rsp; StackCookie
0x180011d8e  call    __security_check_cookie
0x180011d93  lea     r11, [rsp+268h+var_8]
0x180011d9b  mov     rbx, [r11+18h]
0x180011d9f  mov     rsi, [r11+20h]
0x180011da3  mov     rsp, r11
0x180011da6  pop     rdi
0x180011da7  retn
```
