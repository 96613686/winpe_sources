# BaseFormatObjectAttributes

- ea: `0x1800715e0`
- end: `0x18007182a`
- name: `BaseFormatObjectAttributes`
- size: `586`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180070c40`
- `0x180071080`
- `0x1800711a4`
- `0x18008e220`
- `0x1800ce100`
- `0x1800f12a0`
- `0x18018b310`

## callees

- `0x1800715e0`
- `0x1800731a0`
- `0x1801a4010`

## import_xrefs

- `ntdll!NtClose` at `0x180071738`
- `ntdll!NtClose` at `0x18007174e`
- `ntdll!NtClose` at `0x18007180f`
- `ntdll!NtClose` at `0x180071738`
- `ntdll!NtClose` at `0x18007174e`
- `ntdll!NtClose` at `0x18007180f`
- `ntdll!NtOpenProcessToken` at `0x1800716c6`
- `ntdll!NtOpenProcessToken` at `0x1800716c6`
- `ntdll!NtOpenThreadToken` at `0x180071787`
- `ntdll!NtOpenThreadToken` at `0x180071787`
- `ntdll!NtSetInformationThread` at `0x1800717b6`
- `ntdll!NtSetInformationThread` at `0x1800717fe`
- `ntdll!NtSetInformationThread` at `0x1800717b6`
- `ntdll!NtSetInformationThread` at `0x1800717fe`

## pseudocode

```c
__int64 __fastcall BaseFormatObjectAttributes(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rbx
  __int64 v9; // r12
  int v10; // ebp
  __int64 v11; // r15
  void (__fastcall *v12)(__int64); // rax
  int NamedObjectDirectoryForToken; // r13d
  HANDLE v14; // rcx
  HANDLE v15; // [rsp+30h] [rbp-68h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-60h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-58h] BYREF
  _QWORD ThreadInformation[10]; // [rsp+48h] [rbp-50h] BYREF
  int v19; // [rsp+A8h] [rbp+10h]

  if ( a2 )
  {
    v9 = *(_QWORD *)(a2 + 8);
    v10 = *(_DWORD *)(a2 + 16) != 0 ? 2 : 0;
    if ( !a3 )
    {
      v11 = 0;
      goto LABEL_7;
    }
  }
  else
  {
    v7 = 0;
    if ( !a3 )
    {
LABEL_3:
      *a4 = v7;
      return 0;
    }
    v10 = 0;
    v9 = 0;
  }
  v11 = BaseNamedObjectDirectory;
  v15 = 0;
  TokenHandle = 0;
  ThreadInformation[0] = 0;
  Handle = 0;
  if ( BaseNamedObjectDirectory )
  {
LABEL_6:
    v10 |= 0x80u;
LABEL_7:
    v12 = (void (__fastcall *)(__int64))pfnAdjustObjectAttributesForPrivateNamespace;
    *(_DWORD *)a1 = 48;
    *(_QWORD *)(a1 + 8) = v11;
    *(_DWORD *)(a1 + 24) = v10;
    *(_QWORD *)(a1 + 16) = a3;
    *(_QWORD *)(a1 + 32) = v9;
    *(_QWORD *)(a1 + 40) = 0;
    if ( v12 )
      v12(a1);
    v7 = a1;
    goto LABEL_3;
  }
  v11 = 0;
  v19 = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    NamedObjectDirectoryForToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &v15);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_16;
    ThreadInformation[0] = 0;
    NamedObjectDirectoryForToken = NtSetInformationThread(
                                     (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                     ThreadImpersonationToken,
                                     ThreadInformation,
                                     8u);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_16;
    v19 = 1;
  }
  NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( NamedObjectDirectoryForToken >= 0 )
  {
    NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(TokenHandle, 0, 1, 15, &Handle);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&BaseNamedObjectDirectory, (signed __int64)Handle, 0) )
        Handle = 0;
      v11 = BaseNamedObjectDirectory;
    }
  }
LABEL_16:
  v14 = v15;
  if ( v15 )
  {
    if ( v19 )
    {
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v15, 8u);
      v14 = v15;
    }
    NtClose(v14);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( NamedObjectDirectoryForToken >= 0 )
    goto LABEL_6;
  return (unsigned int)NamedObjectDirectoryForToken;
}

```

## disassembly

```asm
0x1800715e0  push    rbx
0x1800715e2  push    rbp
0x1800715e3  push    rsi
0x1800715e4  push    rdi
0x1800715e5  push    r12
0x1800715e7  push    r13
0x1800715e9  push    r14
0x1800715eb  push    r15
0x1800715ed  sub     rsp, 58h
0x1800715f1  mov     rsi, r9
0x1800715f4  mov     rdi, r8
0x1800715f7  mov     r14, rcx
0x1800715fa  test    rdx, rdx
0x1800715fd  jnz     short loc_180071621
0x1800715ff  xor     ebx, ebx
0x180071601  test    r8, r8
0x180071604  jnz     loc_180071820
0x18007160a  mov     [rsi], rbx
0x18007160d  xor     eax, eax
0x18007160f  add     rsp, 58h
0x180071613  pop     r15
0x180071615  pop     r14
0x180071617  pop     r13
0x180071619  pop     r12
0x18007161b  pop     rdi
0x18007161c  pop     rsi
0x18007161d  pop     rbp
0x18007161e  pop     rbx
0x18007161f  retn
0x180071621  mov     eax, [rdx+10h]
0x180071624  mov     r12, [rdx+8]
0x180071628  neg     eax
0x18007162a  sbb     ebp, ebp
0x18007162c  xor     ebx, ebx
0x18007162e  and     ebp, 2
0x180071631  test    rdi, rdi
0x180071634  jz      loc_18007176B
0x18007163a  mov     r15, cs:BaseNamedObjectDirectory
0x180071641  mov     [rsp+98h+var_68], rbx
0x180071646  mov     [rsp+98h+TokenHandle], rbx
0x18007164b  mov     [rsp+98h+ThreadInformation], rbx
0x180071650  mov     [rsp+98h+Handle], rbx
0x180071655  test    r15, r15
0x180071658  jz      short loc_180071695
0x18007165a  bts     ebp, 7
0x18007165e  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x180071665  mov     dword ptr [r14], 30h ; '0'
0x18007166c  mov     [r14+8], r15
0x180071670  mov     [r14+18h], ebp
0x180071674  mov     [r14+10h], rdi
0x180071678  mov     [r14+20h], r12
0x18007167c  mov     [r14+28h], rbx
0x180071680  test    rax, rax
0x180071683  jz      short loc_18007168D
0x180071685  mov     rcx, r14
0x180071688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007168d  mov     rbx, r14
0x180071690  jmp     loc_18007160A
0x180071695  mov     rax, gs:30h
0x18007169e  mov     r15, rbx
0x1800716a1  mov     [rsp+98h+arg_8], ebx
0x1800716a8  cmp     dword ptr [rax+179Ch], 0
0x1800716af  jnz     loc_180071773
0x1800716b5  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x1800716ba  mov     edx, 8; DesiredAccess
0x1800716bf  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800716c6  call    cs:__imp_NtOpenProcessToken
0x1800716cd  nop     dword ptr [rax+rax+00h]
0x1800716d2  mov     r13d, eax
0x1800716d5  test    eax, eax
0x1800716d7  js      short loc_180071720
0x1800716d9  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x1800716de  lea     rax, [rsp+98h+Handle]
0x1800716e3  xor     edx, edx
0x1800716e5  mov     [rsp+98h+var_78], rax; __int64
0x1800716ea  mov     r9d, 0Fh
0x1800716f0  mov     r8d, 1
0x1800716f6  call    BasepGetNamedObjectDirectoryForToken
0x1800716fb  mov     r13d, eax
0x1800716fe  test    eax, eax
0x180071700  js      short loc_180071720
0x180071702  mov     rcx, [rsp+98h+Handle]
0x180071707  xor     eax, eax
0x180071709  lock cmpxchg cs:BaseNamedObjectDirectory, rcx
0x180071712  jnz     short loc_180071719
0x180071714  mov     [rsp+98h+Handle], rbx
0x180071719  mov     r15, cs:BaseNamedObjectDirectory
0x180071720  mov     rcx, [rsp+98h+var_68]
0x180071725  test    rcx, rcx
0x180071728  jnz     loc_1800717DD
0x18007172e  mov     rcx, [rsp+98h+TokenHandle]; Handle
0x180071733  test    rcx, rcx
0x180071736  jz      short loc_180071744
0x180071738  call    cs:__imp_NtClose
0x18007173f  nop     dword ptr [rax+rax+00h]
0x180071744  mov     rcx, [rsp+98h+Handle]; Handle
0x180071749  test    rcx, rcx
0x18007174c  jz      short loc_18007175A
0x18007174e  call    cs:__imp_NtClose
0x180071755  nop     dword ptr [rax+rax+00h]
0x18007175a  test    r13d, r13d
0x18007175d  jns     loc_18007165A
0x180071763  mov     eax, r13d
0x180071766  jmp     loc_18007160F
0x18007176b  mov     r15, rbx
0x18007176e  jmp     loc_18007165E
0x180071773  lea     r9, [rsp+98h+var_68]; TokenHandle
0x180071778  mov     r8b, 1; OpenAsSelf
0x18007177b  mov     edx, 4; DesiredAccess
0x180071780  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180071787  call    cs:__imp_NtOpenThreadToken
0x18007178e  nop     dword ptr [rax+rax+00h]
0x180071793  mov     r13d, eax
0x180071796  test    eax, eax
0x180071798  js      short loc_180071720
0x18007179a  mov     r9d, 8; ThreadInformationLength
0x1800717a0  mov     [rsp+98h+ThreadInformation], rbx
0x1800717a5  lea     r8, [rsp+98h+ThreadInformation]; ThreadInformation
0x1800717aa  mov     edx, 5; ThreadInformationClass
0x1800717af  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800717b6  call    cs:__imp_NtSetInformationThread
0x1800717bd  nop     dword ptr [rax+rax+00h]
0x1800717c2  mov     r13d, eax
0x1800717c5  test    eax, eax
0x1800717c7  js      loc_180071720
0x1800717cd  mov     [rsp+98h+arg_8], 1
0x1800717d8  jmp     loc_1800716B5
0x1800717dd  cmp     [rsp+98h+arg_8], 0
0x1800717e5  jz      short loc_18007180F
0x1800717e7  mov     r9d, 8; ThreadInformationLength
0x1800717ed  lea     r8, [rsp+98h+var_68]; ThreadInformation
0x1800717f2  mov     edx, 5; ThreadInformationClass
0x1800717f7  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800717fe  call    cs:__imp_NtSetInformationThread
0x180071805  nop     dword ptr [rax+rax+00h]
0x18007180a  mov     rcx, [rsp+98h+var_68]; Handle
0x18007180f  call    cs:__imp_NtClose
0x180071816  nop     dword ptr [rax+rax+00h]
0x18007181b  jmp     loc_18007172E
0x180071820  mov     ebp, ebx
0x180071822  mov     r12, rbx
0x180071825  jmp     loc_18007163A
```
