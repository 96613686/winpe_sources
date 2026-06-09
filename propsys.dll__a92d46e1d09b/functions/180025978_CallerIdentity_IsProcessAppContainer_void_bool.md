# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x180025978`
- end: `0x180025a67`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `239`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025298`

## callees

- `0x180024418`
- `0x180025978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025994`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025994`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025a42`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025a42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025a5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025a5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800259e0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800259e0`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsProcessAppContainer(HANDLE ProcessHandle, bool *a2, bool *a3)
{
  signed int Error; // ebx
  char *v6; // rcx
  signed int LastError; // eax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    TokenHandle = (HANDLE)-4LL;
LABEL_3:
    Error = 0;
    goto LABEL_4;
  }
  if ( OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    goto LABEL_3;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
  if ( Error < 0 )
    goto LABEL_8;
  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    Error = 0;
LABEL_7:
    *a2 = TokenInformation != 0;
    goto LABEL_8;
  }
  Error = ResultFromKnownLastError();
  if ( Error >= 0 )
    goto LABEL_7;
LABEL_8:
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180025978  mov     [rsp+arg_18], rbx
0x18002597d  push    rdi
0x18002597e  sub     rsp, 30h
0x180025982  mov     rdi, rdx
0x180025985  mov     byte ptr [rdx], 0
0x180025988  mov     rbx, rcx
0x18002598b  mov     [rsp+38h+TokenHandle], 0
0x180025994  call    cs:__imp_GetCurrentProcess
0x18002599a  cmp     rbx, rax
0x18002599d  jnz     loc_180025A35
0x1800259a3  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x1800259ac  xor     ebx, ebx
0x1800259ae  test    ebx, ebx
0x1800259b0  js      short loc_1800259F6
0x1800259b2  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800259b7  lea     rax, [rsp+38h+arg_8]
0x1800259bc  mov     r9d, 4; TokenInformationLength
0x1800259c2  mov     [rsp+38h+arg_8], 0
0x1800259ca  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800259cf  mov     [rsp+38h+TokenInformation], 0
0x1800259d7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800259dc  lea     edx, [r9+19h]; TokenInformationClass
0x1800259e0  call    cs:__imp_GetTokenInformation
0x1800259e6  test    eax, eax
0x1800259e8  jz      short loc_180025A52
0x1800259ea  xor     ebx, ebx
0x1800259ec  cmp     [rsp+38h+TokenInformation], 0
0x1800259f1  setnz   al
0x1800259f4  mov     [rdi], al
0x1800259f6  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800259fb  mov     [rsp+38h+TokenHandle], 0
0x180025a04  lea     rdx, [rcx-1]
0x180025a08  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180025a0c  jbe     short loc_180025A5F
0x180025a0e  mov     eax, ebx
0x180025a10  mov     rbx, [rsp+38h+arg_18]
0x180025a15  add     rsp, 30h
0x180025a19  pop     rdi
0x180025a1a  retn
0x180025a1b  call    cs:__imp_GetLastError
0x180025a21  mov     ebx, eax
0x180025a23  test    eax, eax
0x180025a25  jle     short loc_1800259AE
0x180025a27  movzx   ebx, ax
0x180025a2a  or      ebx, 80070000h
0x180025a30  jmp     loc_1800259AE
0x180025a35  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180025a3a  mov     edx, 8; DesiredAccess
0x180025a3f  mov     rcx, rbx; ProcessHandle
0x180025a42  call    cs:__imp_OpenProcessToken
0x180025a48  test    eax, eax
0x180025a4a  jnz     loc_1800259AC
0x180025a50  jmp     short loc_180025A1B
0x180025a52  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180025a57  mov     ebx, eax
0x180025a59  test    eax, eax
0x180025a5b  js      short loc_1800259F6
0x180025a5d  jmp     short loc_1800259EC
0x180025a5f  call    cs:__imp_CloseHandle
0x180025a65  jmp     short loc_180025A0E
```
