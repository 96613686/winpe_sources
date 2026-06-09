# CfpIsThreadTerminated

- ea: `0x18000b5d8`
- end: `0x18000b655`
- name: `CfpIsThreadTerminated`
- size: `125`
- prototype: `__int64 __fastcall(DWORD dwThreadId)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800082b0`

## callees

- `0x18000b5d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000b5f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000b5f4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000b610`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000b610`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b63b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b63b`

## pseudocode

```c
__int64 __fastcall CfpIsThreadTerminated(DWORD dwThreadId)
{
  HANDLE v1; // rax
  void *v2; // rbx
  unsigned int v3; // edi
  DWORD ExitCode; // [rsp+38h] [rbp+10h] BYREF

  ExitCode = 0;
  v1 = OpenThread(0x800u, 0, dwThreadId);
  v2 = v1;
  if ( v1 && (!GetExitCodeThread(v1, &ExitCode) || ExitCode == 259) )
  {
    v3 = 0;
LABEL_6:
    CloseHandle(v2);
    return v3;
  }
  v3 = 1;
  if ( v2 )
    goto LABEL_6;
  return v3;
}

```

## disassembly

```asm
0x18000b5d8  mov     [rsp+arg_0], rbx
0x18000b5dd  push    rdi
0x18000b5de  sub     rsp, 20h
0x18000b5e2  mov     r8d, ecx; dwThreadId
0x18000b5e5  mov     [rsp+28h+ExitCode], 0
0x18000b5ed  mov     ecx, 800h; dwDesiredAccess
0x18000b5f2  xor     edx, edx; bInheritHandle
0x18000b5f4  call    cs:__imp_OpenThread
0x18000b5fb  nop     dword ptr [rax+rax+00h]
0x18000b600  mov     rbx, rax
0x18000b603  test    rax, rax
0x18000b606  jz      short loc_18000B62E
0x18000b608  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x18000b60d  mov     rcx, rax; hThread
0x18000b610  call    cs:__imp_GetExitCodeThread
0x18000b617  nop     dword ptr [rax+rax+00h]
0x18000b61c  test    eax, eax
0x18000b61e  jz      short loc_18000B62A
0x18000b620  cmp     [rsp+28h+ExitCode], 103h
0x18000b628  jnz     short loc_18000B62E
0x18000b62a  xor     edi, edi
0x18000b62c  jmp     short loc_18000B638
0x18000b62e  mov     edi, 1
0x18000b633  test    rbx, rbx
0x18000b636  jz      short loc_18000B647
0x18000b638  mov     rcx, rbx; hObject
0x18000b63b  call    cs:__imp_CloseHandle
0x18000b642  nop     dword ptr [rax+rax+00h]
0x18000b647  mov     rbx, [rsp+28h+arg_0]
0x18000b64c  mov     eax, edi
0x18000b64e  add     rsp, 20h
0x18000b652  pop     rdi
0x18000b653  retn
```
