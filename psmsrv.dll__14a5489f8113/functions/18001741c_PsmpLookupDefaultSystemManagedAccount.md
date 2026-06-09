# PsmpLookupDefaultSystemManagedAccount

- ea: `0x18001741c`
- end: `0x1800174e2`
- name: `PsmpLookupDefaultSystemManagedAccount`
- size: `198`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800173f0`

## callees

- `0x18001741c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800174a5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800174a5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18001747a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18001747a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800174cf`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800174cf`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800174c0`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800174c0`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180017461`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180017461`

## pseudocode

```c
__int64 __fastcall PsmpLookupDefaultSystemManagedAccount(__int64 a1)
{
  NTSTATUS v1; // ebx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  DWORD cbSid; // [rsp+60h] [rbp+10h] BYREF
  int v5; // [rsp+64h] [rbp+14h]
  PVOID DomainInfo; // [rsp+68h] [rbp+18h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF

  v5 = HIDWORD(a1);
  cbSid = 0;
  DomainInfo = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v1 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x801u, &PolicyHandle);
  if ( v1 >= 0 )
  {
    v1 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
    if ( v1 >= 0 )
    {
      cbSid = 68;
      v1 = !CreateWellKnownSid(
              WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
              *((PSID *)DomainInfo + 2),
              PsmpDsmaSid,
              &cbSid)
         ? 0xC0000001
         : 0;
    }
  }
  if ( DomainInfo )
    LsaLookupFreeMemory(DomainInfo);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001741c  mov     [rsp-8+arg_18], rbx
0x180017421  mov     qword ptr [rsp-8+cbSid], rcx
0x180017426  push    rbp
0x180017427  mov     rbp, rsp
0x18001742a  sub     rsp, 50h
0x18001742e  xorps   xmm0, xmm0
0x180017431  mov     [rbp+cbSid], 0
0x180017438  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x18001743c  mov     [rbp+DomainInfo], 0
0x180017444  mov     edx, 801h; AccessMask
0x180017449  mov     [rbp+PolicyHandle], 0
0x180017451  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x180017455  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180017459  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001745d  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180017461  call    cs:__imp_LsaLookupOpenLocalPolicy
0x180017467  mov     ebx, eax
0x180017469  test    eax, eax
0x18001746b  js      short loc_1800174B7
0x18001746d  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180017471  lea     r8, [rbp+DomainInfo]; DomainInfo
0x180017475  mov     edx, 5; DomainInfoClass
0x18001747a  call    cs:__imp_LsaLookupGetDomainInfo
0x180017480  mov     ebx, eax
0x180017482  test    eax, eax
0x180017484  js      short loc_1800174B7
0x180017486  mov     rdx, [rbp+DomainInfo]
0x18001748a  lea     r9, [rbp+cbSid]; cbSid
0x18001748e  mov     [rbp+cbSid], 44h ; 'D'
0x180017495  lea     r8, PsmpDsmaSid; pSid
0x18001749c  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x1800174a1  mov     rdx, [rdx+10h]; DomainSid
0x1800174a5  call    cs:__imp_CreateWellKnownSid
0x1800174ab  neg     eax
0x1800174ad  sbb     ebx, ebx
0x1800174af  not     ebx
0x1800174b1  and     ebx, 0C0000001h
0x1800174b7  mov     rcx, [rbp+DomainInfo]; Buffer
0x1800174bb  test    rcx, rcx
0x1800174be  jz      short loc_1800174C6
0x1800174c0  call    cs:__imp_LsaLookupFreeMemory
0x1800174c6  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800174ca  test    rcx, rcx
0x1800174cd  jz      short loc_1800174D5
0x1800174cf  call    cs:__imp_LsaLookupClose
0x1800174d5  mov     eax, ebx
0x1800174d7  mov     rbx, [rsp+50h+arg_18]
0x1800174dc  add     rsp, 50h
0x1800174e0  pop     rbp
0x1800174e1  retn
```
