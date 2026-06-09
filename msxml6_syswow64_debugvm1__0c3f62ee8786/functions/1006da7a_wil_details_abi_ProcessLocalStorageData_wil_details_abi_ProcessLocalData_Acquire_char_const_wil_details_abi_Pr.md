# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1006da7a`
- end: `0x1006db9b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z`
- size: `289`
- prototype: `HRESULT __userpurge@<eax>(const char *staticNameWithVersion@<ecx>, wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data@<edx>)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1006e74e`

## callees

- `0x1006b510`
- `0x1006d864`
- `0x1006d87b`
- `0x1006da7a`
- `0x1006e61f`
- `0x1006f12b`
- `0x1006ffd8`
- `0x10070469`
- `0x100706e8`
- `0x10070dc5`
- `0x10070f4f`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1006dacf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1006dacf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006da9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006da9b`

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
0x1006da7a  mov     edi, edi
0x1006da7c  push    ebp
0x1006da7d  mov     ebp, esp
0x1006da7f  sub     esp, 218h
0x1006da85  mov     eax, ___security_cookie
0x1006da8a  xor     eax, ebp
0x1006da8c  mov     [ebp+var_4], eax
0x1006da8f  push    ebx
0x1006da90  push    esi
0x1006da91  push    edi
0x1006da92  mov     edi, data
0x1006da94  xor     ebx, ebx
0x1006da96  push    staticNameWithVersion
0x1006da97  push    40h ; '@'
0x1006da99  mov     [edi], ebx
0x1006da9b  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1006daa1  push    eax
0x1006daa2  push    offset aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1006daa7  lea     eax, [ebp+name]
0x1006daad  push    104h; cchDest
0x1006dab2  push    eax; pszDest
0x1006dab3  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1006dab8  add     esp, 18h
0x1006dabb  mov     [ebp+mutex.m_ptr], ebx
0x1006dac1  lea     eax, [ebp+name]
0x1006dac7  push    1F0001h; dwDesiredAccess
0x1006dacc  push    ebx; dwMilliseconds
0x1006dacd  push    eax; pStatus
0x1006dace  push    ebx; lpMutexAttributes
0x1006dacf  call    ds:__imp__CreateMutexExW@16; CreateMutexExW(x,x,x,x)
0x1006dad5  push    eax; bAlertable
0x1006dad6  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006dadc  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x1006dae1  cmp     [ebp+mutex.m_ptr], ebx
0x1006dae7  jnz     short loc_1006DAF2
0x1006dae9  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1006daee  mov     esi, eax
0x1006daf0  jmp     short loc_1006DB60
0x1006daf2  sub     esp, 0Ch
0x1006daf5  lea     eax, [ebp+lock]
0x1006dafb  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006db01  push    eax; result
0x1006db02  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QBE?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@@2@PAKKH@Z
0x1006db07  lea     data, [ebp+pointer]; pointer
0x1006db0d  mov     [ebp+pointer], ebx
0x1006db13  lea     staticNameWithVersion, [ebp+name]; name
0x1006db19  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SGJPBGPAPAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1006db1e  mov     esi, eax
0x1006db20  test    esi, esi
0x1006db22  jns     short loc_1006DB40
0x1006db24  mov     data, 12Eh; lineNumber
0x1006db29  push    esi
0x1006db2a  push    staticNameWithVersion; hr
0x1006db2b  mov     staticNameWithVersion, [ebp+4]; callerReturnAddress
0x1006db2e  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1006db33  lea     staticNameWithVersion, [ebp+lock]; this
0x1006db39  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006db3e  jmp     short loc_1006DB60
0x1006db40  mov     eax, [ebp+pointer]
0x1006db46  test    eax, eax
0x1006db48  jz      short loc_1006DB7C
0x1006db4a  mov     [edi], eax
0x1006db4c  mov     staticNameWithVersion, [eax]
0x1006db4e  mov     eax, [edi]
0x1006db50  inc     staticNameWithVersion
0x1006db51  mov     [eax], staticNameWithVersion
0x1006db53  lea     staticNameWithVersion, [ebp+lock]; this
0x1006db59  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006db5e  mov     esi, ebx
0x1006db60  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006db66  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006db6b  mov     staticNameWithVersion, [ebp+var_4]
0x1006db6e  mov     eax, esi
0x1006db70  pop     edi
0x1006db71  pop     esi
0x1006db72  xor     staticNameWithVersion, ebp; cookie
0x1006db74  pop     ebx
0x1006db75  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006db7a  leave
0x1006db7b  retn
0x1006db7c  push    edi; data
0x1006db7d  lea     data, [ebp+mutex]; mutex
0x1006db83  lea     staticNameWithVersion, [ebp+name]; name
0x1006db89  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z
0x1006db8e  mov     esi, eax
0x1006db90  test    esi, esi
0x1006db92  jns     short loc_1006DB53
0x1006db94  mov     data, 137h
0x1006db99  jmp     short loc_1006DB29
```
