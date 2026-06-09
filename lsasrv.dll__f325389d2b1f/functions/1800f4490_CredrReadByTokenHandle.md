# CredrReadByTokenHandle

- ea: `0x1800f4490`
- end: `0x1800f463d`
- name: `CredrReadByTokenHandle`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800432c0`
- `0x180044860`
- `0x1800bc2c4`
- `0x1800f3d60`
- `0x1800f3f3c`
- `0x1800f4490`

## import_xrefs

- `ntdll!NtClose` at `0x1800f452b`
- `ntdll!NtClose` at `0x1800f452b`
- `ntdll!NtSetInformationThread` at `0x1800f45cb`
- `ntdll!NtSetInformationThread` at `0x1800f462c`
- `ntdll!NtSetInformationThread` at `0x1800f45cb`
- `ntdll!NtSetInformationThread` at `0x1800f462c`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800f44eb`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800f44eb`
- `RPCRT4!RpcRevertToSelf` at `0x1800f4516`
- `RPCRT4!RpcRevertToSelf` at `0x1800f45a4`
- `RPCRT4!RpcRevertToSelf` at `0x1800f4516`
- `RPCRT4!RpcRevertToSelf` at `0x1800f45a4`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f44d3`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f44f9`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f44d3`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f44f9`
- `RPCRT4!RpcImpersonateClient` at `0x1800f44c5`
- `RPCRT4!RpcImpersonateClient` at `0x1800f44c5`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditCredentialsRead` at `0x1800f455c`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditCredentialsRead` at `0x1800f455c`

## pseudocode

```c
__int64 __fastcall CredrReadByTokenHandle(
        __int64 a1,
        void *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        struct _ENCRYPTED_CREDENTIALW **a7)
{
  RPC_STATUS v11; // eax
  __int64 v12; // rdx
  int LogonId; // ebx
  __int64 v14; // r8
  RPC_STATUS IsClientLocal; // eax
  HANDLE v16; // rcx
  unsigned int ClientLocalFlag; // [rsp+30h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-20h] BYREF
  struct _LUID v20; // [rsp+40h] [rbp-18h] BYREF
  __int64 ThreadInformation; // [rsp+48h] [rbp-10h] BYREF

  v20 = 0;
  Handle = 0;
  ClientLocalFlag = 0;
  v11 = RpcImpersonateClient(0);
  LogonId = I_RpcMapWin32Status(v11);
  if ( LogonId < 0 )
    goto LABEL_6;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  LogonId = I_RpcMapWin32Status(IsClientLocal);
  if ( LogonId < 0 )
  {
LABEL_5:
    RpcRevertToSelf();
    goto LABEL_6;
  }
  if ( !ClientLocalFlag || !(unsigned int)CredpIsRpcClientTrusted() )
  {
    LogonId = -1073741790;
    goto LABEL_5;
  }
  LogonId = CredpDuplicateImpersonationTokenFromCallersHandle(a3, a2, &Handle);
  if ( LogonId < 0 )
    goto LABEL_5;
  if ( a1 )
  {
    LogonId = -1073741534;
    goto LABEL_5;
  }
  RpcRevertToSelf();
  LogonId = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &Handle, 8u);
  if ( LogonId >= 0 )
  {
    LogonId = CrediGetLogonId(1, &v20);
    if ( LogonId >= 0 )
      LogonId = CrediRead(&v20, 0x22u, a4, a5, a6, a7);
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
LABEL_6:
  v16 = Handle;
  if ( Handle )
    NtClose(Handle);
  if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v16, v12, v14) )
    LsapAdtAuditCredentialsRead(&v20, 8103, a4, a5, 1, LogonId);
  return (unsigned int)LogonId;
}

```

## disassembly

```asm
0x1800f4490  push    rbp
0x1800f4492  push    rbx
0x1800f4493  push    rsi
0x1800f4494  push    rdi
0x1800f4495  push    r14
0x1800f4497  push    r15
0x1800f4499  mov     rbp, rsp
0x1800f449c  sub     rsp, 58h
0x1800f44a0  mov     rdi, rcx
0x1800f44a3  mov     qword ptr [rbp+var_18.LowPart], 0
0x1800f44ab  xor     ecx, ecx; BindingHandle
0x1800f44ad  mov     [rbp+Handle], 0
0x1800f44b5  mov     r15, r9
0x1800f44b8  mov     [rbp+ClientLocalFlag], 0
0x1800f44bf  mov     esi, r8d
0x1800f44c2  mov     r14, rdx
0x1800f44c5  call    cs:__imp_RpcImpersonateClient
0x1800f44cc  nop     dword ptr [rax+rax+00h]
0x1800f44d1  mov     ecx, eax; Status
0x1800f44d3  call    cs:__imp_I_RpcMapWin32Status
0x1800f44da  nop     dword ptr [rax+rax+00h]
0x1800f44df  mov     ebx, eax
0x1800f44e1  test    eax, eax
0x1800f44e3  js      short loc_1800F4522
0x1800f44e5  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x1800f44e9  xor     ecx, ecx; BindingHandle
0x1800f44eb  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800f44f2  nop     dword ptr [rax+rax+00h]
0x1800f44f7  mov     ecx, eax; Status
0x1800f44f9  call    cs:__imp_I_RpcMapWin32Status
0x1800f4500  nop     dword ptr [rax+rax+00h]
0x1800f4505  mov     ebx, eax
0x1800f4507  test    eax, eax
0x1800f4509  js      short loc_1800F4516
0x1800f450b  cmp     [rbp+ClientLocalFlag], 0
0x1800f450f  jnz     short loc_1800F4578
0x1800f4511  mov     ebx, 0C0000022h
0x1800f4516  call    cs:__imp_RpcRevertToSelf
0x1800f451d  nop     dword ptr [rax+rax+00h]
0x1800f4522  mov     rcx, [rbp+Handle]; Handle
0x1800f4526  test    rcx, rcx
0x1800f4529  jz      short loc_1800F4537
0x1800f452b  call    cs:__imp_NtClose
0x1800f4532  nop     dword ptr [rax+rax+00h]
0x1800f4537  call    IsLsapAdtInitParametersArrayPresent
0x1800f453c  test    al, al
0x1800f453e  jz      short loc_1800F4568
0x1800f4540  mov     r9d, [rbp+arg_20]
0x1800f4544  lea     rcx, [rbp+var_18]
0x1800f4548  mov     dword ptr [rsp+58h+var_30], ebx
0x1800f454c  mov     r8, r15
0x1800f454f  mov     edx, 1FA7h
0x1800f4554  mov     [rsp+58h+var_38], 1
0x1800f455c  call    cs:__imp_LsapAdtAuditCredentialsRead
0x1800f4563  nop     dword ptr [rax+rax+00h]
0x1800f4568  mov     eax, ebx
0x1800f456a  add     rsp, 58h
0x1800f456e  pop     r15
0x1800f4570  pop     r14
0x1800f4572  pop     rdi
0x1800f4573  pop     rsi
0x1800f4574  pop     rbx
0x1800f4575  pop     rbp
0x1800f4576  retn
0x1800f4578  call    ?CredpIsRpcClientTrusted@@YAHXZ; CredpIsRpcClientTrusted(void)
0x1800f457d  test    eax, eax
0x1800f457f  jz      short loc_1800F4511
0x1800f4581  lea     r8, [rbp+Handle]; void **
0x1800f4585  mov     rdx, r14; void *
0x1800f4588  mov     ecx, esi; unsigned int
0x1800f458a  call    ?CredpDuplicateImpersonationTokenFromCallersHandle@@YAJKPEAXPEAPEAX@Z; CredpDuplicateImpersonationTokenFromCallersHandle(ulong,void *,void * *)
0x1800f458f  mov     ebx, eax
0x1800f4591  test    eax, eax
0x1800f4593  js      short loc_1800F4516
0x1800f4595  test    rdi, rdi
0x1800f4598  jz      short loc_1800F45A4
0x1800f459a  mov     ebx, 0C0000122h
0x1800f459f  jmp     loc_1800F4516
0x1800f45a4  call    cs:__imp_RpcRevertToSelf
0x1800f45ab  nop     dword ptr [rax+rax+00h]
0x1800f45b0  mov     edi, 8
0x1800f45b5  lea     r8, [rbp+Handle]; ThreadInformation
0x1800f45b9  mov     r14, 0FFFFFFFFFFFFFFFEh
0x1800f45c0  mov     r9d, edi; ThreadInformationLength
0x1800f45c3  mov     rcx, r14; ThreadHandle
0x1800f45c6  lea     esi, [rdi-3]
0x1800f45c9  mov     edx, esi; ThreadInformationClass
0x1800f45cb  call    cs:__imp_NtSetInformationThread
0x1800f45d2  nop     dword ptr [rax+rax+00h]
0x1800f45d7  mov     ebx, eax
0x1800f45d9  test    eax, eax
0x1800f45db  js      loc_1800F4522
0x1800f45e1  lea     rdx, [rbp+var_18]; struct _LUID *
0x1800f45e5  lea     ecx, [rdi-7]; int
0x1800f45e8  call    ?CrediGetLogonId@@YAJHPEAU_LUID@@@Z; CrediGetLogonId(int,_LUID *)
0x1800f45ed  mov     ebx, eax
0x1800f45ef  test    eax, eax
0x1800f45f1  js      short loc_1800F4618
0x1800f45f3  mov     rax, [rbp+arg_30]
0x1800f45f7  lea     edx, [rdi+1Ah]; unsigned int
0x1800f45fa  mov     r9d, [rbp+arg_20]; unsigned int
0x1800f45fe  lea     rcx, [rbp+var_18]; struct _LUID *
0x1800f4602  mov     [rsp+58h+var_30], rax; struct _ENCRYPTED_CREDENTIALW **
0x1800f4607  mov     r8, r15; unsigned __int16 *
0x1800f460a  mov     eax, [rbp+arg_28]
0x1800f460d  mov     [rsp+58h+var_38], eax; unsigned int
0x1800f4611  call    ?CrediRead@@YAJPEAU_LUID@@KPEAGKKPEAPEAU_ENCRYPTED_CREDENTIALW@@@Z; CrediRead(_LUID *,ulong,ushort *,ulong,ulong,_ENCRYPTED_CREDENTIALW * *)
0x1800f4616  mov     ebx, eax
0x1800f4618  mov     r9d, edi; ThreadInformationLength
0x1800f461b  mov     [rbp+ThreadInformation], 0
0x1800f4623  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x1800f4627  mov     edx, esi; ThreadInformationClass
0x1800f4629  mov     rcx, r14; ThreadHandle
0x1800f462c  call    cs:__imp_NtSetInformationThread
0x1800f4633  nop     dword ptr [rax+rax+00h]
0x1800f4638  jmp     loc_1800F4522
```
