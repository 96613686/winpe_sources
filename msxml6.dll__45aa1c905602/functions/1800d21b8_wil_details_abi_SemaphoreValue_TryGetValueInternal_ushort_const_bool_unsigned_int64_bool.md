# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800d21b8`
- end: `0x1800d2367`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `HRESULT __fastcall(const wchar_t *name, bool value, unsigned __int64 *name, bool *is64Bit)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800d2140`

## callees

- `0x1800c12f4`
- `0x1800cc6c0`
- `0x1800cf2a0`
- `0x1800d0560`
- `0x1800d19cc`
- `0x1800d19ec`
- `0x1800d1db4`
- `0x1800d21b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d221c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d22b8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d221c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d22b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2232`

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
0x1800d21b8  mov     [rsp-8+arg_8], rbx
0x1800d21bd  mov     [rsp-8+arg_18], rdi
0x1800d21c2  push    rbp
0x1800d21c3  lea     rbp, [rsp-160h]
0x1800d21cb  sub     rsp, 260h
0x1800d21d2  mov     rax, cs:__security_cookie
0x1800d21d9  xor     rax, rsp
0x1800d21dc  mov     [rbp+160h+var_10], rax
0x1800d21e3  mov     rdi, value
0x1800d21e6  mov     qword ptr [value], 0
0x1800d21ed  mov     value, name; pszSrc
0x1800d21f0  mov     edx, 104h; cchDest
0x1800d21f5  lea     name, [rsp+260h+localName]; pszDest
0x1800d21fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d21ff  lea     value, aP0; "_p0"
0x1800d2206  lea     name, [rsp+260h+localName]; pszDest
0x1800d220b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d2210  lea     value, [rsp+260h+localName]; lpName
0x1800d2215  xor     edx, edx; bInheritHandle
0x1800d2217  mov     ecx, 1F0003h; dwDesiredAccess
0x1800d221c  call    cs:__imp_OpenSemaphoreW
0x1800d2223  nop     dword ptr [rax+rax+00h]
0x1800d2228  mov     [rsp+260h+semaphoreLow.m_ptr], rax
0x1800d222d  test    rax, rax
0x1800d2230  jnz     short loc_1800D225F
0x1800d2232  call    cs:__imp_GetLastError
0x1800d2239  nop     dword ptr [rax+rax+00h]
0x1800d223e  cmp     eax, 2
0x1800d2241  jz      loc_1800D2334
0x1800d2247  mov     name, [rbp+168h]; callerReturnAddress
0x1800d224e  mov     edx, 0D0h; lineNumber
0x1800d2253  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d2258  mov     ebx, eax
0x1800d225a  jmp     loc_1800D2336
0x1800d225f  lea     rdx, [rsp+260h+countLow]; count
0x1800d2264  mov     [rsp+260h+countLow], 0
0x1800d226c  mov     name, rax; semaphore
0x1800d226f  mov     [rsp+260h+countHigh], 0
0x1800d2277  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800d227c  mov     ebx, eax
0x1800d227e  test    eax, eax
0x1800d2280  jns     short loc_1800D229B
0x1800d2282  mov     name, [rbp+168h]; callerReturnAddress
0x1800d2289  mov     r9d, eax; callerReturnAddress
0x1800d228c  mov     edx, 0D6h; lineNumber
0x1800d2291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2296  jmp     loc_1800D2336
0x1800d229b  lea     value, src; "h"
0x1800d22a2  lea     name, [rsp+260h+localName]; pszDest
0x1800d22a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d22ac  lea     value, [rsp+260h+localName]; lpName
0x1800d22b1  xor     edx, edx; bInheritHandle
0x1800d22b3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800d22b8  call    cs:__imp_OpenSemaphoreW
0x1800d22bf  nop     dword ptr [rax+rax+00h]
0x1800d22c4  mov     [rsp+260h+semaphoreHigh.m_ptr], rax
0x1800d22c9  test    rax, rax
0x1800d22cc  jnz     short loc_1800D22ED
0x1800d22ce  mov     name, [rbp+168h]; callerReturnAddress
0x1800d22d5  mov     edx, 0DCh; lineNumber
0x1800d22da  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d22df  mov     ebx, eax
0x1800d22e1  lea     name, [rsp+260h+semaphoreHigh]; this
0x1800d22e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d22eb  jmp     short loc_1800D2336
0x1800d22ed  lea     rdx, [rsp+260h+countHigh]; count
0x1800d22f2  mov     name, rax; semaphore
0x1800d22f5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800d22fa  mov     ebx, eax
0x1800d22fc  test    eax, eax
0x1800d22fe  jns     short loc_1800D2316
0x1800d2300  mov     name, [rbp+168h]; callerReturnAddress
0x1800d2307  mov     r9d, eax; callerReturnAddress
0x1800d230a  mov     edx, 0DEh; lineNumber
0x1800d230f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2314  jmp     short loc_1800D22E1
0x1800d2316  lea     name, [rsp+260h+semaphoreHigh]; this
0x1800d231b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d2320  movsxd  name, [rsp+260h+countHigh]
0x1800d2325  movsxd  rax, [rsp+260h+countLow]
0x1800d232a  shl     name, 1Fh
0x1800d232e  or      name, rax
0x1800d2331  mov     [rdi], name
0x1800d2334  xor     ebx, ebx
0x1800d2336  lea     name, [rsp+260h+semaphoreLow]; this
0x1800d233b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d2340  mov     eax, ebx
0x1800d2342  mov     name, [rbp+160h+var_10]
0x1800d2349  xor     name, rsp; StackCookie
0x1800d234c  call    __security_check_cookie
0x1800d2351  lea     r11, [rsp+260h+var_s0]
0x1800d2359  mov     rbx, [r11+18h]
0x1800d235d  mov     rdi, [r11+28h]
0x1800d2361  mov     rsp, r11
0x1800d2364  pop     rbp
0x1800d2365  retn
```
