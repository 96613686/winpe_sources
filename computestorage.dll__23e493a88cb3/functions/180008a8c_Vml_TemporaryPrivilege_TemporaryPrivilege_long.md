# Vml::TemporaryPrivilege::TemporaryPrivilege(long)

- ea: `0x180008a8c`
- end: `0x180008bf5`
- name: `??0TemporaryPrivilege@Vml@@QEAA@J@Z`
- size: `361`
- prototype: `Vml::TemporaryPrivilege *__fastcall(Vml::TemporaryPrivilege *this, int)`
- caller_count: `10`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ad8`
- `0x1800146e0`
- `0x180014a00`
- `0x180015050`
- `0x18001a5f4`
- `0x18001c5d4`
- `0x18001db70`
- `0x18001ea88`
- `0x180027e8c`
- `0x180028640`

## callees

- `0x1800084a4`
- `0x180008a8c`
- `0x18000ab54`
- `0x18000ad80`
- `0x180012818`
- `0x1800136f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b56`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008ae4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008b46`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008ae4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008b46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008b2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008b2d`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180008b14`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180008b14`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008b64`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008b64`

## string_xrefs

- `0x180008b7c`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180008bd1`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180008be3`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
Vml::TemporaryPrivilege *__fastcall Vml::TemporaryPrivilege::TemporaryPrivilege(Vml::TemporaryPrivilege *this, int a2)
{
  void **v3; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v6; // r9
  HANDLE v7; // rax
  DWORD v8; // ebx
  unsigned int v9; // eax
  const char *v10; // r9
  unsigned int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = (void **)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_BYTE *)this + 20) = 0;
  *(_QWORD *)this = a2;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, v3) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1DD7,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        (const char *)LastError,
        v12);
    if ( !ImpersonateSelf(SecurityImpersonation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1DDA,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v6);
    v7 = GetCurrentThread();
    if ( !OpenThreadToken(v7, 0x28u, 0, v3) )
    {
      v8 = GetLastError();
      v9 = RevertToSelf();
      if ( (unsigned __int8)wil::verify_bool<int,0>(v9) )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1DDF,
          (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
          (const char *)v8,
          v12);
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1DDE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v10);
    }
    *((_BYTE *)this + 20) = 1;
  }
  *((_DWORD *)this + 4) = Vml::VmAccessToken::EnablePrivilege((Vml::VmAccessToken *)v3, (const struct _LUID *)this, 1);
  return this;
}

```

## disassembly

```asm
0x180008a8c  mov     [rsp+arg_8], rbx
0x180008a91  mov     [rsp+arg_0], rcx
0x180008a96  push    rdi; unsigned int
0x180008a97  sub     rsp, 20h
0x180008a9b  mov     rbx, rcx
0x180008a9e  lea     rdi, [rcx+8]
0x180008aa2  mov     qword ptr [rdi], 0
0x180008aa9  mov     dword ptr [rcx+10h], 0
0x180008ab0  mov     byte ptr [rcx+14h], 0
0x180008ab4  movsxd  rax, edx
0x180008ab7  mov     dword ptr [rsp+28h+arg_10], eax
0x180008abb  shr     rax, 20h
0x180008abf  mov     dword ptr [rsp+28h+arg_10+4], eax
0x180008ac3  mov     rax, [rsp+28h+arg_10]
0x180008ac8  mov     [rcx], rax
0x180008acb  call    cs:__imp_GetCurrentThread
0x180008ad2  nop     dword ptr [rax+rax+00h]
0x180008ad7  mov     r9, rdi; TokenHandle
0x180008ada  xor     r8d, r8d; OpenAsSelf
0x180008add  lea     edx, [r8+28h]; DesiredAccess
0x180008ae1  mov     rcx, rax; ThreadHandle
0x180008ae4  call    cs:__imp_OpenThreadToken
0x180008aeb  nop     dword ptr [rax+rax+00h]
0x180008af0  test    eax, eax
0x180008af2  jnz     loc_180008B8D
0x180008af8  call    cs:__imp_GetLastError
0x180008aff  nop     dword ptr [rax+rax+00h]
0x180008b04  cmp     eax, 3F0h
0x180008b09  jnz     loc_180008BC9
0x180008b0f  mov     ecx, 2; ImpersonationLevel
0x180008b14  call    cs:__imp_ImpersonateSelf
0x180008b1b  nop     dword ptr [rax+rax+00h]
0x180008b20  mov     rcx, [rsp+28h]; this
0x180008b25  test    eax, eax
0x180008b27  jz      loc_180008BE3
0x180008b2d  call    cs:__imp_GetCurrentThread
0x180008b34  nop     dword ptr [rax+rax+00h]
0x180008b39  mov     r9, rdi; TokenHandle
0x180008b3c  xor     r8d, r8d; OpenAsSelf
0x180008b3f  lea     edx, [r8+28h]; DesiredAccess
0x180008b43  mov     rcx, rax; ThreadHandle
0x180008b46  call    cs:__imp_OpenThreadToken
0x180008b4d  nop     dword ptr [rax+rax+00h]
0x180008b52  test    eax, eax
0x180008b54  jnz     short loc_180008B89
0x180008b56  call    cs:__imp_GetLastError
0x180008b5d  nop     dword ptr [rax+rax+00h]
0x180008b62  mov     ebx, eax
0x180008b64  call    cs:__imp_RevertToSelf
0x180008b6b  nop     dword ptr [rax+rax+00h]
0x180008b70  mov     ecx, eax
0x180008b72  call    ??$verify_bool@H$0A@@wil@@YA_NH@Z; wil::verify_bool<int,0>(int)
0x180008b77  mov     rcx, [rsp+28h]; this
0x180008b7c  lea     r8, aOnecoreVmCommo_7; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180008b83  test    al, al
0x180008b85  jz      short loc_180008BBE
0x180008b87  jmp     short loc_180008BB0
0x180008b89  mov     byte ptr [rbx+14h], 1
0x180008b8d  mov     r8d, 1; int
0x180008b93  mov     rdx, rbx; struct _LUID *
0x180008b96  mov     rcx, rdi; this
0x180008b99  call    ?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z; Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)
0x180008b9e  mov     [rbx+10h], eax
0x180008ba1  mov     rax, rbx
0x180008ba4  mov     rbx, [rsp+28h+arg_8]
0x180008ba9  add     rsp, 20h
0x180008bad  pop     rdi
0x180008bae  retn
0x180008bb0  mov     r9d, ebx; char *
0x180008bb3  mov     edx, 1DDFh; void *
0x180008bb8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180008bbe  mov     edx, 1DDEh; void *
0x180008bc3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180008bc9  mov     rcx, [rsp+28h]; this
0x180008bce  mov     r9d, eax; char *
0x180008bd1  lea     r8, aOnecoreVmCommo_7; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180008bd8  mov     edx, 1DD7h; void *
0x180008bdd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180008be3  lea     r8, aOnecoreVmCommo_7; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180008bea  mov     edx, 1DDAh; void *
0x180008bef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
