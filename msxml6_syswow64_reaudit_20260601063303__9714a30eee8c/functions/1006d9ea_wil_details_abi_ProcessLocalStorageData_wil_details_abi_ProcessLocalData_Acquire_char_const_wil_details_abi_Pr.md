# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1006d9ea`
- end: `0x1006db0b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z`
- size: `289`
- prototype: `HRESULT __userpurge@<eax>(const char *staticNameWithVersion@<ecx>, wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data@<edx>)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1006e6be`

## callees

- `0x1006b470`
- `0x1006d7d4`
- `0x1006d7eb`
- `0x1006d9ea`
- `0x1006e58f`
- `0x1006f09b`
- `0x1006ff48`
- `0x100703d9`
- `0x10070658`
- `0x10070d35`
- `0x10070ebf`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1006da3f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1006da3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006da0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006da0b`

## pseudocode

```c
HRESULT __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        const char *staticNameWithVersion,
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // eax
  HRESULT LastErrorFailHr; // esi
  wil::details::in1diag3 *v6; // ecx
  _DWORD *v7; // eax
  unsigned int *v9; // [esp-Ch] [ebp-230h]
  unsigned int v10; // [esp-8h] [ebp-22Ch]
  int v12; // [esp-4h] [ebp-228h]
  unsigned int v13; // [esp+0h] [ebp-224h]
  const char *v14; // [esp+4h] [ebp-220h]
  int v15; // [esp+8h] [ebp-21Ch]
  void *pointer; // [esp+Ch] [ebp-218h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__stdcall*)(void *) noexcept,&wil::details::ReleaseMutex,wistd::integral_constant<unsigned int,2>,void *,void *,0,std::nullptr_t> > > lock; // [esp+10h] [ebp-214h] BYREF
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__stdcall*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned int,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > mutex; // [esp+14h] [ebp-210h] BYREF
  wchar_t name[260]; // [esp+18h] [ebp-20Ch] BYREF

  *data = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 64, staticNameWithVersion);
  mutex.m_ptr = 0;
  v4 = CreateMutexExW(0, name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
    &mutex,
    v4);
  if ( mutex.m_ptr )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QBE_AV__unique_any_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_ReleaseMutex_details_wil__YGX0_ZU__integral_constant_I_01_wistd__PAXPAX_0A___T_details_wil___details_wil___2_PAKKH_Z(
      &mutex,
      &lock,
      v9,
      v10,
      v12);
    pointer = 0;
    LastErrorFailHr = wil::details_abi::SemaphoreValue::TryGetPointer(name, &pointer);
    if ( LastErrorFailHr < 0 )
    {
LABEL_4:
      wil::details::in1diag3::Return_Hr(v6, LastErrorFailHr, v13, v14, v15);
      __1__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_ReleaseMutex_details_wil__YGX0_ZU__integral_constant_I_01_wistd__PAXPAX_0A___T_details_wil___details_wil__QAE_XZ(&lock);
      goto LABEL_8;
    }
    v7 = pointer;
    if ( pointer )
    {
      *data = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> *)pointer;
      (*data)->m_refCount = *v7 + 1;
    }
    else
    {
      LastErrorFailHr = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
                          name,
                          &mutex,
                          data);
      if ( LastErrorFailHr < 0 )
        goto LABEL_4;
    }
    __1__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_ReleaseMutex_details_wil__YGX0_ZU__integral_constant_I_01_wistd__PAXPAX_0A___T_details_wil___details_wil__QAE_XZ(&lock);
    LastErrorFailHr = 0;
    goto LABEL_8;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr();
LABEL_8:
  __1__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAE_XZ(&mutex);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1006d9ea  mov     edi, edi
0x1006d9ec  push    ebp
0x1006d9ed  mov     ebp, esp
0x1006d9ef  sub     esp, 218h
0x1006d9f5  mov     eax, ___security_cookie
0x1006d9fa  xor     eax, ebp
0x1006d9fc  mov     [ebp+var_4], eax
0x1006d9ff  push    ebx
0x1006da00  push    esi
0x1006da01  push    edi
0x1006da02  mov     edi, data
0x1006da04  xor     ebx, ebx
0x1006da06  push    staticNameWithVersion
0x1006da07  push    40h ; '@'
0x1006da09  mov     [edi], ebx
0x1006da0b  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1006da11  push    eax
0x1006da12  push    offset aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1006da17  lea     eax, [ebp+name]
0x1006da1d  push    104h; cchDest
0x1006da22  push    eax; pszDest
0x1006da23  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1006da28  add     esp, 18h
0x1006da2b  mov     [ebp+mutex.m_ptr], ebx
0x1006da31  lea     eax, [ebp+name]
0x1006da37  push    1F0001h; dwDesiredAccess
0x1006da3c  push    ebx; dwMilliseconds
0x1006da3d  push    eax; pStatus
0x1006da3e  push    ebx; lpMutexAttributes
0x1006da3f  call    ds:__imp__CreateMutexExW@16; CreateMutexExW(x,x,x,x)
0x1006da45  push    eax; bAlertable
0x1006da46  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006da4c  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x1006da51  cmp     [ebp+mutex.m_ptr], ebx
0x1006da57  jnz     short loc_1006DA62
0x1006da59  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1006da5e  mov     esi, eax
0x1006da60  jmp     short loc_1006DAD0
0x1006da62  sub     esp, 0Ch
0x1006da65  lea     eax, [ebp+lock]
0x1006da6b  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006da71  push    eax; result
0x1006da72  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QBE?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@@2@PAKKH@Z
0x1006da77  lea     data, [ebp+pointer]; pointer
0x1006da7d  mov     [ebp+pointer], ebx
0x1006da83  lea     staticNameWithVersion, [ebp+name]; name
0x1006da89  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SGJPBGPAPAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1006da8e  mov     esi, eax
0x1006da90  test    esi, esi
0x1006da92  jns     short loc_1006DAB0
0x1006da94  mov     data, 12Eh; lineNumber
0x1006da99  push    esi
0x1006da9a  push    staticNameWithVersion; hr
0x1006da9b  mov     staticNameWithVersion, [ebp+4]; callerReturnAddress
0x1006da9e  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1006daa3  lea     staticNameWithVersion, [ebp+lock]; this
0x1006daa9  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006daae  jmp     short loc_1006DAD0
0x1006dab0  mov     eax, [ebp+pointer]
0x1006dab6  test    eax, eax
0x1006dab8  jz      short loc_1006DAEC
0x1006daba  mov     [edi], eax
0x1006dabc  mov     staticNameWithVersion, [eax]
0x1006dabe  mov     eax, [edi]
0x1006dac0  inc     staticNameWithVersion
0x1006dac1  mov     [eax], staticNameWithVersion
0x1006dac3  lea     staticNameWithVersion, [ebp+lock]; this
0x1006dac9  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006dace  mov     esi, ebx
0x1006dad0  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006dad6  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006dadb  mov     staticNameWithVersion, [ebp+var_4]
0x1006dade  mov     eax, esi
0x1006dae0  pop     edi
0x1006dae1  pop     esi
0x1006dae2  xor     staticNameWithVersion, ebp; cookie
0x1006dae4  pop     ebx
0x1006dae5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006daea  leave
0x1006daeb  retn
0x1006daec  push    edi; data
0x1006daed  lea     data, [ebp+mutex]; mutex
0x1006daf3  lea     staticNameWithVersion, [ebp+name]; name
0x1006daf9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z
0x1006dafe  mov     esi, eax
0x1006db00  test    esi, esi
0x1006db02  jns     short loc_1006DAC3
0x1006db04  mov     data, 137h
0x1006db09  jmp     short loc_1006DA99
```
