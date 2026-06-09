# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008464`
- end: `0x180008688`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `548`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180011660`

## callees

- `0x1800081e4`
- `0x180008208`
- `0x180008464`
- `0x18000909c`
- `0x180009d44`
- `0x180015d08`
- `0x18001b77c`
- `0x18001b934`
- `0x18001cea8`
- `0x18001eed8`
- `0x18001f620`
- `0x180021db4`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x18000850d`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000850d`
- `KERNEL32!CreateMutexExW` at `0x1800084e1`
- `KERNEL32!CreateMutexExW` at `0x1800084e1`
- `KERNEL32!GetCurrentProcessId` at `0x18000849f`
- `KERNEL32!GetCurrentProcessId` at `0x18000849f`

## string_xrefs

- `0x18000852e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v6; // rcx
  wil::details *v7; // rbx
  DWORD v9; // eax
  __int64 v10; // rdx
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  void *v16; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  wil::details *v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v20 = Mutex;
  v7 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
    v12 = v7;
  }
  v22 = v12;
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v10, &v21, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v17 = (_DWORD *)(4 * v21);
    if ( 4 * v21 )
    {
      *a2 = v17;
      ++*v17;
    }
    else
    {
      v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (int)"wil", (const char *)(unsigned int)v18);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        return v19;
      }
      v7 = v20;
    }
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v7 )
      wil::details::CloseHandle(v7, v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, (int)"wil", (const char *)(unsigned int)ValueInternal);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (int)"wil", (const char *)v15);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (int)"wil", (const char *)v15);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v16);
    wil::details::CloseHandle(v7, v16);
    return v15;
  }
}

```

## disassembly

```asm
0x180008464  mov     [rsp-8+arg_10], rbx
0x180008469  mov     [rsp-8+arg_18], rsi
0x18000846e  push    rbp
0x18000846f  push    rdi
0x180008470  push    r14
0x180008472  lea     rbp, [rsp-170h]
0x18000847a  sub     rsp, 270h
0x180008481  mov     rax, cs:__security_cookie
0x180008488  xor     rax, rsp
0x18000848b  mov     [rbp+180h+var_20], rax
0x180008492  mov     r14, rdx
0x180008495  mov     qword ptr [rdx], 0
0x18000849c  mov     rbx, rcx
0x18000849f  call    cs:__imp_GetCurrentProcessId
0x1800084a6  nop     dword ptr [rax+rax+00h]
0x1800084ab  mov     [rsp+280h+var_258], rbx
0x1800084b0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800084b7  mov     r9d, eax
0x1800084ba  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x1800084c2  mov     edx, 104h; unsigned __int64
0x1800084c7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800084cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800084d1  mov     r9d, 1F0001h; dwDesiredAccess
0x1800084d7  lea     rdx, [rsp+280h+Name]; lpName
0x1800084dc  xor     r8d, r8d; dwFlags
0x1800084df  xor     ecx, ecx; lpMutexAttributes
0x1800084e1  call    cs:__imp_CreateMutexExW
0x1800084e8  nop     dword ptr [rax+rax+00h]
0x1800084ed  mov     [rsp+280h+var_250], rax
0x1800084f2  mov     rbx, rax
0x1800084f5  test    rax, rax
0x1800084f8  jnz     short loc_180008504
0x1800084fa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800084ff  jmp     loc_180008660
0x180008504  xor     r8d, r8d; bAlertable
0x180008507  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000850a  mov     rcx, rbx; hHandle
0x18000850d  call    cs:__imp_WaitForSingleObjectEx
0x180008514  nop     dword ptr [rax+rax+00h]
0x180008519  cmp     eax, 102h
0x18000851e  jz      short loc_180008545
0x180008520  test    eax, 0FFFFFF7Fh
0x180008525  jz      short loc_180008540
0x180008527  mov     rcx, [rbp+188h]; this
0x18000852e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008535  mov     edx, 0E01h; void *
0x18000853a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008540  mov     rdi, rbx
0x180008543  jmp     short loc_180008547
0x180008545  xor     edi, edi
0x180008547  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18000854c  mov     [rsp+280h+var_240], rdi
0x180008551  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008556  mov     [rsp+280h+var_248], 0
0x18000855f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008564  mov     esi, eax
0x180008566  test    eax, eax
0x180008568  jns     short loc_1800085D7
0x18000856a  mov     rcx, [rbp+188h]; this
0x180008571  lea     r8, aWil; "wil"
0x180008578  mov     r9d, eax; char *
0x18000857b  mov     edx, 66h ; 'f'; void *
0x180008580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008585  mov     rcx, [rbp+188h]; this
0x18000858c  lea     r8, aWil; "wil"
0x180008593  mov     r9d, esi; char *
0x180008596  mov     edx, 6Fh ; 'o'; void *
0x18000859b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085a0  mov     rcx, [rbp+188h]; this
0x1800085a7  lea     r8, aWil; "wil"
0x1800085ae  mov     r9d, esi; char *
0x1800085b1  mov     edx, 12Eh; void *
0x1800085b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085bb  test    rdi, rdi
0x1800085be  jz      short loc_1800085C8
0x1800085c0  mov     rcx, rdi; this
0x1800085c3  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800085c8  mov     rcx, rbx; this
0x1800085cb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800085d0  mov     eax, esi
0x1800085d2  jmp     loc_180008660
0x1800085d7  mov     rax, [rsp+280h+var_248]
0x1800085dc  lea     rcx, ds:0[rax*4]
0x1800085e4  test    rcx, rcx
0x1800085e7  jz      short loc_1800085F4
0x1800085e9  mov     [r14], rcx
0x1800085ec  mov     eax, [rcx]
0x1800085ee  inc     eax
0x1800085f0  mov     [rcx], eax
0x1800085f2  jmp     short loc_180008644
0x1800085f4  mov     r8, r14
0x1800085f7  lea     rdx, [rsp+280h+var_250]
0x1800085fc  lea     rcx, [rsp+280h+Name]
0x180008601  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008606  mov     ebx, eax
0x180008608  test    eax, eax
0x18000860a  jns     short loc_18000863F
0x18000860c  mov     rcx, [rbp+188h]; this
0x180008613  lea     r8, aWil; "wil"
0x18000861a  mov     r9d, eax; char *
0x18000861d  mov     edx, 137h; void *
0x180008622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008627  lea     rcx, [rsp+280h+var_240]
0x18000862c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008631  lea     rcx, [rsp+280h+var_250]
0x180008636  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000863b  mov     eax, ebx
0x18000863d  jmp     short loc_180008660
0x18000863f  mov     rbx, [rsp+280h+var_250]
0x180008644  test    rdi, rdi
0x180008647  jz      short loc_180008651
0x180008649  mov     rcx, rdi; this
0x18000864c  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180008651  test    rbx, rbx
0x180008654  jz      short loc_18000865E
0x180008656  mov     rcx, rbx; this
0x180008659  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000865e  xor     eax, eax
0x180008660  mov     rcx, [rbp+180h+var_20]
0x180008667  xor     rcx, rsp; StackCookie
0x18000866a  call    __security_check_cookie
0x18000866f  lea     r11, [rsp+280h+var_10]
0x180008677  mov     rbx, [r11+30h]
0x18000867b  mov     rsi, [r11+38h]
0x18000867f  mov     rsp, r11
0x180008682  pop     r14
0x180008684  pop     rdi
0x180008685  pop     rbp
0x180008686  retn
```
