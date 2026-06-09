# GetEndpointsFromResponse(ushort *,MDMAuthPolicy *,ulong *,ushort * *,ushort * *,ushort * *)

- ea: `0x180028ee8`
- end: `0x1800294a3`
- name: `?GetEndpointsFromResponse@@YAJPEAGPEAW4MDMAuthPolicy@@PEAKPEAPEAG33@Z`
- size: `1467`
- prototype: `__int64 __fastcall(unsigned __int16 *, enum MDMAuthPolicy *, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001436c`

## callees

- `0x1800026d0`
- `0x1800032d0`
- `0x180012f70`
- `0x1800141b0`
- `0x1800194e0`
- `0x180019ec0`
- `0x18001afd8`
- `0x18001b028`
- `0x18001cb08`
- `0x18001df00`
- `0x18001df98`
- `0x180028ee8`
- `0x18002aba0`
- `0x18002ba18`
- `0x18002d008`
- `0x18002d0c4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180028fc7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029092`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029113`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180028fc7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029092`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029113`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002945d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002945d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029423`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029449`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029423`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029449`

## string_xrefs

- `0x180028f5e`: `xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:e='http://schemas.microsoft.com/windows/management/2012/01/enrollment'`
- `0x180028fe8`: `//e:DiscoverResponse//e:AuthenticationServiceUrl`
- `0x1800290d5`: `//e:DiscoverResponse//e:AuthenticationServiceUrl`
- `0x180029384`: `//e:DiscoverResponse//e:EnrollmentPolicyServiceUrl`
- `0x1800293a6`: `//e:DiscoverResponse//e:EnrollmentServiceUrl`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetEndpointsFromResponse(
        unsigned __int16 *a1,
        enum MDMAuthPolicy *a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  unsigned __int16 *v8; // r14
  wchar_t *v9; // r13
  int inited; // ebx
  __int64 v11; // r8
  __int64 *v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  const WCHAR *v16; // rdx
  unsigned int v17; // r8d
  const wchar_t *v18; // rcx
  unsigned int Ptr; // r8d
  bool v20; // al
  unsigned __int16 **v21; // rdi
  unsigned __int16 **v22; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v24; // rax
  unsigned __int16 v26; // [rsp+40h] [rbp-69h] BYREF
  int NodeStringWithNamespace; // [rsp+44h] [rbp-65h] BYREF
  int v28; // [rsp+48h] [rbp-61h] BYREF
  __int16 v29; // [rsp+4Ch] [rbp-5Dh]
  unsigned __int16 v30; // [rsp+50h] [rbp-59h] BYREF
  struct IXMLDOMDocument2 *v31; // [rsp+58h] [rbp-51h] BYREF
  wchar_t *Buffer; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int16 **v34; // [rsp+70h] [rbp-39h]
  unsigned __int16 **v35; // [rsp+78h] [rbp-31h]
  _QWORD v36[2]; // [rsp+80h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+90h] [rbp-19h] BYREF

  v34 = a4;
  v35 = a5;
  NodeStringWithNamespace = 0;
  v31 = 0;
  v8 = 0;
  v33 = 0;
  v9 = 0;
  Buffer = 0;
  *a4 = 0;
  *a5 = 0;
  *a3 |= 0x20u;
  v36[0] = "GetEndpointsFromResponse";
  v36[1] = &NodeStringWithNamespace;
  inited = InitXMLDOMDoc(
             a1,
             (OLECHAR *)L"xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:e='http://schemas.microsoft.com/windows/man"
                         "agement/2012/01/enrollment'",
             (LPVOID *)&v31);
  NodeStringWithNamespace = inited;
  if ( inited < 0 )
    goto LABEL_67;
  inited = HlpGetNodeStringWithNamespace(v31, 0, L"//e:DiscoverResponse//e:AuthPolicy", &v33);
  NodeStringWithNamespace = inited;
  v8 = v33;
  if ( inited < 0 )
    goto LABEL_67;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, AuthenticationModeUsedEvent, v33);
  if ( !(unsigned int)_o__wcsicmp(v8, L"Federated") )
  {
    *(_DWORD *)a2 = 1;
    inited = HlpGetNodeStringWithNamespace(v31, 0, L"//e:DiscoverResponse//e:AuthenticationServiceUrl", a6);
    NodeStringWithNamespace = inited;
    if ( inited < 0 )
      goto LABEL_67;
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, FederatedAuthenticationURL, *a6);
    goto LABEL_9;
  }
  if ( (unsigned int)_o__wcsicmp(v8, L"OnPremise") )
  {
    if ( (unsigned int)_o__wcsicmp(v8, L"Certificate") )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, UnknownAuthModeEvent, v8);
      inited = -2145910778;
      goto LABEL_66;
    }
    *(_DWORD *)a2 = 2;
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    {
      v12 = CertificateAuthModeInfoEvent;
      goto LABEL_16;
    }
  }
  else
  {
    *(_DWORD *)a2 = 0;
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    {
      v12 = OnPremiseAuthModeInfoEvent;
LABEL_16:
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)v12,
        v11,
        1u,
        &v37);
    }
  }
  if ( HlpGetNodeStringWithNamespace(v31, 0, L"//e:DiscoverResponse//e:AuthenticationServiceUrl", a6) >= 0
    && *a6
    && **a6 )
  {
    goto LABEL_12;
  }
LABEL_9:
  NodeStringWithNamespace = HlpGetNodeStringWithNamespace(v31, 0, L"//e:DiscoverResponse//e:EnrollmentVersion", &Buffer);
  v9 = Buffer;
  if ( NodeStringWithNamespace >= 0 && Buffer )
  {
    v26 = 0;
    v30 = 0;
    if ( swscanf_s(Buffer, L"%hu.%hu", &v26, &v30) != 2 )
    {
LABEL_12:
      inited = -2147024809;
LABEL_66:
      NodeStringWithNamespace = inited;
      goto LABEL_67;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl)
      && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      *a3 &= 0xF27FFBDF;
      v14 = *a3;
      switch ( v26 )
      {
        case 4u:
LABEL_27:
          v14 |= 0x400u;
LABEL_36:
          *a3 = v14;
          goto LABEL_37;
        case 5u:
LABEL_29:
          v14 |= 0x800000u;
          goto LABEL_36;
        case 6u:
LABEL_31:
          v14 |= 0x1000000u;
          goto LABEL_36;
      }
      if ( v26 != 7 )
      {
        if ( v26 != 8 )
          goto LABEL_37;
        v14 |= 0x8000000u;
        goto LABEL_36;
      }
    }
    else
    {
      Ptr = *(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor;
      if ( (*(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor & 4) == 0 )
      {
        v37.Ptr = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(
                               v13,
                               &v37);
        Ptr = v37.Ptr;
      }
      v28 = 0;
      v29 = 3;
      wil::details::ReportUsageToService(&qword_180070DB0, 46391183, (Ptr >> 10) & 1, (Ptr >> 11) & 1, &v28, 1);
      *a3 &= 0xFA7FFBDF;
      v14 = *a3;
      switch ( v26 )
      {
        case 4u:
          goto LABEL_27;
        case 5u:
          goto LABEL_29;
        case 6u:
          goto LABEL_31;
      }
      if ( v26 != 7 )
      {
LABEL_37:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl)
          && CheckServerIsV8OrAbove(v14)
          && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
        {
          v18 = L"8.0";
        }
        else
        {
          v17 = *(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor;
          if ( (*(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor & 4) == 0 )
          {
            v37.Ptr = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(
                                   v15,
                                   &v37);
            v17 = v37.Ptr;
          }
          v28 = 0;
          v29 = 3;
          wil::details::ReportUsageToService(&qword_180070DB0, 46391183, (v17 >> 10) & 1, (v17 >> 11) & 1, &v28, 1);
          if ( CheckServerIsVersionOrAbove(v14, 7) )
          {
            v18 = L"7.0";
          }
          else if ( CheckServerIsVersionOrAbove(v14, 6) )
          {
            v18 = L"6.0";
          }
          else
          {
            v20 = CheckServerIsVersionOrAbove(v14, 5);
            v18 = L"5.0";
            v16 = &String2;
            if ( !v20 )
              v18 = &String2;
          }
        }
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
          McTemplateU0qqz_EventWriteTransfer((_DWORD)v18, (_DWORD)v16, v26, v30, (__int64)v18);
        v9 = Buffer;
        goto LABEL_59;
      }
    }
    v14 |= 0x4000000u;
    goto LABEL_36;
  }
LABEL_59:
  v21 = v34;
  inited = HlpGetNodeStringWithNamespace(v31, 0, L"//e:DiscoverResponse//e:EnrollmentPolicyServiceUrl", v34);
  NodeStringWithNamespace = inited;
  if ( inited >= 0 )
  {
    v22 = v35;
    inited = HlpGetNodeStringWithNamespace(v31, 0, L"//e:DiscoverResponse//e:EnrollmentServiceUrl", v35);
    NodeStringWithNamespace = inited;
    if ( inited >= 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    {
      McTemplateU0zz_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, EndpointConfigurationInfoEvent, *v21, *v22);
      inited = NodeStringWithNamespace;
    }
  }
LABEL_67:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v36);
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  if ( v8 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v8);
  }
  if ( v31 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v31->lpVtbl->Release)(v31);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180028ee8  push    rbp
0x180028eea  push    rbx
0x180028eeb  push    rsi
0x180028eec  push    rdi
0x180028eed  push    r12
0x180028eef  push    r13
0x180028ef1  push    r14
0x180028ef3  push    r15
0x180028ef5  lea     rbp, [rsp-0Fh]
0x180028efa  sub     rsp, 0B8h
0x180028f01  mov     rax, cs:__security_cookie
0x180028f08  xor     rax, rsp
0x180028f0b  mov     [rbp+47h+var_50], rax
0x180028f0f  mov     [rbp+47h+var_80], r9
0x180028f13  mov     rdi, r8
0x180028f16  mov     r12, rdx
0x180028f19  mov     rdx, [rbp+47h+arg_20]
0x180028f1d  mov     [rbp+47h+var_78], rdx
0x180028f21  mov     rsi, [rbp+47h+arg_28]
0x180028f25  xor     r8d, r8d
0x180028f28  mov     [rbp+47h+var_AC], r8d
0x180028f2c  mov     [rbp+47h+var_98], r8
0x180028f30  mov     r14d, r8d
0x180028f33  mov     [rbp+47h+var_88], r8
0x180028f37  mov     r13d, r8d
0x180028f3a  mov     [rbp+47h+Buffer], r8
0x180028f3e  mov     [r9], r8
0x180028f41  mov     [rdx], r8
0x180028f44  or      dword ptr [rdi], 20h
0x180028f47  lea     rax, aGetendpointsfr; "GetEndpointsFromResponse"
0x180028f4e  mov     [rbp+47h+var_70], rax
0x180028f52  lea     rax, [rbp+47h+var_AC]
0x180028f56  mov     [rbp+47h+var_68], rax
0x180028f5a  lea     r8, [rbp+47h+var_98]; ppv
0x180028f5e  lea     rdx, aXmlnsAHttpWwwW; "xmlns:a='http://www.w3.org/2005/08/addr"...
0x180028f65  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x180028f6a  mov     ebx, eax
0x180028f6c  mov     [rbp+47h+var_AC], eax
0x180028f6f  test    eax, eax
0x180028f71  js      loc_180029414
0x180028f77  lea     r9, [rbp+47h+var_88]; unsigned __int16 **
0x180028f7b  lea     r8, aEDiscoverrespo_3; "//e:DiscoverResponse//e:AuthPolicy"
0x180028f82  xor     edx, edx; unsigned __int16 *
0x180028f84  mov     rcx, [rbp+47h+var_98]; struct IXMLDOMDocument2 *
0x180028f88  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x180028f8d  mov     ebx, eax
0x180028f8f  mov     [rbp+47h+var_AC], eax
0x180028f92  mov     r14, [rbp+47h+var_88]
0x180028f96  test    eax, eax
0x180028f98  js      loc_180029414
0x180028f9e  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x180028fa5  jz      short loc_180028FBD
0x180028fa7  mov     r8, r14
0x180028faa  lea     rdx, AuthenticationModeUsedEvent
0x180028fb1  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180028fb8  call    McTemplateU0z_EventWriteTransfer
0x180028fbd  lea     rdx, aFederated; "Federated"
0x180028fc4  mov     rcx, r14
0x180028fc7  call    cs:__imp__o__wcsicmp
0x180028fce  nop     dword ptr [rax+rax+00h]
0x180028fd3  xor     ebx, ebx
0x180028fd5  test    eax, eax
0x180028fd7  jnz     loc_180029088
0x180028fdd  lea     r15d, [rbx+1]
0x180028fe1  mov     [r12], r15d
0x180028fe5  mov     r9, rsi; unsigned __int16 **
0x180028fe8  lea     r8, aEDiscoverrespo_2; "//e:DiscoverResponse//e:AuthenticationS"...
0x180028fef  xor     edx, edx; unsigned __int16 *
0x180028ff1  mov     rcx, [rbp+47h+var_98]; struct IXMLDOMDocument2 *
0x180028ff5  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x180028ffa  mov     ebx, eax
0x180028ffc  mov     [rbp+47h+var_AC], eax
0x180028fff  test    eax, eax
0x180029001  js      loc_180029414
0x180029007  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18002900e  jz      short loc_180029026
0x180029010  mov     r8, [rsi]
0x180029013  lea     rdx, FederatedAuthenticationURL
0x18002901a  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180029021  call    McTemplateU0z_EventWriteTransfer
0x180029026  xor     ebx, ebx
0x180029028  lea     r9, [rbp+47h+Buffer]; unsigned __int16 **
0x18002902c  lea     r8, aEDiscoverrespo_1; "//e:DiscoverResponse//e:EnrollmentVersi"...
0x180029033  xor     edx, edx; unsigned __int16 *
0x180029035  mov     rcx, [rbp+47h+var_98]; struct IXMLDOMDocument2 *
0x180029039  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18002903e  mov     [rbp+47h+var_AC], eax
0x180029041  mov     r13, [rbp+47h+Buffer]
0x180029045  test    eax, eax
0x180029047  js      loc_18002937D
0x18002904d  test    r13, r13
0x180029050  jz      loc_18002937D
0x180029056  mov     [rbp+47h+var_B0], bx
0x18002905a  mov     [rbp+47h+var_A0], bx
0x18002905e  lea     r9, [rbp+47h+var_A0]
0x180029062  lea     r8, [rbp+47h+var_B0]
0x180029066  lea     rdx, aHuHu; "%hu.%hu"
0x18002906d  mov     rcx, r13; Buffer
0x180029070  call    swscanf_s
0x180029075  cmp     eax, 2
0x180029078  jz      loc_180029148
0x18002907e  mov     ebx, 80070057h
0x180029083  jmp     loc_180029411
0x180029088  lea     rdx, aOnpremise; "OnPremise"
0x18002908f  mov     rcx, r14
0x180029092  call    cs:__imp__o__wcsicmp
0x180029099  nop     dword ptr [rax+rax+00h]
0x18002909e  test    eax, eax
0x1800290a0  jnz     short loc_180029109
0x1800290a2  mov     [r12], ebx
0x1800290a6  lea     r15d, [rax+1]
0x1800290aa  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x1800290b1  jz      short loc_1800290D2
0x1800290b3  lea     rdx, OnPremiseAuthModeInfoEvent
0x1800290ba  lea     rax, [rbp+47h+var_60]
0x1800290be  mov     r9d, r15d
0x1800290c1  mov     [rsp+0F0h+var_D0], rax
0x1800290c6  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x1800290cd  call    McGenEventWrite_EventWriteTransfer
0x1800290d2  mov     r9, rsi; unsigned __int16 **
0x1800290d5  lea     r8, aEDiscoverrespo_2; "//e:DiscoverResponse//e:AuthenticationS"...
0x1800290dc  xor     edx, edx; unsigned __int16 *
0x1800290de  mov     rcx, [rbp+47h+var_98]; struct IXMLDOMDocument2 *
0x1800290e2  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x1800290e7  test    eax, eax
0x1800290e9  js      loc_180029028
0x1800290ef  mov     rax, [rsi]
0x1800290f2  test    rax, rax
0x1800290f5  jz      loc_180029028
0x1800290fb  cmp     [rax], bx
0x1800290fe  jnz     loc_18002907E
0x180029104  jmp     loc_180029028
0x180029109  lea     rdx, aCertificate; "Certificate"
0x180029110  mov     rcx, r14
0x180029113  call    cs:__imp__o__wcsicmp
0x18002911a  nop     dword ptr [rax+rax+00h]
0x18002911f  test    eax, eax
0x180029121  jnz     loc_1800293E8
0x180029127  mov     dword ptr [r12], 2
0x18002912f  lea     r15d, [rax+1]
0x180029133  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18002913a  jz      short loc_1800290D2
0x18002913c  lea     rdx, CertificateAuthModeInfoEvent
0x180029143  jmp     loc_1800290BA
0x180029148  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl(void)'::`2'::impl
0x18002914f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(void)
0x180029154  test    al, al
0x180029156  jz      loc_180029276
0x18002915c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180029163  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180029168  test    al, al
0x18002916a  jz      loc_180029276
0x180029170  and     dword ptr [rdi], 0F27FFBDFh
0x180029176  mov     ebx, [rdi]
0x180029178  mov     esi, 4
0x18002917d  lea     ecx, [rsi+3]
0x180029180  lea     r12d, [rsi+2]
0x180029184  lea     r13d, [rsi+1]
0x180029188  movzx   eax, [rbp+47h+var_B0]
0x18002918c  cmp     si, ax
0x18002918f  jnz     short loc_180029197
0x180029191  bts     ebx, 0Ah
0x180029195  jmp     short loc_1800291C8
0x180029197  cmp     r13w, ax
0x18002919b  jnz     short loc_1800291A3
0x18002919d  bts     ebx, 17h
0x1800291a1  jmp     short loc_1800291C8
0x1800291a3  cmp     r12w, ax
0x1800291a7  jnz     short loc_1800291AF
0x1800291a9  bts     ebx, 18h
0x1800291ad  jmp     short loc_1800291C8
0x1800291af  cmp     cx, ax
0x1800291b2  jnz     short loc_1800291BA
0x1800291b4  bts     ebx, 1Ah
0x1800291b8  jmp     short loc_1800291C8
0x1800291ba  mov     ecx, 8
0x1800291bf  cmp     cx, ax
0x1800291c2  jnz     short loc_1800291CA
0x1800291c4  bts     ebx, 1Bh
0x1800291c8  mov     [rdi], ebx
0x1800291ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl(void)'::`2'::impl
0x1800291d1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(void)
0x1800291d6  xor     edi, edi
0x1800291d8  test    al, al
0x1800291da  jz      short loc_1800291FB
0x1800291dc  mov     ecx, ebx; unsigned int
0x1800291de  call    ?CheckServerIsV8OrAbove@@YA_NK@Z; CheckServerIsV8OrAbove(ulong)
0x1800291e3  test    al, al
0x1800291e5  jz      short loc_1800291FB
0x1800291e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1800291ee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1800291f3  test    al, al
0x1800291f5  jnz     loc_18002931E
0x1800291fb  mov     rax, cs:Feature_EnrollmentAttestationDebugFields__descriptor
0x180029202  mov     r8d, [rax]
0x180029205  test    sil, r8b
0x180029208  jnz     short loc_18002921D
0x18002920a  lea     rdx, [rbp+47h+var_60]
0x18002920e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(void)
0x180029213  mov     rcx, [rax]
0x180029216  mov     qword ptr [rbp+47h+var_60], rcx
0x18002921a  mov     r8d, ecx
0x18002921d  mov     [rbp+47h+var_A8], edi
0x180029220  mov     [rbp+47h+var_A4], 3
0x180029226  mov     r9d, r8d
0x180029229  shr     r9d, 0Bh
0x18002922d  and     r9d, r15d
0x180029230  shr     r8d, 0Ah
0x180029234  and     r8d, r15d
0x180029237  mov     [rsp+0F0h+var_C8], r15d
0x18002923c  lea     rax, [rbp+47h+var_A8]
0x180029240  mov     [rsp+0F0h+var_D0], rax
0x180029245  mov     edx, 2C3DF8Fh
0x18002924a  lea     rcx, qword_180070DB0
0x180029251  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180029256  mov     edx, 7; int
0x18002925b  mov     ecx, ebx; unsigned int
0x18002925d  call    ?CheckServerIsVersionOrAbove@@YA_NKH@Z; CheckServerIsVersionOrAbove(ulong,int)
0x180029262  test    al, al
0x180029264  jz      loc_180029327
0x18002926a  lea     rcx, a70; "7.0"
0x180029271  jmp     loc_18002935C
0x180029276  mov     rax, cs:Feature_EnrollmentAttestationDebugFields__descriptor
0x18002927d  mov     r8d, [rax]
0x180029280  mov     esi, 4
0x180029285  test    sil, r8b
0x180029288  jnz     short loc_18002929D
0x18002928a  lea     rdx, [rbp+47h+var_60]
0x18002928e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(void)
0x180029293  mov     rcx, [rax]
0x180029296  mov     qword ptr [rbp+47h+var_60], rcx
0x18002929a  mov     r8d, ecx
0x18002929d  mov     [rbp+47h+var_A8], 0
0x1800292a4  mov     [rbp+47h+var_A4], 3
0x1800292aa  mov     r9d, r8d
0x1800292ad  shr     r9d, 0Bh
0x1800292b1  and     r9d, r15d
0x1800292b4  shr     r8d, 0Ah
0x1800292b8  and     r8d, r15d
0x1800292bb  mov     [rsp+0F0h+var_C8], r15d
0x1800292c0  lea     rax, [rbp+47h+var_A8]
0x1800292c4  mov     [rsp+0F0h+var_D0], rax
0x1800292c9  mov     edx, 2C3DF8Fh
0x1800292ce  lea     rcx, qword_180070DB0
0x1800292d5  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800292da  and     dword ptr [rdi], 0FA7FFBDFh
0x1800292e0  mov     ebx, [rdi]
0x1800292e2  mov     ecx, 7
0x1800292e7  lea     r12d, [rcx-1]
0x1800292eb  lea     r13d, [rcx-2]
0x1800292ef  movzx   eax, [rbp+47h+var_B0]
0x1800292f3  cmp     si, ax
0x1800292f6  jz      loc_180029191
0x1800292fc  cmp     r13w, ax
0x180029300  jz      loc_18002919D
0x180029306  cmp     r12w, ax
0x18002930a  jz      loc_1800291A9
0x180029310  cmp     cx, ax
0x180029313  jnz     loc_1800291CA
0x180029319  jmp     loc_1800291B4
0x18002931e  lea     rcx, a80; "8.0"
0x180029325  jmp     short loc_18002935C
0x180029327  mov     edx, r12d; int
0x18002932a  mov     ecx, ebx; unsigned int
0x18002932c  call    ?CheckServerIsVersionOrAbove@@YA_NKH@Z; CheckServerIsVersionOrAbove(ulong,int)
0x180029331  test    al, al
0x180029333  jz      short loc_18002933E
0x180029335  lea     rcx, a60; "6.0"
0x18002933c  jmp     short loc_18002935C
0x18002933e  mov     edx, r13d; int
0x180029341  mov     ecx, ebx; unsigned int
0x180029343  call    ?CheckServerIsVersionOrAbove@@YA_NKH@Z; CheckServerIsVersionOrAbove(ulong,int)
0x180029348  lea     rcx, a50; "5.0"
0x18002934f  test    al, al
0x180029351  lea     rdx, String2
0x180029358  cmovz   rcx, rdx
0x18002935c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x180029363  jz      short loc_180029379
0x180029365  mov     [rsp+0F0h+var_D0], rcx
0x18002936a  movzx   r9d, [rbp+47h+var_A0]
0x18002936f  movzx   r8d, [rbp+47h+var_B0]
0x180029374  call    McTemplateU0qqz_EventWriteTransfer
0x180029379  mov     r13, [rbp+47h+Buffer]
0x18002937d  mov     rdi, [rbp+47h+var_80]
0x180029381  mov     r9, rdi; unsigned __int16 **
0x180029384  lea     r8, aEDiscoverrespo; "//e:DiscoverResponse//e:EnrollmentPolic"...
0x18002938b  xor     edx, edx; unsigned __int16 *
0x18002938d  mov     rcx, [rbp+47h+var_98]; struct IXMLDOMDocument2 *
0x180029391  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x180029396  mov     ebx, eax
0x180029398  mov     [rbp+47h+var_AC], eax
0x18002939b  test    eax, eax
0x18002939d  js      short loc_180029414
0x18002939f  mov     rsi, [rbp+47h+var_78]
0x1800293a3  mov     r9, rsi; unsigned __int16 **
0x1800293a6  lea     r8, aEDiscoverrespo_0; "//e:DiscoverResponse//e:EnrollmentServi"...
0x1800293ad  xor     edx, edx; unsigned __int16 *
0x1800293af  mov     rcx, [rbp+47h+var_98]; struct IXMLDOMDocument2 *
0x1800293b3  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x1800293b8  mov     ebx, eax
  ... truncated ...
```
