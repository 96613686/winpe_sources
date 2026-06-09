# CGhostThread::ShutdownGhostThread(void * *)

- ea: `0x180008b38`
- end: `0x180008c08`
- name: `?ShutdownGhostThread@CGhostThread@@QEAAHPEAPEAX@Z`
- size: `208`
- prototype: `int(CGhostThread *__hidden this, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007b74`
- `0x180008558`

## callees

- `0x1800087f0`
- `0x180008b00`
- `0x180008b38`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008b8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008b8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008bb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008bbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008bb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008bbd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008be7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008be7`

## pseudocode

```c
_BOOL8 __fastcall CGhostThread::ShutdownGhostThread(HANDLE *this, void **a2)
{
  int v2; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // r14
  int State; // ebp
  HANDLE CurrentProcess; // rax
  HANDLE v8; // rdi
  void *v9; // rbx
  HANDLE v10; // rax

  v2 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
  CLock::Acquire((LPCRITICAL_SECTION)(this + 2));
  State = CGhostThread::GetState(this);
  if ( State == 1 )
  {
    CGhostThread::SetState(this, 4);
  }
  else
  {
    if ( State == 2 )
    {
      CGhostThread::SetState(this, 3);
    }
    else if ( State != 3 )
    {
      goto LABEL_10;
    }
    SetEvent(this[8]);
    v2 = 1;
  }
LABEL_10:
  if ( a2 && v2 )
  {
    CurrentProcess = GetCurrentProcess();
    v8 = this[12];
    v9 = CurrentProcess;
    v10 = GetCurrentProcess();
    DuplicateHandle(v10, v8, v9, a2, 0, 0, 2u);
  }
  CLock::Release(v5);
  return State == 4;
}

```

## disassembly

```asm
0x180008b38  push    rbx
0x180008b3a  push    rbp
0x180008b3b  push    rsi
0x180008b3c  push    rdi
0x180008b3d  push    r14
0x180008b3f  sub     rsp, 40h
0x180008b43  xor     ebx, ebx
0x180008b45  mov     rsi, rdx
0x180008b48  mov     rdi, rcx
0x180008b4b  test    rdx, rdx
0x180008b4e  jz      short loc_180008B53
0x180008b50  mov     [rdx], rbx
0x180008b53  lea     r14, [rcx+10h]
0x180008b57  mov     rcx, r14; lpCriticalSection
0x180008b5a  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180008b5f  mov     rcx, rdi
0x180008b62  call    ?GetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@XZ; CGhostThread::GetState(void)
0x180008b67  mov     edx, eax
0x180008b69  mov     ebp, eax
0x180008b6b  sub     edx, 1
0x180008b6e  jz      short loc_180008B9A
0x180008b70  sub     edx, 1
0x180008b73  jz      short loc_180008B7C
0x180008b75  cmp     edx, 1
0x180008b78  jz      short loc_180008B89
0x180008b7a  jmp     short loc_180008BA7
0x180008b7c  mov     edx, 3
0x180008b81  mov     rcx, rdi
0x180008b84  call    ?SetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@W42@@Z; CGhostThread::SetState(tagGHOSTTHREADSTATE)
0x180008b89  mov     rcx, [rdi+40h]; hEvent
0x180008b8d  call    cs:__imp_SetEvent
0x180008b93  mov     ebx, 1
0x180008b98  jmp     short loc_180008BA7
0x180008b9a  mov     edx, 4
0x180008b9f  mov     rcx, rdi
0x180008ba2  call    ?SetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@W42@@Z; CGhostThread::SetState(tagGHOSTTHREADSTATE)
0x180008ba7  test    rsi, rsi
0x180008baa  jz      short loc_180008BED
0x180008bac  test    ebx, ebx
0x180008bae  jz      short loc_180008BED
0x180008bb0  call    cs:__imp_GetCurrentProcess
0x180008bb6  mov     rdi, [rdi+60h]
0x180008bba  mov     rbx, rax
0x180008bbd  call    cs:__imp_GetCurrentProcess
0x180008bc3  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180008bcb  mov     r9, rsi; lpTargetHandle
0x180008bce  mov     rcx, rax; hSourceProcessHandle
0x180008bd1  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180008bd9  mov     r8, rbx; hTargetProcessHandle
0x180008bdc  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180008be4  mov     rdx, rdi; hSourceHandle
0x180008be7  call    cs:__imp_DuplicateHandle
0x180008bed  mov     rcx, r14; lpCriticalSection
0x180008bf0  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180008bf5  xor     eax, eax
0x180008bf7  cmp     ebp, 4
0x180008bfa  setz    al
0x180008bfd  add     rsp, 40h
0x180008c01  pop     r14
0x180008c03  pop     rdi
0x180008c04  pop     rsi
0x180008c05  pop     rbp
0x180008c06  pop     rbx
0x180008c07  retn
```
