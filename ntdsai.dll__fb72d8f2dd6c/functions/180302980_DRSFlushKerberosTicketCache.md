# DRSFlushKerberosTicketCache

- ea: `0x180302980`
- end: `0x180302b68`
- name: `DRSFlushKerberosTicketCache`
- size: `488`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180194070`
- `0x18030e658`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x180302980`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803029d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803029d0`
- `ntdll!RtlInitString` at `0x180302a17`
- `ntdll!RtlInitString` at `0x180302a4b`
- `ntdll!RtlInitString` at `0x180302a17`
- `ntdll!RtlInitString` at `0x180302a4b`
- `ntdll!RtlAdjustPrivilege` at `0x1803029ee`
- `ntdll!RtlAdjustPrivilege` at `0x180302b54`
- `ntdll!RtlAdjustPrivilege` at `0x1804708ee`
- `ntdll!RtlAdjustPrivilege` at `0x1803029ee`
- `ntdll!RtlAdjustPrivilege` at `0x180302b54`
- `ntdll!RtlAdjustPrivilege` at `0x1804708ee`
- `ntdll!RtlNtStatusToDosError` at `0x1803029fa`
- `ntdll!RtlNtStatusToDosError` at `0x1803029fa`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180302a63`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180302a63`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180302adf`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180302adf`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180302b0c`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180470898`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180302b0c`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180470898`
- `SspiCli!LsaRegisterLogonProcess` at `0x180302a2f`
- `SspiCli!LsaRegisterLogonProcess` at `0x180302a2f`

## pseudocode

```c
ULONG DRSFlushKerberosTicketCache()
{
  _DWORD *v0; // rdi
  void *Value; // rax
  int v2; // esi
  NTSTATUS v3; // eax
  NTSTATUS v4; // ecx
  NTSTATUS v6; // ebx
  int v7; // r8d
  int v8; // r9d
  ULONG ReturnBufferLength; // [rsp+6Ch] [rbp-54h] BYREF
  void *LsaHandle; // [rsp+70h] [rbp-50h] BYREF
  _DWORD *v11; // [rsp+78h] [rbp-48h]
  PVOID ProtocolReturnBuffer[2]; // [rsp+80h] [rbp-40h] BYREF
  struct _STRING DestinationString; // [rsp+90h] [rbp-30h] BYREF
  unsigned __int8 OldValue; // [rsp+C8h] [rbp+8h] BYREF
  int ProtocolStatus; // [rsp+D0h] [rbp+10h] BYREF
  ULONG AuthenticationPackage; // [rsp+D8h] [rbp+18h] BYREF
  ULONG SecurityMode; // [rsp+E0h] [rbp+20h] BYREF

  OldValue = 0;
  DestinationString = 0;
  SecurityMode = 0;
  LsaHandle = 0;
  AuthenticationPackage = 0;
  ProtocolReturnBuffer[0] = 0;
  ReturnBufferLength = 0;
  ProtocolStatus = 0;
  v0 = 0;
  v11 = 0;
  Value = TlsGetValue(dwTSindex);
  v2 = (int)Value;
  ProtocolReturnBuffer[1] = Value;
  v3 = RtlAdjustPrivilege(7u, 1u, 0, &OldValue);
  if ( v3 >= 0 )
  {
    RtlInitString(&DestinationString, "DS Replication");
    v6 = LsaRegisterLogonProcess((PLSA_STRING)&DestinationString, &LsaHandle, &SecurityMode);
    if ( v6 >= 0 )
    {
      RtlInitString(&DestinationString, "Kerberos");
      v6 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
      if ( v6 >= 0 )
      {
        v0 = (_DWORD *)THAlloc_(v2, 1, 48, 1, 0, 83890997);
        v11 = v0;
        *v0 = 6;
        v6 = LsaCallAuthenticationPackage(
               LsaHandle,
               AuthenticationPackage,
               v0,
               0x30u,
               ProtocolReturnBuffer,
               &ReturnBufferLength,
               &ProtocolStatus);
        if ( (v6 < 0 || ProtocolStatus < 0) && v6 >= 0 )
          v6 = ProtocolStatus;
      }
      ProtocolStatus = LsaDeregisterLogonProcess(LsaHandle);
      if ( v0 )
      {
        THFreeAux(v2, (_DWORD)v0, v7, v8, 83891031);
        v11 = 0;
      }
    }
    if ( !OldValue )
      ProtocolStatus = RtlAdjustPrivilege(7u, 0, 0, &OldValue);
    v4 = v6;
  }
  else
  {
    v4 = v3;
  }
  return RtlNtStatusToDosError(v4);
}

```

## disassembly

```asm
0x180302980  mov     rax, rsp
0x180302983  push    rbx
0x180302984  push    rsi
0x180302985  push    rdi
0x180302986  sub     rsp, 80h
0x18030298d  mov     byte ptr [rax+8], 0
0x180302991  xorps   xmm0, xmm0
0x180302994  movups  xmmword ptr [rax-30h], xmm0
0x180302998  mov     dword ptr [rax+20h], 0
0x18030299f  mov     qword ptr [rax-50h], 0
0x1803029a7  mov     dword ptr [rax+18h], 0
0x1803029ae  mov     qword ptr [rax-40h], 0
0x1803029b6  mov     dword ptr [rax-54h], 0
0x1803029bd  mov     dword ptr [rax+10h], 0
0x1803029c4  xor     edi, edi
0x1803029c6  mov     [rax-48h], rdi
0x1803029ca  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1803029d0  call    cs:__imp_TlsGetValue
0x1803029d6  mov     rsi, rax
0x1803029d9  mov     [rsp+98h+var_38], rax
0x1803029de  lea     r9, [rsp+98h+OldValue]; OldValue
0x1803029e6  xor     r8d, r8d; ForThread
0x1803029e9  mov     dl, 1; NewValue
0x1803029eb  lea     ecx, [rdi+7]; Privilege
0x1803029ee  call    cs:__imp_RtlAdjustPrivilege
0x1803029f4  test    eax, eax
0x1803029f6  jns     short loc_180302A0B
0x1803029f8  mov     ecx, eax; Status
0x1803029fa  call    cs:__imp_RtlNtStatusToDosError
0x180302a00  add     rsp, 80h
0x180302a07  pop     rdi
0x180302a08  pop     rsi
0x180302a09  pop     rbx
0x180302a0a  retn
0x180302a0b  lea     rdx, aDsReplication; "DS Replication"
0x180302a12  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180302a17  call    cs:__imp_RtlInitString
0x180302a1d  lea     r8, [rsp+98h+SecurityMode]; SecurityMode
0x180302a25  lea     rdx, [rsp+98h+LsaHandle]; LsaHandle
0x180302a2a  lea     rcx, [rsp+98h+DestinationString]; LogonProcessName
0x180302a2f  call    cs:__imp_LsaRegisterLogonProcess
0x180302a35  mov     ebx, eax
0x180302a37  test    eax, eax
0x180302a39  js      loc_180302B3A
0x180302a3f  lea     rdx, pszPackage; "Kerberos"
0x180302a46  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180302a4b  call    cs:__imp_RtlInitString
0x180302a51  lea     r8, [rsp+98h+AuthenticationPackage]; AuthenticationPackage
0x180302a59  lea     rdx, [rsp+98h+DestinationString]; PackageName
0x180302a5e  mov     rcx, [rsp+98h+LsaHandle]; LsaHandle
0x180302a63  call    cs:__imp_LsaLookupAuthenticationPackage
0x180302a69  mov     ebx, eax
0x180302a6b  mov     [rsp+98h+var_58], eax
0x180302a6f  test    eax, eax
0x180302a71  js      loc_180302B07
0x180302a77  mov     dword ptr [rsp+98h+ReturnBufferLength], 5001335h
0x180302a7f  mov     dword ptr [rsp+98h+ProtocolReturnBuffer], 0
0x180302a87  mov     ebx, 30h ; '0'
0x180302a8c  lea     r9d, [rbx-2Fh]
0x180302a90  mov     r8d, ebx
0x180302a93  mov     edx, r9d
0x180302a96  mov     rcx, rsi
0x180302a99  call    THAlloc_
0x180302a9e  mov     rdi, rax
0x180302aa1  mov     [rsp+98h+var_48], rax
0x180302aa6  mov     dword ptr [rax], 6
0x180302aac  lea     rax, [rsp+98h+arg_8]
0x180302ab4  mov     [rsp+98h+ProtocolStatus], rax; ProtocolStatus
0x180302ab9  lea     rax, [rsp+98h+var_54]
0x180302abe  mov     [rsp+98h+ReturnBufferLength], rax; ReturnBufferLength
0x180302ac3  lea     rax, [rsp+98h+var_40]
0x180302ac8  mov     [rsp+98h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x180302acd  mov     r9d, ebx; SubmitBufferLength
0x180302ad0  mov     r8, rdi; ProtocolSubmitBuffer
0x180302ad3  mov     edx, [rsp+98h+AuthenticationPackage]; AuthenticationPackage
0x180302ada  mov     rcx, [rsp+98h+LsaHandle]; LsaHandle
0x180302adf  call    cs:__imp_LsaCallAuthenticationPackage
0x180302ae5  mov     ebx, eax
0x180302ae7  mov     [rsp+98h+var_58], eax
0x180302aeb  test    eax, eax
0x180302aed  js      short loc_180302AF9
0x180302aef  cmp     [rsp+98h+arg_8], 0
0x180302af7  jge     short loc_180302B07
0x180302af9  test    ebx, ebx
0x180302afb  cmovns  ebx, [rsp+98h+arg_8]
0x180302b03  mov     [rsp+98h+var_58], ebx
0x180302b07  mov     rcx, [rsp+98h+LsaHandle]; LsaHandle
0x180302b0c  call    cs:__imp_LsaDeregisterLogonProcess
0x180302b12  mov     [rsp+98h+arg_8], eax
0x180302b19  test    rdi, rdi
0x180302b1c  jz      short loc_180302B3A
0x180302b1e  mov     dword ptr [rsp+98h+ProtocolReturnBuffer], 5001357h
0x180302b26  mov     rdx, rdi
0x180302b29  mov     rcx, rsi
0x180302b2c  call    THFreeAux
0x180302b31  mov     [rsp+98h+var_48], 0
0x180302b3a  cmp     [rsp+98h+OldValue], 0
0x180302b42  jnz     short loc_180302B61
0x180302b44  lea     r9, [rsp+98h+OldValue]; OldValue
0x180302b4c  xor     r8d, r8d; ForThread
0x180302b4f  xor     edx, edx; NewValue
0x180302b51  lea     ecx, [rdx+7]; Privilege
0x180302b54  call    cs:__imp_RtlAdjustPrivilege
0x180302b5a  mov     [rsp+98h+arg_8], eax
0x180302b61  mov     ecx, ebx
0x180302b63  jmp     loc_1803029FA
0x18047088b  push    rbp
0x18047088d  sub     rsp, 40h
0x180470891  mov     rbp, rdx
0x180470894  mov     rcx, [rbp+48h]; LsaHandle
0x180470898  call    cs:__imp_LsaDeregisterLogonProcess
0x18047089e  mov     [rbp+0A8h], eax
0x1804708a4  mov     rdx, [rbp+50h]
0x1804708a8  test    rdx, rdx
0x1804708ab  jz      short loc_1804708C6
0x1804708ad  mov     dword ptr [rsp+48h+DestinationString.Buffer], 5001357h
0x1804708b5  mov     rcx, [rbp+60h]
0x1804708b9  call    THFreeAux
0x1804708be  mov     qword ptr [rbp+50h], 0
0x1804708c6  add     rsp, 40h
0x1804708ca  pop     rbp
0x1804708cb  retn
0x1804708cd  push    rbp
0x1804708cf  sub     rsp, 40h
0x1804708d3  mov     rbp, rdx
0x1804708d6  cmp     byte ptr [rbp+0A0h], 0
0x1804708dd  jnz     short loc_1804708F5
0x1804708df  lea     r9, [rbp+0A0h]; OldValue
0x1804708e6  xor     r8d, r8d; ForThread
0x1804708e9  xor     edx, edx; NewValue
0x1804708eb  lea     ecx, [rdx+7]; Privilege
0x1804708ee  call    cs:__imp_RtlAdjustPrivilege
0x1804708f4  nop
0x1804708f5  add     rsp, 40h
0x1804708f9  pop     rbp
0x1804708fa  retn
```
