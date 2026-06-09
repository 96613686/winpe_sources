# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x180068ec4`
- end: `0x180068f5c`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `152`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068b94`

## callees

- `0x180010134`
- `0x180068ec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068eeb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068eeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068f49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068f49`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180068f1c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180068f1c`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetImpersonationTokenFromProcess(
        CallerIdentity *this,
        void *a2,
        void **a3,
        void **a4)
{
  int Error; // ebx
  char *v6; // rcx
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(this, 0xEu, &TokenHandle) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, a3) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
  }
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180068ec4  mov     [rsp+arg_0], rbx
0x180068ec9  push    rdi
0x180068eca  sub     rsp, 30h
0x180068ece  mov     rdi, r8
0x180068ed1  mov     qword ptr [r8], 0
0x180068ed8  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180068edd  mov     [rsp+38h+TokenHandle], 0
0x180068ee6  mov     edx, 0Eh; DesiredAccess
0x180068eeb  call    cs:__imp_OpenProcessToken
0x180068ef1  test    eax, eax
0x180068ef3  jnz     short loc_180068F00
0x180068ef5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180068efa  mov     ebx, eax
0x180068efc  test    eax, eax
0x180068efe  js      short loc_180068F31
0x180068f00  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x180068f05  mov     r9d, 2; ImpersonationLevel
0x180068f0b  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x180068f10  xor     r8d, r8d; lpTokenAttributes
0x180068f13  mov     [rsp+38h+TokenType], r9d; TokenType
0x180068f18  lea     edx, [r9+0Ah]; dwDesiredAccess
0x180068f1c  call    cs:__imp_DuplicateTokenEx
0x180068f22  test    eax, eax
0x180068f24  jz      short loc_180068F2A
0x180068f26  xor     ebx, ebx
0x180068f28  jmp     short loc_180068F31
0x180068f2a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180068f2f  mov     ebx, eax
0x180068f31  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180068f36  mov     [rsp+38h+TokenHandle], 0
0x180068f3f  lea     rdx, [rcx-1]
0x180068f43  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180068f47  ja      short loc_180068F4F
0x180068f49  call    cs:__imp_CloseHandle
0x180068f4f  mov     eax, ebx
0x180068f51  mov     rbx, [rsp+38h+arg_0]
0x180068f56  add     rsp, 30h
0x180068f5a  pop     rdi
0x180068f5b  retn
```
