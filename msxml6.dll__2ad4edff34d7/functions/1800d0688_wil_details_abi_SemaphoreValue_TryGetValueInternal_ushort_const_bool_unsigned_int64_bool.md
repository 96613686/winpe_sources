# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800d0688`
- end: `0x1800d0824`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `HRESULT __fastcall(const wchar_t *name, bool value, unsigned __int64 *name, bool *is64Bit)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800d0614`

## callees

- `0x1800bfc70`
- `0x1800cada0`
- `0x1800cd96c`
- `0x1800ceb14`
- `0x1800cfecc`
- `0x1800cfeec`
- `0x1800d02a4`
- `0x1800d0688`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d06ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d077c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d06ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d077c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d06fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d06fc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *name,
        bool value,
        unsigned __int64 *a3,
        bool *is64Bit)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  const char *v7; // r8
  unsigned int LastError; // ebx
  HRESULT ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  const char *v11; // r8
  HANDLE v12; // rax
  const char *v13; // r8
  HRESULT v14; // eax
  const char *v15; // r8
  int countHigh; // [rsp+20h] [rbp-E0h] BYREF
  int countLow; // [rsp+24h] [rbp-DCh] BYREF
  wil::unique_any_t<wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > semaphoreHigh; // [rsp+28h] [rbp-D8h] BYREF
  wil::unique_any_t<wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > semaphoreLow; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t localName[264]; // [rsp+40h] [rbp-C0h] BYREF
  void *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(localName, 0x104u, name);
  StringCchCatW(localName, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, localName);
  semaphoreLow.m_ptr = v6;
  if ( v6 )
  {
    countLow = 0;
    countHigh = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &countLow);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0xD6u, v11, ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(localName, v10, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, localName);
    semaphoreHigh.m_ptr = v12;
    if ( v12 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &countHigh);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreHigh);
        *a3 = countLow | (unsigned __int64)((__int64)countHigh << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, 0xDEu, v15, v14);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xDCu, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreHigh);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xD0u, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreLow);
  return LastError;
}

```

## disassembly

```asm
0x1800d0688  mov     [rsp-8+arg_8], rbx
0x1800d068d  mov     [rsp-8+arg_18], rdi
0x1800d0692  push    rbp
0x1800d0693  lea     rbp, [rsp-160h]
0x1800d069b  sub     rsp, 260h
0x1800d06a2  mov     rax, cs:__security_cookie
0x1800d06a9  xor     rax, rsp
0x1800d06ac  mov     [rbp+160h+var_10], rax
0x1800d06b3  mov     rdi, value
0x1800d06b6  mov     qword ptr [value], 0
0x1800d06bd  mov     value, name; pszSrc
0x1800d06c0  mov     edx, 104h; cchDest
0x1800d06c5  lea     name, [rsp+260h+localName]; pszDest
0x1800d06ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d06cf  lea     value, aP0; "_p0"
0x1800d06d6  lea     name, [rsp+260h+localName]; pszDest
0x1800d06db  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d06e0  lea     value, [rsp+260h+localName]; lpName
0x1800d06e5  xor     edx, edx; bInheritHandle
0x1800d06e7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800d06ec  call    cs:__imp_OpenSemaphoreW
0x1800d06f2  mov     [rsp+260h+semaphoreLow.m_ptr], rax
0x1800d06f7  test    rax, rax
0x1800d06fa  jnz     short loc_1800D0723
0x1800d06fc  call    cs:__imp_GetLastError
0x1800d0702  cmp     eax, 2
0x1800d0705  jz      loc_1800D07F2
0x1800d070b  mov     name, [rbp+168h]; callerReturnAddress
0x1800d0712  mov     edx, 0D0h; lineNumber
0x1800d0717  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d071c  mov     ebx, eax
0x1800d071e  jmp     loc_1800D07F4
0x1800d0723  lea     rdx, [rsp+260h+countLow]; count
0x1800d0728  mov     [rsp+260h+countLow], 0
0x1800d0730  mov     name, rax; semaphore
0x1800d0733  mov     [rsp+260h+countHigh], 0
0x1800d073b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800d0740  mov     ebx, eax
0x1800d0742  test    eax, eax
0x1800d0744  jns     short loc_1800D075F
0x1800d0746  mov     name, [rbp+168h]; callerReturnAddress
0x1800d074d  mov     r9d, eax; callerReturnAddress
0x1800d0750  mov     edx, 0D6h; lineNumber
0x1800d0755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d075a  jmp     loc_1800D07F4
0x1800d075f  lea     value, src; "h"
0x1800d0766  lea     name, [rsp+260h+localName]; pszDest
0x1800d076b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d0770  lea     value, [rsp+260h+localName]; lpName
0x1800d0775  xor     edx, edx; bInheritHandle
0x1800d0777  mov     ecx, 1F0003h; dwDesiredAccess
0x1800d077c  call    cs:__imp_OpenSemaphoreW
0x1800d0782  mov     [rsp+260h+semaphoreHigh.m_ptr], rax
0x1800d0787  test    rax, rax
0x1800d078a  jnz     short loc_1800D07AB
0x1800d078c  mov     name, [rbp+168h]; callerReturnAddress
0x1800d0793  mov     edx, 0DCh; lineNumber
0x1800d0798  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d079d  mov     ebx, eax
0x1800d079f  lea     name, [rsp+260h+semaphoreHigh]; this
0x1800d07a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d07a9  jmp     short loc_1800D07F4
0x1800d07ab  lea     rdx, [rsp+260h+countHigh]; count
0x1800d07b0  mov     name, rax; semaphore
0x1800d07b3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800d07b8  mov     ebx, eax
0x1800d07ba  test    eax, eax
0x1800d07bc  jns     short loc_1800D07D4
0x1800d07be  mov     name, [rbp+168h]; callerReturnAddress
0x1800d07c5  mov     r9d, eax; callerReturnAddress
0x1800d07c8  mov     edx, 0DEh; lineNumber
0x1800d07cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d07d2  jmp     short loc_1800D079F
0x1800d07d4  lea     name, [rsp+260h+semaphoreHigh]; this
0x1800d07d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d07de  movsxd  name, [rsp+260h+countHigh]
0x1800d07e3  movsxd  rax, [rsp+260h+countLow]
0x1800d07e8  shl     name, 1Fh
0x1800d07ec  or      name, rax
0x1800d07ef  mov     [rdi], name
0x1800d07f2  xor     ebx, ebx
0x1800d07f4  lea     name, [rsp+260h+semaphoreLow]; this
0x1800d07f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d07fe  mov     eax, ebx
0x1800d0800  mov     name, [rbp+160h+var_10]
0x1800d0807  xor     name, rsp; StackCookie
0x1800d080a  call    __security_check_cookie
0x1800d080f  lea     r11, [rsp+260h+var_s0]
0x1800d0817  mov     rbx, [r11+18h]
0x1800d081b  mov     rdi, [r11+28h]
0x1800d081f  mov     rsp, r11
0x1800d0822  pop     rbp
0x1800d0823  retn
```
