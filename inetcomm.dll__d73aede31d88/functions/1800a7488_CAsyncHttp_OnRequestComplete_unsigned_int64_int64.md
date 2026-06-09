# CAsyncHttp::OnRequestComplete(unsigned __int64,__int64)

- ea: `0x1800a7488`
- end: `0x1800a754f`
- name: `?OnRequestComplete@CAsyncHttp@@AEAA_J_K_J@Z`
- size: `199`
- prototype: `__int64 __fastcall(CAsyncHttp *__hidden this, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a7120`

## callees

- `0x1800a6744`
- `0x1800a7488`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800a7519`
- `KERNEL32!WaitForSingleObject` at `0x1800a7519`
- `KERNEL32!CloseHandle` at `0x1800a7522`
- `KERNEL32!CloseHandle` at `0x1800a7522`
- `KERNEL32!SetEvent` at `0x1800a750d`
- `KERNEL32!SetEvent` at `0x1800a750d`
- `KERNEL32!OpenThread` at `0x1800a74db`
- `KERNEL32!OpenThread` at `0x1800a74db`
- `KERNEL32!GetExitCodeThread` at `0x1800a74f9`
- `KERNEL32!GetExitCodeThread` at `0x1800a74f9`

## pseudocode

```c
__int64 __fastcall CAsyncHttp::OnRequestComplete(CAsyncHttp *this, int a2, __int64 a3)
{
  HANDLE v4; // rax
  void *v5; // rdi
  DWORD ExitCode; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 )
  {
    *((_DWORD *)this + 29) = a2;
    *(_OWORD *)((char *)this + 2728) = *(_OWORD *)a3;
    *(_OWORD *)((char *)this + 2744) = *(_OWORD *)(a3 + 16);
    *((_QWORD *)this + 345) = *(_QWORD *)(a3 + 32);
  }
  else
  {
    *((_QWORD *)this + 347) = a3;
    *((_DWORD *)this + 29) = 0;
  }
  v4 = OpenThread(0x1FFFFFu, 0, *((_DWORD *)this + 698));
  v5 = v4;
  if ( v4 )
  {
    ExitCode = 0;
    GetExitCodeThread(v4, &ExitCode);
    if ( ExitCode == 259 )
    {
      SetEvent(*((HANDLE *)this + 12));
      WaitForSingleObject(v5, 0xFFFFFFFF);
    }
    CloseHandle(v5);
  }
  *((_DWORD *)this + 698) = 0;
  CAsyncHttp::ChangeState(this, 9, 9);
  return 0;
}

```

## disassembly

```asm
0x1800a7488  mov     [rsp+arg_8], rbx
0x1800a748d  push    rdi
0x1800a748e  sub     rsp, 20h
0x1800a7492  mov     rbx, rcx
0x1800a7495  test    edx, edx
0x1800a7497  jnz     short loc_1800A74A5
0x1800a7499  mov     [rcx+0AD8h], r8
0x1800a74a0  mov     [rcx+74h], edx
0x1800a74a3  jmp     short loc_1800A74CD
0x1800a74a5  mov     [rcx+74h], edx
0x1800a74a8  movups  xmm0, xmmword ptr [r8]
0x1800a74ac  movups  xmmword ptr [rcx+0AA8h], xmm0
0x1800a74b3  movups  xmm1, xmmword ptr [r8+10h]
0x1800a74b8  movups  xmmword ptr [rcx+0AB8h], xmm1
0x1800a74bf  movsd   xmm0, qword ptr [r8+20h]
0x1800a74c5  movsd   qword ptr [rcx+0AC8h], xmm0
0x1800a74cd  mov     r8d, [rcx+0AE8h]; dwThreadId
0x1800a74d4  xor     edx, edx; bInheritHandle
0x1800a74d6  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800a74db  call    cs:__imp_OpenThread
0x1800a74e1  mov     rdi, rax
0x1800a74e4  test    rax, rax
0x1800a74e7  jz      short loc_1800A7528
0x1800a74e9  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x1800a74ee  mov     [rsp+28h+ExitCode], 0
0x1800a74f6  mov     rcx, rax; hThread
0x1800a74f9  call    cs:__imp_GetExitCodeThread
0x1800a74ff  cmp     [rsp+28h+ExitCode], 103h
0x1800a7507  jnz     short loc_1800A751F
0x1800a7509  mov     rcx, [rbx+60h]; hEvent
0x1800a750d  call    cs:__imp_SetEvent
0x1800a7513  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a7516  mov     rcx, rdi; hHandle
0x1800a7519  call    cs:__imp_WaitForSingleObject
0x1800a751f  mov     rcx, rdi; hObject
0x1800a7522  call    cs:__imp_CloseHandle
0x1800a7528  mov     edx, 9
0x1800a752d  mov     dword ptr [rbx+0AE8h], 0
0x1800a7537  mov     r8d, edx
0x1800a753a  mov     rcx, rbx
0x1800a753d  call    ?ChangeState@CAsyncHttp@@AEAAXW4ASYNCHTTP_STATE@@W4ASYNCHTTP_EVENT@@@Z; CAsyncHttp::ChangeState(ASYNCHTTP_STATE,ASYNCHTTP_EVENT)
0x1800a7542  mov     rbx, [rsp+28h+arg_8]
0x1800a7547  xor     eax, eax
0x1800a7549  add     rsp, 20h
0x1800a754d  pop     rdi
0x1800a754e  retn
```
