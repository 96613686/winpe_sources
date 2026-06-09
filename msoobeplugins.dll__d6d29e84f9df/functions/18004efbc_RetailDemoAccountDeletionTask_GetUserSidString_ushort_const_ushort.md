# RetailDemoAccountDeletionTask::GetUserSidString(ushort const *,ushort * *)

- ea: `0x18004efbc`
- end: `0x18004f0ff`
- name: `?GetUserSidString@RetailDemoAccountDeletionTask@@AEAAXPEBGPEAPEAG@Z`
- size: `323`
- prototype: `void(RetailDemoAccountDeletionTask *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004f1bc`

## callees

- `0x180003470`
- `0x18001e968`
- `0x18001e9a4`
- `0x18004e87c`
- `0x18004efbc`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004f08c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004f08c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18004f042`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18004f042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f002`

## string_xrefs

- `0x18004f053`: `shell\oobe\machine\plugins\retaildemo\retaildemotasks.cpp`
- `0x18004f09d`: `shell\oobe\machine\plugins\retaildemo\retaildemotasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RetailDemoAccountDeletionTask::GetUserSidString(
        RetailDemoAccountDeletionTask *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  void *v5; // rbx
  const char *v6; // r9
  const char *v7; // r9
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  void *v13; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 **v14; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  char v16; // [rsp+70h] [rbp-90h]
  WCHAR ReferencedDomainName[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *a3 = 0;
  peUse = 0;
  cbSid = 68;
  v5 = CoTaskMemAlloc(0x44u);
  v13 = v5;
  cchReferencedDomainName = 128;
  if ( !LookupAccountNameW(0, a2, v5, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x20,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemotasks.cpp",
      v6);
  v9 = 0;
  v14 = &v9;
  StringSid = 0;
  v16 = 1;
  if ( !ConvertSidToStringSidW(v5, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x23,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemotasks.cpp",
      v7);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v14);
  v8 = v9;
  v9 = 0;
  *a3 = v8;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v9);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v13);
}

```

## disassembly

```asm
0x18004efbc  mov     [rsp-8+arg_0], rbx
0x18004efc1  push    rbp
0x18004efc2  push    rsi
0x18004efc3  push    rdi
0x18004efc4  lea     rbp, [rsp-90h]
0x18004efcc  sub     rsp, 190h
0x18004efd3  mov     rax, cs:__security_cookie
0x18004efda  xor     rax, rsp
0x18004efdd  mov     [rbp+0A0h+var_20], rax
0x18004efe4  mov     rsi, r8
0x18004efe7  mov     rdi, rdx
0x18004efea  mov     qword ptr [r8], 0
0x18004eff1  mov     [rsp+1A0h+var_158], 0
0x18004eff9  mov     ecx, 44h ; 'D'; cb
0x18004effe  mov     [rsp+1A0h+cbSid], ecx
0x18004f002  call    cs:__imp_CoTaskMemAlloc
0x18004f008  mov     rbx, rax
0x18004f00b  mov     [rsp+1A0h+var_148], rax
0x18004f010  mov     [rsp+1A0h+var_154], 80h
0x18004f018  lea     rax, [rsp+1A0h+var_158]
0x18004f01d  mov     [rsp+1A0h+peUse], rax; peUse
0x18004f022  lea     rax, [rsp+1A0h+var_154]
0x18004f027  mov     [rsp+1A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18004f02c  lea     rax, [rbp+0A0h+var_120]
0x18004f030  mov     [rsp+1A0h+ReferencedDomainName], rax; ReferencedDomainName
0x18004f035  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x18004f03a  mov     r8, rbx; Sid
0x18004f03d  mov     rdx, rdi; lpAccountName
0x18004f040  xor     ecx, ecx; lpSystemName
0x18004f042  call    cs:__imp_LookupAccountNameW
0x18004f048  mov     rcx, [rbp+0A8h]; this
0x18004f04f  test    eax, eax
0x18004f051  jnz     short loc_18004F063
0x18004f053  lea     r8, aShellOobeMachi_40; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004f05a  lea     edx, [rax+20h]; void *
0x18004f05d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004f063  mov     [rsp+1A0h+var_160], 0
0x18004f06c  lea     rax, [rsp+1A0h+var_160]
0x18004f071  mov     [rsp+1A0h+var_140], rax
0x18004f076  mov     [rsp+1A0h+StringSid], 0
0x18004f07f  mov     [rsp+1A0h+var_130], 1
0x18004f084  lea     rdx, [rsp+1A0h+StringSid]; StringSid
0x18004f089  mov     rcx, rbx; Sid
0x18004f08c  call    cs:__imp_ConvertSidToStringSidW
0x18004f092  mov     rcx, [rbp+0A8h]; this
0x18004f099  test    eax, eax
0x18004f09b  jnz     short loc_18004F0AD
0x18004f09d  lea     r8, aShellOobeMachi_40; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004f0a4  lea     edx, [rax+23h]; void *
0x18004f0a7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004f0ad  lea     rcx, [rsp+1A0h+var_140]
0x18004f0b2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18004f0b7  mov     rax, [rsp+1A0h+var_160]
0x18004f0bc  mov     [rsp+1A0h+var_160], 0
0x18004f0c5  mov     [rsi], rax
0x18004f0c8  lea     rcx, [rsp+1A0h+var_160]
0x18004f0cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004f0d2  nop
0x18004f0d3  lea     rcx, [rsp+1A0h+var_148]
0x18004f0d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004f0dd  mov     rcx, [rbp+0A0h+var_20]
0x18004f0e4  xor     rcx, rsp; StackCookie
0x18004f0e7  call    __security_check_cookie
0x18004f0ec  mov     rbx, [rsp+1A0h+arg_0]
0x18004f0f4  add     rsp, 190h
0x18004f0fb  pop     rdi
0x18004f0fc  pop     rsi
0x18004f0fd  pop     rbp
0x18004f0fe  retn
```
