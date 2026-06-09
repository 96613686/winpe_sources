# StartAddress

- ea: `0x1400c4870`
- end: `0x1400c4a28`
- name: `StartAddress`
- size: `440`
- prototype: `__int64 __fastcall(_BYTE *Parameter)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x1400430c4`
- `0x14005e050`
- `0x140087e00`
- `0x14008a550`
- `0x14008d6d0`
- `0x1400c4870`
- `0x1400ced40`
- `0x1400d0020`
- `0x1400d0090`
- `0x1400d0570`
- `0x1400d1380`
- `0x1400f3a00`
- `0x1400f3a10`
- `0x1400f3a80`
- `0x1400f3b00`
- `0x14012fc90`
- `0x140160e00`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x1400c48ed`
- `KERNEL32!DuplicateHandle` at `0x1400c48ed`
- `KERNEL32!GetCurrentProcess` at `0x1400c48bd`
- `KERNEL32!GetCurrentProcess` at `0x1400c48cc`
- `KERNEL32!GetCurrentProcess` at `0x1400c48b6`
- `KERNEL32!GetCurrentThread` at `0x1400c48c3`
- `KERNEL32!GetCurrentThread` at `0x1400c4994`
- `KERNEL32!GetCurrentThread` at `0x1400c48c3`
- `KERNEL32!GetCurrentThread` at `0x1400c4994`
- `KERNEL32!GetCurrentThreadId` at `0x1400c4930`
- `KERNEL32!GetCurrentThreadId` at `0x1400c4a03`
- `KERNEL32!GetCurrentThreadId` at `0x1400c4930`
- `KERNEL32!GetCurrentThreadId` at `0x1400c4a03`
- `KERNEL32!GetThreadPriority` at `0x1400c499d`
- `KERNEL32!GetThreadPriority` at `0x1400c499d`

## pseudocode

```c
__int64 __fastcall StartAddress(_BYTE *Parameter)
{
  void (__fastcall ***v2)(_QWORD); // rsi
  HANDLE CurrentProcess; // r14
  HANDLE CurrentThread; // r15
  HANDLE v5; // rax
  BOOL v6; // ebx
  RTL_SRWLOCK *v7; // r14
  RTL_SRWLOCK *v8; // r15
  RTL_SRWLOCK *v9; // rax
  HANDLE v10; // rax
  __int64 v11; // rcx
  RTL_SRWLOCK *v13; // rsi
  __int64 v14; // [rsp+0h] [rbp-88h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h] BYREF
  HANDLE TargetHandle[9]; // [rsp+40h] [rbp-48h] BYREF

  v2 = *(void (__fastcall ****)(_QWORD))Parameter;
  if ( !Parameter[8] )
    sub_1400CED40();
  if ( *((_DWORD *)Parameter + 3) != 2 )
    ((void (*)(void))sub_1400D1380)();
  TargetHandle[0] = 0;
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v5 = GetCurrentProcess();
  v6 = DuplicateHandle(v5, CurrentThread, CurrentProcess, TargetHandle, 0, 0, 2u);
  v7 = (RTL_SRWLOCK *)sub_1400F3A10();
  sub_1400F3A00();
  sub_1400F3A80(v7);
  v15 = 0;
  if ( v6 )
  {
    sub_1400430C4(&v15, TargetHandle[0]);
    v8 = (RTL_SRWLOCK *)sub_1400D0020();
    GetCurrentThreadId();
    sub_1400D0090(v8);
  }
  if ( Parameter )
  {
    if ( (*(_QWORD *)Parameter & 0xFFFFFFFC00000000uLL) == qword_14038B548 )
      sub_14008A550();
    sub_14008D6D0(Parameter, 16);
  }
  (**v2)(v2);
  if ( v6 )
  {
    v13 = (RTL_SRWLOCK *)sub_1400D0020();
    GetCurrentThreadId();
    sub_1400D0570(v13);
  }
  v9 = (RTL_SRWLOCK *)sub_1400F3A10();
  sub_1400F3B00(v9);
  v10 = GetCurrentThread();
  if ( GetThreadPriority(v10) < 0 )
    goto LABEL_18;
  while ( 1 )
  {
    if ( v15 != 0 && (unsigned int)v15 < 0xFFFFFFF4 )
    {
      LOBYTE(v11) = v15 == 0;
      sub_140087E00(v11);
      sub_14005E050(v15);
    }
    if ( _security_cookie == ((unsigned __int64)&v14 ^ (unsigned __int64)TargetHandle[1]) )
      break;
LABEL_18:
    sub_1400D1380(2);
  }
  return 0;
}

```

## disassembly

```asm
0x1400c4870  push    r15
0x1400c4872  push    r14
0x1400c4874  push    r13
0x1400c4876  push    r12
0x1400c4878  push    rsi
0x1400c4879  push    rdi
0x1400c487a  push    rbx
0x1400c487b  sub     rsp, 50h
0x1400c487f  mov     rdi, rcx
0x1400c4882  mov     rax, cs:__security_cookie
0x1400c4889  xor     rax, rsp
0x1400c488c  mov     [rsp+88h+var_40], rax
0x1400c4891  mov     rsi, [rcx]
0x1400c4894  cmp     byte ptr [rcx+8], 0
0x1400c4898  jz      loc_1400C4A1E
0x1400c489e  mov     ecx, [rdi+0Ch]
0x1400c48a1  cmp     ecx, 2
0x1400c48a4  jz      short loc_1400C48AB
0x1400c48a6  call    sub_1400D1380
0x1400c48ab  xor     r12d, r12d
0x1400c48ae  lea     rbx, [rsp+88h+TargetHandle]
0x1400c48b3  mov     [rbx], r12
0x1400c48b6  mov     r13, cs:__imp_GetCurrentProcess
0x1400c48bd  call    r13 ; __imp_GetCurrentProcess
0x1400c48c0  mov     r14, rax
0x1400c48c3  call    cs:GetCurrentThread
0x1400c48c9  mov     r15, rax
0x1400c48cc  call    r13 ; __imp_GetCurrentProcess
0x1400c48cf  mov     [rsp+88h+bInheritHandle], r12d; bInheritHandle
0x1400c48d4  mov     [rsp+88h+dwDesiredAccess], r12d; dwDesiredAccess
0x1400c48d9  mov     [rsp+88h+dwOptions], 2; dwOptions
0x1400c48e1  mov     rcx, rax; hSourceProcessHandle
0x1400c48e4  mov     rdx, r15; hSourceHandle
0x1400c48e7  mov     r8, r14; hTargetProcessHandle
0x1400c48ea  mov     r9, rbx; lpTargetHandle
0x1400c48ed  call    cs:DuplicateHandle
0x1400c48f3  mov     ebx, eax
0x1400c48f5  call    sub_1400F3A10
0x1400c48fa  mov     r14, rax
0x1400c48fd  call    sub_1400F3A00
0x1400c4902  mov     rcx, r14; SRWLock
0x1400c4905  mov     rdx, rax
0x1400c4908  call    sub_1400F3A80
0x1400c490d  mov     [rsp+88h+var_50], r12
0x1400c4912  test    ebx, ebx
0x1400c4914  jz      short loc_1400C4944
0x1400c4916  mov     rdx, [rsp+88h+TargetHandle]
0x1400c491b  lea     r14, [rsp+88h+var_50]
0x1400c4920  mov     rcx, r14
0x1400c4923  call    sub_1400430C4
0x1400c4928  call    sub_1400D0020
0x1400c492d  mov     r15, rax
0x1400c4930  call    cs:__imp_GetCurrentThreadId
0x1400c4936  mov     rdx, [r14]
0x1400c4939  mov     rcx, r15; SRWLock
0x1400c493c  mov     r8d, eax
0x1400c493f  call    sub_1400D0090
0x1400c4944  test    rdi, rdi
0x1400c4947  jz      short loc_1400C4974
0x1400c4949  mov     rcx, [rdi]
0x1400c494c  mov     rax, 0FFFFFFFC00000000h
0x1400c4956  and     rax, rcx
0x1400c4959  cmp     rax, cs:qword_14038B548
0x1400c4960  jnz     short loc_1400C4967
0x1400c4962  call    sub_14008A550
0x1400c4967  mov     edx, 10h
0x1400c496c  mov     rcx, rdi
0x1400c496f  call    sub_14008D6D0
0x1400c4974  mov     rax, [rsi]
0x1400c4977  mov     rax, [rax]
0x1400c497a  mov     rcx, rsi
0x1400c497d  call    cs:__guard_dispatch_icall_fptr
0x1400c4983  test    ebx, ebx
0x1400c4985  jnz     short loc_1400C49FB
0x1400c4987  call    sub_1400F3A10
0x1400c498c  mov     rcx, rax; SRWLock
0x1400c498f  call    sub_1400F3B00
0x1400c4994  call    cs:GetCurrentThread
0x1400c499a  mov     rcx, rax; hThread
0x1400c499d  call    cs:GetThreadPriority
0x1400c49a3  test    eax, eax
0x1400c49a5  js      loc_140180717
0x1400c49ab  mov     rax, [rsp+88h+var_50]
0x1400c49b0  test    rax, rax
0x1400c49b3  setz    cl
0x1400c49b6  cmp     eax, 0FFFFFFF4h
0x1400c49b9  setnb   al
0x1400c49bc  or      al, cl
0x1400c49be  jz      short loc_1400C49EA
0x1400c49c0  mov     rax, [rsp+88h+var_40]
0x1400c49c5  xor     rax, rsp
0x1400c49c8  mov     rcx, cs:__security_cookie
0x1400c49cf  cmp     rcx, rax
0x1400c49d2  jnz     loc_14018070A
0x1400c49d8  xor     eax, eax
0x1400c49da  add     rsp, 50h
0x1400c49de  pop     rbx
0x1400c49df  pop     rdi
0x1400c49e0  pop     rsi
0x1400c49e1  pop     r12
0x1400c49e3  pop     r13
0x1400c49e5  pop     r14
0x1400c49e7  pop     r15
0x1400c49e9  retn
0x1400c49ea  call    sub_140087E00
0x1400c49ef  mov     rcx, [rsp+88h+var_50]
0x1400c49f4  call    sub_14005E050
0x1400c49f9  jmp     short loc_1400C49C0
0x1400c49fb  call    sub_1400D0020
0x1400c4a00  mov     rsi, rax
0x1400c4a03  call    cs:__imp_GetCurrentThreadId
0x1400c4a09  mov     rdx, [rsp+88h+var_50]
0x1400c4a0e  mov     rcx, rsi; SRWLock
0x1400c4a11  mov     r8d, eax
0x1400c4a14  call    sub_1400D0570
0x1400c4a19  jmp     loc_1400C4987
0x1400c4a1e  call    sub_1400CED40
0x1400c4a23  jmp     loc_1400C489E
0x14018070a  mov     rcx, [rsp+88h+var_40]
0x14018070f  xor     rcx, rsp; StackCookie
0x140180712  call    __security_check_cookie
0x140180717  mov     ecx, 2
0x14018071c  call    sub_1400D1380
0x140180721  jmp     loc_1400C49AB
```
