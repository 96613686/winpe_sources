# UninitializeService(long)

- ea: `0x18000993c`
- end: `0x180009af4`
- name: `?UninitializeService@@YAJJ@Z`
- size: `440`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008f30`

## callees

- `0x180001cf0`
- `0x180009418`
- `0x18000993c`
- `0x18000a850`
- `0x18000e83c`
- `0x18000e91c`
- `0x18000f0b8`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupClose` at `0x1800099d8`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x1800099d8`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x180009979`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x180009979`
- `DeclaredConfigurationAPI!DeinitOrchestratorEngine` at `0x180009957`
- `DeclaredConfigurationAPI!DeinitOrchestratorEngine` at `0x180009957`

## pseudocode

```c
__int64 __fastcall UninitializeService()
{
  __int64 v0; // rcx
  signed int v1; // eax
  __int64 v2; // rcx
  __int64 v3; // r8
  bool v4; // sf
  __int64 *v5; // rdx
  int v6; // eax
  __int64 v7; // r8
  signed int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 *v11; // rdx
  int v12; // eax
  CDeclaredConfigurationLogger *Logger; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  signed int v18; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v19[16]; // [rsp+38h] [rbp-30h] BYREF
  signed int *v20; // [rsp+48h] [rbp-20h]
  __int64 v21; // [rsp+50h] [rbp-18h]

  DeinitOrchestratorEngine();
  LODWORD(v0) = qword_18001B6D8;
  if ( !qword_18001B6D8 )
    goto LABEL_18;
  v1 = RpcServerInterfaceGroupDeactivate(qword_18001B6D8, 1);
  v4 = v1 < 0;
  if ( v1 > 0 )
  {
    v1 = (unsigned __int16)v1 | 0x80070000;
    v4 = v1 < 0;
  }
  if ( v4 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) == 0 )
      goto LABEL_10;
    v5 = EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupDeactivationFailure;
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) == 0 )
      goto LABEL_10;
    v5 = EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupDeactivationSuccess;
  }
  v18 = v1;
  v21 = 4;
  v20 = &v18;
  McGenEventWrite_EventWriteTransfer(v2, v5, v3, 2, v19);
LABEL_10:
  v6 = RpcServerInterfaceGroupClose(qword_18001B6D8);
  v8 = v6;
  if ( v6 > 0 )
    v8 = (unsigned __int16)v6 | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      v18 = v8;
      v20 = &v18;
      v21 = 4;
      McGenEventWrite_EventWriteTransfer(v0, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupCloseSuccess, v7, 2, v19);
    }
    qword_18001B6D8 = 0;
LABEL_18:
    v8 = CmLockSvcUninitialize(v0);
    if ( v8 >= 0 )
    {
      v12 = SvcEngUninitialize();
      v8 = v12;
      if ( v12 >= 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) == 0 )
          goto LABEL_28;
        v11 = EnterpriseDiagnosticsDcSvcEngUninitializeSuccess;
      }
      else
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) == 0 )
          goto LABEL_28;
        v11 = EnterpriseDiagnosticsDcSvcEngUninitializeFailure;
      }
      v18 = v12;
      goto LABEL_27;
    }
    goto LABEL_19;
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) == 0 )
    goto LABEL_28;
  v18 = v8;
  v20 = &v18;
  v21 = 4;
  McGenEventWrite_EventWriteTransfer(v0, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupCloseFailure, v7, 2, v19);
LABEL_19:
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
  {
    v18 = v8;
    v11 = EnterpriseDiagnosticsDcSvcEngUnregisterRPCInterfaceFailure;
LABEL_27:
    v21 = 4;
    v20 = &v18;
    McGenEventWrite_EventWriteTransfer(v9, v11, v10, 2, v19);
  }
LABEL_28:
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogServiceStop(Logger, v14, v15, v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000993c  push    rbp
0x18000993e  push    rbx
0x18000993f  push    rsi
0x180009940  push    r14
0x180009942  mov     rbp, rsp
0x180009945  sub     rsp, 68h
0x180009949  mov     rax, cs:__security_cookie
0x180009950  xor     rax, rsp
0x180009953  mov     [rbp+var_10], rax
0x180009957  call    cs:__imp_DeinitOrchestratorEngine
0x18000995d  mov     rcx, cs:qword_18001B6D8
0x180009964  mov     esi, 4
0x180009969  lea     r14d, [rsi-2]
0x18000996d  test    rcx, rcx
0x180009970  jz      loc_180009A62
0x180009976  lea     edx, [rsi-3]
0x180009979  call    cs:__imp_RpcServerInterfaceGroupDeactivate
0x18000997f  test    eax, eax
0x180009981  jle     short loc_18000998D
0x180009983  movzx   eax, ax
0x180009986  or      eax, 80070000h
0x18000998b  test    eax, eax
0x18000998d  jns     short loc_1800099A1
0x18000998f  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180009996  jz      short loc_1800099D1
0x180009998  lea     rdx, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupDeactivationFailure
0x18000999f  jmp     short loc_1800099B1
0x1800099a1  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, sil
0x1800099a8  jz      short loc_1800099D1
0x1800099aa  lea     rdx, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupDeactivationSuccess
0x1800099b1  mov     [rbp+var_38], eax
0x1800099b4  mov     r9d, r14d
0x1800099b7  lea     rax, [rbp+var_38]
0x1800099bb  mov     [rbp+var_18], rsi
0x1800099bf  mov     [rbp+var_20], rax
0x1800099c3  lea     rax, [rbp+var_30]
0x1800099c7  mov     [rsp+68h+var_48], rax
0x1800099cc  call    McGenEventWrite_EventWriteTransfer
0x1800099d1  mov     rcx, cs:qword_18001B6D8
0x1800099d8  call    cs:__imp_RpcServerInterfaceGroupClose
0x1800099de  mov     ebx, eax
0x1800099e0  test    eax, eax
0x1800099e2  jle     short loc_1800099ED
0x1800099e4  movzx   ebx, ax
0x1800099e7  or      ebx, 80070000h
0x1800099ed  test    ebx, ebx
0x1800099ef  jns     short loc_180009A27
0x1800099f1  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800099f8  jz      loc_180009ACF
0x1800099fe  lea     rax, [rbp+var_38]
0x180009a02  mov     [rbp+var_38], ebx
0x180009a05  mov     [rbp+var_20], rax
0x180009a09  lea     rdx, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupCloseFailure
0x180009a10  lea     rax, [rbp+var_30]
0x180009a14  mov     [rbp+var_18], rsi
0x180009a18  mov     r9d, r14d
0x180009a1b  mov     [rsp+68h+var_48], rax
0x180009a20  call    McGenEventWrite_EventWriteTransfer
0x180009a25  jmp     short loc_180009A6D
0x180009a27  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, sil
0x180009a2e  jz      short loc_180009A57
0x180009a30  lea     rax, [rbp+var_38]
0x180009a34  mov     [rbp+var_38], ebx
0x180009a37  mov     [rbp+var_20], rax
0x180009a3b  lea     rdx, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupCloseSuccess
0x180009a42  lea     rax, [rbp+var_30]
0x180009a46  mov     [rbp+var_18], rsi
0x180009a4a  mov     r9d, r14d
0x180009a4d  mov     [rsp+68h+var_48], rax
0x180009a52  call    McGenEventWrite_EventWriteTransfer
0x180009a57  mov     cs:qword_18001B6D8, 0
0x180009a62  call    ?CmLockSvcUninitialize@@YAJJ@Z; CmLockSvcUninitialize(long)
0x180009a67  mov     ebx, eax
0x180009a69  test    eax, eax
0x180009a6b  jns     short loc_180009A82
0x180009a6d  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180009a74  jz      short loc_180009ACF
0x180009a76  mov     [rbp+var_38], ebx
0x180009a79  lea     rdx, EnterpriseDiagnosticsDcSvcEngUnregisterRPCInterfaceFailure
0x180009a80  jmp     short loc_180009AB2
0x180009a82  call    ?SvcEngUninitialize@@YAJJ@Z; SvcEngUninitialize(long)
0x180009a87  mov     ebx, eax
0x180009a89  test    eax, eax
0x180009a8b  jns     short loc_180009A9F
0x180009a8d  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180009a94  jz      short loc_180009ACF
0x180009a96  lea     rdx, EnterpriseDiagnosticsDcSvcEngUninitializeFailure
0x180009a9d  jmp     short loc_180009AAF
0x180009a9f  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, sil
0x180009aa6  jz      short loc_180009ACF
0x180009aa8  lea     rdx, EnterpriseDiagnosticsDcSvcEngUninitializeSuccess
0x180009aaf  mov     [rbp+var_38], eax
0x180009ab2  lea     rax, [rbp+var_38]
0x180009ab6  mov     [rbp+var_18], rsi
0x180009aba  mov     [rbp+var_20], rax
0x180009abe  mov     r9d, r14d
0x180009ac1  lea     rax, [rbp+var_30]
0x180009ac5  mov     [rsp+68h+var_48], rax
0x180009aca  call    McGenEventWrite_EventWriteTransfer
0x180009acf  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180009ad4  mov     rcx, rax; this
0x180009ad7  call    ?LogServiceStop@CDeclaredConfigurationLogger@@QEAAXXZ; CDeclaredConfigurationLogger::LogServiceStop(void)
0x180009adc  mov     eax, ebx
0x180009ade  mov     rcx, [rbp+var_10]
0x180009ae2  xor     rcx, rsp; StackCookie
0x180009ae5  call    __security_check_cookie
0x180009aea  add     rsp, 68h
0x180009aee  pop     r14
0x180009af0  pop     rsi
0x180009af1  pop     rbx
0x180009af2  pop     rbp
0x180009af3  retn
```
