# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1000fa6a`
- end: `0x1000fbc3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x10007e10`

## callees

- `0x10006937`
- `0x10007173`
- `0x100075ad`
- `0x10007630`
- `0x10007661`
- `0x10007aee`
- `0x1000f6d4`
- `0x1000fa6a`
- `0x1000fcc8`
- `0x1000fdee`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1000fabf`
- `KERNEL32!CreateMutexExW` at `0x1000fabf`
- `KERNEL32!GetCurrentProcessId` at `0x1000fa8b`
- `KERNEL32!GetCurrentProcessId` at `0x1000fa8b`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        int a1,
        _DWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // eax
  HANDLE v5; // esi
  void *v6; // edi
  bool v7; // cl
  void *ValueInternal; // eax
  _DWORD *v9; // eax
  int v11; // eax
  int v12; // [esp-Ch] [ebp-234h]
  int v13; // [esp-8h] [ebp-230h]
  int v15; // [esp-4h] [ebp-22Ch]
  wil::details *v16; // [esp+0h] [ebp-228h]
  void *v17; // [esp+0h] [ebp-228h]
  unsigned int v18; // [esp+0h] [ebp-228h]
  bool *v19; // [esp+4h] [ebp-224h]
  const char *v20; // [esp+4h] [ebp-224h]
  const char *v21; // [esp+4h] [ebp-224h]
  int v22; // [esp+8h] [ebp-220h]
  int v23; // [esp+8h] [ebp-220h]
  unsigned __int16 v24[4]; // [esp+Ch] [ebp-21Ch] BYREF
  wil::details *v25; // [esp+14h] [ebp-214h] BYREF
  HANDLE hObject; // [esp+18h] [ebp-210h] BYREF
  WCHAR Name[260]; // [esp+1Ch] [ebp-20Ch] BYREF

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 64, a1);
  hObject = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
    &hObject,
    Mutex);
  v5 = hObject;
  if ( !hObject )
    return wil::details::GetLastErrorFailHr(v16);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QBE_AV__unique_any_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_ReleaseMutex_details_wil__YGX0_ZU__integral_constant_I_01_wistd__PAXPAX_0A___T_details_wil___details_wil___2_PAKKH_Z(
    &hObject,
    &v25,
    v12,
    v13,
    v15);
  *(_QWORD *)v24 = 0;
  ValueInternal = (void *)wil::details_abi::SemaphoreValue::TryGetValueInternal(v24, v7, (unsigned __int64 *)v16, v19);
  v6 = ValueInternal;
  if ( (int)ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)"wil", ValueInternal, (unsigned int)v17, v20, v22);
    wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)"wil", v6, v18, v21, v23);
LABEL_14:
    wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)"wil", v6, (unsigned int)v17, v20, v22);
    goto LABEL_8;
  }
  v9 = (_DWORD *)(4 * *(_DWORD *)v24);
  if ( 4 * *(_DWORD *)v24 )
  {
    *a2 = v9;
    *(_DWORD *)*a2 = *v9 + 1;
  }
  else
  {
    v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
            Name,
            (int)a2);
    v5 = hObject;
    v6 = (void *)v11;
    if ( v11 < 0 )
      goto LABEL_14;
  }
  v6 = 0;
LABEL_8:
  if ( v25 )
    wil::details::ReleaseMutex(v25, v17);
  if ( v5 )
    wil::details::CloseHandle(v5, v17);
  return (int)v6;
}

```

## disassembly

```asm
0x1000fa6a  mov     edi, edi
0x1000fa6c  push    ebp
0x1000fa6d  mov     ebp, esp
0x1000fa6f  sub     esp, 21Ch
0x1000fa75  mov     eax, ___security_cookie
0x1000fa7a  xor     eax, ebp
0x1000fa7c  mov     [ebp+var_4], eax
0x1000fa7f  push    ebx; int
0x1000fa80  push    esi; char *
0x1000fa81  push    edi; unsigned int
0x1000fa82  mov     ebx, edx
0x1000fa84  xor     esi, esi
0x1000fa86  push    ecx
0x1000fa87  push    40h ; '@'
0x1000fa89  mov     [ebx], esi
0x1000fa8b  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1000fa91  push    eax
0x1000fa92  push    offset aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1000fa97  lea     eax, [ebp+Name]
0x1000fa9d  push    104h; unsigned int
0x1000faa2  push    eax; unsigned __int16 *
0x1000faa3  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1000faa8  add     esp, 18h
0x1000faab  mov     [ebp+hObject], esi
0x1000fab1  lea     eax, [ebp+Name]
0x1000fab7  push    1F0001h; dwDesiredAccess
0x1000fabc  push    esi; dwFlags
0x1000fabd  push    eax; lpName
0x1000fabe  push    esi; lpMutexAttributes
0x1000fabf  call    ds:__imp__CreateMutexExW@16; CreateMutexExW(x,x,x,x)
0x1000fac5  push    eax
0x1000fac6  lea     ecx, [ebp+hObject]
0x1000facc  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x1000fad1  mov     esi, [ebp+hObject]
0x1000fad7  test    esi, esi
0x1000fad9  jnz     short loc_1000FAE7
0x1000fadb  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1000fae0  mov     edi, eax
0x1000fae2  jmp     loc_1000FB7F
0x1000fae7  sub     esp, 0Ch
0x1000faea  lea     eax, [ebp+var_214]
0x1000faf0  lea     ecx, [ebp+hObject]
0x1000faf6  push    eax
0x1000faf7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QBE?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@@2@PAKKH@Z
0x1000fafc  push    ecx; bool
0x1000fafd  lea     eax, [ebp+var_21C]
0x1000fb03  xorps   xmm0, xmm0
0x1000fb06  push    eax; unsigned __int16 *
0x1000fb07  lea     ecx, [ebp+Name]
0x1000fb0d  movlpd  qword ptr [ebp+var_21C], xmm0
0x1000fb15  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CGJPBG_NPA_KPA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1000fb1a  mov     edi, eax
0x1000fb1c  test    edi, edi
0x1000fb1e  jns     short loc_1000FB49
0x1000fb20  mov     ecx, [ebp+4]
0x1000fb23  push    edi; void *
0x1000fb24  push    offset aWil; "wil"
0x1000fb29  push    66h ; 'f'
0x1000fb2b  pop     edx
0x1000fb2c  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000fb31  mov     ecx, [ebp+4]
0x1000fb34  push    edi; void *
0x1000fb35  push    offset aWil; "wil"
0x1000fb3a  push    6Fh ; 'o'
0x1000fb3c  pop     edx
0x1000fb3d  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000fb42  mov     edx, 12Eh
0x1000fb47  jmp     short loc_1000FBB3
0x1000fb49  mov     eax, dword ptr [ebp+var_21C]
0x1000fb4f  shl     eax, 2
0x1000fb52  test    eax, eax
0x1000fb54  jz      short loc_1000FB90
0x1000fb56  mov     [ebx], eax
0x1000fb58  mov     ecx, [eax]
0x1000fb5a  mov     eax, [ebx]
0x1000fb5c  inc     ecx
0x1000fb5d  mov     [eax], ecx
0x1000fb5f  xor     edi, edi
0x1000fb61  cmp     [ebp+var_214], 0
0x1000fb68  jz      short loc_1000FB75
0x1000fb6a  push    [ebp+var_214]; this
0x1000fb70  call    ?ReleaseMutex@details@wil@@YGXPAX@Z; wil::details::ReleaseMutex(void *)
0x1000fb75  test    esi, esi
0x1000fb77  jz      short loc_1000FB7F
0x1000fb79  push    esi; hObject
0x1000fb7a  call    ?CloseHandle@details@wil@@YGXPAX@Z; wil::details::CloseHandle(void *)
0x1000fb7f  mov     ecx, [ebp+var_4]
0x1000fb82  mov     eax, edi
0x1000fb84  pop     edi
0x1000fb85  pop     esi
0x1000fb86  xor     ecx, ebp; StackCookie
0x1000fb88  pop     ebx
0x1000fb89  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000fb8e  leave
0x1000fb8f  retn
0x1000fb90  push    ebx; int
0x1000fb91  lea     edx, [ebp+hObject]
0x1000fb97  lea     ecx, [ebp+Name]; unsigned __int16 *
0x1000fb9d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z
0x1000fba2  mov     esi, [ebp+hObject]
0x1000fba8  mov     edi, eax
0x1000fbaa  test    edi, edi
0x1000fbac  jns     short loc_1000FB5F
0x1000fbae  mov     edx, 137h
0x1000fbb3  mov     ecx, [ebp+4]
0x1000fbb6  push    edi; void *
0x1000fbb7  push    offset aWil; "wil"
0x1000fbbc  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000fbc1  jmp     short loc_1000FB61
```
