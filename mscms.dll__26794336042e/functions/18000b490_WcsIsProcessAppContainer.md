# WcsIsProcessAppContainer

- ea: `0x18000b490`
- end: `0x18000b6a8`
- name: `WcsIsProcessAppContainer`
- size: `536`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a780`

## callees

- `0x18000b490`
- `0x180018090`
- `0x18005c320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b636`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b675`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b675`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b5a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b5a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b617`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b687`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b698`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b687`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b65c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b651`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b651`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b511`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b511`

## pseudocode

```c
signed int __fastcall WcsIsProcessAppContainer(_DWORD *a1)
{
  HANDLE CurrentProcess; // rax
  bool v3; // si
  void *v4; // rbx
  signed int Error; // edi
  char *v6; // rcx
  signed int v7; // ebx
  signed int result; // eax
  signed int LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  HANDLE v12; // rax
  bool *v13; // r8
  signed int IsProcessAppContainer; // eax
  HANDLE CurrentThread; // rax
  HANDLE Token; // [rsp+30h] [rbp-38h] BYREF
  bool v17; // [rsp+70h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+78h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+88h] [rbp+20h] BYREF

  *a1 = 0;
  Token = 0;
  CurrentProcess = GetCurrentProcess();
  v3 = 0;
  TokenHandle = 0;
  v4 = CurrentProcess;
  v17 = 0;
  if ( CurrentProcess == GetCurrentProcess() )
  {
    TokenHandle = (HANDLE)-4LL;
LABEL_3:
    Error = 0;
    goto LABEL_4;
  }
  if ( OpenProcessToken(v4, 8u, &TokenHandle) )
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
    v3 = TokenInformation != 0;
    v17 = TokenInformation != 0;
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
  v7 = -2147024891;
  if ( Error != -2147024891 )
  {
    v7 = Error;
LABEL_12:
    if ( v7 >= 0 && v3 )
      *a1 = 1;
    goto LABEL_15;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &Token) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 == -2147023888 )
      goto LABEL_15;
    if ( v10 < 0 )
    {
      v7 = v10;
      goto LABEL_15;
    }
  }
  if ( SetThreadToken(0, 0) )
    goto LABEL_31;
  v11 = GetLastError();
  v7 = v11;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_31:
    v12 = GetCurrentProcess();
    IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(v12, &v17, v13);
    v3 = v17;
    v7 = IsProcessAppContainer;
    goto LABEL_12;
  }
LABEL_15:
  if ( !Token || SetThreadToken(0, Token) )
    return v7;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000b490  push    rbx
0x18000b492  push    rbp
0x18000b493  push    rsi
0x18000b494  push    rdi
0x18000b495  push    r14
0x18000b497  sub     rsp, 40h
0x18000b49b  xor     ebp, ebp
0x18000b49d  mov     r14, rcx
0x18000b4a0  mov     [rcx], ebp
0x18000b4a2  mov     [rsp+68h+Token], rbp
0x18000b4a7  call    cs:__imp_GetCurrentProcess
0x18000b4ad  xor     sil, sil
0x18000b4b0  mov     [rsp+68h+TokenHandle], rbp
0x18000b4b8  mov     rbx, rax
0x18000b4bb  mov     [rsp+68h+arg_0], sil
0x18000b4c0  call    cs:__imp_GetCurrentProcess
0x18000b4c6  cmp     rbx, rax
0x18000b4c9  jnz     loc_18000B592
0x18000b4cf  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x18000b4db  mov     edi, ebp
0x18000b4dd  test    edi, edi
0x18000b4df  js      short loc_18000B52A
0x18000b4e1  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18000b4e9  lea     rax, [rsp+68h+arg_10]
0x18000b4f1  mov     r9d, 4; TokenInformationLength
0x18000b4f7  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18000b4fc  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x18000b501  mov     [rsp+68h+arg_10], ebp
0x18000b508  mov     edx, 1Dh; TokenInformationClass
0x18000b50d  mov     [rsp+68h+TokenInformation], ebp
0x18000b511  call    cs:__imp_GetTokenInformation
0x18000b517  test    eax, eax
0x18000b519  jz      short loc_18000B585
0x18000b51b  mov     edi, ebp
0x18000b51d  cmp     [rsp+68h+TokenInformation], ebp
0x18000b521  setnz   sil
0x18000b525  mov     [rsp+68h+arg_0], sil
0x18000b52a  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18000b532  mov     [rsp+68h+TokenHandle], rbp
0x18000b53a  lea     rax, [rcx-1]
0x18000b53e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b542  jbe     loc_18000B651
0x18000b548  mov     ebx, 80070005h
0x18000b54d  cmp     edi, ebx
0x18000b54f  jz      loc_18000B65C
0x18000b555  mov     ebx, edi
0x18000b557  test    ebx, ebx
0x18000b559  js      short loc_18000B561
0x18000b55b  cmp     sil, 1
0x18000b55f  jz      short loc_18000B57C
0x18000b561  mov     rdx, [rsp+68h+Token]; Token
0x18000b566  test    rdx, rdx
0x18000b569  jnz     loc_18000B696
0x18000b56f  mov     eax, ebx
0x18000b571  add     rsp, 40h
0x18000b575  pop     r14
0x18000b577  pop     rdi
0x18000b578  pop     rsi
0x18000b579  pop     rbp
0x18000b57a  pop     rbx
0x18000b57b  retn
0x18000b57c  mov     dword ptr [r14], 1
0x18000b583  jmp     short loc_18000B561
0x18000b585  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b58a  mov     edi, eax
0x18000b58c  test    eax, eax
0x18000b58e  js      short loc_18000B52A
0x18000b590  jmp     short loc_18000B51D
0x18000b592  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x18000b59a  mov     edx, 8; DesiredAccess
0x18000b59f  mov     rcx, rbx; ProcessHandle
0x18000b5a2  call    cs:__imp_OpenProcessToken
0x18000b5a8  test    eax, eax
0x18000b5aa  jnz     loc_18000B4DB
0x18000b5b0  call    cs:__imp_GetLastError
0x18000b5b6  mov     edi, eax
0x18000b5b8  test    eax, eax
0x18000b5ba  jle     loc_18000B4DD
0x18000b5c0  movzx   edi, ax
0x18000b5c3  or      edi, 80070000h
0x18000b5c9  jmp     loc_18000B4DD
0x18000b5ce  call    cs:__imp_GetLastError
0x18000b5d4  test    eax, eax
0x18000b5d6  jle     short loc_18000B5E0
0x18000b5d8  movzx   eax, ax
0x18000b5db  or      eax, 80070000h
0x18000b5e0  cmp     eax, 800703F0h
0x18000b5e5  jz      loc_18000B561
0x18000b5eb  test    eax, eax
0x18000b5ed  jns     loc_18000B683
0x18000b5f3  mov     ebx, eax
0x18000b5f5  jmp     loc_18000B561
0x18000b5fa  call    cs:__imp_GetLastError
0x18000b600  mov     ebx, eax
0x18000b602  test    eax, eax
0x18000b604  jle     short loc_18000B60F
0x18000b606  movzx   ebx, ax
0x18000b609  or      ebx, 80070000h
0x18000b60f  test    ebx, ebx
0x18000b611  js      loc_18000B561
0x18000b617  call    cs:__imp_GetCurrentProcess
0x18000b61d  mov     rcx, rax; ProcessHandle
0x18000b620  lea     rdx, [rsp+68h+arg_0]; void *
0x18000b625  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18000b62a  movzx   esi, [rsp+68h+arg_0]
0x18000b62f  mov     ebx, eax
0x18000b631  jmp     loc_18000B557
0x18000b636  call    cs:__imp_GetLastError
0x18000b63c  test    eax, eax
0x18000b63e  jle     loc_18000B571
0x18000b644  movzx   eax, ax
0x18000b647  or      eax, 80070000h
0x18000b64c  jmp     loc_18000B571
0x18000b651  call    cs:__imp_CloseHandle
0x18000b657  jmp     loc_18000B548
0x18000b65c  call    cs:__imp_GetCurrentThread
0x18000b662  lea     r9, [rsp+68h+Token]; TokenHandle
0x18000b667  mov     edx, 4; DesiredAccess
0x18000b66c  mov     rcx, rax; ThreadHandle
0x18000b66f  mov     r8d, 1; OpenAsSelf
0x18000b675  call    cs:__imp_OpenThreadToken
0x18000b67b  test    eax, eax
0x18000b67d  jz      loc_18000B5CE
0x18000b683  xor     edx, edx; Token
0x18000b685  xor     ecx, ecx; Thread
0x18000b687  call    cs:__imp_SetThreadToken
0x18000b68d  test    eax, eax
0x18000b68f  jnz     short loc_18000B617
0x18000b691  jmp     loc_18000B5FA
0x18000b696  xor     ecx, ecx; Thread
0x18000b698  call    cs:__imp_SetThreadToken
0x18000b69e  test    eax, eax
0x18000b6a0  jnz     loc_18000B56F
0x18000b6a6  jmp     short loc_18000B636
```
