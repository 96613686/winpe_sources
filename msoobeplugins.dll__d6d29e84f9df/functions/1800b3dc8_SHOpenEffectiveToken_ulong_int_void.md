# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1800b3dc8`
- end: `0x1800b3e2f`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800b3cb4`

## callees

- `0x18000ac48`
- `0x1800b3dc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b3dd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b3dd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b3deb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b3deb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b3e01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b3e01`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b3e12`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b3e12`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, a3) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1800b3dc8  push    rbx
0x1800b3dca  sub     rsp, 20h
0x1800b3dce  mov     rbx, r8
0x1800b3dd1  mov     qword ptr [r8], 0
0x1800b3dd8  call    cs:__imp_GetCurrentThread
0x1800b3dde  xor     r8d, r8d; OpenAsSelf
0x1800b3de1  mov     r9, rbx; TokenHandle
0x1800b3de4  mov     rcx, rax; ThreadHandle
0x1800b3de7  lea     edx, [r8+28h]; DesiredAccess
0x1800b3deb  call    cs:__imp_OpenThreadToken
0x1800b3df1  test    eax, eax
0x1800b3df3  jnz     short loc_1800B3E1C
0x1800b3df5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b3dfa  cmp     eax, 800703F0h
0x1800b3dff  jnz     short loc_1800B3E29
0x1800b3e01  call    cs:__imp_GetCurrentProcess
0x1800b3e07  mov     r8, rbx; TokenHandle
0x1800b3e0a  mov     edx, 28h ; '('; DesiredAccess
0x1800b3e0f  mov     rcx, rax; ProcessHandle
0x1800b3e12  call    cs:__imp_OpenProcessToken
0x1800b3e18  test    eax, eax
0x1800b3e1a  jz      short loc_1800B3E24
0x1800b3e1c  xor     eax, eax
0x1800b3e1e  add     rsp, 20h
0x1800b3e22  pop     rbx
0x1800b3e23  retn
0x1800b3e24  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b3e29  add     rsp, 20h
0x1800b3e2d  pop     rbx
0x1800b3e2e  retn
```
