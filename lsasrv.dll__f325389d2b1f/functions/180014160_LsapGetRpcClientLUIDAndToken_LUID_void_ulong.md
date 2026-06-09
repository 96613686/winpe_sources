# LsapGetRpcClientLUIDAndToken(_LUID *,void * *,ulong)

- ea: `0x180014160`
- end: `0x1800143d8`
- name: `?LsapGetRpcClientLUIDAndToken@@YAJPEAU_LUID@@PEAPEAXK@Z`
- size: `632`
- prototype: `int(struct _LUID *, void **, unsigned int)`
- caller_count: `13`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011cdc`
- `0x180013b8c`
- `0x18001f7c8`
- `0x180022590`
- `0x180061e88`
- `0x180064628`
- `0x18008d958`
- `0x1800a11ec`
- `0x1800cb680`
- `0x18011c588`
- `0x18012a610`
- `0x18012a780`
- `0x18012a8b0`

## callees

- `0x180014160`
- `0x1800b86d0`
- `0x18012cf84`

## import_xrefs

- `ntdll!NtImpersonateAnonymousToken` at `0x180014337`
- `ntdll!NtImpersonateAnonymousToken` at `0x180014337`
- `ntdll!NtClose` at `0x18001421a`
- `ntdll!NtClose` at `0x18001421a`
- `ntdll!NtSetInformationThread` at `0x18001438a`
- `ntdll!NtSetInformationThread` at `0x18001438a`
- `ntdll!NtQueryInformationToken` at `0x1800142fa`
- `ntdll!NtQueryInformationToken` at `0x1800142fa`
- `ntdll!NtOpenThreadToken` at `0x1800142a4`
- `ntdll!NtOpenThreadToken` at `0x180014366`
- `ntdll!NtOpenThreadToken` at `0x1800142a4`
- `ntdll!NtOpenThreadToken` at `0x180014366`
- `RPCRT4!RpcRevertToSelf` at `0x1800142b2`
- `RPCRT4!RpcRevertToSelf` at `0x1800142b2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800141d3`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001425c`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800142c0`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800141d3`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001425c`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800142c0`
- `RPCRT4!RpcImpersonateClient` at `0x18001424e`
- `RPCRT4!RpcImpersonateClient` at `0x18001424e`
- `RPCRT4!I_RpcBindingInqClientTokenAttributes` at `0x1800141c5`
- `RPCRT4!I_RpcBindingInqClientTokenAttributes` at `0x1800141c5`

## pseudocode

```c
__int64 __fastcall LsapGetRpcClientLUIDAndToken(struct _LUID *a1, void **a2, unsigned int a3)
{
  RPC_STATUS v6; // eax
  NTSTATUS v7; // ebx
  RPC_STATUS v9; // eax
  int v10; // eax
  RPC_STATUS v11; // eax
  int DuplicatedGlobalProcessHandle; // eax
  LUID v13; // rax
  LUID AuthenticationId; // [rsp+30h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-21h] BYREF
  ULONG ReturnLength; // [rsp+40h] [rbp-19h] BYREF
  __int64 ThreadInformation; // [rsp+48h] [rbp-11h] BYREF
  _OWORD TokenInformation[3]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v19; // [rsp+80h] [rbp+27h]

  Handle = 0;
  ReturnLength = 0;
  v19 = 0;
  AuthenticationId = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( a2
    || (v6 = I_RpcBindingInqClientTokenAttributes(0, 0, &AuthenticationId, 0), v7 = I_RpcMapWin32Status(v6), v7 < 0) )
  {
    v9 = RpcImpersonateClient(0);
    v10 = I_RpcMapWin32Status(v9);
    v7 = v10;
    switch ( v10 )
    {
      case -1073610687:
        if ( !a2 )
        {
          AuthenticationId = (LUID)998LL;
          v7 = 0;
          goto LABEL_3;
        }
        v7 = NtImpersonateAnonymousToken((HANDLE)0xFFFFFFFFFFFFFFFELL);
        if ( v7 < 0 )
          goto LABEL_7;
        ThreadInformation = 0;
        v7 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, a3 | 0xA, 1u, &Handle);
        NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
        break;
      case -1073610726:
      case -1073610686:
        if ( !a2 )
        {
          v13 = LsapGlobalProcessTokenLuid;
          v7 = 0;
          goto LABEL_23;
        }
        DuplicatedGlobalProcessHandle = LsapGetDuplicatedGlobalProcessHandle(&Handle, a3);
LABEL_19:
        v7 = DuplicatedGlobalProcessHandle;
        break;
      case 0:
        v7 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, a3 | 0xA, 1u, &Handle);
        v11 = RpcRevertToSelf();
        DuplicatedGlobalProcessHandle = I_RpcMapWin32Status(v11);
        if ( v7 < 0 )
          goto LABEL_7;
        goto LABEL_19;
    }
    if ( v7 >= 0 )
    {
      v7 = NtQueryInformationToken(Handle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
      if ( v7 >= 0 )
      {
        v13 = (LUID)*((_QWORD *)&TokenInformation[0] + 1);
LABEL_23:
        AuthenticationId = v13;
        goto LABEL_3;
      }
    }
LABEL_7:
    if ( a1 )
      *a1 = 0;
    if ( a2 )
      *a2 = 0;
    goto LABEL_11;
  }
LABEL_3:
  if ( a1 )
    *a1 = AuthenticationId;
  if ( a2 )
  {
    *a2 = Handle;
    return (unsigned int)v7;
  }
LABEL_11:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014160  mov     [rsp-8+arg_18], rbx
0x180014165  push    rbp
0x180014166  push    rsi
0x180014167  push    rdi
0x180014168  push    r14
0x18001416a  push    r15
0x18001416c  lea     rbp, [rsp-37h]
0x180014171  sub     rsp, 90h
0x180014178  mov     rax, cs:__security_cookie
0x18001417f  xor     rax, rsp
0x180014182  mov     [rbp+57h+var_28], rax
0x180014186  xor     r15d, r15d
0x180014189  xorps   xmm0, xmm0
0x18001418c  xor     eax, eax
0x18001418e  mov     [rbp+57h+Handle], r15
0x180014192  mov     [rbp+57h+var_70], r15d
0x180014196  mov     r14d, r8d
0x180014199  mov     [rbp+57h+var_30], rax
0x18001419d  mov     rdi, rdx
0x1800141a0  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], r15
0x1800141a4  mov     rsi, rcx
0x1800141a7  movups  [rbp+57h+TokenInformation], xmm0
0x1800141ab  movups  [rbp+57h+var_50], xmm0
0x1800141af  movups  [rbp+57h+var_40], xmm0
0x1800141b3  test    rdx, rdx
0x1800141b6  jnz     loc_18001424C
0x1800141bc  xor     r9d, r9d; ModifiedId
0x1800141bf  lea     r8, [rbp+57h+AuthenticationId]; AuthenticationId
0x1800141c3  xor     ecx, ecx; Binding
0x1800141c5  call    cs:__imp_I_RpcBindingInqClientTokenAttributes
0x1800141cc  nop     dword ptr [rax+rax+00h]
0x1800141d1  mov     ecx, eax; Status
0x1800141d3  call    cs:__imp_I_RpcMapWin32Status
0x1800141da  nop     dword ptr [rax+rax+00h]
0x1800141df  mov     ebx, eax
0x1800141e1  test    eax, eax
0x1800141e3  js      short loc_18001424C
0x1800141e5  test    rsi, rsi
0x1800141e8  jz      short loc_1800141F1
0x1800141ea  mov     rax, qword ptr [rbp+57h+AuthenticationId.LowPart]
0x1800141ee  mov     [rsi], rax
0x1800141f1  test    rdi, rdi
0x1800141f4  jz      short loc_180014211
0x1800141f6  mov     rax, [rbp+57h+Handle]
0x1800141fa  mov     [rdi], rax
0x1800141fd  jmp     short loc_180014226
0x1800141ff  test    rsi, rsi
0x180014202  jnz     loc_18001431D
0x180014208  test    rdi, rdi
0x18001420b  jnz     loc_1800143D0
0x180014211  mov     rcx, [rbp+57h+Handle]; Handle
0x180014215  test    rcx, rcx
0x180014218  jz      short loc_180014226
0x18001421a  call    cs:__imp_NtClose
0x180014221  nop     dword ptr [rax+rax+00h]
0x180014226  mov     eax, ebx
0x180014228  mov     rcx, [rbp+57h+var_28]
0x18001422c  xor     rcx, rsp; StackCookie
0x18001422f  call    __security_check_cookie
0x180014234  mov     rbx, [rsp+0B0h+arg_18]
0x18001423c  add     rsp, 90h
0x180014243  pop     r15
0x180014245  pop     r14
0x180014247  pop     rdi
0x180014248  pop     rsi
0x180014249  pop     rbp
0x18001424a  retn
0x18001424c  xor     ecx, ecx; BindingHandle
0x18001424e  call    cs:__imp_RpcImpersonateClient
0x180014255  nop     dword ptr [rax+rax+00h]
0x18001425a  mov     ecx, eax; Status
0x18001425c  call    cs:__imp_I_RpcMapWin32Status
0x180014263  nop     dword ptr [rax+rax+00h]
0x180014268  mov     ebx, eax
0x18001426a  cmp     eax, 0C0020041h
0x18001426f  jz      loc_180014327
0x180014275  cmp     eax, 0C002001Ah
0x18001427a  jz      loc_18001439B
0x180014280  cmp     eax, 0C0020042h
0x180014285  jz      loc_18001439B
0x18001428b  test    eax, eax
0x18001428d  jnz     short loc_1800142D6
0x18001428f  or      r14d, 0Ah
0x180014293  lea     r9, [rbp+57h+Handle]; TokenHandle
0x180014297  mov     edx, r14d; DesiredAccess
0x18001429a  mov     r8b, 1; OpenAsSelf
0x18001429d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800142a4  call    cs:__imp_NtOpenThreadToken
0x1800142ab  nop     dword ptr [rax+rax+00h]
0x1800142b0  mov     ebx, eax
0x1800142b2  call    cs:__imp_RpcRevertToSelf
0x1800142b9  nop     dword ptr [rax+rax+00h]
0x1800142be  mov     ecx, eax; Status
0x1800142c0  call    cs:__imp_I_RpcMapWin32Status
0x1800142c7  nop     dword ptr [rax+rax+00h]
0x1800142cc  test    ebx, ebx
0x1800142ce  js      loc_1800141FF
0x1800142d4  mov     ebx, eax
0x1800142d6  test    ebx, ebx
0x1800142d8  js      loc_1800141FF
0x1800142de  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x1800142e2  lea     rax, [rbp+57h+var_70]
0x1800142e6  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800142ec  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800142f1  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800142f5  mov     edx, 0Ah; TokenInformationClass
0x1800142fa  call    cs:__imp_NtQueryInformationToken
0x180014301  nop     dword ptr [rax+rax+00h]
0x180014306  mov     ebx, eax
0x180014308  test    eax, eax
0x18001430a  js      loc_1800141FF
0x180014310  mov     rax, qword ptr [rbp+57h+TokenInformation+8]
0x180014314  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], rax
0x180014318  jmp     loc_1800141E5
0x18001431d  xor     eax, eax
0x18001431f  mov     [rsi], rax
0x180014322  jmp     loc_180014208
0x180014327  test    rdi, rdi
0x18001432a  jz      loc_1800143B1
0x180014330  mov     rcx, 0FFFFFFFFFFFFFFFEh; Thread
0x180014337  call    cs:__imp_NtImpersonateAnonymousToken
0x18001433e  nop     dword ptr [rax+rax+00h]
0x180014343  mov     ebx, eax
0x180014345  test    eax, eax
0x180014347  js      loc_1800141FF
0x18001434d  or      r14d, 0Ah
0x180014351  mov     [rbp+57h+ThreadInformation], r15
0x180014355  mov     edx, r14d; DesiredAccess
0x180014358  lea     r9, [rbp+57h+Handle]; TokenHandle
0x18001435c  mov     r8b, 1; OpenAsSelf
0x18001435f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180014366  call    cs:__imp_NtOpenThreadToken
0x18001436d  nop     dword ptr [rax+rax+00h]
0x180014372  mov     r9d, 8; ThreadInformationLength
0x180014378  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18001437c  mov     edx, 5; ThreadInformationClass
0x180014381  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180014388  mov     ebx, eax
0x18001438a  call    cs:__imp_NtSetInformationThread
0x180014391  nop     dword ptr [rax+rax+00h]
0x180014396  jmp     loc_1800142D6
0x18001439b  test    rdi, rdi
0x18001439e  jz      short loc_1800143C1
0x1800143a0  mov     edx, r14d; unsigned int
0x1800143a3  lea     rcx, [rbp+57h+Handle]; NewTokenHandle
0x1800143a7  call    ?LsapGetDuplicatedGlobalProcessHandle@@YAJPEAPEAXK@Z; LsapGetDuplicatedGlobalProcessHandle(void * *,ulong)
0x1800143ac  jmp     loc_1800142D4
0x1800143b1  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], 3E6h
0x1800143b9  mov     ebx, r15d
0x1800143bc  jmp     loc_1800141E5
0x1800143c1  mov     rax, cs:?LsapGlobalProcessTokenLuid@@3U_LUID@@A; _LUID LsapGlobalProcessTokenLuid
0x1800143c8  mov     ebx, r15d
0x1800143cb  jmp     loc_180014314
0x1800143d0  mov     [rdi], r15
0x1800143d3  jmp     loc_180014211
```
