# DsRolepFlushKerberosTicketCache

- ea: `0x18001f174`
- end: `0x18001f2c3`
- name: `DsRolepFlushKerberosTicketCache`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012460`

## callees

- `0x18001f174`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f295`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f295`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f230`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f230`
- `ntdll!RtlInitString` at `0x18001f1e1`
- `ntdll!RtlInitString` at `0x18001f206`
- `ntdll!RtlInitString` at `0x18001f1e1`
- `ntdll!RtlInitString` at `0x18001f206`
- `ntdll!RtlAdjustPrivilege` at `0x18001f1c3`
- `ntdll!RtlAdjustPrivilege` at `0x18001f2ad`
- `ntdll!RtlAdjustPrivilege` at `0x18001f1c3`
- `ntdll!RtlAdjustPrivilege` at `0x18001f2ad`
- `ntdll!RtlNtStatusToDosError` at `0x18001f2b5`
- `ntdll!RtlNtStatusToDosError` at `0x18001f2b5`
- `SspiCli!LsaRegisterLogonProcess` at `0x18001f1f3`
- `SspiCli!LsaRegisterLogonProcess` at `0x18001f1f3`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18001f284`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18001f284`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18001f267`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18001f267`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18001f21c`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18001f21c`

## pseudocode

```c
ULONG DsRolepFlushKerberosTicketCache()
{
  NTSTATUS v0; // eax
  NTSTATUS v1; // ecx
  _DWORD *v2; // rdi
  NTSTATUS v3; // ebx
  ULONG ReturnBufferLength; // [rsp+40h] [rbp-30h] BYREF
  void *LsaHandle; // [rsp+48h] [rbp-28h] BYREF
  PVOID ProtocolReturnBuffer; // [rsp+50h] [rbp-20h] BYREF
  struct _STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 OldValue; // [rsp+90h] [rbp+20h] BYREF
  int ProtocolStatus; // [rsp+98h] [rbp+28h] BYREF
  ULONG AuthenticationPackage; // [rsp+A0h] [rbp+30h] BYREF
  ULONG SecurityMode; // [rsp+A8h] [rbp+38h] BYREF

  SecurityMode = 0;
  LsaHandle = 0;
  AuthenticationPackage = 0;
  ProtocolReturnBuffer = 0;
  ReturnBufferLength = 0;
  DestinationString = 0;
  ProtocolStatus = 0;
  OldValue = 0;
  v0 = RtlAdjustPrivilege(7u, 1u, 0, &OldValue);
  if ( v0 >= 0 )
  {
    v2 = 0;
    RtlInitString(&DestinationString, "dsRole");
    v3 = LsaRegisterLogonProcess((PLSA_STRING)&DestinationString, &LsaHandle, &SecurityMode);
    RtlInitString(&DestinationString, "Kerberos");
    if ( v3 >= 0 )
    {
      v3 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
      if ( v3 >= 0 )
      {
        v2 = LocalAlloc(0x40u, 0x30u);
        *v2 = 6;
        v3 = LsaCallAuthenticationPackage(
               LsaHandle,
               AuthenticationPackage,
               v2,
               0x30u,
               &ProtocolReturnBuffer,
               &ReturnBufferLength,
               &ProtocolStatus);
        if ( v3 >= 0 && ProtocolStatus < 0 )
          v3 = ProtocolStatus;
      }
    }
    if ( LsaHandle )
      ProtocolStatus = LsaDeregisterLogonProcess(LsaHandle);
    if ( v2 )
      LocalFree(v2);
    if ( !OldValue )
      RtlAdjustPrivilege(7u, 0, 0, &OldValue);
    v1 = v3;
  }
  else
  {
    v1 = v0;
  }
  return RtlNtStatusToDosError(v1);
}

```

## disassembly

```asm
0x18001f174  push    rbp
0x18001f176  push    rbx
0x18001f177  push    rdi
0x18001f178  mov     rbp, rsp
0x18001f17b  sub     rsp, 70h
0x18001f17f  xor     r8d, r8d; ForThread
0x18001f182  mov     [rbp+SecurityMode], 0
0x18001f189  xorps   xmm0, xmm0
0x18001f18c  mov     [rbp+LsaHandle], 0
0x18001f194  lea     r9, [rbp+OldValue]; OldValue
0x18001f198  mov     [rbp+AuthenticationPackage], 0
0x18001f19f  mov     dl, 1; NewValue
0x18001f1a1  mov     [rbp+var_20], 0
0x18001f1a9  lea     ecx, [r8+7]; Privilege
0x18001f1ad  mov     [rbp+var_30], 0
0x18001f1b4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001f1b8  mov     [rbp+arg_8], 0
0x18001f1bf  mov     [rbp+OldValue], 0
0x18001f1c3  call    cs:__imp_RtlAdjustPrivilege
0x18001f1c9  test    eax, eax
0x18001f1cb  jns     short loc_18001F1D4
0x18001f1cd  mov     ecx, eax
0x18001f1cf  jmp     loc_18001F2B5
0x18001f1d4  lea     rdx, aDsrole_1; "dsRole"
0x18001f1db  xor     edi, edi
0x18001f1dd  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001f1e1  call    cs:__imp_RtlInitString
0x18001f1e7  lea     r8, [rbp+SecurityMode]; SecurityMode
0x18001f1eb  lea     rdx, [rbp+LsaHandle]; LsaHandle
0x18001f1ef  lea     rcx, [rbp+DestinationString]; LogonProcessName
0x18001f1f3  call    cs:__imp_LsaRegisterLogonProcess
0x18001f1f9  lea     rdx, aKerberos; "Kerberos"
0x18001f200  mov     ebx, eax
0x18001f202  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001f206  call    cs:__imp_RtlInitString
0x18001f20c  test    ebx, ebx
0x18001f20e  js      short loc_18001F27B
0x18001f210  mov     rcx, [rbp+LsaHandle]; LsaHandle
0x18001f214  lea     r8, [rbp+AuthenticationPackage]; AuthenticationPackage
0x18001f218  lea     rdx, [rbp+DestinationString]; PackageName
0x18001f21c  call    cs:__imp_LsaLookupAuthenticationPackage
0x18001f222  mov     ebx, eax
0x18001f224  test    eax, eax
0x18001f226  js      short loc_18001F27B
0x18001f228  lea     ebx, [rdi+30h]
0x18001f22b  mov     edx, ebx; uBytes
0x18001f22d  lea     ecx, [rdi+40h]; uFlags
0x18001f230  call    cs:__imp_LocalAlloc
0x18001f236  mov     rdi, rax
0x18001f239  mov     r9d, ebx; SubmitBufferLength
0x18001f23c  mov     r8, rdi; ProtocolSubmitBuffer
0x18001f23f  mov     dword ptr [rax], 6
0x18001f245  lea     rax, [rbp+arg_8]
0x18001f249  mov     edx, [rbp+AuthenticationPackage]; AuthenticationPackage
0x18001f24c  mov     rcx, [rbp+LsaHandle]; LsaHandle
0x18001f250  mov     [rsp+70h+ProtocolStatus], rax; ProtocolStatus
0x18001f255  lea     rax, [rbp+var_30]
0x18001f259  mov     [rsp+70h+ReturnBufferLength], rax; ReturnBufferLength
0x18001f25e  lea     rax, [rbp+var_20]
0x18001f262  mov     [rsp+70h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x18001f267  call    cs:__imp_LsaCallAuthenticationPackage
0x18001f26d  mov     ebx, eax
0x18001f26f  test    eax, eax
0x18001f271  js      short loc_18001F27B
0x18001f273  mov     eax, [rbp+arg_8]
0x18001f276  test    eax, eax
0x18001f278  cmovs   ebx, eax
0x18001f27b  mov     rcx, [rbp+LsaHandle]; LsaHandle
0x18001f27f  test    rcx, rcx
0x18001f282  jz      short loc_18001F28D
0x18001f284  call    cs:__imp_LsaDeregisterLogonProcess
0x18001f28a  mov     [rbp+arg_8], eax
0x18001f28d  test    rdi, rdi
0x18001f290  jz      short loc_18001F29B
0x18001f292  mov     rcx, rdi; hMem
0x18001f295  call    cs:__imp_LocalFree
0x18001f29b  cmp     [rbp+OldValue], 0
0x18001f29f  jnz     short loc_18001F2B3
0x18001f2a1  xor     edx, edx; NewValue
0x18001f2a3  lea     r9, [rbp+OldValue]; OldValue
0x18001f2a7  xor     r8d, r8d; ForThread
0x18001f2aa  lea     ecx, [rdx+7]; Privilege
0x18001f2ad  call    cs:__imp_RtlAdjustPrivilege
0x18001f2b3  mov     ecx, ebx; Status
0x18001f2b5  call    cs:__imp_RtlNtStatusToDosError
0x18001f2bb  add     rsp, 70h
0x18001f2bf  pop     rdi
0x18001f2c0  pop     rbx
0x18001f2c1  pop     rbp
0x18001f2c2  retn
```
