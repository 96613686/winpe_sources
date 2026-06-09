# IASLogonInitialize

- ea: `0x180003fa0`
- end: `0x1800042e0`
- name: `IASLogonInitialize`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800042f0`

## callees

- `0x180003bd0`
- `0x180003fa0`
- `0x180006a20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x1800042c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x1800042c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180004169`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180004169`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800042b1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800042b1`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18000412d`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18000412d`
- `ntdll!RtlNtStatusToDosError` at `0x180004288`
- `ntdll!RtlNtStatusToDosError` at `0x180004288`
- `ntdll!RtlInitString` at `0x180004048`
- `ntdll!RtlInitString` at `0x18000408b`
- `ntdll!RtlInitString` at `0x1800040d7`
- `ntdll!RtlInitString` at `0x180004048`
- `ntdll!RtlInitString` at `0x18000408b`
- `ntdll!RtlInitString` at `0x1800040d7`
- `ntdll!RtlAdjustPrivilege` at `0x180004004`
- `ntdll!RtlAdjustPrivilege` at `0x180004004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041b8`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180004255`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180004255`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800040a3`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800040ef`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800040a3`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800040ef`
- `SspiCli!LsaRegisterLogonProcess` at `0x18000405d`
- `SspiCli!LsaRegisterLogonProcess` at `0x18000405d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180004181`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180004181`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180004248`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800042cf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180004248`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800042cf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180004211`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180004211`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800041d6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800041d6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180004205`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180004205`

## pseudocode

```c
DWORD IASLogonInitialize()
{
  NTSTATUS v0; // eax
  int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  NTSTATUS v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  NTSTATUS v8; // eax
  NTSTATUS LocallyUniqueId; // eax
  __int64 v10; // rbx
  DWORD LastError; // eax
  NTSTATUS v13; // eax
  PVOID PolicyHandle; // [rsp+20h] [rbp-38h] BYREF
  struct _STRING v15; // [rsp+28h] [rbp-30h] BYREF
  _STRING DestinationString; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 OldValue; // [rsp+80h] [rbp+28h] BYREF
  DWORD nSize; // [rsp+88h] [rbp+30h] BYREF
  ULONG SecurityMode; // [rsp+90h] [rbp+38h] BYREF
  PVOID Buffer; // [rsp+98h] [rbp+40h] BYREF

  OldValue = 0;
  Buffer = 0;
  SecurityMode = 0;
  DestinationString = 0;
  nSize = 0;
  v15 = 0;
  PolicyHandle = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids);
  v0 = RtlAdjustPrivilege(7u, 1u, 0, &OldValue);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v3 = 11;
LABEL_6:
      WPP_SF_d(v2[2], v3, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids, (unsigned int)v0);
LABEL_33:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids,
          (unsigned int)v1);
      return RtlNtStatusToDosError(v1);
    }
    return RtlNtStatusToDosError(v1);
  }
  RtlInitString(&DestinationString, "CHAP");
  v0 = LsaRegisterLogonProcess((PLSA_STRING)&DestinationString, &theLogonProcess, &SecurityMode);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v3 = 12;
      goto LABEL_6;
    }
    return RtlNtStatusToDosError(v1);
  }
  RtlInitString(&v15, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
  v4 = LsaLookupAuthenticationPackage(theLogonProcess, (PLSA_STRING)&v15, &theMSV1_0_Package);
  v1 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v6 = 13;
      v7 = (unsigned int)v4;
LABEL_29:
      WPP_SF_d(v5[2], v6, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids, v7);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  RtlInitString(&v15, "Kerberos");
  v8 = LsaLookupAuthenticationPackage(theLogonProcess, (PLSA_STRING)&v15, &theKerberosPackage);
  v1 = v8;
  if ( v8 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v6 = 14;
      v7 = (unsigned int)v8;
      goto LABEL_29;
    }
LABEL_30:
    if ( Buffer )
      LsaFreeMemory(Buffer);
    LsaDeregisterLogonProcess(theLogonProcess);
    theLogonProcess = 0;
    goto LABEL_33;
  }
  *(_QWORD *)theSourceContext.SourceName = TOKEN_SOURCE_NAME;
  LocallyUniqueId = NtAllocateLocallyUniqueId(&theSourceContext.SourceIdentifier);
  v1 = LocallyUniqueId;
  if ( LocallyUniqueId < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v6 = 15;
      v7 = (unsigned int)LocallyUniqueId;
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  _o_wcscpy_s(theLocalServer, 18, L"\\\\");
  nSize = 16;
  if ( GetComputerNameW(&::Buffer, &nSize) )
  {
    v13 = LsaOpenPolicy(0, &theObjectAttributes, 1u, &PolicyHandle);
    v1 = v13;
    if ( v13 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v6 = 17;
        v7 = (unsigned int)v13;
        goto LABEL_29;
      }
      goto LABEL_30;
    }
    v1 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    LsaClose(PolicyHandle);
    if ( v1 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v6 = 18;
        v7 = (unsigned int)v1;
        goto LABEL_29;
      }
      goto LABEL_30;
    }
    _o_wcsncpy_s(theAccountDomain, 257, *((_QWORD *)Buffer + 1), 256);
    word_180033E00 = 0;
    _o__wcsupr(theAccountDomain);
    LsaFreeMemory(Buffer);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v10, 16, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids, LastError);
    }
    return GetLastError();
  }
}

```

## disassembly

```asm
0x180003fa0  push    rbp
0x180003fa2  push    rbx
0x180003fa3  push    rsi
0x180003fa4  push    rdi
0x180003fa5  mov     rbp, rsp
0x180003fa8  sub     rsp, 58h
0x180003fac  xor     edi, edi
0x180003fae  mov     [rbp+OldValue], 0
0x180003fb2  xorps   xmm0, xmm0
0x180003fb5  mov     [rbp+Buffer], rdi
0x180003fb9  xorps   xmm1, xmm1
0x180003fbc  mov     [rbp+SecurityMode], edi
0x180003fbf  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180003fc3  mov     [rbp+nSize], edi
0x180003fc6  movups  xmmword ptr [rbp+var_30.Length], xmm1
0x180003fca  mov     [rbp+PolicyHandle], rdi
0x180003fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd5  lea     rsi, WPP_GLOBAL_Control
0x180003fdc  cmp     rcx, rsi
0x180003fdf  jz      short loc_180003FF6
0x180003fe1  mov     rcx, [rcx+10h]
0x180003fe5  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x180003fec  mov     edx, 0Ah
0x180003ff1  call    WPP_SF_
0x180003ff6  lea     r9, [rbp+OldValue]; OldValue
0x180003ffa  xor     r8d, r8d; ForThread
0x180003ffd  mov     dl, 1; NewValue
0x180003fff  mov     ecx, 7; Privilege
0x180004004  call    cs:__imp_RtlAdjustPrivilege
0x18000400a  mov     ebx, eax
0x18000400c  test    eax, eax
0x18000400e  jns     short loc_18000403D
0x180004010  mov     rcx, cs:WPP_GLOBAL_Control
0x180004017  cmp     rcx, rsi
0x18000401a  jz      loc_180004286
0x180004020  mov     edx, 0Bh
0x180004025  mov     rcx, [rcx+10h]
0x180004029  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x180004030  mov     r9d, eax
0x180004033  call    WPP_SF_d
0x180004038  jmp     loc_180004262
0x18000403d  lea     rdx, LOGON_PROCESS_NAME; "CHAP"
0x180004044  lea     rcx, [rbp+DestinationString]; DestinationString
0x180004048  call    cs:__imp_RtlInitString
0x18000404e  lea     r8, [rbp+SecurityMode]; SecurityMode
0x180004052  lea     rdx, theLogonProcess; LsaHandle
0x180004059  lea     rcx, [rbp+DestinationString]; LogonProcessName
0x18000405d  call    cs:__imp_LsaRegisterLogonProcess
0x180004063  mov     ebx, eax
0x180004065  test    eax, eax
0x180004067  jns     short loc_180004080
0x180004069  mov     rcx, cs:WPP_GLOBAL_Control
0x180004070  cmp     rcx, rsi
0x180004073  jz      loc_180004286
0x180004079  mov     edx, 0Ch
0x18000407e  jmp     short loc_180004025
0x180004080  lea     rdx, SourceString; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x180004087  lea     rcx, [rbp+var_30]; DestinationString
0x18000408b  call    cs:__imp_RtlInitString
0x180004091  mov     rcx, cs:theLogonProcess; LsaHandle
0x180004098  lea     r8, theMSV1_0_Package; AuthenticationPackage
0x18000409f  lea     rdx, [rbp+var_30]; PackageName
0x1800040a3  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800040a9  mov     ebx, eax
0x1800040ab  test    eax, eax
0x1800040ad  jns     short loc_1800040CC
0x1800040af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040b6  cmp     rcx, rsi
0x1800040b9  jz      loc_18000423F
0x1800040bf  mov     edx, 0Dh
0x1800040c4  mov     r9d, eax
0x1800040c7  jmp     loc_18000422F
0x1800040cc  lea     rdx, aKerberos; "Kerberos"
0x1800040d3  lea     rcx, [rbp+var_30]; DestinationString
0x1800040d7  call    cs:__imp_RtlInitString
0x1800040dd  mov     rcx, cs:theLogonProcess; LsaHandle
0x1800040e4  lea     r8, theKerberosPackage; AuthenticationPackage
0x1800040eb  lea     rdx, [rbp+var_30]; PackageName
0x1800040ef  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800040f5  mov     ebx, eax
0x1800040f7  test    eax, eax
0x1800040f9  jns     short loc_180004118
0x1800040fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004102  cmp     rcx, rsi
0x180004105  jz      loc_18000423F
0x18000410b  mov     edx, 0Eh
0x180004110  mov     r9d, eax
0x180004113  jmp     loc_18000422F
0x180004118  mov     rax, cs:TOKEN_SOURCE_NAME
0x18000411f  lea     rcx, theSourceContext.SourceIdentifier; LocallyUniqueId
0x180004126  mov     qword ptr cs:theSourceContext.SourceName, rax
0x18000412d  call    cs:__imp_NtAllocateLocallyUniqueId
0x180004133  mov     ebx, eax
0x180004135  test    eax, eax
0x180004137  jns     short loc_180004156
0x180004139  mov     rcx, cs:WPP_GLOBAL_Control
0x180004140  cmp     rcx, rsi
0x180004143  jz      loc_18000423F
0x180004149  mov     edx, 0Fh
0x18000414e  mov     r9d, eax
0x180004151  jmp     loc_18000422F
0x180004156  lea     r8, asc_180029688; "\\\\"
0x18000415d  mov     edx, 12h
0x180004162  lea     rcx, theLocalServer
0x180004169  call    cs:__imp__o_wcscpy_s
0x18000416f  lea     rdx, [rbp+nSize]; nSize
0x180004173  mov     [rbp+nSize], 10h
0x18000417a  lea     rcx, Buffer; lpBuffer
0x180004181  call    cs:__imp_GetComputerNameW
0x180004187  test    eax, eax
0x180004189  jnz     short loc_1800041C3
0x18000418b  mov     rbx, cs:WPP_GLOBAL_Control
0x180004192  cmp     rbx, rsi
0x180004195  jz      short loc_1800041B8
0x180004197  mov     rbx, [rbx+10h]
0x18000419b  call    cs:__imp_GetLastError
0x1800041a1  mov     edx, 10h
0x1800041a6  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x1800041ad  mov     r9d, eax
0x1800041b0  mov     rcx, rbx
0x1800041b3  call    WPP_SF_d
0x1800041b8  call    cs:__imp_GetLastError
0x1800041be  jmp     loc_1800042D7
0x1800041c3  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800041c7  mov     r8d, 1; DesiredAccess
0x1800041cd  lea     rdx, theObjectAttributes; ObjectAttributes
0x1800041d4  xor     ecx, ecx; SystemName
0x1800041d6  call    cs:__imp_LsaOpenPolicy
0x1800041dc  mov     ebx, eax
0x1800041de  test    eax, eax
0x1800041e0  jns     short loc_1800041F8
0x1800041e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041e9  cmp     rcx, rsi
0x1800041ec  jz      short loc_18000423F
0x1800041ee  mov     edx, 11h
0x1800041f3  mov     r9d, eax
0x1800041f6  jmp     short loc_18000422F
0x1800041f8  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800041fc  lea     r8, [rbp+Buffer]; Buffer
0x180004200  mov     edx, 5; InformationClass
0x180004205  call    cs:__imp_LsaQueryInformationPolicy
0x18000420b  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18000420f  mov     ebx, eax
0x180004211  call    cs:__imp_LsaClose
0x180004217  test    ebx, ebx
0x180004219  jns     short loc_180004297
0x18000421b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004222  cmp     rcx, rsi
0x180004225  jz      short loc_18000423F
0x180004227  mov     edx, 12h
0x18000422c  mov     r9d, ebx
0x18000422f  mov     rcx, [rcx+10h]
0x180004233  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18000423a  call    WPP_SF_d
0x18000423f  mov     rcx, [rbp+Buffer]; Buffer
0x180004243  test    rcx, rcx
0x180004246  jz      short loc_18000424E
0x180004248  call    cs:__imp_LsaFreeMemory
0x18000424e  mov     rcx, cs:theLogonProcess; LsaHandle
0x180004255  call    cs:__imp_LsaDeregisterLogonProcess
0x18000425b  mov     cs:theLogonProcess, rdi
0x180004262  mov     rcx, cs:WPP_GLOBAL_Control
0x180004269  cmp     rcx, rsi
0x18000426c  jz      short loc_180004286
0x18000426e  mov     rcx, [rcx+10h]
0x180004272  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x180004279  mov     edx, 13h
0x18000427e  mov     r9d, ebx
0x180004281  call    WPP_SF_d
0x180004286  mov     ecx, ebx; Status
0x180004288  call    cs:__imp_RtlNtStatusToDosError
0x18000428e  add     rsp, 58h
0x180004292  pop     rdi
0x180004293  pop     rsi
0x180004294  pop     rbx
0x180004295  pop     rbp
0x180004296  retn
0x180004297  mov     r8, [rbp+Buffer]
0x18000429b  lea     rcx, theAccountDomain
0x1800042a2  mov     r9d, 100h
0x1800042a8  mov     edx, 101h
0x1800042ad  mov     r8, [r8+8]
0x1800042b1  call    cs:__imp__o_wcsncpy_s
0x1800042b7  lea     rcx, theAccountDomain
0x1800042be  mov     cs:word_180033E00, di
0x1800042c5  call    cs:__imp__o__wcsupr
0x1800042cb  mov     rcx, [rbp+Buffer]; Buffer
0x1800042cf  call    cs:__imp_LsaFreeMemory
0x1800042d5  xor     eax, eax
0x1800042d7  add     rsp, 58h
0x1800042db  pop     rdi
0x1800042dc  pop     rsi
0x1800042dd  pop     rbx
0x1800042de  pop     rbp
0x1800042df  retn
```
