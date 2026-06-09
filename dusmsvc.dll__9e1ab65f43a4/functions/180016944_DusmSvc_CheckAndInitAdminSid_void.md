# DusmSvc::CheckAndInitAdminSid(void)

- ea: `0x180016944`
- end: `0x180016a0d`
- name: `?CheckAndInitAdminSid@DusmSvc@@AEAAXXZ`
- size: `201`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016b04`

## callees

- `0x180007c90`
- `0x18000f094`
- `0x1800122a4`
- `0x180016944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016963`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016963`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800169b2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800169b2`

## string_xrefs

- `0x1800169c5`: `DusmSvc::CheckAndInitAdminSid::AllocateAndInitializeSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DusmSvc::CheckAndInitAdminSid(struct _RTL_CRITICAL_SECTION *this)
{
  PSID *pSid; // rbx
  BOOL v3; // eax
  const char *nSubAuthority3; // [rsp+28h] [rbp-60h]
  struct _RTL_CRITICAL_SECTION *v5; // [rsp+60h] [rbp-28h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  EnterCriticalSection(this);
  v5 = this;
  pSid = (PSID *)&this[1].DebugInfo;
  if ( !*pSid )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    v3 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, pSid);
    wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecoreuap\\net\\dusm\\svc\\dusmsvc.cpp",
      (const char *)v3,
      (bool)"DusmSvc::CheckAndInitAdminSid::AllocateAndInitializeSid",
      nSubAuthority3);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x180016944  mov     [rsp+arg_8], rbx
0x180016949  push    rdi
0x18001694a  sub     rsp, 80h
0x180016951  mov     rax, cs:__security_cookie
0x180016958  xor     rax, rsp
0x18001695b  mov     [rsp+88h+var_18], rax
0x180016960  mov     rbx, rcx
0x180016963  call    cs:__imp_EnterCriticalSection
0x180016969  mov     [rsp+88h+var_28], rbx
0x18001696e  add     rbx, 28h ; '('
0x180016972  xor     edi, edi
0x180016974  cmp     [rbx], rdi
0x180016977  jnz     short loc_1800169E5
0x180016979  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], edi
0x18001697d  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x180016984  mov     [rsp+88h+pSid], rbx; pSid
0x180016989  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x18001698d  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x180016991  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x180016995  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x180016999  mov     dword ptr [rsp+88h+nSubAuthority3], edi; char *
0x18001699d  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x1800169a1  mov     r9d, 220h; nSubAuthority1
0x1800169a7  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800169ab  mov     dl, 2; nSubAuthorityCount
0x1800169ad  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x1800169b2  call    cs:__imp_AllocateAndInitializeSid
0x1800169b8  test    eax, eax
0x1800169ba  setnz   al
0x1800169bd  mov     rcx, [rsp+88h]; this
0x1800169c5  lea     rdx, aDusmsvcCheckan; "DusmSvc::CheckAndInitAdminSid::Allocate"...
0x1800169cc  mov     qword ptr [rsp+88h+nSubAuthority2], rdx; bool
0x1800169d1  movzx   r9d, al; char *
0x1800169d5  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dusm\\svc\\dusmsvc.cpp"
0x1800169dc  lea     edx, [rdi+73h]; void *
0x1800169df  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x1800169e4  nop
0x1800169e5  lea     rcx, [rsp+88h+var_28]
0x1800169ea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800169ef  mov     rcx, [rsp+88h+var_18]
0x1800169f4  xor     rcx, rsp; StackCookie
0x1800169f7  call    __security_check_cookie
0x1800169fc  mov     rbx, [rsp+88h+arg_8]
0x180016a04  add     rsp, 80h
0x180016a0b  pop     rdi
0x180016a0c  retn
```
