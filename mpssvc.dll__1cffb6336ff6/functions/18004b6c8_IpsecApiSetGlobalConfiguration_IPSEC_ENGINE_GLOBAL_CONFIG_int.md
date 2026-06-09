# IpsecApiSetGlobalConfiguration(_IPSEC_ENGINE_GLOBAL_CONFIG_ *,int)

- ea: `0x18004b6c8`
- end: `0x18004ba96`
- name: `?IpsecApiSetGlobalConfiguration@@YAKPEAU_IPSEC_ENGINE_GLOBAL_CONFIG_@@H@Z`
- size: `974`
- prototype: `unsigned int __fastcall(struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004b560`

## callees

- `0x1800093b0`
- `0x18004b6c8`
- `0x18004c284`
- `0x18004c368`
- `0x18005a9cc`
- `0x18006b2b8`
- `0x18006f520`
- `0x18008d1cc`
- `0x1800acd1c`
- `0x1800d48ec`
- `0x1800d71f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba4c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b74e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b7ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b85b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b8da`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b74e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b7ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b85b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b8da`

## string_xrefs

- `0x18004b800`: `IpsecApiSetGlobalConfiguration`
- `0x18004b890`: `IpsecApiSetGlobalConfiguration`
- `0x18004ba60`: `IpsecApiSetGlobalConfiguration`

## pseudocode

```c
unsigned int __fastcall IpsecApiSetGlobalConfiguration(
        struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // ebx
  int v5; // r14d
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  const WCHAR *v11; // rcx
  signed int LastError; // eax
  int v13; // r8d
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  signed int v16; // eax
  __int64 v17; // rdx
  const WCHAR *v18; // rcx
  signed int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // edx
  unsigned int v22; // r8d
  const WCHAR *v23; // rcx
  signed int v24; // eax
  __int64 v25; // rdx
  int v26; // eax
  int v27; // edi
  int v28; // edx
  unsigned int v29; // eax
  unsigned int v31; // [rsp+30h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR v34; // [rsp+48h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR v35; // [rsp+50h] [rbp-10h] BYREF

  v4 = 0;
  v5 = a2;
  SecurityDescriptor = 0;
  hMem = 0;
  v34 = 0;
  v35 = 0;
  if ( !gvBfeEngineHandle )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  PrintGlobalConfig(a1, (struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *)&gvIpsGlobalConfig);
  if ( *((_DWORD *)a1 + 3) >= 0x10u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9, v10);
  v11 = (const WCHAR *)*((_QWORD *)a1 + 4);
  if ( v11 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(v11, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( v5 )
    {
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = (unsigned int)LastError;
      FwEventInitConfigReadFailure(12, v14);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      FwTelemetryEventWriteInitGlobalConfigFailure(12, (unsigned int)v4);
      v4 = 0;
    }
    else if ( LastError )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sdD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          v13,
          (unsigned int)"IpsecApiSetGlobalConfiguration",
          101,
          LastError);
      goto LABEL_61;
    }
  }
  v15 = (const WCHAR *)*((_QWORD *)a1 + 5);
  if ( v15 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(v15, 1u, &hMem, 0) )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v5 )
    {
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      else
        v17 = (unsigned int)v16;
      FwEventInitConfigReadFailure(13, v17);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      FwTelemetryEventWriteInitGlobalConfigFailure(13, (unsigned int)v4);
      v4 = 0;
    }
    else if ( v16 )
    {
      v21 = 367;
      goto LABEL_34;
    }
  }
  v18 = (const WCHAR *)*((_QWORD *)a1 + 7);
  if ( v18 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(v18, 1u, &v34, 0) )
  {
    v19 = GetLastError();
    v4 = v19;
    if ( v5 )
    {
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      else
        v20 = (unsigned int)v19;
      FwEventInitConfigReadFailure(15, v20);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      FwTelemetryEventWriteInitGlobalConfigFailure(15, (unsigned int)v4);
      v4 = 0;
    }
    else if ( v19 )
    {
      v21 = 377;
      goto LABEL_34;
    }
  }
  v23 = (const WCHAR *)*((_QWORD *)a1 + 8);
  if ( !v23 || ConvertStringSecurityDescriptorToSecurityDescriptorW(v23, 1u, &v35, 0) )
    goto LABEL_51;
  v24 = GetLastError();
  v4 = v24;
  if ( !v5 )
  {
    if ( !v24 )
      goto LABEL_51;
    v21 = 387;
LABEL_34:
    v22 = v4;
LABEL_35:
    IpsTraceError("IpsecApiSetGlobalConfiguration", v21, v22, 0);
LABEL_61:
    LocalFree(SecurityDescriptor);
    LocalFree(hMem);
    LocalFree(v34);
    LocalFree(v35);
    return IpsReturnError("IpsecApiSetGlobalConfiguration", 0x1C3u, v4, 1, 0);
  }
  if ( v24 > 0 )
    v25 = (unsigned __int16)v24 | 0x80070000;
  else
    v25 = (unsigned int)v24;
  FwEventInitConfigReadFailure(16, v25);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  FwTelemetryEventWriteInitGlobalConfigFailure(16, (unsigned int)v4);
  v4 = 0;
LABEL_51:
  if ( gvIpsecCSRuleCount )
  {
    v26 = *(&gvIpsGlobalConfig + 3);
    v27 = *(&gvIpsGlobalConfig + 3) ^ *((_DWORD *)a1 + 3);
    v28 = *((_DWORD *)a1 + 3) & v27;
    if ( v28 )
    {
      v29 = BfeExemptionFiltersCreate((__int64)v23, v28);
      v4 = v29;
      if ( v29 )
      {
        v22 = v29;
        v21 = 410;
        goto LABEL_35;
      }
      v26 = *(&gvIpsGlobalConfig + 3);
    }
    v31 = v26 & v27;
    if ( (v26 & v27) != 0 )
      BfeExemptionFiltersDelete(3, 1, &v31);
  }
  gvIpsGlobalConfig = *(_OWORD *)a1;
  xmmword_18012C890 = *((_OWORD *)a1 + 1);
  xmmword_18012C8A0 = *((_OWORD *)a1 + 2);
  xmmword_18012C8B0 = *((_OWORD *)a1 + 3);
  qword_18012C8C0 = *((_QWORD *)a1 + 8);
  LocalFree(gvIpsecTunnelRemoteMachineAuthz);
  gvIpsecTunnelRemoteMachineAuthz = SecurityDescriptor;
  LocalFree(gvIpsecTunnelRemoteUserAuthz);
  gvIpsecTunnelRemoteUserAuthz = hMem;
  LocalFree(gvIpsecTransportRemoteMachineAuthz);
  gvIpsecTransportRemoteMachineAuthz = v34;
  LocalFree(gvIpsecTransportRemoteUserAuthz);
  gvIpsecTransportRemoteUserAuthz = v35;
  return IpsReturnError("IpsecApiSetGlobalConfiguration", 0x1C3u, v4, 1, 0);
}

```

## disassembly

```asm
0x18004b6c8  mov     [rsp-28h+arg_8], rbx
0x18004b6cd  mov     [rsp-28h+arg_10], rsi
0x18004b6d2  push    rbp
0x18004b6d3  push    rdi
0x18004b6d4  push    r12
0x18004b6d6  push    r13
0x18004b6d8  push    r14
0x18004b6da  mov     rbp, rsp
0x18004b6dd  sub     rsp, 60h
0x18004b6e1  mov     rax, cs:__security_cookie
0x18004b6e8  xor     rax, rsp
0x18004b6eb  mov     [rbp+var_8], rax
0x18004b6ef  xor     ebx, ebx
0x18004b6f1  mov     r14d, edx
0x18004b6f4  cmp     cs:?gvBfeEngineHandle@@3PEAXEA, rbx; void * gvBfeEngineHandle
0x18004b6fb  mov     rsi, rcx
0x18004b6fe  mov     [rbp+SecurityDescriptor], rbx
0x18004b702  mov     [rbp+hMem], rbx
0x18004b706  mov     [rbp+var_18], rbx
0x18004b70a  mov     [rbp+var_10], rbx
0x18004b70e  jnz     short loc_18004B715
0x18004b710  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004b715  lea     rdx, ?gvIpsGlobalConfig@@3U_IPSEC_ENGINE_GLOBAL_CONFIG_@@A; struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *
0x18004b71c  mov     rcx, rsi; struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *
0x18004b71f  call    ?PrintGlobalConfig@@YAXPEAU_IPSEC_ENGINE_GLOBAL_CONFIG_@@0@Z; PrintGlobalConfig(_IPSEC_ENGINE_GLOBAL_CONFIG_ *,_IPSEC_ENGINE_GLOBAL_CONFIG_ *)
0x18004b724  cmp     dword ptr [rsi+0Ch], 10h
0x18004b728  jb      short loc_18004B72F
0x18004b72a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004b72f  mov     rcx, [rsi+20h]; StringSecurityDescriptor
0x18004b733  mov     r12d, 80070000h
0x18004b739  mov     r13d, 1
0x18004b73f  test    rcx, rcx
0x18004b742  jz      short loc_18004B796
0x18004b744  xor     r9d, r9d; SecurityDescriptorSize
0x18004b747  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004b74b  mov     edx, r13d; StringSDRevision
0x18004b74e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004b754  test    eax, eax
0x18004b756  jnz     short loc_18004B796
0x18004b758  call    cs:__imp_GetLastError
0x18004b75e  mov     ebx, eax
0x18004b760  test    r14d, r14d
0x18004b763  jz      short loc_18004B7D7
0x18004b765  movzx   edi, bx
0x18004b768  test    eax, eax
0x18004b76a  jg      short loc_18004B770
0x18004b76c  mov     edx, eax
0x18004b76e  jmp     short loc_18004B775
0x18004b770  mov     edx, edi
0x18004b772  or      edx, r12d
0x18004b775  mov     ecx, 0Ch
0x18004b77a  call    FwEventInitConfigReadFailure
0x18004b77f  test    ebx, ebx
0x18004b781  jle     short loc_18004B788
0x18004b783  mov     ebx, edi
0x18004b785  or      ebx, r12d
0x18004b788  mov     edx, ebx
0x18004b78a  mov     ecx, 0Ch
0x18004b78f  call    FwTelemetryEventWriteInitGlobalConfigFailure
0x18004b794  xor     ebx, ebx
0x18004b796  mov     rcx, [rsi+28h]; StringSecurityDescriptor
0x18004b79a  test    rcx, rcx
0x18004b79d  jz      loc_18004B848
0x18004b7a3  xor     r9d, r9d; SecurityDescriptorSize
0x18004b7a6  lea     r8, [rbp+hMem]; SecurityDescriptor
0x18004b7aa  mov     edx, r13d; StringSDRevision
0x18004b7ad  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004b7b3  test    eax, eax
0x18004b7b5  jnz     loc_18004B848
0x18004b7bb  call    cs:__imp_GetLastError
0x18004b7c1  mov     ebx, eax
0x18004b7c3  test    r14d, r14d
0x18004b7c6  jz      loc_18004B881
0x18004b7cc  movzx   edi, bx
0x18004b7cf  test    eax, eax
0x18004b7d1  jg      short loc_18004B822
0x18004b7d3  mov     edx, eax
0x18004b7d5  jmp     short loc_18004B827
0x18004b7d7  test    ebx, ebx
0x18004b7d9  jz      short loc_18004B796
0x18004b7db  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b7e2  lea     rax, WPP_GLOBAL_Control
0x18004b7e9  cmp     rcx, rax
0x18004b7ec  jz      loc_18004BA2A
0x18004b7f2  test    [rcx+1Ch], r13b
0x18004b7f6  jz      loc_18004BA2A
0x18004b7fc  mov     rcx, [rcx+10h]
0x18004b800  lea     r9, aIpsecapisetglo; "IpsecApiSetGlobalConfiguration"
0x18004b807  mov     edx, 0Eh
0x18004b80c  mov     [rsp+60h+var_38], ebx
0x18004b810  mov     [rsp+60h+var_40], 165h
0x18004b818  call    WPP_SF_sdD
0x18004b81d  jmp     loc_18004BA2A
0x18004b822  mov     edx, edi
0x18004b824  or      edx, r12d
0x18004b827  mov     ecx, 0Dh
0x18004b82c  call    FwEventInitConfigReadFailure
0x18004b831  test    ebx, ebx
0x18004b833  jle     short loc_18004B83A
0x18004b835  mov     ebx, edi
0x18004b837  or      ebx, r12d
0x18004b83a  mov     edx, ebx
0x18004b83c  mov     ecx, 0Dh
0x18004b841  call    FwTelemetryEventWriteInitGlobalConfigFailure
0x18004b846  xor     ebx, ebx
0x18004b848  mov     rcx, [rsi+38h]; StringSecurityDescriptor
0x18004b84c  test    rcx, rcx
0x18004b84f  jz      short loc_18004B8C7
0x18004b851  xor     r9d, r9d; SecurityDescriptorSize
0x18004b854  lea     r8, [rbp+var_18]; SecurityDescriptor
0x18004b858  mov     edx, r13d; StringSDRevision
0x18004b85b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004b861  test    eax, eax
0x18004b863  jnz     short loc_18004B8C7
0x18004b865  call    cs:__imp_GetLastError
0x18004b86b  mov     ebx, eax
0x18004b86d  test    r14d, r14d
0x18004b870  jz      loc_18004B8FC
0x18004b876  movzx   edi, bx
0x18004b879  test    eax, eax
0x18004b87b  jg      short loc_18004B8A1
0x18004b87d  mov     edx, eax
0x18004b87f  jmp     short loc_18004B8A6
0x18004b881  test    ebx, ebx
0x18004b883  jz      short loc_18004B848
0x18004b885  mov     edx, 16Fh; unsigned int
0x18004b88a  mov     r8d, ebx; unsigned int
0x18004b88d  xor     r9d, r9d; int
0x18004b890  lea     rcx, aIpsecapisetglo; "IpsecApiSetGlobalConfiguration"
0x18004b897  call    ?IpsTraceError@@YAXPEBDKKH@Z; IpsTraceError(char const *,ulong,ulong,int)
0x18004b89c  jmp     loc_18004BA2A
0x18004b8a1  mov     edx, edi
0x18004b8a3  or      edx, r12d
0x18004b8a6  mov     ecx, 0Fh
0x18004b8ab  call    FwEventInitConfigReadFailure
0x18004b8b0  test    ebx, ebx
0x18004b8b2  jle     short loc_18004B8B9
0x18004b8b4  mov     ebx, edi
0x18004b8b6  or      ebx, r12d
0x18004b8b9  mov     edx, ebx
0x18004b8bb  mov     ecx, 0Fh
0x18004b8c0  call    FwTelemetryEventWriteInitGlobalConfigFailure
0x18004b8c5  xor     ebx, ebx
0x18004b8c7  mov     rcx, [rsi+40h]; StringSecurityDescriptor
0x18004b8cb  test    rcx, rcx
0x18004b8ce  jz      short loc_18004B92F
0x18004b8d0  xor     r9d, r9d; SecurityDescriptorSize
0x18004b8d3  lea     r8, [rbp+var_10]; SecurityDescriptor
0x18004b8d7  mov     edx, r13d; StringSDRevision
0x18004b8da  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004b8e0  test    eax, eax
0x18004b8e2  jnz     short loc_18004B92F
0x18004b8e4  call    cs:__imp_GetLastError
0x18004b8ea  mov     ebx, eax
0x18004b8ec  test    r14d, r14d
0x18004b8ef  jz      short loc_18004B962
0x18004b8f1  movzx   edi, bx
0x18004b8f4  test    eax, eax
0x18004b8f6  jg      short loc_18004B907
0x18004b8f8  mov     edx, eax
0x18004b8fa  jmp     short loc_18004B90C
0x18004b8fc  test    ebx, ebx
0x18004b8fe  jz      short loc_18004B8C7
0x18004b900  mov     edx, 179h
0x18004b905  jmp     short loc_18004B88A
0x18004b907  mov     edx, edi
0x18004b909  or      edx, r12d
0x18004b90c  mov     r14d, 10h
0x18004b912  mov     ecx, r14d
0x18004b915  call    FwEventInitConfigReadFailure
0x18004b91a  test    ebx, ebx
0x18004b91c  jle     short loc_18004B923
0x18004b91e  mov     ebx, edi
0x18004b920  or      ebx, r12d
0x18004b923  mov     edx, ebx
0x18004b925  mov     ecx, r14d
0x18004b928  call    FwTelemetryEventWriteInitGlobalConfigFailure
0x18004b92d  xor     ebx, ebx
0x18004b92f  cmp     cs:?gvIpsecCSRuleCount@@3KA, r13d; ulong gvIpsecCSRuleCount
0x18004b936  jb      short loc_18004B98E
0x18004b938  mov     edi, [rsi+0Ch]
0x18004b93b  mov     eax, dword ptr cs:?gvIpsGlobalConfig@@3U_IPSEC_ENGINE_GLOBAL_CONFIG_@@A+0Ch; _IPSEC_ENGINE_GLOBAL_CONFIG_ gvIpsGlobalConfig
0x18004b941  xor     edi, eax
0x18004b943  mov     edx, edi
0x18004b945  and     edx, [rsi+0Ch]; unsigned int
0x18004b948  jz      short loc_18004B976
0x18004b94a  call    ?BfeExemptionFiltersCreate@@YAKHK@Z; BfeExemptionFiltersCreate(int,ulong)
0x18004b94f  mov     ebx, eax
0x18004b951  test    eax, eax
0x18004b953  jz      short loc_18004B970
0x18004b955  mov     r8d, eax
0x18004b958  mov     edx, 19Ah
0x18004b95d  jmp     loc_18004B88D
0x18004b962  test    ebx, ebx
0x18004b964  jz      short loc_18004B92F
0x18004b966  mov     edx, 183h
0x18004b96b  jmp     loc_18004B88A
0x18004b970  mov     eax, dword ptr cs:?gvIpsGlobalConfig@@3U_IPSEC_ENGINE_GLOBAL_CONFIG_@@A+0Ch; _IPSEC_ENGINE_GLOBAL_CONFIG_ gvIpsGlobalConfig
0x18004b976  and     edi, eax
0x18004b978  mov     [rbp+var_30], edi
0x18004b97b  jz      short loc_18004B98E
0x18004b97d  lea     r8, [rbp+var_30]; unsigned int *
0x18004b981  mov     edx, r13d; unsigned int
0x18004b984  mov     ecx, 3; unsigned int
0x18004b989  call    ?BfeExemptionFiltersDelete@@YAXKKPEAK@Z; BfeExemptionFiltersDelete(ulong,ulong,ulong *)
0x18004b98e  movaps  xmm0, xmmword ptr [rsi]
0x18004b991  mov     rcx, cs:?gvIpsecTunnelRemoteMachineAuthz@@3PEAXEA; hMem
0x18004b998  movaps  cs:?gvIpsGlobalConfig@@3U_IPSEC_ENGINE_GLOBAL_CONFIG_@@A, xmm0; _IPSEC_ENGINE_GLOBAL_CONFIG_ gvIpsGlobalConfig
0x18004b99f  movaps  xmm1, xmmword ptr [rsi+10h]
0x18004b9a3  movaps  cs:xmmword_18012C890, xmm1
0x18004b9aa  movaps  xmm0, xmmword ptr [rsi+20h]
0x18004b9ae  movaps  cs:xmmword_18012C8A0, xmm0
0x18004b9b5  movaps  xmm1, xmmword ptr [rsi+30h]
0x18004b9b9  movaps  cs:xmmword_18012C8B0, xmm1
0x18004b9c0  movsd   xmm0, qword ptr [rsi+40h]
0x18004b9c5  movsd   cs:qword_18012C8C0, xmm0
0x18004b9cd  call    cs:__imp_LocalFree
0x18004b9d3  mov     rax, [rbp+SecurityDescriptor]
0x18004b9d7  mov     rcx, cs:?gvIpsecTunnelRemoteUserAuthz@@3PEAXEA; hMem
0x18004b9de  mov     cs:?gvIpsecTunnelRemoteMachineAuthz@@3PEAXEA, rax; void * gvIpsecTunnelRemoteMachineAuthz
0x18004b9e5  call    cs:__imp_LocalFree
0x18004b9eb  mov     rax, [rbp+hMem]
0x18004b9ef  mov     rcx, cs:?gvIpsecTransportRemoteMachineAuthz@@3PEAXEA; hMem
0x18004b9f6  mov     cs:?gvIpsecTunnelRemoteUserAuthz@@3PEAXEA, rax; void * gvIpsecTunnelRemoteUserAuthz
0x18004b9fd  call    cs:__imp_LocalFree
0x18004ba03  mov     rax, [rbp+var_18]
0x18004ba07  mov     rcx, cs:?gvIpsecTransportRemoteUserAuthz@@3PEAXEA; hMem
0x18004ba0e  mov     cs:?gvIpsecTransportRemoteMachineAuthz@@3PEAXEA, rax; void * gvIpsecTransportRemoteMachineAuthz
0x18004ba15  call    cs:__imp_LocalFree
0x18004ba1b  mov     rax, [rbp+var_10]
0x18004ba1f  mov     cs:?gvIpsecTransportRemoteUserAuthz@@3PEAXEA, rax; void * gvIpsecTransportRemoteUserAuthz
0x18004ba26  test    ebx, ebx
0x18004ba28  jz      short loc_18004BA52
0x18004ba2a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18004ba2e  call    cs:__imp_LocalFree
0x18004ba34  mov     rcx, [rbp+hMem]; hMem
0x18004ba38  call    cs:__imp_LocalFree
0x18004ba3e  mov     rcx, [rbp+var_18]; hMem
0x18004ba42  call    cs:__imp_LocalFree
0x18004ba48  mov     rcx, [rbp+var_10]; hMem
0x18004ba4c  call    cs:__imp_LocalFree
0x18004ba52  mov     r9d, r13d; int
0x18004ba55  mov     [rsp+60h+var_40], 0; int
0x18004ba5d  mov     r8d, ebx; unsigned int
0x18004ba60  lea     rcx, aIpsecapisetglo; "IpsecApiSetGlobalConfiguration"
0x18004ba67  mov     edx, 1C3h; unsigned int
0x18004ba6c  call    ?IpsReturnError@@YAKPEBDKKHH@Z; IpsReturnError(char const *,ulong,ulong,int,int)
0x18004ba71  mov     rcx, [rbp+var_8]
0x18004ba75  xor     rcx, rsp; StackCookie
0x18004ba78  call    __security_check_cookie
0x18004ba7d  lea     r11, [rsp+60h+var_s0]
0x18004ba82  mov     rbx, [r11+38h]
0x18004ba86  mov     rsi, [r11+40h]
0x18004ba8a  mov     rsp, r11
0x18004ba8d  pop     r14
0x18004ba8f  pop     r13
0x18004ba91  pop     r12
0x18004ba93  pop     rdi
0x18004ba94  pop     rbp
0x18004ba95  retn
```
