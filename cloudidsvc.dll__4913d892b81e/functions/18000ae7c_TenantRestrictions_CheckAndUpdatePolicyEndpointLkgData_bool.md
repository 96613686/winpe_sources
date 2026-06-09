# TenantRestrictions::CheckAndUpdatePolicyEndpointLkgData(bool)

- ea: `0x18000ae7c`
- end: `0x18000afdb`
- name: `?CheckAndUpdatePolicyEndpointLkgData@TenantRestrictions@@AEAAX_N@Z`
- size: `351`
- prototype: `void __fastcall(RTL_SRWLOCK *this, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b1d0`

## callees

- `0x1800040f4`
- `0x180004740`
- `0x18000a864`
- `0x18000a884`
- `0x18000ae7c`
- `0x18000afe4`
- `0x18000b638`
- `0x18000c43c`
- `0x18000ca74`
- `0x18000ce4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aefb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aefb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aece`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aece`

## string_xrefs

- `0x18000aedf`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`

## pseudocode

```c
void __fastcall TenantRestrictions::CheckAndUpdatePolicyEndpointLkgData(RTL_SRWLOCK *this, char a2)
{
  unsigned int v4; // eax
  unsigned __int64 PolicyValueHash; // rdi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  __int64 v8; // r8
  char updated; // r12
  __int64 v10; // r8
  __int64 v11; // r9
  char v12; // di
  __int64 v13; // r8
  __int64 v14; // r9
  const struct _WNF_STATE_NAME *v15; // rdx
  wil *v16; // rcx
  char v17; // bl
  unsigned int phkResult; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HKEY v20; // [rsp+70h] [rbp+40h] BYREF
  RTL_SRWLOCK *v21; // [rsp+78h] [rbp+48h] BYREF

  v20 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v20,
    0);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\TenantRestrictions\\Payload",
         0,
         0x20119u,
         &v20);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x149,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
      (const char *)v4,
      phkResult);
  AcquireSRWLockExclusive(this + 22);
  v21 = this + 22;
  PolicyValueHash = TenantRestrictions::GetPolicyValueHash(v20, L"hostnames");
  v6 = TenantRestrictions::GetPolicyValueHash(v20, L"subdomainSupportedHostnames");
  v7 = TenantRestrictions::GetPolicyValueHash(v20, L"ipRanges");
  updated = TenantRestrictions::UpdatePolicyLkgHash(&this[15], PolicyValueHash, v8, v7);
  v12 = TenantRestrictions::UpdatePolicyLkgHash(&this[17], v6, v10, v11);
  v17 = TenantRestrictions::UpdatePolicyLkgHash(&this[19], v14, v13, v14);
  if ( this != (RTL_SRWLOCK *)-176LL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v21);
    ReleaseSRWLockExclusive(this + 22);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v21);
  }
  v21 = 0;
  if ( !a2 && (updated || v12 || v17) )
    wil::wnf_publish(v16, v15);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v21);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
}

```

## disassembly

```asm
0x18000ae7c  mov     [rsp-28h+arg_0], rbx
0x18000ae81  mov     [rsp-28h+arg_8], rsi
0x18000ae86  push    rbp
0x18000ae87  push    rdi
0x18000ae88  push    r12
0x18000ae8a  push    r14
0x18000ae8c  push    r15
0x18000ae8e  mov     rbp, rsp
0x18000ae91  sub     rsp, 30h
0x18000ae95  mov     sil, dl
0x18000ae98  mov     r15, rcx
0x18000ae9b  mov     [rbp+arg_10], 0
0x18000aea3  xor     edx, edx
0x18000aea5  lea     rcx, [rbp+arg_10]
0x18000aea9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000aeae  lea     rax, [rbp+arg_10]
0x18000aeb2  mov     qword ptr [rsp+30h+phkResult], rax; unsigned int
0x18000aeb7  mov     r9d, 20119h; samDesired
0x18000aebd  xor     r8d, r8d; ulOptions
0x18000aec0  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000aec7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000aece  call    cs:__imp_RegOpenKeyExW
0x18000aed4  mov     rcx, [rbp+28h]; this
0x18000aed8  test    eax, eax
0x18000aeda  jz      short loc_18000AEF1
0x18000aedc  mov     r9d, eax; char *
0x18000aedf  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000aee6  mov     edx, 149h; void *
0x18000aeeb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000aef1  lea     r14, [r15+0B0h]
0x18000aef8  mov     rcx, r14; SRWLock
0x18000aefb  call    cs:__imp_AcquireSRWLockExclusive
0x18000af01  mov     [rbp+arg_18], r14
0x18000af05  lea     rdx, aHostnames_0; "hostnames"
0x18000af0c  mov     rcx, [rbp+arg_10]; HKEY
0x18000af10  call    ?GetPolicyValueHash@TenantRestrictions@@CA_KPEAUHKEY__@@PEBG@Z; TenantRestrictions::GetPolicyValueHash(HKEY__ *,ushort const *)
0x18000af15  mov     rdi, rax
0x18000af18  lea     rdx, aSubdomainsuppo_0; "subdomainSupportedHostnames"
0x18000af1f  mov     rcx, [rbp+arg_10]; HKEY
0x18000af23  call    ?GetPolicyValueHash@TenantRestrictions@@CA_KPEAUHKEY__@@PEBG@Z; TenantRestrictions::GetPolicyValueHash(HKEY__ *,ushort const *)
0x18000af28  mov     rbx, rax
0x18000af2b  lea     rdx, aIpranges_0; "ipRanges"
0x18000af32  mov     rcx, [rbp+arg_10]; HKEY
0x18000af36  call    ?GetPolicyValueHash@TenantRestrictions@@CA_KPEAUHKEY__@@PEBG@Z; TenantRestrictions::GetPolicyValueHash(HKEY__ *,ushort const *)
0x18000af3b  mov     r9, rax
0x18000af3e  lea     rcx, [r15+78h]
0x18000af42  mov     rdx, rdi
0x18000af45  call    ?UpdatePolicyLkgHash@TenantRestrictions@@CA_NAEAV?$optional@_K@std@@_K@Z; TenantRestrictions::UpdatePolicyLkgHash(std::optional<unsigned __int64> &,unsigned __int64)
0x18000af4a  mov     r12b, al
0x18000af4d  lea     rcx, [r15+88h]
0x18000af54  mov     rdx, rbx
0x18000af57  call    ?UpdatePolicyLkgHash@TenantRestrictions@@CA_NAEAV?$optional@_K@std@@_K@Z; TenantRestrictions::UpdatePolicyLkgHash(std::optional<unsigned __int64> &,unsigned __int64)
0x18000af5c  mov     dil, al
0x18000af5f  lea     rcx, [r15+98h]
0x18000af66  mov     rdx, r9
0x18000af69  call    ?UpdatePolicyLkgHash@TenantRestrictions@@CA_NAEAV?$optional@_K@std@@_K@Z; TenantRestrictions::UpdatePolicyLkgHash(std::optional<unsigned __int64> &,unsigned __int64)
0x18000af6e  mov     bl, al
0x18000af70  test    r14, r14
0x18000af73  jz      short loc_18000AF90
0x18000af75  lea     rcx, [rbp+arg_18]; this
0x18000af79  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000af7e  mov     rcx, r14; SRWLock
0x18000af81  call    cs:__imp_ReleaseSRWLockExclusive
0x18000af87  lea     rcx, [rbp+arg_18]; this
0x18000af8b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000af90  mov     [rbp+arg_18], 0
0x18000af98  test    sil, sil
0x18000af9b  jnz     short loc_18000AFB1
0x18000af9d  test    r12b, r12b
0x18000afa0  jnz     short loc_18000AFAB
0x18000afa2  test    dil, dil
0x18000afa5  jnz     short loc_18000AFAB
0x18000afa7  test    bl, bl
0x18000afa9  jz      short loc_18000AFB1
0x18000afab  call    ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
0x18000afb0  nop
0x18000afb1  lea     rcx, [rbp+arg_18]
0x18000afb5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000afba  nop
0x18000afbb  lea     rcx, [rbp+arg_10]
0x18000afbf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000afc4  mov     rbx, [rsp+30h+arg_0]
0x18000afc9  mov     rsi, [rsp+30h+arg_8]
0x18000afce  add     rsp, 30h
0x18000afd2  pop     r15
0x18000afd4  pop     r14
0x18000afd6  pop     r12
0x18000afd8  pop     rdi
0x18000afd9  pop     rbp
0x18000afda  retn
```
