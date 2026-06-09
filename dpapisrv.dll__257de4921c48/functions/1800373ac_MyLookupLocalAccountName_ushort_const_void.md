# MyLookupLocalAccountName(ushort const *,void * *)

- ea: `0x1800373ac`
- end: `0x180037599`
- name: `?MyLookupLocalAccountName@@YAKPEBGPEAPEAX@Z`
- size: `493`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038874`

## callees

- `0x180007f10`
- `0x1800373ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800374cb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800374cb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003750e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003750e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003749f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003749f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003751e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003751e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800374e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800374e0`
- `ntdll!RtlNtStatusToDosError` at `0x180037417`
- `ntdll!RtlNtStatusToDosError` at `0x180037483`
- `ntdll!RtlNtStatusToDosError` at `0x180037417`
- `ntdll!RtlNtStatusToDosError` at `0x180037483`
- `ntdll!RtlInitUnicodeString` at `0x18003743e`
- `ntdll!RtlInitUnicodeString` at `0x18003743e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003757a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003757a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18003746f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18003746f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180037403`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180037403`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180037550`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180037565`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180037550`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180037565`

## string_xrefs

- `0x18003753b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall MyLookupLocalAccountName(PCWSTR SourceString, void **a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // edi
  ULONG LastError; // eax
  __int64 v7; // r9
  const char *v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  DWORD LengthSid; // edi
  HLOCAL v13; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+98h] [rbp+28h] BYREF
  PVOID PolicyHandle; // [rsp+A0h] [rbp+30h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+A8h] [rbp+38h] BYREF

  *a2 = 0;
  PolicyHandle = 0;
  ReferencedDomains = 0;
  Sids = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
  v5 = v4;
  if ( v4 )
  {
    LastError = RtlNtStatusToDosError(v4);
    v7 = 726;
LABEL_3:
    v8 = "Status";
    v9 = v5;
LABEL_13:
    v11 = LastError;
    goto LABEL_14;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v10 = LsaLookupNames2(
          PolicyHandle,
          0x80000000,
          1u,
          (PLSA_UNICODE_STRING)&DestinationString,
          &ReferencedDomains,
          &Sids);
  v5 = v10;
  if ( v10 < 0 )
  {
    LastError = RtlNtStatusToDosError(v10);
    v7 = 743;
    goto LABEL_3;
  }
  if ( IsValidSid(Sids->Sid) )
  {
    LengthSid = GetLengthSid(Sids->Sid);
    v13 = LocalAlloc(0x40u, LengthSid);
    *a2 = v13;
    if ( v13 )
    {
      v11 = 0;
      if ( CopySid(LengthSid, v13, Sids->Sid) )
        goto LABEL_15;
      LastError = GetLastError();
      v7 = 768;
      v8 = "dwError";
      v9 = LastError;
      goto LABEL_13;
    }
    v11 = 8;
    v7 = 761;
  }
  else
  {
    v11 = 13;
    v7 = 750;
  }
  v8 = "dwError";
  v9 = v11;
LABEL_14:
  DebugTraceError(v9, v8, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v7);
LABEL_15:
  if ( Sids )
    LsaFreeMemory(Sids);
  if ( ReferencedDomains )
    LsaFreeMemory(ReferencedDomains);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v11;
}

```

## disassembly

```asm
0x1800373ac  mov     [rsp-18h+arg_0], rbx
0x1800373b1  push    rbp
0x1800373b2  push    rsi
0x1800373b3  push    rdi
0x1800373b4  mov     rbp, rsp
0x1800373b7  sub     rsp, 70h
0x1800373bb  xorps   xmm0, xmm0
0x1800373be  mov     qword ptr [rdx], 0
0x1800373c5  mov     rbx, rdx
0x1800373c8  mov     [rbp+PolicyHandle], 0
0x1800373d0  mov     rsi, rcx
0x1800373d3  mov     [rbp+arg_18], 0
0x1800373db  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800373df  mov     [rbp+arg_8], 0
0x1800373e7  xor     ecx, ecx; SystemName
0x1800373e9  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800373ed  mov     r8d, 800h; DesiredAccess
0x1800373f3  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800373f7  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800373fb  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800373ff  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180037403  call    cs:__imp_LsaOpenPolicy
0x18003740a  nop     dword ptr [rax+rax+00h]
0x18003740f  mov     edi, eax
0x180037411  test    eax, eax
0x180037413  jz      short loc_180037437
0x180037415  mov     ecx, eax; Status
0x180037417  call    cs:__imp_RtlNtStatusToDosError
0x18003741e  nop     dword ptr [rax+rax+00h]
0x180037423  mov     r9d, 2D6h
0x180037429  lea     rdx, aStatus; "Status"
0x180037430  mov     ecx, edi
0x180037432  jmp     loc_180037539
0x180037437  mov     rdx, rsi; SourceString
0x18003743a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003743e  call    cs:__imp_RtlInitUnicodeString
0x180037445  nop     dword ptr [rax+rax+00h]
0x18003744a  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18003744e  lea     rax, [rbp+arg_8]
0x180037452  mov     [rsp+70h+Sids], rax; Sids
0x180037457  lea     r9, [rbp+DestinationString]; Names
0x18003745b  lea     rax, [rbp+arg_18]
0x18003745f  mov     edx, 80000000h; Flags
0x180037464  mov     r8d, 1; Count
0x18003746a  mov     [rsp+70h+ReferencedDomains], rax; ReferencedDomains
0x18003746f  call    cs:__imp_LsaLookupNames2
0x180037476  nop     dword ptr [rax+rax+00h]
0x18003747b  mov     edi, eax
0x18003747d  test    eax, eax
0x18003747f  jns     short loc_180037497
0x180037481  mov     ecx, eax; Status
0x180037483  call    cs:__imp_RtlNtStatusToDosError
0x18003748a  nop     dword ptr [rax+rax+00h]
0x18003748f  mov     r9d, 2E7h
0x180037495  jmp     short loc_180037429
0x180037497  mov     rcx, [rbp+arg_8]
0x18003749b  mov     rcx, [rcx+8]; pSid
0x18003749f  call    cs:__imp_IsValidSid
0x1800374a6  nop     dword ptr [rax+rax+00h]
0x1800374ab  test    eax, eax
0x1800374ad  jnz     short loc_1800374C3
0x1800374af  lea     ebx, [rax+0Dh]
0x1800374b2  mov     r9d, 2EEh
0x1800374b8  lea     rdx, aDwerror; "dwError"
0x1800374bf  mov     ecx, ebx
0x1800374c1  jmp     short loc_18003753B
0x1800374c3  mov     rcx, [rbp+arg_8]
0x1800374c7  mov     rcx, [rcx+8]; pSid
0x1800374cb  call    cs:__imp_GetLengthSid
0x1800374d2  nop     dword ptr [rax+rax+00h]
0x1800374d7  mov     edx, eax; uBytes
0x1800374d9  mov     ecx, 40h ; '@'; uFlags
0x1800374de  mov     edi, eax
0x1800374e0  call    cs:__imp_LocalAlloc
0x1800374e7  nop     dword ptr [rax+rax+00h]
0x1800374ec  mov     [rbx], rax
0x1800374ef  test    rax, rax
0x1800374f2  jnz     short loc_1800374FF
0x1800374f4  lea     ebx, [rax+8]
0x1800374f7  mov     r9d, 2F9h
0x1800374fd  jmp     short loc_1800374B8
0x1800374ff  mov     r8, [rbp+arg_8]
0x180037503  mov     rdx, rax; pDestinationSid
0x180037506  mov     ecx, edi; nDestinationSidLength
0x180037508  xor     ebx, ebx
0x18003750a  mov     r8, [r8+8]; pSourceSid
0x18003750e  call    cs:__imp_CopySid
0x180037515  nop     dword ptr [rax+rax+00h]
0x18003751a  test    eax, eax
0x18003751c  jnz     short loc_180037547
0x18003751e  call    cs:__imp_GetLastError
0x180037525  nop     dword ptr [rax+rax+00h]
0x18003752a  mov     r9d, 300h
0x180037530  lea     rdx, aDwerror; "dwError"
0x180037537  mov     ecx, eax
0x180037539  mov     ebx, eax
0x18003753b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180037542  call    DebugTraceError
0x180037547  mov     rcx, [rbp+arg_8]; Buffer
0x18003754b  test    rcx, rcx
0x18003754e  jz      short loc_18003755C
0x180037550  call    cs:__imp_LsaFreeMemory
0x180037557  nop     dword ptr [rax+rax+00h]
0x18003755c  mov     rcx, [rbp+arg_18]; Buffer
0x180037560  test    rcx, rcx
0x180037563  jz      short loc_180037571
0x180037565  call    cs:__imp_LsaFreeMemory
0x18003756c  nop     dword ptr [rax+rax+00h]
0x180037571  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180037575  test    rcx, rcx
0x180037578  jz      short loc_180037586
0x18003757a  call    cs:__imp_LsaClose
0x180037581  nop     dword ptr [rax+rax+00h]
0x180037586  mov     eax, ebx
0x180037588  mov     rbx, [rsp+70h+arg_0]
0x180037590  add     rsp, 70h
0x180037594  pop     rdi
0x180037595  pop     rsi
0x180037596  pop     rbp
0x180037597  retn
```
