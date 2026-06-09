# RegisterRPCInterface(void)

- ea: `0x180007b9c`
- end: `0x180007ed2`
- name: `?RegisterRPCInterface@@YAJXZ`
- size: `822`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800060b0`

## callees

- `0x180001cf0`
- `0x180007b9c`
- `0x18000a850`
- `0x18000f00c`
- `0x1800106c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007c40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007c40`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180007e50`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180007e50`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x180007dc4`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x180007dc4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007ea2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007ea2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007c9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007c9b`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180007ced`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180007d1b`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180007ced`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180007d1b`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180007caa`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180007cb9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180007ec7`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180007caa`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180007cb9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180007ec7`

## string_xrefs

- `0x180007ce6`: `DefaultRpcAccess`
- `0x180007c00`: `SYSTEM\CurrentControlSet\Services\dcsvc\Parameters`
- `0x180007c34`: `SYSTEM\CurrentControlSet\Services\dcsvc\Parameters`

## pseudocode

```c
__int64 RegisterRPCInterface(void)
{
  void *v0; // rdi
  signed int v1; // eax
  __int64 v2; // rcx
  __int64 v3; // r8
  signed int v4; // ebx
  int MergedSecurityDescriptorForTransientObject; // eax
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  int i; // r14d
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  int pvData; // [rsp+40h] [rbp-39h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-31h] BYREF
  __int64 v16; // [rsp+50h] [rbp-29h] BYREF
  __int64 v17; // [rsp+58h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-19h] BYREF
  __int64 v19; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v20[16]; // [rsp+70h] [rbp-9h] BYREF
  DWORD *p_pcbData; // [rsp+80h] [rbp+7h]
  __int64 v22; // [rsp+88h] [rbp+Fh]

  v0 = 0;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  hKey = 0;
  pvData = 120;
  pcbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\dcsvc\\Parameters", 0, 0x20019u, &hKey)
    && RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\dcsvc\\Parameters",
         L"IdleTimeout(sec)",
         0x10u,
         0,
         &pvData,
         &pcbData) )
  {
    pvData = 120;
  }
  RegCloseKey(hKey);
  pcbData = 0;
  v1 = CmLockSvcInitialize();
  v4 = v1;
  if ( v1 < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
    {
      pcbData = v1;
      v22 = 4;
      p_pcbData = &pcbData;
      McGenEventWrite_EventWriteTransfer(v2, EnterpriseDiagnosticsConfigManagerLockServiceBindingFailed, v3, 2, v20);
    }
LABEL_7:
    LocalFree(v0);
    goto LABEL_8;
  }
  v4 = QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", &v16);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -1073741772 )
    goto LABEL_7;
  v4 = QueryTransientObjectSecurityDescriptor(9, L"DMOrchestratorRpc\\Interface", &v17);
  if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -1073741772 )
    goto LABEL_7;
  qword_18001B288 = v17;
  qword_18001B018 = v16;
  MergedSecurityDescriptorForTransientObject = DmGetMergedSecurityDescriptorForTransientObject(
                                                 9,
                                                 L"CmLockSvcDcRpcUap\\Interface",
                                                 L"CmLockSvcDcRpc\\Interface",
                                                 &v19,
                                                 &pcbData);
  v0 = (void *)v19;
  v4 = MergedSecurityDescriptorForTransientObject;
  if ( MergedSecurityDescriptorForTransientObject >= 0 )
  {
    qword_18001B2D8 = v19;
    v7 = RpcServerInterfaceGroupCreateW(&g_SharedRpcInterfaceList, 2, &g_SharedRpcEndpointList);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 >= 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        pvData = v4;
        p_pcbData = (DWORD *)&pvData;
        v22 = 4;
        McGenEventWrite_EventWriteTransfer(
          v8,
          EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupCreateSuccess,
          v9,
          2,
          v20);
      }
      for ( i = 0; i < 5; ++i )
      {
        v11 = RpcServerInterfaceGroupActivate(qword_18001B6D8);
        v4 = v11;
        if ( v11 > 0 )
          v4 = (unsigned __int16)v11 | 0x80070000;
        if ( v4 != -2147023156 )
          break;
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
        {
          pvData = -2147023156;
          p_pcbData = (DWORD *)&pvData;
          v22 = 4;
          McGenEventWrite_EventWriteTransfer(
            v12,
            EnterpriseDiagnosticDcSvcRpcServerInterfaceGroupActivationFailedDuplicateEndPoints,
            v13,
            2,
            v20);
        }
        Sleep(0xBB8u);
      }
    }
    else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
    {
      pvData = v4;
      p_pcbData = (DWORD *)&pvData;
      v22 = 4;
      McGenEventWrite_EventWriteTransfer(v8, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupCreateFailure, v9, 2, v20);
    }
  }
  if ( !v0 || !pcbData )
    goto LABEL_7;
  FreeTransientObjectSecurityDescriptor(v0);
LABEL_8:
  if ( v16 )
    FreeTransientObjectSecurityDescriptor(v16);
  if ( v17 )
    FreeTransientObjectSecurityDescriptor(v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007b9c  push    rbp
0x180007b9e  push    rbx
0x180007b9f  push    rsi
0x180007ba0  push    rdi
0x180007ba1  push    r12
0x180007ba3  push    r14
0x180007ba5  lea     rbp, [rsp-2Fh]
0x180007baa  sub     rsp, 0A8h
0x180007bb1  mov     rax, cs:__security_cookie
0x180007bb8  xor     rax, rsp
0x180007bbb  mov     [rbp+57h+var_40], rax
0x180007bbf  xor     edi, edi
0x180007bc1  mov     [rbp+57h+var_80], 0
0x180007bc9  lea     rax, [rbp+57h+hKey]
0x180007bcd  mov     [rbp+57h+var_78], 0
0x180007bd5  mov     rsi, 0FFFFFFFF80000002h
0x180007bdc  mov     [rbp+57h+var_68], rdi
0x180007be0  mov     r9d, 20019h; samDesired
0x180007be6  mov     [rbp+57h+hKey], rdi
0x180007bea  lea     ebx, [rdi+78h]
0x180007bed  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180007bf2  lea     r12d, [rdi+4]
0x180007bf6  mov     [rbp+57h+var_90], ebx
0x180007bf9  xor     r8d, r8d; ulOptions
0x180007bfc  mov     [rbp+57h+var_88], r12d
0x180007c00  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\dc"...
0x180007c07  mov     rcx, rsi; hKey
0x180007c0a  call    cs:__imp_RegOpenKeyExW
0x180007c10  test    eax, eax
0x180007c12  jnz     short loc_180007C4D
0x180007c14  lea     rax, [rbp+57h+var_88]
0x180007c18  mov     rcx, rsi; hkey
0x180007c1b  mov     [rsp+0D0h+pcbData], rax; pcbData
0x180007c20  lea     r9d, [rdi+10h]; dwFlags
0x180007c24  lea     rax, [rbp+57h+var_90]
0x180007c28  mov     [rsp+0D0h+pvData], rax; pvData
0x180007c2d  lea     r8, Value; "IdleTimeout(sec)"
0x180007c34  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\dc"...
0x180007c3b  mov     [rsp+0D0h+phkResult], rdi; pdwType
0x180007c40  call    cs:__imp_RegGetValueW
0x180007c46  test    eax, eax
0x180007c48  jz      short loc_180007C4D
0x180007c4a  mov     [rbp+57h+var_90], ebx
0x180007c4d  mov     rcx, [rbp+57h+hKey]; hKey
0x180007c51  call    cs:__imp_RegCloseKey
0x180007c57  mov     [rbp+57h+var_88], edi
0x180007c5a  call    ?CmLockSvcInitialize@@YAJXZ; CmLockSvcInitialize(void)
0x180007c5f  mov     ebx, eax
0x180007c61  test    eax, eax
0x180007c63  jns     short loc_180007CDD
0x180007c65  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180007c6c  jz      short loc_180007C98
0x180007c6e  mov     [rbp+57h+var_88], eax
0x180007c71  lea     rdx, EnterpriseDiagnosticsConfigManagerLockServiceBindingFailed
0x180007c78  lea     rax, [rbp+57h+var_88]
0x180007c7c  mov     [rbp+57h+var_48], r12
0x180007c80  mov     [rbp+57h+var_50], rax
0x180007c84  mov     r9d, 2
0x180007c8a  lea     rax, [rbp+57h+var_60]
0x180007c8e  mov     [rsp+0D0h+phkResult], rax
0x180007c93  call    McGenEventWrite_EventWriteTransfer
0x180007c98  mov     rcx, rdi; hMem
0x180007c9b  call    cs:__imp_LocalFree
0x180007ca1  mov     rcx, [rbp+57h+var_80]
0x180007ca5  test    rcx, rcx
0x180007ca8  jz      short loc_180007CB0
0x180007caa  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180007cb0  mov     rcx, [rbp+57h+var_78]
0x180007cb4  test    rcx, rcx
0x180007cb7  jz      short loc_180007CBF
0x180007cb9  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180007cbf  mov     eax, ebx
0x180007cc1  mov     rcx, [rbp+57h+var_40]
0x180007cc5  xor     rcx, rsp; StackCookie
0x180007cc8  call    __security_check_cookie
0x180007ccd  add     rsp, 0A8h
0x180007cd4  pop     r14
0x180007cd6  pop     r12
0x180007cd8  pop     rdi
0x180007cd9  pop     rsi
0x180007cda  pop     rbx
0x180007cdb  pop     rbp
0x180007cdc  retn
0x180007cdd  lea     r8, [rbp+57h+var_80]
0x180007ce1  mov     ecx, 8
0x180007ce6  lea     rdx, aDefaultrpcacce; "DefaultRpcAccess"
0x180007ced  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180007cf3  mov     esi, 80000000h
0x180007cf8  mov     r14d, 0C0000034h
0x180007cfe  mov     ebx, eax
0x180007d00  add     eax, esi
0x180007d02  test    esi, eax
0x180007d04  jnz     short loc_180007D0B
0x180007d06  cmp     ebx, r14d
0x180007d09  jnz     short loc_180007C98
0x180007d0b  lea     r8, [rbp+57h+var_78]
0x180007d0f  mov     ecx, 9
0x180007d14  lea     rdx, aDmorchestrator; "DMOrchestratorRpc\\Interface"
0x180007d1b  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180007d21  mov     ebx, eax
0x180007d23  add     eax, esi
0x180007d25  test    esi, eax
0x180007d27  jnz     short loc_180007D32
0x180007d29  cmp     ebx, r14d
0x180007d2c  jnz     loc_180007C98
0x180007d32  mov     rax, [rbp+57h+var_78]
0x180007d36  lea     r9, [rbp+57h+var_68]
0x180007d3a  mov     cs:qword_18001B288, rax
0x180007d41  lea     r8, c_szCmLockServiceDcRpcIface; "CmLockSvcDcRpc\\Interface"
0x180007d48  mov     rax, [rbp+57h+var_80]
0x180007d4c  lea     rdx, c_szCmLockServiceDcRpcUapIface; "CmLockSvcDcRpcUap\\Interface"
0x180007d53  mov     cs:qword_18001B018, rax
0x180007d5a  mov     ecx, 9
0x180007d5f  lea     rax, [rbp+57h+var_88]
0x180007d63  mov     [rsp+0D0h+phkResult], rax
0x180007d68  call    ?DmGetMergedSecurityDescriptorForTransientObject@@YAJW4TransientObject_Type@@PEBG1PEAPEAXPEAH@Z; DmGetMergedSecurityDescriptorForTransientObject(TransientObject_Type,ushort const *,ushort const *,void * *,int *)
0x180007d6d  mov     rdi, [rbp+57h+var_68]
0x180007d71  mov     ebx, eax
0x180007d73  test    eax, eax
0x180007d75  js      loc_180007EB1
0x180007d7b  mov     r9d, 1
0x180007d81  mov     cs:qword_18001B2D8, rdi
0x180007d88  lea     rax, qword_18001B6D8
0x180007d8f  mov     [rsp+0D0h+var_98], rax
0x180007d94  lea     r8, ?g_SharedRpcEndpointList@@3PAURPC_ENDPOINT_TEMPLATEW@@A; RPC_ENDPOINT_TEMPLATEW near * g_SharedRpcEndpointList
0x180007d9b  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007da2  mov     [rsp+0D0h+pcbData], 0
0x180007dab  mov     [rsp+0D0h+pvData], rax
0x180007db0  lea     esi, [r9+1]
0x180007db4  mov     eax, [rbp+57h+var_90]
0x180007db7  lea     rcx, ?g_SharedRpcInterfaceList@@3PAURPC_INTERFACE_TEMPLATEW@@A; RPC_INTERFACE_TEMPLATEW near * g_SharedRpcInterfaceList
0x180007dbe  mov     edx, esi
0x180007dc0  mov     dword ptr [rsp+0D0h+phkResult], eax
0x180007dc4  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x180007dca  mov     ebx, eax
0x180007dcc  test    eax, eax
0x180007dce  jle     short loc_180007DD9
0x180007dd0  movzx   ebx, ax
0x180007dd3  or      ebx, 80070000h
0x180007dd9  test    ebx, ebx
0x180007ddb  jns     short loc_180007E16
0x180007ddd  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180007de4  jz      loc_180007EB1
0x180007dea  lea     rax, [rbp+57h+var_90]
0x180007dee  mov     [rbp+57h+var_90], ebx
0x180007df1  mov     [rbp+57h+var_50], rax
0x180007df5  lea     rdx, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupCreateFailure
0x180007dfc  lea     rax, [rbp+57h+var_60]
0x180007e00  mov     [rbp+57h+var_48], r12
0x180007e04  mov     r9d, esi
0x180007e07  mov     [rsp+0D0h+phkResult], rax
0x180007e0c  call    McGenEventWrite_EventWriteTransfer
0x180007e11  jmp     loc_180007EB1
0x180007e16  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, r12b
0x180007e1d  jz      short loc_180007E46
0x180007e1f  lea     rax, [rbp+57h+var_90]
0x180007e23  mov     [rbp+57h+var_90], ebx
0x180007e26  mov     [rbp+57h+var_50], rax
0x180007e2a  lea     rdx, EnterpriseDiagnosticsDcSvcRpcServerInterfaceGroupCreateSuccess
0x180007e31  lea     rax, [rbp+57h+var_60]
0x180007e35  mov     [rbp+57h+var_48], r12
0x180007e39  mov     r9d, esi
0x180007e3c  mov     [rsp+0D0h+phkResult], rax
0x180007e41  call    McGenEventWrite_EventWriteTransfer
0x180007e46  xor     r14d, r14d
0x180007e49  mov     rcx, cs:qword_18001B6D8
0x180007e50  call    cs:__imp_RpcServerInterfaceGroupActivate
0x180007e56  mov     ebx, eax
0x180007e58  test    eax, eax
0x180007e5a  jle     short loc_180007E65
0x180007e5c  movzx   ebx, ax
0x180007e5f  or      ebx, 80070000h
0x180007e65  cmp     ebx, 800706CCh
0x180007e6b  jnz     short loc_180007EB1
0x180007e6d  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180007e74  jz      short loc_180007E9D
0x180007e76  lea     rax, [rbp+57h+var_90]
0x180007e7a  mov     [rbp+57h+var_90], ebx
0x180007e7d  mov     [rbp+57h+var_50], rax
0x180007e81  lea     rdx, EnterpriseDiagnosticDcSvcRpcServerInterfaceGroupActivationFailedDuplicateEndPoints
0x180007e88  lea     rax, [rbp+57h+var_60]
0x180007e8c  mov     [rbp+57h+var_48], r12
0x180007e90  mov     r9d, esi
0x180007e93  mov     [rsp+0D0h+phkResult], rax
0x180007e98  call    McGenEventWrite_EventWriteTransfer
0x180007e9d  mov     ecx, 0BB8h; dwMilliseconds
0x180007ea2  call    cs:__imp_Sleep
0x180007ea8  inc     r14d
0x180007eab  cmp     r14d, 5
0x180007eaf  jl      short loc_180007E49
0x180007eb1  test    rdi, rdi
0x180007eb4  jz      loc_180007C98
0x180007eba  cmp     [rbp+57h+var_88], 0
0x180007ebe  jz      loc_180007C98
0x180007ec4  mov     rcx, rdi
0x180007ec7  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180007ecd  jmp     loc_180007CA1
```
