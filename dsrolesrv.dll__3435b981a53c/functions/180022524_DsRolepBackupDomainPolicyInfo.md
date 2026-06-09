# DsRolepBackupDomainPolicyInfo

- ea: `0x180022524`
- end: `0x1800225d2`
- name: `DsRolepBackupDomainPolicyInfo`
- size: `174`
- prototype: `ULONG __fastcall(void *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800100c0`
- `0x180011240`
- `0x180012460`

## callees

- `0x180022524`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800225c1`
- `ntdll!RtlNtStatusToDosError` at `0x1800225c1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800225b2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800225b2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180022586`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800225a0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180022586`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800225a0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002256c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002256c`

## pseudocode

```c
ULONG __fastcall DsRolepBackupDomainPolicyInfo(void *a1, __int64 a2)
{
  bool v2; // zf
  int InformationPolicy; // ebx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF
  PVOID PolicyHandle; // [rsp+60h] [rbp+8h] BYREF

  PolicyHandle = a1;
  v2 = *(_BYTE *)a2 == 0;
  PolicyHandle = 0;
  if ( !v2 )
    return 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  InformationPolicy = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( InformationPolicy >= 0 )
  {
    InformationPolicy = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, (PVOID *)(a2 + 8));
    if ( InformationPolicy >= 0 )
      InformationPolicy = LsaQueryInformationPolicy(PolicyHandle, PolicyLsaServerRoleInformation, (PVOID *)(a2 + 16));
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( InformationPolicy >= 0 )
    *(_BYTE *)a2 = 1;
  return RtlNtStatusToDosError(InformationPolicy);
}

```

## disassembly

```asm
0x180022524  mov     [rsp+arg_8], rbx
0x180022529  mov     [rsp+PolicyHandle], rcx
0x18002252e  push    rdi
0x18002252f  sub     rsp, 50h
0x180022533  cmp     byte ptr [rdx], 0
0x180022536  mov     rdi, rdx
0x180022539  mov     [rsp+58h+PolicyHandle], 0
0x180022542  jz      short loc_180022548
0x180022544  xor     eax, eax
0x180022546  jmp     short loc_1800225C7
0x180022548  xorps   xmm0, xmm0
0x18002254b  lea     r9, [rsp+58h+PolicyHandle]; PolicyHandle
0x180022550  mov     r8d, 1; DesiredAccess
0x180022556  lea     rdx, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x18002255b  xor     ecx, ecx; SystemName
0x18002255d  movups  xmmword ptr [rsp+58h+ObjectAttributes.Length], xmm0
0x180022562  movups  xmmword ptr [rsp+58h+ObjectAttributes.ObjectName], xmm0
0x180022567  movups  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002256c  call    cs:__imp_LsaOpenPolicy
0x180022572  mov     ebx, eax
0x180022574  test    eax, eax
0x180022576  js      short loc_1800225A8
0x180022578  mov     rcx, [rsp+58h+PolicyHandle]; PolicyHandle
0x18002257d  lea     r8, [rdi+8]; Buffer
0x180022581  mov     edx, 0Ch; InformationClass
0x180022586  call    cs:__imp_LsaQueryInformationPolicy
0x18002258c  mov     ebx, eax
0x18002258e  test    eax, eax
0x180022590  js      short loc_1800225A8
0x180022592  mov     rcx, [rsp+58h+PolicyHandle]; PolicyHandle
0x180022597  lea     r8, [rdi+10h]; Buffer
0x18002259b  mov     edx, 6; InformationClass
0x1800225a0  call    cs:__imp_LsaQueryInformationPolicy
0x1800225a6  mov     ebx, eax
0x1800225a8  mov     rcx, [rsp+58h+PolicyHandle]; ObjectHandle
0x1800225ad  test    rcx, rcx
0x1800225b0  jz      short loc_1800225B8
0x1800225b2  call    cs:__imp_LsaClose
0x1800225b8  test    ebx, ebx
0x1800225ba  js      short loc_1800225BF
0x1800225bc  mov     byte ptr [rdi], 1
0x1800225bf  mov     ecx, ebx; Status
0x1800225c1  call    cs:__imp_RtlNtStatusToDosError
0x1800225c7  mov     rbx, [rsp+58h+arg_8]
0x1800225cc  add     rsp, 50h
0x1800225d0  pop     rdi
0x1800225d1  retn
```
