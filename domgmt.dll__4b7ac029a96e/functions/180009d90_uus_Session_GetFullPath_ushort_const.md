# uus::Session::GetFullPath(ushort const *)

- ea: `0x180009d90`
- end: `0x180009eba`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEBG@Z`
- size: `298`
- prototype: `void *__fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008334`

## callees

- `0x180001ba0`
- `0x180006aa0`
- `0x180007504`
- `0x180008d88`
- `0x180008f94`
- `0x180009d90`
- `0x180009ec0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009e55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009e55`

## string_xrefs

- `0x180009dbe`: `domiprov.dll`

## pseudocode

```c
void *__fastcall uus::Session::GetFullPath(__int64 a1, void *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  LPVOID pv[2]; // [rsp+20h] [rbp-49h] BYREF
  const WCHAR *v10; // [rsp+30h] [rbp-39h]
  __int64 v11; // [rsp+38h] [rbp-31h]
  _BYTE v12[32]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v13[32]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v14[32]; // [rsp+88h] [rbp+1Fh] BYREF

  pv[0] = a2;
  v10 = L"domiprov.dll";
  v11 = 12;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v14);
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    v10 = (const WCHAR *)v5;
    v11 = v6;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v12);
  }
  else
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(pv);
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)pv[0] + v7) );
    v10 = (const WCHAR *)pv[0];
    v11 = v7;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v13);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    uus::Utility::GetGuestOrNativeArchFolder(v12, v13);
    std::wstring::~wstring(v13);
  }
  std::filesystem::operator/(a2, (struct std::filesystem::path *)v12, (std::filesystem *)v14);
  std::wstring::~wstring(v12);
  std::wstring::~wstring(v14);
  return a2;
}

```

## disassembly

```asm
0x180009d90  mov     [rsp-8+arg_10], rbx
0x180009d95  push    rbp
0x180009d96  push    rsi
0x180009d97  push    rdi
0x180009d98  lea     rbp, [rsp-47h]
0x180009d9d  sub     rsp, 0B0h
0x180009da4  mov     rax, cs:__security_cookie
0x180009dab  xor     rax, rsp
0x180009dae  mov     [rbp+57h+var_18], rax
0x180009db2  mov     rdi, rdx
0x180009db5  mov     rbx, rcx
0x180009db8  mov     [rbp+57h+pv], rdx
0x180009dbc  xor     esi, esi
0x180009dbe  lea     rax, LibFileName; "domiprov.dll"
0x180009dc5  mov     [rbp+57h+var_90], rax
0x180009dc9  mov     [rbp+57h+var_88], 0Ch
0x180009dd1  lea     rdx, [rbp+57h+var_90]
0x180009dd5  lea     rcx, [rbp+57h+var_38]; void *
0x180009dd9  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180009dde  nop
0x180009ddf  mov     rcx, [rbx+8]
0x180009de3  test    rcx, rcx
0x180009de6  jz      short loc_180009E1B
0x180009de8  mov     rax, [rcx]
0x180009deb  lea     edx, [rsi+1]
0x180009dee  mov     rax, [rax+28h]
0x180009df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009dfb  inc     rcx
0x180009dfe  cmp     [rax+rcx*2], si
0x180009e02  jnz     short loc_180009DFB
0x180009e04  mov     [rbp+57h+var_90], rax
0x180009e08  mov     [rbp+57h+var_88], rcx
0x180009e0c  lea     rdx, [rbp+57h+var_90]
0x180009e10  lea     rcx, [rbp+57h+var_78]; void *
0x180009e14  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180009e19  jmp     short loc_180009E74
0x180009e1b  lea     rcx, [rbp+57h+pv]
0x180009e1f  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180009e24  nop
0x180009e25  mov     rax, [rbp+57h+pv]
0x180009e29  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009e2d  inc     rcx
0x180009e30  cmp     [rax+rcx*2], si
0x180009e34  jnz     short loc_180009E2D
0x180009e36  mov     [rbp+57h+var_90], rax
0x180009e3a  mov     [rbp+57h+var_88], rcx
0x180009e3e  lea     rdx, [rbp+57h+var_90]
0x180009e42  lea     rcx, [rbp+57h+var_58]; void *
0x180009e46  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180009e4b  nop
0x180009e4c  mov     rcx, [rbp+57h+pv]; pv
0x180009e50  test    rcx, rcx
0x180009e53  jz      short loc_180009E5C
0x180009e55  call    cs:__imp_CoTaskMemFree
0x180009e5b  nop
0x180009e5c  lea     rdx, [rbp+57h+var_58]
0x180009e60  lea     rcx, [rbp+57h+var_78]
0x180009e64  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180009e69  nop
0x180009e6a  lea     rcx, [rbp+57h+var_58]
0x180009e6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009e73  nop
0x180009e74  lea     r8, [rbp+57h+var_38]; this
0x180009e78  lea     rdx, [rbp+57h+var_78]; struct std::filesystem::path *
0x180009e7c  mov     rcx, rdi; Src
0x180009e7f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180009e84  nop
0x180009e85  lea     rcx, [rbp+57h+var_78]
0x180009e89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009e8e  nop
0x180009e8f  lea     rcx, [rbp+57h+var_38]
0x180009e93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009e98  mov     rax, rdi
0x180009e9b  mov     rcx, [rbp+57h+var_18]
0x180009e9f  xor     rcx, rsp; StackCookie
0x180009ea2  call    __security_check_cookie
0x180009ea7  mov     rbx, [rsp+0C0h+arg_10]
0x180009eaf  add     rsp, 0B0h
0x180009eb6  pop     rdi
0x180009eb7  pop     rsi
0x180009eb8  pop     rbp
0x180009eb9  retn
```
