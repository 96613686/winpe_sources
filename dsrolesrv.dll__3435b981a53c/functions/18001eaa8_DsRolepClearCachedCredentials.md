# DsRolepClearCachedCredentials

- ea: `0x18001eaa8`
- end: `0x18001ebff`
- name: `DsRolepClearCachedCredentials`
- size: `343`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x18001eaa8`
- `0x180020dbc`

## import_xrefs

- `ntdll!RtlInitString` at `0x18001eb0a`
- `ntdll!RtlInitString` at `0x18001eb4f`
- `ntdll!RtlInitString` at `0x18001eb0a`
- `ntdll!RtlInitString` at `0x18001eb4f`
- `ntdll!RtlAdjustPrivilege` at `0x18001eb1d`
- `ntdll!RtlAdjustPrivilege` at `0x18001ebd6`
- `ntdll!RtlAdjustPrivilege` at `0x18001eb1d`
- `ntdll!RtlAdjustPrivilege` at `0x18001ebd6`
- `SspiCli!LsaRegisterLogonProcess` at `0x18001eb38`
- `SspiCli!LsaRegisterLogonProcess` at `0x18001eb38`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18001ebaa`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18001ebaa`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18001eb99`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18001eb99`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18001eb61`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18001eb61`
- `SspiCli!LsaFreeReturnBuffer` at `0x18001ebb9`
- `SspiCli!LsaFreeReturnBuffer` at `0x18001ebb9`

## string_xrefs

- `0x18001ebe0`: `DsRolepClearCachedCredentials returns with status 0x%08x, and protocol status is 0x%08x\n`

## pseudocode

```c
__int64 DsRolepClearCachedCredentials()
{
  char v0; // di
  NTSTATUS v1; // ebx
  ULONG ReturnBufferLength; // [rsp+40h] [rbp-40h] BYREF
  void *LsaHandle; // [rsp+48h] [rbp-38h] BYREF
  __int64 ProtocolSubmitBuffer; // [rsp+50h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-28h] BYREF
  _STRING DestinationString; // [rsp+60h] [rbp-20h] BYREF
  struct _STRING v8; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int8 OldValue; // [rsp+A0h] [rbp+20h] BYREF
  ULONG AuthenticationPackage; // [rsp+A8h] [rbp+28h] BYREF
  int ProtocolStatus; // [rsp+B0h] [rbp+30h] BYREF
  ULONG SecurityMode; // [rsp+B8h] [rbp+38h] BYREF

  Buffer = 0;
  LsaHandle = 0;
  ReturnBufferLength = 0;
  AuthenticationPackage = 0;
  DestinationString = 0;
  SecurityMode = 0;
  v0 = 0;
  v8 = 0;
  ProtocolStatus = 0;
  OldValue = 0;
  ProtocolSubmitBuffer = 14;
  RtlInitString(&DestinationString, "dsRole");
  v1 = RtlAdjustPrivilege(7u, 1u, 0, &OldValue);
  if ( v1 >= 0 )
  {
    v0 = 1;
    v1 = LsaRegisterLogonProcess((PLSA_STRING)&DestinationString, &LsaHandle, &SecurityMode);
    if ( v1 >= 0 )
    {
      RtlInitString(&v8, "NTLM");
      v1 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&v8, &AuthenticationPackage);
      if ( v1 >= 0 )
        v1 = LsaCallAuthenticationPackage(
               LsaHandle,
               AuthenticationPackage,
               &ProtocolSubmitBuffer,
               8u,
               &Buffer,
               &ReturnBufferLength,
               &ProtocolStatus);
    }
  }
  if ( LsaHandle )
    LsaDeregisterLogonProcess(LsaHandle);
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v0 && !OldValue )
    RtlAdjustPrivilege(7u, 0, 0, &OldValue);
  return DsRolepLogPrintRoutine(
           4,
           "DsRolepClearCachedCredentials returns with status 0x%08x, and protocol status is 0x%08x\n",
           v1,
           ProtocolStatus);
}

```

## disassembly

```asm
0x18001eaa8  push    rbp
0x18001eaaa  push    rbx
0x18001eaab  push    rdi
0x18001eaac  mov     rbp, rsp
0x18001eaaf  sub     rsp, 80h
0x18001eab6  xorps   xmm0, xmm0
0x18001eab9  mov     [rbp+Buffer], 0
0x18001eac1  xorps   xmm1, xmm1
0x18001eac4  mov     [rbp+LsaHandle], 0
0x18001eacc  lea     rdx, aDsrole_1; "dsRole"
0x18001ead3  mov     [rbp+var_40], 0
0x18001eada  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001eade  mov     [rbp+AuthenticationPackage], 0
0x18001eae5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001eae9  mov     [rbp+SecurityMode], 0
0x18001eaf0  xor     dil, dil
0x18001eaf3  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x18001eaf7  mov     [rbp+arg_10], 0
0x18001eafe  mov     [rbp+OldValue], 0
0x18001eb02  mov     [rbp+ProtocolSubmitBuffer], 0Eh
0x18001eb0a  call    cs:__imp_RtlInitString
0x18001eb10  xor     r8d, r8d; ForThread
0x18001eb13  lea     r9, [rbp+OldValue]; OldValue
0x18001eb17  mov     dl, 1; NewValue
0x18001eb19  lea     ecx, [r8+7]; Privilege
0x18001eb1d  call    cs:__imp_RtlAdjustPrivilege
0x18001eb23  mov     ebx, eax
0x18001eb25  test    eax, eax
0x18001eb27  js      short loc_18001EBA1
0x18001eb29  lea     r8, [rbp+SecurityMode]; SecurityMode
0x18001eb2d  mov     dil, 1
0x18001eb30  lea     rdx, [rbp+LsaHandle]; LsaHandle
0x18001eb34  lea     rcx, [rbp+DestinationString]; LogonProcessName
0x18001eb38  call    cs:__imp_LsaRegisterLogonProcess
0x18001eb3e  mov     ebx, eax
0x18001eb40  test    eax, eax
0x18001eb42  js      short loc_18001EBA1
0x18001eb44  lea     rdx, aNtlm; "NTLM"
0x18001eb4b  lea     rcx, [rbp+var_10]; DestinationString
0x18001eb4f  call    cs:__imp_RtlInitString
0x18001eb55  mov     rcx, [rbp+LsaHandle]; LsaHandle
0x18001eb59  lea     r8, [rbp+AuthenticationPackage]; AuthenticationPackage
0x18001eb5d  lea     rdx, [rbp+var_10]; PackageName
0x18001eb61  call    cs:__imp_LsaLookupAuthenticationPackage
0x18001eb67  mov     ebx, eax
0x18001eb69  test    eax, eax
0x18001eb6b  js      short loc_18001EBA1
0x18001eb6d  mov     edx, [rbp+AuthenticationPackage]; AuthenticationPackage
0x18001eb70  lea     rax, [rbp+arg_10]
0x18001eb74  mov     rcx, [rbp+LsaHandle]; LsaHandle
0x18001eb78  lea     r8, [rbp+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x18001eb7c  mov     [rsp+80h+ProtocolStatus], rax; ProtocolStatus
0x18001eb81  mov     r9d, 8; SubmitBufferLength
0x18001eb87  lea     rax, [rbp+var_40]
0x18001eb8b  mov     [rsp+80h+ReturnBufferLength], rax; ReturnBufferLength
0x18001eb90  lea     rax, [rbp+Buffer]
0x18001eb94  mov     [rsp+80h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x18001eb99  call    cs:__imp_LsaCallAuthenticationPackage
0x18001eb9f  mov     ebx, eax
0x18001eba1  mov     rcx, [rbp+LsaHandle]; LsaHandle
0x18001eba5  test    rcx, rcx
0x18001eba8  jz      short loc_18001EBB0
0x18001ebaa  call    cs:__imp_LsaDeregisterLogonProcess
0x18001ebb0  mov     rcx, [rbp+Buffer]; Buffer
0x18001ebb4  test    rcx, rcx
0x18001ebb7  jz      short loc_18001EBBF
0x18001ebb9  call    cs:__imp_LsaFreeReturnBuffer
0x18001ebbf  test    dil, dil
0x18001ebc2  jz      short loc_18001EBDC
0x18001ebc4  cmp     [rbp+OldValue], 0
0x18001ebc8  jnz     short loc_18001EBDC
0x18001ebca  xor     edx, edx; NewValue
0x18001ebcc  lea     r9, [rbp+OldValue]; OldValue
0x18001ebd0  xor     r8d, r8d; ForThread
0x18001ebd3  lea     ecx, [rdx+7]; Privilege
0x18001ebd6  call    cs:__imp_RtlAdjustPrivilege
0x18001ebdc  mov     r9d, [rbp+arg_10]
0x18001ebe0  lea     rdx, aDsrolepclearca; "DsRolepClearCachedCredentials returns w"...
0x18001ebe7  mov     r8d, ebx
0x18001ebea  mov     ecx, 4
0x18001ebef  call    DsRolepLogPrintRoutine
0x18001ebf4  add     rsp, 80h
0x18001ebfb  pop     rdi
0x18001ebfc  pop     rbx
0x18001ebfd  pop     rbp
0x18001ebfe  retn
```
