# VmWbemCore::GetNullableProperty(IWbemClassObject *,ushort const *,Vml::VmVariant &)

- ea: `0x18023127c`
- end: `0x1802313de`
- name: `?GetNullableProperty@VmWbemCore@@QEAAHPEAUIWbemClassObject@@PEBGAEAVVmVariant@Vml@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(VmWbemCore *__hidden this, struct IWbemClassObject *, const unsigned __int16 *, struct Vml::VmVariant *)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18022ef7c`
- `0x180230064`
- `0x1802301a4`
- `0x180230374`
- `0x180230bd8`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x1800663fc`
- `0x1800666b4`
- `0x180078200`
- `0x18007845c`
- `0x18007cbc8`
- `0x1802309d0`
- `0x18023127c`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802312da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802312da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802312bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802312bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802312d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802312d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802312ee`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802312ee`

## string_xrefs

- `0x18023136a`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1802313cc`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1802313b3`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall VmWbemCore::GetNullableProperty(
        VmWbemCore *this,
        struct IWbemClassObject *a2,
        const unsigned __int16 *a3,
        struct Vml::VmVariant *a4)
{
  void *v7; // r14
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v10; // r9
  int v11; // ebx
  unsigned int v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-40h]
  void ***v15; // [rsp+20h] [rbp-40h]
  void **v16; // [rsp+40h] [rbp-20h] BYREF
  void *TokenHandle[2]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  *(_OWORD *)TokenHandle = 0;
  v7 = (void *)*((_QWORD *)this + 12);
  v16 = TokenHandle;
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
  if ( !ImpersonateLoggedOnUser(v7) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D52,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v10);
  LOBYTE(TokenHandle[1]) = 1;
  LODWORD(v16) = 0;
  v15 = &v16;
  v11 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct Vml::VmVariant *))a2->lpVtbl->Get)(
          a2,
          a3,
          0,
          a4);
  if ( v11 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
    {
      LODWORD(v15) = v11;
      VmlDebugTrace(
        16391,
        L"Failed to get WMI object property '%ls'CIMTYPE = 0x%X HRESULT = 0x%08lX \n",
        a3,
        (unsigned int)v16);
    }
    v13 = wil::verify_hresult<long>((unsigned int)v11);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v13,
      (int)v15);
  }
  LOBYTE(TokenHandle[1]) = 0;
  Vml::VmImpersonator::~VmImpersonator((Vml::VmImpersonator *)TokenHandle);
  return *(_WORD *)a4 > 1u;
}

```

## disassembly

```asm
0x18023127c  push    rbp
0x18023127e  push    rbx
0x18023127f  push    rsi
0x180231280  push    rdi
0x180231281  push    r14
0x180231283  mov     rbp, rsp
0x180231286  sub     rsp, 60h
0x18023128a  mov     rax, cs:__security_cookie
0x180231291  xor     rax, rsp
0x180231294  mov     [rbp+var_8], rax
0x180231298  mov     rdi, r9
0x18023129b  mov     rsi, r8
0x18023129e  mov     rbx, rdx
0x1802312a1  xorps   xmm0, xmm0
0x1802312a4  movups  xmmword ptr [rbp+TokenHandle], xmm0
0x1802312a8  mov     r14, [rcx+60h]
0x1802312ac  lea     rax, [rbp+TokenHandle]
0x1802312b0  mov     [rbp+var_20], rax
0x1802312b4  mov     [rbp+TokenHandle], 0
0x1802312bc  call    cs:__imp_GetCurrentThread
0x1802312c2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1802312c6  xor     r8d, r8d; OpenAsSelf
0x1802312c9  lea     edx, [r8+0Ch]; DesiredAccess
0x1802312cd  mov     rcx, rax; ThreadHandle
0x1802312d0  call    cs:__imp_OpenThreadToken
0x1802312d6  test    eax, eax
0x1802312d8  jnz     short loc_1802312EB
0x1802312da  call    cs:__imp_GetLastError
0x1802312e0  cmp     eax, 3F0h
0x1802312e5  jnz     loc_1802313C5
0x1802312eb  mov     rcx, r14; hToken
0x1802312ee  call    cs:__imp_ImpersonateLoggedOnUser
0x1802312f4  mov     rcx, [rbp+28h]; this
0x1802312f8  test    eax, eax
0x1802312fa  jz      short loc_18023136A
0x1802312fc  mov     r14d, 1
0x180231302  mov     byte ptr [rbp+TokenHandle+8], r14b
0x180231306  mov     dword ptr [rbp+var_20], 0
0x18023130d  mov     rax, [rbx]
0x180231310  mov     [rsp+60h+var_38], 0
0x180231319  lea     rcx, [rbp+var_20]
0x18023131d  mov     qword ptr [rsp+60h+var_40], rcx
0x180231322  mov     r9, rdi
0x180231325  xor     r8d, r8d
0x180231328  mov     rdx, rsi
0x18023132b  mov     rcx, rbx
0x18023132e  mov     rax, [rax+20h]
0x180231332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180231337  mov     ebx, eax
0x180231339  test    eax, eax
0x18023133b  js      short loc_18023137C
0x18023133d  mov     byte ptr [rbp+TokenHandle+8], 0
0x180231341  lea     rcx, [rbp+TokenHandle]; this
0x180231345  call    ??1VmImpersonator@Vml@@QEAA@XZ; Vml::VmImpersonator::~VmImpersonator(void)
0x18023134a  xor     eax, eax
0x18023134c  cmp     r14w, [rdi]
0x180231350  setb    al
0x180231353  mov     rcx, [rbp+var_8]
0x180231357  xor     rcx, rsp; StackCookie
0x18023135a  call    __security_check_cookie
0x18023135f  add     rsp, 60h
0x180231363  pop     r14
0x180231365  pop     rdi
0x180231366  pop     rsi
0x180231367  pop     rbx
0x180231368  pop     rbp
0x180231369  retn
0x18023136a  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180231371  mov     edx, 1D52h; void *
0x180231376  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18023137c  mov     edi, 4007h
0x180231381  mov     ecx, edi
0x180231383  call    VmlIsDebugTraceEnabled
0x180231388  test    eax, eax
0x18023138a  jz      short loc_1802313A5
0x18023138c  mov     [rsp+60h+var_40], ebx; int
0x180231390  mov     r9d, dword ptr [rbp+var_20]
0x180231394  mov     r8, rsi
0x180231397  lea     rdx, aFailedToGetWmi; "Failed to get WMI object property '%ls'"...
0x18023139e  mov     ecx, edi
0x1802313a0  call    VmlDebugTrace
0x1802313a5  mov     ecx, ebx
0x1802313a7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1802313ac  mov     r9d, eax; char *
0x1802313af  mov     rcx, [rbp+28h]; this
0x1802313b3  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x1802313ba  mov     edx, 0F4h; void *
0x1802313bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802313c5  mov     rcx, [rbp+28h]; this
0x1802313c9  mov     r9d, eax; char *
0x1802313cc  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1802313d3  mov     edx, 1CC3h; void *
0x1802313d8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
