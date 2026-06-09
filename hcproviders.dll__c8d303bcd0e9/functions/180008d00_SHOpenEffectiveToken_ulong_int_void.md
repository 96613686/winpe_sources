# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x180008d00`
- end: `0x180008dbc`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `188`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180008dc4`

## callees

- `0x180004a4c`
- `0x180008d00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008d80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008d80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008d10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008d10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008d49`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008d29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008d64`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008d29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008d64`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008d97`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008d97`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE v6; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (int)result >= 0 )
    return result;
  if ( (_DWORD)result == -2147024891 )
  {
    v6 = GetCurrentThread();
    if ( !OpenThreadToken(v6, 0x28u, 1, a3) )
    {
      result = ResultFromKnownLastError();
      goto LABEL_6;
    }
    return 0;
  }
LABEL_6:
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, a3) )
    return 0;
  return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180008d00  push    rbx
0x180008d02  sub     rsp, 20h
0x180008d06  mov     rbx, r8
0x180008d09  mov     qword ptr [r8], 0
0x180008d10  call    cs:__imp_GetCurrentThread
0x180008d17  nop     dword ptr [rax+rax+00h]
0x180008d1c  xor     r8d, r8d; OpenAsSelf
0x180008d1f  mov     r9, rbx; TokenHandle
0x180008d22  mov     rcx, rax; ThreadHandle
0x180008d25  lea     edx, [r8+28h]; DesiredAccess
0x180008d29  call    cs:__imp_OpenThreadToken
0x180008d30  nop     dword ptr [rax+rax+00h]
0x180008d35  test    eax, eax
0x180008d37  jnz     short loc_180008DA7
0x180008d39  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180008d3e  test    eax, eax
0x180008d40  jns     short loc_180008DB5
0x180008d42  cmp     eax, 80070005h
0x180008d47  jnz     short loc_180008D79
0x180008d49  call    cs:__imp_GetCurrentThread
0x180008d50  nop     dword ptr [rax+rax+00h]
0x180008d55  mov     edx, 28h ; '('; DesiredAccess
0x180008d5a  mov     r9, rbx; TokenHandle
0x180008d5d  mov     rcx, rax; ThreadHandle
0x180008d60  lea     r8d, [rdx-27h]; OpenAsSelf
0x180008d64  call    cs:__imp_OpenThreadToken
0x180008d6b  nop     dword ptr [rax+rax+00h]
0x180008d70  test    eax, eax
0x180008d72  jnz     short loc_180008DA7
0x180008d74  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180008d79  cmp     eax, 800703F0h
0x180008d7e  jnz     short loc_180008DB5
0x180008d80  call    cs:__imp_GetCurrentProcess
0x180008d87  nop     dword ptr [rax+rax+00h]
0x180008d8c  mov     r8, rbx; TokenHandle
0x180008d8f  mov     edx, 28h ; '('; DesiredAccess
0x180008d94  mov     rcx, rax; ProcessHandle
0x180008d97  call    cs:__imp_OpenProcessToken
0x180008d9e  nop     dword ptr [rax+rax+00h]
0x180008da3  test    eax, eax
0x180008da5  jz      short loc_180008DB0
0x180008da7  xor     eax, eax
0x180008da9  add     rsp, 20h
0x180008dad  pop     rbx
0x180008dae  retn
0x180008db0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180008db5  add     rsp, 20h
0x180008db9  pop     rbx
0x180008dba  retn
```
