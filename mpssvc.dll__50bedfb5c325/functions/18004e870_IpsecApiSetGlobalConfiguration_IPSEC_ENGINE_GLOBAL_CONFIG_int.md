# IpsecApiSetGlobalConfiguration(_IPSEC_ENGINE_GLOBAL_CONFIG_ *,int)

- ea: `0x18004e870`
- end: `0x18004eca6`
- name: `?IpsecApiSetGlobalConfiguration@@YAKPEAU_IPSEC_ENGINE_GLOBAL_CONFIG_@@H@Z`
- size: `1078`
- prototype: `unsigned int __fastcall(struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004e6f0`

## callees

- `0x1800089bc`
- `0x18004e870`
- `0x18004f4ac`
- `0x18004f594`
- `0x18005fa54`
- `0x18006e384`
- `0x1800729c0`
- `0x180091ab4`
- `0x1800b32d0`
- `0x1800db0b4`
- `0x1800dd578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eaba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eaba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ebac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ebca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ebe8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ebac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ebca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ebe8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ec55`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004e8f6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004e961`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004ea1f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004eaaa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004e8f6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004e961`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004ea1f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004eaaa`

## string_xrefs

- `0x18004e9c0`: `IpsecApiSetGlobalConfiguration`
- `0x18004ea60`: `IpsecApiSetGlobalConfiguration`
- `0x18004ec6f`: `IpsecApiSetGlobalConfiguration`

## pseudocode

```c
unsigned int __fastcall IpsecApiSetGlobalConfiguration(struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *a1, int a2)
{
  int v2; // ebx
  __int64 v5; // rcx
  const WCHAR *v6; // rcx
  signed int LastError; // eax
  int v8; // r8d
  __int64 v9; // rdx
  const WCHAR *v10; // rcx
  signed int v11; // eax
  __int64 v12; // rdx
  const WCHAR *v13; // rcx
  signed int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // edx
  unsigned int v17; // r8d
  const WCHAR *v18; // rcx
  signed int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  int v22; // edi
  unsigned int v23; // eax
  unsigned int v25; // [rsp+30h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR v28; // [rsp+48h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR v29; // [rsp+50h] [rbp-10h] BYREF

  v2 = 0;
  SecurityDescriptor = 0;
  hMem = 0;
  v28 = 0;
  v29 = 0;
  if ( !gvBfeEngineHandle )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  PrintGlobalConfig(a1, (struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *)&gvIpsGlobalConfig);
  if ( *((_DWORD *)a1 + 3) >= 0x10u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  v6 = (const WCHAR *)*((_QWORD *)a1 + 4);
  if ( v6 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(v6, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( a2 )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = (unsigned int)LastError;
      FwEventInitConfigReadFailure(12, v9);
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      FwTelemetryEventWriteInitGlobalConfigFailure(12, (unsigned int)v2);
      v2 = 0;
    }
    else if ( LastError )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sdD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          v8,
          (unsigned int)"IpsecApiSetGlobalConfiguration",
          59,
          LastError);
      goto LABEL_61;
    }
  }
  v10 = (const WCHAR *)*((_QWORD *)a1 + 5);
  if ( v10 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(v10, 1u, &hMem, 0) )
  {
    v11 = GetLastError();
    v2 = v11;
    if ( a2 )
    {
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      else
        v12 = (unsigned int)v11;
      FwEventInitConfigReadFailure(13, v12);
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      FwTelemetryEventWriteInitGlobalConfigFailure(13, (unsigned int)v2);
      v2 = 0;
    }
    else if ( v11 )
    {
      v16 = 325;
      goto LABEL_34;
    }
  }
  v13 = (const WCHAR *)*((_QWORD *)a1 + 7);
  if ( v13 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(v13, 1u, &v28, 0) )
  {
    v14 = GetLastError();
    v2 = v14;
    if ( a2 )
    {
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      else
        v15 = (unsigned int)v14;
      FwEventInitConfigReadFailure(15, v15);
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      FwTelemetryEventWriteInitGlobalConfigFailure(15, (unsigned int)v2);
      v2 = 0;
    }
    else if ( v14 )
    {
      v16 = 335;
      goto LABEL_34;
    }
  }
  v18 = (const WCHAR *)*((_QWORD *)a1 + 8);
  if ( !v18 || ConvertStringSecurityDescriptorToSecurityDescriptorW(v18, 1u, &v29, 0) )
    goto LABEL_51;
  v19 = GetLastError();
  v2 = v19;
  if ( !a2 )
  {
    if ( !v19 )
      goto LABEL_51;
    v16 = 345;
LABEL_34:
    v17 = v2;
LABEL_35:
    IpsTraceError("IpsecApiSetGlobalConfiguration", v16, v17, 0);
LABEL_61:
    LocalFree(SecurityDescriptor);
    LocalFree(hMem);
    LocalFree(v28);
    LocalFree(v29);
    return IpsReturnError("IpsecApiSetGlobalConfiguration", 0x199u, v2, 1, 0);
  }
  if ( v19 > 0 )
    v20 = (unsigned __int16)v19 | 0x80070000;
  else
    v20 = (unsigned int)v19;
  FwEventInitConfigReadFailure(16, v20);
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  FwTelemetryEventWriteInitGlobalConfigFailure(16, (unsigned int)v2);
  v2 = 0;
LABEL_51:
  if ( gvIpsecCSRuleCount )
  {
    v21 = *(&gvIpsGlobalConfig + 3);
    v22 = *(&gvIpsGlobalConfig + 3) ^ *((_DWORD *)a1 + 3);
    if ( (*((_DWORD *)a1 + 3) & v22) != 0 )
    {
      v23 = BfeExemptionFiltersCreate((int)v18, *((_DWORD *)a1 + 3) & (*(&gvIpsGlobalConfig + 3) ^ *((_DWORD *)a1 + 3)));
      v2 = v23;
      if ( v23 )
      {
        v17 = v23;
        v16 = 368;
        goto LABEL_35;
      }
      v21 = *(&gvIpsGlobalConfig + 3);
    }
    v25 = v21 & v22;
    if ( (v21 & v22) != 0 )
      BfeExemptionFiltersDelete(3u, 1u, &v25);
  }
  gvIpsGlobalConfig = *(_OWORD *)a1;
  xmmword_180132A70 = *((_OWORD *)a1 + 1);
  xmmword_180132A80 = *((_OWORD *)a1 + 2);
  xmmword_180132A90 = *((_OWORD *)a1 + 3);
  qword_180132AA0 = *((_QWORD *)a1 + 8);
  LocalFree(gvIpsecTunnelRemoteMachineAuthz);
  gvIpsecTunnelRemoteMachineAuthz = SecurityDescriptor;
  LocalFree(gvIpsecTunnelRemoteUserAuthz);
  gvIpsecTunnelRemoteUserAuthz = hMem;
  LocalFree(gvIpsecTransportRemoteMachineAuthz);
  gvIpsecTransportRemoteMachineAuthz = v28;
  LocalFree(gvIpsecTransportRemoteUserAuthz);
  gvIpsecTransportRemoteUserAuthz = v29;
  return IpsReturnError("IpsecApiSetGlobalConfiguration", 0x199u, v2, 1, 0);
}

```

## disassembly

```asm
0x18004e870  mov     [rsp-28h+arg_8], rbx
0x18004e875  mov     [rsp-28h+arg_10], rsi
0x18004e87a  push    rbp
0x18004e87b  push    rdi
0x18004e87c  push    r12
0x18004e87e  push    r13
0x18004e880  push    r14
0x18004e882  mov     rbp, rsp
0x18004e885  sub     rsp, 60h
0x18004e889  mov     rax, cs:__security_cookie
0x18004e890  xor     rax, rsp
0x18004e893  mov     [rbp+var_8], rax
0x18004e897  xor     ebx, ebx
0x18004e899  mov     r14d, edx
0x18004e89c  cmp     cs:?gvBfeEngineHandle@@3PEAXEA, rbx; void * gvBfeEngineHandle
0x18004e8a3  mov     rsi, rcx
0x18004e8a6  mov     [rbp+SecurityDescriptor], rbx
0x18004e8aa  mov     [rbp+hMem], rbx
0x18004e8ae  mov     [rbp+var_18], rbx
0x18004e8b2  mov     [rbp+var_10], rbx
0x18004e8b6  jnz     short loc_18004E8BD
0x18004e8b8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gvBfeEngineHandle != NULL")
0x18004e8bd  lea     rdx, ?gvIpsGlobalConfig@@3U_IPSEC_ENGINE_GLOBAL_CONFIG_@@A; struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *
0x18004e8c4  mov     rcx, rsi; struct _IPSEC_ENGINE_GLOBAL_CONFIG_ *
0x18004e8c7  call    ?PrintGlobalConfig@@YAXPEAU_IPSEC_ENGINE_GLOBAL_CONFIG_@@0@Z; PrintGlobalConfig(_IPSEC_ENGINE_GLOBAL_CONFIG_ *,_IPSEC_ENGINE_GLOBAL_CONFIG_ *)
0x18004e8cc  cmp     dword ptr [rsi+0Ch], 10h
0x18004e8d0  jb      short loc_18004E8D7
0x18004e8d2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pIpsGlobalConfig->GCConfigExemptFlags < FW_GLOBAL_CONFIG_IPSEC_EXEMPT_MAX")
0x18004e8d7  mov     rcx, [rsi+20h]; StringSecurityDescriptor
0x18004e8db  mov     r12d, 80070000h
0x18004e8e1  mov     r13d, 1
0x18004e8e7  test    rcx, rcx
0x18004e8ea  jz      short loc_18004E94A
0x18004e8ec  xor     r9d, r9d; SecurityDescriptorSize
0x18004e8ef  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004e8f3  mov     edx, r13d; StringSDRevision
0x18004e8f6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004e8fd  nop     dword ptr [rax+rax+00h]
0x18004e902  test    eax, eax
0x18004e904  jnz     short loc_18004E94A
0x18004e906  call    cs:__imp_GetLastError
0x18004e90d  nop     dword ptr [rax+rax+00h]
0x18004e912  mov     ebx, eax
0x18004e914  test    r14d, r14d
0x18004e917  jz      short loc_18004E997
0x18004e919  movzx   edi, bx
0x18004e91c  test    eax, eax
0x18004e91e  jg      short loc_18004E924
0x18004e920  mov     edx, eax
0x18004e922  jmp     short loc_18004E929
0x18004e924  mov     edx, edi
0x18004e926  or      edx, r12d
0x18004e929  mov     ecx, 0Ch
0x18004e92e  call    FwEventInitConfigReadFailure
0x18004e933  test    ebx, ebx
0x18004e935  jle     short loc_18004E93C
0x18004e937  mov     ebx, edi
0x18004e939  or      ebx, r12d
0x18004e93c  mov     edx, ebx
0x18004e93e  mov     ecx, 0Ch
0x18004e943  call    FwTelemetryEventWriteInitGlobalConfigFailure
0x18004e948  xor     ebx, ebx
0x18004e94a  mov     rcx, [rsi+28h]; StringSecurityDescriptor
0x18004e94e  test    rcx, rcx
0x18004e951  jz      loc_18004EA08
0x18004e957  xor     r9d, r9d; SecurityDescriptorSize
0x18004e95a  lea     r8, [rbp+hMem]; SecurityDescriptor
0x18004e95e  mov     edx, r13d; StringSDRevision
0x18004e961  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004e968  nop     dword ptr [rax+rax+00h]
0x18004e96d  test    eax, eax
0x18004e96f  jnz     loc_18004EA08
0x18004e975  call    cs:__imp_GetLastError
0x18004e97c  nop     dword ptr [rax+rax+00h]
0x18004e981  mov     ebx, eax
0x18004e983  test    r14d, r14d
0x18004e986  jz      loc_18004EA51
0x18004e98c  movzx   edi, bx
0x18004e98f  test    eax, eax
0x18004e991  jg      short loc_18004E9E2
0x18004e993  mov     edx, eax
0x18004e995  jmp     short loc_18004E9E7
0x18004e997  test    ebx, ebx
0x18004e999  jz      short loc_18004E94A
0x18004e99b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e9a2  lea     rax, WPP_GLOBAL_Control
0x18004e9a9  cmp     rcx, rax
0x18004e9ac  jz      loc_18004EC21
0x18004e9b2  test    [rcx+1Ch], r13b
0x18004e9b6  jz      loc_18004EC21
0x18004e9bc  mov     rcx, [rcx+10h]
0x18004e9c0  lea     r9, aIpsecapisetglo; "IpsecApiSetGlobalConfiguration"
0x18004e9c7  mov     edx, 0Eh
0x18004e9cc  mov     [rsp+60h+var_38], ebx
0x18004e9d0  mov     [rsp+60h+var_40], 13Bh
0x18004e9d8  call    WPP_SF_sdD
0x18004e9dd  jmp     loc_18004EC21
0x18004e9e2  mov     edx, edi
0x18004e9e4  or      edx, r12d
0x18004e9e7  mov     ecx, 0Dh
0x18004e9ec  call    FwEventInitConfigReadFailure
0x18004e9f1  test    ebx, ebx
0x18004e9f3  jle     short loc_18004E9FA
0x18004e9f5  mov     ebx, edi
0x18004e9f7  or      ebx, r12d
0x18004e9fa  mov     edx, ebx
0x18004e9fc  mov     ecx, 0Dh
0x18004ea01  call    FwTelemetryEventWriteInitGlobalConfigFailure
0x18004ea06  xor     ebx, ebx
0x18004ea08  mov     rcx, [rsi+38h]; StringSecurityDescriptor
0x18004ea0c  test    rcx, rcx
0x18004ea0f  jz      loc_18004EA97
0x18004ea15  xor     r9d, r9d; SecurityDescriptorSize
0x18004ea18  lea     r8, [rbp+var_18]; SecurityDescriptor
0x18004ea1c  mov     edx, r13d; StringSDRevision
0x18004ea1f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004ea26  nop     dword ptr [rax+rax+00h]
0x18004ea2b  test    eax, eax
0x18004ea2d  jnz     short loc_18004EA97
0x18004ea2f  call    cs:__imp_GetLastError
0x18004ea36  nop     dword ptr [rax+rax+00h]
0x18004ea3b  mov     ebx, eax
0x18004ea3d  test    r14d, r14d
0x18004ea40  jz      loc_18004EAD8
0x18004ea46  movzx   edi, bx
0x18004ea49  test    eax, eax
0x18004ea4b  jg      short loc_18004EA71
0x18004ea4d  mov     edx, eax
0x18004ea4f  jmp     short loc_18004EA76
0x18004ea51  test    ebx, ebx
0x18004ea53  jz      short loc_18004EA08
0x18004ea55  mov     edx, 145h; unsigned int
0x18004ea5a  mov     r8d, ebx; unsigned int
0x18004ea5d  xor     r9d, r9d; int
0x18004ea60  lea     rcx, aIpsecapisetglo; "IpsecApiSetGlobalConfiguration"
0x18004ea67  call    ?IpsTraceError@@YAXPEBDKKH@Z; IpsTraceError(char const *,ulong,ulong,int)
0x18004ea6c  jmp     loc_18004EC21
0x18004ea71  mov     edx, edi
0x18004ea73  or      edx, r12d
0x18004ea76  mov     ecx, 0Fh
0x18004ea7b  call    FwEventInitConfigReadFailure
0x18004ea80  test    ebx, ebx
0x18004ea82  jle     short loc_18004EA89
0x18004ea84  mov     ebx, edi
0x18004ea86  or      ebx, r12d
0x18004ea89  mov     edx, ebx
0x18004ea8b  mov     ecx, 0Fh
0x18004ea90  call    FwTelemetryEventWriteInitGlobalConfigFailure
0x18004ea95  xor     ebx, ebx
0x18004ea97  mov     rcx, [rsi+40h]; StringSecurityDescriptor
0x18004ea9b  test    rcx, rcx
0x18004ea9e  jz      short loc_18004EB0E
0x18004eaa0  xor     r9d, r9d; SecurityDescriptorSize
0x18004eaa3  lea     r8, [rbp+var_10]; SecurityDescriptor
0x18004eaa7  mov     edx, r13d; StringSDRevision
0x18004eaaa  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004eab1  nop     dword ptr [rax+rax+00h]
0x18004eab6  test    eax, eax
0x18004eab8  jnz     short loc_18004EB0E
0x18004eaba  call    cs:__imp_GetLastError
0x18004eac1  nop     dword ptr [rax+rax+00h]
0x18004eac6  mov     ebx, eax
0x18004eac8  test    r14d, r14d
0x18004eacb  jz      short loc_18004EB41
0x18004eacd  movzx   edi, bx
0x18004ead0  test    eax, eax
0x18004ead2  jg      short loc_18004EAE6
0x18004ead4  mov     edx, eax
0x18004ead6  jmp     short loc_18004EAEB
0x18004ead8  test    ebx, ebx
0x18004eada  jz      short loc_18004EA97
0x18004eadc  mov     edx, 14Fh
0x18004eae1  jmp     loc_18004EA5A
0x18004eae6  mov     edx, edi
0x18004eae8  or      edx, r12d
0x18004eaeb  mov     r14d, 10h
0x18004eaf1  mov     ecx, r14d
0x18004eaf4  call    FwEventInitConfigReadFailure
0x18004eaf9  test    ebx, ebx
0x18004eafb  jle     short loc_18004EB02
0x18004eafd  mov     ebx, edi
0x18004eaff  or      ebx, r12d
0x18004eb02  mov     edx, ebx
0x18004eb04  mov     ecx, r14d
0x18004eb07  call    FwTelemetryEventWriteInitGlobalConfigFailure
0x18004eb0c  xor     ebx, ebx
0x18004eb0e  cmp     cs:?gvIpsecCSRuleCount@@3KA, r13d; ulong gvIpsecCSRuleCount
0x18004eb15  jb      short loc_18004EB6D
0x18004eb17  mov     edi, [rsi+0Ch]
0x18004eb1a  mov     eax, dword ptr cs:?gvIpsGlobalConfig@@3U_IPSEC_ENGINE_GLOBAL_CONFIG_@@A+0Ch; _IPSEC_ENGINE_GLOBAL_CONFIG_ gvIpsGlobalConfig
0x18004eb20  xor     edi, eax
0x18004eb22  mov     edx, edi
0x18004eb24  and     edx, [rsi+0Ch]; unsigned int
0x18004eb27  jz      short loc_18004EB55
0x18004eb29  call    ?BfeExemptionFiltersCreate@@YAKHK@Z; BfeExemptionFiltersCreate(int,ulong)
0x18004eb2e  mov     ebx, eax
0x18004eb30  test    eax, eax
0x18004eb32  jz      short loc_18004EB4F
0x18004eb34  mov     r8d, eax
0x18004eb37  mov     edx, 170h
0x18004eb3c  jmp     loc_18004EA5D
0x18004eb41  test    ebx, ebx
0x18004eb43  jz      short loc_18004EB0E
0x18004eb45  mov     edx, 159h
0x18004eb4a  jmp     loc_18004EA5A
0x18004eb4f  mov     eax, dword ptr cs:?gvIpsGlobalConfig@@3U_IPSEC_ENGINE_GLOBAL_CONFIG_@@A+0Ch; _IPSEC_ENGINE_GLOBAL_CONFIG_ gvIpsGlobalConfig
0x18004eb55  and     edi, eax
0x18004eb57  mov     [rbp+var_30], edi
0x18004eb5a  jz      short loc_18004EB6D
0x18004eb5c  lea     r8, [rbp+var_30]; unsigned int *
0x18004eb60  mov     edx, r13d; unsigned int
0x18004eb63  mov     ecx, 3; unsigned int
0x18004eb68  call    ?BfeExemptionFiltersDelete@@YAXKKPEAK@Z; BfeExemptionFiltersDelete(ulong,ulong,ulong *)
0x18004eb6d  movaps  xmm0, xmmword ptr [rsi]
0x18004eb70  mov     rcx, cs:?gvIpsecTunnelRemoteMachineAuthz@@3PEAXEA; hMem
0x18004eb77  movaps  cs:?gvIpsGlobalConfig@@3U_IPSEC_ENGINE_GLOBAL_CONFIG_@@A, xmm0; _IPSEC_ENGINE_GLOBAL_CONFIG_ gvIpsGlobalConfig
0x18004eb7e  movaps  xmm1, xmmword ptr [rsi+10h]
0x18004eb82  movaps  cs:xmmword_180132A70, xmm1
0x18004eb89  movaps  xmm0, xmmword ptr [rsi+20h]
0x18004eb8d  movaps  cs:xmmword_180132A80, xmm0
0x18004eb94  movaps  xmm1, xmmword ptr [rsi+30h]
0x18004eb98  movaps  cs:xmmword_180132A90, xmm1
0x18004eb9f  movsd   xmm0, qword ptr [rsi+40h]
0x18004eba4  movsd   cs:qword_180132AA0, xmm0
0x18004ebac  call    cs:__imp_LocalFree
0x18004ebb3  nop     dword ptr [rax+rax+00h]
0x18004ebb8  mov     rax, [rbp+SecurityDescriptor]
0x18004ebbc  mov     rcx, cs:?gvIpsecTunnelRemoteUserAuthz@@3PEAXEA; hMem
0x18004ebc3  mov     cs:?gvIpsecTunnelRemoteMachineAuthz@@3PEAXEA, rax; void * gvIpsecTunnelRemoteMachineAuthz
0x18004ebca  call    cs:__imp_LocalFree
0x18004ebd1  nop     dword ptr [rax+rax+00h]
0x18004ebd6  mov     rax, [rbp+hMem]
0x18004ebda  mov     rcx, cs:?gvIpsecTransportRemoteMachineAuthz@@3PEAXEA; hMem
0x18004ebe1  mov     cs:?gvIpsecTunnelRemoteUserAuthz@@3PEAXEA, rax; void * gvIpsecTunnelRemoteUserAuthz
0x18004ebe8  call    cs:__imp_LocalFree
0x18004ebef  nop     dword ptr [rax+rax+00h]
0x18004ebf4  mov     rax, [rbp+var_18]
0x18004ebf8  mov     rcx, cs:?gvIpsecTransportRemoteUserAuthz@@3PEAXEA; hMem
0x18004ebff  mov     cs:?gvIpsecTransportRemoteMachineAuthz@@3PEAXEA, rax; void * gvIpsecTransportRemoteMachineAuthz
0x18004ec06  call    cs:__imp_LocalFree
0x18004ec0d  nop     dword ptr [rax+rax+00h]
0x18004ec12  mov     rax, [rbp+var_10]
0x18004ec16  mov     cs:?gvIpsecTransportRemoteUserAuthz@@3PEAXEA, rax; void * gvIpsecTransportRemoteUserAuthz
0x18004ec1d  test    ebx, ebx
0x18004ec1f  jz      short loc_18004EC61
0x18004ec21  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18004ec25  call    cs:__imp_LocalFree
0x18004ec2c  nop     dword ptr [rax+rax+00h]
0x18004ec31  mov     rcx, [rbp+hMem]; hMem
0x18004ec35  call    cs:__imp_LocalFree
0x18004ec3c  nop     dword ptr [rax+rax+00h]
0x18004ec41  mov     rcx, [rbp+var_18]; hMem
0x18004ec45  call    cs:__imp_LocalFree
0x18004ec4c  nop     dword ptr [rax+rax+00h]
0x18004ec51  mov     rcx, [rbp+var_10]; hMem
0x18004ec55  call    cs:__imp_LocalFree
0x18004ec5c  nop     dword ptr [rax+rax+00h]
0x18004ec61  mov     r9d, r13d; int
0x18004ec64  mov     [rsp+60h+var_40], 0; int
0x18004ec6c  mov     r8d, ebx; unsigned int
0x18004ec6f  lea     rcx, aIpsecapisetglo; "IpsecApiSetGlobalConfiguration"
0x18004ec76  mov     edx, 199h; unsigned int
0x18004ec7b  call    ?IpsReturnError@@YAKPEBDKKHH@Z; IpsReturnError(char const *,ulong,ulong,int,int)
0x18004ec80  mov     rcx, [rbp+var_8]
0x18004ec84  xor     rcx, rsp; StackCookie
0x18004ec87  call    __security_check_cookie
0x18004ec8c  lea     r11, [rsp+60h+var_s0]
0x18004ec91  mov     rbx, [r11+38h]
0x18004ec95  mov     rsi, [r11+40h]
0x18004ec99  mov     rsp, r11
0x18004ec9c  pop     r14
0x18004ec9e  pop     r13
0x18004eca0  pop     r12
0x18004eca2  pop     rdi
0x18004eca3  pop     rbp
0x18004eca4  retn
```
