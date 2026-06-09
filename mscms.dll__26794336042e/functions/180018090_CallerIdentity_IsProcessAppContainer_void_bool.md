# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x180018090`
- end: `0x18001816a`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `218`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b490`

## callees

- `0x180018090`
- `0x18005c320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018144`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180018136`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180018136`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800180a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800180a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018162`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800180e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800180e9`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsProcessAppContainer(HANDLE ProcessHandle, bool *a2, bool *a3)
{
  signed int Error; // ebx
  char *v6; // rcx
  signed int LastError; // eax
  int TokenInformation; // [rsp+50h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+18h] BYREF

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
0x180018090  push    rbx
0x180018092  push    rsi
0x180018093  push    rdi
0x180018094  sub     rsp, 30h
0x180018098  xor     esi, esi
0x18001809a  mov     byte ptr [rdx], 0
0x18001809d  mov     [rsp+48h+TokenHandle], rsi
0x1800180a2  mov     rdi, rdx
0x1800180a5  mov     rbx, rcx
0x1800180a8  call    cs:__imp_GetCurrentProcess
0x1800180ae  cmp     rbx, rax
0x1800180b1  jnz     short loc_180018129
0x1800180b3  mov     [rsp+48h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x1800180bc  mov     ebx, esi
0x1800180be  test    ebx, ebx
0x1800180c0  js      short loc_1800180FE
0x1800180c2  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800180c7  lea     rax, [rsp+48h+arg_8]
0x1800180cc  mov     r9d, 4; TokenInformationLength
0x1800180d2  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800180d7  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1800180dc  mov     [rsp+48h+arg_8], esi
0x1800180e0  mov     edx, 1Dh; TokenInformationClass
0x1800180e5  mov     [rsp+48h+TokenInformation], esi
0x1800180e9  call    cs:__imp_GetTokenInformation
0x1800180ef  test    eax, eax
0x1800180f1  jz      short loc_18001811C
0x1800180f3  mov     ebx, esi
0x1800180f5  cmp     [rsp+48h+TokenInformation], esi
0x1800180f9  setnz   al
0x1800180fc  mov     [rdi], al
0x1800180fe  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180018103  mov     [rsp+48h+TokenHandle], rsi
0x180018108  lea     rax, [rcx-1]
0x18001810c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018110  jbe     short loc_180018162
0x180018112  mov     eax, ebx
0x180018114  add     rsp, 30h
0x180018118  pop     rdi
0x180018119  pop     rsi
0x18001811a  pop     rbx
0x18001811b  retn
0x18001811c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180018121  mov     ebx, eax
0x180018123  test    eax, eax
0x180018125  js      short loc_1800180FE
0x180018127  jmp     short loc_1800180F5
0x180018129  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18001812e  mov     edx, 8; DesiredAccess
0x180018133  mov     rcx, rbx; ProcessHandle
0x180018136  call    cs:__imp_OpenProcessToken
0x18001813c  test    eax, eax
0x18001813e  jnz     loc_1800180BC
0x180018144  call    cs:__imp_GetLastError
0x18001814a  mov     ebx, eax
0x18001814c  test    eax, eax
0x18001814e  jle     loc_1800180BE
0x180018154  movzx   ebx, ax
0x180018157  or      ebx, 80070000h
0x18001815d  jmp     loc_1800180BE
0x180018162  call    cs:__imp_CloseHandle
0x180018168  jmp     short loc_180018112
```
