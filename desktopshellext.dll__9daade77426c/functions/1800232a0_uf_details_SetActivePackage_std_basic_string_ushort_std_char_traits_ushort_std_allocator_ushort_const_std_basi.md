# uf::details::SetActivePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800232a0`
- end: `0x180023466`
- name: `?SetActivePackage@details@uf@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800660fc`

## callees

- `0x18000f59c`
- `0x180016148`
- `0x1800232a0`
- `0x18002346c`
- `0x180023668`
- `0x18002661c`
- `0x180062934`
- `0x180064014`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800232e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800232e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233a5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002340d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002340d`

## string_xrefs

- `0x18002342a`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800232f5`: `shellcommon\internal\shell\inc\UndockedFlighting\UndockedFlightingActiveStateCache.h`
- `0x18002334a`: `shellcommon\internal\shell\inc\UndockedFlighting\UndockedFlightingActiveStateCache.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall uf::details::SetActivePackage(
        _QWORD *a1,
        wil::reg::reg_view_details::reg_value_type_info *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  char v8; // r15
  HRESULT v9; // eax
  _QWORD *v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rdx
  DWORD cbData; // eax
  HKEY v16; // r10
  int v17; // eax
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  LPVOID v21; // [rsp+38h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v23[2]; // [rsp+48h] [rbp-30h] BYREF
  _QWORD v24[4]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v8 = 0;
  v21 = 0;
  v9 = CoCreateInstance(&CLSID_UndockedFlightingBroker, 0, 4u, &GUID_a8c5e2f4_8d1b_4e3a_9f2c_1d6a7b8e4c3f, &v21);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UndockedFlightingActiveStateCache.h",
      (const char *)(unsigned int)v9,
      ppv);
  if ( a4[3] > 7u )
    a4 = (_QWORD *)*a4;
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  if ( a1[3] <= 7u )
    v10 = a1;
  else
    v10 = (_QWORD *)*a1;
  v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, _QWORD *, _QWORD *))(*(_QWORD *)v21 + 24LL))(v21, v10, a3, a4);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UndockedFlightingActiveStateCache.h",
      (const char *)(unsigned int)v11,
      ppv);
  if ( uf::details::IsImpersonating(retaddr) )
  {
    v8 = 1;
    v12 = *(_QWORD *)uf::details::GetHkcuKeyImpersonated(&hKey);
  }
  else
  {
    v12 = -2147483647;
  }
  uf::details::create_shared_key_with_expected_access(
    v24,
    v12,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UndockedFlighting\\ActivePackages");
  if ( (v8 & 1) != 0 && hKey )
    RegCloseKey(hKey);
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  if ( v24[0] )
    v13 = *(_QWORD *)v24[0];
  else
    v13 = 0;
  uf::details::create_shared_key_with_expected_access(v23, v13, a1);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(wil::reg::reg_view_details::reg_value_type_info **)a2;
  cbData = wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(a2, v14);
  v17 = RegSetKeyValueW(v16, 0, L"PackageFullName", 1u, a2, cbData);
  if ( v17 > 0 )
    v17 = (unsigned __int16)v17 | 0x80070000;
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v17,
      ppva);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v23);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v24);
  return wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v21);
}

```

## disassembly

```asm
0x1800232a0  push    rbp
0x1800232a2  push    rbx
0x1800232a3  push    rsi
0x1800232a4  push    rdi
0x1800232a5  push    r14
0x1800232a7  push    r15
0x1800232a9  mov     rbp, rsp
0x1800232ac  sub     rsp, 78h
0x1800232b0  mov     r14, r9
0x1800232b3  mov     rsi, r8
0x1800232b6  mov     rdi, rdx
0x1800232b9  mov     rbx, rcx
0x1800232bc  xor     r15d, r15d
0x1800232bf  mov     [rbp+var_48], r15d
0x1800232c3  mov     [rbp+var_40], r15
0x1800232c7  lea     rax, [rbp+var_40]
0x1800232cb  mov     [rsp+78h+ppv], rax; int
0x1800232d0  lea     r9, _GUID_a8c5e2f4_8d1b_4e3a_9f2c_1d6a7b8e4c3f; riid
0x1800232d7  xor     edx, edx; pUnkOuter
0x1800232d9  lea     r8d, [r15+4]; dwClsContext
0x1800232dd  lea     rcx, CLSID_UndockedFlightingBroker; rclsid
0x1800232e4  call    cs:__imp_CoCreateInstance
0x1800232ea  mov     rcx, [rbp+30h]; this
0x1800232ee  test    eax, eax
0x1800232f0  jns     short loc_180023306
0x1800232f2  mov     r9d, eax; char *
0x1800232f5  lea     r8, aShellcommonInt_6; "shellcommon\\internal\\shell\\inc\\Undo"...
0x1800232fc  lea     edx, [r15+42h]; void *
0x180023300  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023306  mov     rcx, [rbp+var_40]
0x18002330a  mov     rax, [rcx]
0x18002330d  cmp     qword ptr [r14+18h], 7
0x180023312  jbe     short loc_180023317
0x180023314  mov     r14, [r14]
0x180023317  cmp     qword ptr [rsi+18h], 7
0x18002331c  jbe     short loc_180023321
0x18002331e  mov     rsi, [rsi]
0x180023321  cmp     qword ptr [rbx+18h], 7
0x180023326  jbe     short loc_18002332D
0x180023328  mov     rdx, [rbx]
0x18002332b  jmp     short loc_180023330
0x18002332d  mov     rdx, rbx
0x180023330  mov     r9, r14
0x180023333  mov     r8, rsi
0x180023336  mov     rax, [rax+18h]
0x18002333a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002333f  mov     rcx, [rbp+30h]; this
0x180023343  test    eax, eax
0x180023345  jns     short loc_18002335C
0x180023347  mov     r9d, eax; char *
0x18002334a  lea     r8, aShellcommonInt_6; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180023351  mov     edx, 47h ; 'G'; void *
0x180023356  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002335c  call    ?IsImpersonating@details@uf@@YA_NXZ; uf::details::IsImpersonating(void)
0x180023361  mov     esi, 1
0x180023366  test    al, al
0x180023368  jz      short loc_18002337F
0x18002336a  lea     rcx, [rbp+hKey]
0x18002336e  call    ?GetHkcuKeyImpersonated@details@uf@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; uf::details::GetHkcuKeyImpersonated(void)
0x180023373  nop
0x180023374  mov     r15d, esi
0x180023377  mov     [rbp+var_48], esi
0x18002337a  mov     rdx, [rax]
0x18002337d  jmp     short loc_180023386
0x18002337f  mov     rdx, 0FFFFFFFF80000001h
0x180023386  lea     r8, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002338d  lea     rcx, [rbp+var_20]
0x180023391  call    ?create_shared_key_with_expected_access@details@uf@@YA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; uf::details::create_shared_key_with_expected_access(HKEY__ *,ushort const *)
0x180023396  nop
0x180023397  test    sil, r15b
0x18002339a  jz      short loc_1800233AB
0x18002339c  mov     rcx, [rbp+hKey]; hKey
0x1800233a0  test    rcx, rcx
0x1800233a3  jz      short loc_1800233AB
0x1800233a5  call    cs:__imp_RegCloseKey
0x1800233ab  cmp     qword ptr [rbx+18h], 7
0x1800233b0  jbe     short loc_1800233B5
0x1800233b2  mov     rbx, [rbx]
0x1800233b5  mov     rax, [rbp+var_20]
0x1800233b9  test    rax, rax
0x1800233bc  jz      short loc_1800233C3
0x1800233be  mov     rdx, [rax]
0x1800233c1  jmp     short loc_1800233C5
0x1800233c3  xor     edx, edx
0x1800233c5  mov     r8, rbx
0x1800233c8  lea     rcx, [rbp+var_30]
0x1800233cc  call    ?create_shared_key_with_expected_access@details@uf@@YA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; uf::details::create_shared_key_with_expected_access(HKEY__ *,ushort const *)
0x1800233d1  nop
0x1800233d2  cmp     qword ptr [rdi+18h], 7
0x1800233d7  jbe     short loc_1800233DC
0x1800233d9  mov     rdi, [rdi]
0x1800233dc  mov     rax, [rbp+var_30]
0x1800233e0  test    rax, rax
0x1800233e3  jz      short loc_1800233EA
0x1800233e5  mov     r10, [rax]
0x1800233e8  jmp     short loc_1800233ED
0x1800233ea  xor     r10d, r10d
0x1800233ed  mov     rcx, rdi; this
0x1800233f0  call    ?get_buffer_size_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAKPEBG@Z; wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(ushort const *)
0x1800233f5  mov     [rsp+78h+cbData], eax; cbData
0x1800233f9  mov     [rsp+78h+ppv], rdi; int
0x1800233fe  mov     r9d, esi; dwType
0x180023401  lea     r8, aPackagefullnam; "PackageFullName"
0x180023408  xor     edx, edx; lpSubKey
0x18002340a  mov     rcx, r10; hKey
0x18002340d  call    cs:__imp_RegSetKeyValueW
0x180023413  test    eax, eax
0x180023415  jle     short loc_18002341F
0x180023417  movzx   eax, ax
0x18002341a  or      eax, 80070000h
0x18002341f  mov     rcx, [rbp+30h]; this
0x180023423  test    eax, eax
0x180023425  jns     short loc_18002343C
0x180023427  mov     r9d, eax; char *
0x18002342a  lea     r8, aOnecoreInterna_16; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023431  mov     edx, 1CBEh; void *
0x180023436  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002343c  lea     rcx, [rbp+var_30]
0x180023440  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180023445  nop
0x180023446  lea     rcx, [rbp+var_20]
0x18002344a  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002344f  nop
0x180023450  lea     rcx, [rbp+var_40]
0x180023454  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180023459  add     rsp, 78h
0x18002345d  pop     r15
0x18002345f  pop     r14
0x180023461  pop     rdi
0x180023462  pop     rsi
0x180023463  pop     rbx
0x180023464  pop     rbp
0x180023465  retn
```
