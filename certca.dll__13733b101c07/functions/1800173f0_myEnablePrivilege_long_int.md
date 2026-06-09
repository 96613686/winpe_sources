# myEnablePrivilege(long,int)

- ea: `0x1800173f0`
- end: `0x18001756a`
- name: `?myEnablePrivilege@@YAJJH@Z`
- size: `378`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008400`
- `0x180012450`
- `0x1800173b8`
- `0x1800173f0`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001742f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001742f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017474`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017474`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001748c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001748c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800174b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800174b1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001750a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001750a`

## pseudocode

```c
__int64 __fastcall myEnablePrivilege(int a1, int a2)
{
  LUID v3; // r14
  HANDLE CurrentThread; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  HANDLE v11; // [rsp+38h] [rbp-28h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  v3 = (LUID)a1;
  NewState = 0;
  v11 = 0;
  TokenHandle = 0;
  NewState.PrivilegeCount = 1;
  CurrentThread = GetCurrentThread();
  CertSrv::CAutoPtr<void *,&int CloseHandle(void *),0>::Cleanup(&v11);
  v11 = CurrentThread;
  if ( !CurrentThread )
  {
    v5 = myHLastError();
    v6 = v5;
    if ( v5 )
    {
      v7 = 29753769;
LABEL_4:
      CSPrintErrorLineFile(v7, v5);
      goto LABEL_17;
    }
  }
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
  {
    v5 = myHLastError();
    v6 = v5;
    if ( v5 != -2147023888 )
    {
      v7 = 31916457;
      goto LABEL_4;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !CurrentProcess )
    {
      v5 = myHLastError();
      v6 = v5;
      v7 = 30933417;
      goto LABEL_4;
    }
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      v5 = myHLastError();
      v6 = v5;
      v7 = 31457705;
      goto LABEL_4;
    }
  }
  NewState.Privileges[0].Luid = v3;
  NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
  {
    v5 = myHLastError();
    v6 = v5;
    if ( !v5 )
      goto LABEL_17;
    v7 = 32899497;
    goto LABEL_4;
  }
  v6 = myHLastError();
  if ( v6 == -2147023596 )
    v6 = -2147024891;
LABEL_17:
  CertSrv::CAutoPtr<void *,&int CloseHandle(void *),0>::Cleanup(&TokenHandle);
  CertSrv::CAutoPtr<void *,&int CloseHandle(void *),0>::Cleanup(&v11);
  return v6;
}

```

## disassembly

```asm
0x1800173f0  push    rbp
0x1800173f2  push    rbx
0x1800173f3  push    rsi
0x1800173f4  push    rdi
0x1800173f5  push    r14
0x1800173f7  mov     rbp, rsp
0x1800173fa  sub     rsp, 60h
0x1800173fe  mov     rax, cs:__security_cookie
0x180017405  xor     rax, rsp
0x180017408  mov     [rbp+var_10], rax
0x18001740c  mov     esi, edx
0x18001740e  movsxd  r14, ecx
0x180017411  xorps   xmm0, xmm0
0x180017414  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180017418  mov     [rbp+var_28], 0
0x180017420  mov     [rbp+TokenHandle], 0
0x180017428  mov     [rbp+NewState.PrivilegeCount], 1
0x18001742f  call    cs:__imp_GetCurrentThread
0x180017435  mov     rdi, rax
0x180017438  lea     rcx, [rbp+var_28]
0x18001743c  call    ?Cleanup@?$CAutoPtr@PEAX$1?CloseHandle@@YAHPEAX@Z$0A@@CertSrv@@QEAAXXZ; CertSrv::CAutoPtr<void *,&CloseHandle(void *),0>::Cleanup(void)
0x180017441  mov     [rbp+var_28], rdi
0x180017445  test    rdi, rdi
0x180017448  jnz     short loc_180017466
0x18001744a  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001744f  mov     ebx, eax
0x180017451  test    eax, eax
0x180017453  jz      short loc_180017466
0x180017455  mov     ecx, 1C601A9h; unsigned int
0x18001745a  mov     edx, eax; int
0x18001745c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017461  jmp     loc_18001753E
0x180017466  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001746a  xor     r8d, r8d; OpenAsSelf
0x18001746d  lea     edx, [r8+28h]; DesiredAccess
0x180017471  mov     rcx, rdi; ThreadHandle
0x180017474  call    cs:__imp_OpenThreadToken
0x18001747a  test    eax, eax
0x18001747c  jnz     short loc_1800174D0
0x18001747e  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017483  mov     ebx, eax
0x180017485  cmp     eax, 800703F0h
0x18001748a  jnz     short loc_1800174C9
0x18001748c  call    cs:__imp_GetCurrentProcess
0x180017492  test    rax, rax
0x180017495  jnz     short loc_1800174A5
0x180017497  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001749c  mov     ebx, eax
0x18001749e  mov     ecx, 1D801A9h
0x1800174a3  jmp     short loc_18001745A
0x1800174a5  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800174a9  mov     edx, 28h ; '('; DesiredAccess
0x1800174ae  mov     rcx, rax; ProcessHandle
0x1800174b1  call    cs:__imp_OpenProcessToken
0x1800174b7  test    eax, eax
0x1800174b9  jnz     short loc_1800174D0
0x1800174bb  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800174c0  mov     ebx, eax
0x1800174c2  mov     ecx, 1E001A9h
0x1800174c7  jmp     short loc_18001745A
0x1800174c9  mov     ecx, 1E701A9h
0x1800174ce  jmp     short loc_18001745A
0x1800174d0  mov     rcx, r14
0x1800174d3  shr     rcx, 20h
0x1800174d7  mov     [rbp+NewState.Privileges.Luid.LowPart], r14d
0x1800174db  mov     [rbp+NewState.Privileges.Luid.HighPart], ecx
0x1800174de  neg     esi
0x1800174e0  sbb     eax, eax
0x1800174e2  and     eax, 2
0x1800174e5  mov     [rbp+NewState.Privileges.Attributes], eax
0x1800174e8  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x1800174f1  mov     [rsp+60h+PreviousState], 0; PreviousState
0x1800174fa  mov     r9d, 10h; BufferLength
0x180017500  lea     r8, [rbp+NewState]; NewState
0x180017504  xor     edx, edx; DisableAllPrivileges
0x180017506  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001750a  call    cs:__imp_AdjustTokenPrivileges
0x180017510  test    eax, eax
0x180017512  jnz     short loc_180017529
0x180017514  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017519  mov     ebx, eax
0x18001751b  test    eax, eax
0x18001751d  jz      short loc_18001753E
0x18001751f  mov     ecx, 1F601A9h
0x180017524  jmp     loc_18001745A
0x180017529  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001752e  mov     ebx, eax
0x180017530  mov     eax, 80070005h
0x180017535  cmp     ebx, 80070514h
0x18001753b  cmovz   ebx, eax
0x18001753e  lea     rcx, [rbp+TokenHandle]
0x180017542  call    ?Cleanup@?$CAutoPtr@PEAX$1?CloseHandle@@YAHPEAX@Z$0A@@CertSrv@@QEAAXXZ; CertSrv::CAutoPtr<void *,&CloseHandle(void *),0>::Cleanup(void)
0x180017547  nop
0x180017548  lea     rcx, [rbp+var_28]
0x18001754c  call    ?Cleanup@?$CAutoPtr@PEAX$1?CloseHandle@@YAHPEAX@Z$0A@@CertSrv@@QEAAXXZ; CertSrv::CAutoPtr<void *,&CloseHandle(void *),0>::Cleanup(void)
0x180017551  mov     eax, ebx
0x180017553  mov     rcx, [rbp+var_10]
0x180017557  xor     rcx, rsp; StackCookie
0x18001755a  call    __security_check_cookie
0x18001755f  add     rsp, 60h
0x180017563  pop     r14
0x180017565  pop     rdi
0x180017566  pop     rsi
0x180017567  pop     rbx
0x180017568  pop     rbp
0x180017569  retn
```
