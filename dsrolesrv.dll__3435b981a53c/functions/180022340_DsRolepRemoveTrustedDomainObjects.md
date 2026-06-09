# DsRolepRemoveTrustedDomainObjects

- ea: `0x180022340`
- end: `0x18002251b`
- name: `DsRolepRemoveTrustedDomainObjects`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011240`

## callees

- `0x180016374`
- `0x1800203d0`
- `0x1800204c4`
- `0x180020530`
- `0x1800205ac`
- `0x180020dbc`
- `0x180022340`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180022505`
- `ntdll!RtlNtStatusToDosError` at `0x180022505`
- `ntdll!RtlInitUnicodeString` at `0x1800223b8`
- `ntdll!RtlInitUnicodeString` at `0x1800223b8`
- `ADVAPI32!LsaOpenTrustedDomain` at `0x1800224a0`
- `ADVAPI32!LsaOpenTrustedDomain` at `0x1800224a0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800224ec`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800224ec`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180022432`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180022432`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800224dd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800224dd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180022415`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180022415`
- `api-ms-win-security-lsapolicy-l1-1-1!LsaDelete` at `0x1800224b0`
- `api-ms-win-security-lsapolicy-l1-1-1!LsaDelete` at `0x1800224b0`

## string_xrefs

- `0x1800224c5`: `OpenPolicy on %ws failed with 0x%lx\n`

## pseudocode

```c
ULONG __fastcall DsRolepRemoveTrustedDomainObjects(__int64 a1, const WCHAR *a2, __int64 a3, char a4)
{
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  NTSTATUS v12; // eax
  PVOID PolicyHandle; // [rsp+30h] [rbp-39h] BYREF
  PVOID Buffer; // [rsp+38h] [rbp-31h] BYREF
  __int64 v15; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  PVOID TrustedDomainHandle; // [rsp+D8h] [rbp+6Fh] BYREF

  PolicyHandle = 0;
  v15 = 0;
  TrustedDomainHandle = 0;
  Buffer = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  DsRolepSetCurrentOperationStatus(28693, 0, 0);
  if ( !a2 )
    return 0;
  RtlInitUnicodeString(&DestinationString, a2);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = ImpLsaOpenPolicy(a1, &DestinationString, &ObjectAttributes, 0x2000000, &v15);
  v10 = v9;
  if ( v9 < 0 )
  {
    DsRolepLogPrintRoutine(4, "OpenPolicy on %ws failed with 0x%lx\n", a2, (unsigned int)v9);
  }
  else
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v10 = LsaOpenPolicy(0, &ObjectAttributes, 0x2000000u, &PolicyHandle);
    if ( v10 < 0 )
      goto LABEL_16;
    v10 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( v10 < 0 )
      goto LABEL_16;
    if ( (a4 & 2) == 0 )
      goto LABEL_11;
    v11 = ImpLsaOpenTrustedDomain(a1, v15, *((_QWORD *)Buffer + 8), 0x10000, &TrustedDomainHandle);
    v10 = v11;
    if ( v11 >= 0 )
    {
      v10 = ImpLsaDelete(a1, TrustedDomainHandle);
      if ( v10 < 0 )
        goto LABEL_16;
LABEL_11:
      v12 = LsaOpenTrustedDomain(PolicyHandle, *(PSID *)(a3 + 64), 0x10000u, &TrustedDomainHandle);
      v10 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -1073741772 )
          v10 = 0;
      }
      else
      {
        v10 = LsaDelete(TrustedDomainHandle);
      }
      goto LABEL_16;
    }
    if ( v11 == -1073741772 )
      goto LABEL_11;
  }
LABEL_16:
  LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v15 )
    ImpLsaClose(a1, v15);
  return RtlNtStatusToDosError(v10);
}

```

## disassembly

```asm
0x180022340  push    rbp
0x180022342  push    rbx
0x180022343  push    rsi
0x180022344  push    rdi
0x180022345  push    r14
0x180022347  push    r15
0x180022349  lea     rbp, [rsp-2Fh]
0x18002234e  sub     rsp, 98h
0x180022355  xorps   xmm0, xmm0
0x180022358  mov     [rbp+57h+PolicyHandle], 0
0x180022360  mov     r15, r8
0x180022363  mov     [rbp+57h+var_80], 0
0x18002236b  mov     rsi, rdx
0x18002236e  mov     [rbp+57h+TrustedDomainHandle], 0
0x180022376  mov     rdi, rcx
0x180022379  mov     [rbp+57h+Buffer], 0
0x180022381  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180022385  xor     eax, eax
0x180022387  xor     r8d, r8d
0x18002238a  xor     edx, edx
0x18002238c  mov     ecx, 7015h
0x180022391  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180022395  mov     r14d, r9d
0x180022398  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002239c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800223a0  call    DsRolepSetCurrentOperationStatus
0x1800223a5  test    rsi, rsi
0x1800223a8  jnz     short loc_1800223B1
0x1800223aa  xor     eax, eax
0x1800223ac  jmp     loc_18002250B
0x1800223b1  mov     rdx, rsi; SourceString
0x1800223b4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800223b8  call    cs:__imp_RtlInitUnicodeString
0x1800223be  xorps   xmm0, xmm0
0x1800223c1  lea     rax, [rbp+57h+var_80]
0x1800223c5  mov     r9d, 2000000h
0x1800223cb  mov     [rsp+0C0h+var_A0], rax
0x1800223d0  lea     r8, [rbp+57h+ObjectAttributes]
0x1800223d4  mov     rcx, rdi
0x1800223d7  lea     rdx, [rbp+57h+DestinationString]
0x1800223db  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800223df  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800223e3  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800223e7  call    ImpLsaOpenPolicy
0x1800223ec  mov     ebx, eax
0x1800223ee  test    eax, eax
0x1800223f0  js      loc_1800224C2
0x1800223f6  xorps   xmm0, xmm0
0x1800223f9  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800223fd  mov     r8d, 2000000h; DesiredAccess
0x180022403  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180022407  xor     ecx, ecx; SystemName
0x180022409  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002240d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180022411  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180022415  call    cs:__imp_LsaOpenPolicy
0x18002241b  mov     ebx, eax
0x18002241d  test    eax, eax
0x18002241f  js      loc_1800224D9
0x180022425  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180022429  lea     r8, [rbp+57h+Buffer]; Buffer
0x18002242d  mov     edx, 0Ch; InformationClass
0x180022432  call    cs:__imp_LsaQueryInformationPolicy
0x180022438  mov     ebx, eax
0x18002243a  test    eax, eax
0x18002243c  js      loc_1800224D9
0x180022442  mov     esi, 0C0000034h
0x180022447  test    r14b, 2
0x18002244b  jz      short loc_18002248E
0x18002244d  mov     r8, [rbp+57h+Buffer]
0x180022451  lea     rax, [rbp+57h+TrustedDomainHandle]
0x180022455  mov     rdx, [rbp+57h+var_80]
0x180022459  mov     r9d, 10000h
0x18002245f  mov     rcx, rdi
0x180022462  mov     [rsp+0C0h+var_A0], rax
0x180022467  mov     r8, [r8+40h]
0x18002246b  call    ImpLsaOpenTrustedDomain
0x180022470  mov     ebx, eax
0x180022472  test    eax, eax
0x180022474  js      short loc_18002248A
0x180022476  mov     rdx, [rbp+57h+TrustedDomainHandle]
0x18002247a  mov     rcx, rdi
0x18002247d  call    ImpLsaDelete
0x180022482  mov     ebx, eax
0x180022484  test    eax, eax
0x180022486  jns     short loc_18002248E
0x180022488  jmp     short loc_1800224D9
0x18002248a  cmp     eax, esi
0x18002248c  jnz     short loc_1800224D9
0x18002248e  mov     rdx, [r15+40h]; TrustedDomainSid
0x180022492  lea     r9, [rbp+57h+TrustedDomainHandle]; TrustedDomainHandle
0x180022496  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002249a  mov     r8d, 10000h; DesiredAccess
0x1800224a0  call    cs:__imp_LsaOpenTrustedDomain
0x1800224a6  mov     ebx, eax
0x1800224a8  test    eax, eax
0x1800224aa  js      short loc_1800224BA
0x1800224ac  mov     rcx, [rbp+57h+TrustedDomainHandle]; ObjectHandle
0x1800224b0  call    cs:__imp_LsaDelete
0x1800224b6  mov     ebx, eax
0x1800224b8  jmp     short loc_1800224D9
0x1800224ba  cmp     eax, esi
0x1800224bc  jnz     short loc_1800224D9
0x1800224be  xor     ebx, ebx
0x1800224c0  jmp     short loc_1800224D9
0x1800224c2  mov     r9d, eax
0x1800224c5  lea     rdx, aOpenpolicyOnWs; "OpenPolicy on %ws failed with 0x%lx\n"
0x1800224cc  mov     r8, rsi
0x1800224cf  mov     ecx, 4
0x1800224d4  call    DsRolepLogPrintRoutine
0x1800224d9  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800224dd  call    cs:__imp_LsaFreeMemory
0x1800224e3  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x1800224e7  test    rcx, rcx
0x1800224ea  jz      short loc_1800224F2
0x1800224ec  call    cs:__imp_LsaClose
0x1800224f2  mov     rdx, [rbp+57h+var_80]
0x1800224f6  test    rdx, rdx
0x1800224f9  jz      short loc_180022503
0x1800224fb  mov     rcx, rdi
0x1800224fe  call    ImpLsaClose
0x180022503  mov     ecx, ebx; Status
0x180022505  call    cs:__imp_RtlNtStatusToDosError
0x18002250b  add     rsp, 98h
0x180022512  pop     r15
0x180022514  pop     r14
0x180022516  pop     rdi
0x180022517  pop     rsi
0x180022518  pop     rbx
0x180022519  pop     rbp
0x18002251a  retn
```
