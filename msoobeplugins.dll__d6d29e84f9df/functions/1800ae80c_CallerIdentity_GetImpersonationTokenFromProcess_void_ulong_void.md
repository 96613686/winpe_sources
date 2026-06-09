# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x1800ae80c`
- end: `0x1800ae8a4`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `152`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ae6a0`

## callees

- `0x18000ac48`
- `0x1800ae80c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ae833`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ae833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae891`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae891`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800ae864`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800ae864`

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
0x1800ae80c  mov     [rsp+arg_0], rbx
0x1800ae811  push    rdi
0x1800ae812  sub     rsp, 30h
0x1800ae816  mov     rdi, r8
0x1800ae819  mov     qword ptr [r8], 0
0x1800ae820  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800ae825  mov     [rsp+38h+TokenHandle], 0
0x1800ae82e  mov     edx, 0Eh; DesiredAccess
0x1800ae833  call    cs:__imp_OpenProcessToken
0x1800ae839  test    eax, eax
0x1800ae83b  jnz     short loc_1800AE848
0x1800ae83d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ae842  mov     ebx, eax
0x1800ae844  test    eax, eax
0x1800ae846  js      short loc_1800AE879
0x1800ae848  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1800ae84d  mov     r9d, 2; ImpersonationLevel
0x1800ae853  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1800ae858  xor     r8d, r8d; lpTokenAttributes
0x1800ae85b  mov     [rsp+38h+TokenType], r9d; TokenType
0x1800ae860  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800ae864  call    cs:__imp_DuplicateTokenEx
0x1800ae86a  test    eax, eax
0x1800ae86c  jz      short loc_1800AE872
0x1800ae86e  xor     ebx, ebx
0x1800ae870  jmp     short loc_1800AE879
0x1800ae872  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ae877  mov     ebx, eax
0x1800ae879  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800ae87e  mov     [rsp+38h+TokenHandle], 0
0x1800ae887  lea     rdx, [rcx-1]
0x1800ae88b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800ae88f  ja      short loc_1800AE897
0x1800ae891  call    cs:__imp_CloseHandle
0x1800ae897  mov     eax, ebx
0x1800ae899  mov     rbx, [rsp+38h+arg_0]
0x1800ae89e  add     rsp, 30h
0x1800ae8a2  pop     rdi
0x1800ae8a3  retn
```
