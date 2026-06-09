# HNS::Service::Core::WcnAgentManager::Start(void)

- ea: `0x1800d4180`
- end: `0x1800d43f0`
- name: `?Start@WcnAgentManager@Core@Service@HNS@@UEAAXXZ`
- size: `624`
- prototype: `void __fastcall(HNS::Service::Core::WcnAgentManager *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18005eca0`
- `0x180061dc4`
- `0x1800666b4`
- `0x18007046c`
- `0x1800883e8`
- `0x1800a499c`
- `0x1800d4120`
- `0x1800d4180`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d41a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d41a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d41d2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d41ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d41d2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d41ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d4258`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d42cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d4258`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d42cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d438d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d438d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d41da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d41da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d41c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d41c7`

## string_xrefs

- `0x1800d43b1`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1800d43c8`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1800d4337`: `WcnAgent initialization failed.`
- `0x1800d426f`: `onecore\vm\dv\net\hns\service\core\WcnAgentManager.h`
- `0x1800d42da`: `onecore\vm\dv\net\hns\service\core\WcnAgentManager.h`
- `0x1800d422a`: `WcnAgentFunctionTableOpen`
- `0x1800d4199`: `wcnagent.dll`
- `0x1800d41ff`: `onecore\vm\dv\net\hns\service\core\wcnagentmanager.cpp`
- `0x1800d42a1`: `WcnAgentFunctionTableClose`

## pseudocode

```c
void __fastcall HNS::Service::Core::WcnAgentManager::Start(HNS::Service::Core::WcnAgentManager *this)
{
  HMODULE Library; // rbp
  HMODULE *v3; // rsi
  HMODULE v4; // r14
  DWORD LastError; // ebx
  _BYTE *trivial_1; // rax
  const char *v7; // r9
  FARPROC ProcAddress; // rax
  _BYTE *v9; // rax
  const char *v10; // r9
  FARPROC v11; // rax
  int v12; // eax
  __int64 (*v13)(void); // rax
  unsigned int v14; // eax
  RTL_SRWLOCK *v15; // rcx
  int v16; // [rsp+20h] [rbp-58h]
  char *v17; // [rsp+28h] [rbp-50h]
  char v18; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+80h] [rbp+8h] BYREF

  Library = LoadLibraryExW(L"wcnagent.dll", 0, 0);
  v3 = (HMODULE *)((char *)this + 104);
  if ( (char *)this + 104 == &v18 )
  {
    if ( Library )
      FreeLibrary(Library);
  }
  else
  {
    v4 = *v3;
    if ( *v3 )
    {
      LastError = GetLastError();
      FreeLibrary(v4);
      SetLastError(LastError);
    }
    *v3 = Library;
  }
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(
    (int)retaddr,
    55,
    (int)"onecore\\vm\\dv\\net\\hns\\service\\core\\wcnagentmanager.cpp",
    (_DWORD)this + 104,
    "Failed to load %ws.",
    (char)L"wcnagent.dll");
  trivial_1 = (_BYTE *)_std_find_trivial_1("WcnAgentFunctionTableOpen", &unk_1802F1652, 0);
  if ( trivial_1 == (_BYTE *)&unk_1802F1652 || trivial_1 - "WcnAgentFunctionTableOpen" == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v7);
  ProcAddress = GetProcAddress(*v3, "WcnAgentFunctionTableOpen");
  *((_QWORD *)this + 14) = ProcAddress;
  wil::details::in1diag3::Throw_HrIfNullMsg<void (*)(void *),0>(
    retaddr,
    171,
    "onecore\\vm\\dv\\net\\hns\\service\\core\\WcnAgentManager.h",
    2147943685LL,
    ProcAddress,
    "Failed to load %hs.",
    "WcnAgentFunctionTableOpen");
  v9 = (_BYTE *)_std_find_trivial_1("WcnAgentFunctionTableClose", &unk_1802F16FB, 0);
  if ( v9 == (_BYTE *)&unk_1802F16FB || v9 - "WcnAgentFunctionTableClose" == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v10);
  v11 = GetProcAddress(*v3, "WcnAgentFunctionTableClose");
  *((_QWORD *)this + 15) = v11;
  wil::details::in1diag3::Throw_HrIfNullMsg<void (*)(void *),0>(
    retaddr,
    171,
    "onecore\\vm\\dv\\net\\hns\\service\\core\\WcnAgentManager.h",
    2147943685LL,
    v11,
    "Failed to load %hs.",
    "WcnAgentFunctionTableClose");
  v12 = (*((__int64 (__fastcall **)(__int64, char *))this + 14))(1, (char *)this + 128);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\wcnagentmanager.cpp",
      (const char *)(unsigned int)v12,
      v16);
  v13 = *(__int64 (**)(void))(*((_QWORD *)this + 16) + 8LL);
  if ( v13 )
  {
    v14 = v13();
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\wcnagentmanager.cpp",
      (const char *)v14,
      (int)"WcnAgent initialization failed.",
      v17);
  }
  *((_DWORD *)this + 8) = 0;
  HNS::Service::Interface::IManager::AddRef(this);
  (*(void (__fastcall **)(HNS::Service::Core::WcnAgentManager *, PSRWLOCK *))(*(_QWORD *)this + 8LL))(this, &SRWLock);
  v15 = SRWLock;
  *((_DWORD *)this + 20) = 2;
  if ( v15 )
    ReleaseSRWLockExclusive(v15);
}

```

## disassembly

```asm
0x1800d4180  mov     [rsp+arg_8], rbx
0x1800d4185  mov     [rsp+arg_10], rbp
0x1800d418a  push    rsi
0x1800d418b  push    rdi
0x1800d418c  push    r13
0x1800d418e  push    r14
0x1800d4190  push    r15
0x1800d4192  sub     rsp, 50h
0x1800d4196  mov     rdi, rcx
0x1800d4199  lea     r15, LibFileName; "wcnagent.dll"
0x1800d41a0  mov     rcx, r15; lpLibFileName
0x1800d41a3  xor     r8d, r8d; dwFlags
0x1800d41a6  xor     edx, edx; hFile
0x1800d41a8  call    cs:__imp_LoadLibraryExW
0x1800d41ae  mov     rbp, rax
0x1800d41b1  lea     rsi, [rdi+68h]
0x1800d41b5  lea     rax, [rsp+78h+var_38]
0x1800d41ba  cmp     rsi, rax
0x1800d41bd  jz      short loc_1800D41E5
0x1800d41bf  mov     r14, [rsi]
0x1800d41c2  test    r14, r14
0x1800d41c5  jz      short loc_1800D41E0
0x1800d41c7  call    cs:__imp_GetLastError
0x1800d41cd  mov     rcx, r14; hLibModule
0x1800d41d0  mov     ebx, eax
0x1800d41d2  call    cs:__imp_FreeLibrary
0x1800d41d8  mov     ecx, ebx; dwErrCode
0x1800d41da  call    cs:__imp_SetLastError
0x1800d41e0  mov     [rsi], rbp
0x1800d41e3  jmp     short loc_1800D41F3
0x1800d41e5  test    rbp, rbp
0x1800d41e8  jz      short loc_1800D41F3
0x1800d41ea  mov     rcx, rbp; hLibModule
0x1800d41ed  call    cs:__imp_FreeLibrary
0x1800d41f3  mov     rcx, [rsp+78h]; int
0x1800d41f8  lea     rax, aFailedToLoadWs; "Failed to load %ws."
0x1800d41ff  lea     rbp, aOnecoreVmDvNet_58; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800d4206  mov     [rsp+78h+var_50], r15; char
0x1800d420b  mov     r8, rbp; int
0x1800d420e  mov     [rsp+78h+var_58], rax; void *
0x1800d4213  mov     r9, rsi; int
0x1800d4216  mov     edx, 37h ; '7'; int
0x1800d421b  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,char const *,...)
0x1800d4220  lea     rbx, unk_1802F1652
0x1800d4227  xor     r8d, r8d
0x1800d422a  lea     r14, aWcnagentfuncti_0; "WcnAgentFunctionTableOpen"
0x1800d4231  mov     rdx, rbx
0x1800d4234  mov     rcx, r14
0x1800d4237  call    __std_find_trivial_1
0x1800d423c  cmp     rax, rbx
0x1800d423f  jz      loc_1800D43C3
0x1800d4245  sub     rax, r14
0x1800d4248  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d424c  jz      loc_1800D43C3
0x1800d4252  mov     rcx, [rsi]; hModule
0x1800d4255  mov     rdx, r14; lpProcName
0x1800d4258  call    cs:__imp_GetProcAddress
0x1800d425e  mov     rcx, [rsp+78h]
0x1800d4263  lea     r13, aFailedToLoadHs; "Failed to load %hs."
0x1800d426a  mov     [rsp+78h+var_48], r14
0x1800d426f  lea     r8, aOnecoreVmDvNet_117; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800d4276  mov     r15d, 80070505h
0x1800d427c  mov     [rsp+78h+var_50], r13
0x1800d4281  mov     r9d, r15d
0x1800d4284  mov     [rsp+78h+var_58], rax
0x1800d4289  mov     edx, 0ABh
0x1800d428e  mov     [rdi+70h], rax
0x1800d4292  call    ??$Throw_HrIfNullMsg@P6AXPEAX@Z$0A@@in1diag3@details@wil@@YAP6AXPEAX@Z0IPEBDJP6AX0@Z1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void (*)(void *),0>(void *,uint,char const *,long,void (*)(void *),char const *,...)
0x1800d4297  lea     rbx, unk_1802F16FB
0x1800d429e  xor     r8d, r8d
0x1800d42a1  lea     r14, aWcnagentfuncti; "WcnAgentFunctionTableClose"
0x1800d42a8  mov     rdx, rbx
0x1800d42ab  mov     rcx, r14
0x1800d42ae  call    __std_find_trivial_1
0x1800d42b3  cmp     rax, rbx
0x1800d42b6  jz      loc_1800D43AC
0x1800d42bc  sub     rax, r14
0x1800d42bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d42c3  jz      loc_1800D43AC
0x1800d42c9  mov     rcx, [rsi]; hModule
0x1800d42cc  mov     rdx, r14; lpProcName
0x1800d42cf  call    cs:__imp_GetProcAddress
0x1800d42d5  mov     rcx, [rsp+78h]
0x1800d42da  lea     r8, aOnecoreVmDvNet_117; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800d42e1  mov     [rsp+78h+var_48], r14
0x1800d42e6  mov     r9d, r15d
0x1800d42e9  mov     [rsp+78h+var_50], r13; char *
0x1800d42ee  mov     edx, 0ABh
0x1800d42f3  mov     [rdi+78h], rax
0x1800d42f7  mov     [rsp+78h+var_58], rax; int
0x1800d42fc  call    ??$Throw_HrIfNullMsg@P6AXPEAX@Z$0A@@in1diag3@details@wil@@YAP6AXPEAX@Z0IPEBDJP6AX0@Z1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void (*)(void *),0>(void *,uint,char const *,long,void (*)(void *),char const *,...)
0x1800d4301  mov     rax, [rdi+70h]
0x1800d4305  lea     rbx, [rdi+80h]
0x1800d430c  mov     rdx, rbx
0x1800d430f  mov     ecx, 1
0x1800d4314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4319  test    eax, eax
0x1800d431b  js      loc_1800D43DA
0x1800d4321  mov     rax, [rbx]
0x1800d4324  mov     rax, [rax+8]
0x1800d4328  test    rax, rax
0x1800d432b  jz      short loc_1800D4353
0x1800d432d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4332  mov     rcx, [rsp+78h]; this
0x1800d4337  lea     rdx, aWcnagentInitia; "WcnAgent initialization failed."
0x1800d433e  mov     [rsp+78h+var_58], rdx; int
0x1800d4343  mov     r9d, eax; char *
0x1800d4346  mov     edx, 1Bh; void *
0x1800d434b  mov     r8, rbp; unsigned int
0x1800d434e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800d4353  mov     rcx, rdi; this
0x1800d4356  mov     dword ptr [rdi+20h], 0
0x1800d435d  call    ?AddRef@IManager@Interface@Service@HNS@@QEAAKXZ; HNS::Service::Interface::IManager::AddRef(void)
0x1800d4362  mov     rax, [rdi]
0x1800d4365  lea     rdx, [rsp+78h+SRWLock]
0x1800d436d  mov     rcx, rdi
0x1800d4370  mov     rax, [rax+8]
0x1800d4374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4379  mov     rcx, [rsp+78h+SRWLock]; SRWLock
0x1800d4381  mov     dword ptr [rdi+50h], 2
0x1800d4388  test    rcx, rcx
0x1800d438b  jz      short loc_1800D4393
0x1800d438d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d4393  lea     r11, [rsp+78h+var_28]
0x1800d4398  mov     rbx, [r11+38h]
0x1800d439c  mov     rbp, [r11+40h]
0x1800d43a0  mov     rsp, r11
0x1800d43a3  pop     r15
0x1800d43a5  pop     r14
0x1800d43a7  pop     r13
0x1800d43a9  pop     rdi
0x1800d43aa  pop     rsi
0x1800d43ab  retn
0x1800d43ac  mov     rcx, [rsp+78h]; this
0x1800d43b1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d43b8  mov     edx, 0EBh; void *
0x1800d43bd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d43c3  mov     rcx, [rsp+78h]; this
0x1800d43c8  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d43cf  mov     edx, 0EBh; void *
0x1800d43d4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d43da  mov     rcx, [rsp+78h]; this
0x1800d43df  mov     r9d, eax; char *
0x1800d43e2  mov     r8, rbp; unsigned int
0x1800d43e5  mov     edx, 3Eh ; '>'; void *
0x1800d43ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
