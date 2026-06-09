# GenerateAadAttestationClaims(bool,bool,ushort const *,uchar * *,ulong *,uchar * *,ulong *,_ATTESTATION_STATUS *)

- ea: `0x180034184`
- end: `0x1800344c1`
- name: `?GenerateAadAttestationClaims@@YAJ_N0PEBGPEAPEAEPEAK23PEAU_ATTESTATION_STATUS@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(bool, bool, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, struct _ATTESTATION_STATUS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x180012fcc`
- `0x1800141b0`
- `0x18001e0b0`
- `0x180021db4`
- `0x180034184`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034455`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034455`
- `DMCmnUtils!DmGenerateAttestationClaimsOld` at `0x1800343ff`
- `DMCmnUtils!DmGenerateAttestationClaimsOld` at `0x1800343ff`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800341e3`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800341e3`
- `DMCmnUtils!DmRevertToSelf` at `0x1800342ba`
- `DMCmnUtils!DmRevertToSelf` at `0x180034348`
- `DMCmnUtils!DmRevertToSelf` at `0x18003438d`
- `DMCmnUtils!DmRevertToSelf` at `0x18003442a`
- `DMCmnUtils!DmRevertToSelf` at `0x1800342ba`
- `DMCmnUtils!DmRevertToSelf` at `0x180034348`
- `DMCmnUtils!DmRevertToSelf` at `0x18003438d`
- `DMCmnUtils!DmRevertToSelf` at `0x18003442a`
- `DMCmnUtils!DmImpersonate` at `0x180034228`
- `DMCmnUtils!DmImpersonate` at `0x180034228`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800342c8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034356`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800343a8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034438`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800342c8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034356`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800343a8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034438`
- `dsreg!DsrFreeJoinInfo` at `0x180034411`
- `dsreg!DsrFreeJoinInfo` at `0x180034411`
- `dsreg!DsrGetJoinInfo` at `0x18003424a`
- `dsreg!DsrGetJoinInfo` at `0x18003424a`

## string_xrefs

- `0x180034209`: `DmGetActiveUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  int v10; // r14d
  int v11; // r15d
  char v12; // bl
  char v13; // di
  int ActiveUserSid; // eax
  __int64 v15; // rcx
  unsigned int AttestationClaimsOld; // esi
  int JoinInfo; // eax
  __int64 v18; // rcx
  struct _ATTESTATION_STATUS *v19; // rcx
  HRESULT v20; // eax
  struct _ATTESTATION_STATUS *v21; // rcx
  HRESULT v22; // eax
  HRESULT v23; // ecx
  HRESULT v24; // eax
  int v26; // [rsp+20h] [rbp-81h]
  int v27; // [rsp+20h] [rbp-81h]
  HLOCAL hMem; // [rsp+60h] [rbp-41h] BYREF
  __int64 v29; // [rsp+68h] [rbp-39h] BYREF
  char v30; // [rsp+70h] [rbp-31h]
  char v31; // [rsp+72h] [rbp-2Fh]
  _QWORD v32[3]; // [rsp+80h] [rbp-21h] BYREF
  char v33; // [rsp+98h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]
  int v35; // [rsp+F0h] [rbp+4Fh] BYREF

  v10 = a2;
  v11 = a1;
  v35 = 0;
  v32[0] = "GenerateAadAttestationClaims";
  v32[1] = &v35;
  v29 = 0;
  hMem = 0;
  v12 = 0;
  v30 = 0;
  v13 = 0;
  v31 = 0;
  if ( !a1 )
  {
    hMem = 0;
    ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
    AttestationClaimsOld = ActiveUserSid;
    v35 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      if ( (_BYTE)v10 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        McTemplateU0zd_EventWriteTransfer(
          v15,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGetActiveUserSid",
          (unsigned int)ActiveUserSid);
        AttestationClaimsOld = v35;
      }
      goto LABEL_43;
    }
    if ( (int)DmImpersonate((const unsigned __int16 *)hMem) >= 0 )
    {
      v12 = 1;
      v30 = 1;
      v13 = 1;
      v31 = 1;
    }
  }
  JoinInfo = DsrGetJoinInfo(a3, &v29);
  v35 = JoinInfo;
  if ( JoinInfo < 0 )
  {
    if ( (_BYTE)v10 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v18,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DsrGetJoinInfo",
        (unsigned int)JoinInfo);
      JoinInfo = v35;
    }
    v19 = a8;
    *((_DWORD *)a8 + 1) = JoinInfo;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      (char *)v19 + 8,
      L"AAD join information is missing",
      31);
    AttestationClaimsOld = v35;
    v20 = 0;
    if ( v12 )
    {
      if ( v13 )
        v20 = DmRevertToSelf();
      else
        v20 = CoRevertToSelf();
    }
    if ( v20 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
        (const char *)(unsigned int)v20,
        v26);
    goto LABEL_43;
  }
  if ( !v29 )
  {
    AttestationClaimsOld = -2147467261;
    if ( (_BYTE)v10 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(v18, EnterpriseDiagnosticsTPMFunctionFailure, L"DsrGetJoinInfo", 2147500035LL);
      JoinInfo = v35;
    }
    v21 = a8;
    *((_DWORD *)a8 + 1) = JoinInfo;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      (char *)v21 + 8,
      L"AAD join information is missing",
      31);
    v22 = 0;
    if ( v12 )
    {
      if ( v13 )
        v22 = DmRevertToSelf();
      else
        v22 = CoRevertToSelf();
    }
    if ( v22 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
        (const char *)(unsigned int)v22,
        v26);
    goto LABEL_43;
  }
  v32[2] = &v29;
  v33 = 1;
  if ( !(_BYTE)v11 && v12 )
  {
    if ( !v13 )
    {
      v23 = CoRevertToSelf();
      goto LABEL_35;
    }
    v23 = DmRevertToSelf();
    if ( v23 >= 0 )
    {
      v13 = 0;
      v31 = 0;
LABEL_35:
      if ( v23 >= 0 )
        v12 = 0;
      v30 = v12;
    }
  }
  AttestationClaimsOld = DmGenerateAttestationClaimsOld(
                           *(const struct _CERT_CONTEXT **)(v29 + 8),
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
  DsrFreeJoinInfo(v29);
  v24 = 0;
  if ( v12 )
  {
    if ( v13 )
      v24 = DmRevertToSelf();
    else
      v24 = CoRevertToSelf();
  }
  if ( v24 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
      (const char *)(unsigned int)v24,
      v27);
LABEL_43:
  if ( hMem )
    LocalFree(hMem);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v32);
  return AttestationClaimsOld;
}

```

## disassembly

```asm
0x180034184  push    rbp
0x180034186  push    rbx
0x180034187  push    rsi
0x180034188  push    rdi
0x180034189  push    r12
0x18003418b  push    r13
0x18003418d  push    r14
0x18003418f  push    r15
0x180034191  lea     rbp, [rsp-7]
0x180034196  sub     rsp, 0A8h
0x18003419d  mov     r13, r9
0x1800341a0  mov     r12, r8
0x1800341a3  movzx   r14d, dl
0x1800341a7  movzx   r15d, cl
0x1800341ab  xor     ecx, ecx
0x1800341ad  mov     [rbp+3Fh+arg_0], ecx
0x1800341b0  lea     rax, aGenerateaadatt_0; "GenerateAadAttestationClaims"
0x1800341b7  mov     [rbp+3Fh+var_60], rax
0x1800341bb  lea     rax, [rbp+3Fh+arg_0]
0x1800341bf  mov     [rbp+3Fh+var_58], rax
0x1800341c3  mov     [rbp+3Fh+var_78], rcx
0x1800341c7  mov     [rbp+3Fh+hMem], rcx
0x1800341cb  mov     bl, cl
0x1800341cd  mov     [rbp+3Fh+var_70], cl
0x1800341d0  mov     dil, cl
0x1800341d3  mov     [rbp+3Fh+var_6E], cl
0x1800341d6  test    r15b, r15b
0x1800341d9  jnz     short loc_180034243
0x1800341db  mov     [rbp+3Fh+hMem], rcx
0x1800341df  lea     rcx, [rbp+3Fh+hMem]
0x1800341e3  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800341ea  nop     dword ptr [rax+rax+00h]
0x1800341ef  mov     esi, eax
0x1800341f1  mov     [rbp+3Fh+arg_0], eax
0x1800341f4  test    eax, eax
0x1800341f6  jns     short loc_180034224
0x1800341f8  test    r14b, r14b
0x1800341fb  jz      short loc_18003421F
0x1800341fd  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034204  jz      short loc_18003421F
0x180034206  mov     r9d, eax
0x180034209  lea     r8, aDmgetactiveuse_0; "DmGetActiveUserSid"
0x180034210  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180034217  call    McTemplateU0zd_EventWriteTransfer
0x18003421c  mov     esi, [rbp+3Fh+arg_0]
0x18003421f  jmp     loc_18003444C
0x180034224  mov     rcx, [rbp+3Fh+hMem]
0x180034228  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18003422f  nop     dword ptr [rax+rax+00h]
0x180034234  test    eax, eax
0x180034236  js      short loc_180034243
0x180034238  mov     bl, 1
0x18003423a  mov     [rbp+3Fh+var_70], bl
0x18003423d  mov     dil, bl
0x180034240  mov     [rbp+3Fh+var_6E], bl
0x180034243  lea     rdx, [rbp+3Fh+var_78]
0x180034247  mov     rcx, r12
0x18003424a  call    cs:__imp_DsrGetJoinInfo
0x180034251  nop     dword ptr [rax+rax+00h]
0x180034256  mov     [rbp+3Fh+arg_0], eax
0x180034259  xor     r12d, r12d
0x18003425c  test    eax, eax
0x18003425e  jns     loc_1800342E5
0x180034264  test    r14b, r14b
0x180034267  jz      short loc_18003428B
0x180034269  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034270  jz      short loc_18003428B
0x180034272  mov     r9d, eax
0x180034275  lea     r8, aDsrgetjoininfo_0; "DsrGetJoinInfo"
0x18003427c  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180034283  call    McTemplateU0zd_EventWriteTransfer
0x180034288  mov     eax, [rbp+3Fh+arg_0]
0x18003428b  mov     rcx, [rbp+3Fh+arg_38]
0x180034292  mov     [rcx+4], eax
0x180034295  add     rcx, 8
0x180034299  mov     r8d, 1Fh
0x18003429f  lea     rdx, aAadJoinInforma; "AAD join information is missing"
0x1800342a6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800342ab  mov     esi, [rbp+3Fh+arg_0]
0x1800342ae  mov     eax, r12d
0x1800342b1  test    bl, bl
0x1800342b3  jz      short loc_1800342D4
0x1800342b5  test    dil, dil
0x1800342b8  jz      short loc_1800342C8
0x1800342ba  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1800342c1  nop     dword ptr [rax+rax+00h]
0x1800342c6  jmp     short loc_1800342D4
0x1800342c8  call    cs:__imp_CoRevertToSelf
0x1800342cf  nop     dword ptr [rax+rax+00h]
0x1800342d4  mov     rcx, [rbp+47h]; this
0x1800342d8  test    eax, eax
0x1800342da  js      loc_180034497
0x1800342e0  jmp     loc_18003444C
0x1800342e5  cmp     [rbp+3Fh+var_78], r12
0x1800342e9  jnz     loc_180034373
0x1800342ef  mov     esi, 80004003h
0x1800342f4  test    r14b, r14b
0x1800342f7  jz      short loc_18003431B
0x1800342f9  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180034300  jz      short loc_18003431B
0x180034302  mov     r9d, esi
0x180034305  lea     r8, aDsrgetjoininfo_0; "DsrGetJoinInfo"
0x18003430c  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180034313  call    McTemplateU0zd_EventWriteTransfer
0x180034318  mov     eax, [rbp+3Fh+arg_0]
0x18003431b  mov     rcx, [rbp+3Fh+arg_38]
0x180034322  mov     [rcx+4], eax
0x180034325  add     rcx, 8
0x180034329  mov     r8d, 1Fh
0x18003432f  lea     rdx, aAadJoinInforma; "AAD join information is missing"
0x180034336  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003433b  nop
0x18003433c  mov     eax, r12d
0x18003433f  test    bl, bl
0x180034341  jz      short loc_180034362
0x180034343  test    dil, dil
0x180034346  jz      short loc_180034356
0x180034348  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18003434f  nop     dword ptr [rax+rax+00h]
0x180034354  jmp     short loc_180034362
0x180034356  call    cs:__imp_CoRevertToSelf
0x18003435d  nop     dword ptr [rax+rax+00h]
0x180034362  mov     rcx, [rbp+47h]; this
0x180034366  test    eax, eax
0x180034368  js      loc_1800344AC
0x18003436e  jmp     loc_18003444C
0x180034373  lea     rax, [rbp+3Fh+var_78]
0x180034377  mov     [rbp+3Fh+var_50], rax
0x18003437b  mov     [rbp+3Fh+var_48], 1
0x18003437f  test    r15b, r15b
0x180034382  jnz     short loc_1800343C2
0x180034384  test    bl, bl
0x180034386  jz      short loc_1800343C2
0x180034388  test    dil, dil
0x18003438b  jz      short loc_1800343A8
0x18003438d  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180034394  nop     dword ptr [rax+rax+00h]
0x180034399  mov     ecx, eax
0x18003439b  test    eax, eax
0x18003439d  js      short loc_1800343C2
0x18003439f  mov     dil, r12b
0x1800343a2  mov     [rbp+3Fh+var_6E], r12b
0x1800343a6  jmp     short loc_1800343B6
0x1800343a8  call    cs:__imp_CoRevertToSelf
0x1800343af  nop     dword ptr [rax+rax+00h]
0x1800343b4  mov     ecx, eax
0x1800343b6  movzx   ebx, bl
0x1800343b9  test    ecx, ecx
0x1800343bb  cmovns  ebx, r12d
0x1800343bf  mov     [rbp+3Fh+var_70], bl
0x1800343c2  mov     edx, r15d
0x1800343c5  mov     [rsp+0E0h+var_90], r14d
0x1800343ca  mov     [rsp+0E0h+var_98], r12
0x1800343cf  mov     [rsp+0E0h+var_A0], r12
0x1800343d4  mov     [rsp+0E0h+var_A8], r12
0x1800343d9  mov     [rsp+0E0h+var_B0], r12
0x1800343de  mov     rax, [rbp+3Fh+arg_30]
0x1800343e2  mov     [rsp+0E0h+var_B8], rax
0x1800343e7  mov     rax, [rbp+3Fh+arg_28]
0x1800343eb  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800343f0  mov     r9, [rbp+3Fh+arg_20]
0x1800343f4  mov     r8, r13
0x1800343f7  mov     rcx, [rbp+3Fh+var_78]
0x1800343fb  mov     rcx, [rcx+8]
0x1800343ff  call    cs:__imp_?DmGenerateAttestationClaimsOld@@YAJPEBU_CERT_CONTEXT@@HPEAPEAEPEAK121212H@Z; DmGenerateAttestationClaimsOld(_CERT_CONTEXT const *,int,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,int)
0x180034406  nop     dword ptr [rax+rax+00h]
0x18003440b  mov     esi, eax
0x18003440d  mov     rcx, [rbp+3Fh+var_78]
0x180034411  call    cs:__imp_DsrFreeJoinInfo
0x180034418  nop     dword ptr [rax+rax+00h]
0x18003441d  nop
0x18003441e  mov     eax, r12d
0x180034421  test    bl, bl
0x180034423  jz      short loc_180034444
0x180034425  test    dil, dil
0x180034428  jz      short loc_180034438
0x18003442a  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180034431  nop     dword ptr [rax+rax+00h]
0x180034436  jmp     short loc_180034444
0x180034438  call    cs:__imp_CoRevertToSelf
0x18003443f  nop     dword ptr [rax+rax+00h]
0x180034444  mov     rcx, [rbp+47h]; this
0x180034448  test    eax, eax
0x18003444a  js      short loc_180034482
0x18003444c  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180034450  test    rcx, rcx
0x180034453  jz      short loc_180034462
0x180034455  call    cs:__imp_LocalFree
0x18003445c  nop     dword ptr [rax+rax+00h]
0x180034461  nop
0x180034462  lea     rcx, [rbp+3Fh+var_60]; this
0x180034466  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18003446b  mov     eax, esi
0x18003446d  add     rsp, 0A8h
0x180034474  pop     r15
0x180034476  pop     r14
0x180034478  pop     r13
0x18003447a  pop     r12
0x18003447c  pop     rdi
0x18003447d  pop     rsi
0x18003447e  pop     rbx
0x18003447f  pop     rbp
0x180034480  retn
0x180034482  mov     r9d, eax; char *
0x180034485  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\published\\inc\\"...
0x18003448c  mov     edx, 2Ch ; ','; void *
0x180034491  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180034497  mov     r9d, eax; char *
0x18003449a  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\published\\inc\\"...
0x1800344a1  mov     edx, 2Ch ; ','; void *
0x1800344a6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800344ac  mov     r9d, eax; char *
0x1800344af  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\published\\inc\\"...
0x1800344b6  mov     edx, 2Ch ; ','; void *
0x1800344bb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
