# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x14001c0a0`
- end: `0x14001c256`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `438`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001c028`
- `0x14019b85c`

## callees

- `0x14001c0a0`
- `0x14001c330`
- `0x140085c1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c1de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c1de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c243`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001c11e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001c11e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001c0c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001c0c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001c0e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001c0e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001c109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001c109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c18b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c18b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001c13f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001c13f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001c1c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001c1f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001c1c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001c1f4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c16f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c22f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c16f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c22f`

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
0x14001c0a0  mov     [rsp-28h+TokenInformationLength], r8d
0x14001c0a5  mov     [rsp-28h+TokenHandle], rcx
0x14001c0aa  push    rbp
0x14001c0ab  push    rbx
0x14001c0ac  push    rsi
0x14001c0ad  push    rdi
0x14001c0ae  push    r14
0x14001c0b0  mov     rbp, rsp
0x14001c0b3  sub     rsp, 30h
0x14001c0b7  mov     r14, r9
0x14001c0ba  mov     qword ptr [r9], 0
0x14001c0c1  mov     [rbp+TokenHandle], 0
0x14001c0c9  call    cs:__imp_GetCurrentThread
0x14001c0d0  nop     dword ptr [rax+rax+00h]
0x14001c0d5  xor     r8d, r8d; OpenAsSelf
0x14001c0d8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14001c0dc  mov     rcx, rax; ThreadHandle
0x14001c0df  lea     ebx, [r8+8]
0x14001c0e3  mov     edx, ebx; DesiredAccess
0x14001c0e5  call    cs:__imp_OpenThreadToken
0x14001c0ec  nop     dword ptr [rax+rax+00h]
0x14001c0f1  test    eax, eax
0x14001c0f3  jnz     short loc_14001C12E
0x14001c0f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001c0fa  test    eax, eax
0x14001c0fc  jns     short loc_14001C12E
0x14001c0fe  cmp     eax, 800703F0h
0x14001c103  jnz     loc_14001C199
0x14001c109  call    cs:__imp_GetCurrentProcess
0x14001c110  nop     dword ptr [rax+rax+00h]
0x14001c115  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14001c119  mov     edx, ebx; DesiredAccess
0x14001c11b  mov     rcx, rax; ProcessHandle
0x14001c11e  call    cs:__imp_OpenProcessToken
0x14001c125  nop     dword ptr [rax+rax+00h]
0x14001c12a  test    eax, eax
0x14001c12c  jz      short loc_14001C1AC
0x14001c12e  mov     rsi, [rbp+TokenHandle]
0x14001c132  mov     edx, 800h; uBytes
0x14001c137  mov     ecx, 40h ; '@'; uFlags
0x14001c13c  mov     [rbp+TokenInformationLength], edx
0x14001c13f  call    cs:__imp_LocalAlloc
0x14001c146  nop     dword ptr [rax+rax+00h]
0x14001c14b  mov     [rbp+TokenInformation], rax
0x14001c14f  mov     rdi, rax
0x14001c152  test    rax, rax
0x14001c155  jz      short loc_14001C1A5
0x14001c157  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14001c15b  lea     rax, [rbp+TokenInformationLength]
0x14001c15f  xor     ebx, ebx
0x14001c161  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14001c166  mov     r8, rdi; TokenInformation
0x14001c169  mov     rcx, rsi; TokenHandle
0x14001c16c  lea     edx, [rbx+1]; TokenInformationClass
0x14001c16f  call    cs:__imp_GetTokenInformation
0x14001c176  nop     dword ptr [rax+rax+00h]
0x14001c17b  test    eax, eax
0x14001c17d  jz      short loc_14001C1DE
0x14001c17f  mov     [r14], rdi
0x14001c182  mov     rcx, [rbp+TokenHandle]; hObject
0x14001c186  test    rcx, rcx
0x14001c189  jz      short loc_14001C197
0x14001c18b  call    cs:__imp_CloseHandle
0x14001c192  nop     dword ptr [rax+rax+00h]
0x14001c197  mov     eax, ebx
0x14001c199  add     rsp, 30h
0x14001c19d  pop     r14
0x14001c19f  pop     rdi
0x14001c1a0  pop     rsi
0x14001c1a1  pop     rbx
0x14001c1a2  pop     rbp
0x14001c1a3  retn
0x14001c1a5  mov     ebx, 8007000Eh
0x14001c1aa  jmp     short loc_14001C182
0x14001c1ac  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001c1b1  test    eax, eax
0x14001c1b3  js      short loc_14001C199
0x14001c1b5  jmp     loc_14001C12E
0x14001c1ba  test    ebx, ebx
0x14001c1bc  jns     short loc_14001C17F
0x14001c1be  mov     rcx, rdi; hMem
0x14001c1c1  call    cs:__imp_LocalFree
0x14001c1c8  nop     dword ptr [rax+rax+00h]
0x14001c1cd  jmp     short loc_14001C182
0x14001c1cf  test    eax, eax
0x14001c1d1  jle     short loc_14001C1BA
0x14001c1d3  movzx   ebx, ax
0x14001c1d6  or      ebx, 80070000h
0x14001c1dc  jmp     short loc_14001C1BA
0x14001c1de  call    cs:__imp_GetLastError
0x14001c1e5  nop     dword ptr [rax+rax+00h]
0x14001c1ea  mov     ebx, eax
0x14001c1ec  cmp     eax, 7Ah ; 'z'
0x14001c1ef  jnz     short loc_14001C1CF
0x14001c1f1  mov     rcx, rdi; hMem
0x14001c1f4  call    cs:__imp_LocalFree
0x14001c1fb  nop     dword ptr [rax+rax+00h]
0x14001c200  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x14001c204  lea     r9, [rbp+TokenInformation]; void **
0x14001c208  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x14001c20d  mov     rdi, [rbp+TokenInformation]
0x14001c211  mov     ebx, eax
0x14001c213  test    eax, eax
0x14001c215  js      short loc_14001C1BE
0x14001c217  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14001c21b  lea     rax, [rbp+TokenInformationLength]
0x14001c21f  mov     r8, rdi; TokenInformation
0x14001c222  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14001c227  mov     edx, 1; TokenInformationClass
0x14001c22c  mov     rcx, rsi; TokenHandle
0x14001c22f  call    cs:__imp_GetTokenInformation
0x14001c236  nop     dword ptr [rax+rax+00h]
0x14001c23b  test    eax, eax
0x14001c23d  jnz     loc_14001C17F
0x14001c243  call    cs:__imp_GetLastError
0x14001c24a  nop     dword ptr [rax+rax+00h]
0x14001c24f  mov     ebx, eax
0x14001c251  jmp     loc_14001C1CF
```
