# uf::details::ClearActivePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180060ac4`
- end: `0x180060c0c`
- name: `?ClearActivePackage@details@uf@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063944`

## callees

- `0x18000f59c`
- `0x180016148`
- `0x18002346c`
- `0x18002661c`
- `0x180039c50`
- `0x180060ac4`
- `0x180062934`
- `0x180064014`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180060af9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180060af9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060ba4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060ba4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180060bc8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180060bc8`

## string_xrefs

- `0x180060b0b`: `shellcommon\internal\shell\inc\UndockedFlighting\UndockedFlightingActiveStateCache.h`
- `0x180060b47`: `shellcommon\internal\shell\inc\UndockedFlighting\UndockedFlightingActiveStateCache.h`
- `0x180060bda`: `shellcommon\internal\shell\inc\UndockedFlighting\UndockedFlightingActiveStateCache.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall uf::details::ClearActivePackage(_QWORD *lpSubKey)
{
  char v2; // di
  HRESULT v3; // eax
  _QWORD *v4; // rdx
  int v5; // eax
  __int64 v6; // rdx
  HKEY v7; // rcx
  unsigned int v8; // eax
  unsigned int ppv; // [rsp+20h] [rbp-28h]
  _QWORD v11[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID v13; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  v13 = 0;
  v3 = CoCreateInstance(&CLSID_UndockedFlightingBroker, 0, 4u, &GUID_a8c5e2f4_8d1b_4e3a_9f2c_1d6a7b8e4c3f, &v13);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UndockedFlightingActiveStateCache.h",
      (const char *)(unsigned int)v3,
      ppv);
  if ( lpSubKey[3] <= 7u )
    v4 = lpSubKey;
  else
    v4 = (_QWORD *)*lpSubKey;
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)v13 + 32LL))(v13, v4);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UndockedFlightingActiveStateCache.h",
      (const char *)(unsigned int)v5,
      ppv);
  if ( uf::details::IsImpersonating(retaddr) )
  {
    v2 = 1;
    v6 = *(_QWORD *)uf::details::GetHkcuKeyImpersonated(&hKey);
  }
  else
  {
    v6 = -2147483647;
  }
  uf::details::create_shared_key_with_expected_access(
    v11,
    v6,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UndockedFlighting\\ActivePackages");
  if ( (v2 & 1) != 0 && hKey )
    RegCloseKey(hKey);
  if ( lpSubKey[3] > 7u )
    lpSubKey = (_QWORD *)*lpSubKey;
  if ( v11[0] )
    v7 = *(HKEY *)v11[0];
  else
    v7 = 0;
  v8 = RegDeleteKeyW(v7, (LPCWSTR)lpSubKey);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x76,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UndockedFlightingActiveStateCache.h",
      (const char *)v8,
      ppv);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v11);
  return wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v13);
}

```

## disassembly

```asm
0x180060ac4  mov     rax, rsp
0x180060ac7  mov     [rax+8], rbx
0x180060acb  push    rdi
0x180060acc  sub     rsp, 40h
0x180060ad0  mov     rbx, rcx
0x180060ad3  xor     edi, edi
0x180060ad5  mov     [rax+10h], edi
0x180060ad8  mov     [rax+18h], rdi
0x180060adc  lea     rax, [rax+18h]
0x180060ae0  mov     qword ptr [rsp+48h+ppv], rax; unsigned int
0x180060ae5  lea     r9, _GUID_a8c5e2f4_8d1b_4e3a_9f2c_1d6a7b8e4c3f; riid
0x180060aec  xor     edx, edx; pUnkOuter
0x180060aee  lea     r8d, [rdi+4]; dwClsContext
0x180060af2  lea     rcx, CLSID_UndockedFlightingBroker; rclsid
0x180060af9  call    cs:__imp_CoCreateInstance
0x180060aff  mov     rcx, [rsp+48h]; this
0x180060b04  test    eax, eax
0x180060b06  jns     short loc_180060B1B
0x180060b08  mov     r9d, eax; char *
0x180060b0b  lea     r8, aShellcommonInt_6; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180060b12  lea     edx, [rdi+6Dh]; void *
0x180060b15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060b1b  mov     rcx, [rsp+48h+arg_10]
0x180060b20  mov     rax, [rcx]
0x180060b23  cmp     qword ptr [rbx+18h], 7
0x180060b28  jbe     short loc_180060B2F
0x180060b2a  mov     rdx, [rbx]
0x180060b2d  jmp     short loc_180060B32
0x180060b2f  mov     rdx, rbx
0x180060b32  mov     rax, [rax+20h]
0x180060b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b3b  mov     rcx, [rsp+48h]; this
0x180060b40  test    eax, eax
0x180060b42  jns     short loc_180060B59
0x180060b44  mov     r9d, eax; char *
0x180060b47  lea     r8, aShellcommonInt_6; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180060b4e  mov     edx, 6Fh ; 'o'; void *
0x180060b53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060b59  call    ?IsImpersonating@details@uf@@YA_NXZ; uf::details::IsImpersonating(void)
0x180060b5e  test    al, al
0x180060b60  jz      short loc_180060B7B
0x180060b62  lea     rcx, [rsp+48h+hKey]
0x180060b67  call    ?GetHkcuKeyImpersonated@details@uf@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; uf::details::GetHkcuKeyImpersonated(void)
0x180060b6c  nop
0x180060b6d  mov     edi, 1
0x180060b72  mov     [rsp+48h+arg_8], edi
0x180060b76  mov     rdx, [rax]
0x180060b79  jmp     short loc_180060B82
0x180060b7b  mov     rdx, 0FFFFFFFF80000001h
0x180060b82  lea     r8, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180060b89  lea     rcx, [rsp+48h+var_18]
0x180060b8e  call    ?create_shared_key_with_expected_access@details@uf@@YA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; uf::details::create_shared_key_with_expected_access(HKEY__ *,ushort const *)
0x180060b93  nop
0x180060b94  test    dil, 1
0x180060b98  jz      short loc_180060BAA
0x180060b9a  mov     rcx, [rsp+48h+hKey]; hKey
0x180060b9f  test    rcx, rcx
0x180060ba2  jz      short loc_180060BAA
0x180060ba4  call    cs:__imp_RegCloseKey
0x180060baa  cmp     qword ptr [rbx+18h], 7
0x180060baf  jbe     short loc_180060BB4
0x180060bb1  mov     rbx, [rbx]
0x180060bb4  mov     rax, [rsp+48h+var_18]
0x180060bb9  test    rax, rax
0x180060bbc  jz      short loc_180060BC3
0x180060bbe  mov     rcx, [rax]
0x180060bc1  jmp     short loc_180060BC5
0x180060bc3  xor     ecx, ecx; hKey
0x180060bc5  mov     rdx, rbx; lpSubKey
0x180060bc8  call    cs:__imp_RegDeleteKeyW
0x180060bce  mov     rcx, [rsp+48h]; this
0x180060bd3  test    eax, eax
0x180060bd5  jz      short loc_180060BEC
0x180060bd7  mov     r9d, eax; char *
0x180060bda  lea     r8, aShellcommonInt_6; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180060be1  mov     edx, 76h ; 'v'; void *
0x180060be6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180060bec  lea     rcx, [rsp+48h+var_18]
0x180060bf1  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180060bf6  nop
0x180060bf7  lea     rcx, [rsp+48h+arg_10]
0x180060bfc  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180060c01  mov     rbx, [rsp+48h+arg_0]
0x180060c06  add     rsp, 40h
0x180060c0a  pop     rdi
0x180060c0b  retn
```
