# ShellProcess::CreateIoPipes(void *,ushort const *,ushort const *,ushort const *)

- ea: `0x1802e35dc`
- end: `0x1802e3933`
- name: `?CreateIoPipes@ShellProcess@@QEAAJPEAXPEBG11@Z`
- size: `855`
- prototype: `__int64 __fastcall(void **this, HANDLE hSourceHandle, LPCWSTR lpFileName, LPCWSTR, LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800da60c`

## callees

- `0x1800793cc`
- `0x1800daa38`
- `0x1802e3498`
- `0x1802e35dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802e38c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802e38c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e38f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e3907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e38f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e3907`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3632`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e375b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e37b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e37c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3877`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3632`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e375b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e37b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e37c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802e3877`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802e365c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802e37f3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802e38a4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802e365c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802e37f3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802e38a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802e36a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802e36f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802e3845`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802e36a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802e36f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802e3845`

## string_xrefs

- `0x1802e3710`: `.shell: Unable to open %s\n`
- `0x1802e36c1`: `.shell: Unable to create %s\n`
- `0x1802e373d`: `.shell: Unable to create stdin pipe.\n`
- `0x1802e37ab`: `.shell: Unable to create stdout pipe.\n`

## pseudocode

```c
signed int __fastcall ShellProcess::CreateIoPipes(
        void **this,
        HANDLE hSourceHandle,
        LPCWSTR lpFileName,
        LPCWSTR a4,
        LPCWSTR lpFileNamea)
{
  HANDLE *v7; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v11; // rax
  BOOL v12; // eax
  unsigned int v13; // r9d
  void **v14; // r14
  HANDLE v15; // rax
  LPCWSTR v16; // rdx
  HANDLE v17; // rax
  HANDLE v18; // rax
  void *v19; // rdi
  void *v20; // rbx
  HANDLE v21; // rax
  HANDLE v22; // rax
  void *v23; // rdi
  void *v24; // rbx
  HANDLE v25; // rax
  void **v26; // r15
  HANDLE v27; // rax
  HANDLE v28; // rax
  void *v29; // rdi
  void *v30; // rbx
  HANDLE v31; // rax
  HANDLE EventW; // rax
  signed int result; // eax
  BOOL bInheritHandle; // [rsp+28h] [rbp-70h]
  BOOL bInheritHandlea; // [rsp+28h] [rbp-70h]
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-58h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v7 = this + 2;
  if ( hSourceHandle )
  {
    CurrentProcess = GetCurrentProcess();
    v11 = GetCurrentProcess();
    v12 = DuplicateHandle(v11, hSourceHandle, CurrentProcess, v7, 0, 1, 3u);
    goto LABEL_3;
  }
  if ( !lpFileName )
  {
    if ( !ShellProcess::CreateAsyncPipePair(this + 2, this, &SecurityAttributes, (unsigned int)a4, 0, bInheritHandle) )
    {
      ErrOut(L".shell: Unable to create stdin pipe.\n");
      goto LABEL_27;
    }
    v18 = GetCurrentProcess();
    v19 = *this;
    v20 = v18;
    v21 = GetCurrentProcess();
    v12 = DuplicateHandle(v21, v19, v20, this, 0, 0, 3u);
LABEL_3:
    if ( !v12 )
    {
      ErrOut(L".shell: Unable to duplicate stdin handle.\n");
      goto LABEL_27;
    }
    goto LABEL_4;
  }
  v17 = CreateFileW(lpFileName, 0x80000000, 1u, &SecurityAttributes, 3u, 0x80u, 0);
  *v7 = v17;
  if ( v17 == (HANDLE)-1LL )
  {
    *v7 = 0;
    ErrOut(L".shell: Unable to open %s\n", lpFileName);
    goto LABEL_27;
  }
LABEL_4:
  v14 = this + 3;
  if ( a4 )
  {
    v15 = CreateFileW(a4, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
    *v14 = v15;
    if ( v15 == (HANDLE)-1LL )
    {
      *v14 = 0;
      v16 = a4;
LABEL_7:
      ErrOut(L".shell: Unable to create %s\n", v16);
      goto LABEL_27;
    }
  }
  else
  {
    if ( !ShellProcess::CreateAsyncPipePair(this + 1, this + 3, &SecurityAttributes, v13, 0x40000000u, bInheritHandlea) )
    {
      ErrOut(L".shell: Unable to create stdout pipe.\n");
      goto LABEL_27;
    }
    v22 = GetCurrentProcess();
    v23 = this[1];
    v24 = v22;
    v25 = GetCurrentProcess();
    if ( !DuplicateHandle(v25, v23, v24, this + 1, 0, 0, 3u) )
    {
      ErrOut(L".shell: Unable to duplicate local stdout handle.\n");
      goto LABEL_27;
    }
  }
  v26 = this + 4;
  if ( lpFileNamea )
  {
    v27 = CreateFileW(lpFileNamea, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
    *v26 = v27;
    if ( v27 == (HANDLE)-1LL )
    {
      *v26 = 0;
      v16 = lpFileNamea;
      goto LABEL_7;
    }
  }
  else
  {
    v28 = GetCurrentProcess();
    v29 = *v14;
    v30 = v28;
    v31 = GetCurrentProcess();
    if ( !DuplicateHandle(v31, v29, v30, this + 4, 0, 1, 2u) )
    {
      ErrOut(L".shell: Unable to duplicate stdout handle for stderr.\n");
      goto LABEL_27;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  this[5] = EventW;
  if ( EventW )
    return 0;
  ErrOut(L".shell: Unable to allocate event.\n");
LABEL_27:
  ShellProcess::Close((ShellProcess *)this);
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1802e35dc  push    rbx
0x1802e35de  push    rbp
0x1802e35df  push    rsi
0x1802e35e0  push    rdi
0x1802e35e1  push    r12
0x1802e35e3  push    r14
0x1802e35e5  push    r15
0x1802e35e7  sub     rsp, 60h
0x1802e35eb  xor     r12d, r12d
0x1802e35ee  mov     qword ptr [rsp+98h+SecurityAttributes.nLength], 18h
0x1802e35f7  mov     qword ptr [rsp+98h+SecurityAttributes.bInheritHandle], 1
0x1802e3600  mov     rbp, r9
0x1802e3603  mov     [rsp+98h+SecurityAttributes.lpSecurityDescriptor], r12
0x1802e3608  mov     rbx, r8
0x1802e360b  lea     rdi, [rcx+10h]
0x1802e360f  mov     r14, rdx
0x1802e3612  lea     r15d, [r12+1]
0x1802e3617  mov     rsi, rcx
0x1802e361a  test    rdx, rdx
0x1802e361d  jz      loc_1802E36CA
0x1802e3623  call    cs:__imp_GetCurrentProcess
0x1802e362a  nop     dword ptr [rax+rax+00h]
0x1802e362f  mov     rbx, rax
0x1802e3632  call    cs:__imp_GetCurrentProcess
0x1802e3639  nop     dword ptr [rax+rax+00h]
0x1802e363e  mov     [rsp+98h+dwOptions], 3; dwOptions
0x1802e3646  mov     r9, rdi; lpTargetHandle
0x1802e3649  mov     [rsp+98h+bInheritHandle], r15d; unsigned int
0x1802e364e  mov     rdx, r14; hSourceHandle
0x1802e3651  mov     r8, rbx; hTargetProcessHandle
0x1802e3654  mov     [rsp+98h+dwDesiredAccess], r12d; dwDesiredAccess
0x1802e3659  mov     rcx, rax; hSourceProcessHandle
0x1802e365c  call    cs:__imp_DuplicateHandle
0x1802e3663  nop     dword ptr [rax+rax+00h]
0x1802e3668  test    eax, eax
0x1802e366a  jz      loc_1802E377F
0x1802e3670  lea     r14, [rsi+18h]
0x1802e3674  test    rbp, rbp
0x1802e3677  jz      loc_1802E378B
0x1802e367d  mov     qword ptr [rsp+98h+dwOptions], r12; hTemplateFile
0x1802e3682  lea     r9, [rsp+98h+SecurityAttributes]; lpSecurityAttributes
0x1802e3687  mov     [rsp+98h+bInheritHandle], 80h; dwFlagsAndAttributes
0x1802e368f  xor     r8d, r8d; dwShareMode
0x1802e3692  mov     edx, 40000000h; dwDesiredAccess
0x1802e3697  mov     [rsp+98h+dwDesiredAccess], 2; dwCreationDisposition
0x1802e369f  mov     rcx, rbp; lpFileName
0x1802e36a2  call    cs:__imp_CreateFileW
0x1802e36a9  nop     dword ptr [rax+rax+00h]
0x1802e36ae  mov     [r14], rax
0x1802e36b1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802e36b5  jnz     loc_1802E380F
0x1802e36bb  mov     [r14], r12
0x1802e36be  mov     rdx, rbp
0x1802e36c1  lea     rcx, aShellUnableToC_1; ".shell: Unable to create %s\n"
0x1802e36c8  jmp     short loc_1802E371A
0x1802e36ca  test    rbx, rbx
0x1802e36cd  jz      short loc_1802E3724
0x1802e36cf  mov     qword ptr [rsp+98h+dwOptions], r12; hTemplateFile
0x1802e36d4  lea     r9, [rsp+98h+SecurityAttributes]; lpSecurityAttributes
0x1802e36d9  mov     [rsp+98h+bInheritHandle], 80h; dwFlagsAndAttributes
0x1802e36e1  mov     r8d, r15d; dwShareMode
0x1802e36e4  mov     edx, 80000000h; dwDesiredAccess
0x1802e36e9  mov     [rsp+98h+dwDesiredAccess], 3; dwCreationDisposition
0x1802e36f1  mov     rcx, rbx; lpFileName
0x1802e36f4  call    cs:__imp_CreateFileW
0x1802e36fb  nop     dword ptr [rax+rax+00h]
0x1802e3700  mov     [rdi], rax
0x1802e3703  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802e3707  jnz     loc_1802E3670
0x1802e370d  mov     [rdi], r12
0x1802e3710  lea     rcx, aShellUnableToO; ".shell: Unable to open %s\n"
0x1802e3717  mov     rdx, rbx
0x1802e371a  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1802e371f  jmp     loc_1802E38E8
0x1802e3724  lea     r8, [rsp+98h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x1802e3729  mov     [rsp+98h+dwDesiredAccess], r12d; unsigned int
0x1802e372e  mov     rdx, rsi; void **
0x1802e3731  mov     rcx, rdi; void **
0x1802e3734  call    ?CreateAsyncPipePair@ShellProcess@@SAHPEAPEAX0PEAU_SECURITY_ATTRIBUTES@@KKK@Z; ShellProcess::CreateAsyncPipePair(void * *,void * *,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong)
0x1802e3739  test    eax, eax
0x1802e373b  jnz     short loc_1802E3749
0x1802e373d  lea     rcx, aShellUnableToC_0; ".shell: Unable to create stdin pipe.\n"
0x1802e3744  jmp     loc_1802E38E3
0x1802e3749  call    cs:__imp_GetCurrentProcess
0x1802e3750  nop     dword ptr [rax+rax+00h]
0x1802e3755  mov     rdi, [rsi]
0x1802e3758  mov     rbx, rax
0x1802e375b  call    cs:__imp_GetCurrentProcess
0x1802e3762  nop     dword ptr [rax+rax+00h]
0x1802e3767  mov     [rsp+98h+dwOptions], 3
0x1802e376f  mov     r9, rsi
0x1802e3772  mov     [rsp+98h+bInheritHandle], r12d
0x1802e3777  mov     rdx, rdi
0x1802e377a  jmp     loc_1802E3651
0x1802e377f  lea     rcx, aShellUnableToD_1; ".shell: Unable to duplicate stdin handl"...
0x1802e3786  jmp     loc_1802E38E3
0x1802e378b  lea     r15, [rsi+8]
0x1802e378f  mov     [rsp+98h+dwDesiredAccess], 40000000h; unsigned int
0x1802e3797  mov     rcx, r15; void **
0x1802e379a  lea     r8, [rsp+98h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x1802e379f  mov     rdx, r14; void **
0x1802e37a2  call    ?CreateAsyncPipePair@ShellProcess@@SAHPEAPEAX0PEAU_SECURITY_ATTRIBUTES@@KKK@Z; ShellProcess::CreateAsyncPipePair(void * *,void * *,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong)
0x1802e37a7  test    eax, eax
0x1802e37a9  jnz     short loc_1802E37B7
0x1802e37ab  lea     rcx, aShellUnableToC_2; ".shell: Unable to create stdout pipe.\n"
0x1802e37b2  jmp     loc_1802E38E3
0x1802e37b7  call    cs:__imp_GetCurrentProcess
0x1802e37be  nop     dword ptr [rax+rax+00h]
0x1802e37c3  mov     rdi, [r15]
0x1802e37c6  mov     rbx, rax
0x1802e37c9  call    cs:__imp_GetCurrentProcess
0x1802e37d0  nop     dword ptr [rax+rax+00h]
0x1802e37d5  mov     [rsp+98h+dwOptions], 3; dwOptions
0x1802e37dd  mov     r9, r15; lpTargetHandle
0x1802e37e0  mov     rcx, rax; hSourceProcessHandle
0x1802e37e3  mov     [rsp+98h+bInheritHandle], r12d; bInheritHandle
0x1802e37e8  mov     r8, rbx; hTargetProcessHandle
0x1802e37eb  mov     [rsp+98h+dwDesiredAccess], r12d; dwDesiredAccess
0x1802e37f0  mov     rdx, rdi; hSourceHandle
0x1802e37f3  call    cs:__imp_DuplicateHandle
0x1802e37fa  nop     dword ptr [rax+rax+00h]
0x1802e37ff  test    eax, eax
0x1802e3801  jnz     short loc_1802E380F
0x1802e3803  lea     rcx, aShellUnableToD_0; ".shell: Unable to duplicate local stdou"...
0x1802e380a  jmp     loc_1802E38E3
0x1802e380f  mov     rbx, [rsp+98h+lpFileName]
0x1802e3817  lea     r15, [rsi+20h]
0x1802e381b  test    rbx, rbx
0x1802e381e  jz      short loc_1802E3865
0x1802e3820  mov     qword ptr [rsp+98h+dwOptions], r12; hTemplateFile
0x1802e3825  lea     r9, [rsp+98h+SecurityAttributes]; lpSecurityAttributes
0x1802e382a  mov     [rsp+98h+bInheritHandle], 80h; dwFlagsAndAttributes
0x1802e3832  xor     r8d, r8d; dwShareMode
0x1802e3835  mov     edx, 40000000h; dwDesiredAccess
0x1802e383a  mov     [rsp+98h+dwDesiredAccess], 2; dwCreationDisposition
0x1802e3842  mov     rcx, rbx; lpFileName
0x1802e3845  call    cs:__imp_CreateFileW
0x1802e384c  nop     dword ptr [rax+rax+00h]
0x1802e3851  mov     [r15], rax
0x1802e3854  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802e3858  jnz     short loc_1802E38BD
0x1802e385a  mov     [r15], r12
0x1802e385d  mov     rdx, rbx
0x1802e3860  jmp     loc_1802E36C1
0x1802e3865  call    cs:__imp_GetCurrentProcess
0x1802e386c  nop     dword ptr [rax+rax+00h]
0x1802e3871  mov     rdi, [r14]
0x1802e3874  mov     rbx, rax
0x1802e3877  call    cs:__imp_GetCurrentProcess
0x1802e387e  nop     dword ptr [rax+rax+00h]
0x1802e3883  mov     [rsp+98h+dwOptions], 2; dwOptions
0x1802e388b  mov     r9, r15; lpTargetHandle
0x1802e388e  mov     rcx, rax; hSourceProcessHandle
0x1802e3891  mov     [rsp+98h+bInheritHandle], 1; bInheritHandle
0x1802e3899  mov     r8, rbx; hTargetProcessHandle
0x1802e389c  mov     [rsp+98h+dwDesiredAccess], r12d; dwDesiredAccess
0x1802e38a1  mov     rdx, rdi; hSourceHandle
0x1802e38a4  call    cs:__imp_DuplicateHandle
0x1802e38ab  nop     dword ptr [rax+rax+00h]
0x1802e38b0  test    eax, eax
0x1802e38b2  jnz     short loc_1802E38BD
0x1802e38b4  lea     rcx, aShellUnableToD; ".shell: Unable to duplicate stdout hand"...
0x1802e38bb  jmp     short loc_1802E38E3
0x1802e38bd  xor     r9d, r9d; lpName
0x1802e38c0  xor     r8d, r8d; bInitialState
0x1802e38c3  xor     edx, edx; bManualReset
0x1802e38c5  xor     ecx, ecx; lpEventAttributes
0x1802e38c7  call    cs:__imp_CreateEventW
0x1802e38ce  nop     dword ptr [rax+rax+00h]
0x1802e38d3  mov     [rsi+28h], rax
0x1802e38d7  test    rax, rax
0x1802e38da  jnz     short loc_1802E3921
0x1802e38dc  lea     rcx, aShellUnableToA; ".shell: Unable to allocate event.\n"
0x1802e38e3  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1802e38e8  mov     rcx, rsi; this
0x1802e38eb  call    ?Close@ShellProcess@@QEAAXXZ; ShellProcess::Close(void)
0x1802e38f0  call    cs:__imp_GetLastError
0x1802e38f7  nop     dword ptr [rax+rax+00h]
0x1802e38fc  test    eax, eax
0x1802e38fe  jnz     short loc_1802E3907
0x1802e3900  mov     eax, 80004005h
0x1802e3905  jmp     short loc_1802E3923
0x1802e3907  call    cs:__imp_GetLastError
0x1802e390e  nop     dword ptr [rax+rax+00h]
0x1802e3913  test    eax, eax
0x1802e3915  jle     short loc_1802E3923
0x1802e3917  movzx   eax, ax
0x1802e391a  or      eax, 80070000h
0x1802e391f  jmp     short loc_1802E3923
0x1802e3921  xor     eax, eax
0x1802e3923  add     rsp, 60h
0x1802e3927  pop     r15
0x1802e3929  pop     r14
0x1802e392b  pop     r12
0x1802e392d  pop     rdi
0x1802e392e  pop     rsi
0x1802e392f  pop     rbp
0x1802e3930  pop     rbx
0x1802e3931  retn
```
