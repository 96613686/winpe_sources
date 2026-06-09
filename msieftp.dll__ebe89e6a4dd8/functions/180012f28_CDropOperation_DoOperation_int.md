# CDropOperation::DoOperation(int)

- ea: `0x180012f28`
- end: `0x180012fa7`
- name: `?DoOperation@CDropOperation@@QEAAJH@Z`
- size: `127`
- prototype: `__int64 __fastcall(CDropOperation *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800129a0`

## callees

- `0x180012f28`
- `0x180014c6c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012f69`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f77`

## pseudocode

```c
__int64 __fastcall CDropOperation::DoOperation(CDropOperation *this, int a2)
{
  unsigned int v4; // ebx
  HANDLE v5; // rax
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  (*(void (__fastcall **)(CDropOperation *))(*(_QWORD *)this + 8LL))(this);
  if ( a2 )
  {
    v4 = 0;
    ThreadId = 0;
    v5 = CreateThread(0, 0, CDropOperation::_ThreadProc, this, 0, &ThreadId);
    if ( v5 )
      CloseHandle(v5);
    else
      (*(void (__fastcall **)(CDropOperation *))(*(_QWORD *)this + 16LL))(this);
  }
  else
  {
    return (unsigned int)CDropOperation::_ThreadProcCB(this);
  }
  return v4;
}

```

## disassembly

```asm
0x180012f28  mov     [rsp+arg_0], rbx
0x180012f2d  push    rdi
0x180012f2e  sub     rsp, 30h
0x180012f32  mov     rax, [rcx]
0x180012f35  mov     ebx, edx
0x180012f37  mov     rdi, rcx
0x180012f3a  mov     rax, [rax+8]
0x180012f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f43  test    ebx, ebx
0x180012f45  jz      short loc_180012F90
0x180012f47  lea     rax, [rsp+38h+ThreadId]
0x180012f4c  xor     ebx, ebx
0x180012f4e  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180012f53  lea     r8, ?_ThreadProc@CDropOperation@@CAKPEAX@Z; lpStartAddress
0x180012f5a  mov     r9, rdi; lpParameter
0x180012f5d  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180012f61  xor     edx, edx; dwStackSize
0x180012f63  mov     [rsp+38h+ThreadId], ebx
0x180012f67  xor     ecx, ecx; lpThreadAttributes
0x180012f69  call    cs:__imp_CreateThread
0x180012f6f  test    rax, rax
0x180012f72  jz      short loc_180012F7F
0x180012f74  mov     rcx, rax; hObject
0x180012f77  call    cs:__imp_CloseHandle
0x180012f7d  jmp     short loc_180012F9A
0x180012f7f  mov     rax, [rdi]
0x180012f82  mov     rcx, rdi
0x180012f85  mov     rax, [rax+10h]
0x180012f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f8e  jmp     short loc_180012F9A
0x180012f90  mov     rcx, rdi; this
0x180012f93  call    ?_ThreadProcCB@CDropOperation@@IEAAJXZ; CDropOperation::_ThreadProcCB(void)
0x180012f98  mov     ebx, eax
0x180012f9a  mov     eax, ebx
0x180012f9c  mov     rbx, [rsp+38h+arg_0]
0x180012fa1  add     rsp, 30h
0x180012fa5  pop     rdi
0x180012fa6  retn
```
