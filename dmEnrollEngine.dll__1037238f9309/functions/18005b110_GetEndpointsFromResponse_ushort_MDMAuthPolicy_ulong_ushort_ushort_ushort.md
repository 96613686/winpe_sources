# GetEndpointsFromResponse(ushort *,MDMAuthPolicy *,ulong *,ushort * *,ushort * *,ushort * *)

- ea: `0x18005b110`
- end: `0x18005b57b`
- name: `?GetEndpointsFromResponse@@YAJPEAGPEAW4MDMAuthPolicy@@PEAKPEAPEAG33@Z`
- size: `1131`
- prototype: `int(unsigned __int16 *, enum MDMAuthPolicy *, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005f5e4`

## callees

- `0x18000de50`
- `0x18000e508`
- `0x1800140d0`
- `0x180020a1c`
- `0x18002e1a0`
- `0x18002ee0c`
- `0x18003b068`
- `0x18003b170`
- `0x180042efc`
- `0x180043754`
- `0x1800437a4`
- `0x18004c2ec`
- `0x18004c328`
- `0x180059920`
- `0x18005b110`
- `0x18005d01c`
- `0x18005e0a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b1e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b24b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b274`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b1e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b24b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b274`

## string_xrefs

- `0x18005b17d`: `xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:e='http://schemas.microsoft.com/windows/management/2012/01/enrollment'`
- `0x18005b1fa`: `//e:DiscoverResponse//e:AuthenticationServiceUrl`
- `0x18005b2b7`: `//e:DiscoverResponse//e:AuthenticationServiceUrl`
- `0x18005b4c3`: `//e:DiscoverResponse//e:EnrollmentServiceUrl`
- `0x18005b4a5`: `//e:DiscoverResponse//e:EnrollmentPolicyServiceUrl`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetEndpointsFromResponse(
        unsigned __int16 *a1,
        enum MDMAuthPolicy *a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  __int64 v9; // rdx
  int inited; // ebx
  unsigned __int16 *v11; // rbx
  __int64 v12; // r8
  __int64 *v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // ebx
  const WCHAR *v16; // rdx
  const wchar_t *v17; // rcx
  bool v18; // al
  unsigned __int16 v20; // [rsp+30h] [rbp-49h] BYREF
  int NodeStringWithNamespace; // [rsp+34h] [rbp-45h] BYREF
  unsigned __int16 v22; // [rsp+38h] [rbp-41h] BYREF
  struct IXMLDOMDocument2 *v23; // [rsp+40h] [rbp-39h] BYREF
  wchar_t *Buffer; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v25; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v26[2]; // [rsp+58h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+68h] [rbp-11h] BYREF

  NodeStringWithNamespace = 0;
  v23 = 0;
  v25 = 0;
  Buffer = 0;
  *a4 = 0;
  *a5 = 0;
  *a3 |= 0x20u;
  v26[0] = "GetEndpointsFromResponse";
  v26[1] = &NodeStringWithNamespace;
  inited = InitXMLDOMDoc(
             a1,
             (OLECHAR *)L"xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:e='http://schemas.microsoft.com/windows/man"
                         "agement/2012/01/enrollment'",
             (LPVOID *)&v23);
  NodeStringWithNamespace = inited;
  if ( inited < 0 )
    goto LABEL_62;
  inited = HlpGetNodeStringWithNamespace(v23, 0, L"//e:DiscoverResponse//e:AuthPolicy", &v25);
  NodeStringWithNamespace = inited;
  if ( inited < 0 )
    goto LABEL_62;
  v11 = v25;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, AuthenticationModeUsedEvent, v25);
  if ( (unsigned int)_o__wcsicmp(v11, L"Federated") )
  {
    if ( (unsigned int)_o__wcsicmp(v11, L"OnPremise") )
    {
      if ( (unsigned int)_o__wcsicmp(v11, L"Certificate") )
      {
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, UnknownAuthModeEvent, v11);
        inited = -2145910778;
        goto LABEL_61;
      }
      *(_DWORD *)a2 = 2;
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      {
        v13 = CertificateAuthModeInfoEvent;
        goto LABEL_15;
      }
    }
    else
    {
      *(_DWORD *)a2 = 0;
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      {
        v13 = OnPremiseAuthModeInfoEvent;
LABEL_15:
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)v13,
          v12,
          1u,
          &v27);
      }
    }
    if ( HlpGetNodeStringWithNamespace(v23, 0, L"//e:DiscoverResponse//e:AuthenticationServiceUrl", a6) >= 0
      && *a6
      && **a6 )
    {
      goto LABEL_22;
    }
    goto LABEL_19;
  }
  *(_DWORD *)a2 = 1;
  inited = HlpGetNodeStringWithNamespace(v23, 0, L"//e:DiscoverResponse//e:AuthenticationServiceUrl", a6);
  NodeStringWithNamespace = inited;
  if ( inited < 0 )
    goto LABEL_62;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, FederatedAuthenticationURL, *a6);
LABEL_19:
  NodeStringWithNamespace = HlpGetNodeStringWithNamespace(v23, 0, L"//e:DiscoverResponse//e:EnrollmentVersion", &Buffer);
  if ( NodeStringWithNamespace >= 0 && Buffer )
  {
    v20 = 0;
    v22 = 0;
    if ( swscanf_s(Buffer, L"%hu.%hu", &v20, &v22) != 2 )
    {
LABEL_22:
      inited = -2147024809;
LABEL_61:
      NodeStringWithNamespace = inited;
      goto LABEL_62;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl)
      && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      *a3 &= 0xF27FFBDF;
      v15 = *a3;
      if ( v20 != 4 )
      {
        if ( v20 != 5 )
        {
          if ( v20 != 6 )
          {
            if ( v20 == 7 )
            {
              v15 |= 0x4000000u;
LABEL_38:
              *a3 = v15;
              goto LABEL_42;
            }
            if ( v20 != 8 )
              goto LABEL_42;
            v15 |= 0x8000000u;
            goto LABEL_41;
          }
          goto LABEL_37;
        }
        goto LABEL_35;
      }
    }
    else
    {
      LOBYTE(v14) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
        v14);
      *a3 &= 0xFA7FFBDF;
      v15 = *a3;
      if ( v20 != 4 )
      {
        if ( v20 != 5 )
        {
          if ( v20 != 6 )
          {
            if ( v20 != 7 )
              goto LABEL_42;
            v15 |= 0x4000000u;
LABEL_41:
            *a3 = v15;
LABEL_42:
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl)
              && CheckServerIsV8OrAbove(v15)
              && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
            {
              v17 = L"8.0";
            }
            else
            {
              LOBYTE(v16) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
                v16);
              if ( CheckServerIsVersionOrAbove(v15, 7) )
              {
                v17 = L"7.0";
              }
              else if ( CheckServerIsVersionOrAbove(v15, 6) )
              {
                v17 = L"6.0";
              }
              else
              {
                v18 = CheckServerIsVersionOrAbove(v15, 5);
                v17 = L"5.0";
                v16 = &wszURI;
                if ( !v18 )
                  v17 = &wszURI;
              }
            }
            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
              McTemplateU0qqz_EventWriteTransfer((_DWORD)v17, (_DWORD)v16, v20, v22, (__int64)v17);
            goto LABEL_54;
          }
LABEL_37:
          v15 |= 0x1000000u;
          goto LABEL_38;
        }
LABEL_35:
        v15 |= 0x800000u;
        goto LABEL_38;
      }
    }
    v15 |= 0x400u;
    goto LABEL_38;
  }
LABEL_54:
  inited = HlpGetNodeStringWithNamespace(v23, 0, L"//e:DiscoverResponse//e:EnrollmentPolicyServiceUrl", a4);
  NodeStringWithNamespace = inited;
  if ( inited >= 0 )
  {
    inited = HlpGetNodeStringWithNamespace(v23, 0, L"//e:DiscoverResponse//e:EnrollmentServiceUrl", a5);
    NodeStringWithNamespace = inited;
    if ( inited >= 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    {
      McTemplateU0zz_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, EndpointConfigurationInfoEvent, *a4, *a5);
      inited = NodeStringWithNamespace;
    }
  }
LABEL_62:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v26, v9);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&Buffer);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v25);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v23);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18005b110  push    rbp
0x18005b112  push    rbx
0x18005b113  push    rsi
0x18005b114  push    rdi
0x18005b115  push    r12
0x18005b117  push    r13
0x18005b119  push    r14
0x18005b11b  push    r15
0x18005b11d  lea     rbp, [rsp-0Fh]
0x18005b122  sub     rsp, 88h
0x18005b129  mov     rax, cs:__security_cookie
0x18005b130  xor     rax, rsp
0x18005b133  mov     [rbp+47h+var_48], rax
0x18005b137  mov     r12, r9
0x18005b13a  mov     rdi, r8
0x18005b13d  mov     r14, rdx
0x18005b140  mov     r13, [rbp+47h+arg_20]
0x18005b144  mov     rsi, [rbp+47h+arg_28]
0x18005b148  xor     r15d, r15d
0x18005b14b  mov     [rbp+47h+var_8C], r15d
0x18005b14f  mov     [rbp+47h+var_80], r15
0x18005b153  mov     [rbp+47h+var_70], r15
0x18005b157  mov     [rbp+47h+Buffer], r15
0x18005b15b  mov     [r9], r15
0x18005b15e  mov     [r13+0], r15
0x18005b162  or      dword ptr [r8], 20h
0x18005b166  lea     rax, aGetendpointsfr; "GetEndpointsFromResponse"
0x18005b16d  mov     [rbp+47h+var_68], rax
0x18005b171  lea     rax, [rbp+47h+var_8C]
0x18005b175  mov     [rbp+47h+var_60], rax
0x18005b179  lea     r8, [rbp+47h+var_80]; ppv
0x18005b17d  lea     rdx, aXmlnsAHttpWwwW; "xmlns:a='http://www.w3.org/2005/08/addr"...
0x18005b184  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x18005b189  mov     ebx, eax
0x18005b18b  mov     [rbp+47h+var_8C], eax
0x18005b18e  test    eax, eax
0x18005b190  js      loc_18005B532
0x18005b196  lea     r9, [rbp+47h+var_70]; unsigned __int16 **
0x18005b19a  lea     r8, aEDiscoverrespo_3; "//e:DiscoverResponse//e:AuthPolicy"
0x18005b1a1  xor     edx, edx; unsigned __int16 *
0x18005b1a3  mov     rcx, [rbp+47h+var_80]; struct IXMLDOMDocument2 *
0x18005b1a7  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005b1ac  mov     ebx, eax
0x18005b1ae  mov     [rbp+47h+var_8C], eax
0x18005b1b1  test    eax, eax
0x18005b1b3  js      loc_18005B532
0x18005b1b9  mov     rbx, [rbp+47h+var_70]
0x18005b1bd  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18005b1c4  jz      short loc_18005B1DC
0x18005b1c6  mov     r8, rbx
0x18005b1c9  lea     rdx, AuthenticationModeUsedEvent
0x18005b1d0  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18005b1d7  call    McTemplateU0z_EventWriteTransfer
0x18005b1dc  lea     rdx, aFederated; "Federated"
0x18005b1e3  mov     rcx, rbx
0x18005b1e6  call    cs:__imp__o__wcsicmp
0x18005b1ec  test    eax, eax
0x18005b1ee  jnz     short loc_18005B241
0x18005b1f0  mov     dword ptr [r14], 1
0x18005b1f7  mov     r9, rsi; unsigned __int16 **
0x18005b1fa  lea     r8, aEDiscoverrespo_2; "//e:DiscoverResponse//e:AuthenticationS"...
0x18005b201  xor     edx, edx; unsigned __int16 *
0x18005b203  mov     rcx, [rbp+47h+var_80]; struct IXMLDOMDocument2 *
0x18005b207  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005b20c  mov     ebx, eax
0x18005b20e  mov     [rbp+47h+var_8C], eax
0x18005b211  test    eax, eax
0x18005b213  js      loc_18005B532
0x18005b219  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18005b220  jz      loc_18005B2DB
0x18005b226  mov     r8, [rsi]
0x18005b229  lea     rdx, FederatedAuthenticationURL
0x18005b230  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18005b237  call    McTemplateU0z_EventWriteTransfer
0x18005b23c  jmp     loc_18005B2DB
0x18005b241  lea     rdx, aOnpremise; "OnPremise"
0x18005b248  mov     rcx, rbx
0x18005b24b  call    cs:__imp__o__wcsicmp
0x18005b251  test    eax, eax
0x18005b253  jnz     short loc_18005B26A
0x18005b255  mov     [r14], r15d
0x18005b258  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18005b25f  jz      short loc_18005B2B4
0x18005b261  lea     rdx, OnPremiseAuthModeInfoEvent
0x18005b268  jmp     short loc_18005B299
0x18005b26a  lea     rdx, aCertificate; "Certificate"
0x18005b271  mov     rcx, rbx
0x18005b274  call    cs:__imp__o__wcsicmp
0x18005b27a  test    eax, eax
0x18005b27c  jnz     loc_18005B507
0x18005b282  mov     dword ptr [r14], 2
0x18005b289  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18005b290  jz      short loc_18005B2B4
0x18005b292  lea     rdx, CertificateAuthModeInfoEvent
0x18005b299  lea     rax, [rbp+47h+var_58]
0x18005b29d  mov     [rsp+0C0h+var_A0], rax
0x18005b2a2  mov     r9d, 1
0x18005b2a8  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18005b2af  call    McGenEventWrite_EventWriteTransfer
0x18005b2b4  mov     r9, rsi; unsigned __int16 **
0x18005b2b7  lea     r8, aEDiscoverrespo_2; "//e:DiscoverResponse//e:AuthenticationS"...
0x18005b2be  xor     edx, edx; unsigned __int16 *
0x18005b2c0  mov     rcx, [rbp+47h+var_80]; struct IXMLDOMDocument2 *
0x18005b2c4  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005b2c9  test    eax, eax
0x18005b2cb  js      short loc_18005B2DB
0x18005b2cd  mov     rax, [rsi]
0x18005b2d0  test    rax, rax
0x18005b2d3  jz      short loc_18005B2DB
0x18005b2d5  cmp     [rax], r15w
0x18005b2d9  jnz     short loc_18005B32C
0x18005b2db  lea     r9, [rbp+47h+Buffer]; unsigned __int16 **
0x18005b2df  lea     r8, aEDiscoverrespo_1; "//e:DiscoverResponse//e:EnrollmentVersi"...
0x18005b2e6  xor     edx, edx; unsigned __int16 *
0x18005b2e8  mov     rcx, [rbp+47h+var_80]; struct IXMLDOMDocument2 *
0x18005b2ec  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005b2f1  mov     [rbp+47h+var_8C], eax
0x18005b2f4  test    eax, eax
0x18005b2f6  js      loc_18005B4A2
0x18005b2fc  mov     rcx, [rbp+47h+Buffer]; Buffer
0x18005b300  test    rcx, rcx
0x18005b303  jz      loc_18005B4A2
0x18005b309  mov     [rbp+47h+var_90], r15w
0x18005b30e  mov     [rbp+47h+var_88], r15w
0x18005b313  lea     r9, [rbp+47h+var_88]
0x18005b317  lea     r8, [rbp+47h+var_90]
0x18005b31b  lea     rdx, aHuHu; "%hu.%hu"
0x18005b322  call    swscanf_s
0x18005b327  cmp     eax, 2
0x18005b32a  jz      short loc_18005B336
0x18005b32c  mov     ebx, 80070057h
0x18005b331  jmp     loc_18005B52F
0x18005b336  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl(void)'::`2'::impl
0x18005b33d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(void)
0x18005b342  test    al, al
0x18005b344  jz      short loc_18005B39E
0x18005b346  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18005b34d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18005b352  test    al, al
0x18005b354  jz      short loc_18005B39E
0x18005b356  and     dword ptr [rdi], 0F27FFBDFh
0x18005b35c  mov     ebx, [rdi]
0x18005b35e  mov     eax, 4
0x18005b363  lea     esi, [rax+2]
0x18005b366  lea     r14d, [rax+3]
0x18005b36a  lea     r15d, [rax+1]
0x18005b36e  movzx   ecx, [rbp+47h+var_90]
0x18005b372  cmp     ax, cx
0x18005b375  jz      short loc_18005B3CD
0x18005b377  cmp     r15w, cx
0x18005b37b  jz      short loc_18005B3D9
0x18005b37d  cmp     si, cx
0x18005b380  jz      short loc_18005B3E4
0x18005b382  cmp     r14w, cx
0x18005b386  jnz     short loc_18005B38E
0x18005b388  bts     ebx, 1Ah
0x18005b38c  jmp     short loc_18005B3E8
0x18005b38e  mov     eax, 8
0x18005b393  cmp     ax, cx
0x18005b396  jnz     short loc_18005B3F8
0x18005b398  bts     ebx, 1Bh
0x18005b39c  jmp     short loc_18005B3F6
0x18005b39e  mov     dl, 1
0x18005b3a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl(void)'::`2'::impl
0x18005b3a7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18005b3ac  and     dword ptr [rdi], 0FA7FFBDFh
0x18005b3b2  mov     ebx, [rdi]
0x18005b3b4  mov     eax, 4
0x18005b3b9  lea     esi, [rax+2]
0x18005b3bc  lea     r14d, [rax+3]
0x18005b3c0  lea     r15d, [rax+1]
0x18005b3c4  movzx   ecx, [rbp+47h+var_90]
0x18005b3c8  cmp     ax, cx
0x18005b3cb  jnz     short loc_18005B3D3
0x18005b3cd  bts     ebx, 0Ah
0x18005b3d1  jmp     short loc_18005B3E8
0x18005b3d3  cmp     r15w, cx
0x18005b3d7  jnz     short loc_18005B3DF
0x18005b3d9  bts     ebx, 17h
0x18005b3dd  jmp     short loc_18005B3E8
0x18005b3df  cmp     si, cx
0x18005b3e2  jnz     short loc_18005B3EC
0x18005b3e4  bts     ebx, 18h
0x18005b3e8  mov     [rdi], ebx
0x18005b3ea  jmp     short loc_18005B3F8
0x18005b3ec  cmp     r14w, cx
0x18005b3f0  jnz     short loc_18005B3F8
0x18005b3f2  bts     ebx, 1Ah
0x18005b3f6  mov     [rdi], ebx
0x18005b3f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl(void)'::`2'::impl
0x18005b3ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(void)
0x18005b404  test    al, al
0x18005b406  jz      short loc_18005B42C
0x18005b408  mov     ecx, ebx; unsigned int
0x18005b40a  call    ?CheckServerIsV8OrAbove@@YA_NK@Z; CheckServerIsV8OrAbove(ulong)
0x18005b40f  test    al, al
0x18005b411  jz      short loc_18005B42C
0x18005b413  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18005b41a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18005b41f  test    al, al
0x18005b421  jz      short loc_18005B42C
0x18005b423  lea     rcx, String1; "8.0"
0x18005b42a  jmp     short loc_18005B485
0x18005b42c  mov     dl, 1
0x18005b42e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl(void)'::`2'::impl
0x18005b435  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18005b43a  mov     edx, r14d; int
0x18005b43d  mov     ecx, ebx; unsigned int
0x18005b43f  call    ?CheckServerIsVersionOrAbove@@YA_NKH@Z; CheckServerIsVersionOrAbove(ulong,int)
0x18005b444  test    al, al
0x18005b446  jz      short loc_18005B451
0x18005b448  lea     rcx, a70; "7.0"
0x18005b44f  jmp     short loc_18005B485
0x18005b451  mov     edx, esi; int
0x18005b453  mov     ecx, ebx; unsigned int
0x18005b455  call    ?CheckServerIsVersionOrAbove@@YA_NKH@Z; CheckServerIsVersionOrAbove(ulong,int)
0x18005b45a  test    al, al
0x18005b45c  jz      short loc_18005B467
0x18005b45e  lea     rcx, a60; "6.0"
0x18005b465  jmp     short loc_18005B485
0x18005b467  mov     edx, r15d; int
0x18005b46a  mov     ecx, ebx; unsigned int
0x18005b46c  call    ?CheckServerIsVersionOrAbove@@YA_NKH@Z; CheckServerIsVersionOrAbove(ulong,int)
0x18005b471  lea     rcx, a50; "5.0"
0x18005b478  test    al, al
0x18005b47a  lea     rdx, wszURI
0x18005b481  cmovz   rcx, rdx
0x18005b485  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18005b48c  jz      short loc_18005B4A2
0x18005b48e  mov     [rsp+0C0h+var_A0], rcx
0x18005b493  movzx   r9d, [rbp+47h+var_88]
0x18005b498  movzx   r8d, [rbp+47h+var_90]
0x18005b49d  call    McTemplateU0qqz_EventWriteTransfer
0x18005b4a2  mov     r9, r12; unsigned __int16 **
0x18005b4a5  lea     r8, aEDiscoverrespo; "//e:DiscoverResponse//e:EnrollmentPolic"...
0x18005b4ac  xor     edx, edx; unsigned __int16 *
0x18005b4ae  mov     rcx, [rbp+47h+var_80]; struct IXMLDOMDocument2 *
0x18005b4b2  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005b4b7  mov     ebx, eax
0x18005b4b9  mov     [rbp+47h+var_8C], eax
0x18005b4bc  test    eax, eax
0x18005b4be  js      short loc_18005B532
0x18005b4c0  mov     r9, r13; unsigned __int16 **
0x18005b4c3  lea     r8, aEDiscoverrespo_0; "//e:DiscoverResponse//e:EnrollmentServi"...
0x18005b4ca  xor     edx, edx; unsigned __int16 *
0x18005b4cc  mov     rcx, [rbp+47h+var_80]; struct IXMLDOMDocument2 *
0x18005b4d0  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005b4d5  mov     ebx, eax
0x18005b4d7  mov     [rbp+47h+var_8C], eax
0x18005b4da  test    eax, eax
0x18005b4dc  js      short loc_18005B532
0x18005b4de  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18005b4e5  jz      short loc_18005B532
0x18005b4e7  mov     r9, [r13+0]
0x18005b4eb  mov     r8, [r12]
0x18005b4ef  lea     rdx, EndpointConfigurationInfoEvent
0x18005b4f6  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18005b4fd  call    McTemplateU0zz_EventWriteTransfer
0x18005b502  mov     ebx, [rbp+47h+var_8C]
0x18005b505  jmp     short loc_18005B532
0x18005b507  mov     eax, 4
0x18005b50c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, al
0x18005b512  jz      short loc_18005B52A
0x18005b514  mov     r8, rbx
0x18005b517  lea     rdx, UnknownAuthModeEvent
0x18005b51e  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18005b525  call    McTemplateU0z_EventWriteTransfer
0x18005b52a  mov     ebx, 80180006h
0x18005b52f  mov     [rbp+47h+var_8C], ebx
0x18005b532  lea     rcx, [rbp+47h+var_68]; this
0x18005b536  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005b53b  nop
0x18005b53c  lea     rcx, [rbp+47h+Buffer]
0x18005b540  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18005b545  nop
0x18005b546  lea     rcx, [rbp+47h+var_70]
0x18005b54a  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18005b54f  nop
0x18005b550  lea     rcx, [rbp+47h+var_80]
0x18005b554  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005b559  mov     eax, ebx
0x18005b55b  mov     rcx, [rbp+47h+var_48]
0x18005b55f  xor     rcx, rsp; StackCookie
0x18005b562  call    __security_check_cookie
0x18005b567  add     rsp, 88h
0x18005b56e  pop     r15
0x18005b570  pop     r14
0x18005b572  pop     r13
0x18005b574  pop     r12
0x18005b576  pop     rdi
0x18005b577  pop     rsi
0x18005b578  pop     rbx
0x18005b579  pop     rbp
0x18005b57a  retn
```
