# RdpEdpPolicyManager::TryApplyProcessUIPolicy(void)

- ea: `0x140098734`
- end: `0x140098a4b`
- name: `?TryApplyProcessUIPolicy@RdpEdpPolicyManager@@QEAAJXZ`
- size: `791`
- prototype: `__int64 __fastcall(RdpEdpPolicyManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140014918`

## callees

- `0x140003b08`
- `0x140003b2c`
- `0x1400610b0`
- `0x140097f3c`
- `0x140098000`
- `0x1400984d8`
- `0x1400986c8`
- `0x140098734`
- `0x140109c18`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140098788`
- `KERNEL32!GetCurrentProcess` at `0x140098788`
- `KERNEL32!GetLastError` at `0x1400987a4`
- `KERNEL32!GetLastError` at `0x1400987a4`
- `ADVAPI32!OpenProcessToken` at `0x14009879a`
- `ADVAPI32!OpenProcessToken` at `0x14009879a`

## string_xrefs

- `0x1400988ed`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`
- `0x1400987c1`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x14009888a`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x140098930`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x1400989b6`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x1400987b0`: `OpenProcessToken failed. GetLastError[0x%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RdpEdpPolicyManager::TryApplyProcessUIPolicy(RdpEdpPolicyManager *this)
{
  const unsigned __int16 **v2; // r14
  HANDLE CurrentProcess; // rax
  signed int LastError; // ebx
  int EnterpriseIds; // eax
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, _BYTE *); // rbx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[8]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v13; // [rsp+48h] [rbp-60h] BYREF
  size_t Size; // [rsp+50h] [rbp-58h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-48h] BYREF
  const unsigned __int16 **v16; // [rsp+68h] [rbp-40h]
  __int64 v17; // [rsp+70h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-30h] BYREF
  __int64 v19; // [rsp+90h] [rbp-18h]

  v17 = -2;
  v2 = 0;
  v16 = 0;
  TokenHandle = (void *)-1LL;
  Size = 0;
  v13 = 0;
  v12[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( (unsigned int)RdpEdpSrpApi::SrpGetEnterpriseIds(
                         (RdpEdpPolicyManager *)((char *)this + 64),
                         TokenHandle,
                         (unsigned int *)&Size,
                         0,
                         (unsigned int *)&Size + 1) == -2147024774 )
    {
      v2 = (const unsigned __int16 **)operator new((unsigned int)Size);
      v16 = v2;
      EnterpriseIds = RdpEdpSrpApi::SrpGetEnterpriseIds(
                        (RdpEdpPolicyManager *)((char *)this + 64),
                        TokenHandle,
                        (unsigned int *)&Size,
                        v2,
                        (unsigned int *)&Size + 1);
      LastError = EnterpriseIds;
      if ( EnterpriseIds < 0 )
      {
        TRC_TraceBufferW(
          3,
          512,
          933,
          (int)L"RdpEdpPolicyManager::TryApplyProcessUIPolicy",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"SrpGetEnterpriseIds failed. hr[0x%x]",
          EnterpriseIds);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(&v13);
        goto LABEL_19;
      }
      if ( v2 && HIDWORD(Size) )
      {
        v19 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Security.EnterpriseData.ProtectionPolicyManager",
          0x38u,
          0x37u);
        v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>>(
               v19,
               &v13);
        LastError = v6;
        if ( v6 >= 0 )
        {
          v7 = v13;
          v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v13 + 56LL);
          v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v2);
          v10 = v8(v7, *(_QWORD *)(v9 + 24), v12);
          LastError = v10;
          if ( v10 >= 0 )
            LastError = 0;
          else
            TRC_TraceBufferW(
              3,
              512,
              952,
              (int)L"RdpEdpPolicyManager::TryApplyProcessUIPolicy",
              (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
              0,
              L"TryApplyProcessUIPolicy failed. hr[0x%x]",
              v10);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(&v13);
        }
        else
        {
          TRC_TraceBufferW(
            3,
            512,
            946,
            (int)L"RdpEdpPolicyManager::TryApplyProcessUIPolicy",
            (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
            0,
            L"GetActivationFactory<IProtectionPolicyManagerStatics> failed. hr[0x%x]",
            v6);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(&v13);
        }
        goto LABEL_20;
      }
    }
    LastError = 1;
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(&v13);
LABEL_19:
    if ( !v2 )
      return (unsigned int)LastError;
LABEL_20:
    operator delete(v2);
    return (unsigned int)LastError;
  }
  LastError = GetLastError();
  TRC_TraceBufferW(
    3,
    512,
    909,
    (int)L"RdpEdpPolicyManager::TryApplyProcessUIPolicy",
    (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
    0,
    L"OpenProcessToken failed. GetLastError[0x%x]",
    LastError);
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    LastError = -2147467259;
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(&v13);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140098734  mov     r11, rsp
0x140098737  push    r14
0x140098739  sub     rsp, 0A0h
0x140098740  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x140098748  mov     [r11+10h], rbx
0x14009874c  mov     [r11+18h], rdi
0x140098750  mov     rax, cs:__security_cookie
0x140098757  xor     rax, rsp
0x14009875a  mov     [rsp+0A8h+var_10], rax
0x140098762  mov     rbx, rcx
0x140098765  xor     r14d, r14d
0x140098768  mov     [rsp+0A8h+var_40], r14
0x14009876d  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFFh
0x140098775  mov     dword ptr [rsp+0A8h+Size], r14d
0x14009877a  mov     dword ptr [rsp+0A8h+Size+4], r14d
0x14009877f  mov     [r11-60h], r14
0x140098783  mov     [rsp+0A8h+var_68], r14b
0x140098788  call    cs:__imp_GetCurrentProcess
0x14009878e  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x140098793  lea     edx, [r14+8]; DesiredAccess
0x140098797  mov     rcx, rax; ProcessHandle
0x14009879a  call    cs:__imp_OpenProcessToken
0x1400987a0  test    eax, eax
0x1400987a2  jnz     short loc_14009880F
0x1400987a4  call    cs:__imp_GetLastError
0x1400987aa  mov     ebx, eax
0x1400987ac  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x1400987b0  lea     rax, aOpenprocesstok_0; "OpenProcessToken failed. GetLastError[0"...
0x1400987b7  mov     [rsp+0A8h+pszFormat], rax; pszFormat
0x1400987bc  mov     qword ptr [rsp+0A8h+var_80], r14; int
0x1400987c1  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x1400987c8  mov     [rsp+0A8h+var_88], rax; int
0x1400987cd  lea     r9, aRdpedppolicyma_3; "RdpEdpPolicyManager::TryApplyProcessUIP"...
0x1400987d4  mov     edx, 200h; int
0x1400987d9  lea     ecx, [r14+3]; int
0x1400987dd  mov     r8d, 38Dh; int
0x1400987e3  call    TRC_TraceBufferW
0x1400987e8  test    ebx, ebx
0x1400987ea  jle     short loc_1400987F5
0x1400987ec  movzx   ebx, bx
0x1400987ef  or      ebx, 80070000h
0x1400987f5  mov     eax, 80004005h
0x1400987fa  test    ebx, ebx
0x1400987fc  cmovns  ebx, eax
0x1400987ff  lea     rcx, [rsp+0A8h+var_60]
0x140098804  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x140098809  nop
0x14009880a  jmp     loc_140098A23
0x14009880f  lea     rax, [rsp+0A8h+Size+4]
0x140098814  mov     [rsp+0A8h+var_88], rax; unsigned int *
0x140098819  xor     r9d, r9d; unsigned __int16 **
0x14009881c  lea     r8, [rsp+0A8h+Size]; unsigned int *
0x140098821  mov     rdx, [rsp+0A8h+TokenHandle]; void *
0x140098826  lea     rcx, [rbx+40h]; this
0x14009882a  call    ?SrpGetEnterpriseIds@RdpEdpSrpApi@@QEAAJPEAXPEAKPEAPEBG1@Z; RdpEdpSrpApi::SrpGetEnterpriseIds(void *,ulong *,ushort const * *,ulong *)
0x14009882f  cmp     eax, 8007007Ah
0x140098834  jnz     loc_1400989FB
0x14009883a  mov     ecx, dword ptr [rsp+0A8h+Size]; Size
0x14009883e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140098843  mov     r14, rax
0x140098846  mov     [rsp+0A8h+var_40], rax
0x14009884b  lea     rax, [rsp+0A8h+Size+4]
0x140098850  mov     [rsp+0A8h+var_88], rax; unsigned int *
0x140098855  mov     r9, r14; unsigned __int16 **
0x140098858  lea     r8, [rsp+0A8h+Size]; unsigned int *
0x14009885d  mov     rdx, [rsp+0A8h+TokenHandle]; void *
0x140098862  lea     rcx, [rbx+40h]; this
0x140098866  call    ?SrpGetEnterpriseIds@RdpEdpSrpApi@@QEAAJPEAXPEAKPEAPEBG1@Z; RdpEdpSrpApi::SrpGetEnterpriseIds(void *,ulong *,ushort const * *,ulong *)
0x14009886b  mov     ebx, eax
0x14009886d  test    eax, eax
0x14009886f  jns     short loc_1400988C3
0x140098871  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x140098875  lea     rax, aSrpgetenterpri; "SrpGetEnterpriseIds failed. hr[0x%x]"
0x14009887c  mov     [rsp+0A8h+pszFormat], rax; pszFormat
0x140098881  mov     qword ptr [rsp+0A8h+var_80], 0; int
0x14009888a  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x140098891  mov     [rsp+0A8h+var_88], rax; int
0x140098896  lea     r9, aRdpedppolicyma_3; "RdpEdpPolicyManager::TryApplyProcessUIP"...
0x14009889d  mov     edx, 200h; int
0x1400988a2  mov     ecx, 3; int
0x1400988a7  mov     r8d, 3A5h; int
0x1400988ad  call    TRC_TraceBufferW
0x1400988b2  nop
0x1400988b3  lea     rcx, [rsp+0A8h+var_60]
0x1400988b8  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x1400988bd  nop
0x1400988be  jmp     loc_140098A16
0x1400988c3  test    r14, r14
0x1400988c6  jz      loc_1400989FB
0x1400988cc  cmp     dword ptr [rsp+0A8h+Size+4], 0
0x1400988d1  jz      loc_1400989FB
0x1400988d7  mov     [rsp+0A8h+var_18], 0
0x1400988e3  mov     r9d, 37h ; '7'; unsigned int
0x1400988e9  lea     r8d, [r9+1]; unsigned int
0x1400988ed  lea     rdx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyManager@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x1400988f4  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1400988f9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400988fe  nop
0x1400988ff  lea     rdx, [rsp+0A8h+var_60]
0x140098904  mov     rcx, [rsp+0A8h+var_18]
0x14009890c  call    ??$GetActivationFactory@V?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>>)
0x140098911  mov     ebx, eax
0x140098913  test    eax, eax
0x140098915  jns     short loc_140098969
0x140098917  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x14009891b  lea     rax, aGetactivationf_1; "GetActivationFactory<IProtectionPolicyM"...
0x140098922  mov     [rsp+0A8h+pszFormat], rax; pszFormat
0x140098927  mov     qword ptr [rsp+0A8h+var_80], 0; int
0x140098930  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x140098937  mov     [rsp+0A8h+var_88], rax; int
0x14009893c  lea     r9, aRdpedppolicyma_3; "RdpEdpPolicyManager::TryApplyProcessUIP"...
0x140098943  mov     edx, 200h; int
0x140098948  mov     ecx, 3; int
0x14009894d  mov     r8d, 3B2h; int
0x140098953  call    TRC_TraceBufferW
0x140098958  nop
0x140098959  lea     rcx, [rsp+0A8h+var_60]
0x14009895e  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x140098963  nop
0x140098964  jmp     loc_140098A1B
0x140098969  mov     rdi, [rsp+0A8h+var_60]
0x14009896e  mov     rax, [rdi]
0x140098971  mov     rbx, [rax+38h]
0x140098975  mov     rdx, r14
0x140098978  lea     rcx, [rsp+0A8h+hstringHeader]
0x14009897d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140098982  nop
0x140098983  lea     r8, [rsp+0A8h+var_68]
0x140098988  mov     rdx, [rax+18h]
0x14009898c  mov     rcx, rdi
0x14009898f  mov     rax, rbx
0x140098992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098997  mov     ebx, eax
0x140098999  test    eax, eax
0x14009899b  jns     short loc_1400989EC
0x14009899d  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x1400989a1  lea     rax, aTryapplyproces; "TryApplyProcessUIPolicy failed. hr[0x%x"...
0x1400989a8  mov     [rsp+0A8h+pszFormat], rax; pszFormat
0x1400989ad  mov     qword ptr [rsp+0A8h+var_80], 0; int
0x1400989b6  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x1400989bd  mov     [rsp+0A8h+var_88], rax; int
0x1400989c2  lea     r9, aRdpedppolicyma_3; "RdpEdpPolicyManager::TryApplyProcessUIP"...
0x1400989c9  mov     edx, 200h; int
0x1400989ce  mov     ecx, 3; int
0x1400989d3  mov     r8d, 3B8h; int
0x1400989d9  call    TRC_TraceBufferW
0x1400989de  nop
0x1400989df  lea     rcx, [rsp+0A8h+var_60]
0x1400989e4  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x1400989e9  nop
0x1400989ea  jmp     short loc_140098A1B
0x1400989ec  xor     ebx, ebx
0x1400989ee  lea     rcx, [rsp+0A8h+var_60]
0x1400989f3  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x1400989f8  nop
0x1400989f9  jmp     short loc_140098A1B
0x1400989fb  mov     ebx, 1
0x140098a00  lea     rcx, [rsp+0A8h+var_60]
0x140098a05  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x140098a0a  nop
0x140098a0b  jmp     short loc_140098A16
0x140098a0d  mov     ebx, [rsp+0A8h+var_50]
0x140098a11  mov     r14, [rsp+0A8h+var_40]
0x140098a16  test    r14, r14
0x140098a19  jz      short loc_140098A23
0x140098a1b  mov     rcx, r14; Block
0x140098a1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140098a23  mov     eax, ebx
0x140098a25  mov     rcx, [rsp+0A8h+var_10]
0x140098a2d  xor     rcx, rsp; StackCookie
0x140098a30  call    __security_check_cookie
0x140098a35  lea     r11, [rsp+0A8h+var_8]
0x140098a3d  mov     rbx, [r11+18h]
0x140098a41  mov     rdi, [r11+20h]
0x140098a45  mov     rsp, r11
0x140098a48  pop     r14
0x140098a4a  retn
```
