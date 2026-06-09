# DusmSvc::IsClientAdminCheck(void * const &)

- ea: `0x180016b04`
- end: `0x180016b90`
- name: `?IsClientAdminCheck@DusmSvc@@AEAAHAEBQEAX@Z`
- size: `140`
- prototype: `__int64 __fastcall(DusmSvc *this, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001050c`

## callees

- `0x180007c90`
- `0x1800122a4`
- `0x180016944`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016b43`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016b43`

## string_xrefs

- `0x180016b4e`: `DusmSvc::IsClientAdminCheck::CheckTokenMembership`

## pseudocode

```c
__int64 __fastcall DusmSvc::IsClientAdminCheck(DusmSvc *this, void **a2)
{
  DusmSvc *v2; // rbx
  void *v4; // rdx
  void *v5; // rcx
  BOOL v6; // eax
  const char *v8; // [rsp+28h] [rbp-20h]
  WINBOOL IsMember; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = DusmSvc::s_pInstance;
  DusmSvc::CheckAndInitAdminSid(DusmSvc::s_pInstance);
  v4 = (void *)*((_QWORD *)v2 + 5);
  v5 = *a2;
  IsMember = 0;
  v6 = CheckTokenMembership(v5, v4, &IsMember);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x65,
    (unsigned int)"onecoreuap\\net\\dusm\\svc\\dusmsvc.cpp",
    (const char *)v6,
    (bool)"DusmSvc::IsClientAdminCheck::CheckTokenMembership",
    v8);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180016b04  mov     [rsp+arg_0], rbx
0x180016b09  push    rdi
0x180016b0a  sub     rsp, 40h
0x180016b0e  mov     rax, cs:__security_cookie
0x180016b15  xor     rax, rsp
0x180016b18  mov     [rsp+48h+var_10], rax
0x180016b1d  mov     rbx, cs:?s_pInstance@DusmSvc@@0PEAV1@EA; DusmSvc * DusmSvc::s_pInstance
0x180016b24  mov     rdi, rdx
0x180016b27  mov     rcx, rbx; this
0x180016b2a  call    ?CheckAndInitAdminSid@DusmSvc@@AEAAXXZ; DusmSvc::CheckAndInitAdminSid(void)
0x180016b2f  mov     rdx, [rbx+28h]; SidToCheck
0x180016b33  lea     r8, [rsp+48h+IsMember]; IsMember
0x180016b38  mov     rcx, [rdi]; TokenHandle
0x180016b3b  mov     [rsp+48h+IsMember], 0
0x180016b43  call    cs:__imp_CheckTokenMembership
0x180016b49  mov     rcx, [rsp+48h]; this
0x180016b4e  lea     rdx, aDusmsvcIsclien; "DusmSvc::IsClientAdminCheck::CheckToken"...
0x180016b55  test    eax, eax
0x180016b57  mov     qword ptr [rsp+48h+var_28], rdx; bool
0x180016b5c  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dusm\\svc\\dusmsvc.cpp"
0x180016b63  mov     edx, 65h ; 'e'; void *
0x180016b68  setnz   al
0x180016b6b  movzx   r9d, al; char *
0x180016b6f  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180016b74  mov     eax, [rsp+48h+IsMember]
0x180016b78  mov     rcx, [rsp+48h+var_10]
0x180016b7d  xor     rcx, rsp; StackCookie
0x180016b80  call    __security_check_cookie
0x180016b85  mov     rbx, [rsp+48h+arg_0]
0x180016b8a  add     rsp, 40h
0x180016b8e  pop     rdi
0x180016b8f  retn
```
