# Intl_SetPrivilegeAccessToken(ushort const *,uchar,uchar *)

- ea: `0x180026874`
- end: `0x18002698e`
- name: `?Intl_SetPrivilegeAccessToken@@YAKPEBGEPEAE@Z`
- size: `282`
- prototype: `unsigned int __fastcall(LPCWSTR lpName, unsigned __int8, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025d38`
- `0x180025fe0`
- `0x180026df0`

## callees

- `0x180026874`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002694f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002694f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800268da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800268da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800268bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800268bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002696a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002696a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800268ed`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800268ed`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180026933`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180026933`

## pseudocode

```c
__int64 __fastcall Intl_SetPrivilegeAccessToken(LPCWSTR lpName, char a2, bool *a3)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF

  TokenHandle = 0;
  Luid = 0;
  NewState = 0;
  PreviousState = 0;
  ReturnLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( CurrentProcess
    && OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    && LookupPrivilegeValueW(0, lpName, &Luid)
    && (NewState.Privileges[0].Luid = Luid,
        NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0,
        AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength)) )
  {
    LastError = 0;
    if ( a3 )
      *a3 = PreviousState.Privileges[0].Attributes == 2;
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1359;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180026874  mov     [rsp-18h+arg_8], rbx
0x180026879  push    rbp
0x18002687a  push    rsi
0x18002687b  push    rdi
0x18002687c  mov     rbp, rsp
0x18002687f  sub     rsp, 70h
0x180026883  mov     rax, cs:__security_cookie
0x18002688a  xor     rax, rsp
0x18002688d  mov     [rbp+var_8], rax
0x180026891  xorps   xmm0, xmm0
0x180026894  mov     [rbp+TokenHandle], 0
0x18002689c  xorps   xmm1, xmm1
0x18002689f  mov     qword ptr [rbp+Luid.LowPart], 0
0x1800268a7  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800268ab  mov     rdi, r8
0x1800268ae  mov     sil, dl
0x1800268b1  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm1
0x1800268b5  mov     rbx, rcx
0x1800268b8  mov     [rbp+var_40], 0
0x1800268bf  call    cs:__imp_GetCurrentProcess
0x1800268c5  test    rax, rax
0x1800268c8  jz      loc_18002694F
0x1800268ce  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800268d2  mov     edx, 28h ; '('; DesiredAccess
0x1800268d7  mov     rcx, rax; ProcessHandle
0x1800268da  call    cs:__imp_OpenProcessToken
0x1800268e0  test    eax, eax
0x1800268e2  jz      short loc_18002694F
0x1800268e4  lea     r8, [rbp+Luid]; lpLuid
0x1800268e8  mov     rdx, rbx; lpName
0x1800268eb  xor     ecx, ecx; lpSystemName
0x1800268ed  call    cs:__imp_LookupPrivilegeValueW
0x1800268f3  test    eax, eax
0x1800268f5  jz      short loc_18002694F
0x1800268f7  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1800268fb  lea     r8, [rbp+NewState]; NewState
0x1800268ff  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180026903  neg     sil
0x180026906  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18002690a  mov     r9d, 10h; BufferLength
0x180026910  sbb     eax, eax
0x180026912  mov     [rbp+NewState.PrivilegeCount], 1
0x180026919  and     eax, 2
0x18002691c  xor     edx, edx; DisableAllPrivileges
0x18002691e  mov     [rbp+NewState.Privileges.Attributes], eax
0x180026921  lea     rax, [rbp+var_40]
0x180026925  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002692a  lea     rax, [rbp+var_18]
0x18002692e  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180026933  call    cs:__imp_AdjustTokenPrivileges
0x180026939  test    eax, eax
0x18002693b  jz      short loc_18002694F
0x18002693d  xor     ebx, ebx
0x18002693f  test    rdi, rdi
0x180026942  jz      short loc_180026961
0x180026944  cmp     [rbp+var_18.Privileges.Attributes], 2
0x180026948  setz    al
0x18002694b  mov     [rdi], al
0x18002694d  jmp     short loc_180026961
0x18002694f  call    cs:__imp_GetLastError
0x180026955  mov     ebx, eax
0x180026957  mov     eax, 54Fh
0x18002695c  test    ebx, ebx
0x18002695e  cmovz   ebx, eax
0x180026961  mov     rcx, [rbp+TokenHandle]; hObject
0x180026965  test    rcx, rcx
0x180026968  jz      short loc_180026970
0x18002696a  call    cs:__imp_CloseHandle
0x180026970  mov     eax, ebx
0x180026972  mov     rcx, [rbp+var_8]
0x180026976  xor     rcx, rsp; StackCookie
0x180026979  call    __security_check_cookie
0x18002697e  mov     rbx, [rsp+70h+arg_8]
0x180026986  add     rsp, 70h
0x18002698a  pop     rdi
0x18002698b  pop     rsi
0x18002698c  pop     rbp
0x18002698d  retn
```
