# RegisterRPCInterface

- ea: `0x18000dcc0`
- end: `0x18000e099`
- name: `RegisterRPCInterface`
- size: `985`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800039f0`
- `0x18000bab4`
- `0x18000dc6c`
- `0x18000dcc0`
- `0x18000e710`
- `0x180033720`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000dfb5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000dfe8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000dfb5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000dfe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dffa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000df81`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000df81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd68`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000dd57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000dd57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd21`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000df1e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000df1e`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000dec4`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000dec4`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000de20`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000de20`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000e015`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000e024`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000e015`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000e024`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000dd7e`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000ddb7`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000dd7e`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000ddb7`

## string_xrefs

- `0x18000dd77`: `DefaultRpcAccess`
- `0x18000dd17`: `SYSTEM\CurrentControlSet\Services\dmwappushservice\Parameters`
- `0x18000dd4b`: `SYSTEM\CurrentControlSet\Services\dmwappushservice\Parameters`

## pseudocode

```c
__int64 RegisterRPCInterface()
{
  signed int v0; // ebx
  __int64 v1; // r8
  int v2; // eax
  int v3; // edi
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  signed int LastError; // eax
  __int64 *v9; // rdx
  DWORD ThreadId; // [rsp+40h] [rbp-29h] BYREF
  int pvData; // [rsp+48h] [rbp-21h] BYREF
  __int64 v13; // [rsp+50h] [rbp-19h] BYREF
  __int64 v14; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  int v16[4]; // [rsp+68h] [rbp-1h] BYREF
  DWORD *p_ThreadId; // [rsp+78h] [rbp+Fh]
  __int64 v18; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  ThreadId = 4;
  v13 = 0;
  v14 = 0;
  hKey = 0;
  pvData = 120;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\dmwappushservice\\Parameters",
          0,
          0x20019u,
          &hKey)
    && RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\dmwappushservice\\Parameters",
         L"IdleTimeout(sec)",
         0x10u,
         0,
         &pvData,
         &ThreadId) )
  {
    pvData = 120;
  }
  RegCloseKey(hKey);
  v0 = QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", &v13);
  if ( (int)(v0 + 0x80000000) < 0 || v0 == -1073741772 )
  {
    v0 = QueryTransientObjectSecurityDescriptor(9, L"PushRouterSvcRpc\\Interface", &v14);
    if ( ((v0 + 0x80000000) & 0x80000000) != 0 || v0 == -1073741772 )
    {
      qword_180050408 = v14;
      qword_180050018 = v13;
      v2 = RpcServerInterfaceGroupCreateW(&g_SharedRpcInterfaceList, 1, &g_SharedRpcEndpointList);
      v0 = v2;
      if ( v2 > 0 )
        v0 = (unsigned __int16)v2 | 0x80070000;
      if ( v0 >= 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
        {
          ThreadId = v0;
          p_ThreadId = &ThreadId;
          v18 = 4;
          McGenEventWrite_EventWriteTransfer(
            MDM_PUSHROUTER_Context,
            PushRouterRpcServerInterfaceGroupCreateSucceeded,
            v1,
            2,
            v16);
        }
        v3 = 0;
        while ( 1 )
        {
          v4 = RpcServerInterfaceGroupActivate(qword_180050A48);
          v0 = v4;
          if ( v4 > 0 )
            v0 = (unsigned __int16)v4 | 0x80070000;
          if ( v0 != -2147023156 )
            break;
          if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
          {
            ThreadId = -2147023156;
            p_ThreadId = &ThreadId;
            v18 = 4;
            McGenEventWrite_EventWriteTransfer(
              MDM_PUSHROUTER_Context,
              PushRouterRpcServerInterfaceGroupActivationFailedDuplicateEndPoints,
              v1,
              2,
              v16);
          }
          Sleep(0xBB8u);
          if ( ++v3 >= 5 )
            goto LABEL_25;
        }
        if ( v0 < 0 )
          goto LABEL_34;
        PrSvcIncMessageCount(v6, v5, v1);
LABEL_25:
        pvData = 0;
        v7 = SkipNonSecureCore(&pvData);
        v0 = v7;
        if ( v7 >= 0 )
        {
          if ( pvData )
          {
            v0 = 0;
          }
          else
          {
            g_ShutdownMonitoring = CreateEventW(0, 1, 0, 0);
            if ( !g_ShutdownMonitoring
              || (ThreadId = 0, (monitorThread1 = CreateThread(0, 0, TurnOnMonitoring, lpParameter, 0, &ThreadId)) == 0)
              || (v0 = 0, (monitorThread2 = CreateThread(0, 0, TurnOnMonitoring, qword_180050DE8, 0, &ThreadId)) == 0) )
            {
              LastError = GetLastError();
              v0 = LastError;
              if ( LastError > 0 )
                v0 = (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x220,
            (int)"onecoreuap\\admin\\dm\\pushrouter\\prcorelib\\api.cpp",
            (const char *)(unsigned int)v7);
        }
      }
      else if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
      {
        ThreadId = v0;
        p_ThreadId = &ThreadId;
        v18 = 4;
        McGenEventWrite_EventWriteTransfer(
          MDM_PUSHROUTER_Context,
          PushRouterRpcServerInterfaceGroupCreateFailed,
          v1,
          2,
          v16);
      }
    }
  }
LABEL_34:
  if ( v13 )
    FreeTransientObjectSecurityDescriptor();
  if ( v14 )
    FreeTransientObjectSecurityDescriptor();
  if ( v0 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    {
      v9 = PushRouterRpcServerInterfaceGroupActivationSucceeded;
      goto LABEL_43;
    }
  }
  else if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
  {
    v9 = PushRouterRpcServerInterfaceGroupActivationFailed;
LABEL_43:
    ThreadId = v0;
    p_ThreadId = &ThreadId;
    v18 = 4;
    McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, v9, v1, 2, v16);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18000dcc0  push    rbp
0x18000dcc2  push    rbx
0x18000dcc3  push    rsi
0x18000dcc4  push    rdi
0x18000dcc5  push    r14
0x18000dcc7  push    r15
0x18000dcc9  lea     rbp, [rsp-2Fh]
0x18000dcce  sub     rsp, 98h
0x18000dcd5  mov     rax, cs:__security_cookie
0x18000dcdc  xor     rax, rsp
0x18000dcdf  mov     [rbp+57h+var_38], rax
0x18000dce3  xor     esi, esi
0x18000dce5  mov     [rbp+57h+ThreadId], 4
0x18000dcec  lea     rax, [rbp+57h+hKey]
0x18000dcf0  mov     [rbp+57h+var_70], rsi
0x18000dcf4  mov     rdi, 0FFFFFFFF80000002h
0x18000dcfb  mov     [rbp+57h+var_68], rsi
0x18000dcff  mov     r9d, 20019h; samDesired
0x18000dd05  mov     [rbp+57h+hKey], rsi
0x18000dd09  lea     ebx, [rsi+78h]
0x18000dd0c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000dd11  xor     r8d, r8d; ulOptions
0x18000dd14  mov     [rbp+57h+var_78], ebx
0x18000dd17  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\dm"...
0x18000dd1e  mov     rcx, rdi; hKey
0x18000dd21  call    cs:__imp_RegOpenKeyExW
0x18000dd27  test    eax, eax
0x18000dd29  jnz     short loc_18000DD64
0x18000dd2b  lea     rax, [rbp+57h+ThreadId]
0x18000dd2f  mov     rcx, rdi; hkey
0x18000dd32  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000dd37  lea     r9d, [rsi+10h]; dwFlags
0x18000dd3b  lea     rax, [rbp+57h+var_78]
0x18000dd3f  mov     [rsp+0C0h+pvData], rax; pvData
0x18000dd44  lea     r8, Value; "IdleTimeout(sec)"
0x18000dd4b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\dm"...
0x18000dd52  mov     [rsp+0C0h+phkResult], rsi; pdwType
0x18000dd57  call    cs:__imp_RegGetValueW
0x18000dd5d  test    eax, eax
0x18000dd5f  jz      short loc_18000DD64
0x18000dd61  mov     [rbp+57h+var_78], ebx
0x18000dd64  mov     rcx, [rbp+57h+hKey]; hKey
0x18000dd68  call    cs:__imp_RegCloseKey
0x18000dd6e  lea     r8, [rbp+57h+var_70]
0x18000dd72  mov     ecx, 8
0x18000dd77  lea     rdx, aDefaultrpcacce; "DefaultRpcAccess"
0x18000dd7e  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18000dd84  mov     r14d, 80000000h
0x18000dd8a  mov     edi, 0C0000034h
0x18000dd8f  mov     ebx, eax
0x18000dd91  mov     r15d, 2
0x18000dd97  add     eax, r14d
0x18000dd9a  test    r14d, eax
0x18000dd9d  jnz     short loc_18000DDA7
0x18000dd9f  cmp     ebx, edi
0x18000dda1  jnz     loc_18000E00C
0x18000dda7  lea     r8, [rbp+57h+var_68]
0x18000ddab  mov     ecx, 9
0x18000ddb0  lea     rdx, aPushroutersvcr; "PushRouterSvcRpc\\Interface"
0x18000ddb7  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18000ddbd  mov     ebx, eax
0x18000ddbf  add     eax, r14d
0x18000ddc2  test    r14d, eax
0x18000ddc5  jnz     short loc_18000DDCF
0x18000ddc7  cmp     ebx, edi
0x18000ddc9  jnz     loc_18000E00C
0x18000ddcf  mov     rax, [rbp+57h+var_68]
0x18000ddd3  lea     r8, ?g_SharedRpcEndpointList@@3PAURPC_ENDPOINT_TEMPLATEW@@A; RPC_ENDPOINT_TEMPLATEW near * g_SharedRpcEndpointList
0x18000ddda  mov     cs:qword_180050408, rax
0x18000dde1  lea     rcx, ?g_SharedRpcInterfaceList@@3PAURPC_INTERFACE_TEMPLATEW@@A; RPC_INTERFACE_TEMPLATEW near * g_SharedRpcInterfaceList
0x18000dde8  mov     rax, [rbp+57h+var_70]
0x18000ddec  mov     r9d, 1
0x18000ddf2  mov     cs:qword_180050018, rax
0x18000ddf9  mov     edx, r9d
0x18000ddfc  lea     rax, qword_180050A48
0x18000de03  mov     [rsp+0C0h+var_88], rax
0x18000de08  lea     rax, ?PushRouterRPCIdleCallback@@YAXPEAX0K@Z; PushRouterRPCIdleCallback(void *,void *,ulong)
0x18000de0f  mov     [rsp+0C0h+pcbData], rsi
0x18000de14  mov     [rsp+0C0h+pvData], rax
0x18000de19  mov     eax, [rbp+57h+var_78]
0x18000de1c  mov     dword ptr [rsp+0C0h+phkResult], eax
0x18000de20  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x18000de26  mov     ebx, eax
0x18000de28  mov     r14d, 80070000h
0x18000de2e  test    eax, eax
0x18000de30  jle     short loc_18000DE38
0x18000de32  movzx   ebx, ax
0x18000de35  or      ebx, r14d
0x18000de38  test    ebx, ebx
0x18000de3a  jns     short loc_18000DE80
0x18000de3c  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000de43  jz      loc_18000E00C
0x18000de49  lea     rax, [rbp+57h+ThreadId]
0x18000de4d  mov     [rbp+57h+ThreadId], ebx
0x18000de50  mov     [rbp+57h+var_48], rax
0x18000de54  lea     rdx, PushRouterRpcServerInterfaceGroupCreateFailed
0x18000de5b  lea     rax, [rbp+57h+var_58]
0x18000de5f  mov     [rbp+57h+var_40], 4
0x18000de67  mov     r9d, r15d
0x18000de6a  mov     [rsp+0C0h+phkResult], rax
0x18000de6f  lea     rcx, MDM_PUSHROUTER_Context
0x18000de76  call    McGenEventWrite_EventWriteTransfer
0x18000de7b  jmp     loc_18000E00C
0x18000de80  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, r15b
0x18000de87  jz      short loc_18000DEBB
0x18000de89  lea     rax, [rbp+57h+ThreadId]
0x18000de8d  mov     [rbp+57h+ThreadId], ebx
0x18000de90  mov     [rbp+57h+var_48], rax
0x18000de94  lea     rdx, PushRouterRpcServerInterfaceGroupCreateSucceeded
0x18000de9b  lea     rax, [rbp+57h+var_58]
0x18000de9f  mov     [rbp+57h+var_40], 4
0x18000dea7  mov     r9d, r15d
0x18000deaa  mov     [rsp+0C0h+phkResult], rax; int
0x18000deaf  lea     rcx, MDM_PUSHROUTER_Context
0x18000deb6  call    McGenEventWrite_EventWriteTransfer
0x18000debb  mov     edi, esi
0x18000debd  mov     rcx, cs:qword_180050A48
0x18000dec4  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18000deca  mov     ebx, eax
0x18000decc  test    eax, eax
0x18000dece  jle     short loc_18000DED6
0x18000ded0  movzx   ebx, ax
0x18000ded3  or      ebx, r14d
0x18000ded6  cmp     ebx, 800706CCh
0x18000dedc  jnz     short loc_18000DF2D
0x18000dede  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000dee5  jz      short loc_18000DF19
0x18000dee7  lea     rax, [rbp+57h+ThreadId]
0x18000deeb  mov     [rbp+57h+ThreadId], ebx
0x18000deee  mov     [rbp+57h+var_48], rax
0x18000def2  lea     rdx, PushRouterRpcServerInterfaceGroupActivationFailedDuplicateEndPoints
0x18000def9  lea     rax, [rbp+57h+var_58]
0x18000defd  mov     [rbp+57h+var_40], 4
0x18000df05  mov     r9d, r15d
0x18000df08  mov     [rsp+0C0h+phkResult], rax
0x18000df0d  lea     rcx, MDM_PUSHROUTER_Context
0x18000df14  call    McGenEventWrite_EventWriteTransfer
0x18000df19  mov     ecx, 0BB8h; dwMilliseconds
0x18000df1e  call    cs:__imp_Sleep
0x18000df24  inc     edi
0x18000df26  cmp     edi, 5
0x18000df29  jl      short loc_18000DEBD
0x18000df2b  jmp     short loc_18000DF3A
0x18000df2d  test    ebx, ebx
0x18000df2f  js      loc_18000E00C
0x18000df35  call    ?PrSvcIncMessageCount@@YAHXZ; PrSvcIncMessageCount(void)
0x18000df3a  lea     rcx, [rbp+57h+var_78]; int *
0x18000df3e  mov     [rbp+57h+var_78], esi
0x18000df41  call    ?SkipNonSecureCore@@YAJPEAH@Z; SkipNonSecureCore(int *)
0x18000df46  mov     ebx, eax
0x18000df48  test    eax, eax
0x18000df4a  jns     short loc_18000DF69
0x18000df4c  mov     rcx, [rbp+5Fh]; this
0x18000df50  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\pushrouter\\prco"...
0x18000df57  mov     r9d, eax; char *
0x18000df5a  mov     edx, 220h; void *
0x18000df5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df64  jmp     loc_18000E00C
0x18000df69  cmp     [rbp+57h+var_78], esi
0x18000df6c  jz      short loc_18000DF75
0x18000df6e  mov     ebx, esi
0x18000df70  jmp     loc_18000E00C
0x18000df75  xor     r9d, r9d; lpName
0x18000df78  xor     r8d, r8d; bInitialState
0x18000df7b  xor     ecx, ecx; lpEventAttributes
0x18000df7d  lea     edx, [r9+1]; bManualReset
0x18000df81  call    cs:__imp_CreateEventW
0x18000df87  mov     cs:?g_ShutdownMonitoring@@3PEAXEA, rax; void * g_ShutdownMonitoring
0x18000df8e  test    rax, rax
0x18000df91  jz      short loc_18000DFFA
0x18000df93  mov     r9, cs:lpParameter; lpParameter
0x18000df9a  lea     rax, [rbp+57h+ThreadId]
0x18000df9e  mov     [rsp+0C0h+pvData], rax; lpThreadId
0x18000dfa3  lea     r8, ?TurnOnMonitoring@@YAKPEAX@Z; lpStartAddress
0x18000dfaa  xor     edx, edx; dwStackSize
0x18000dfac  mov     dword ptr [rsp+0C0h+phkResult], esi; dwCreationFlags
0x18000dfb0  xor     ecx, ecx; lpThreadAttributes
0x18000dfb2  mov     [rbp+57h+ThreadId], esi
0x18000dfb5  call    cs:__imp_CreateThread
0x18000dfbb  mov     cs:?monitorThread1@@3PEAXEA, rax; void * monitorThread1
0x18000dfc2  test    rax, rax
0x18000dfc5  jz      short loc_18000DFFA
0x18000dfc7  mov     r9, cs:qword_180050DE8; lpParameter
0x18000dfce  lea     rax, [rbp+57h+ThreadId]
0x18000dfd2  mov     [rsp+0C0h+pvData], rax; lpThreadId
0x18000dfd7  lea     r8, ?TurnOnMonitoring@@YAKPEAX@Z; lpStartAddress
0x18000dfde  xor     edx, edx; dwStackSize
0x18000dfe0  mov     dword ptr [rsp+0C0h+phkResult], esi; dwCreationFlags
0x18000dfe4  xor     ecx, ecx; lpThreadAttributes
0x18000dfe6  mov     ebx, esi
0x18000dfe8  call    cs:__imp_CreateThread
0x18000dfee  mov     cs:?monitorThread2@@3PEAXEA, rax; void * monitorThread2
0x18000dff5  test    rax, rax
0x18000dff8  jnz     short loc_18000E00C
0x18000dffa  call    cs:__imp_GetLastError
0x18000e000  mov     ebx, eax
0x18000e002  test    eax, eax
0x18000e004  jle     short loc_18000E00C
0x18000e006  movzx   ebx, ax
0x18000e009  or      ebx, r14d
0x18000e00c  mov     rcx, [rbp+57h+var_70]
0x18000e010  test    rcx, rcx
0x18000e013  jz      short loc_18000E01B
0x18000e015  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000e01b  mov     rcx, [rbp+57h+var_68]
0x18000e01f  test    rcx, rcx
0x18000e022  jz      short loc_18000E02A
0x18000e024  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000e02a  test    ebx, ebx
0x18000e02c  jns     short loc_18000E040
0x18000e02e  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000e035  jz      short loc_18000E07B
0x18000e037  lea     rdx, PushRouterRpcServerInterfaceGroupActivationFailed
0x18000e03e  jmp     short loc_18000E050
0x18000e040  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, r15b
0x18000e047  jz      short loc_18000E07B
0x18000e049  lea     rdx, PushRouterRpcServerInterfaceGroupActivationSucceeded
0x18000e050  lea     rax, [rbp+57h+ThreadId]
0x18000e054  mov     [rbp+57h+ThreadId], ebx
0x18000e057  mov     [rbp+57h+var_48], rax
0x18000e05b  lea     rcx, MDM_PUSHROUTER_Context
0x18000e062  lea     rax, [rbp+57h+var_58]
0x18000e066  mov     [rbp+57h+var_40], 4
0x18000e06e  mov     r9d, r15d
0x18000e071  mov     [rsp+0C0h+phkResult], rax
0x18000e076  call    McGenEventWrite_EventWriteTransfer
0x18000e07b  mov     eax, ebx
0x18000e07d  mov     rcx, [rbp+57h+var_38]
0x18000e081  xor     rcx, rsp; StackCookie
0x18000e084  call    __security_check_cookie
0x18000e089  add     rsp, 98h
0x18000e090  pop     r15
0x18000e092  pop     r14
0x18000e094  pop     rdi
0x18000e095  pop     rsi
0x18000e096  pop     rbx
0x18000e097  pop     rbp
0x18000e098  retn
```
