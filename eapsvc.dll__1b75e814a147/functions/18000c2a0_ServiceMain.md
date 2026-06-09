# ServiceMain

- ea: `0x18000c2a0`
- end: `0x18000c394`
- name: `ServiceMain`
- size: `244`
- prototype: `void __fastcall(__int64, const wchar_t **, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180001f60`
- `0x18000aa48`
- `0x18000c2a0`
- `0x18000cd98`
- `0x18000cee8`
- `0x18000d338`
- `0x18000dfb0`
- `0x18000e2bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c35e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c35e`

## string_xrefs

- `0x18000c2d4`: `System\CurrentControlSet\Services\EapHost\Parameters`
- `0x18000c2fa`: `AuthenticatorInstalled`
- `0x18000c386`: `RegOpenKeyExW`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, const wchar_t **a2, __int64 a3, __int64 a4)
{
  bool v5; // bl
  bool v6; // r8
  DWORD v7; // [rsp+20h] [rbp-E8h]
  int v8; // [rsp+30h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-D0h] BYREF
  int v10; // [rsp+40h] [rbp-C8h]
  _QWORD v11[18]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v12; // [rsp+E0h] [rbp-28h]

  try
  {
    hKey = 0;
    v5 = 1;
    v10 = 1;
    if ( (unsigned int)RegistryKey::Create(
                         (__int64)&hKey,
                         (__int64)a2,
                         L"System\\CurrentControlSet\\Services\\EapHost\\Parameters",
                         a4,
                         v7) )
      SystemError::Throw(L"RegOpenKeyExW");
    v8 = 0;
    if ( !(unsigned int)RegistryKey::QueryValue(&hKey, L"AuthenticatorInstalled", &v8) )
      v5 = v8 == 0;
    ServiceManager::ServiceManager((ServiceManager *)v11, *a2, v6, v5);
    v11[0] = &EapHost::EapSvcMgr::`vftable';
    v12 = 0;
    ServiceManager::ExecuteService((ServiceManager *)v11);
    EapHost::EapSvcMgr::~EapSvcMgr((EapHost::EapSvcMgr *)v11);
    if ( hKey )
      RegCloseKey(hKey);
  }
  catch ( Exception )
  {
  }
}

```

## disassembly

```asm
0x18000c2a0  mov     [rsp+arg_0], rbx
0x18000c2a5  push    rdi
0x18000c2a6  sub     rsp, 100h
0x18000c2ad  mov     rax, cs:__security_cookie
0x18000c2b4  xor     rax, rsp
0x18000c2b7  mov     [rsp+108h+var_18], rax
0x18000c2bf  mov     rdi, rdx
0x18000c2c2  mov     [rsp+108h+hKey], 0
0x18000c2cb  mov     ebx, 1
0x18000c2d0  mov     [rsp+108h+var_C8], ebx
0x18000c2d4  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ea"...
0x18000c2db  lea     rcx, [rsp+108h+hKey]
0x18000c2e0  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x18000c2e5  test    eax, eax
0x18000c2e7  jnz     loc_18000C386
0x18000c2ed  mov     [rsp+108h+var_D8], 0
0x18000c2f5  lea     r8, [rsp+108h+var_D8]
0x18000c2fa  lea     rdx, aAuthenticatori; "AuthenticatorInstalled"
0x18000c301  lea     rcx, [rsp+108h+hKey]
0x18000c306  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18000c30b  test    eax, eax
0x18000c30d  jnz     short loc_18000C316
0x18000c30f  cmp     [rsp+108h+var_D8], eax
0x18000c313  cmovnz  ebx, eax
0x18000c316  mov     r9b, bl; bool
0x18000c319  mov     rdx, [rdi]; wchar_t *
0x18000c31c  lea     rcx, [rsp+108h+var_B8]; this
0x18000c321  call    ??0ServiceManager@@QEAA@PEB_W_N1@Z; ServiceManager::ServiceManager(wchar_t const *,bool,bool)
0x18000c326  lea     rax, ??_7EapSvcMgr@EapHost@@6B@; const EapHost::EapSvcMgr::`vftable'
0x18000c32d  mov     [rsp+108h+var_B8], rax
0x18000c332  xorps   xmm0, xmm0
0x18000c335  movdqa  [rsp+108h+var_28], xmm0
0x18000c33e  lea     rcx, [rsp+108h+var_B8]; this
0x18000c343  call    ?ExecuteService@ServiceManager@@QEAAXXZ; ServiceManager::ExecuteService(void)
0x18000c348  nop
0x18000c349  lea     rcx, [rsp+108h+var_B8]; this
0x18000c34e  call    ??1EapSvcMgr@EapHost@@UEAA@XZ; EapHost::EapSvcMgr::~EapSvcMgr(void)
0x18000c353  nop
0x18000c354  mov     rcx, [rsp+108h+hKey]; hKey
0x18000c359  test    rcx, rcx
0x18000c35c  jz      short loc_18000C365
0x18000c35e  call    cs:__imp_RegCloseKey
0x18000c364  nop
0x18000c365  mov     rcx, [rsp+108h+var_18]
0x18000c36d  xor     rcx, rsp; StackCookie
0x18000c370  call    __security_check_cookie
0x18000c375  mov     rbx, [rsp+108h+arg_0]
0x18000c37d  add     rsp, 100h
0x18000c384  pop     rdi
0x18000c385  retn
0x18000c386  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x18000c38d  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
```
