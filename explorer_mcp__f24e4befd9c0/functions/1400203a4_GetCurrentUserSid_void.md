# GetCurrentUserSid(void * *)

- ea: `0x1400203a4`
- end: `0x140020579`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `469`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e264`
- `0x14001e6a8`
- `0x140020260`
- `0x140020a00`
- `0x140025e1c`
- `0x1400493e8`

## callees

- `0x14001c330`
- `0x1400203a4`
- `0x14010e160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14002051e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14002051e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400203de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400203de`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400203ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400203ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020508`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400204c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400204c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140020489`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140020489`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020568`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140020434`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140020434`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400204a5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400204a5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002046f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002046f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14002045c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14002045c`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rsi
  int Error; // ebx
  void *v5; // rcx
  DWORD LengthSid; // ebp
  HLOCAL v7; // rax
  void *v8; // rdi
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-88h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  Error = ResultFromKnownLastError();
  if ( Error == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_2;
    Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
    return (unsigned int)Error;
LABEL_2:
  ReturnLength = 88;
  if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &ReturnLength) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_8;
  }
  v3 = TokenInformation;
  Error = -2147024809;
  v5 = TokenInformation;
  *a1 = 0;
  if ( !IsValidSid(v5) )
    goto LABEL_8;
  LengthSid = GetLengthSid(v3);
  Error = -2147024882;
  v7 = LocalAlloc(0x40u, LengthSid);
  v8 = v7;
  if ( !v7 )
    goto LABEL_8;
  if ( CopySid(LengthSid, v7, v3) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      LocalFree(v8);
      goto LABEL_8;
    }
  }
  *a1 = v8;
LABEL_8:
  CloseHandle(TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1400203a4  mov     [rsp+arg_8], rbx
0x1400203a9  mov     [rsp+arg_10], rbp
0x1400203ae  push    rsi
0x1400203af  push    rdi
0x1400203b0  push    r14
0x1400203b2  sub     rsp, 0B0h
0x1400203b9  mov     rax, cs:__security_cookie
0x1400203c0  xor     rax, rsp
0x1400203c3  mov     [rsp+0C8h+var_28], rax
0x1400203cb  mov     r14, rcx
0x1400203ce  mov     qword ptr [rcx], 0
0x1400203d5  mov     [rsp+0C8h+TokenHandle], 0
0x1400203de  call    cs:__imp_GetCurrentThread
0x1400203e5  nop     dword ptr [rax+rax+00h]
0x1400203ea  mov     esi, 1
0x1400203ef  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x1400203f4  mov     rcx, rax; ThreadHandle
0x1400203f7  mov     r8d, esi; OpenAsSelf
0x1400203fa  lea     edi, [rsi+7]
0x1400203fd  mov     edx, edi; DesiredAccess
0x1400203ff  call    cs:__imp_OpenThreadToken
0x140020406  nop     dword ptr [rax+rax+00h]
0x14002040b  test    eax, eax
0x14002040d  jz      loc_1400204FA
0x140020413  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x140020418  lea     rax, [rsp+0C8h+var_90]
0x14002041d  mov     r9d, 58h ; 'X'; TokenInformationLength
0x140020423  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x140020428  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x14002042d  mov     [rsp+0C8h+var_90], r9d
0x140020432  mov     edx, esi; TokenInformationClass
0x140020434  call    cs:__imp_GetTokenInformation
0x14002043b  nop     dword ptr [rax+rax+00h]
0x140020440  test    eax, eax
0x140020442  jz      loc_140020542
0x140020448  mov     rsi, [rsp+0C8h+TokenInformation]
0x14002044d  mov     ebx, 80070057h
0x140020452  mov     rcx, rsi; pSid
0x140020455  mov     qword ptr [r14], 0
0x14002045c  call    cs:__imp_IsValidSid
0x140020463  nop     dword ptr [rax+rax+00h]
0x140020468  test    eax, eax
0x14002046a  jz      short loc_1400204BE
0x14002046c  mov     rcx, rsi; pSid
0x14002046f  call    cs:__imp_GetLengthSid
0x140020476  nop     dword ptr [rax+rax+00h]
0x14002047b  mov     edx, eax; uBytes
0x14002047d  mov     ecx, 40h ; '@'; uFlags
0x140020482  mov     ebp, eax
0x140020484  mov     ebx, 8007000Eh
0x140020489  call    cs:__imp_LocalAlloc
0x140020490  nop     dword ptr [rax+rax+00h]
0x140020495  mov     rdi, rax
0x140020498  test    rax, rax
0x14002049b  jz      short loc_1400204BE
0x14002049d  mov     r8, rsi; pSourceSid
0x1400204a0  mov     rdx, rax; pDestinationSid
0x1400204a3  mov     ecx, ebp; nDestinationSidLength
0x1400204a5  call    cs:__imp_CopySid
0x1400204ac  nop     dword ptr [rax+rax+00h]
0x1400204b1  test    eax, eax
0x1400204b3  jz      loc_140020556
0x1400204b9  xor     ebx, ebx
0x1400204bb  mov     [r14], rdi
0x1400204be  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x1400204c3  call    cs:__imp_CloseHandle
0x1400204ca  nop     dword ptr [rax+rax+00h]
0x1400204cf  mov     eax, ebx
0x1400204d1  mov     rcx, [rsp+0C8h+var_28]
0x1400204d9  xor     rcx, rsp; StackCookie
0x1400204dc  call    __security_check_cookie
0x1400204e1  lea     r11, [rsp+0C8h+var_18]
0x1400204e9  mov     rbx, [r11+28h]
0x1400204ed  mov     rbp, [r11+30h]
0x1400204f1  mov     rsp, r11
0x1400204f4  pop     r14
0x1400204f6  pop     rdi
0x1400204f7  pop     rsi
0x1400204f8  retn
0x1400204fa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400204ff  mov     ebx, eax
0x140020501  cmp     eax, 800703F0h
0x140020506  jnz     short loc_140020539
0x140020508  call    cs:__imp_GetCurrentProcess
0x14002050f  nop     dword ptr [rax+rax+00h]
0x140020514  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x140020519  mov     edx, edi; DesiredAccess
0x14002051b  mov     rcx, rax; ProcessHandle
0x14002051e  call    cs:__imp_OpenProcessToken
0x140020525  nop     dword ptr [rax+rax+00h]
0x14002052a  test    eax, eax
0x14002052c  jnz     loc_140020413
0x140020532  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140020537  mov     ebx, eax
0x140020539  test    ebx, ebx
0x14002053b  js      short loc_1400204CF
0x14002053d  jmp     loc_140020413
0x140020542  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140020547  mov     ebx, eax
0x140020549  test    eax, eax
0x14002054b  js      loc_1400204BE
0x140020551  jmp     loc_140020448
0x140020556  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14002055b  mov     ebx, eax
0x14002055d  test    eax, eax
0x14002055f  jns     loc_1400204BB
0x140020565  mov     rcx, rdi; hMem
0x140020568  call    cs:__imp_LocalFree
0x14002056f  nop     dword ptr [rax+rax+00h]
0x140020574  jmp     loc_1400204BE
```
