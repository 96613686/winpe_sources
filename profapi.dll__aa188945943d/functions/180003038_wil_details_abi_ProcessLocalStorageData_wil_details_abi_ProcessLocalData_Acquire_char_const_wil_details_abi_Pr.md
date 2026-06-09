# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003038`
- end: `0x18000323b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `515`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180002164`

## callees

- `0x180001fb8`
- `0x1800023bc`
- `0x180002458`
- `0x18000261c`
- `0x180002bb0`
- `0x18000300c`
- `0x180003038`
- `0x180003244`
- `0x180003330`
- `0x180005b60`
- `0x18000bf10`
- `0x18000fa10`
- `0x180010fa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800030e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800030e2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800030b8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800030b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003073`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003073`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  char *v10; // r9
  wil::details *v11; // rsi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // edi
  _DWORD *v15; // rcx
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  void *v19; // rdx
  int v20; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v25; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v21 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v7 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v7 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v8, v9, v10);
    v11 = v6;
  }
  v25 = v11;
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v8, &v24, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v22);
    v17 = v14;
    v18 = 302;
    goto LABEL_16;
  }
  v15 = (_DWORD *)(4 * v24);
  if ( !(4 * v24) )
  {
    v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v14 = v20;
    if ( v20 >= 0 )
    {
      v6 = (wil::details *)hHandle;
      goto LABEL_8;
    }
    v17 = (unsigned int)v20;
    v18 = 311;
LABEL_16:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, (unsigned int)"wil", (const char *)v17, v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      (wil::details **)&hHandle,
      v19);
    return v14;
  }
  *a2 = v15;
  ++*v15;
LABEL_8:
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
    wil::details::CloseHandle(v6, v13);
  return 0;
}

```

## disassembly

```asm
0x180003038  mov     [rsp-8+arg_10], rbx
0x18000303d  mov     [rsp-8+arg_18], rsi
0x180003042  push    rbp
0x180003043  push    rdi
0x180003044  push    r14
0x180003046  lea     rbp, [rsp-170h]
0x18000304e  sub     rsp, 270h
0x180003055  mov     rax, cs:__security_cookie
0x18000305c  xor     rax, rsp
0x18000305f  mov     [rbp+180h+var_20], rax
0x180003066  mov     r14, rdx
0x180003069  mov     qword ptr [rdx], 0
0x180003070  mov     rbx, rcx
0x180003073  call    cs:__imp_GetCurrentProcessId
0x180003079  mov     [rsp+280h+var_258], rbx
0x18000307e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003085  mov     r9d, eax
0x180003088  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180003090  mov     edx, 104h; unsigned __int64
0x180003095  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000309a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000309f  mov     r9d, 1F0001h; dwDesiredAccess
0x1800030a5  mov     [rsp+280h+hHandle], 0
0x1800030ae  xor     r8d, r8d; dwFlags
0x1800030b1  lea     rdx, [rsp+280h+Name]; lpName
0x1800030b6  xor     ecx, ecx; lpMutexAttributes
0x1800030b8  call    cs:__imp_CreateMutexExW
0x1800030be  mov     rdx, rax
0x1800030c1  lea     rcx, [rsp+280h+hHandle]
0x1800030c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800030cb  mov     rbx, [rsp+280h+hHandle]
0x1800030d0  test    rbx, rbx
0x1800030d3  jz      loc_18000317E
0x1800030d9  xor     r8d, r8d; bAlertable
0x1800030dc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800030df  mov     rcx, rbx; hHandle
0x1800030e2  call    cs:__imp_WaitForSingleObjectEx
0x1800030e8  cmp     eax, 102h
0x1800030ed  jz      loc_180003185
0x1800030f3  test    eax, 0FFFFFF7Fh
0x1800030f8  jnz     loc_180003202
0x1800030fe  mov     rsi, rbx
0x180003101  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180003106  mov     [rsp+280h+var_240], rsi
0x18000310b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003110  mov     [rsp+280h+var_248], 0
0x180003119  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000311e  mov     edi, eax
0x180003120  test    eax, eax
0x180003122  js      short loc_180003196
0x180003124  mov     rax, [rsp+280h+var_248]
0x180003129  lea     rcx, ds:0[rax*4]
0x180003131  test    rcx, rcx
0x180003134  jz      loc_18000320F
0x18000313a  mov     [r14], rcx
0x18000313d  mov     eax, [rcx]
0x18000313f  inc     eax
0x180003141  mov     [rcx], eax
0x180003143  test    rsi, rsi
0x180003146  jnz     short loc_18000318C
0x180003148  test    rbx, rbx
0x18000314b  jz      short loc_180003155
0x18000314d  mov     rcx, rbx; this
0x180003150  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180003155  xor     eax, eax
0x180003157  mov     rcx, [rbp+180h+var_20]
0x18000315e  xor     rcx, rsp; StackCookie
0x180003161  call    __security_check_cookie
0x180003166  lea     r11, [rsp+280h+var_10]
0x18000316e  mov     rbx, [r11+30h]
0x180003172  mov     rsi, [r11+38h]
0x180003176  mov     rsp, r11
0x180003179  pop     r14
0x18000317b  pop     rdi
0x18000317c  pop     rbp
0x18000317d  retn
0x18000317e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003183  jmp     short loc_180003157
0x180003185  xor     esi, esi
0x180003187  jmp     loc_180003101
0x18000318c  mov     rcx, rsi; this
0x18000318f  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180003194  jmp     short loc_180003148
0x180003196  mov     rcx, [rbp+188h]; this
0x18000319d  lea     r8, aWil; "wil"
0x1800031a4  mov     r9d, edi; char *
0x1800031a7  mov     edx, 66h ; 'f'; void *
0x1800031ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031b1  mov     rcx, [rbp+188h]; this
0x1800031b8  lea     r8, aWil; "wil"
0x1800031bf  mov     r9d, edi; char *
0x1800031c2  mov     edx, 6Fh ; 'o'; void *
0x1800031c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031cc  mov     r9d, edi; char *
0x1800031cf  mov     edx, 12Eh; void *
0x1800031d4  mov     rcx, [rbp+188h]; this
0x1800031db  lea     r8, aWil; "wil"
0x1800031e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031e7  lea     rcx, [rsp+280h+var_240]
0x1800031ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800031f1  lea     rcx, [rsp+280h+hHandle]
0x1800031f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800031fb  mov     eax, edi
0x1800031fd  jmp     loc_180003157
0x180003202  mov     rcx, [rbp+188h]; this
0x180003209  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000320f  mov     r8, r14
0x180003212  lea     rdx, [rsp+280h+hHandle]
0x180003217  lea     rcx, [rsp+280h+Name]
0x18000321c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003221  mov     edi, eax
0x180003223  test    eax, eax
0x180003225  jns     short loc_180003231
0x180003227  mov     r9d, eax
0x18000322a  mov     edx, 137h
0x18000322f  jmp     short loc_1800031D4
0x180003231  mov     rbx, [rsp+280h+hHandle]
0x180003236  jmp     loc_180003143
```
