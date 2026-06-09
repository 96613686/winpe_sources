# DsRolepRestoreDomainPolicyInfo

- ea: `0x1800226c0`
- end: `0x180022763`
- name: `DsRolepRestoreDomainPolicyInfo`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x180020dbc`
- `0x1800226c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180022752`
- `ntdll!RtlNtStatusToDosError` at `0x180022752`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002272d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002272d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180022706`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180022706`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x180022720`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x180022720`

## pseudocode

```c
ULONG __fastcall DsRolepRestoreDomainPolicyInfo(__int64 a1)
{
  bool v1; // zf
  int v4; // ebx
  NTSTATUS v5; // eax
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF
  PVOID PolicyHandle; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_BYTE *)a1 == 0;
  PolicyHandle = 0;
  if ( v1 )
    return 13;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x207F8u, &PolicyHandle);
  if ( v4 >= 0 )
  {
    v4 = LsaSetInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, *(PVOID *)(a1 + 8));
    v5 = LsaClose(PolicyHandle);
    if ( v4 >= 0 )
      v4 = v5;
  }
  if ( v4 )
    DsRolepLogPrintRoutine(4, "RestoreDomainPolicyInfo failed with 0x%lx\n", v4);
  return RtlNtStatusToDosError(v4);
}

```

## disassembly

```asm
0x1800226c0  mov     [rsp+arg_8], rbx
0x1800226c5  push    rdi
0x1800226c6  sub     rsp, 50h
0x1800226ca  cmp     byte ptr [rcx], 0
0x1800226cd  mov     rdi, rcx
0x1800226d0  mov     [rsp+58h+PolicyHandle], 0
0x1800226d9  jnz     short loc_1800226E2
0x1800226db  mov     eax, 0Dh
0x1800226e0  jmp     short loc_180022758
0x1800226e2  xorps   xmm0, xmm0
0x1800226e5  lea     r9, [rsp+58h+PolicyHandle]; PolicyHandle
0x1800226ea  mov     r8d, 207F8h; DesiredAccess
0x1800226f0  lea     rdx, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x1800226f5  xor     ecx, ecx; SystemName
0x1800226f7  movups  xmmword ptr [rsp+58h+ObjectAttributes.Length], xmm0
0x1800226fc  movups  xmmword ptr [rsp+58h+ObjectAttributes.ObjectName], xmm0
0x180022701  movups  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x180022706  call    cs:__imp_LsaOpenPolicy
0x18002270c  mov     ebx, eax
0x18002270e  test    eax, eax
0x180022710  js      short loc_180022738
0x180022712  mov     r8, [rdi+8]; Buffer
0x180022716  mov     edx, 0Ch; InformationClass
0x18002271b  mov     rcx, [rsp+58h+PolicyHandle]; PolicyHandle
0x180022720  call    cs:__imp_LsaSetInformationPolicy
0x180022726  mov     rcx, [rsp+58h+PolicyHandle]; ObjectHandle
0x18002272b  mov     ebx, eax
0x18002272d  call    cs:__imp_LsaClose
0x180022733  test    ebx, ebx
0x180022735  cmovns  ebx, eax
0x180022738  test    ebx, ebx
0x18002273a  jz      short loc_180022750
0x18002273c  mov     r8d, ebx
0x18002273f  lea     rdx, aRestoredomainp; "RestoreDomainPolicyInfo failed with 0x%"...
0x180022746  mov     ecx, 4
0x18002274b  call    DsRolepLogPrintRoutine
0x180022750  mov     ecx, ebx; Status
0x180022752  call    cs:__imp_RtlNtStatusToDosError
0x180022758  mov     rbx, [rsp+58h+arg_8]
0x18002275d  add     rsp, 50h
0x180022761  pop     rdi
0x180022762  retn
```
