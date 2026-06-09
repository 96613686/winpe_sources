# I_GetProcessInfo

- ea: `0x1800206c8`
- end: `0x1800207d6`
- name: `I_GetProcessInfo`
- size: `270`
- prototype: `__int64 __fastcall(DWORD *, WCHAR **)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800201c0`
- `0x1800202c4`
- `0x1800204b4`
- `0x180051d20`

## callees

- `0x18000d3d0`
- `0x18000def0`
- `0x1800206c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207b0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180020758`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180020758`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020779`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180020721`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180020721`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800206f6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800206f6`

## pseudocode

```c
__int64 __fastcall I_GetProcessInfo(DWORD *a1, WCHAR **a2)
{
  DWORD LastError; // ebx
  HANDLE v5; // rsi
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  __int64 result; // rax
  DWORD dwProcessId; // [rsp+40h] [rbp+8h] BYREF
  DWORD dwSize; // [rsp+48h] [rbp+10h] BYREF

  dwProcessId = 0;
  dwSize = 1023;
  LastError = I_RpcBindingInqLocalClientPID(0, &dwProcessId);
  if ( LastError )
    goto LABEL_10;
  if ( !dwProcessId )
  {
    LastError = 1287;
LABEL_10:
    v7 = 0;
    goto LABEL_9;
  }
  v5 = OpenProcess(0x1000u, 0, dwProcessId);
  if ( v5 )
  {
    v6 = (WCHAR *)SafeAllocaAllocateFromHeap(2LL * (dwSize + 1));
    v7 = v6;
    if ( !v6 || !QueryFullProcessImageNameW(v5, 0, v6, &dwSize) )
      LastError = GetLastError();
    CloseHandle(v5);
  }
  else
  {
    v7 = 0;
    LastError = GetLastError();
  }
  if ( LastError )
  {
    if ( v7 )
      MSCryptFree(v7);
    goto LABEL_10;
  }
LABEL_9:
  *a1 = dwProcessId;
  result = LastError;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x1800206c8  mov     rax, rsp
0x1800206cb  mov     [rax+18h], rbx
0x1800206cf  mov     [rax+20h], rsi
0x1800206d3  push    rdi
0x1800206d4  push    r14
0x1800206d6  push    r15
0x1800206d8  sub     rsp, 20h
0x1800206dc  mov     r14, rdx
0x1800206df  mov     dword ptr [rax+8], 0
0x1800206e6  mov     r15, rcx
0x1800206e9  mov     dword ptr [rax+10h], 3FFh
0x1800206f0  lea     rdx, [rax+8]; Pid
0x1800206f4  xor     ecx, ecx; Binding
0x1800206f6  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800206fd  nop     dword ptr [rax+rax+00h]
0x180020702  mov     ebx, eax
0x180020704  test    eax, eax
0x180020706  jnz     loc_1800207AA
0x18002070c  mov     r8d, [rsp+38h+dwProcessId]; dwProcessId
0x180020711  test    r8d, r8d
0x180020714  jz      loc_1800207CF
0x18002071a  xor     edx, edx; bInheritHandle
0x18002071c  mov     ecx, 1000h; dwDesiredAccess
0x180020721  call    cs:__imp_OpenProcess
0x180020728  nop     dword ptr [rax+rax+00h]
0x18002072d  mov     rsi, rax
0x180020730  test    rax, rax
0x180020733  jz      short loc_1800207AE
0x180020735  mov     ecx, [rsp+38h+dwSize]
0x180020739  inc     ecx
0x18002073b  add     rcx, rcx
0x18002073e  call    SafeAllocaAllocateFromHeap
0x180020743  mov     rdi, rax
0x180020746  test    rax, rax
0x180020749  jz      short loc_180020768
0x18002074b  lea     r9, [rsp+38h+dwSize]; lpdwSize
0x180020750  mov     r8, rax; lpExeName
0x180020753  xor     edx, edx; dwFlags
0x180020755  mov     rcx, rsi; hProcess
0x180020758  call    cs:__imp_QueryFullProcessImageNameW
0x18002075f  nop     dword ptr [rax+rax+00h]
0x180020764  test    eax, eax
0x180020766  jnz     short loc_180020776
0x180020768  call    cs:__imp_GetLastError
0x18002076f  nop     dword ptr [rax+rax+00h]
0x180020774  mov     ebx, eax
0x180020776  mov     rcx, rsi; hObject
0x180020779  call    cs:__imp_CloseHandle
0x180020780  nop     dword ptr [rax+rax+00h]
0x180020785  test    ebx, ebx
0x180020787  jnz     short loc_1800207C0
0x180020789  mov     eax, [rsp+38h+dwProcessId]
0x18002078d  mov     rsi, [rsp+38h+arg_18]
0x180020792  mov     [r15], eax
0x180020795  mov     eax, ebx
0x180020797  mov     rbx, [rsp+38h+arg_10]
0x18002079c  mov     [r14], rdi
0x18002079f  add     rsp, 20h
0x1800207a3  pop     r15
0x1800207a5  pop     r14
0x1800207a7  pop     rdi
0x1800207a8  retn
0x1800207aa  xor     edi, edi
0x1800207ac  jmp     short loc_180020789
0x1800207ae  xor     edi, edi
0x1800207b0  call    cs:__imp_GetLastError
0x1800207b7  nop     dword ptr [rax+rax+00h]
0x1800207bc  mov     ebx, eax
0x1800207be  jmp     short loc_180020785
0x1800207c0  test    rdi, rdi
0x1800207c3  jz      short loc_1800207AA
0x1800207c5  mov     rcx, rdi
0x1800207c8  call    MSCryptFree
0x1800207cd  jmp     short loc_1800207AA
0x1800207cf  mov     ebx, 507h
0x1800207d4  jmp     short loc_1800207AA
```
