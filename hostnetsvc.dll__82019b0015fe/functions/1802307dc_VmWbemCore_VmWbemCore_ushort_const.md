# VmWbemCore::VmWbemCore(ushort const *)

- ea: `0x1802307dc`
- end: `0x180230992`
- name: `??0VmWbemCore@@QEAA@PEBG@Z`
- size: `438`
- prototype: `VmWbemCore *__fastcall(VmWbemCore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18022e568`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x1800663fc`
- `0x1800666b4`
- `0x18007cbc8`
- `0x18022ebe4`
- `0x1802307dc`
- `0x1802309d0`
- `0x180231014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180230877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802308c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180230877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802308c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180230851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802308a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180230851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802308a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180230869`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802308ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180230869`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802308ba`
- `OLEAUT32!__imp_SysAllocString` at `0x180230824`
- `OLEAUT32!__imp_SysAllocString` at `0x180230824`
- `OLEAUT32!__imp_SysFreeString` at `0x18023083f`
- `OLEAUT32!__imp_SysFreeString` at `0x18023083f`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1802308d7`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1802308d7`

## string_xrefs

- `0x18023094c`: `onecore\vm\common\vml\VmBstr.h`
- `0x180230928`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180230966`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180230980`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
VmWbemCore *__fastcall VmWbemCore::VmWbemCore(VmWbemCore *this, const unsigned __int16 *a2)
{
  BSTR v3; // rbx
  OLECHAR *v4; // rcx
  HANDLE CurrentThread; // rax
  const unsigned __int16 *v6; // rdx
  DWORD LastError; // eax
  HANDLE v8; // rax
  DWORD v9; // eax
  const unsigned __int16 *v10; // rdx
  const char *v11; // r9
  unsigned int v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-38h]
  void *TokenHandle[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v14 = (unsigned int)this;
  Vml::VmSharableObject::VmSharableObject(this);
  *(_QWORD *)this = &VmWbemCore::`vftable';
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  v3 = SysAllocString(L"WQL");
  if ( !v3 )
  {
    v13 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"onecore\\vm\\common\\vml\\VmBstr.h",
      (const char *)v13,
      v14);
  }
  v4 = (OLECHAR *)*((_QWORD *)this + 11);
  if ( v4 )
    SysFreeString(v4);
  *((_QWORD *)this + 11) = v3;
  *((_QWORD *)this + 12) = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, (PHANDLE)this + 12) )
  {
    VmWbemCore::FinishConstruction(this, v6);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1CC3,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        (const char *)LastError,
        v14);
    *(_OWORD *)TokenHandle = 0;
    v8 = GetCurrentThread();
    if ( !OpenThreadToken(v8, 0xCu, 0, TokenHandle) )
    {
      v9 = GetLastError();
      if ( v9 != 1008 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1CC3,
          (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
          (const char *)v9,
          v14);
    }
    if ( !ImpersonateSelf(SecurityImpersonation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1D33,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v11);
    LOBYTE(TokenHandle[1]) = 1;
    VmWbemCore::FinishConstruction(this, v10);
    LOBYTE(TokenHandle[1]) = 0;
    Vml::VmImpersonator::~VmImpersonator((Vml::VmImpersonator *)TokenHandle);
  }
  return this;
}

```

## disassembly

```asm
0x1802307dc  mov     [rsp+arg_8], rbx
0x1802307e1  push    rdi
0x1802307e2  sub     rsp, 50h
0x1802307e6  mov     rax, cs:__security_cookie
0x1802307ed  xor     rax, rsp
0x1802307f0  mov     [rsp+58h+var_18], rax
0x1802307f5  mov     rdi, rcx
0x1802307f8  mov     qword ptr [rsp+58h+var_38], rcx; unsigned int
0x1802307fd  call    ??0VmSharableObject@Vml@@IEAA@XZ; Vml::VmSharableObject::VmSharableObject(void)
0x180230802  nop
0x180230803  lea     rax, ??_7VmWbemCore@@6B@; const VmWbemCore::`vftable'
0x18023080a  mov     [rdi], rax
0x18023080d  mov     qword ptr [rdi+50h], 0
0x180230815  mov     qword ptr [rdi+58h], 0
0x18023081d  lea     rcx, aWql; "WQL"
0x180230824  call    cs:__imp_SysAllocString
0x18023082a  mov     rbx, rax
0x18023082d  test    rax, rax
0x180230830  jz      loc_18023093A
0x180230836  mov     rcx, [rdi+58h]; bstrString
0x18023083a  test    rcx, rcx
0x18023083d  jz      short loc_180230845
0x18023083f  call    cs:__imp_SysFreeString
0x180230845  mov     [rdi+58h], rbx
0x180230849  mov     qword ptr [rdi+60h], 0
0x180230851  call    cs:__imp_GetCurrentThread
0x180230857  lea     r9, [rdi+60h]; TokenHandle
0x18023085b  mov     edx, 2000Eh; DesiredAccess
0x180230860  mov     r8d, 1; OpenAsSelf
0x180230866  mov     rcx, rax; ThreadHandle
0x180230869  call    cs:__imp_OpenThreadToken
0x18023086f  test    eax, eax
0x180230871  jnz     loc_180230904
0x180230877  call    cs:__imp_GetLastError
0x18023087d  mov     ebx, 3F0h
0x180230882  cmp     eax, ebx
0x180230884  jnz     loc_18023095E
0x18023088a  xorps   xmm0, xmm0
0x18023088d  movups  xmmword ptr [rsp+58h+TokenHandle], xmm0
0x180230892  lea     rax, [rsp+58h+TokenHandle]
0x180230897  mov     [rsp+58h+var_30], rax
0x18023089c  mov     [rsp+58h+TokenHandle], 0
0x1802308a5  call    cs:__imp_GetCurrentThread
0x1802308ab  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x1802308b0  xor     r8d, r8d; OpenAsSelf
0x1802308b3  lea     edx, [r8+0Ch]; DesiredAccess
0x1802308b7  mov     rcx, rax; ThreadHandle
0x1802308ba  call    cs:__imp_OpenThreadToken
0x1802308c0  test    eax, eax
0x1802308c2  jnz     short loc_1802308D2
0x1802308c4  call    cs:__imp_GetLastError
0x1802308ca  cmp     eax, ebx
0x1802308cc  jnz     loc_180230978
0x1802308d2  mov     ecx, 2; ImpersonationLevel
0x1802308d7  call    cs:__imp_ImpersonateSelf
0x1802308dd  mov     rcx, [rsp+58h]; this
0x1802308e2  test    eax, eax
0x1802308e4  jz      short loc_180230928
0x1802308e6  mov     byte ptr [rsp+58h+TokenHandle+8], 1
0x1802308eb  mov     rcx, rdi; this
0x1802308ee  call    ?FinishConstruction@VmWbemCore@@AEAAXPEBG@Z; VmWbemCore::FinishConstruction(ushort const *)
0x1802308f3  mov     byte ptr [rsp+58h+TokenHandle+8], 0
0x1802308f8  lea     rcx, [rsp+58h+TokenHandle]; this
0x1802308fd  call    ??1VmImpersonator@Vml@@QEAA@XZ; Vml::VmImpersonator::~VmImpersonator(void)
0x180230902  jmp     short loc_18023090D
0x180230904  mov     rcx, rdi; this
0x180230907  call    ?FinishConstruction@VmWbemCore@@AEAAXPEBG@Z; VmWbemCore::FinishConstruction(ushort const *)
0x18023090c  nop
0x18023090d  mov     rax, rdi
0x180230910  mov     rcx, [rsp+58h+var_18]
0x180230915  xor     rcx, rsp; StackCookie
0x180230918  call    __security_check_cookie
0x18023091d  mov     rbx, [rsp+58h+arg_8]
0x180230922  add     rsp, 50h
0x180230926  pop     rdi
0x180230927  retn
0x180230928  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18023092f  mov     edx, 1D33h; void *
0x180230934  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18023093a  mov     ecx, 8007000Eh
0x18023093f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180230944  mov     r9d, eax; char *
0x180230947  mov     rcx, [rsp+58h]; this
0x18023094c  lea     r8, aOnecoreVmCommo_4; "onecore\\vm\\common\\vml\\VmBstr.h"
0x180230953  mov     edx, 254h; void *
0x180230958  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023095e  mov     rcx, [rsp+58h]; this
0x180230963  mov     r9d, eax; char *
0x180230966  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18023096d  mov     edx, 1CC3h; void *
0x180230972  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180230978  mov     rcx, [rsp+58h]; this
0x18023097d  mov     r9d, eax; char *
0x180230980  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180230987  mov     edx, 1CC3h; void *
0x18023098c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
