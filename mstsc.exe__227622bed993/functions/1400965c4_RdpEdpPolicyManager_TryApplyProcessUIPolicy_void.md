# RdpEdpPolicyManager::TryApplyProcessUIPolicy(void)

- ea: `0x1400965c4`
- end: `0x1400968db`
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
- `0x14005ef40`
- `0x140095dcc`
- `0x140095e90`
- `0x140096368`
- `0x140096558`
- `0x1400965c4`
- `0x140107aa8`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140096618`
- `KERNEL32!GetCurrentProcess` at `0x140096618`
- `KERNEL32!GetLastError` at `0x140096634`
- `KERNEL32!GetLastError` at `0x140096634`
- `ADVAPI32!OpenProcessToken` at `0x14009662a`
- `ADVAPI32!OpenProcessToken` at `0x14009662a`

## string_xrefs

- `0x14009677d`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`
- `0x140096651`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x14009671a`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x1400967c0`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x140096846`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x140096640`: `OpenProcessToken failed. GetLastError[0x%x]`

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
0x1400965c4  mov     r11, rsp
0x1400965c7  push    r14
0x1400965c9  sub     rsp, 0A0h
0x1400965d0  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x1400965d8  mov     [r11+10h], rbx
0x1400965dc  mov     [r11+18h], rdi
0x1400965e0  mov     rax, cs:__security_cookie
0x1400965e7  xor     rax, rsp
0x1400965ea  mov     [rsp+0A8h+var_10], rax
0x1400965f2  mov     rbx, rcx
0x1400965f5  xor     r14d, r14d
0x1400965f8  mov     [rsp+0A8h+var_40], r14
0x1400965fd  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFFh
0x140096605  mov     dword ptr [rsp+0A8h+Size], r14d
0x14009660a  mov     dword ptr [rsp+0A8h+Size+4], r14d
0x14009660f  mov     [r11-60h], r14
0x140096613  mov     [rsp+0A8h+var_68], r14b
0x140096618  call    cs:__imp_GetCurrentProcess
0x14009661e  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x140096623  lea     edx, [r14+8]; DesiredAccess
0x140096627  mov     rcx, rax; ProcessHandle
0x14009662a  call    cs:__imp_OpenProcessToken
0x140096630  test    eax, eax
0x140096632  jnz     short loc_14009669F
0x140096634  call    cs:__imp_GetLastError
0x14009663a  mov     ebx, eax
0x14009663c  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x140096640  lea     rax, aOpenprocesstok_0; "OpenProcessToken failed. GetLastError[0"...
0x140096647  mov     [rsp+0A8h+pszFormat], rax; pszFormat
0x14009664c  mov     qword ptr [rsp+0A8h+var_80], r14; int
0x140096651  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x140096658  mov     [rsp+0A8h+var_88], rax; int
0x14009665d  lea     r9, aRdpedppolicyma_3; "RdpEdpPolicyManager::TryApplyProcessUIP"...
0x140096664  mov     edx, 200h; int
0x140096669  lea     ecx, [r14+3]; int
0x14009666d  mov     r8d, 38Dh; int
0x140096673  call    TRC_TraceBufferW
0x140096678  test    ebx, ebx
0x14009667a  jle     short loc_140096685
0x14009667c  movzx   ebx, bx
0x14009667f  or      ebx, 80070000h
0x140096685  mov     eax, 80004005h
0x14009668a  test    ebx, ebx
0x14009668c  cmovns  ebx, eax
0x14009668f  lea     rcx, [rsp+0A8h+var_60]
0x140096694  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x140096699  nop
0x14009669a  jmp     loc_1400968B3
0x14009669f  lea     rax, [rsp+0A8h+Size+4]
0x1400966a4  mov     [rsp+0A8h+var_88], rax; unsigned int *
0x1400966a9  xor     r9d, r9d; unsigned __int16 **
0x1400966ac  lea     r8, [rsp+0A8h+Size]; unsigned int *
0x1400966b1  mov     rdx, [rsp+0A8h+TokenHandle]; void *
0x1400966b6  lea     rcx, [rbx+40h]; this
0x1400966ba  call    ?SrpGetEnterpriseIds@RdpEdpSrpApi@@QEAAJPEAXPEAKPEAPEBG1@Z; RdpEdpSrpApi::SrpGetEnterpriseIds(void *,ulong *,ushort const * *,ulong *)
0x1400966bf  cmp     eax, 8007007Ah
0x1400966c4  jnz     loc_14009688B
0x1400966ca  mov     ecx, dword ptr [rsp+0A8h+Size]; Size
0x1400966ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400966d3  mov     r14, rax
0x1400966d6  mov     [rsp+0A8h+var_40], rax
0x1400966db  lea     rax, [rsp+0A8h+Size+4]
0x1400966e0  mov     [rsp+0A8h+var_88], rax; unsigned int *
0x1400966e5  mov     r9, r14; unsigned __int16 **
0x1400966e8  lea     r8, [rsp+0A8h+Size]; unsigned int *
0x1400966ed  mov     rdx, [rsp+0A8h+TokenHandle]; void *
0x1400966f2  lea     rcx, [rbx+40h]; this
0x1400966f6  call    ?SrpGetEnterpriseIds@RdpEdpSrpApi@@QEAAJPEAXPEAKPEAPEBG1@Z; RdpEdpSrpApi::SrpGetEnterpriseIds(void *,ulong *,ushort const * *,ulong *)
0x1400966fb  mov     ebx, eax
0x1400966fd  test    eax, eax
0x1400966ff  jns     short loc_140096753
0x140096701  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x140096705  lea     rax, aSrpgetenterpri; "SrpGetEnterpriseIds failed. hr[0x%x]"
0x14009670c  mov     [rsp+0A8h+pszFormat], rax; pszFormat
0x140096711  mov     qword ptr [rsp+0A8h+var_80], 0; int
0x14009671a  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x140096721  mov     [rsp+0A8h+var_88], rax; int
0x140096726  lea     r9, aRdpedppolicyma_3; "RdpEdpPolicyManager::TryApplyProcessUIP"...
0x14009672d  mov     edx, 200h; int
0x140096732  mov     ecx, 3; int
0x140096737  mov     r8d, 3A5h; int
0x14009673d  call    TRC_TraceBufferW
0x140096742  nop
0x140096743  lea     rcx, [rsp+0A8h+var_60]
0x140096748  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x14009674d  nop
0x14009674e  jmp     loc_1400968A6
0x140096753  test    r14, r14
0x140096756  jz      loc_14009688B
0x14009675c  cmp     dword ptr [rsp+0A8h+Size+4], 0
0x140096761  jz      loc_14009688B
0x140096767  mov     [rsp+0A8h+var_18], 0
0x140096773  mov     r9d, 37h ; '7'; unsigned int
0x140096779  lea     r8d, [r9+1]; unsigned int
0x14009677d  lea     rdx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyManager@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x140096784  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x140096789  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14009678e  nop
0x14009678f  lea     rdx, [rsp+0A8h+var_60]
0x140096794  mov     rcx, [rsp+0A8h+var_18]
0x14009679c  call    ??$GetActivationFactory@V?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>>)
0x1400967a1  mov     ebx, eax
0x1400967a3  test    eax, eax
0x1400967a5  jns     short loc_1400967F9
0x1400967a7  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x1400967ab  lea     rax, aGetactivationf_1; "GetActivationFactory<IProtectionPolicyM"...
0x1400967b2  mov     [rsp+0A8h+pszFormat], rax; pszFormat
0x1400967b7  mov     qword ptr [rsp+0A8h+var_80], 0; int
0x1400967c0  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x1400967c7  mov     [rsp+0A8h+var_88], rax; int
0x1400967cc  lea     r9, aRdpedppolicyma_3; "RdpEdpPolicyManager::TryApplyProcessUIP"...
0x1400967d3  mov     edx, 200h; int
0x1400967d8  mov     ecx, 3; int
0x1400967dd  mov     r8d, 3B2h; int
0x1400967e3  call    TRC_TraceBufferW
0x1400967e8  nop
0x1400967e9  lea     rcx, [rsp+0A8h+var_60]
0x1400967ee  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x1400967f3  nop
0x1400967f4  jmp     loc_1400968AB
0x1400967f9  mov     rdi, [rsp+0A8h+var_60]
0x1400967fe  mov     rax, [rdi]
0x140096801  mov     rbx, [rax+38h]
0x140096805  mov     rdx, r14
0x140096808  lea     rcx, [rsp+0A8h+hstringHeader]
0x14009680d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140096812  nop
0x140096813  lea     r8, [rsp+0A8h+var_68]
0x140096818  mov     rdx, [rax+18h]
0x14009681c  mov     rcx, rdi
0x14009681f  mov     rax, rbx
0x140096822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096827  mov     ebx, eax
0x140096829  test    eax, eax
0x14009682b  jns     short loc_14009687C
0x14009682d  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x140096831  lea     rax, aTryapplyproces; "TryApplyProcessUIPolicy failed. hr[0x%x"...
0x140096838  mov     [rsp+0A8h+pszFormat], rax; pszFormat
0x14009683d  mov     qword ptr [rsp+0A8h+var_80], 0; int
0x140096846  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x14009684d  mov     [rsp+0A8h+var_88], rax; int
0x140096852  lea     r9, aRdpedppolicyma_3; "RdpEdpPolicyManager::TryApplyProcessUIP"...
0x140096859  mov     edx, 200h; int
0x14009685e  mov     ecx, 3; int
0x140096863  mov     r8d, 3B8h; int
0x140096869  call    TRC_TraceBufferW
0x14009686e  nop
0x14009686f  lea     rcx, [rsp+0A8h+var_60]
0x140096874  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x140096879  nop
0x14009687a  jmp     short loc_1400968AB
0x14009687c  xor     ebx, ebx
0x14009687e  lea     rcx, [rsp+0A8h+var_60]
0x140096883  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x140096888  nop
0x140096889  jmp     short loc_1400968AB
0x14009688b  mov     ebx, 1
0x140096890  lea     rcx, [rsp+0A8h+var_60]
0x140096895  call    ?InternalRelease@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>::InternalRelease(void)
0x14009689a  nop
0x14009689b  jmp     short loc_1400968A6
0x14009689d  mov     ebx, [rsp+0A8h+var_50]
0x1400968a1  mov     r14, [rsp+0A8h+var_40]
0x1400968a6  test    r14, r14
0x1400968a9  jz      short loc_1400968B3
0x1400968ab  mov     rcx, r14; Block
0x1400968ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400968b3  mov     eax, ebx
0x1400968b5  mov     rcx, [rsp+0A8h+var_10]
0x1400968bd  xor     rcx, rsp; StackCookie
0x1400968c0  call    __security_check_cookie
0x1400968c5  lea     r11, [rsp+0A8h+var_8]
0x1400968cd  mov     rbx, [r11+18h]
0x1400968d1  mov     rdi, [r11+20h]
0x1400968d5  mov     rsp, r11
0x1400968d8  pop     r14
0x1400968da  retn
```
