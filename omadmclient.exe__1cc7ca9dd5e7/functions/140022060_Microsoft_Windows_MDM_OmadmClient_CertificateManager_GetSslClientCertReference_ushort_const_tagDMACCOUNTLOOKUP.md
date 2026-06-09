# Microsoft::Windows::MDM::OmadmClient::CertificateManager::GetSslClientCertReference(ushort const *,tagDMACCOUNTLOOKUPTYPE,tagOMADMACCTINFO &,ushort * *,ushort * *,ulong *)

- ea: `0x140022060`
- end: `0x1400223e0`
- name: `?GetSslClientCertReference@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@AEAUtagOMADMACCTINFO@@PEAPEAG3PEAK@Z`
- size: `896`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000e610`
- `0x140013404`
- `0x14001391c`
- `0x14001f84c`
- `0x14001fe18`
- `0x140022060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1400221ff`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002221f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1400221ff`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002221f`
- `DMCmnUtils!CopyString` at `0x1400222eb`
- `DMCmnUtils!CopyString` at `0x140022328`
- `DMCmnUtils!CopyString` at `0x1400222eb`
- `DMCmnUtils!CopyString` at `0x140022328`
- `DMCmnUtils!InvStrCmpNIW` at `0x140022287`
- `DMCmnUtils!InvStrCmpNIW` at `0x1400222bf`
- `DMCmnUtils!InvStrCmpNIW` at `0x140022287`
- `DMCmnUtils!InvStrCmpNIW` at `0x1400222bf`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1400221a4`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1400221a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CertificateManager::GetSslClientCertReference(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        _DWORD *a7)
{
  __int64 v11; // r8
  unsigned int v12; // ebx
  int ValueFromStruct; // eax
  const unsigned __int16 *v14; // rsi
  struct COmaDmLogger *Logger; // rax
  const unsigned __int16 *v16; // rdi
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // rbx
  wchar_t *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  struct COmaDmLogger *v22; // rax
  struct COmaDmLogger *v23; // rax
  int v25; // [rsp+20h] [rbp-A1h]
  unsigned int v26; // [rsp+30h] [rbp-91h] BYREF
  _DWORD *v27; // [rsp+38h] [rbp-89h] BYREF
  unsigned __int16 **v28; // [rsp+40h] [rbp-81h] BYREF
  int v29; // [rsp+48h] [rbp-79h] BYREF
  unsigned __int16 **v30; // [rsp+50h] [rbp-71h] BYREF
  const wchar_t **v31; // [rsp+58h] [rbp-69h] BYREF
  _QWORD v32[3]; // [rsp+60h] [rbp-61h] BYREF
  int v33; // [rsp+78h] [rbp-49h]
  unsigned int *v34; // [rsp+80h] [rbp-41h]
  _QWORD v35[2]; // [rsp+88h] [rbp-39h] BYREF
  int *v36; // [rsp+98h] [rbp-29h]
  __int64 v37; // [rsp+A0h] [rbp-21h]
  char v38; // [rsp+A8h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v30 = a5;
  v28 = a6;
  v27 = a7;
  v26 = 0;
  v32[0] = 0;
  v32[1] = "GetSslClientCertReference";
  v32[2] = COmaDmLogger::GetLogger();
  v33 = 2;
  v34 = &v26;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v29 = 47;
    v36 = &v29;
    v37 = 4;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, v11, 2);
  }
  v35[0] = &v26;
  v35[1] = &v30;
  v36 = (int *)&v28;
  v37 = (__int64)&v27;
  v38 = 1;
  if ( !v30 )
  {
    v12 = -805306126;
LABEL_33:
    v26 = v12;
    goto LABEL_34;
  }
  if ( !v28 )
  {
    v12 = -805306125;
    goto LABEL_33;
  }
  if ( !v27 )
  {
    v12 = -805306124;
    goto LABEL_33;
  }
  *v30 = 0;
  *v28 = 0;
  *v27 = 0;
  v31 = 0;
  ValueFromStruct = OmaDmGetValueFromStruct(24, a4, 0xFFFFFFFFLL, &v31, 0);
  v12 = ValueFromStruct;
  v26 = ValueFromStruct;
  if ( ValueFromStruct < 0 )
  {
    LODWORD(v32[0]) = 6030;
LABEL_31:
    HIDWORD(v32[0]) = ValueFromStruct;
    goto LABEL_34;
  }
  v14 = *v31;
  if ( !*v31 )
  {
    Logger = COmaDmLogger::GetLogger();
    Microsoft::Windows::TelemetryLogger::LogMeasure(Logger, 1, 6042, 0);
    v12 = v26;
    goto LABEL_34;
  }
  v16 = 0;
  v17 = wcschr(*v31, 0x3Bu);
  v18 = v17;
  if ( v17 )
  {
    v18 = v17 + 1;
    v19 = wcschr(v17 + 1, 0x3Bu);
    v16 = v19;
    if ( v19 )
      v16 = v19 + 1;
  }
  if ( *v14 == 59 || !v18 || !*v18 || !v16 || !*v16 )
  {
    v23 = COmaDmLogger::GetLogger();
    Microsoft::Windows::TelemetryLogger::LogMeasure(v23, 1, 12047, 0);
    v12 = Microsoft::Windows::MDM::OmadmClient::CertificateManager::ClearAcctData(a1, a2, a3);
    LODWORD(v32[0]) = 12017;
    HIDWORD(v32[0]) = v12;
    goto LABEL_33;
  }
  v20 = v16 - v18;
  if ( (_DWORD)v20 != 7 )
  {
    if ( (_DWORD)v20 == 5 && !InvStrCmpNIW(v18, L"User", 4u) )
    {
      *v27 = 98304;
      goto LABEL_27;
    }
LABEL_30:
    v22 = COmaDmLogger::GetLogger();
    Microsoft::Windows::TelemetryLogger::LogMeasure(v22, 1, 12046, 0);
    ValueFromStruct = Microsoft::Windows::MDM::OmadmClient::CertificateManager::ClearAcctData(a1, a2, a3);
    v12 = ValueFromStruct;
    v26 = ValueFromStruct;
    LODWORD(v32[0]) = 12017;
    goto LABEL_31;
  }
  if ( InvStrCmpNIW(v18, L"System", 6u) )
    goto LABEL_30;
  *v27 = 688128;
LABEL_27:
  v21 = CopyString(v14, v18 - v14 - 1, v28);
  v12 = v21;
  v26 = v21;
  if ( v21 >= 0 )
  {
    v12 = CopyString(v16, 0xFFFFFFFF, v30);
    goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31A,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
    (const char *)(unsigned int)v21,
    v25);
LABEL_34:
  wil::details::ScopeExitFn__lambda_ae022be5714a01c5bf21ca6186f54ac3___::_ScopeExitFn__lambda_ae022be5714a01c5bf21ca6186f54ac3___(v35);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v32);
  return v12;
}

```

## disassembly

```asm
0x140022060  push    rbp
0x140022062  push    rbx
0x140022063  push    rsi
0x140022064  push    rdi
0x140022065  push    r12
0x140022067  push    r13
0x140022069  push    r14
0x14002206b  push    r15
0x14002206d  lea     rbp, [rsp-7]
0x140022072  sub     rsp, 0C8h
0x140022079  mov     rax, cs:__security_cookie
0x140022080  xor     rax, rsp
0x140022083  mov     [rbp+3Fh+var_50], rax
0x140022087  mov     rbx, r9
0x14002208a  mov     r12d, r8d
0x14002208d  mov     r15, rdx
0x140022090  mov     r14, rcx
0x140022093  mov     rax, [rbp+3Fh+arg_20]
0x140022097  mov     [rbp+3Fh+var_B0], rax
0x14002209b  mov     rax, [rbp+3Fh+arg_28]
0x14002209f  mov     [rsp+100h+var_C0], rax
0x1400220a4  mov     rax, [rbp+3Fh+arg_30]
0x1400220a8  mov     [rsp+100h+var_C8], rax
0x1400220ad  xor     r13d, r13d
0x1400220b0  mov     [rsp+100h+var_D0], r13d
0x1400220b5  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x1400220ba  mov     [rbp+3Fh+var_A0], r13
0x1400220be  lea     rcx, aGetsslclientce_0; "GetSslClientCertReference"
0x1400220c5  mov     [rbp+3Fh+var_98], rcx
0x1400220c9  mov     [rbp+3Fh+var_90], rax
0x1400220cd  mov     [rbp+3Fh+var_88], 2
0x1400220d4  lea     rax, [rsp+100h+var_D0]
0x1400220d9  mov     [rbp+3Fh+var_80], rax
0x1400220dd  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x1400220e4  jz      short loc_14002211D
0x1400220e6  mov     [rbp+3Fh+var_B8], 2Fh ; '/'
0x1400220ed  lea     rax, [rbp+3Fh+var_B8]
0x1400220f1  mov     [rbp+3Fh+var_68], rax
0x1400220f5  mov     [rbp+3Fh+var_60], 4
0x1400220fd  lea     rax, [rbp+3Fh+var_78]
0x140022101  mov     qword ptr [rsp+100h+var_E0], rax
0x140022106  lea     r9d, [r13+2]
0x14002210a  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140022111  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140022118  call    McGenEventWrite_EventWriteTransfer
0x14002211d  lea     rax, [rsp+100h+var_D0]
0x140022122  mov     [rbp+3Fh+var_78], rax
0x140022126  lea     rax, [rbp+3Fh+var_B0]
0x14002212a  mov     [rbp+3Fh+var_70], rax
0x14002212e  lea     rax, [rsp+100h+var_C0]
0x140022133  mov     [rbp+3Fh+var_68], rax
0x140022137  lea     rax, [rsp+100h+var_C8]
0x14002213c  mov     [rbp+3Fh+var_60], rax
0x140022140  mov     [rbp+3Fh+var_58], 1
0x140022144  mov     rax, [rbp+3Fh+var_B0]
0x140022148  test    rax, rax
0x14002214b  jnz     short loc_140022157
0x14002214d  mov     ebx, 0D00000F2h
0x140022152  jmp     loc_1400223A6
0x140022157  cmp     [rsp+100h+var_C0], r13
0x14002215c  jnz     short loc_140022168
0x14002215e  mov     ebx, 0D00000F3h
0x140022163  jmp     loc_1400223A6
0x140022168  cmp     [rsp+100h+var_C8], r13
0x14002216d  jnz     short loc_140022179
0x14002216f  mov     ebx, 0D00000F4h
0x140022174  jmp     loc_1400223A6
0x140022179  mov     [rax], r13
0x14002217c  mov     rax, [rsp+100h+var_C0]
0x140022181  mov     [rax], r13
0x140022184  mov     rax, [rsp+100h+var_C8]
0x140022189  mov     [rax], r13d
0x14002218c  mov     [rbp+3Fh+var_A8], r13
0x140022190  mov     qword ptr [rsp+100h+var_E0], r13; int
0x140022195  lea     r9, [rbp+3Fh+var_A8]
0x140022199  or      r8d, 0FFFFFFFFh
0x14002219d  mov     rdx, rbx
0x1400221a0  lea     ecx, [r8+19h]
0x1400221a4  call    cs:__imp_OmaDmGetValueFromStruct
0x1400221ab  nop     dword ptr [rax+rax+00h]
0x1400221b0  mov     ebx, eax
0x1400221b2  mov     [rsp+100h+var_D0], eax
0x1400221b6  test    eax, eax
0x1400221b8  jns     short loc_1400221C6
0x1400221ba  mov     dword ptr [rbp+3Fh+var_A0], 178Eh
0x1400221c1  jmp     loc_14002236D
0x1400221c6  mov     rax, [rbp+3Fh+var_A8]
0x1400221ca  mov     rsi, [rax]
0x1400221cd  test    rsi, rsi
0x1400221d0  jnz     short loc_1400221F4
0x1400221d2  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x1400221d7  xor     r9d, r9d
0x1400221da  lea     edx, [rsi+1]
0x1400221dd  mov     r8d, 179Ah
0x1400221e3  mov     rcx, rax
0x1400221e6  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x1400221eb  mov     ebx, [rsp+100h+var_D0]
0x1400221ef  jmp     loc_1400223AA
0x1400221f4  mov     rdi, r13
0x1400221f7  mov     edx, 3Bh ; ';'; Ch
0x1400221fc  mov     rcx, rsi; Str
0x1400221ff  call    cs:__imp_wcschr
0x140022206  nop     dword ptr [rax+rax+00h]
0x14002220b  mov     rbx, rax
0x14002220e  test    rax, rax
0x140022211  jz      short loc_140022237
0x140022213  add     rbx, 2
0x140022217  mov     edx, 3Bh ; ';'; Ch
0x14002221c  mov     rcx, rbx; Str
0x14002221f  call    cs:__imp_wcschr
0x140022226  nop     dword ptr [rax+rax+00h]
0x14002222b  mov     rdi, rax
0x14002222e  test    rax, rax
0x140022231  jz      short loc_140022237
0x140022233  add     rdi, 2
0x140022237  mov     eax, 3Bh ; ';'
0x14002223c  cmp     ax, [rsi]
0x14002223f  jz      loc_140022372
0x140022245  test    rbx, rbx
0x140022248  jz      loc_140022372
0x14002224e  cmp     [rbx], r13w
0x140022252  jz      loc_140022372
0x140022258  test    rdi, rdi
0x14002225b  jz      loc_140022372
0x140022261  cmp     [rdi], r13w
0x140022265  jz      loc_140022372
0x14002226b  mov     rax, rdi
0x14002226e  sub     rax, rbx
0x140022271  sar     rax, 1
0x140022274  cmp     eax, 7
0x140022277  jnz     short loc_1400222A8
0x140022279  lea     r8d, [rax-1]
0x14002227d  lea     rdx, aSystem; "System"
0x140022284  mov     rcx, rbx
0x140022287  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x14002228e  nop     dword ptr [rax+rax+00h]
0x140022293  test    eax, eax
0x140022295  jnz     loc_140022338
0x14002229b  mov     rax, [rsp+100h+var_C8]
0x1400222a0  mov     dword ptr [rax], 0A8000h
0x1400222a6  jmp     short loc_1400222DA
0x1400222a8  cmp     eax, 5
0x1400222ab  jnz     loc_140022338
0x1400222b1  lea     r8d, [rax-1]
0x1400222b5  lea     rdx, aUser_1; "User"
0x1400222bc  mov     rcx, rbx
0x1400222bf  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x1400222c6  nop     dword ptr [rax+rax+00h]
0x1400222cb  test    eax, eax
0x1400222cd  jnz     short loc_140022338
0x1400222cf  mov     rax, [rsp+100h+var_C8]
0x1400222d4  mov     dword ptr [rax], 18000h
0x1400222da  sub     rbx, rsi
0x1400222dd  sar     rbx, 1
0x1400222e0  lea     edx, [rbx-1]
0x1400222e3  mov     r8, [rsp+100h+var_C0]
0x1400222e8  mov     rcx, rsi
0x1400222eb  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1400222f2  nop     dword ptr [rax+rax+00h]
0x1400222f7  mov     ebx, eax
0x1400222f9  mov     [rsp+100h+var_D0], eax
0x1400222fd  test    eax, eax
0x1400222ff  jns     short loc_14002231E
0x140022301  mov     rcx, [rbp+47h]; this
0x140022305  mov     r9d, eax; char *
0x140022308  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002230f  mov     edx, 31Ah; void *
0x140022314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022319  jmp     loc_1400223AA
0x14002231e  mov     r8, [rbp+3Fh+var_B0]
0x140022322  or      edx, 0FFFFFFFFh
0x140022325  mov     rcx, rdi
0x140022328  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14002232f  nop     dword ptr [rax+rax+00h]
0x140022334  mov     ebx, eax
0x140022336  jmp     short loc_1400223A6
0x140022338  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002233d  xor     r9d, r9d
0x140022340  lea     edx, [r9+1]
0x140022344  mov     r8d, 2F0Eh
0x14002234a  mov     rcx, rax
0x14002234d  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x140022352  mov     r8d, r12d
0x140022355  mov     rdx, r15
0x140022358  mov     rcx, r14
0x14002235b  call    ?ClearAcctData@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@W4tagOMADM_ACCT_MEMBER_TYPE@@@Z; Microsoft::Windows::MDM::OmadmClient::CertificateManager::ClearAcctData(ushort const *,tagDMACCOUNTLOOKUPTYPE,tagOMADM_ACCT_MEMBER_TYPE)
0x140022360  mov     ebx, eax
0x140022362  mov     [rsp+100h+var_D0], eax
0x140022366  mov     dword ptr [rbp+3Fh+var_A0], 2EF1h
0x14002236d  mov     dword ptr [rbp+3Fh+var_A0+4], eax
0x140022370  jmp     short loc_1400223AA
0x140022372  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140022377  xor     r9d, r9d
0x14002237a  lea     edx, [r9+1]
0x14002237e  mov     r8d, 2F0Fh
0x140022384  mov     rcx, rax
0x140022387  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x14002238c  mov     r8d, r12d
0x14002238f  mov     rdx, r15
0x140022392  mov     rcx, r14
0x140022395  call    ?ClearAcctData@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@W4tagOMADM_ACCT_MEMBER_TYPE@@@Z; Microsoft::Windows::MDM::OmadmClient::CertificateManager::ClearAcctData(ushort const *,tagDMACCOUNTLOOKUPTYPE,tagOMADM_ACCT_MEMBER_TYPE)
0x14002239a  mov     ebx, eax
0x14002239c  mov     dword ptr [rbp+3Fh+var_A0], 2EF1h
0x1400223a3  mov     dword ptr [rbp+3Fh+var_A0+4], eax
0x1400223a6  mov     [rsp+100h+var_D0], ebx
0x1400223aa  lea     rcx, [rbp+3Fh+var_78]
0x1400223ae  call    wil__details__ScopeExitFn__lambda_ae022be5714a01c5bf21ca6186f54ac3______ScopeExitFn__lambda_ae022be5714a01c5bf21ca6186f54ac3___
0x1400223b3  nop
0x1400223b4  lea     rcx, [rbp+3Fh+var_A0]; this
0x1400223b8  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x1400223bd  mov     eax, ebx
0x1400223bf  mov     rcx, [rbp+3Fh+var_50]
0x1400223c3  xor     rcx, rsp; StackCookie
0x1400223c6  call    __security_check_cookie
0x1400223cb  add     rsp, 0C8h
0x1400223d2  pop     r15
0x1400223d4  pop     r14
0x1400223d6  pop     r13
0x1400223d8  pop     r12
0x1400223da  pop     rdi
0x1400223db  pop     rsi
0x1400223dc  pop     rbx
0x1400223dd  pop     rbp
0x1400223de  retn
```
