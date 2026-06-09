# IsTPMReady(ushort const *,bool *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180036ea0`
- end: `0x18003716e`
- name: `?IsTPMReady@@YAJPEBGPEA_NAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x180012fcc`
- `0x1800141b0`
- `0x18001e0b0`
- `0x180036c9c`
- `0x180036ea0`
- `0x18003b55c`
- `0x180041410`
- `0x18004284c`

## import_xrefs

- `DMCmnUtils!DmGetTpmState` at `0x180036fd4`
- `DMCmnUtils!DmGetTpmState` at `0x180036fd4`
- `DMCmnUtils!DmGetTpmIsAlgorithmSupported` at `0x180036f82`
- `DMCmnUtils!DmGetTpmIsAlgorithmSupported` at `0x180036f82`
- `DMCmnUtils!DmGetTpmInfo` at `0x180036f33`
- `DMCmnUtils!DmGetTpmInfo` at `0x180036f33`

## string_xrefs

- `0x180036f0d`: `IsTPMReady`
- `0x1800370e8`: `TPM not ready for storage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsTPMReady(const unsigned __int16 *a1, _BYTE *a2, __int64 a3)
{
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // ebx
  int IsAlgorithmSupported; // eax
  __int64 v10; // rcx
  int TpmState; // eax
  __int64 v12; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  int v17; // eax
  char v18; // r8
  char v19; // dl
  char v20; // cl
  char v21; // r9
  int TpmInfo; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+6Ch] [rbp-94h]
  unsigned int v26[2]; // [rsp+70h] [rbp-90h]
  unsigned int v27; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+7Ch] [rbp-84h] BYREF
  _QWORD v29[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v30[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v31[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  TpmInfo = 0;
  v27 = 0;
  memset_0(v31, 0, 0x208u);
  memset_0(v30, 0, 0x208u);
  v28 = 1;
  *a2 = 0;
  v29[0] = "IsTPMReady";
  v29[1] = &TpmInfo;
  TpmInfo = DmGetTpmInfo(&v27, 0, 0, 0, 0);
  if ( TpmInfo >= 0 )
  {
    IsAlgorithmSupported = DmGetTpmIsAlgorithmSupported(a1, &v28);
    TpmInfo = IsAlgorithmSupported;
    if ( IsAlgorithmSupported < 0 )
    {
      v28 = 1;
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v10,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGetTpmIsAlgorithmSupported",
          (unsigned int)IsAlgorithmSupported);
    }
    v24 = 0;
    v25 = 0x10000;
    *(_QWORD *)v26 = 0;
    TpmState = DmGetTpmState(&v24);
    TpmInfo = TpmState;
    if ( TpmState < 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v12,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGetTpmState",
        (unsigned int)TpmState);
    GetReasonString(v26[0], v31, v13);
    GetReasonString(v26[1], v30, v14);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0qtztzttttz_EventWriteTransfer(
        BYTE1(v24),
        (unsigned __int8)v25,
        v27,
        BYTE2(v25),
        (__int64)v31,
        SHIBYTE(v25),
        (__int64)v30,
        SBYTE1(v25),
        v25,
        SBYTE1(v24),
        v28,
        (__int64)a1);
    if ( v27 >= 2 )
    {
      *a2 = 1;
      if ( TpmInfo < 0 )
        goto LABEL_29;
      v17 = v28;
      v18 = BYTE1(v25);
      v19 = v25;
      v20 = BYTE1(v24);
      v21 = BYTE2(v25);
      if ( BYTE2(v25) )
      {
        if ( !(_WORD)v25 && !BYTE1(v24) && v28 )
          goto LABEL_29;
      }
      *a2 = 0;
      if ( v21 )
      {
        if ( v18 )
        {
          v15 = 23;
          v16 = L"TPM is not satisfactory";
        }
        else if ( v19 )
        {
          v15 = 36;
          v16 = L"TPM has an attestation vulnerability";
        }
        else if ( v20 )
        {
          v15 = 17;
          v16 = L"TPM is locked out";
        }
        else
        {
          if ( v17 )
          {
LABEL_29:
            v8 = 0;
            goto LABEL_30;
          }
          v15 = 34;
          v16 = L"TPM does not support the algorithm";
        }
      }
      else
      {
        v15 = 25;
        v16 = L"TPM not ready for storage";
      }
    }
    else
    {
      v15 = 29;
      v16 = L"TPM not version 2.0 or higher";
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      a3,
      v16,
      v15);
    goto LABEL_29;
  }
  Logger = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogDmGetTpmInfoFailure(Logger, v7, v27, TpmInfo);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    a3,
    L"Generic TPM failure",
    19);
  v8 = TpmInfo;
LABEL_30:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v29);
  return v8;
}

```

## disassembly

```asm
0x180036ea0  push    rbp
0x180036ea2  push    rbx
0x180036ea3  push    rsi
0x180036ea4  push    rdi
0x180036ea5  push    r15
0x180036ea7  lea     rbp, [rsp-3C0h]
0x180036eaf  sub     rsp, 4C0h
0x180036eb6  mov     rax, cs:__security_cookie
0x180036ebd  xor     rax, rsp
0x180036ec0  mov     [rbp+3E0h+var_30], rax
0x180036ec7  mov     rbx, r8
0x180036eca  mov     rdi, rdx
0x180036ecd  mov     rsi, rcx
0x180036ed0  xor     r15d, r15d
0x180036ed3  mov     [rsp+4E0h+var_480], r15d
0x180036ed8  mov     [rsp+4E0h+var_468], r15d
0x180036edd  xor     edx, edx; Val
0x180036edf  mov     r8d, 208h; Size
0x180036ee5  lea     rcx, [rbp+3E0h+var_240]; void *
0x180036eec  call    memset_0
0x180036ef1  xor     edx, edx; Val
0x180036ef3  mov     r8d, 208h; Size
0x180036ef9  lea     rcx, [rbp+3E0h+var_450]; void *
0x180036efd  call    memset_0
0x180036f02  mov     [rsp+4E0h+var_464], 1
0x180036f0a  mov     [rdi], r15b
0x180036f0d  lea     rax, aIstpmready_0; "IsTPMReady"
0x180036f14  mov     [rbp+3E0h+var_460], rax
0x180036f18  lea     rax, [rsp+4E0h+var_480]
0x180036f1d  mov     [rbp+3E0h+var_458], rax
0x180036f21  mov     dword ptr [rsp+4E0h+var_4C0], r15d
0x180036f26  xor     r9d, r9d
0x180036f29  xor     r8d, r8d
0x180036f2c  xor     edx, edx
0x180036f2e  lea     rcx, [rsp+4E0h+var_468]
0x180036f33  call    cs:__imp_?DmGetTpmInfo@@YAJPEAKPEAGK1K@Z; DmGetTpmInfo(ulong *,ushort *,ulong,ushort *,ulong)
0x180036f3a  nop     dword ptr [rax+rax+00h]
0x180036f3f  mov     [rsp+4E0h+var_480], eax
0x180036f43  test    eax, eax
0x180036f45  jns     short loc_180036F7A
0x180036f47  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180036f4c  mov     r9d, [rsp+4E0h+var_480]; int
0x180036f51  mov     r8d, [rsp+4E0h+var_468]; unsigned int
0x180036f56  mov     rcx, rax; this
0x180036f59  call    ?LogDmGetTpmInfoFailure@CEnrollmentLogger@@QEAAXPEBGKJ@Z; CEnrollmentLogger::LogDmGetTpmInfoFailure(ushort const *,ulong,long)
0x180036f5e  lea     r8d, [r15+13h]
0x180036f62  lea     rdx, aGenericTpmFail; "Generic TPM failure"
0x180036f69  mov     rcx, rbx
0x180036f6c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180036f71  mov     ebx, [rsp+4E0h+var_480]
0x180036f75  jmp     loc_180037145
0x180036f7a  lea     rdx, [rsp+4E0h+var_464]
0x180036f7f  mov     rcx, rsi
0x180036f82  call    cs:__imp_?DmGetTpmIsAlgorithmSupported@@YAJPEBGPEAH@Z; DmGetTpmIsAlgorithmSupported(ushort const *,int *)
0x180036f89  nop     dword ptr [rax+rax+00h]
0x180036f8e  mov     [rsp+4E0h+var_480], eax
0x180036f92  test    eax, eax
0x180036f94  jns     short loc_180036FBD
0x180036f96  mov     [rsp+4E0h+var_464], 1
0x180036f9e  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180036fa5  jz      short loc_180036FBD
0x180036fa7  mov     r9d, eax
0x180036faa  lea     r8, aDmgettpmisalgo_0; "DmGetTpmIsAlgorithmSupported"
0x180036fb1  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180036fb8  call    McTemplateU0zd_EventWriteTransfer
0x180036fbd  mov     [rsp+4E0h+var_478], r15d
0x180036fc2  mov     [rsp+4E0h+var_474], 10000h
0x180036fca  mov     qword ptr [rsp+4E0h+var_470], r15
0x180036fcf  lea     rcx, [rsp+4E0h+var_478]
0x180036fd4  call    cs:__imp_?DmGetTpmState@@YAJPEAX@Z; DmGetTpmState(void *)
0x180036fdb  nop     dword ptr [rax+rax+00h]
0x180036fe0  mov     [rsp+4E0h+var_480], eax
0x180036fe4  test    eax, eax
0x180036fe6  jns     short loc_180037007
0x180036fe8  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180036fef  jz      short loc_180037007
0x180036ff1  mov     r9d, eax
0x180036ff4  lea     r8, aDmgettpmstate_0; "DmGetTpmState"
0x180036ffb  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180037002  call    McTemplateU0zd_EventWriteTransfer
0x180037007  lea     rdx, [rbp+3E0h+var_240]; unsigned __int16 *
0x18003700e  mov     ecx, [rsp+4E0h+var_470]; unsigned int
0x180037012  call    ?GetReasonString@@YAXKPEAGK@Z; GetReasonString(ulong,ushort *,ulong)
0x180037017  lea     rdx, [rbp+3E0h+var_450]; unsigned __int16 *
0x18003701b  mov     ecx, [rsp+4E0h+var_470+4]; unsigned int
0x18003701f  call    ?GetReasonString@@YAXKPEAGK@Z; GetReasonString(ulong,ushort *,ulong)
0x180037024  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 2
0x18003702b  jz      short loc_180037087
0x18003702d  movzx   ecx, byte ptr [rsp+4E0h+var_478+1]
0x180037032  movzx   edx, byte ptr [rsp+4E0h+var_474]
0x180037037  movzx   r8d, byte ptr [rsp+4E0h+var_474+1]
0x18003703d  movzx   r10d, byte ptr [rsp+4E0h+var_474+3]
0x180037043  movzx   r9d, byte ptr [rsp+4E0h+var_474+2]
0x180037049  mov     [rsp+4E0h+var_488], rsi
0x18003704e  mov     eax, [rsp+4E0h+var_464]
0x180037052  mov     [rsp+4E0h+var_490], eax
0x180037056  mov     [rsp+4E0h+var_498], ecx
0x18003705a  mov     [rsp+4E0h+var_4A0], edx
0x18003705e  mov     [rsp+4E0h+var_4A8], r8d
0x180037063  lea     rax, [rbp+3E0h+var_450]
0x180037067  mov     [rsp+4E0h+var_4B0], rax
0x18003706c  mov     [rsp+4E0h+var_4B8], r10d
0x180037071  lea     rax, [rbp+3E0h+var_240]
0x180037078  mov     [rsp+4E0h+var_4C0], rax
0x18003707d  mov     r8d, [rsp+4E0h+var_468]
0x180037082  call    McTemplateU0qtztzttttz_EventWriteTransfer
0x180037087  cmp     [rsp+4E0h+var_468], 2
0x18003708c  jnb     short loc_1800370A0
0x18003708e  mov     r8d, 1Dh
0x180037094  lea     rdx, aTpmNotVersion2; "TPM not version 2.0 or higher"
0x18003709b  jmp     loc_18003713A
0x1800370a0  mov     byte ptr [rdi], 1
0x1800370a3  cmp     [rsp+4E0h+var_480], r15d
0x1800370a8  jl      loc_180037142
0x1800370ae  mov     eax, [rsp+4E0h+var_464]
0x1800370b2  mov     r8b, byte ptr [rsp+4E0h+var_474+1]
0x1800370b7  mov     dl, byte ptr [rsp+4E0h+var_474]
0x1800370bb  mov     cl, byte ptr [rsp+4E0h+var_478+1]
0x1800370bf  mov     r9b, byte ptr [rsp+4E0h+var_474+2]
0x1800370c4  test    r9b, r9b
0x1800370c7  jz      short loc_1800370DA
0x1800370c9  test    r8b, r8b
0x1800370cc  jnz     short loc_1800370DA
0x1800370ce  test    dl, dl
0x1800370d0  jnz     short loc_1800370DA
0x1800370d2  test    cl, cl
0x1800370d4  jnz     short loc_1800370DA
0x1800370d6  test    eax, eax
0x1800370d8  jnz     short loc_180037142
0x1800370da  mov     [rdi], r15b
0x1800370dd  test    r9b, r9b
0x1800370e0  jnz     short loc_1800370F1
0x1800370e2  mov     r8d, 19h
0x1800370e8  lea     rdx, aTpmNotReadyFor; "TPM not ready for storage"
0x1800370ef  jmp     short loc_18003713A
0x1800370f1  test    r8b, r8b
0x1800370f4  jz      short loc_180037105
0x1800370f6  mov     r8d, 17h
0x1800370fc  lea     rdx, aTpmIsNotSatisf; "TPM is not satisfactory"
0x180037103  jmp     short loc_18003713A
0x180037105  test    dl, dl
0x180037107  jz      short loc_180037118
0x180037109  mov     r8d, 24h ; '$'
0x18003710f  lea     rdx, aTpmHasAnAttest; "TPM has an attestation vulnerability"
0x180037116  jmp     short loc_18003713A
0x180037118  test    cl, cl
0x18003711a  jz      short loc_18003712B
0x18003711c  mov     r8d, 11h
0x180037122  lea     rdx, aTpmIsLockedOut; "TPM is locked out"
0x180037129  jmp     short loc_18003713A
0x18003712b  test    eax, eax
0x18003712d  jnz     short loc_180037142
0x18003712f  lea     r8d, [rax+22h]
0x180037133  lea     rdx, aTpmDoesNotSupp; "TPM does not support the algorithm"
0x18003713a  mov     rcx, rbx
0x18003713d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180037142  mov     ebx, r15d
0x180037145  lea     rcx, [rbp+3E0h+var_460]; this
0x180037149  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18003714e  mov     eax, ebx
0x180037150  mov     rcx, [rbp+3E0h+var_30]
0x180037157  xor     rcx, rsp; StackCookie
0x18003715a  call    __security_check_cookie
0x18003715f  add     rsp, 4C0h
0x180037166  pop     r15
0x180037168  pop     rdi
0x180037169  pop     rsi
0x18003716a  pop     rbx
0x18003716b  pop     rbp
0x18003716c  retn
```
