# CSecurityInfo::GetDGState(void)

- ea: `0x1800c9100`
- end: `0x1800c9650`
- name: `?GetDGState@CSecurityInfo@@QEBA_KXZ`
- size: `1360`
- prototype: `unsigned __int64 __fastcall(CSecurityInfo *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180014f2c`
- `0x180016748`
- `0x18001db0c`
- `0x18007245c`
- `0x1800724e8`
- `0x180072610`
- `0x1800751a0`
- `0x180075290`
- `0x1800752bc`
- `0x18007f000`
- `0x18007f814`
- `0x1800c9100`
- `0x1800c9660`
- `0x1800c98b0`
- `0x1800c9ca0`
- `0x1800cd1fc`
- `0x1800d10e8`
- `0x18018e010`

## import_xrefs

- `ntdll!NtQuerySecurityPolicy` at `0x1800c95d9`
- `ntdll!NtQuerySecurityPolicy` at `0x1800c95d9`
- `ntdll!NtQuerySystemInformation` at `0x1800c91a7`
- `ntdll!NtQuerySystemInformation` at `0x1800c9258`
- `ntdll!NtQuerySystemInformation` at `0x1800c91a7`
- `ntdll!NtQuerySystemInformation` at `0x1800c9258`

## string_xrefs

- `0x1800c947f`: `SecurityServicesConfigured`
- `0x1800c94cc`: `SELECT SecurityServicesConfigured FROM Win32_DeviceGuard `
- `0x1800c92fe`: `root\CIMV2\Security\MicrosoftTPM`
- `0x1800c9204`: `onecore\base\appcompat\programs\devicecensus\dlls\securityinfo.cpp`
- `0x1800c927c`: `onecore\base\appcompat\programs\devicecensus\dlls\securityinfo.cpp`

## pseudocode

```c
__int64 __fastcall CSecurityInfo::GetDGState(CSecurityInfo *this)
{
  NTSTATUS v2; // eax
  char SecureBootCapable; // al
  NTSTATUS v4; // eax
  char v5; // cl
  char VBSState; // al
  __int64 v7; // rdi
  char v8; // r15
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD *, _QWORD, __int128 *, _QWORD, _QWORD); // r14
  _QWORD *v11; // rdx
  int v12; // ebx
  __int64 v13; // rcx
  char WMIListAttribute; // al
  char RequiredSecurityProperties; // al
  char AvailableSecurityProperties; // al
  int v17; // eax
  const char *v19; // [rsp+28h] [rbp-D8h]
  __int16 v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  int v23[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h]
  unsigned __int16 v26[8]; // [rsp+78h] [rbp-88h] BYREF
  __m128i si128; // [rsp+88h] [rbp-78h]
  unsigned __int16 v28[8]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v29; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v30[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v31; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v32[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v33; // [rsp+E8h] [rbp-18h]
  _OWORD SystemInformation[2]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v21 = (16 * (CSecurityInfo::GetHVCIRunning(this) & 1)) | 1;
  v21 = v21 & 0xFFFFFFFFFFFFFFDFuLL | (32 * (SecurityInfo::GetCGRunning(this) & 1));
  SecurityInfo::GetCGState((v21 & 0x20) != 0, (union _DG_CENSUS__2 *)&v21);
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v2 = NtQuerySystemInformation(SystemContextSwitchInformation|0x80, SystemInformation, 0x20u, 0);
  if ( v2 < 0 )
  {
    if ( v2 != -1073741637 )
      wil::details::in1diag3::Log_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x1B1,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\securityinfo.cpp",
        (const char *)(unsigned int)v2,
        (int)"NtQuerySystemInformation(SystemCodeIntegrityPolicyInformation)",
        v19);
  }
  else
  {
    v21 = v21 & 0xFFFFFFFFFFFFFE3FuLL
        | (8 * (SystemInformation[0] & 0x10 | (8 * (SystemInformation[0] & 1 | (2LL * (SystemInformation[0] & 2))))));
  }
  SecureBootCapable = CSecurityInfo::GetSecureBootCapable(this);
  v21 = v21 & 0xFFFFFFFFFFFFFDFFuLL | ((unsigned __int64)(SecureBootCapable & 1) << 9);
  ReturnLength = 0;
  v20 = 0;
  v4 = NtQuerySystemInformation(SystemObjectInformation|0x80, &v20, 2u, &ReturnLength);
  if ( v4 >= 0 )
  {
    v5 = v20;
  }
  else
  {
    if ( v4 != -2143092730 )
      wil::details::in1diag3::Log_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x298,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\securityinfo.cpp",
        (const char *)(unsigned int)v4,
        (int)"NtQuerySystemInformation(SystemSecureBootInformation)",
        v19);
    v5 = 0;
  }
  v21 = v21 & 0xFFFFFFFFFFFFFBFFuLL | ((unsigned __int64)(v5 & 1) << 10);
  VBSState = CSecurityInfo::GetVBSState(this);
  v7 = 3;
  v21 = v21 & 0xFFFFFFFFFFFFE7FFuLL | ((unsigned __int64)(VBSState & 3) << 11);
  v24 = 0;
  v25 = 0;
  v8 = 0;
  *(_QWORD *)v23 = 0;
  *(_OWORD *)v26 = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)v26, L"root\\CIMV2\\Security\\MicrosoftTPM", 0x20u);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)v30, L"SELECT * FROM Win32_Tpm", 0x17u);
  *(_OWORD *)v28 = 0;
  v29 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)v28, L"Win32_Tpm", 9u);
  *(_OWORD *)v32 = 0;
  v33 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)v32, L"IsEnabled", 9u);
  if ( (int)Utils::ExecuteWmiMethod(v30, v26, v28, v32, (__int64 *)v23) >= 0 )
  {
    v9 = *(_QWORD *)v23;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int128 *, _QWORD, _QWORD))(**(_QWORD **)v23 + 32LL);
    v11 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&ReturnLength, L"IsEnabled");
    if ( v11 )
      v11 = (_QWORD *)*v11;
    v12 = v10(v9, v11, 0, &v24, 0, 0);
    _bstr_t::~_bstr_t((_bstr_t *)&ReturnLength);
    if ( v12 >= 0 )
      v8 = BYTE8(v24);
  }
  std::wstring::~wstring((char **)v32);
  std::wstring::~wstring((char **)v28);
  std::wstring::~wstring((char **)v30);
  std::wstring::~wstring((char **)v26);
  v13 = *(_QWORD *)v23;
  if ( *(_QWORD *)v23 )
  {
    *(_QWORD *)v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v21 = v21 & 0xFFFFFFFFFFFFDFFFuLL | ((unsigned __int64)(v8 & 1) << 13);
  *(_OWORD *)v28 = 0;
  v29 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)v28, L"SecurityServicesConfigured", 0x1Au);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)v30, L"root\\Microsoft\\Windows\\DeviceGuard", 0x22u);
  *(_OWORD *)v26 = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)v26,
    L"SELECT SecurityServicesConfigured FROM Win32_DeviceGuard ",
    0x39u);
  WMIListAttribute = SecurityInfo::GetWMIListAttribute(v26, v30, v28);
  v21 = v21 & 0xFFFFFFFFFFFE3FFFuLL | ((unsigned __int64)(WMIListAttribute & 7) << 14);
  std::wstring::~wstring((char **)v26);
  std::wstring::~wstring((char **)v30);
  std::wstring::~wstring((char **)v28);
  RequiredSecurityProperties = CSecurityInfo::GetRequiredSecurityProperties(this);
  v21 = v21 & 0xFFFFFFFFFF81FFFFuLL | ((unsigned __int64)(RequiredSecurityProperties & 0x3F) << 17);
  AvailableSecurityProperties = SecurityInfo::GetAvailableSecurityProperties(this);
  v21 = v21 & 0xFFFFFFFFC07FFFFFuLL | ((unsigned __int64)(AvailableSecurityProperties & 0x3F) << 23);
  if ( SystemRequirements::IsWindowsCore() )
  {
    ReturnLength = 0;
    LOBYTE(v20) = 0;
    *(_OWORD *)v26 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v26[0]) = 0;
    v23[0] = 1;
    v17 = NtQuerySecurityPolicy(&qword_1801A3378, &qword_1801A3358, &qword_1801A3368, &ReturnLength, &v20, v23);
    if ( v17 )
    {
      if ( v17 == -1073741275 )
        goto LABEL_24;
    }
    else if ( !ReturnLength )
    {
      v7 = ((_BYTE)v20 != 1) + 1LL;
LABEL_24:
      std::string::~string(v26);
      return (v7 << 30) | v21 & 0xE3FFFFFFFLL;
    }
    v7 = 4;
    goto LABEL_24;
  }
  v7 = 0;
  return (v7 << 30) | v21 & 0xE3FFFFFFFLL;
}

```

## disassembly

```asm
0x1800c9100  mov     [rsp-8+arg_8], rbx
0x1800c9105  mov     [rsp-8+arg_10], rsi
0x1800c910a  push    rbp
0x1800c910b  push    rdi
0x1800c910c  push    r13
0x1800c910e  push    r14
0x1800c9110  push    r15
0x1800c9112  lea     rbp, [rsp-20h]
0x1800c9117  sub     rsp, 120h
0x1800c911e  mov     rax, cs:__security_cookie
0x1800c9125  xor     rax, rsp
0x1800c9128  mov     [rbp+40h+var_28], rax
0x1800c912c  mov     rsi, rcx
0x1800c912f  mov     r13d, 1
0x1800c9135  mov     [rsp+140h+var_F8], r13
0x1800c913a  call    ?GetHVCIRunning@CSecurityInfo@@QEBAHXZ; CSecurityInfo::GetHVCIRunning(void)
0x1800c913f  and     rax, r13
0x1800c9142  shl     rax, 4
0x1800c9146  mov     rcx, [rsp+140h+var_F8]
0x1800c914b  and     rcx, 0FFFFFFFFFFFFFFEFh
0x1800c914f  or      rax, rcx
0x1800c9152  mov     [rsp+140h+var_F8], rax
0x1800c9157  mov     rcx, rsi; this
0x1800c915a  call    ?GetCGRunning@SecurityInfo@@QEBAHXZ; SecurityInfo::GetCGRunning(void)
0x1800c915f  and     rax, r13
0x1800c9162  shl     rax, 5
0x1800c9166  mov     rcx, [rsp+140h+var_F8]
0x1800c916b  and     rcx, 0FFFFFFFFFFFFFFDFh
0x1800c916f  or      rax, rcx
0x1800c9172  mov     [rsp+140h+var_F8], rax
0x1800c9177  shr     al, 5
0x1800c917a  and     al, r13b
0x1800c917d  lea     rdx, [rsp+140h+var_F8]; union _DG_CENSUS__2 *
0x1800c9182  mov     cl, al; bool
0x1800c9184  call    ?GetCGState@SecurityInfo@@CAX_NAEAT_DG_CENSUS__2@@@Z; SecurityInfo::GetCGState(bool,_DG_CENSUS__2 &)
0x1800c9189  xorps   xmm0, xmm0
0x1800c918c  movups  [rbp+40h+SystemInformation], xmm0
0x1800c9190  movups  [rbp+40h+var_38], xmm0
0x1800c9194  xor     r9d, r9d; ReturnLength
0x1800c9197  lea     ebx, [r13+1Fh]
0x1800c919b  mov     r8d, ebx; SystemInformationLength
0x1800c919e  lea     rdx, [rbp+40h+SystemInformation]; SystemInformation
0x1800c91a2  mov     ecx, 0A4h; SystemInformationClass
0x1800c91a7  call    cs:__imp_NtQuerySystemInformation
0x1800c91ad  test    eax, eax
0x1800c91af  js      short loc_1800C91EA
0x1800c91b1  mov     rcx, qword ptr [rbp+40h+SystemInformation]
0x1800c91b5  mov     rdx, rcx
0x1800c91b8  and     edx, 2
0x1800c91bb  add     rdx, rdx
0x1800c91be  mov     rax, rcx
0x1800c91c1  and     rax, r13
0x1800c91c4  or      rdx, rax
0x1800c91c7  shl     rdx, 3
0x1800c91cb  and     ecx, 10h
0x1800c91ce  or      rdx, rcx
0x1800c91d1  shl     rdx, 3
0x1800c91d5  mov     rax, [rsp+140h+var_F8]
0x1800c91da  and     rax, 0FFFFFFFFFFFFFE3Fh
0x1800c91e0  or      rdx, rax
0x1800c91e3  mov     [rsp+140h+var_F8], rdx
0x1800c91e8  jmp     short loc_1800C9215
0x1800c91ea  cmp     eax, 0C00000BBh
0x1800c91ef  jz      short loc_1800C9215
0x1800c91f1  mov     rcx, [rbp+48h]; this
0x1800c91f5  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation(SystemCodeInte"...
0x1800c91fc  mov     qword ptr [rsp+140h+var_120], rdx; int
0x1800c9201  mov     r9d, eax; char *
0x1800c9204  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\programs\\dev"...
0x1800c920b  mov     edx, 1B1h; void *
0x1800c9210  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800c9215  mov     rcx, rsi; this
0x1800c9218  call    ?GetSecureBootCapable@CSecurityInfo@@QEBAHXZ; CSecurityInfo::GetSecureBootCapable(void)
0x1800c921d  and     rax, r13
0x1800c9220  shl     rax, 9
0x1800c9224  mov     rcx, [rsp+140h+var_F8]
0x1800c9229  btr     rcx, 9
0x1800c922e  or      rax, rcx
0x1800c9231  mov     [rsp+140h+var_F8], rax
0x1800c9236  mov     [rsp+140h+ReturnLength], 0
0x1800c923e  xor     eax, eax
0x1800c9240  mov     [rsp+140h+var_100], ax
0x1800c9245  lea     r9, [rsp+140h+ReturnLength]; ReturnLength
0x1800c924a  lea     r8d, [rax+2]; SystemInformationLength
0x1800c924e  lea     rdx, [rsp+140h+var_100]; SystemInformation
0x1800c9253  mov     ecx, 91h; SystemInformationClass
0x1800c9258  call    cs:__imp_NtQuerySystemInformation
0x1800c925e  test    eax, eax
0x1800c9260  jns     short loc_1800C9291
0x1800c9262  cmp     eax, 80430006h
0x1800c9267  jz      short loc_1800C928D
0x1800c9269  mov     rcx, [rbp+48h]; this
0x1800c926d  lea     rdx, aNtquerysystemi_0; "NtQuerySystemInformation(SystemSecureBo"...
0x1800c9274  mov     qword ptr [rsp+140h+var_120], rdx; int
0x1800c9279  mov     r9d, eax; char *
0x1800c927c  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\programs\\dev"...
0x1800c9283  mov     edx, 298h; void *
0x1800c9288  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800c928d  xor     ecx, ecx
0x1800c928f  jmp     short loc_1800C9296
0x1800c9291  movzx   ecx, byte ptr [rsp+140h+var_100]
0x1800c9296  and     rcx, r13
0x1800c9299  shl     rcx, 0Ah
0x1800c929d  mov     rax, [rsp+140h+var_F8]
0x1800c92a2  btr     rax, 0Ah
0x1800c92a7  or      rcx, rax
0x1800c92aa  mov     [rsp+140h+var_F8], rcx
0x1800c92af  mov     rcx, rsi; this
0x1800c92b2  call    ?GetVBSState@CSecurityInfo@@QEBAIXZ; CSecurityInfo::GetVBSState(void)
0x1800c92b7  mov     edi, 3
0x1800c92bc  and     rax, rdi
0x1800c92bf  shl     rax, 0Bh
0x1800c92c3  mov     rcx, [rsp+140h+var_F8]
0x1800c92c8  and     rcx, 0FFFFFFFFFFFFE7FFh
0x1800c92cf  or      rax, rcx
0x1800c92d2  mov     [rsp+140h+var_F8], rax
0x1800c92d7  xorps   xmm0, xmm0
0x1800c92da  xor     eax, eax
0x1800c92dc  movups  [rsp+140h+var_E0], xmm0
0x1800c92e1  mov     [rsp+140h+var_D0], rax
0x1800c92e6  xor     r15d, r15d
0x1800c92e9  mov     qword ptr [rsp+140h+var_E8], rax
0x1800c92ee  movups  xmmword ptr [rsp+140h+var_C8], xmm0
0x1800c92f3  xorps   xmm1, xmm1
0x1800c92f6  movdqu  [rbp+40h+var_B8], xmm1
0x1800c92fb  mov     r8, rbx
0x1800c92fe  lea     rdx, aRootCimv2Secur; "root\\CIMV2\\Security\\MicrosoftTPM"
0x1800c9305  lea     rcx, [rsp+140h+var_C8]
0x1800c930a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c930f  nop
0x1800c9310  xorps   xmm0, xmm0
0x1800c9313  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x1800c9317  xorps   xmm1, xmm1
0x1800c931a  movdqu  [rbp+40h+var_78], xmm1
0x1800c931f  lea     r8d, [rdi+14h]
0x1800c9323  lea     rdx, aSelectFromWin3; "SELECT * FROM Win32_Tpm"
0x1800c932a  lea     rcx, [rbp+40h+var_88]
0x1800c932e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c9333  nop
0x1800c9334  xorps   xmm0, xmm0
0x1800c9337  movups  xmmword ptr [rbp+40h+var_A8], xmm0
0x1800c933b  xorps   xmm1, xmm1
0x1800c933e  movdqu  [rbp+40h+var_98], xmm1
0x1800c9343  lea     ebx, [rdi+6]
0x1800c9346  mov     r8d, ebx
0x1800c9349  lea     rdx, aWin32Tpm; "Win32_Tpm"
0x1800c9350  lea     rcx, [rbp+40h+var_A8]
0x1800c9354  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c9359  nop
0x1800c935a  xorps   xmm0, xmm0
0x1800c935d  movups  xmmword ptr [rbp+40h+var_68], xmm0
0x1800c9361  xorps   xmm1, xmm1
0x1800c9364  movdqu  [rbp+40h+var_58], xmm1
0x1800c9369  mov     r8d, ebx
0x1800c936c  lea     rdx, aIsenabled; "IsEnabled"
0x1800c9373  lea     rcx, [rbp+40h+var_68]
0x1800c9377  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c937c  nop
0x1800c937d  lea     rax, [rsp+140h+var_E8]
0x1800c9382  mov     qword ptr [rsp+140h+var_120], rax; int
0x1800c9387  lea     r9, [rbp+40h+var_68]; unsigned __int16 *
0x1800c938b  lea     r8, [rbp+40h+var_A8]; unsigned __int16 *
0x1800c938f  lea     rdx, [rsp+140h+var_C8]; unsigned __int16 *
0x1800c9394  lea     rcx, [rbp+40h+var_88]; unsigned __int16 *
0x1800c9398  call    ?ExecuteWmiMethod@Utils@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000AEAV?$ComPtr@UIWbemClassObject@@@WRL@Microsoft@@@Z; Utils::ExecuteWmiMethod(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,Microsoft::WRL::ComPtr<IWbemClassObject> &)
0x1800c939d  test    eax, eax
0x1800c939f  js      short loc_1800C9405
0x1800c93a1  mov     rbx, qword ptr [rsp+140h+var_E8]
0x1800c93a6  mov     rax, [rbx]
0x1800c93a9  mov     r14, [rax+20h]
0x1800c93ad  lea     rdx, aIsenabled; "IsEnabled"
0x1800c93b4  lea     rcx, [rsp+140h+ReturnLength]; this
0x1800c93b9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800c93be  nop
0x1800c93bf  mov     rdx, [rax]
0x1800c93c2  test    rdx, rdx
0x1800c93c5  jz      short loc_1800C93CA
0x1800c93c7  mov     rdx, [rdx]
0x1800c93ca  mov     [rsp+140h+var_118], 0
0x1800c93d3  mov     qword ptr [rsp+140h+var_120], 0
0x1800c93dc  lea     r9, [rsp+140h+var_E0]
0x1800c93e1  xor     r8d, r8d
0x1800c93e4  mov     rcx, rbx
0x1800c93e7  mov     rax, r14
0x1800c93ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c93ef  mov     ebx, eax
0x1800c93f1  lea     rcx, [rsp+140h+ReturnLength]; this
0x1800c93f6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800c93fb  test    ebx, ebx
0x1800c93fd  js      short loc_1800C9405
0x1800c93ff  movsx   r15d, word ptr [rsp+140h+var_E0+8]
0x1800c9405  lea     rcx, [rbp+40h+var_68]
0x1800c9409  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c940e  nop
0x1800c940f  lea     rcx, [rbp+40h+var_A8]
0x1800c9413  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c9418  nop
0x1800c9419  lea     rcx, [rbp+40h+var_88]
0x1800c941d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c9422  nop
0x1800c9423  lea     rcx, [rsp+140h+var_C8]
0x1800c9428  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c942d  nop
0x1800c942e  mov     rcx, qword ptr [rsp+140h+var_E8]
0x1800c9433  test    rcx, rcx
0x1800c9436  jz      short loc_1800C944E
0x1800c9438  mov     qword ptr [rsp+140h+var_E8], 0
0x1800c9441  mov     rax, [rcx]
0x1800c9444  mov     rax, [rax+10h]
0x1800c9448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c944d  nop
0x1800c944e  mov     ecx, r15d
0x1800c9451  and     rcx, r13
0x1800c9454  shl     rcx, 0Dh
0x1800c9458  mov     rax, [rsp+140h+var_F8]
0x1800c945d  btr     rax, 0Dh
0x1800c9462  or      rcx, rax
0x1800c9465  mov     [rsp+140h+var_F8], rcx
0x1800c946a  xorps   xmm0, xmm0
0x1800c946d  movups  xmmword ptr [rbp+40h+var_A8], xmm0
0x1800c9471  xorps   xmm1, xmm1
0x1800c9474  movdqu  [rbp+40h+var_98], xmm1
0x1800c9479  mov     r8d, 1Ah
0x1800c947f  lea     rdx, aSecurityservic; "SecurityServicesConfigured"
0x1800c9486  lea     rcx, [rbp+40h+var_A8]
0x1800c948a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c948f  nop
0x1800c9490  xorps   xmm0, xmm0
0x1800c9493  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x1800c9497  xorps   xmm1, xmm1
0x1800c949a  movdqu  [rbp+40h+var_78], xmm1
0x1800c949f  mov     r8d, 22h ; '"'
0x1800c94a5  lea     rdx, aRootMicrosoftW; "root\\Microsoft\\Windows\\DeviceGuard"
0x1800c94ac  lea     rcx, [rbp+40h+var_88]
0x1800c94b0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c94b5  nop
0x1800c94b6  xorps   xmm0, xmm0
0x1800c94b9  movups  xmmword ptr [rsp+140h+var_C8], xmm0
0x1800c94be  xorps   xmm1, xmm1
0x1800c94c1  movdqu  [rbp+40h+var_B8], xmm1
0x1800c94c6  mov     r8d, 39h ; '9'
0x1800c94cc  lea     rdx, aSelectSecurity; "SELECT SecurityServicesConfigured FROM "...
0x1800c94d3  lea     rcx, [rsp+140h+var_C8]
0x1800c94d8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c94dd  nop
0x1800c94de  lea     r8, [rbp+40h+var_A8]
0x1800c94e2  lea     rdx, [rbp+40h+var_88]
0x1800c94e6  lea     rcx, [rsp+140h+var_C8]
0x1800c94eb  call    ?GetWMIListAttribute@SecurityInfo@@CAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; SecurityInfo::GetWMIListAttribute(std::wstring const &,std::wstring const &,std::wstring const &)
0x1800c94f0  and     eax, 7
0x1800c94f3  shl     rax, 0Eh
0x1800c94f7  mov     rcx, [rsp+140h+var_F8]
0x1800c94fc  and     rcx, 0FFFFFFFFFFFE3FFFh
0x1800c9503  or      rax, rcx
0x1800c9506  mov     [rsp+140h+var_F8], rax
0x1800c950b  lea     rcx, [rsp+140h+var_C8]
0x1800c9510  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c9515  nop
0x1800c9516  lea     rcx, [rbp+40h+var_88]
0x1800c951a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c951f  nop
0x1800c9520  lea     rcx, [rbp+40h+var_A8]
0x1800c9524  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c9529  mov     rcx, rsi; this
0x1800c952c  call    ?GetRequiredSecurityProperties@CSecurityInfo@@QEBAIXZ; CSecurityInfo::GetRequiredSecurityProperties(void)
0x1800c9531  and     eax, 3Fh
0x1800c9534  shl     rax, 11h
0x1800c9538  mov     rdx, [rsp+140h+var_F8]
0x1800c953d  and     rdx, 0FFFFFFFFFF81FFFFh
0x1800c9544  or      rax, rdx
0x1800c9547  mov     [rsp+140h+var_F8], rax
0x1800c954c  mov     rcx, rsi; this
0x1800c954f  call    ?GetAvailableSecurityProperties@SecurityInfo@@QEBAIXZ; SecurityInfo::GetAvailableSecurityProperties(void)
0x1800c9554  and     eax, 3Fh
0x1800c9557  shl     rax, 17h
0x1800c955b  mov     rcx, [rsp+140h+var_F8]
0x1800c9560  and     rcx, 0FFFFFFFFC07FFFFFh
0x1800c9567  or      rax, rcx
0x1800c956a  mov     [rsp+140h+var_F8], rax
0x1800c956f  call    ?IsWindowsCore@SystemRequirements@@SA_NXZ; SystemRequirements::IsWindowsCore(void)
0x1800c9574  test    al, al
0x1800c9576  jnz     short loc_1800C957F
0x1800c9578  xor     edi, edi
0x1800c957a  jmp     loc_1800C960F
0x1800c957f  mov     [rsp+140h+ReturnLength], 0
0x1800c9587  mov     byte ptr [rsp+140h+var_100], 0
0x1800c958c  xorps   xmm0, xmm0
0x1800c958f  movups  xmmword ptr [rsp+140h+var_C8], xmm0
0x1800c9594  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800c959c  movdqu  [rbp+40h+var_B8], xmm1
0x1800c95a1  mov     byte ptr [rsp+140h+var_C8], 0
0x1800c95a6  mov     [rsp+140h+var_E8], r13d
0x1800c95ab  lea     rax, [rsp+140h+var_E8]
0x1800c95b0  mov     [rsp+140h+var_118], rax
0x1800c95b5  lea     rax, [rsp+140h+var_100]
0x1800c95ba  mov     qword ptr [rsp+140h+var_120], rax
0x1800c95bf  lea     r9, [rsp+140h+ReturnLength]
0x1800c95c4  lea     r8, qword_1801A3368
0x1800c95cb  lea     rdx, qword_1801A3358
0x1800c95d2  lea     rcx, qword_1801A3378
  ... truncated ...
```
