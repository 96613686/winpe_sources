# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005aa8`
- end: `0x180005cf6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006194`

## callees

- `0x180004030`
- `0x180004594`
- `0x180005aa8`
- `0x180005cfc`
- `0x180006478`
- `0x18000d18c`
- `0x18000d540`
- `0x18000f114`
- `0x18000f580`
- `0x18000f968`
- `0x180016ddc`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005b25`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005b25`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005ba9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005ba9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005ae3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005ae3`

## string_xrefs

- `0x180005c68`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  _DWORD *v8; // rcx
  DWORD v9; // eax
  bool v10; // dl
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // esi
  void *v15; // rdx
  int v16; // eax
  unsigned int v17; // ebx
  void *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
    v12 = v6;
  }
  v23 = v12;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v10, &v22, (bool *)v11);
  v14 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v8 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v8;
      ++*v8;
    }
    else
    {
      v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v16,
          120);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        return v17;
      }
      v6 = v21;
    }
    if ( v12 )
      wil::details::ReleaseMutex(v12, v18);
    if ( v6 )
      wil::details::CloseHandle(v6, v18);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v20);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v15);
    wil::details::CloseHandle(v6, v15);
    return v14;
  }
}

```

## disassembly

```asm
0x180005aa8  mov     [rsp-8+arg_10], rbx
0x180005aad  mov     [rsp-8+arg_18], rsi
0x180005ab2  push    rbp
0x180005ab3  push    rdi
0x180005ab4  push    r14
0x180005ab6  lea     rbp, [rsp-170h]
0x180005abe  sub     rsp, 270h
0x180005ac5  mov     rax, cs:__security_cookie
0x180005acc  xor     rax, rsp
0x180005acf  mov     [rbp+180h+var_20], rax
0x180005ad6  mov     r14, rdx
0x180005ad9  mov     qword ptr [rdx], 0
0x180005ae0  mov     rbx, rcx
0x180005ae3  call    cs:__imp_GetCurrentProcessId
0x180005aea  nop     dword ptr [rax+rax+00h]
0x180005aef  mov     [rsp+280h+var_258], rbx
0x180005af4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005afb  mov     r9d, eax
0x180005afe  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180005b06  mov     edx, 104h; unsigned __int64
0x180005b0b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005b10  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005b15  mov     r9d, 1F0001h; dwDesiredAccess
0x180005b1b  lea     rdx, [rsp+280h+Name]; lpName
0x180005b20  xor     r8d, r8d; dwFlags
0x180005b23  xor     ecx, ecx; lpMutexAttributes
0x180005b25  call    cs:__imp_CreateMutexExW
0x180005b2c  nop     dword ptr [rax+rax+00h]
0x180005b31  mov     [rsp+280h+var_250], rax
0x180005b36  mov     rbx, rax
0x180005b39  test    rax, rax
0x180005b3c  jnz     short loc_180005BA0
0x180005b3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005b43  jmp     short loc_180005B78
0x180005b45  mov     rax, [rsp+280h+var_248]
0x180005b4a  lea     rcx, ds:0[rax*4]
0x180005b52  test    rcx, rcx
0x180005b55  jz      loc_180005C84
0x180005b5b  mov     [r14], rcx
0x180005b5e  mov     eax, [rcx]
0x180005b60  inc     eax
0x180005b62  mov     [rcx], eax
0x180005b64  test    rdi, rdi
0x180005b67  jnz     loc_180005CDC
0x180005b6d  test    rbx, rbx
0x180005b70  jnz     loc_180005CE9
0x180005b76  xor     eax, eax
0x180005b78  mov     rcx, [rbp+180h+var_20]
0x180005b7f  xor     rcx, rsp; StackCookie
0x180005b82  call    __security_check_cookie
0x180005b87  lea     r11, [rsp+280h+var_10]
0x180005b8f  mov     rbx, [r11+30h]
0x180005b93  mov     rsi, [r11+38h]
0x180005b97  mov     rsp, r11
0x180005b9a  pop     r14
0x180005b9c  pop     rdi
0x180005b9d  pop     rbp
0x180005b9e  retn
0x180005ba0  xor     r8d, r8d; bAlertable
0x180005ba3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005ba6  mov     rcx, rbx; hHandle
0x180005ba9  call    cs:__imp_WaitForSingleObjectEx
0x180005bb0  nop     dword ptr [rax+rax+00h]
0x180005bb5  cmp     eax, 102h
0x180005bba  jz      loc_180005C5A
0x180005bc0  test    eax, 0FFFFFF7Fh
0x180005bc5  jnz     loc_180005C61
0x180005bcb  mov     rdi, rbx
0x180005bce  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180005bd3  mov     [rsp+280h+var_240], rdi
0x180005bd8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005bdd  mov     [rsp+280h+var_248], 0
0x180005be6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005beb  mov     esi, eax
0x180005bed  test    eax, eax
0x180005bef  jns     loc_180005B45
0x180005bf5  mov     rcx, [rbp+188h]; this
0x180005bfc  lea     r8, aWil; "wil"
0x180005c03  mov     r9d, eax; char *
0x180005c06  mov     edx, 66h ; 'f'; void *
0x180005c0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c10  mov     rcx, [rbp+188h]; this
0x180005c17  lea     r8, aWil; "wil"
0x180005c1e  mov     r9d, esi; char *
0x180005c21  mov     edx, 6Fh ; 'o'; void *
0x180005c26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c2b  mov     rcx, [rbp+188h]; this
0x180005c32  lea     r8, aWil; "wil"
0x180005c39  mov     r9d, esi; char *
0x180005c3c  mov     edx, 12Eh; void *
0x180005c41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c46  test    rdi, rdi
0x180005c49  jnz     short loc_180005C7A
0x180005c4b  mov     rcx, rbx; this
0x180005c4e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005c53  mov     eax, esi
0x180005c55  jmp     loc_180005B78
0x180005c5a  xor     edi, edi
0x180005c5c  jmp     loc_180005BCE
0x180005c61  mov     rcx, [rbp+188h]; this
0x180005c68  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005c6f  mov     edx, 0E01h; void *
0x180005c74  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005c7a  mov     rcx, rdi; this
0x180005c7d  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180005c82  jmp     short loc_180005C4B
0x180005c84  mov     r8, r14
0x180005c87  lea     rdx, [rsp+280h+var_250]
0x180005c8c  lea     rcx, [rsp+280h+Name]
0x180005c91  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005c96  mov     ebx, eax
0x180005c98  test    eax, eax
0x180005c9a  jns     short loc_180005CD2
0x180005c9c  mov     rcx, [rbp+188h]; this
0x180005ca3  lea     r8, aWil; "wil"
0x180005caa  mov     r9d, eax; char *
0x180005cad  mov     edx, 137h; void *
0x180005cb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005cb7  lea     rcx, [rsp+280h+var_240]
0x180005cbc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005cc1  lea     rcx, [rsp+280h+var_250]
0x180005cc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005ccb  mov     eax, ebx
0x180005ccd  jmp     loc_180005B78
0x180005cd2  mov     rbx, [rsp+280h+var_250]
0x180005cd7  jmp     loc_180005B64
0x180005cdc  mov     rcx, rdi; this
0x180005cdf  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180005ce4  jmp     loc_180005B6D
0x180005ce9  mov     rcx, rbx; this
0x180005cec  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005cf1  jmp     loc_180005B76
```
