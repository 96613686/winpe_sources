# VmWbemCore::SetProperty(IWbemClassObject *,ushort const *,Vml::VmVariant &,long)

- ea: `0x1802317a0`
- end: `0x1802318e3`
- name: `?SetProperty@VmWbemCore@@QEAAXPEAUIWbemClassObject@@PEBGAEAVVmVariant@Vml@@J@Z`
- size: `323`
- prototype: `void __fastcall(VmWbemCore *__hidden this, struct IWbemClassObject *, const unsigned __int16 *, struct Vml::VmVariant *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180230064`
- `0x1802318ec`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x1800663fc`
- `0x1800666b4`
- `0x180078200`
- `0x18007845c`
- `0x18007cbc8`
- `0x1802309d0`
- `0x1802317a0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802317ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802317ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802317e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802317e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802317f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802317f5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180231813`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180231813`

## string_xrefs

- `0x180231875`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1802318d1`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1802318b7`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VmWbemCore::SetProperty(
        VmWbemCore *this,
        struct IWbemClassObject *a2,
        const unsigned __int16 *a3,
        struct Vml::VmVariant *a4,
        int a5)
{
  void *v8; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v11; // r9
  int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-58h]
  void *TokenHandle[2]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_OWORD *)TokenHandle = 0;
  v8 = (void *)*((_QWORD *)this + 12);
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 0, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1CC3,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        (const char *)LastError,
        v14);
  }
  if ( !ImpersonateLoggedOnUser(v8) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D52,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v11);
  LOBYTE(TokenHandle[1]) = 1;
  v12 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct Vml::VmVariant *))a2->lpVtbl->Put)(
          a2,
          a3,
          0,
          a4);
  if ( v12 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
      VmlDebugTrace(16391, L"Failed to set WMI object property '%ls'", a3);
    v13 = wil::verify_hresult<long>((unsigned int)v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x845,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v13,
      a5);
  }
  LOBYTE(TokenHandle[1]) = 0;
  Vml::VmImpersonator::~VmImpersonator((Vml::VmImpersonator *)TokenHandle);
}

```

## disassembly

```asm
0x1802317a0  push    rbx
0x1802317a2  push    rbp
0x1802317a3  push    rsi
0x1802317a4  push    rdi
0x1802317a5  sub     rsp, 58h
0x1802317a9  mov     rax, cs:__security_cookie
0x1802317b0  xor     rax, rsp
0x1802317b3  mov     [rsp+78h+var_30], rax
0x1802317b8  mov     rbp, r9
0x1802317bb  mov     rdi, r8
0x1802317be  mov     rbx, rdx
0x1802317c1  xorps   xmm0, xmm0
0x1802317c4  movups  xmmword ptr [rsp+78h+TokenHandle], xmm0
0x1802317c9  mov     rsi, [rcx+60h]
0x1802317cd  lea     rax, [rsp+78h+TokenHandle]
0x1802317d2  mov     [rsp+78h+var_48], rax
0x1802317d7  mov     [rsp+78h+TokenHandle], 0
0x1802317e0  call    cs:__imp_GetCurrentThread
0x1802317e6  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x1802317eb  xor     r8d, r8d; OpenAsSelf
0x1802317ee  lea     edx, [r8+0Ch]; DesiredAccess
0x1802317f2  mov     rcx, rax; ThreadHandle
0x1802317f5  call    cs:__imp_OpenThreadToken
0x1802317fb  test    eax, eax
0x1802317fd  jnz     short loc_180231810
0x1802317ff  call    cs:__imp_GetLastError
0x180231805  cmp     eax, 3F0h
0x18023180a  jnz     loc_1802318C9
0x180231810  mov     rcx, rsi; hToken
0x180231813  call    cs:__imp_ImpersonateLoggedOnUser
0x180231819  mov     rcx, [rsp+78h]; this
0x18023181e  test    eax, eax
0x180231820  jz      short loc_180231875
0x180231822  mov     byte ptr [rsp+78h+TokenHandle+8], 1
0x180231827  mov     rax, [rbx]
0x18023182a  mov     edx, [rsp+78h+arg_20]
0x180231831  mov     [rsp+78h+var_58], edx; int
0x180231835  mov     r9, rbp
0x180231838  xor     r8d, r8d
0x18023183b  mov     rdx, rdi
0x18023183e  mov     rcx, rbx
0x180231841  mov     rax, [rax+28h]
0x180231845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023184a  mov     ebx, eax
0x18023184c  test    eax, eax
0x18023184e  js      short loc_180231887
0x180231850  mov     byte ptr [rsp+78h+TokenHandle+8], 0
0x180231855  lea     rcx, [rsp+78h+TokenHandle]; this
0x18023185a  call    ??1VmImpersonator@Vml@@QEAA@XZ; Vml::VmImpersonator::~VmImpersonator(void)
0x18023185f  mov     rcx, [rsp+78h+var_30]
0x180231864  xor     rcx, rsp; StackCookie
0x180231867  call    __security_check_cookie
0x18023186c  add     rsp, 58h
0x180231870  pop     rdi
0x180231871  pop     rsi
0x180231872  pop     rbp
0x180231873  pop     rbx
0x180231874  retn
0x180231875  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18023187c  mov     edx, 1D52h; void *
0x180231881  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180231887  mov     esi, 4007h
0x18023188c  mov     ecx, esi
0x18023188e  call    VmlIsDebugTraceEnabled
0x180231893  test    eax, eax
0x180231895  jz      short loc_1802318A8
0x180231897  mov     r8, rdi
0x18023189a  lea     rdx, aFailedToSetWmi; "Failed to set WMI object property '%ls'"
0x1802318a1  mov     ecx, esi
0x1802318a3  call    VmlDebugTrace
0x1802318a8  mov     ecx, ebx
0x1802318aa  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1802318af  mov     r9d, eax; char *
0x1802318b2  mov     rcx, [rsp+78h]; this
0x1802318b7  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x1802318be  mov     edx, 845h; void *
0x1802318c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802318c9  mov     rcx, [rsp+78h]; this
0x1802318ce  mov     r9d, eax; char *
0x1802318d1  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1802318d8  mov     edx, 1CC3h; void *
0x1802318dd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
