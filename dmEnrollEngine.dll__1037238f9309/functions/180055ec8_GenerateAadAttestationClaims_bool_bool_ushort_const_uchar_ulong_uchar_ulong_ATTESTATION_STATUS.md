# GenerateAadAttestationClaims(bool,bool,ushort const *,uchar * *,ulong *,uchar * *,ulong *,_ATTESTATION_STATUS *)

- ea: `0x180055ec8`
- end: `0x1800560d3`
- name: `?GenerateAadAttestationClaims@@YAJ_N0PEBGPEAPEAEPEAK23PEAU_ATTESTATION_STATUS@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(bool, bool, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, struct _ATTESTATION_STATUS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b3ac`

## callees

- `0x180010fcc`
- `0x1800140d0`
- `0x18001ac7c`
- `0x18001b308`
- `0x18004234c`
- `0x1800424fc`
- `0x180042634`
- `0x18004c38c`
- `0x180055ec8`

## import_xrefs

- `DMCmnUtils!DmGenerateAttestationClaimsOld` at `0x180056091`
- `DMCmnUtils!DmGenerateAttestationClaimsOld` at `0x180056091`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180055f2e`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180055f2e`
- `dsreg!DsrGetJoinInfo` at `0x180055f7f`
- `dsreg!DsrGetJoinInfo` at `0x180055f7f`
- `dsreg!DsrFreeJoinInfo` at `0x18005609d`
- `dsreg!DsrFreeJoinInfo` at `0x18005609d`

## string_xrefs

- `0x180055f56`: `DmGetActiveUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GenerateAadAttestationClaims(
        unsigned __int8 a1,
        unsigned __int8 a2,
        const unsigned __int16 *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        struct _ATTESTATION_STATUS *a8)
{
  int v10; // edi
  int v11; // esi
  int ActiveUserSid; // eax
  __int64 v13; // rcx
  unsigned int AttestationClaimsOld; // ebx
  int JoinInfo; // eax
  __int64 v16; // rcx
  struct _ATTESTATION_STATUS *v17; // rcx
  __int64 v18; // rcx
  struct _ATTESTATION_STATUS *v19; // rcx
  __int64 v20; // rdx
  __int64 v22; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 *v23; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v24[16]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v25[3]; // [rsp+80h] [rbp-19h] BYREF
  char v26; // [rsp+98h] [rbp-1h]
  int v27; // [rsp+E0h] [rbp+47h] BYREF

  v10 = a2;
  v11 = a1;
  v27 = 0;
  v25[0] = "GenerateAadAttestationClaims";
  v25[1] = &v27;
  v22 = 0;
  v23 = 0;
  v24[0] = 0;
  v24[2] = 0;
  if ( !a1 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v23,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v23);
    AttestationClaimsOld = ActiveUserSid;
    v27 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      if ( (_BYTE)v10 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        McTemplateU0zd_EventWriteTransfer(
          v13,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGetActiveUserSid",
          (unsigned int)ActiveUserSid);
LABEL_12:
        AttestationClaimsOld = v27;
        goto LABEL_21;
      }
      goto LABEL_21;
    }
    AutoImpersonate::ImpersonateSID((AutoImpersonate *)v24, v23);
  }
  JoinInfo = DsrGetJoinInfo(a3, &v22);
  v27 = JoinInfo;
  if ( JoinInfo < 0 )
  {
    if ( (_BYTE)v10 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v16,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DsrGetJoinInfo",
        (unsigned int)JoinInfo);
      JoinInfo = v27;
    }
    v17 = a8;
    *((_DWORD *)a8 + 1) = JoinInfo;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      (char *)v17 + 8,
      L"AAD join information is missing",
      31);
    goto LABEL_12;
  }
  v18 = v22;
  if ( v22 )
  {
    v25[2] = &v22;
    v26 = 1;
    if ( !(_BYTE)v11 )
    {
      AutoImpersonate::RevertToSelf((AutoImpersonate *)v24);
      v18 = v22;
    }
    AttestationClaimsOld = DmGenerateAttestationClaimsOld(
                             *(const struct _CERT_CONTEXT **)(v18 + 8),
                             v11,
                             a4,
                             a5,
                             a6,
                             a7,
                             0,
                             0,
                             0,
                             0,
                             v10);
    DsrFreeJoinInfo(v22);
  }
  else
  {
    AttestationClaimsOld = -2147467261;
    if ( (_BYTE)v10 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(0, EnterpriseDiagnosticsTPMFunctionFailure, L"DsrGetJoinInfo", 2147500035LL);
      JoinInfo = v27;
    }
    v19 = a8;
    *((_DWORD *)a8 + 1) = JoinInfo;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      (char *)v19 + 8,
      L"AAD join information is missing",
      31);
  }
LABEL_21:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v24);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v25, v20);
  return AttestationClaimsOld;
}

```

## disassembly

```asm
0x180055ec8  push    rbp
0x180055eca  push    rbx
0x180055ecb  push    rsi
0x180055ecc  push    rdi
0x180055ecd  push    r14
0x180055ecf  push    r15
0x180055ed1  lea     rbp, [rsp-0Fh]
0x180055ed6  sub     rsp, 0A8h
0x180055edd  mov     r15, r9
0x180055ee0  mov     r14, r8
0x180055ee3  movzx   edi, dl
0x180055ee6  movzx   esi, cl
0x180055ee9  mov     [rbp+37h+arg_0], 0
0x180055ef0  lea     rax, aGenerateaadatt_0; "GenerateAadAttestationClaims"
0x180055ef7  mov     [rbp+37h+var_50], rax
0x180055efb  lea     rax, [rbp+37h+arg_0]
0x180055eff  mov     [rbp+37h+var_48], rax
0x180055f03  mov     [rbp+37h+var_70], 0
0x180055f0b  mov     [rbp+37h+var_68], 0
0x180055f13  mov     [rbp+37h+var_60], 0
0x180055f17  mov     [rbp+37h+var_5E], 0
0x180055f1b  test    cl, cl
0x180055f1d  jnz     short loc_180055F78
0x180055f1f  xor     edx, edx
0x180055f21  lea     rcx, [rbp+37h+var_68]
0x180055f25  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180055f2a  lea     rcx, [rbp+37h+var_68]
0x180055f2e  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180055f34  mov     ebx, eax
0x180055f36  mov     [rbp+37h+arg_0], eax
0x180055f39  test    eax, eax
0x180055f3b  jns     short loc_180055F6B
0x180055f3d  test    dil, dil
0x180055f40  jz      loc_1800560A4
0x180055f46  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180055f4d  jz      loc_1800560A4
0x180055f53  mov     r9d, eax
0x180055f56  lea     r8, aDmgetactiveuse_0; "DmGetActiveUserSid"
0x180055f5d  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180055f64  call    McTemplateU0zd_EventWriteTransfer
0x180055f69  jmp     short loc_180055FD0
0x180055f6b  mov     rdx, [rbp+37h+var_68]; unsigned __int16 *
0x180055f6f  lea     rcx, [rbp+37h+var_60]; this
0x180055f73  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x180055f78  lea     rdx, [rbp+37h+var_70]
0x180055f7c  mov     rcx, r14
0x180055f7f  call    cs:__imp_DsrGetJoinInfo
0x180055f85  mov     [rbp+37h+arg_0], eax
0x180055f88  test    eax, eax
0x180055f8a  jns     short loc_180055FD8
0x180055f8c  test    dil, dil
0x180055f8f  jz      short loc_180055FB3
0x180055f91  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180055f98  jz      short loc_180055FB3
0x180055f9a  mov     r9d, eax
0x180055f9d  lea     r8, aDsrgetjoininfo_0; "DsrGetJoinInfo"
0x180055fa4  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180055fab  call    McTemplateU0zd_EventWriteTransfer
0x180055fb0  mov     eax, [rbp+37h+arg_0]
0x180055fb3  mov     rcx, [rbp+37h+arg_38]
0x180055fb7  mov     [rcx+4], eax
0x180055fba  add     rcx, 8
0x180055fbe  mov     r8d, 1Fh
0x180055fc4  lea     rdx, aAadJoinInforma; "AAD join information is missing"
0x180055fcb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180055fd0  mov     ebx, [rbp+37h+arg_0]
0x180055fd3  jmp     loc_1800560A4
0x180055fd8  mov     rcx, [rbp+37h+var_70]
0x180055fdc  test    rcx, rcx
0x180055fdf  jnz     short loc_18005602C
0x180055fe1  mov     ebx, 80004003h
0x180055fe6  test    dil, dil
0x180055fe9  jz      short loc_18005600D
0x180055feb  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180055ff2  jz      short loc_18005600D
0x180055ff4  mov     r9d, ebx
0x180055ff7  lea     r8, aDsrgetjoininfo_0; "DsrGetJoinInfo"
0x180055ffe  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180056005  call    McTemplateU0zd_EventWriteTransfer
0x18005600a  mov     eax, [rbp+37h+arg_0]
0x18005600d  mov     rcx, [rbp+37h+arg_38]
0x180056011  mov     [rcx+4], eax
0x180056014  add     rcx, 8
0x180056018  mov     r8d, 1Fh
0x18005601e  lea     rdx, aAadJoinInforma; "AAD join information is missing"
0x180056025  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18005602a  jmp     short loc_1800560A4
0x18005602c  lea     rax, [rbp+37h+var_70]
0x180056030  mov     [rbp+37h+var_40], rax
0x180056034  mov     [rbp+37h+var_38], 1
0x180056038  test    sil, sil
0x18005603b  jnz     short loc_18005604A
0x18005603d  lea     rcx, [rbp+37h+var_60]; this
0x180056041  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x180056046  mov     rcx, [rbp+37h+var_70]
0x18005604a  mov     edx, esi
0x18005604c  mov     [rsp+0D0h+var_80], edi
0x180056050  mov     [rsp+0D0h+var_88], 0
0x180056059  mov     [rsp+0D0h+var_90], 0
0x180056062  mov     [rsp+0D0h+var_98], 0
0x18005606b  mov     [rsp+0D0h+var_A0], 0
0x180056074  mov     rax, [rbp+37h+arg_30]
0x180056078  mov     [rsp+0D0h+var_A8], rax
0x18005607d  mov     rax, [rbp+37h+arg_28]
0x180056081  mov     [rsp+0D0h+var_B0], rax
0x180056086  mov     r9, [rbp+37h+arg_20]
0x18005608a  mov     r8, r15
0x18005608d  mov     rcx, [rcx+8]
0x180056091  call    cs:__imp_?DmGenerateAttestationClaimsOld@@YAJPEBU_CERT_CONTEXT@@HPEAPEAEPEAK121212H@Z; DmGenerateAttestationClaimsOld(_CERT_CONTEXT const *,int,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,int)
0x180056097  mov     ebx, eax
0x180056099  mov     rcx, [rbp+37h+var_70]
0x18005609d  call    cs:__imp_DsrFreeJoinInfo
0x1800560a3  nop
0x1800560a4  lea     rcx, [rbp+37h+var_60]; this
0x1800560a8  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800560ad  nop
0x1800560ae  lea     rcx, [rbp+37h+var_68]
0x1800560b2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800560b7  nop
0x1800560b8  lea     rcx, [rbp+37h+var_50]; this
0x1800560bc  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800560c1  mov     eax, ebx
0x1800560c3  add     rsp, 0A8h
0x1800560ca  pop     r15
0x1800560cc  pop     r14
0x1800560ce  pop     rdi
0x1800560cf  pop     rsi
0x1800560d0  pop     rbx
0x1800560d1  pop     rbp
0x1800560d2  retn
```
