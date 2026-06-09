# VmWbemCore::DeleteObject(IWbemClassObject *)

- ea: `0x180230bd8`
- end: `0x180230e4e`
- name: `?DeleteObject@VmWbemCore@@QEAAXPEAUIWbemClassObject@@@Z`
- size: `630`
- prototype: `void __fastcall(VmWbemCore *__hidden this, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18022fe08`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x1800663fc`
- `0x1800666b4`
- `0x180078200`
- `0x18007845c`
- `0x18007cbc8`
- `0x1802309d0`
- `0x180230bd8`
- `0x18023127c`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180230cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180230cbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180230c9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180230c9f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180230cb3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180230cb3`
- `OLEAUT32!__imp_SysAllocString` at `0x180230c4d`
- `OLEAUT32!__imp_SysAllocString` at `0x180230c4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180230d24`
- `OLEAUT32!__imp_SysFreeString` at `0x180230d24`
- `OLEAUT32!__imp_VariantInit` at `0x180230c14`
- `OLEAUT32!__imp_VariantInit` at `0x180230c14`
- `OLEAUT32!__imp_VariantClear` at `0x180230c67`
- `OLEAUT32!__imp_VariantClear` at `0x180230c67`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180230cd1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180230cd1`

## string_xrefs

- `0x180230dc5`: `onecore\vm\common\vml\VmBstr.h`
- `0x180230de8`: `onecore\vm\common\wmimgmt\VmWbemCore.h`
- `0x180230d46`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180230e3c`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180230d6e`: `Failed to delete WMI object %ws. HRESULT = 0x%08lX\n`
- `0x180230c1f`: `__PATH`
- `0x180230d8a`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x180230da2`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x180230e0b`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x180230e23`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall VmWbemCore::DeleteObject(VmWbemCore *this, struct IWbemClassObject *a2)
{
  OLECHAR *v4; // rbx
  int NullableProperty; // esi
  void *v6; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v9; // r9
  int v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // [rsp+20h] [rbp-40h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( !*((_QWORD *)this + 10) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA51,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)0x80004003LL,
      v15);
  v4 = 0;
  VariantInit(&pvarg);
  NullableProperty = VmWbemCore::GetNullableProperty(this, a2, L"__PATH", (struct Vml::VmVariant *)&pvarg);
  if ( NullableProperty )
  {
    if ( pvarg.vt != 8 )
    {
      v14 = wil::verify_hresult<long>(2147614725LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x359,
        (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
        (const char *)v14,
        v15);
    }
    if ( pvarg.llVal )
    {
      v4 = SysAllocString(pvarg.bstrVal);
      if ( !v4 )
      {
        v12 = wil::verify_hresult<long>(2147942414LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x254,
          (unsigned int)"onecore\\vm\\common\\vml\\VmBstr.h",
          (const char *)v12,
          v15);
      }
    }
  }
  VariantClear(&pvarg);
  if ( !NullableProperty )
  {
    v13 = wil::verify_hresult<long>(2147614725LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\VmWbemCore.h",
      (const char *)v13,
      v15);
  }
  if ( !*((_QWORD *)this + 10) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA74,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)0x80004003LL,
      v15);
  *(_OWORD *)&pvarg.vt = 0;
  v6 = (void *)*((_QWORD *)this + 12);
  *(_QWORD *)&pvarg.vt = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 0, (PHANDLE)&pvarg) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1CC3,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        (const char *)LastError,
        v15);
  }
  if ( !ImpersonateLoggedOnUser(v6) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D52,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v9);
  pvarg.bVal = 1;
  v10 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD))(**((_QWORD **)this + 10) + 128LL))(
          *((_QWORD *)this + 10),
          v4,
          0,
          0);
  if ( v10 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
      VmlDebugTrace(16391, L"Failed to delete WMI object %ws. HRESULT = 0x%08lX\n", v4, (unsigned int)v10);
    v11 = wil::verify_hresult<long>((unsigned int)v10);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA7E,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v11,
      0);
  }
  pvarg.bVal = 0;
  Vml::VmImpersonator::~VmImpersonator((Vml::VmImpersonator *)&pvarg);
  if ( v4 )
    SysFreeString(v4);
}

```

## disassembly

```asm
0x180230bd8  mov     [rsp-18h+arg_10], rbx
0x180230bdd  push    rbp
0x180230bde  push    rsi
0x180230bdf  push    rdi
0x180230be0  mov     rbp, rsp
0x180230be3  sub     rsp, 60h
0x180230be7  mov     rax, cs:__security_cookie
0x180230bee  xor     rax, rsp
0x180230bf1  mov     [rbp+var_8], rax
0x180230bf5  mov     rsi, rdx
0x180230bf8  mov     rdi, rcx
0x180230bfb  mov     rcx, [rbp+18h]; this
0x180230bff  cmp     qword ptr [rdi+50h], 0
0x180230c04  jz      loc_180230D9C
0x180230c0a  xor     ebx, ebx
0x180230c0c  mov     [rbp+var_30], rbx
0x180230c10  lea     rcx, [rbp+pvarg]; pvarg
0x180230c14  call    cs:__imp_VariantInit
0x180230c1a  nop
0x180230c1b  lea     r9, [rbp+pvarg]; struct Vml::VmVariant *
0x180230c1f  lea     r8, aPath_0; "__PATH"
0x180230c26  mov     rdx, rsi; struct IWbemClassObject *
0x180230c29  mov     rcx, rdi; this
0x180230c2c  call    ?GetNullableProperty@VmWbemCore@@QEAAHPEAUIWbemClassObject@@PEBGAEAVVmVariant@Vml@@@Z; VmWbemCore::GetNullableProperty(IWbemClassObject *,ushort const *,Vml::VmVariant &)
0x180230c31  mov     esi, eax
0x180230c33  test    eax, eax
0x180230c35  jz      short loc_180230C63
0x180230c37  lea     eax, [rbx+8]
0x180230c3a  cmp     ax, word ptr [rbp+pvarg]
0x180230c3e  jnz     loc_180230DFA
0x180230c44  mov     rcx, qword ptr [rbp+pvarg+8]; psz
0x180230c48  test    rcx, rcx
0x180230c4b  jz      short loc_180230C5F
0x180230c4d  call    cs:__imp_SysAllocString
0x180230c53  mov     rbx, rax
0x180230c56  test    rax, rax
0x180230c59  jz      loc_180230DB4
0x180230c5f  mov     [rbp+var_30], rbx
0x180230c63  lea     rcx, [rbp+pvarg]; pvarg
0x180230c67  call    cs:__imp_VariantClear
0x180230c6d  test    esi, esi
0x180230c6f  jz      loc_180230DD7
0x180230c75  mov     rcx, [rbp+18h]; this
0x180230c79  cmp     qword ptr [rdi+50h], 0
0x180230c7e  jz      loc_180230E1D
0x180230c84  xorps   xmm0, xmm0
0x180230c87  movups  xmmword ptr [rbp+pvarg], xmm0
0x180230c8b  mov     rsi, [rdi+60h]
0x180230c8f  lea     rax, [rbp+pvarg]
0x180230c93  mov     [rbp+var_28], rax
0x180230c97  mov     qword ptr [rbp+pvarg], 0
0x180230c9f  call    cs:__imp_GetCurrentThread
0x180230ca5  lea     r9, [rbp+pvarg]; TokenHandle
0x180230ca9  xor     r8d, r8d; OpenAsSelf
0x180230cac  lea     edx, [r8+0Ch]; DesiredAccess
0x180230cb0  mov     rcx, rax; ThreadHandle
0x180230cb3  call    cs:__imp_OpenThreadToken
0x180230cb9  test    eax, eax
0x180230cbb  jnz     short loc_180230CCE
0x180230cbd  call    cs:__imp_GetLastError
0x180230cc3  cmp     eax, 3F0h
0x180230cc8  jnz     loc_180230E35
0x180230cce  mov     rcx, rsi; hToken
0x180230cd1  call    cs:__imp_ImpersonateLoggedOnUser
0x180230cd7  mov     rcx, [rbp+18h]; this
0x180230cdb  test    eax, eax
0x180230cdd  jz      short loc_180230D46
0x180230cdf  mov     byte ptr [rbp+pvarg+8], 1
0x180230ce3  mov     rcx, [rdi+50h]
0x180230ce7  mov     rax, [rcx]
0x180230cea  mov     qword ptr [rsp+60h+var_40], 0; int
0x180230cf3  xor     r9d, r9d
0x180230cf6  xor     r8d, r8d
0x180230cf9  mov     rdx, rbx
0x180230cfc  mov     rax, [rax+80h]
0x180230d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180230d08  mov     edi, eax
0x180230d0a  test    eax, eax
0x180230d0c  js      short loc_180230D58
0x180230d0e  mov     byte ptr [rbp+pvarg+8], 0
0x180230d12  lea     rcx, [rbp+pvarg]; this
0x180230d16  call    ??1VmImpersonator@Vml@@QEAA@XZ; Vml::VmImpersonator::~VmImpersonator(void)
0x180230d1b  nop
0x180230d1c  test    rbx, rbx
0x180230d1f  jz      short loc_180230D2A
0x180230d21  mov     rcx, rbx; bstrString
0x180230d24  call    cs:__imp_SysFreeString
0x180230d2a  mov     rcx, [rbp+var_8]
0x180230d2e  xor     rcx, rsp; StackCookie
0x180230d31  call    __security_check_cookie
0x180230d36  mov     rbx, [rsp+60h+arg_10]
0x180230d3e  add     rsp, 60h
0x180230d42  pop     rdi
0x180230d43  pop     rsi
0x180230d44  pop     rbp
0x180230d45  retn
0x180230d46  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180230d4d  mov     edx, 1D52h; void *
0x180230d52  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180230d58  mov     esi, 4007h
0x180230d5d  mov     ecx, esi
0x180230d5f  call    VmlIsDebugTraceEnabled
0x180230d64  test    eax, eax
0x180230d66  jz      short loc_180230D7C
0x180230d68  mov     r9d, edi
0x180230d6b  mov     r8, rbx
0x180230d6e  lea     rdx, aFailedToDelete; "Failed to delete WMI object %ws. HRESUL"...
0x180230d75  mov     ecx, esi
0x180230d77  call    VmlDebugTrace
0x180230d7c  mov     ecx, edi
0x180230d7e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180230d83  mov     r9d, eax; char *
0x180230d86  mov     rcx, [rbp+18h]; this
0x180230d8a  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180230d91  mov     edx, 0A7Eh; void *
0x180230d96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180230d9c  mov     r9d, 80004003h; char *
0x180230da2  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180230da9  mov     edx, 0A51h; void *
0x180230dae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180230db4  mov     ecx, 8007000Eh
0x180230db9  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180230dbe  mov     r9d, eax; char *
0x180230dc1  mov     rcx, [rbp+18h]; this
0x180230dc5  lea     r8, aOnecoreVmCommo_4; "onecore\\vm\\common\\vml\\VmBstr.h"
0x180230dcc  mov     edx, 254h; void *
0x180230dd1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180230dd7  mov     ecx, 80020005h
0x180230ddc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180230de1  mov     r9d, eax; char *
0x180230de4  mov     rcx, [rbp+18h]; this
0x180230de8  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\wmimgmt\\VmWbemCor"...
0x180230def  mov     edx, 0BAh; void *
0x180230df4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180230dfa  mov     ecx, 80020005h
0x180230dff  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180230e04  mov     r9d, eax; char *
0x180230e07  mov     rcx, [rbp+18h]; this
0x180230e0b  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180230e12  mov     edx, 359h; void *
0x180230e17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180230e1d  mov     r9d, 80004003h; char *
0x180230e23  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180230e2a  mov     edx, 0A74h; void *
0x180230e2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180230e35  mov     rcx, [rbp+18h]; this
0x180230e39  mov     r9d, eax; char *
0x180230e3c  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180230e43  mov     edx, 1CC3h; void *
0x180230e48  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
