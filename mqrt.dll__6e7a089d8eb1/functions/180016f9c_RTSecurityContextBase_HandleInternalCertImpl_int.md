# RTSecurityContextBase::HandleInternalCertImpl(int)

- ea: `0x180016f9c`
- end: `0x1800171a3`
- name: `?HandleInternalCertImpl@RTSecurityContextBase@@AEAAJH@Z`
- size: `519`
- prototype: `__int64 __fastcall(RTSecurityContextBase *__hidden this, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016f30`

## callees

- `0x1800087f8`
- `0x180010b10`
- `0x18001138c`
- `0x1800113b8`
- `0x180013c74`
- `0x1800163ec`
- `0x1800164a8`
- `0x180016f9c`
- `0x1800175f0`
- `0x18001762c`
- `0x180026010`

## import_xrefs

- `ADVAPI32!RegOpenCurrentUser` at `0x180016ffe`
- `ADVAPI32!RegOpenCurrentUser` at `0x180016ffe`
- `KERNEL32!GetLastError` at `0x1800170b4`
- `KERNEL32!GetLastError` at `0x1800170b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RTSecurityContextBase::HandleInternalCertImpl(RTSecurityContextBase *this, int a2)
{
  unsigned int v3; // ebx
  HKEY v5; // rax
  LSTATUS v6; // eax
  unsigned __int16 v7; // r8
  int v8; // eax
  int v9; // ecx
  DWORD LastError; // eax
  __int64 v11; // [rsp+30h] [rbp-18h] BYREF
  void *v12; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+50h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    v3 = -1072824272;
    LogMsgHR(-1072824272, (wchar_t *)L"rt/rtsecctx", 0x7Du);
    return v3;
  }
  v11 = 0;
  v15 = 0;
  *((_DWORD *)this + 16) = 2;
  v5 = 0;
  phkResult = 0;
  if ( a2 )
  {
    v6 = RegOpenCurrentUser(0x20019u, &phkResult);
    v3 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      if ( (v3 & 0x80000000) == 0 )
        goto LABEL_23;
      v7 = 130;
      goto LABEL_21;
    }
    v5 = phkResult;
  }
  v8 = RTGetInternalCert((unsigned int)&v15, (unsigned int)&v11, 0, *((_DWORD *)this + 10), (__int64)v5);
  v3 = v8;
  if ( v8 < 0 )
  {
    v7 = 140;
LABEL_13:
    v9 = v8;
LABEL_22:
    LogMsgHR(v9, (wchar_t *)L"rt/rtsecctx", v7);
LABEL_23:
    CRegHandle::~CRegHandle((CRegHandle *)&phkResult);
    SafeRelease<CMQSigCertificate>(v15);
    SafeRelease<CMQSigCertificate>(v11);
    return v3;
  }
  v12 = 0;
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, void **, unsigned int *))(*(_QWORD *)v15 + 32LL))(v15, &v12, &v13);
  v3 = v8;
  if ( v8 < 0 )
  {
    v7 = 150;
    goto LABEL_13;
  }
  try
  {
    RTSecurityContextBase::AllocateAndCopyUserCert(this, v12, v13);
  }
  catch ( std::bad_alloc )
  {
    LogMsgHR(-1072824281, (wchar_t *)L"rt/rtsecctx", 0xA0u);
    CRegHandle::~CRegHandle((CRegHandle *)&phkResult);
    SafeRelease<CMQSigCertificate>(v15);
    SafeRelease<CMQSigCertificate>(v11);
    return 3222143015LL;
  }
  if ( !(unsigned int)RTSecurityContextBase::SetInternalCryptoProvider(this) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, LastError);
    v7 = 170;
    v3 = -1072824272;
LABEL_21:
    v9 = v3;
    goto LABEL_22;
  }
  RTSecurityContextBase::AllocateAndCopyProviderName(
    this,
    L"Microsoft Enhanced RSA and AES Cryptographic Provider",
    0x36u);
  *((_DWORD *)this + 14) = 24;
  RTSecurityContextBase::SetDefaultProviderHelper(this);
  CRegHandle::~CRegHandle((CRegHandle *)&phkResult);
  SafeRelease<CMQSigCertificate>(v15);
  SafeRelease<CMQSigCertificate>(v11);
  return 0;
}

```

## disassembly

```asm
0x180016f9c  mov     [rsp+arg_8], rbx
0x180016fa1  push    rdi
0x180016fa2  sub     rsp, 40h
0x180016fa6  mov     rdi, rcx
0x180016fa9  cmp     qword ptr [rcx+10h], 0
0x180016fae  jz      short loc_180016FD0
0x180016fb0  mov     r8d, 7Dh ; '}'; unsigned __int16
0x180016fb6  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016fbd  mov     ebx, 0C00E0030h
0x180016fc2  mov     ecx, ebx; int
0x180016fc4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180016fc9  mov     eax, ebx
0x180016fcb  jmp     loc_180017198
0x180016fd0  mov     [rsp+48h+var_18], 0
0x180016fd9  mov     [rsp+48h+arg_18], 0
0x180016fe2  mov     dword ptr [rcx+40h], 2
0x180016fe9  xor     eax, eax
0x180016feb  mov     [rsp+48h+phkResult], rax
0x180016ff0  test    edx, edx
0x180016ff2  jz      short loc_18001702D
0x180016ff4  lea     rdx, [rsp+48h+phkResult]; phkResult
0x180016ff9  mov     ecx, 20019h; samDesired
0x180016ffe  call    cs:__imp_RegOpenCurrentUser
0x180017004  mov     ebx, eax
0x180017006  test    eax, eax
0x180017008  jz      short loc_180017028
0x18001700a  jle     short loc_180017015
0x18001700c  movzx   ebx, ax
0x18001700f  or      ebx, 80070000h
0x180017015  test    ebx, ebx
0x180017017  jns     loc_180017105
0x18001701d  mov     r8d, 82h
0x180017023  jmp     loc_1800170F6
0x180017028  mov     rax, [rsp+48h+phkResult]
0x18001702d  mov     [rsp+48h+var_28], rax
0x180017032  mov     r9d, [rdi+28h]
0x180017036  xor     r8d, r8d
0x180017039  lea     rdx, [rsp+48h+var_18]
0x18001703e  lea     rcx, [rsp+48h+arg_18]
0x180017043  call    RTGetInternalCert
0x180017048  mov     ebx, eax
0x18001704a  test    eax, eax
0x18001704c  jns     short loc_18001705B
0x18001704e  mov     r8d, 8Ch
0x180017054  mov     ecx, eax
0x180017056  jmp     loc_1800170F8
0x18001705b  mov     [rsp+48h+var_10], 0
0x180017064  mov     [rsp+48h+arg_0], 0
0x18001706c  mov     rcx, [rsp+48h+arg_18]
0x180017071  mov     rax, [rcx]
0x180017074  lea     r8, [rsp+48h+arg_0]
0x180017079  lea     rdx, [rsp+48h+var_10]
0x18001707e  mov     rax, [rax+20h]
0x180017082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017087  mov     ebx, eax
0x180017089  test    eax, eax
0x18001708b  jns     short loc_180017095
0x18001708d  mov     r8d, 96h
0x180017093  jmp     short loc_180017054
0x180017095  mov     r8d, [rsp+48h+arg_0]; unsigned int
0x18001709a  mov     rdx, [rsp+48h+var_10]; void *
0x18001709f  mov     rcx, rdi; this
0x1800170a2  call    ?AllocateAndCopyUserCert@RTSecurityContextBase@@IEAAXPEAXK@Z; RTSecurityContextBase::AllocateAndCopyUserCert(void *,ulong)
0x1800170a7  nop
0x1800170a8  mov     rcx, rdi; this
0x1800170ab  call    ?SetInternalCryptoProvider@RTSecurityContextBase@@AEAAHXZ; RTSecurityContextBase::SetInternalCryptoProvider(void)
0x1800170b0  test    eax, eax
0x1800170b2  jnz     short loc_18001712A
0x1800170b4  call    cs:__imp_GetLastError
0x1800170ba  lea     rdx, WPP_GLOBAL_Control
0x1800170c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170c8  cmp     rcx, rdx
0x1800170cb  jz      short loc_1800170EB
0x1800170cd  test    byte ptr [rcx+1Ch], 1
0x1800170d1  jz      short loc_1800170EB
0x1800170d3  mov     edx, 0Ah
0x1800170d8  mov     r9d, eax
0x1800170db  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x1800170e2  mov     rcx, [rcx+10h]
0x1800170e6  call    WPP_SF_d
0x1800170eb  mov     r8d, 0AAh; unsigned __int16
0x1800170f1  mov     ebx, 0C00E0030h
0x1800170f6  mov     ecx, ebx; int
0x1800170f8  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x1800170ff  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017104  nop
0x180017105  lea     rcx, [rsp+48h+phkResult]; this
0x18001710a  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18001710f  nop
0x180017110  mov     rcx, [rsp+48h+arg_18]
0x180017115  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x18001711a  nop
0x18001711b  mov     rcx, [rsp+48h+var_18]
0x180017120  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x180017125  jmp     loc_180016FC9
0x18001712a  mov     r8d, 36h ; '6'; unsigned int
0x180017130  lea     rdx, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180017137  mov     rcx, rdi; this
0x18001713a  call    ?AllocateAndCopyProviderName@RTSecurityContextBase@@IEAAXPEB_WK@Z; RTSecurityContextBase::AllocateAndCopyProviderName(wchar_t const *,ulong)
0x18001713f  mov     dword ptr [rdi+38h], 18h
0x180017146  mov     rcx, rdi; this
0x180017149  call    ?SetDefaultProviderHelper@RTSecurityContextBase@@IEAAXXZ; RTSecurityContextBase::SetDefaultProviderHelper(void)
0x18001714e  nop
0x18001714f  lea     rcx, [rsp+48h+phkResult]; this
0x180017154  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180017159  nop
0x18001715a  mov     rcx, [rsp+48h+arg_18]
0x18001715f  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x180017164  nop
0x180017165  mov     rcx, [rsp+48h+var_18]
0x18001716a  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x18001716f  xor     eax, eax
0x180017171  jmp     short loc_180017198
0x180017173  lea     rcx, [rsp+48h+phkResult]; this
0x180017178  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18001717d  nop
0x18001717e  mov     rcx, [rsp+48h+arg_18]
0x180017183  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x180017188  nop
0x180017189  mov     rcx, [rsp+48h+var_18]
0x18001718e  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x180017193  mov     eax, 0C00E0027h
0x180017198  mov     rbx, [rsp+48h+arg_8]
0x18001719d  add     rsp, 40h
0x1800171a1  pop     rdi
0x1800171a2  retn
```
