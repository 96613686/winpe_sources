# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x1400168e8`
- end: `0x140016a4b`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `355`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001687c`
- `0x14018f028`

## callees

- `0x1400168e8`
- `0x140016b10`
- `0x14007ff8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400169ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400169ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016a41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140016941`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140016941`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140016927`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140016927`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140016950`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140016950`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140016911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140016911`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400169ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400169ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400169d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400169fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400169d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400169fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001696b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001696b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140016995`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140016a33`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140016995`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140016a33`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(__int64 a1, __int64 a2, DWORD a3, _QWORD *a4)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  void *v8; // rsi
  void *v9; // rdi
  signed int v10; // ebx
  signed int LastError; // eax
  unsigned int v12; // edx
  void *v13; // rcx
  int v14; // eax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    result = ResultFromKnownLastError();
    if ( (int)result < 0 )
    {
      if ( (_DWORD)result != -2147023888 )
        return result;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        result = ResultFromKnownLastError();
        if ( (int)result < 0 )
          return result;
      }
    }
  }
  v8 = TokenHandle;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v9 = TokenInformation;
  if ( !TokenInformation )
  {
    v10 = -2147024882;
    goto LABEL_8;
  }
  v10 = 0;
  if ( !GetTokenInformation(v8, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v9);
      v14 = CTLocalAllocPolicy::Alloc(v13, v12, TokenInformationLength, &TokenInformation);
      v9 = TokenInformation;
      v10 = v14;
      if ( v14 < 0 )
        goto LABEL_16;
      if ( GetTokenInformation(v8, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_7;
      LastError = GetLastError();
      v10 = LastError;
    }
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      goto LABEL_7;
LABEL_16:
    LocalFree(v9);
    goto LABEL_8;
  }
LABEL_7:
  *a4 = v9;
LABEL_8:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400168e8  mov     [rsp-28h+TokenInformationLength], r8d
0x1400168ed  mov     [rsp-28h+TokenHandle], rcx
0x1400168f2  push    rbp
0x1400168f3  push    rbx
0x1400168f4  push    rsi
0x1400168f5  push    rdi
0x1400168f6  push    r14
0x1400168f8  mov     rbp, rsp
0x1400168fb  sub     rsp, 30h
0x1400168ff  mov     r14, r9
0x140016902  mov     qword ptr [r9], 0
0x140016909  mov     [rbp+TokenHandle], 0
0x140016911  call    cs:__imp_GetCurrentThread
0x140016917  xor     r8d, r8d; OpenAsSelf
0x14001691a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14001691e  mov     rcx, rax; ThreadHandle
0x140016921  lea     ebx, [r8+8]
0x140016925  mov     edx, ebx; DesiredAccess
0x140016927  call    cs:__imp_OpenThreadToken
0x14001692d  test    eax, eax
0x14001692f  jnz     short loc_14001695A
0x140016931  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140016936  test    eax, eax
0x140016938  jns     short loc_14001695A
0x14001693a  cmp     eax, 800703F0h
0x14001693f  jnz     short loc_1400169B3
0x140016941  call    cs:__imp_GetCurrentProcess
0x140016947  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14001694b  mov     edx, ebx; DesiredAccess
0x14001694d  mov     rcx, rax; ProcessHandle
0x140016950  call    cs:__imp_OpenProcessToken
0x140016956  test    eax, eax
0x140016958  jz      short loc_1400169C5
0x14001695a  mov     rsi, [rbp+TokenHandle]
0x14001695e  mov     edx, 800h; uBytes
0x140016963  mov     ecx, 40h ; '@'; uFlags
0x140016968  mov     [rbp+TokenInformationLength], edx
0x14001696b  call    cs:__imp_LocalAlloc
0x140016971  mov     [rbp+TokenInformation], rax
0x140016975  mov     rdi, rax
0x140016978  test    rax, rax
0x14001697b  jz      short loc_1400169BE
0x14001697d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140016981  lea     rax, [rbp+TokenInformationLength]
0x140016985  xor     ebx, ebx
0x140016987  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14001698c  mov     r8, rdi; TokenInformation
0x14001698f  mov     rcx, rsi; TokenHandle
0x140016992  lea     edx, [rbx+1]; TokenInformationClass
0x140016995  call    cs:__imp_GetTokenInformation
0x14001699b  test    eax, eax
0x14001699d  jz      short loc_1400169EE
0x14001699f  mov     [r14], rdi
0x1400169a2  mov     rcx, [rbp+TokenHandle]; hObject
0x1400169a6  test    rcx, rcx
0x1400169a9  jz      short loc_1400169B1
0x1400169ab  call    cs:__imp_CloseHandle
0x1400169b1  mov     eax, ebx
0x1400169b3  add     rsp, 30h
0x1400169b7  pop     r14
0x1400169b9  pop     rdi
0x1400169ba  pop     rsi
0x1400169bb  pop     rbx
0x1400169bc  pop     rbp
0x1400169bd  retn
0x1400169be  mov     ebx, 8007000Eh
0x1400169c3  jmp     short loc_1400169A2
0x1400169c5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400169ca  test    eax, eax
0x1400169cc  js      short loc_1400169B3
0x1400169ce  jmp     short loc_14001695A
0x1400169d0  test    ebx, ebx
0x1400169d2  jns     short loc_14001699F
0x1400169d4  mov     rcx, rdi; hMem
0x1400169d7  call    cs:__imp_LocalFree
0x1400169dd  jmp     short loc_1400169A2
0x1400169df  test    eax, eax
0x1400169e1  jle     short loc_1400169D0
0x1400169e3  movzx   ebx, ax
0x1400169e6  or      ebx, 80070000h
0x1400169ec  jmp     short loc_1400169D0
0x1400169ee  call    cs:__imp_GetLastError
0x1400169f4  mov     ebx, eax
0x1400169f6  cmp     eax, 7Ah ; 'z'
0x1400169f9  jnz     short loc_1400169DF
0x1400169fb  mov     rcx, rdi; hMem
0x1400169fe  call    cs:__imp_LocalFree
0x140016a04  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x140016a08  lea     r9, [rbp+TokenInformation]; void **
0x140016a0c  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x140016a11  mov     rdi, [rbp+TokenInformation]
0x140016a15  mov     ebx, eax
0x140016a17  test    eax, eax
0x140016a19  js      short loc_1400169D4
0x140016a1b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140016a1f  lea     rax, [rbp+TokenInformationLength]
0x140016a23  mov     r8, rdi; TokenInformation
0x140016a26  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140016a2b  mov     edx, 1; TokenInformationClass
0x140016a30  mov     rcx, rsi; TokenHandle
0x140016a33  call    cs:__imp_GetTokenInformation
0x140016a39  test    eax, eax
0x140016a3b  jnz     loc_14001699F
0x140016a41  call    cs:__imp_GetLastError
0x140016a47  mov     ebx, eax
0x140016a49  jmp     short loc_1400169DF
```
