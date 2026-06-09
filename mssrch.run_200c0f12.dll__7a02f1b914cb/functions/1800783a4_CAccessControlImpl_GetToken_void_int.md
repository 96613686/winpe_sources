# CAccessControlImpl::GetToken(void * *,int &)

- ea: `0x1800783a4`
- end: `0x180078424`
- name: `?GetToken@CAccessControlImpl@@CAJPEAPEAXAEAH@Z`
- size: `128`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180078328`
- `0x180161e58`

## callees

- `0x1800783a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800783e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800783e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800783f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800783f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800783b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800783b4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800783c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800783c9`

## pseudocode

```c
signed int __fastcall CAccessControlImpl::GetToken(PHANDLE TokenHandle, int *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int result; // eax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
    *a2 = 1;
    return 0;
  }
  *a2 = 0;
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800783a4  mov     [rsp+arg_0], rbx
0x1800783a9  push    rdi
0x1800783aa  sub     rsp, 20h
0x1800783ae  mov     rbx, rdx
0x1800783b1  mov     rdi, rcx
0x1800783b4  call    cs:__imp_GetCurrentThread
0x1800783ba  mov     edx, 8; DesiredAccess
0x1800783bf  mov     r9, rdi; TokenHandle
0x1800783c2  mov     rcx, rax; ThreadHandle
0x1800783c5  lea     r8d, [rdx-7]; OpenAsSelf
0x1800783c9  call    cs:__imp_OpenThreadToken
0x1800783cf  test    eax, eax
0x1800783d1  jnz     short loc_180078411
0x1800783d3  mov     [rbx], eax
0x1800783d5  call    cs:__imp_GetLastError
0x1800783db  cmp     eax, 3F0h
0x1800783e0  jnz     short loc_1800783FD
0x1800783e2  call    cs:__imp_GetCurrentProcess
0x1800783e8  mov     r8, rdi; TokenHandle
0x1800783eb  mov     edx, 8; DesiredAccess
0x1800783f0  mov     rcx, rax; ProcessHandle
0x1800783f3  call    cs:__imp_OpenProcessToken
0x1800783f9  test    eax, eax
0x1800783fb  jnz     short loc_180078417
0x1800783fd  call    cs:__imp_GetLastError
0x180078403  test    eax, eax
0x180078405  jle     short loc_180078419
0x180078407  movzx   eax, ax
0x18007840a  or      eax, 80070000h
0x18007840f  jmp     short loc_180078419
0x180078411  mov     dword ptr [rbx], 1
0x180078417  xor     eax, eax
0x180078419  mov     rbx, [rsp+28h+arg_0]
0x18007841e  add     rsp, 20h
0x180078422  pop     rdi
0x180078423  retn
```
