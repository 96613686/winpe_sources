# AppContainerRegistrationHelper::IsRegistryStoragePresent(void *,ushort const *,ushort const *,_GUID const *,int *)

- ea: `0x18000a18c`
- end: `0x18000a2f2`
- name: `?IsRegistryStoragePresent@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEBU_GUID@@PEAH@Z`
- size: `358`
- prototype: `static int(void *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004c80`
- `0x180009a34`

## callees

- `0x180003d30`
- `0x1800044e0`
- `0x18000a18c`
- `0x18000a4d8`
- `0x18000a540`
- `0x18000a740`
- `0x18000f440`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a231`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a231`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a25b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a25b`

## string_xrefs

- `0x18000a1ea`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000a2a5`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000a1de`: `Name %ls Sid %ls`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::IsRegistryStoragePresent(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        int *a5)
{
  int v8; // ebx
  HKEY *phkResult; // rax
  LSTATUS v10; // ebx
  int v11; // eax
  unsigned int v13; // r8d
  HKEY hKey[2]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR SubKey[520]; // [rsp+50h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+0h]

  hKey[0] = 0;
  v8 = AppContainerRegistrationHelper::DeriveTopLevelRegistryKey(a1, a2, a3, SubKey);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3B6,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v8,
      (int)"Name %ls Sid %ls",
      (const char *)a2,
      a3);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return (unsigned int)v8;
  }
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  v10 = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20019u, phkResult);
  if ( v10 )
  {
    if ( v10 != 2 )
    {
      if ( v10 > 0 )
        v13 = (unsigned __int16)v10 | 0x80070000;
      else
        v13 = v10;
      AppContainerRegistrationHelper::LogFailureWithContext(
        &AppModelAppContainerVerifyRegistryKeyFailure,
        SubKey,
        v13,
        a4);
      v8 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x3CB,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
             (const char *)(unsigned int)v10,
             (unsigned int)"Subkey %ls",
             (const char *)SubKey);
      goto LABEL_14;
    }
    v11 = 0;
  }
  else
  {
    v11 = 1;
  }
  *a5 = v11;
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return 0;
}

```

## disassembly

```asm
0x18000a18c  push    rbx
0x18000a18e  push    rbp
0x18000a18f  push    rsi
0x18000a190  push    rdi
0x18000a191  push    r14
0x18000a193  sub     rsp, 470h
0x18000a19a  mov     rax, cs:__security_cookie
0x18000a1a1  xor     rax, rsp
0x18000a1a4  mov     [rsp+498h+var_38], rax
0x18000a1ac  mov     rdi, [rsp+498h+arg_20]
0x18000a1b4  mov     r14, r9
0x18000a1b7  lea     r9, [rsp+498h+SubKey]; unsigned __int16 *
0x18000a1bc  mov     [rsp+498h+hKey], 0
0x18000a1c5  mov     rbp, r8
0x18000a1c8  mov     rsi, rdx
0x18000a1cb  call    ?DeriveTopLevelRegistryKey@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEAG_K@Z; AppContainerRegistrationHelper::DeriveTopLevelRegistryKey(void *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x18000a1d0  mov     ebx, eax
0x18000a1d2  test    eax, eax
0x18000a1d4  jns     short loc_18000A20D
0x18000a1d6  mov     rcx, [rsp+498h]; this
0x18000a1de  lea     rax, aNameLsSidLs; "Name %ls Sid %ls"
0x18000a1e5  mov     [rsp+498h+var_468], rbp
0x18000a1ea  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a1f1  mov     [rsp+498h+var_470], rsi; char *
0x18000a1f6  mov     r9d, ebx; char *
0x18000a1f9  mov     edx, 3B6h; void *
0x18000a1fe  mov     [rsp+498h+phkResult], rax; int
0x18000a203  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a208  jmp     loc_18000A2C7
0x18000a20d  lea     rcx, [rsp+498h+hKey]
0x18000a212  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18000a217  mov     r9d, 20019h; samDesired
0x18000a21d  mov     [rsp+498h+phkResult], rax; phkResult
0x18000a222  xor     r8d, r8d; ulOptions
0x18000a225  lea     rdx, [rsp+498h+SubKey]; lpSubKey
0x18000a22a  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000a231  call    cs:__imp_RegOpenKeyExW
0x18000a238  nop     dword ptr [rax+rax+00h]
0x18000a23d  mov     ebx, eax
0x18000a23f  test    eax, eax
0x18000a241  jnz     short loc_18000A248
0x18000a243  lea     eax, [rbx+1]
0x18000a246  jmp     short loc_18000A24F
0x18000a248  cmp     ebx, 2
0x18000a24b  jnz     short loc_18000A26B
0x18000a24d  xor     eax, eax
0x18000a24f  mov     [rdi], eax
0x18000a251  mov     rcx, [rsp+498h+hKey]; hKey
0x18000a256  test    rcx, rcx
0x18000a259  jz      short loc_18000A267
0x18000a25b  call    cs:__imp_RegCloseKey
0x18000a262  nop     dword ptr [rax+rax+00h]
0x18000a267  xor     eax, eax
0x18000a269  jmp     short loc_18000A2D3
0x18000a26b  test    ebx, ebx
0x18000a26d  jg      short loc_18000A274
0x18000a26f  mov     r8d, ebx
0x18000a272  jmp     short loc_18000A27F
0x18000a274  movzx   r8d, bx
0x18000a278  or      r8d, 80070000h; int
0x18000a27f  mov     r9, r14; struct _GUID *
0x18000a282  lea     rdx, [rsp+498h+SubKey]; unsigned __int16 *
0x18000a287  lea     rcx, AppModelAppContainerVerifyRegistryKeyFailure; struct _EVENT_DESCRIPTOR *
0x18000a28e  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000a293  mov     rcx, [rsp+498h]; this
0x18000a29b  lea     rax, [rsp+498h+SubKey]
0x18000a2a0  mov     [rsp+498h+var_470], rax; char *
0x18000a2a5  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a2ac  lea     rax, aSubkeyLs; "Subkey %ls"
0x18000a2b3  mov     r9d, ebx; char *
0x18000a2b6  mov     edx, 3CBh; void *
0x18000a2bb  mov     [rsp+498h+phkResult], rax; unsigned int
0x18000a2c0  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000a2c5  mov     ebx, eax
0x18000a2c7  lea     rcx, [rsp+498h+hKey]
0x18000a2cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a2d1  mov     eax, ebx
0x18000a2d3  mov     rcx, [rsp+498h+var_38]
0x18000a2db  xor     rcx, rsp; StackCookie
0x18000a2de  call    __security_check_cookie
0x18000a2e3  add     rsp, 470h
0x18000a2ea  pop     r14
0x18000a2ec  pop     rdi
0x18000a2ed  pop     rsi
0x18000a2ee  pop     rbp
0x18000a2ef  pop     rbx
0x18000a2f0  retn
```
