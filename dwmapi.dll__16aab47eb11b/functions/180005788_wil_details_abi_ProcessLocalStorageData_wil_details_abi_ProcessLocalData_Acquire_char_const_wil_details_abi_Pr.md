# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005788`
- end: `0x180005970`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006474`

## callees

- `0x180003b30`
- `0x180004d20`
- `0x180005788`
- `0x180005cf8`
- `0x180005d14`
- `0x180006180`
- `0x18000a190`
- `0x18000bc38`
- `0x18000c35c`
- `0x18000c704`
- `0x18000d0a0`
- `0x18000ec1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800057ff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800057ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005825`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800057c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800057c3`

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
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rsi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // edi
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v20 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    v16 = v15;
    v17 = 302;
LABEL_7:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    return v15;
  }
  v18 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = (unsigned int)v19;
      v17 = 311;
      goto LABEL_7;
    }
    v6 = v22;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x180005788  mov     [rsp-8+arg_10], rbx
0x18000578d  mov     [rsp-8+arg_18], rsi
0x180005792  push    rbp
0x180005793  push    rdi
0x180005794  push    r14
0x180005796  lea     rbp, [rsp-170h]
0x18000579e  sub     rsp, 270h
0x1800057a5  mov     rax, cs:__security_cookie
0x1800057ac  xor     rax, rsp
0x1800057af  mov     [rbp+180h+var_20], rax
0x1800057b6  mov     r14, rdx
0x1800057b9  mov     qword ptr [rdx], 0
0x1800057c0  mov     rbx, rcx
0x1800057c3  call    cs:__imp_GetCurrentProcessId
0x1800057c9  mov     [rsp+280h+var_258], rbx
0x1800057ce  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800057d5  mov     r9d, eax
0x1800057d8  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x1800057e0  mov     edx, 104h; unsigned __int64
0x1800057e5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800057ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800057ef  mov     r9d, 1F0001h; dwDesiredAccess
0x1800057f5  lea     rdx, [rsp+280h+Name]; lpName
0x1800057fa  xor     r8d, r8d; dwFlags
0x1800057fd  xor     ecx, ecx; lpMutexAttributes
0x1800057ff  call    cs:__imp_CreateMutexExW
0x180005805  mov     [rsp+280h+var_250], rax
0x18000580a  mov     rbx, rax
0x18000580d  test    rax, rax
0x180005810  jnz     short loc_18000581C
0x180005812  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005817  jmp     loc_1800058C6
0x18000581c  xor     r8d, r8d; bAlertable
0x18000581f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005822  mov     rcx, rbx; hHandle
0x180005825  call    cs:__imp_WaitForSingleObjectEx
0x18000582b  cmp     eax, 102h
0x180005830  jnz     loc_18000591E
0x180005836  xor     esi, esi
0x180005838  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18000583d  mov     [rsp+280h+var_240], rsi
0x180005842  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005847  mov     [rsp+280h+var_248], 0
0x180005850  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005855  mov     edi, eax
0x180005857  test    eax, eax
0x180005859  jns     loc_1800058ED
0x18000585f  mov     rcx, [rbp+188h]; this
0x180005866  lea     r8, aWil; "wil"
0x18000586d  mov     r9d, eax; char *
0x180005870  mov     edx, 66h ; 'f'; void *
0x180005875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000587a  mov     rcx, [rbp+188h]; this
0x180005881  lea     r8, aWil; "wil"
0x180005888  mov     r9d, edi; char *
0x18000588b  mov     edx, 6Fh ; 'o'; void *
0x180005890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005895  mov     r9d, edi; char *
0x180005898  mov     edx, 12Eh; void *
0x18000589d  mov     rcx, [rbp+188h]; this
0x1800058a4  lea     r8, aWil; "wil"
0x1800058ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058b0  lea     rcx, [rsp+280h+var_240]
0x1800058b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800058ba  lea     rcx, [rsp+280h+var_250]
0x1800058bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800058c4  mov     eax, edi
0x1800058c6  mov     rcx, [rbp+180h+var_20]
0x1800058cd  xor     rcx, rsp; StackCookie
0x1800058d0  call    __security_check_cookie
0x1800058d5  lea     r11, [rsp+280h+var_10]
0x1800058dd  mov     rbx, [r11+30h]
0x1800058e1  mov     rsi, [r11+38h]
0x1800058e5  mov     rsp, r11
0x1800058e8  pop     r14
0x1800058ea  pop     rdi
0x1800058eb  pop     rbp
0x1800058ec  retn
0x1800058ed  mov     rax, [rsp+280h+var_248]
0x1800058f2  lea     rcx, ds:0[rax*4]
0x1800058fa  test    rcx, rcx
0x1800058fd  jz      short loc_18000593A
0x1800058ff  mov     [r14], rcx
0x180005902  mov     eax, [rcx]
0x180005904  inc     eax
0x180005906  mov     [rcx], eax
0x180005908  test    rsi, rsi
0x18000590b  jnz     short loc_180005966
0x18000590d  test    rbx, rbx
0x180005910  jz      short loc_18000591A
0x180005912  mov     rcx, rbx; this
0x180005915  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000591a  xor     eax, eax
0x18000591c  jmp     short loc_1800058C6
0x18000591e  test    eax, 0FFFFFF7Fh
0x180005923  jz      short loc_180005932
0x180005925  mov     rcx, [rbp+188h]; this
0x18000592c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005932  mov     rsi, rbx
0x180005935  jmp     loc_180005838
0x18000593a  mov     r8, r14
0x18000593d  lea     rdx, [rsp+280h+var_250]
0x180005942  lea     rcx, [rsp+280h+Name]
0x180005947  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000594c  mov     edi, eax
0x18000594e  test    eax, eax
0x180005950  jns     short loc_18000595F
0x180005952  mov     r9d, eax
0x180005955  mov     edx, 137h
0x18000595a  jmp     loc_18000589D
0x18000595f  mov     rbx, [rsp+280h+var_250]
0x180005964  jmp     short loc_180005908
0x180005966  mov     rcx, rsi; this
0x180005969  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000596e  jmp     short loc_18000590D
```
