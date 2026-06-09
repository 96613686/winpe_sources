# SecurityInfo::GetDGState(void)

- ea: `0x18007e550`
- end: `0x18007eaa0`
- name: `?GetDGState@SecurityInfo@@QEBA_KXZ`
- size: `1360`
- prototype: `unsigned __int64 __fastcall(SecurityInfo *__hidden this)`
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
- `0x18007e550`
- `0x18007eab0`
- `0x18007f000`
- `0x18007f0f0`
- `0x18007f720`
- `0x18007f814`
- `0x1800cd1fc`
- `0x1800d10e8`
- `0x18018e010`

## import_xrefs

- `ntdll!NtQuerySecurityPolicy` at `0x18007ea29`
- `ntdll!NtQuerySecurityPolicy` at `0x18007ea29`
- `ntdll!NtQuerySystemInformation` at `0x18007e5f7`
- `ntdll!NtQuerySystemInformation` at `0x18007e6a8`
- `ntdll!NtQuerySystemInformation` at `0x18007e5f7`
- `ntdll!NtQuerySystemInformation` at `0x18007e6a8`

## string_xrefs

- `0x18007e654`: `onecore\base\appcompat\programs\devicecensus\dlls\_securityinfo.cpp`
- `0x18007e6cc`: `onecore\base\appcompat\programs\devicecensus\dlls\_securityinfo.cpp`
- `0x18007e8cf`: `SecurityServicesConfigured`
- `0x18007e91c`: `SELECT SecurityServicesConfigured FROM Win32_DeviceGuard `
- `0x18007e74e`: `root\CIMV2\Security\MicrosoftTPM`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SecurityInfo::GetDGState(SecurityInfo *this)
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

  v21 = (16 * (SecurityInfo::GetHVCIRunning(this) & 1)) | 1;
  v21 = v21 & 0xFFFFFFFFFFFFFFDFuLL | (32 * (SecurityInfo::GetCGRunning(this) & 1));
  SecurityInfo::GetCGState((v21 & 0x20) != 0, (union _DG_CENSUS__2 *)&v21);
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v2 = NtQuerySystemInformation(SystemContextSwitchInformation|0x80, SystemInformation, 0x20u, 0);
  if ( v2 < 0 )
  {
    if ( v2 != -1073741637 )
      wil::details::in1diag3::Log_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\_securityinfo.cpp",
        (const char *)(unsigned int)v2,
        (int)"NtQuerySystemInformation(SystemCodeIntegrityPolicyInformation)",
        v19);
  }
  else
  {
    v21 = v21 & 0xFFFFFFFFFFFFFE3FuLL
        | (8 * (SystemInformation[0] & 0x10 | (8 * (SystemInformation[0] & 1 | (2LL * (SystemInformation[0] & 2))))));
  }
  SecureBootCapable = SecurityInfo::GetSecureBootCapable(this);
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
        (void *)0x294,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\_securityinfo.cpp",
        (const char *)(unsigned int)v4,
        (int)"NtQuerySystemInformation(SystemSecureBootInformation)",
        v19);
    v5 = 0;
  }
  v21 = v21 & 0xFFFFFFFFFFFFFBFFuLL | ((unsigned __int64)(v5 & 1) << 10);
  VBSState = SecurityInfo::GetVBSState(this);
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
    v17 = NtQuerySecurityPolicy(&qword_1801A2A78, &qword_1801A2A68, &qword_1801A2A58, &ReturnLength, &v20, v23);
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
0x18007e550  mov     [rsp-8+arg_8], rbx
0x18007e555  mov     [rsp-8+arg_10], rsi
0x18007e55a  push    rbp
0x18007e55b  push    rdi
0x18007e55c  push    r13
0x18007e55e  push    r14
0x18007e560  push    r15
0x18007e562  lea     rbp, [rsp-20h]
0x18007e567  sub     rsp, 120h
0x18007e56e  mov     rax, cs:__security_cookie
0x18007e575  xor     rax, rsp
0x18007e578  mov     [rbp+40h+var_28], rax
0x18007e57c  mov     rsi, rcx
0x18007e57f  mov     r13d, 1
0x18007e585  mov     [rsp+140h+var_F8], r13
0x18007e58a  call    ?GetHVCIRunning@SecurityInfo@@QEBAHXZ; SecurityInfo::GetHVCIRunning(void)
0x18007e58f  and     rax, r13
0x18007e592  shl     rax, 4
0x18007e596  mov     rcx, [rsp+140h+var_F8]
0x18007e59b  and     rcx, 0FFFFFFFFFFFFFFEFh
0x18007e59f  or      rax, rcx
0x18007e5a2  mov     [rsp+140h+var_F8], rax
0x18007e5a7  mov     rcx, rsi; this
0x18007e5aa  call    ?GetCGRunning@SecurityInfo@@QEBAHXZ; SecurityInfo::GetCGRunning(void)
0x18007e5af  and     rax, r13
0x18007e5b2  shl     rax, 5
0x18007e5b6  mov     rcx, [rsp+140h+var_F8]
0x18007e5bb  and     rcx, 0FFFFFFFFFFFFFFDFh
0x18007e5bf  or      rax, rcx
0x18007e5c2  mov     [rsp+140h+var_F8], rax
0x18007e5c7  shr     al, 5
0x18007e5ca  and     al, r13b
0x18007e5cd  lea     rdx, [rsp+140h+var_F8]; union _DG_CENSUS__2 *
0x18007e5d2  mov     cl, al; bool
0x18007e5d4  call    ?GetCGState@SecurityInfo@@CAX_NAEAT_DG_CENSUS__2@@@Z; SecurityInfo::GetCGState(bool,_DG_CENSUS__2 &)
0x18007e5d9  xorps   xmm0, xmm0
0x18007e5dc  movups  [rbp+40h+SystemInformation], xmm0
0x18007e5e0  movups  [rbp+40h+var_38], xmm0
0x18007e5e4  xor     r9d, r9d; ReturnLength
0x18007e5e7  lea     ebx, [r13+1Fh]
0x18007e5eb  mov     r8d, ebx; SystemInformationLength
0x18007e5ee  lea     rdx, [rbp+40h+SystemInformation]; SystemInformation
0x18007e5f2  mov     ecx, 0A4h; SystemInformationClass
0x18007e5f7  call    cs:__imp_NtQuerySystemInformation
0x18007e5fd  test    eax, eax
0x18007e5ff  js      short loc_18007E63A
0x18007e601  mov     rcx, qword ptr [rbp+40h+SystemInformation]
0x18007e605  mov     rdx, rcx
0x18007e608  and     edx, 2
0x18007e60b  add     rdx, rdx
0x18007e60e  mov     rax, rcx
0x18007e611  and     rax, r13
0x18007e614  or      rdx, rax
0x18007e617  shl     rdx, 3
0x18007e61b  and     ecx, 10h
0x18007e61e  or      rdx, rcx
0x18007e621  shl     rdx, 3
0x18007e625  mov     rax, [rsp+140h+var_F8]
0x18007e62a  and     rax, 0FFFFFFFFFFFFFE3Fh
0x18007e630  or      rdx, rax
0x18007e633  mov     [rsp+140h+var_F8], rdx
0x18007e638  jmp     short loc_18007E665
0x18007e63a  cmp     eax, 0C00000BBh
0x18007e63f  jz      short loc_18007E665
0x18007e641  mov     rcx, [rbp+48h]; this
0x18007e645  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation(SystemCodeInte"...
0x18007e64c  mov     qword ptr [rsp+140h+var_120], rdx; int
0x18007e651  mov     r9d, eax; char *
0x18007e654  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appcompat\\programs\\dev"...
0x18007e65b  mov     edx, 1B0h; void *
0x18007e660  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18007e665  mov     rcx, rsi; this
0x18007e668  call    ?GetSecureBootCapable@SecurityInfo@@QEBAHXZ; SecurityInfo::GetSecureBootCapable(void)
0x18007e66d  and     rax, r13
0x18007e670  shl     rax, 9
0x18007e674  mov     rcx, [rsp+140h+var_F8]
0x18007e679  btr     rcx, 9
0x18007e67e  or      rax, rcx
0x18007e681  mov     [rsp+140h+var_F8], rax
0x18007e686  mov     [rsp+140h+ReturnLength], 0
0x18007e68e  xor     eax, eax
0x18007e690  mov     [rsp+140h+var_100], ax
0x18007e695  lea     r9, [rsp+140h+ReturnLength]; ReturnLength
0x18007e69a  lea     r8d, [rax+2]; SystemInformationLength
0x18007e69e  lea     rdx, [rsp+140h+var_100]; SystemInformation
0x18007e6a3  mov     ecx, 91h; SystemInformationClass
0x18007e6a8  call    cs:__imp_NtQuerySystemInformation
0x18007e6ae  test    eax, eax
0x18007e6b0  jns     short loc_18007E6E1
0x18007e6b2  cmp     eax, 80430006h
0x18007e6b7  jz      short loc_18007E6DD
0x18007e6b9  mov     rcx, [rbp+48h]; this
0x18007e6bd  lea     rdx, aNtquerysystemi_0; "NtQuerySystemInformation(SystemSecureBo"...
0x18007e6c4  mov     qword ptr [rsp+140h+var_120], rdx; int
0x18007e6c9  mov     r9d, eax; char *
0x18007e6cc  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appcompat\\programs\\dev"...
0x18007e6d3  mov     edx, 294h; void *
0x18007e6d8  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18007e6dd  xor     ecx, ecx
0x18007e6df  jmp     short loc_18007E6E6
0x18007e6e1  movzx   ecx, byte ptr [rsp+140h+var_100]
0x18007e6e6  and     rcx, r13
0x18007e6e9  shl     rcx, 0Ah
0x18007e6ed  mov     rax, [rsp+140h+var_F8]
0x18007e6f2  btr     rax, 0Ah
0x18007e6f7  or      rcx, rax
0x18007e6fa  mov     [rsp+140h+var_F8], rcx
0x18007e6ff  mov     rcx, rsi; this
0x18007e702  call    ?GetVBSState@SecurityInfo@@QEBAIXZ; SecurityInfo::GetVBSState(void)
0x18007e707  mov     edi, 3
0x18007e70c  and     rax, rdi
0x18007e70f  shl     rax, 0Bh
0x18007e713  mov     rcx, [rsp+140h+var_F8]
0x18007e718  and     rcx, 0FFFFFFFFFFFFE7FFh
0x18007e71f  or      rax, rcx
0x18007e722  mov     [rsp+140h+var_F8], rax
0x18007e727  xorps   xmm0, xmm0
0x18007e72a  xor     eax, eax
0x18007e72c  movups  [rsp+140h+var_E0], xmm0
0x18007e731  mov     [rsp+140h+var_D0], rax
0x18007e736  xor     r15d, r15d
0x18007e739  mov     qword ptr [rsp+140h+var_E8], rax
0x18007e73e  movups  xmmword ptr [rsp+140h+var_C8], xmm0
0x18007e743  xorps   xmm1, xmm1
0x18007e746  movdqu  [rbp+40h+var_B8], xmm1
0x18007e74b  mov     r8, rbx
0x18007e74e  lea     rdx, aRootCimv2Secur; "root\\CIMV2\\Security\\MicrosoftTPM"
0x18007e755  lea     rcx, [rsp+140h+var_C8]
0x18007e75a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e75f  nop
0x18007e760  xorps   xmm0, xmm0
0x18007e763  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x18007e767  xorps   xmm1, xmm1
0x18007e76a  movdqu  [rbp+40h+var_78], xmm1
0x18007e76f  lea     r8d, [rdi+14h]
0x18007e773  lea     rdx, aSelectFromWin3; "SELECT * FROM Win32_Tpm"
0x18007e77a  lea     rcx, [rbp+40h+var_88]
0x18007e77e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e783  nop
0x18007e784  xorps   xmm0, xmm0
0x18007e787  movups  xmmword ptr [rbp+40h+var_A8], xmm0
0x18007e78b  xorps   xmm1, xmm1
0x18007e78e  movdqu  [rbp+40h+var_98], xmm1
0x18007e793  lea     ebx, [rdi+6]
0x18007e796  mov     r8d, ebx
0x18007e799  lea     rdx, aWin32Tpm; "Win32_Tpm"
0x18007e7a0  lea     rcx, [rbp+40h+var_A8]
0x18007e7a4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e7a9  nop
0x18007e7aa  xorps   xmm0, xmm0
0x18007e7ad  movups  xmmword ptr [rbp+40h+var_68], xmm0
0x18007e7b1  xorps   xmm1, xmm1
0x18007e7b4  movdqu  [rbp+40h+var_58], xmm1
0x18007e7b9  mov     r8d, ebx
0x18007e7bc  lea     rdx, aIsenabled; "IsEnabled"
0x18007e7c3  lea     rcx, [rbp+40h+var_68]
0x18007e7c7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e7cc  nop
0x18007e7cd  lea     rax, [rsp+140h+var_E8]
0x18007e7d2  mov     qword ptr [rsp+140h+var_120], rax; int
0x18007e7d7  lea     r9, [rbp+40h+var_68]; unsigned __int16 *
0x18007e7db  lea     r8, [rbp+40h+var_A8]; unsigned __int16 *
0x18007e7df  lea     rdx, [rsp+140h+var_C8]; unsigned __int16 *
0x18007e7e4  lea     rcx, [rbp+40h+var_88]; unsigned __int16 *
0x18007e7e8  call    ?ExecuteWmiMethod@Utils@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000AEAV?$ComPtr@UIWbemClassObject@@@WRL@Microsoft@@@Z; Utils::ExecuteWmiMethod(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,Microsoft::WRL::ComPtr<IWbemClassObject> &)
0x18007e7ed  test    eax, eax
0x18007e7ef  js      short loc_18007E855
0x18007e7f1  mov     rbx, qword ptr [rsp+140h+var_E8]
0x18007e7f6  mov     rax, [rbx]
0x18007e7f9  mov     r14, [rax+20h]
0x18007e7fd  lea     rdx, aIsenabled; "IsEnabled"
0x18007e804  lea     rcx, [rsp+140h+ReturnLength]; this
0x18007e809  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18007e80e  nop
0x18007e80f  mov     rdx, [rax]
0x18007e812  test    rdx, rdx
0x18007e815  jz      short loc_18007E81A
0x18007e817  mov     rdx, [rdx]
0x18007e81a  mov     [rsp+140h+var_118], 0
0x18007e823  mov     qword ptr [rsp+140h+var_120], 0
0x18007e82c  lea     r9, [rsp+140h+var_E0]
0x18007e831  xor     r8d, r8d
0x18007e834  mov     rcx, rbx
0x18007e837  mov     rax, r14
0x18007e83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e83f  mov     ebx, eax
0x18007e841  lea     rcx, [rsp+140h+ReturnLength]; this
0x18007e846  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18007e84b  test    ebx, ebx
0x18007e84d  js      short loc_18007E855
0x18007e84f  movsx   r15d, word ptr [rsp+140h+var_E0+8]
0x18007e855  lea     rcx, [rbp+40h+var_68]
0x18007e859  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e85e  nop
0x18007e85f  lea     rcx, [rbp+40h+var_A8]
0x18007e863  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e868  nop
0x18007e869  lea     rcx, [rbp+40h+var_88]
0x18007e86d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e872  nop
0x18007e873  lea     rcx, [rsp+140h+var_C8]
0x18007e878  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e87d  nop
0x18007e87e  mov     rcx, qword ptr [rsp+140h+var_E8]
0x18007e883  test    rcx, rcx
0x18007e886  jz      short loc_18007E89E
0x18007e888  mov     qword ptr [rsp+140h+var_E8], 0
0x18007e891  mov     rax, [rcx]
0x18007e894  mov     rax, [rax+10h]
0x18007e898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e89d  nop
0x18007e89e  mov     ecx, r15d
0x18007e8a1  and     rcx, r13
0x18007e8a4  shl     rcx, 0Dh
0x18007e8a8  mov     rax, [rsp+140h+var_F8]
0x18007e8ad  btr     rax, 0Dh
0x18007e8b2  or      rcx, rax
0x18007e8b5  mov     [rsp+140h+var_F8], rcx
0x18007e8ba  xorps   xmm0, xmm0
0x18007e8bd  movups  xmmword ptr [rbp+40h+var_A8], xmm0
0x18007e8c1  xorps   xmm1, xmm1
0x18007e8c4  movdqu  [rbp+40h+var_98], xmm1
0x18007e8c9  mov     r8d, 1Ah
0x18007e8cf  lea     rdx, aSecurityservic; "SecurityServicesConfigured"
0x18007e8d6  lea     rcx, [rbp+40h+var_A8]
0x18007e8da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e8df  nop
0x18007e8e0  xorps   xmm0, xmm0
0x18007e8e3  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x18007e8e7  xorps   xmm1, xmm1
0x18007e8ea  movdqu  [rbp+40h+var_78], xmm1
0x18007e8ef  mov     r8d, 22h ; '"'
0x18007e8f5  lea     rdx, aRootMicrosoftW; "root\\Microsoft\\Windows\\DeviceGuard"
0x18007e8fc  lea     rcx, [rbp+40h+var_88]
0x18007e900  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e905  nop
0x18007e906  xorps   xmm0, xmm0
0x18007e909  movups  xmmword ptr [rsp+140h+var_C8], xmm0
0x18007e90e  xorps   xmm1, xmm1
0x18007e911  movdqu  [rbp+40h+var_B8], xmm1
0x18007e916  mov     r8d, 39h ; '9'
0x18007e91c  lea     rdx, aSelectSecurity; "SELECT SecurityServicesConfigured FROM "...
0x18007e923  lea     rcx, [rsp+140h+var_C8]
0x18007e928  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e92d  nop
0x18007e92e  lea     r8, [rbp+40h+var_A8]
0x18007e932  lea     rdx, [rbp+40h+var_88]
0x18007e936  lea     rcx, [rsp+140h+var_C8]
0x18007e93b  call    ?GetWMIListAttribute@SecurityInfo@@CAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; SecurityInfo::GetWMIListAttribute(std::wstring const &,std::wstring const &,std::wstring const &)
0x18007e940  and     eax, 7
0x18007e943  shl     rax, 0Eh
0x18007e947  mov     rcx, [rsp+140h+var_F8]
0x18007e94c  and     rcx, 0FFFFFFFFFFFE3FFFh
0x18007e953  or      rax, rcx
0x18007e956  mov     [rsp+140h+var_F8], rax
0x18007e95b  lea     rcx, [rsp+140h+var_C8]
0x18007e960  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e965  nop
0x18007e966  lea     rcx, [rbp+40h+var_88]
0x18007e96a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e96f  nop
0x18007e970  lea     rcx, [rbp+40h+var_A8]
0x18007e974  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e979  mov     rcx, rsi; this
0x18007e97c  call    ?GetRequiredSecurityProperties@CSecurityInfo@@QEBAIXZ; CSecurityInfo::GetRequiredSecurityProperties(void)
0x18007e981  and     eax, 3Fh
0x18007e984  shl     rax, 11h
0x18007e988  mov     rdx, [rsp+140h+var_F8]
0x18007e98d  and     rdx, 0FFFFFFFFFF81FFFFh
0x18007e994  or      rax, rdx
0x18007e997  mov     [rsp+140h+var_F8], rax
0x18007e99c  mov     rcx, rsi; this
0x18007e99f  call    ?GetAvailableSecurityProperties@SecurityInfo@@QEBAIXZ; SecurityInfo::GetAvailableSecurityProperties(void)
0x18007e9a4  and     eax, 3Fh
0x18007e9a7  shl     rax, 17h
0x18007e9ab  mov     rcx, [rsp+140h+var_F8]
0x18007e9b0  and     rcx, 0FFFFFFFFC07FFFFFh
0x18007e9b7  or      rax, rcx
0x18007e9ba  mov     [rsp+140h+var_F8], rax
0x18007e9bf  call    ?IsWindowsCore@SystemRequirements@@SA_NXZ; SystemRequirements::IsWindowsCore(void)
0x18007e9c4  test    al, al
0x18007e9c6  jnz     short loc_18007E9CF
0x18007e9c8  xor     edi, edi
0x18007e9ca  jmp     loc_18007EA5F
0x18007e9cf  mov     [rsp+140h+ReturnLength], 0
0x18007e9d7  mov     byte ptr [rsp+140h+var_100], 0
0x18007e9dc  xorps   xmm0, xmm0
0x18007e9df  movups  xmmword ptr [rsp+140h+var_C8], xmm0
0x18007e9e4  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18007e9ec  movdqu  [rbp+40h+var_B8], xmm1
0x18007e9f1  mov     byte ptr [rsp+140h+var_C8], 0
0x18007e9f6  mov     [rsp+140h+var_E8], r13d
0x18007e9fb  lea     rax, [rsp+140h+var_E8]
0x18007ea00  mov     [rsp+140h+var_118], rax
0x18007ea05  lea     rax, [rsp+140h+var_100]
0x18007ea0a  mov     qword ptr [rsp+140h+var_120], rax
0x18007ea0f  lea     r9, [rsp+140h+ReturnLength]
0x18007ea14  lea     r8, qword_1801A2A58
0x18007ea1b  lea     rdx, qword_1801A2A68
0x18007ea22  lea     rcx, qword_1801A2A78
  ... truncated ...
```
