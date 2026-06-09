# MemProtectThreadContext::MemProtectThreadContext(MemProtectHeap *,void (*)(void *),void *)

- ea: `0x1801f1dcc`
- end: `0x1801f1ee5`
- name: `??0MemProtectThreadContext@@QEAA@PEAVMemProtectHeap@@P6AXPEAX@Z1@Z`
- size: `281`
- prototype: `MemProtectThreadContext *__fastcall(MemProtectThreadContext *__hidden this, struct MemProtectHeap *, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1801f1c80`

## callees

- `0x180141950`
- `0x1801f1dcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f1e5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f1e79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f1e5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f1e79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801f1e6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801f1e6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f1ec9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f1ec9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1801f1ea6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1801f1ea6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1ebd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1ebd`

## pseudocode

```c
MemProtectThreadContext *__fastcall MemProtectThreadContext::MemProtectThreadContext(
        MemProtectThreadContext *this,
        struct MemProtectHeap *a2,
        void (*a3)(void *),
        void *a4)
{
  DWORD dwDesiredAccess; // esi
  __int64 v6; // rcx
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v9; // rax

  Js::AgentOfBuffer::AgentOfBuffer(this);
  dwDesiredAccess = 1048650;
  *(_BYTE *)(v6 + 16) = 0;
  *(_BYTE *)(v6 + 17) = 0;
  *((_QWORD *)this + 8) = a3;
  *(_DWORD *)(v6 + 20) = 0;
  *((_QWORD *)this + 9) = a4;
  *((_QWORD *)this + 3) = a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 12) = NtCurrentTeb();
  if ( *((_DWORD *)a2 + 13) != 1 )
    dwDesiredAccess = 0x100000;
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v9 = GetCurrentProcess();
  if ( !DuplicateHandle(v9, CurrentThread, CurrentProcess, (LPHANDLE)this + 11, dwDesiredAccess, 0, 0) )
    RaiseFailFastException(0, 0, 0);
  *((_DWORD *)this + 20) = GetCurrentThreadId();
  return this;
}

```

## disassembly

```asm
0x1801f1dcc  mov     rax, rsp
0x1801f1dcf  mov     [rax+20h], r9
0x1801f1dd3  mov     [rax+18h], r8
0x1801f1dd7  mov     [rax+10h], rdx
0x1801f1ddb  mov     [rax+8], rcx
0x1801f1ddf  push    rbx
0x1801f1de0  push    rbp
0x1801f1de1  push    rsi
0x1801f1de2  push    rdi
0x1801f1de3  sub     rsp, 48h
0x1801f1de7  mov     rbp, rcx
0x1801f1dea  call    ??0AgentOfBuffer@Js@@QEAA@XZ; Js::AgentOfBuffer::AgentOfBuffer(void)
0x1801f1def  mov     rax, [rsp+68h+arg_10]
0x1801f1df7  mov     esi, 10004Ah
0x1801f1dfc  mov     byte ptr [rcx+10h], 0
0x1801f1e00  mov     byte ptr [rcx+11h], 0
0x1801f1e04  mov     [rbp+40h], rax
0x1801f1e08  mov     rax, [rsp+68h+arg_18]
0x1801f1e10  mov     dword ptr [rcx+14h], 0
0x1801f1e17  mov     rcx, [rsp+68h+arg_8]
0x1801f1e1c  mov     [rbp+48h], rax
0x1801f1e20  mov     [rbp+18h], rcx
0x1801f1e24  mov     qword ptr [rbp+20h], 0
0x1801f1e2c  mov     qword ptr [rbp+28h], 0
0x1801f1e34  mov     qword ptr [rbp+30h], 0
0x1801f1e3c  mov     qword ptr [rbp+38h], 0
0x1801f1e44  mov     rax, gs:30h
0x1801f1e4d  mov     [rbp+60h], rax
0x1801f1e51  lea     eax, [rsi-4Ah]
0x1801f1e54  cmp     dword ptr [rcx+34h], 1
0x1801f1e58  cmovnz  esi, eax
0x1801f1e5b  call    cs:__imp_GetCurrentProcess
0x1801f1e62  nop     dword ptr [rax+rax+00h]
0x1801f1e67  mov     rdi, rax
0x1801f1e6a  call    cs:__imp_GetCurrentThread
0x1801f1e71  nop     dword ptr [rax+rax+00h]
0x1801f1e76  mov     rbx, rax
0x1801f1e79  call    cs:__imp_GetCurrentProcess
0x1801f1e80  nop     dword ptr [rax+rax+00h]
0x1801f1e85  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1801f1e8d  lea     r9, [rbp+58h]; lpTargetHandle
0x1801f1e91  mov     rcx, rax; hSourceProcessHandle
0x1801f1e94  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x1801f1e9c  mov     r8, rdi; hTargetProcessHandle
0x1801f1e9f  mov     [rsp+68h+dwDesiredAccess], esi; dwDesiredAccess
0x1801f1ea3  mov     rdx, rbx; hSourceHandle
0x1801f1ea6  call    cs:__imp_DuplicateHandle
0x1801f1ead  nop     dword ptr [rax+rax+00h]
0x1801f1eb2  test    eax, eax
0x1801f1eb4  jnz     short loc_1801F1EC9
0x1801f1eb6  xor     r8d, r8d; dwFlags
0x1801f1eb9  xor     edx, edx; pContextRecord
0x1801f1ebb  xor     ecx, ecx; pExceptionRecord
0x1801f1ebd  call    cs:__imp_RaiseFailFastException
0x1801f1ec4  nop     dword ptr [rax+rax+00h]
0x1801f1ec9  call    cs:__imp_GetCurrentThreadId
0x1801f1ed0  nop     dword ptr [rax+rax+00h]
0x1801f1ed5  mov     [rbp+50h], eax
0x1801f1ed8  mov     rax, rbp
0x1801f1edb  add     rsp, 48h
0x1801f1edf  pop     rdi
0x1801f1ee0  pop     rsi
0x1801f1ee1  pop     rbp
0x1801f1ee2  pop     rbx
0x1801f1ee3  retn
```
