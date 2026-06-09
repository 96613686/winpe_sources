# Memory::Recycler::SetIsThreadBound(void)

- ea: `0x18038f218`
- end: `0x18038f2b4`
- name: `?SetIsThreadBound@Recycler@Memory@@QEAAXXZ`
- size: `156`
- prototype: `void __fastcall(Memory::Recycler *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800b2148`
- `0x1802eebf8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18038f22c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18038f24a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18038f22c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18038f24a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18038f23b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18038f23b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18038f283`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18038f283`

## pseudocode

```c
void __fastcall Memory::Recycler::SetIsThreadBound(HANDLE *this)
{
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v3; // rax

  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v3 = GetCurrentProcess();
  DuplicateHandle(v3, CurrentThread, CurrentProcess, this + 246, 0, 0, 2u);
  this[247] = NtCurrentTeb()->NtTib.StackBase;
}

```

## disassembly

```asm
0x18038f218  mov     [rsp+arg_8], rbx
0x18038f21d  mov     [rsp+arg_10], rsi
0x18038f222  mov     [rsp+arg_0], rcx
0x18038f227  push    rdi
0x18038f228  sub     rsp, 40h
0x18038f22c  call    cs:__imp_GetCurrentProcess
0x18038f233  nop     dword ptr [rax+rax+00h]
0x18038f238  mov     rdi, rax
0x18038f23b  call    cs:__imp_GetCurrentThread
0x18038f242  nop     dword ptr [rax+rax+00h]
0x18038f247  mov     rbx, rax
0x18038f24a  call    cs:__imp_GetCurrentProcess
0x18038f251  nop     dword ptr [rax+rax+00h]
0x18038f256  mov     rsi, [rsp+48h+arg_0]
0x18038f25b  mov     r8, rdi; hTargetProcessHandle
0x18038f25e  mov     [rsp+48h+dwOptions], 2; dwOptions
0x18038f266  mov     rdx, rbx; hSourceHandle
0x18038f269  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x18038f271  mov     rcx, rax; hSourceProcessHandle
0x18038f274  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18038f27c  lea     r9, [rsi+7B0h]; lpTargetHandle
0x18038f283  call    cs:__imp_DuplicateHandle
0x18038f28a  nop     dword ptr [rax+rax+00h]
0x18038f28f  mov     rax, gs:30h
0x18038f298  mov     rbx, [rsp+48h+arg_8]
0x18038f29d  mov     rcx, [rax+8]
0x18038f2a1  mov     [rsi+7B8h], rcx
0x18038f2a8  mov     rsi, [rsp+48h+arg_10]
0x18038f2ad  add     rsp, 40h
0x18038f2b1  pop     rdi
0x18038f2b2  retn
```
