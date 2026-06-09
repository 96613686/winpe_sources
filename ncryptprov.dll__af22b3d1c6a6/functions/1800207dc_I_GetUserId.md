# I_GetUserId

- ea: `0x1800207dc`
- end: `0x180020956`
- name: `I_GetUserId`
- size: `378`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800202c4`
- `0x1800204b4`
- `0x180051d20`

## callees

- `0x18000d3d0`
- `0x18000def0`
- `0x1800207dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020905`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002091a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002091a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002081b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002081b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020800`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020800`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020933`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020933`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020848`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020896`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020848`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020896`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800208ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800208ac`

## pseudocode

```c
__int64 __fastcall I_GetUserId(LPWSTR *StringSid)
{
  PSID *v2; // rdi
  HANDLE CurrentThread; // rax
  BOOL TokenInformation; // ebx
  DWORD v5; // eax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  v2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_9;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_7:
      LastError = GetLastError();
      goto LABEL_9;
    }
  }
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v5 = GetLastError();
  if ( TokenInformation || v5 != 122 )
  {
    LastError = 1287;
  }
  else
  {
    v2 = (PSID *)SafeAllocaAllocateFromHeap(TokenInformationLength);
    if ( !v2
      || !GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength)
      || !ConvertSidToStringSidW(*v2, StringSid) )
    {
      goto LABEL_7;
    }
    LastError = 0;
  }
LABEL_9:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
    MSCryptFree(v2);
  return LastError;
}

```

## disassembly

```asm
0x1800207dc  mov     rax, rsp
0x1800207df  mov     [rax+8], rbx
0x1800207e3  mov     [rax+20h], rsi
0x1800207e7  push    rdi
0x1800207e8  sub     rsp, 30h
0x1800207ec  mov     rsi, rcx
0x1800207ef  mov     qword ptr [rax+18h], 0
0x1800207f7  mov     dword ptr [rax+10h], 0
0x1800207fe  xor     edi, edi
0x180020800  call    cs:__imp_GetCurrentThread
0x180020807  nop     dword ptr [rax+rax+00h]
0x18002080c  mov     rcx, rax; ThreadHandle
0x18002080f  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180020814  lea     edx, [rdi+8]; DesiredAccess
0x180020817  lea     r8d, [rdi+1]; OpenAsSelf
0x18002081b  call    cs:__imp_OpenThreadToken
0x180020822  nop     dword ptr [rax+rax+00h]
0x180020827  test    eax, eax
0x180020829  jz      loc_180020905
0x18002082f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180020834  lea     rax, [rsp+38h+TokenInformationLength]
0x180020839  xor     r9d, r9d; TokenInformationLength
0x18002083c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180020841  xor     r8d, r8d; TokenInformation
0x180020844  lea     edx, [r9+1]; TokenInformationClass
0x180020848  call    cs:__imp_GetTokenInformation
0x18002084f  nop     dword ptr [rax+rax+00h]
0x180020854  mov     ebx, eax
0x180020856  call    cs:__imp_GetLastError
0x18002085d  nop     dword ptr [rax+rax+00h]
0x180020862  test    ebx, ebx
0x180020864  jnz     short loc_1800208CC
0x180020866  cmp     eax, 7Ah ; 'z'
0x180020869  jnz     short loc_1800208CC
0x18002086b  mov     ecx, [rsp+38h+TokenInformationLength]
0x18002086f  call    SafeAllocaAllocateFromHeap
0x180020874  mov     rdi, rax
0x180020877  test    rax, rax
0x18002087a  jz      short loc_1800208BC
0x18002087c  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180020881  lea     rax, [rsp+38h+TokenInformationLength]
0x180020886  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18002088b  lea     edx, [rbx+1]; TokenInformationClass
0x18002088e  mov     r8, rdi; TokenInformation
0x180020891  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180020896  call    cs:__imp_GetTokenInformation
0x18002089d  nop     dword ptr [rax+rax+00h]
0x1800208a2  test    eax, eax
0x1800208a4  jz      short loc_1800208BC
0x1800208a6  mov     rcx, [rdi]; Sid
0x1800208a9  mov     rdx, rsi; StringSid
0x1800208ac  call    cs:__imp_ConvertSidToStringSidW
0x1800208b3  nop     dword ptr [rax+rax+00h]
0x1800208b8  test    eax, eax
0x1800208ba  jnz     short loc_1800208F3
0x1800208bc  call    cs:__imp_GetLastError
0x1800208c3  nop     dword ptr [rax+rax+00h]
0x1800208c8  mov     ebx, eax
0x1800208ca  jmp     short loc_1800208D1
0x1800208cc  mov     ebx, 507h
0x1800208d1  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800208d6  test    rcx, rcx
0x1800208d9  jnz     short loc_1800208F7
0x1800208db  test    rdi, rdi
0x1800208de  jnz     short loc_18002094C
0x1800208e0  mov     rsi, [rsp+38h+arg_18]
0x1800208e5  mov     eax, ebx
0x1800208e7  mov     rbx, [rsp+38h+arg_0]
0x1800208ec  add     rsp, 30h
0x1800208f0  pop     rdi
0x1800208f1  retn
0x1800208f3  xor     ebx, ebx
0x1800208f5  jmp     short loc_1800208D1
0x1800208f7  call    cs:__imp_CloseHandle
0x1800208fe  nop     dword ptr [rax+rax+00h]
0x180020903  jmp     short loc_1800208DB
0x180020905  call    cs:__imp_GetLastError
0x18002090c  nop     dword ptr [rax+rax+00h]
0x180020911  mov     ebx, eax
0x180020913  cmp     eax, 3F0h
0x180020918  jnz     short loc_1800208D1
0x18002091a  call    cs:__imp_GetCurrentProcess
0x180020921  nop     dword ptr [rax+rax+00h]
0x180020926  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18002092b  mov     edx, 8; DesiredAccess
0x180020930  mov     rcx, rax; ProcessHandle
0x180020933  call    cs:__imp_OpenProcessToken
0x18002093a  nop     dword ptr [rax+rax+00h]
0x18002093f  test    eax, eax
0x180020941  jz      loc_1800208BC
0x180020947  jmp     loc_18002082F
0x18002094c  mov     rcx, rdi
0x18002094f  call    MSCryptFree
0x180020954  jmp     short loc_1800208E0
```
