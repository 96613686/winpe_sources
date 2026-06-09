# winrt::ConstrainedLoggedOnUserImpersonator::DuplicateImpersonationToken(void)

- ea: `0x18004f788`
- end: `0x18004f881`
- name: `?DuplicateImpersonationToken@ConstrainedLoggedOnUserImpersonator@winrt@@QEAA?AU?$handle_type@Uhandle_traits@winrt@@@2@XZ`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18004cc5c`
- `0x18004ce04`

## callees

- `0x180003a80`
- `0x180015544`
- `0x180015694`
- `0x1800194fc`
- `0x18004f788`
- `0x18005175c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f81f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f82b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f81f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f82b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004f855`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004f855`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18004f7ed`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18004f7ed`

## string_xrefs

- `0x18004f7ff`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedLoggedOnUserImpersonator.h`
- `0x18004f864`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedLoggedOnUserImpersonator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HANDLE *__fastcall winrt::ConstrainedLoggedOnUserImpersonator::DuplicateImpersonationToken(__int64 a1, HANDLE *a2)
{
  void **v4; // rdi
  int ConstrainedUserToken; // eax
  HANDLE CurrentProcess; // rbx
  void *v7; // rdi
  HANDLE v8; // rax
  const char *v9; // r9
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a2 = 0;
  v4 = (void **)(a1 + 8);
  if ( !*(_QWORD *)(a1 + 16) )
    goto LABEL_6;
  if ( !*v4 )
  {
    if ( (unsigned __int8)IsUMgrGetConstrainedUserTokenPresent() )
    {
      *(_QWORD *)(a1 + 24) = winrt::Windows::System::Internal::UserManager::GetHandleForUser((const struct winrt::Windows::System::User *)(a1 + 16));
      winrt::handle_type<winrt::handle_traits>::close(v4);
      ConstrainedUserToken = UMgrGetConstrainedUserToken(0, *(_QWORD *)(a1 + 24), 0, v4);
      if ( ConstrainedUserToken < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x77,
          (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedLoggedOnUserImpersonator.h",
          (const char *)(unsigned int)ConstrainedUserToken,
          dwDesiredAccess);
    }
LABEL_6:
    if ( !*v4 )
      return a2;
  }
  winrt::handle_type<winrt::handle_traits>::close(a2);
  CurrentProcess = GetCurrentProcess();
  v7 = *v4;
  v8 = GetCurrentProcess();
  if ( !DuplicateHandle(v8, v7, CurrentProcess, a2, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x54,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedLoggedOnUserImpersonator.h",
      v9);
  return a2;
}

```

## disassembly

```asm
0x18004f788  mov     [rsp+arg_8], rdx
0x18004f78d  push    rbx
0x18004f78e  push    rbp
0x18004f78f  push    rsi
0x18004f790  push    rdi
0x18004f791  sub     rsp, 58h
0x18004f795  mov     rsi, rdx
0x18004f798  mov     rbx, rcx
0x18004f79b  mov     [rsp+78h+var_38], 0
0x18004f7a3  mov     qword ptr [rdx], 0
0x18004f7aa  mov     [rsp+78h+var_38], 1
0x18004f7b2  lea     rdi, [rcx+8]
0x18004f7b6  cmp     qword ptr [rcx+10h], 0
0x18004f7bb  jz      short loc_18004F811
0x18004f7bd  cmp     qword ptr [rdi], 0
0x18004f7c1  jnz     short loc_18004F817
0x18004f7c3  call    IsUMgrGetConstrainedUserTokenPresent
0x18004f7c8  test    al, al
0x18004f7ca  jz      short loc_18004F811
0x18004f7cc  lea     rcx, [rbx+10h]; struct winrt::Windows::System::User *
0x18004f7d0  call    ?GetHandleForUser@UserManager@Internal@System@Windows@winrt@@SA@AEBUUser@345@@Z; winrt::Windows::System::Internal::UserManager::GetHandleForUser(winrt::Windows::System::User const &)
0x18004f7d5  mov     [rbx+18h], rax
0x18004f7d9  mov     rcx, rdi
0x18004f7dc  call    ?close@?$handle_type@Uhandle_traits@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::handle_traits>::close(void)
0x18004f7e1  mov     r9, rdi
0x18004f7e4  xor     r8d, r8d
0x18004f7e7  mov     rdx, [rbx+18h]
0x18004f7eb  xor     ecx, ecx
0x18004f7ed  call    cs:__imp_UMgrGetConstrainedUserToken
0x18004f7f3  test    eax, eax
0x18004f7f5  jns     short loc_18004F811
0x18004f7f7  mov     rcx, [rsp+78h]; this
0x18004f7fc  mov     r9d, eax; char *
0x18004f7ff  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18004f806  mov     edx, 77h ; 'w'; void *
0x18004f80b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f811  cmp     qword ptr [rdi], 0
0x18004f815  jz      short loc_18004F874
0x18004f817  mov     rcx, rsi
0x18004f81a  call    ?close@?$handle_type@Uhandle_traits@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::handle_traits>::close(void)
0x18004f81f  call    cs:__imp_GetCurrentProcess
0x18004f825  mov     rbx, rax
0x18004f828  mov     rdi, [rdi]
0x18004f82b  call    cs:__imp_GetCurrentProcess
0x18004f831  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18004f839  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18004f841  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18004f849  mov     r9, rsi; lpTargetHandle
0x18004f84c  mov     r8, rbx; hTargetProcessHandle
0x18004f84f  mov     rdx, rdi; hSourceHandle
0x18004f852  mov     rcx, rax; hSourceProcessHandle
0x18004f855  call    cs:__imp_DuplicateHandle
0x18004f85b  test    eax, eax
0x18004f85d  jnz     short loc_18004F874
0x18004f85f  mov     rcx, [rsp+78h]; this
0x18004f864  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18004f86b  lea     edx, [rax+54h]; void *
0x18004f86e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004f874  mov     rax, rsi
0x18004f877  add     rsp, 58h
0x18004f87b  pop     rdi
0x18004f87c  pop     rsi
0x18004f87d  pop     rbp
0x18004f87e  pop     rbx
0x18004f87f  retn
```
