# Acl::SetACL(_ACL const *)

- ea: `0x1401c818c`
- end: `0x1401c841e`
- name: `?SetACL@Acl@@QEAAPEAVFrsStatus@@PEBU_ACL@@@Z`
- size: `658`
- prototype: `struct FrsStatus *(Acl *__hidden this, const struct _ACL *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1401c7068`

## callees

- `0x1400036a0`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c818c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c820d`
- `KERNEL32!GetLastError` at `0x1401c8283`
- `KERNEL32!GetLastError` at `0x1401c830e`
- `KERNEL32!GetLastError` at `0x1401c8393`
- `KERNEL32!GetLastError` at `0x1401c83c0`
- `KERNEL32!GetLastError` at `0x1401c820d`
- `KERNEL32!GetLastError` at `0x1401c8283`
- `KERNEL32!GetLastError` at `0x1401c830e`
- `KERNEL32!GetLastError` at `0x1401c8393`
- `KERNEL32!GetLastError` at `0x1401c83c0`
- `KERNEL32!GetCurrentThreadId` at `0x1401c81ff`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8275`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8300`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8385`
- `KERNEL32!GetCurrentThreadId` at `0x1401c83b2`
- `KERNEL32!GetCurrentThreadId` at `0x1401c81ff`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8275`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8300`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8385`
- `KERNEL32!GetCurrentThreadId` at `0x1401c83b2`
- `ADVAPI32!AddAce` at `0x1401c8371`
- `ADVAPI32!AddAce` at `0x1401c8371`
- `ADVAPI32!InitializeAcl` at `0x1401c82f0`
- `ADVAPI32!InitializeAcl` at `0x1401c82f0`
- `ADVAPI32!GetAclInformation` at `0x1401c81ef`
- `ADVAPI32!GetAclInformation` at `0x1401c8265`
- `ADVAPI32!GetAclInformation` at `0x1401c81ef`
- `ADVAPI32!GetAclInformation` at `0x1401c8265`
- `ADVAPI32!GetAce` at `0x1401c8349`
- `ADVAPI32!GetAce` at `0x1401c8349`

## string_xrefs

- `0x1401c823f`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c83ef`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c822e`: `Acl::SetACL`
- `0x1401c83dd`: `Acl::SetACL`

## pseudocode

```c
struct FrsStatus *__fastcall Acl::SetACL(Acl *this, struct _ACL *a2)
{
  void *v3; // rcx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  struct FrsStatus *result; // rax
  DWORD v8; // ebx
  DWORD v9; // eax
  struct _ACL *v10; // rax
  DWORD v11; // r8d
  DWORD v12; // edx
  DWORD v13; // ebx
  DWORD v14; // eax
  __int64 v15; // rax
  DWORD i; // ebx
  DWORD v17; // ebx
  DWORD v18; // eax
  DWORD v19; // ebx
  DWORD v20; // eax
  void *v21; // rcx
  struct FrsStatus *v22; // rbx
  int v23; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+68h] [rbp-18h]

  *((_DWORD *)this + 4) = 0;
  v3 = (void *)*((_QWORD *)this + 3);
  pAclInformation = 0;
  v26 = 0;
  v23 = 0;
  operator delete[](v3);
  *((_QWORD *)this + 3) = 0;
  if ( !a2 )
    return 0;
  if ( !GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 LastError,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Acl::SetACL",
                                 1586,
                                 CurrentThreadId,
                                 0);
  }
  if ( !GetAclInformation(a2, &v23, 4u, AclRevisionInformation) )
  {
    v8 = GetCurrentThreadId();
    v9 = GetLastError();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 v9,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Acl::SetACL",
                                 1590,
                                 v8,
                                 0);
  }
  *((_DWORD *)this + 2) = v23;
  if ( !(_DWORD)pAclInformation )
  {
    *((_DWORD *)this + 4) = 1;
    return 0;
  }
  v10 = (struct _ACL *)operator_new(HIDWORD(pAclInformation));
  v11 = *((_DWORD *)this + 2);
  v12 = HIDWORD(pAclInformation);
  *((_QWORD *)this + 3) = v10;
  if ( InitializeAcl(v10, v12, v11) )
  {
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      pAce = 0;
      if ( !GetAce(a2, i, &pAce) )
      {
        v19 = GetCurrentThreadId();
        v20 = GetLastError();
        v15 = FrsStatusList::PushNewError(
                "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                v20,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                "Acl::SetACL",
                1610,
                v19,
                0);
        goto LABEL_19;
      }
      if ( !AddAce(*((PACL *)this + 3), *((_DWORD *)this + 2), 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
      {
        v17 = GetCurrentThreadId();
        v18 = GetLastError();
        v15 = FrsStatusList::PushNewError(
                "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                v18,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                "Acl::SetACL",
                1623,
                v17,
                0);
        goto LABEL_19;
      }
    }
    return 0;
  }
  v13 = GetCurrentThreadId();
  v14 = GetLastError();
  v15 = FrsStatusList::PushNewError(
          "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
          v14,
          0,
          1,
          "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
          "Acl::SetACL",
          1601,
          v13,
          0);
LABEL_19:
  v21 = (void *)*((_QWORD *)this + 3);
  v22 = (struct FrsStatus *)v15;
  *((_DWORD *)this + 4) = 0;
  operator delete[](v21);
  result = v22;
  *((_QWORD *)this + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x1401c818c  mov     [rsp-28h+arg_10], rbx
0x1401c8191  push    rbp
0x1401c8192  push    rsi
0x1401c8193  push    rdi
0x1401c8194  push    r14
0x1401c8196  push    r15
0x1401c8198  mov     rbp, rsp
0x1401c819b  sub     rsp, 80h
0x1401c81a2  mov     rax, cs:__security_cookie
0x1401c81a9  xor     rax, rsp
0x1401c81ac  mov     [rbp+var_10], rax
0x1401c81b0  xor     eax, eax
0x1401c81b2  xor     r15d, r15d
0x1401c81b5  mov     [rcx+10h], r15d
0x1401c81b9  mov     rdi, rcx
0x1401c81bc  mov     rcx, [rcx+18h]; Block
0x1401c81c0  mov     r14, rdx
0x1401c81c3  mov     [rbp+pAclInformation], rax
0x1401c81c7  mov     [rbp+var_18], eax
0x1401c81ca  mov     [rbp+var_30], r15d
0x1401c81ce  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c81d3  mov     [rdi+18h], r15
0x1401c81d7  test    r14, r14
0x1401c81da  jz      loc_1401C82B4
0x1401c81e0  lea     r9d, [r15+2]; dwAclInformationClass
0x1401c81e4  mov     rcx, r14; pAcl
0x1401c81e7  lea     r8d, [r15+0Ch]; nAclInformationLength
0x1401c81eb  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x1401c81ef  call    cs:__imp_GetAclInformation
0x1401c81f6  nop     dword ptr [rax+rax+00h]
0x1401c81fb  test    eax, eax
0x1401c81fd  jnz     short loc_1401C8252
0x1401c81ff  call    cs:__imp_GetCurrentThreadId
0x1401c8206  nop     dword ptr [rax+rax+00h]
0x1401c820b  mov     ebx, eax
0x1401c820d  call    cs:__imp_GetLastError
0x1401c8214  nop     dword ptr [rax+rax+00h]
0x1401c8219  mov     [rsp+80h+var_40], r15
0x1401c821e  lea     r9d, [r15+1]
0x1401c8222  mov     [rsp+80h+var_48], ebx
0x1401c8226  mov     [rsp+80h+var_50], 632h
0x1401c822e  lea     rcx, aAclSetacl; "Acl::SetACL"
0x1401c8235  xor     r8d, r8d
0x1401c8238  mov     [rsp+80h+var_58], rcx
0x1401c823d  mov     edx, eax
0x1401c823f  lea     rcx, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c8246  mov     qword ptr [rsp+80h+nAceListLength], rcx
0x1401c824b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c8250  jmp     short loc_1401C82B6
0x1401c8252  mov     esi, 1
0x1401c8257  lea     rdx, [rbp+var_30]; pAclInformation
0x1401c825b  mov     r9d, esi; dwAclInformationClass
0x1401c825e  mov     rcx, r14; pAcl
0x1401c8261  lea     r8d, [rsi+3]; nAclInformationLength
0x1401c8265  call    cs:__imp_GetAclInformation
0x1401c826c  nop     dword ptr [rax+rax+00h]
0x1401c8271  test    eax, eax
0x1401c8273  jnz     short loc_1401C82A5
0x1401c8275  call    cs:__imp_GetCurrentThreadId
0x1401c827c  nop     dword ptr [rax+rax+00h]
0x1401c8281  mov     ebx, eax
0x1401c8283  call    cs:__imp_GetLastError
0x1401c828a  nop     dword ptr [rax+rax+00h]
0x1401c828f  mov     [rsp+80h+var_40], r15
0x1401c8294  mov     r9d, esi
0x1401c8297  mov     [rsp+80h+var_48], ebx
0x1401c829b  mov     [rsp+80h+var_50], 636h
0x1401c82a3  jmp     short loc_1401C822E
0x1401c82a5  mov     eax, [rbp+var_30]
0x1401c82a8  mov     [rdi+8], eax
0x1401c82ab  cmp     dword ptr [rbp+pAclInformation], r15d
0x1401c82af  jnz     short loc_1401C82DA
0x1401c82b1  mov     [rdi+10h], esi
0x1401c82b4  xor     eax, eax
0x1401c82b6  mov     rcx, [rbp+var_10]
0x1401c82ba  xor     rcx, rsp; StackCookie
0x1401c82bd  call    __security_check_cookie
0x1401c82c2  mov     rbx, [rsp+80h+arg_10]
0x1401c82ca  add     rsp, 80h
0x1401c82d1  pop     r15
0x1401c82d3  pop     r14
0x1401c82d5  pop     rdi
0x1401c82d6  pop     rsi
0x1401c82d7  pop     rbp
0x1401c82d8  retn
0x1401c82da  mov     ecx, dword ptr [rbp+pAclInformation+4]; unsigned __int64
0x1401c82dd  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401c82e2  mov     r8d, [rdi+8]; dwAclRevision
0x1401c82e6  mov     rcx, rax; pAcl
0x1401c82e9  mov     edx, dword ptr [rbp+pAclInformation+4]; nAclLength
0x1401c82ec  mov     [rdi+18h], rax
0x1401c82f0  call    cs:__imp_InitializeAcl
0x1401c82f7  nop     dword ptr [rax+rax+00h]
0x1401c82fc  test    eax, eax
0x1401c82fe  jnz     short loc_1401C8330
0x1401c8300  call    cs:__imp_GetCurrentThreadId
0x1401c8307  nop     dword ptr [rax+rax+00h]
0x1401c830c  mov     ebx, eax
0x1401c830e  call    cs:__imp_GetLastError
0x1401c8315  nop     dword ptr [rax+rax+00h]
0x1401c831a  mov     [rsp+80h+var_40], r15
0x1401c831f  mov     [rsp+80h+var_48], ebx
0x1401c8323  mov     [rsp+80h+var_50], 641h
0x1401c832b  jmp     loc_1401C83DD
0x1401c8330  mov     ebx, r15d
0x1401c8333  cmp     ebx, dword ptr [rbp+pAclInformation]
0x1401c8336  jnb     loc_1401C82B4
0x1401c833c  lea     r8, [rbp+pAce]; pAce
0x1401c8340  mov     [rbp+pAce], r15
0x1401c8344  mov     edx, ebx; dwAceIndex
0x1401c8346  mov     rcx, r14; pAcl
0x1401c8349  call    cs:__imp_GetAce
0x1401c8350  nop     dword ptr [rax+rax+00h]
0x1401c8355  test    eax, eax
0x1401c8357  jz      short loc_1401C83B2
0x1401c8359  mov     r9, [rbp+pAce]; pAceList
0x1401c835d  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1401c8361  mov     edx, [rdi+8]; dwAceRevision
0x1401c8364  mov     rcx, [rdi+18h]; pAcl
0x1401c8368  movzx   eax, word ptr [r9+2]
0x1401c836d  mov     [rsp+80h+nAceListLength], eax; nAceListLength
0x1401c8371  call    cs:__imp_AddAce
0x1401c8378  nop     dword ptr [rax+rax+00h]
0x1401c837d  test    eax, eax
0x1401c837f  jz      short loc_1401C8385
0x1401c8381  add     ebx, esi
0x1401c8383  jmp     short loc_1401C8333
0x1401c8385  call    cs:__imp_GetCurrentThreadId
0x1401c838c  nop     dword ptr [rax+rax+00h]
0x1401c8391  mov     ebx, eax
0x1401c8393  call    cs:__imp_GetLastError
0x1401c839a  nop     dword ptr [rax+rax+00h]
0x1401c839f  mov     [rsp+80h+var_40], r15
0x1401c83a4  mov     [rsp+80h+var_48], ebx
0x1401c83a8  mov     [rsp+80h+var_50], 657h
0x1401c83b0  jmp     short loc_1401C83DD
0x1401c83b2  call    cs:__imp_GetCurrentThreadId
0x1401c83b9  nop     dword ptr [rax+rax+00h]
0x1401c83be  mov     ebx, eax
0x1401c83c0  call    cs:__imp_GetLastError
0x1401c83c7  nop     dword ptr [rax+rax+00h]
0x1401c83cc  mov     [rsp+80h+var_40], r15
0x1401c83d1  mov     [rsp+80h+var_48], ebx
0x1401c83d5  mov     [rsp+80h+var_50], 64Ah
0x1401c83dd  lea     rcx, aAclSetacl; "Acl::SetACL"
0x1401c83e4  mov     r9d, esi
0x1401c83e7  mov     [rsp+80h+var_58], rcx
0x1401c83ec  xor     r8d, r8d
0x1401c83ef  lea     rcx, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c83f6  mov     edx, eax
0x1401c83f8  mov     qword ptr [rsp+80h+nAceListLength], rcx
0x1401c83fd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c8402  mov     rcx, [rdi+18h]; Block
0x1401c8406  mov     rbx, rax
0x1401c8409  mov     [rdi+10h], r15d
0x1401c840d  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c8412  mov     rax, rbx
0x1401c8415  mov     [rdi+18h], r15
0x1401c8419  jmp     loc_1401C82B6
```
