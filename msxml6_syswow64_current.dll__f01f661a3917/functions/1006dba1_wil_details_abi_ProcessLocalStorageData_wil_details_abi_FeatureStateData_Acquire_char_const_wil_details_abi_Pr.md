# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1006dba1`
- end: `0x1006dcc5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z`
- size: `292`
- prototype: `HRESULT __userpurge@<eax>(const char *staticNameWithVersion@<ecx>, wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> **data@<edx>)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1006e797`

## callees

- `0x1006b510`
- `0x1006d864`
- `0x1006d87b`
- `0x1006dba1`
- `0x1006e61f`
- `0x1006f1ef`
- `0x1006ffd8`
- `0x10070469`
- `0x100706e8`
- `0x10070dc5`
- `0x10070f4f`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1006dbf9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1006dbf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006dbc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006dbc5`

## pseudocode

```c
HRESULT __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        const char *staticNameWithVersion,
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> **data)
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
  StringCchPrintfW(name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 168, staticNameWithVersion);
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
      *data = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> *)pointer;
      (*data)->m_refCount = *v7 + 1;
    }
    else
    {
      LastErrorFailHr = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(
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
0x1006dba1  mov     edi, edi
0x1006dba3  push    ebp
0x1006dba4  mov     ebp, esp
0x1006dba6  sub     esp, 218h
0x1006dbac  mov     eax, ___security_cookie
0x1006dbb1  xor     eax, ebp
0x1006dbb3  mov     [ebp+var_4], eax
0x1006dbb6  push    ebx
0x1006dbb7  push    esi
0x1006dbb8  push    edi
0x1006dbb9  mov     edi, data
0x1006dbbb  xor     ebx, ebx
0x1006dbbd  push    staticNameWithVersion
0x1006dbbe  push    0A8h
0x1006dbc3  mov     [edi], ebx
0x1006dbc5  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1006dbcb  push    eax
0x1006dbcc  push    offset aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1006dbd1  lea     eax, [ebp+name]
0x1006dbd7  push    104h; cchDest
0x1006dbdc  push    eax; pszDest
0x1006dbdd  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1006dbe2  add     esp, 18h
0x1006dbe5  mov     [ebp+mutex.m_ptr], ebx
0x1006dbeb  lea     eax, [ebp+name]
0x1006dbf1  push    1F0001h; dwDesiredAccess
0x1006dbf6  push    ebx; dwMilliseconds
0x1006dbf7  push    eax; pStatus
0x1006dbf8  push    ebx; lpMutexAttributes
0x1006dbf9  call    ds:__imp__CreateMutexExW@16; CreateMutexExW(x,x,x,x)
0x1006dbff  push    eax; bAlertable
0x1006dc00  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006dc06  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x1006dc0b  cmp     [ebp+mutex.m_ptr], ebx
0x1006dc11  jnz     short loc_1006DC1C
0x1006dc13  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1006dc18  mov     esi, eax
0x1006dc1a  jmp     short loc_1006DC8A
0x1006dc1c  sub     esp, 0Ch
0x1006dc1f  lea     eax, [ebp+lock]
0x1006dc25  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006dc2b  push    eax; result
0x1006dc2c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QBE?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@@2@PAKKH@Z
0x1006dc31  lea     data, [ebp+pointer]; pointer
0x1006dc37  mov     [ebp+pointer], ebx
0x1006dc3d  lea     staticNameWithVersion, [ebp+name]; name
0x1006dc43  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SGJPBGPAPAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1006dc48  mov     esi, eax
0x1006dc4a  test    esi, esi
0x1006dc4c  jns     short loc_1006DC6A
0x1006dc4e  mov     data, 12Eh; lineNumber
0x1006dc53  push    esi
0x1006dc54  push    staticNameWithVersion; hr
0x1006dc55  mov     staticNameWithVersion, [ebp+4]; callerReturnAddress
0x1006dc58  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1006dc5d  lea     staticNameWithVersion, [ebp+lock]; this
0x1006dc63  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006dc68  jmp     short loc_1006DC8A
0x1006dc6a  mov     eax, [ebp+pointer]
0x1006dc70  test    eax, eax
0x1006dc72  jz      short loc_1006DCA6
0x1006dc74  mov     [edi], eax
0x1006dc76  mov     staticNameWithVersion, [eax]
0x1006dc78  mov     eax, [edi]
0x1006dc7a  inc     staticNameWithVersion
0x1006dc7b  mov     [eax], staticNameWithVersion
0x1006dc7d  lea     staticNameWithVersion, [ebp+lock]; this
0x1006dc83  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006dc88  mov     esi, ebx
0x1006dc8a  lea     staticNameWithVersion, [ebp+mutex]; this
0x1006dc90  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1006dc95  mov     staticNameWithVersion, [ebp+var_4]
0x1006dc98  mov     eax, esi
0x1006dc9a  pop     edi
0x1006dc9b  pop     esi
0x1006dc9c  xor     staticNameWithVersion, ebp; cookie
0x1006dc9e  pop     ebx
0x1006dc9f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006dca4  leave
0x1006dca5  retn
0x1006dca6  push    edi; data
0x1006dca7  lea     data, [ebp+mutex]; mutex
0x1006dcad  lea     staticNameWithVersion, [ebp+name]; name
0x1006dcb3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z
0x1006dcb8  mov     esi, eax
0x1006dcba  test    esi, esi
0x1006dcbc  jns     short loc_1006DC7D
0x1006dcbe  mov     data, 137h
0x1006dcc3  jmp     short loc_1006DC53
```
