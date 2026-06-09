# SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)

- ea: `0x1800ab770`
- end: `0x1800ab92e`
- name: `?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z`
- size: `446`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180068ab0`
- `0x1800ab154`
- `0x1800abe78`
- `0x1800ac1cc`
- `0x1800f5e08`
- `0x180122c78`
- `0x180149770`
- `0x180207b68`
- `0x180207d48`
- `0x180207f2c`

## callees

- `0x1800ab770`
- `0x1800b965c`
- `0x1801244c0`
- `0x1801249b0`
- `0x180124d00`
- `0x18013dd98`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab8cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab8cb`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800ab80f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800ab80f`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x1800ab7ad`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800ab7bc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ab7f0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ab7f0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800ab8b1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800ab8b1`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800ab7e0`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800ab7e0`

## string_xrefs

- `0x1800ab82a`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1800ab8dc`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SecUtil::CACL::AddAccessXXXAces(PACL *a1, int a2, __int64 a3, PSID *a4, __int64 a5, _BYTE *a6)
{
  int v8; // r14d
  BOOL (__stdcall *v9)(PACL, DWORD, DWORD, PSID); // r12
  int v10; // ebx
  DWORD v11; // ebx
  struct _ACL *v12; // rsi
  struct _ACL *v13; // r8
  DWORD LastError; // eax
  __int64 i; // rbx
  __int64 v16; // r8
  DWORD v17; // eax
  unsigned int v18; // [rsp+20h] [rbp-78h]
  LPVOID pAce; // [rsp+30h] [rbp-68h] BYREF
  PSID *v20; // [rsp+38h] [rbp-60h]
  struct _ACL *v21; // [rsp+40h] [rbp-58h]
  __int64 pAclInformation; // [rsp+48h] [rbp-50h] BYREF
  int v23; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v20 = a4;
  if ( a2 )
  {
    v8 = 1;
    v9 = AddAccessAllowedAce;
  }
  else
  {
    v8 = 0;
    v9 = AddAccessDeniedAce;
  }
  pAclInformation = 0;
  v23 = 0;
  GetAclInformation(*a1, &pAclInformation, 0xCu, AclSizeInformation);
  v10 = HIDWORD(pAclInformation) + 8;
  v11 = GetLengthSid(*a4) + v10;
  v12 = (struct _ACL *)operator new[](v11);
  v21 = v12;
  if ( !InitializeAcl(v12, v11, 2u) )
  {
    LastError = GetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x366,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      (const char *)LastError,
      v18);
  }
  if ( v8 )
    SecUtil::AppendACL(v12, *a1, v13);
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    if ( a5 )
      v16 = *(unsigned int *)(a5 + 4 * i);
    else
      v16 = 270467072;
    if ( !((unsigned int (__fastcall *)(struct _ACL *, __int64, __int64, PSID))v9)(v12, 2, v16, *v20) )
    {
      v17 = GetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x382,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
        (const char *)v17,
        v18);
    }
    if ( a6 && *a6 )
    {
      pAce = 0;
      if ( GetAce(v12, pAclInformation, &pAce) )
        *((_BYTE *)pAce + 1) = *a6;
    }
  }
  if ( !v8 )
    SecUtil::AppendACL(v12, *a1, v13);
  operator delete(*a1);
  *a1 = v12;
}

```

## disassembly

```asm
0x1800ab770  mov     [rsp+arg_8], rbx
0x1800ab775  push    rbp
0x1800ab776  push    rsi
0x1800ab777  push    rdi
0x1800ab778  push    r12
0x1800ab77a  push    r13
0x1800ab77c  push    r14
0x1800ab77e  push    r15
0x1800ab780  sub     rsp, 60h
0x1800ab784  mov     rax, cs:__security_cookie
0x1800ab78b  xor     rax, rsp
0x1800ab78e  mov     [rsp+98h+var_40], rax
0x1800ab793  mov     rsi, r9
0x1800ab796  mov     [rsp+98h+var_60], r9
0x1800ab79b  mov     rdi, rcx
0x1800ab79e  mov     r13, [rsp+98h+arg_20]
0x1800ab7a6  test    edx, edx
0x1800ab7a8  jnz     short loc_1800AB7B6
0x1800ab7aa  xor     r14d, r14d
0x1800ab7ad  mov     r12, cs:__imp_AddAccessDeniedAce
0x1800ab7b4  jmp     short loc_1800AB7C3
0x1800ab7b6  mov     r14d, 1
0x1800ab7bc  mov     r12, cs:__imp_AddAccessAllowedAce
0x1800ab7c3  xor     eax, eax
0x1800ab7c5  mov     [rsp+98h+pAclInformation], rax
0x1800ab7ca  mov     [rsp+98h+var_48], eax
0x1800ab7ce  lea     ebp, [rax+2]
0x1800ab7d1  mov     r9d, ebp; dwAclInformationClass
0x1800ab7d4  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1800ab7d8  lea     rdx, [rsp+98h+pAclInformation]; pAclInformation
0x1800ab7dd  mov     rcx, [rcx]; pAcl
0x1800ab7e0  call    cs:__imp_GetAclInformation
0x1800ab7e6  mov     ebx, dword ptr [rsp+98h+pAclInformation+4]
0x1800ab7ea  add     ebx, 8
0x1800ab7ed  mov     rcx, [rsi]; pSid
0x1800ab7f0  call    cs:__imp_GetLengthSid
0x1800ab7f6  add     ebx, eax
0x1800ab7f8  mov     ecx, ebx; unsigned __int64
0x1800ab7fa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ab7ff  mov     rsi, rax
0x1800ab802  mov     [rsp+98h+var_58], rax
0x1800ab807  mov     r8d, ebp; dwAclRevision
0x1800ab80a  mov     edx, ebx; nAclLength
0x1800ab80c  mov     rcx, rax; pAcl
0x1800ab80f  call    cs:__imp_InitializeAcl
0x1800ab815  test    eax, eax
0x1800ab817  jnz     short loc_1800AB83C
0x1800ab819  call    cs:__imp_GetLastError
0x1800ab81f  mov     r9d, eax; char *
0x1800ab822  mov     rcx, [rsp+98h]; this
0x1800ab82a  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800ab831  mov     edx, 366h; void *
0x1800ab836  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ab83c  mov     r15, [rsp+98h+arg_28]
0x1800ab844  test    r14d, r14d
0x1800ab847  jz      short loc_1800AB854
0x1800ab849  mov     rdx, [rdi]; PACL
0x1800ab84c  mov     rcx, rsi; pAcl
0x1800ab84f  call    ?AppendACL@SecUtil@@YAXPEAU_ACL@@0@Z; SecUtil::AppendACL(_ACL *,_ACL *)
0x1800ab854  xor     ebx, ebx
0x1800ab856  cmp     ebx, 1
0x1800ab859  jnb     loc_1800AB8EE
0x1800ab85f  mov     ebp, ebx
0x1800ab861  test    r13, r13
0x1800ab864  jz      short loc_1800AB86D
0x1800ab866  mov     r8d, [r13+rbx*4+0]
0x1800ab86b  jmp     short loc_1800AB873
0x1800ab86d  mov     r8d, 101F0000h
0x1800ab873  mov     rax, [rsp+98h+var_60]
0x1800ab878  mov     r9, [rax+rbp*8]
0x1800ab87c  mov     edx, 2
0x1800ab881  mov     rcx, rsi
0x1800ab884  mov     rax, r12
0x1800ab887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab88c  test    eax, eax
0x1800ab88e  jz      short loc_1800AB8CB
0x1800ab890  test    r15, r15
0x1800ab893  jz      short loc_1800AB8C7
0x1800ab895  cmp     byte ptr [r15+rbp], 0
0x1800ab89a  jz      short loc_1800AB8C7
0x1800ab89c  mov     [rsp+98h+pAce], 0
0x1800ab8a5  lea     r8, [rsp+98h+pAce]; pAce
0x1800ab8aa  mov     edx, dword ptr [rsp+98h+pAclInformation]; dwAceIndex
0x1800ab8ae  mov     rcx, rsi; pAcl
0x1800ab8b1  call    cs:__imp_GetAce
0x1800ab8b7  test    eax, eax
0x1800ab8b9  jz      short loc_1800AB8C7
0x1800ab8bb  mov     cl, [r15+rbp]
0x1800ab8bf  mov     rax, [rsp+98h+pAce]
0x1800ab8c4  mov     [rax+1], cl
0x1800ab8c7  inc     ebx
0x1800ab8c9  jmp     short loc_1800AB856
0x1800ab8cb  call    cs:__imp_GetLastError
0x1800ab8d1  mov     r9d, eax; char *
0x1800ab8d4  mov     rcx, [rsp+98h]; this
0x1800ab8dc  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800ab8e3  mov     edx, 382h; void *
0x1800ab8e8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ab8ee  test    r14d, r14d
0x1800ab8f1  jnz     short loc_1800AB8FE
0x1800ab8f3  mov     rdx, [rdi]; PACL
0x1800ab8f6  mov     rcx, rsi; pAcl
0x1800ab8f9  call    ?AppendACL@SecUtil@@YAXPEAU_ACL@@0@Z; SecUtil::AppendACL(_ACL *,_ACL *)
0x1800ab8fe  mov     rcx, [rdi]; Block
0x1800ab901  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab906  mov     [rdi], rsi
0x1800ab909  mov     rcx, [rsp+98h+var_40]
0x1800ab90e  xor     rcx, rsp; StackCookie
0x1800ab911  call    __security_check_cookie
0x1800ab916  mov     rbx, [rsp+98h+arg_8]
0x1800ab91e  add     rsp, 60h
0x1800ab922  pop     r15
0x1800ab924  pop     r14
0x1800ab926  pop     r13
0x1800ab928  pop     r12
0x1800ab92a  pop     rdi
0x1800ab92b  pop     rsi
0x1800ab92c  pop     rbp
0x1800ab92d  retn
```
