# uf::details::ClearRolloutRequest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180060c14`
- end: `0x180060ccf`
- name: `?ClearRolloutRequest@details@uf@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063944`

## callees

- `0x18000f59c`
- `0x18002346c`
- `0x180039c50`
- `0x180060c14`
- `0x180062934`
- `0x180064014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060c96`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060c96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060c72`

## string_xrefs

- `0x180060ca8`: `shellcommon\internal\shell\inc\UndockedFlighting\UndockedFlighting.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall uf::details::ClearRolloutRequest(uf::details *lpValueName)
{
  uf::details *v1; // rbx
  char v2; // di
  __int64 v3; // rdx
  HKEY v4; // rcx
  unsigned int v5; // eax
  unsigned int v7[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v1 = lpValueName;
  v2 = 0;
  if ( uf::details::IsImpersonating(lpValueName) )
  {
    v2 = 1;
    v3 = *uf::details::GetHkcuKeyImpersonated(&hKey);
  }
  else
  {
    v3 = -2147483647;
  }
  uf::details::create_shared_key_with_expected_access(
    v7,
    v3,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UndockedFlighting\\RequestedRollouts");
  if ( (v2 & 1) != 0 && hKey )
    RegCloseKey(hKey);
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(uf::details **)v1;
  if ( *(_QWORD *)v7 )
    v4 = **(HKEY **)v7;
  else
    v4 = 0;
  v5 = RegDeleteValueW(v4, (LPCWSTR)v1);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x199,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UndockedFlighting.h",
      (const char *)v5,
      v7[0]);
  return std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v7);
}

```

## disassembly

```asm
0x180060c14  mov     [rsp+arg_10], rbx
0x180060c19  push    rdi
0x180060c1a  sub     rsp, 30h
0x180060c1e  mov     rbx, rcx
0x180060c21  xor     edi, edi
0x180060c23  mov     [rsp+38h+arg_0], edi
0x180060c27  call    ?IsImpersonating@details@uf@@YA_NXZ; uf::details::IsImpersonating(void)
0x180060c2c  test    al, al
0x180060c2e  jz      short loc_180060C49
0x180060c30  lea     rcx, [rsp+38h+hKey]
0x180060c35  call    ?GetHkcuKeyImpersonated@details@uf@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; uf::details::GetHkcuKeyImpersonated(void)
0x180060c3a  nop
0x180060c3b  mov     edi, 1
0x180060c40  mov     [rsp+38h+arg_0], edi
0x180060c44  mov     rdx, [rax]
0x180060c47  jmp     short loc_180060C50
0x180060c49  mov     rdx, 0FFFFFFFF80000001h
0x180060c50  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180060c57  lea     rcx, [rsp+38h+var_18]
0x180060c5c  call    ?create_shared_key_with_expected_access@details@uf@@YA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; uf::details::create_shared_key_with_expected_access(HKEY__ *,ushort const *)
0x180060c61  nop
0x180060c62  test    dil, 1
0x180060c66  jz      short loc_180060C78
0x180060c68  mov     rcx, [rsp+38h+hKey]; hKey
0x180060c6d  test    rcx, rcx
0x180060c70  jz      short loc_180060C78
0x180060c72  call    cs:__imp_RegCloseKey
0x180060c78  cmp     qword ptr [rbx+18h], 7
0x180060c7d  jbe     short loc_180060C82
0x180060c7f  mov     rbx, [rbx]
0x180060c82  mov     rax, qword ptr [rsp+38h+var_18]
0x180060c87  test    rax, rax
0x180060c8a  jz      short loc_180060C91
0x180060c8c  mov     rcx, [rax]
0x180060c8f  jmp     short loc_180060C93
0x180060c91  xor     ecx, ecx; hKey
0x180060c93  mov     rdx, rbx; lpValueName
0x180060c96  call    cs:__imp_RegDeleteValueW
0x180060c9c  mov     rcx, [rsp+38h]; this
0x180060ca1  test    eax, eax
0x180060ca3  jz      short loc_180060CBA
0x180060ca5  mov     r9d, eax; char *
0x180060ca8  lea     r8, aShellcommonInt_4; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180060caf  mov     edx, 199h; void *
0x180060cb4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180060cba  lea     rcx, [rsp+38h+var_18]
0x180060cbf  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180060cc4  mov     rbx, [rsp+38h+arg_10]
0x180060cc9  add     rsp, 30h
0x180060ccd  pop     rdi
0x180060cce  retn
```
