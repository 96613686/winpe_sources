# IASLogonInitialize

- ea: `0x180029d90`
- end: `0x180029eb1`
- name: `IASLogonInitialize`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800291bc`

## callees

- `0x180029d90`

## import_xrefs

- `ntdll!RtlInitString` at `0x180029dde`
- `ntdll!RtlInitString` at `0x180029e0e`
- `ntdll!RtlInitString` at `0x180029e3d`
- `ntdll!RtlInitString` at `0x180029dde`
- `ntdll!RtlInitString` at `0x180029e0e`
- `ntdll!RtlInitString` at `0x180029e3d`
- `ntdll!RtlAdjustPrivilege` at `0x180029dc3`
- `ntdll!RtlAdjustPrivilege` at `0x180029dc3`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180029e76`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180029e76`
- `ntdll!RtlNtStatusToDosError` at `0x180029ea0`
- `ntdll!RtlNtStatusToDosError` at `0x180029ea0`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180029e8d`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180029e8d`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180029e26`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180029e55`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180029e26`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180029e55`
- `SspiCli!LsaRegisterLogonProcess` at `0x180029df3`
- `SspiCli!LsaRegisterLogonProcess` at `0x180029df3`

## pseudocode

```c
ULONG IASLogonInitialize()
{
  int LocallyUniqueId; // ebx
  struct _STRING v2; // [rsp+20h] [rbp-20h] BYREF
  _STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 OldValue; // [rsp+50h] [rbp+10h] BYREF
  ULONG SecurityMode; // [rsp+58h] [rbp+18h] BYREF

  OldValue = 0;
  SecurityMode = 0;
  DestinationString = 0;
  v2 = 0;
  LocallyUniqueId = RtlAdjustPrivilege(7u, 1u, 0, &OldValue);
  if ( LocallyUniqueId >= 0 )
  {
    RtlInitString(&DestinationString, "IAS");
    LocallyUniqueId = LsaRegisterLogonProcess((PLSA_STRING)&DestinationString, &theLogonProcess, &SecurityMode);
    if ( LocallyUniqueId >= 0 )
    {
      RtlInitString(&v2, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
      LocallyUniqueId = LsaLookupAuthenticationPackage(theLogonProcess, (PLSA_STRING)&v2, &theMSV1_0_Package);
      if ( LocallyUniqueId >= 0 )
      {
        RtlInitString(&v2, "Kerberos");
        LocallyUniqueId = LsaLookupAuthenticationPackage(theLogonProcess, (PLSA_STRING)&v2, &theKerberosPackage);
        if ( LocallyUniqueId >= 0 )
        {
          *(_QWORD *)theSourceContext.SourceName = TOKEN_SOURCE_NAME;
          LocallyUniqueId = NtAllocateLocallyUniqueId(&theSourceContext.SourceIdentifier);
          if ( LocallyUniqueId >= 0 )
            return 0;
        }
      }
      LsaDeregisterLogonProcess(theLogonProcess);
      theLogonProcess = 0;
    }
  }
  return RtlNtStatusToDosError(LocallyUniqueId);
}

```

## disassembly

```asm
0x180029d90  mov     [rsp-8+arg_10], rbx
0x180029d95  push    rbp
0x180029d96  mov     rbp, rsp
0x180029d99  sub     rsp, 40h
0x180029d9d  xor     r8d, r8d; ForThread
0x180029da0  mov     [rbp+OldValue], 0
0x180029da4  xorps   xmm0, xmm0
0x180029da7  mov     [rbp+SecurityMode], 0
0x180029dae  xorps   xmm1, xmm1
0x180029db1  lea     r9, [rbp+OldValue]; OldValue
0x180029db5  mov     dl, 1; NewValue
0x180029db7  lea     ecx, [r8+7]; Privilege
0x180029dbb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180029dbf  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x180029dc3  call    cs:__imp_RtlAdjustPrivilege
0x180029dc9  mov     ebx, eax
0x180029dcb  test    eax, eax
0x180029dcd  js      loc_180029E9E
0x180029dd3  lea     rdx, LOGON_PROCESS_NAME; "IAS"
0x180029dda  lea     rcx, [rbp+DestinationString]; DestinationString
0x180029dde  call    cs:__imp_RtlInitString
0x180029de4  lea     r8, [rbp+SecurityMode]; SecurityMode
0x180029de8  lea     rdx, theLogonProcess; LsaHandle
0x180029def  lea     rcx, [rbp+DestinationString]; LogonProcessName
0x180029df3  call    cs:__imp_LsaRegisterLogonProcess
0x180029df9  mov     ebx, eax
0x180029dfb  test    eax, eax
0x180029dfd  js      loc_180029E9E
0x180029e03  lea     rdx, SourceString; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x180029e0a  lea     rcx, [rbp+var_20]; DestinationString
0x180029e0e  call    cs:__imp_RtlInitString
0x180029e14  mov     rcx, cs:theLogonProcess; LsaHandle
0x180029e1b  lea     r8, theMSV1_0_Package; AuthenticationPackage
0x180029e22  lea     rdx, [rbp+var_20]; PackageName
0x180029e26  call    cs:__imp_LsaLookupAuthenticationPackage
0x180029e2c  mov     ebx, eax
0x180029e2e  test    eax, eax
0x180029e30  js      short loc_180029E86
0x180029e32  lea     rdx, aKerberos; "Kerberos"
0x180029e39  lea     rcx, [rbp+var_20]; DestinationString
0x180029e3d  call    cs:__imp_RtlInitString
0x180029e43  mov     rcx, cs:theLogonProcess; LsaHandle
0x180029e4a  lea     r8, theKerberosPackage; AuthenticationPackage
0x180029e51  lea     rdx, [rbp+var_20]; PackageName
0x180029e55  call    cs:__imp_LsaLookupAuthenticationPackage
0x180029e5b  mov     ebx, eax
0x180029e5d  test    eax, eax
0x180029e5f  js      short loc_180029E86
0x180029e61  mov     rax, cs:TOKEN_SOURCE_NAME
0x180029e68  lea     rcx, theSourceContext.SourceIdentifier; LocallyUniqueId
0x180029e6f  mov     qword ptr cs:theSourceContext.SourceName, rax
0x180029e76  call    cs:__imp_NtAllocateLocallyUniqueId
0x180029e7c  mov     ebx, eax
0x180029e7e  test    eax, eax
0x180029e80  js      short loc_180029E86
0x180029e82  xor     eax, eax
0x180029e84  jmp     short loc_180029EA6
0x180029e86  mov     rcx, cs:theLogonProcess; LsaHandle
0x180029e8d  call    cs:__imp_LsaDeregisterLogonProcess
0x180029e93  mov     cs:theLogonProcess, 0
0x180029e9e  mov     ecx, ebx; Status
0x180029ea0  call    cs:__imp_RtlNtStatusToDosError
0x180029ea6  mov     rbx, [rsp+40h+arg_10]
0x180029eab  add     rsp, 40h
0x180029eaf  pop     rbp
0x180029eb0  retn
```
