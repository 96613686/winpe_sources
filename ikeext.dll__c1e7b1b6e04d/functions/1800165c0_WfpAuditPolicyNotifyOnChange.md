# WfpAuditPolicyNotifyOnChange

- ea: `0x1800165c0`
- end: `0x1800166d2`
- name: `WfpAuditPolicyNotifyOnChange`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015fb4`

## callees

- `0x1800061ec`
- `0x1800165c0`
- `0x180050850`
- `0x180119010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016639`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18001662f`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18001662f`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x1800165ff`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x1800165ff`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x18001669d`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x18001669d`

## string_xrefs

- `0x18001660f`: `AuditComputeEffectivePolicyBySid`
- `0x18001663f`: `AuditQuerySystemPolicy`

## pseudocode

```c
void __fastcall WfpAuditPolicyNotifyOnChange(__int64 a1)
{
  void *v2; // rcx
  unsigned int v3; // edi
  ULONG v4; // edx
  DWORD LastError; // eax
  __int64 v6; // rcx
  const char *v7; // rdx
  unsigned int v8; // r8d
  __int64 v9; // rdx
  ULONG AuditingInformation; // r9d
  __int64 v11; // rcx
  PAUDIT_POLICY_INFORMATION ppAuditPolicy; // [rsp+20h] [rbp-18h] BYREF

  ppAuditPolicy = 0;
  v2 = *(void **)a1;
  v3 = -1;
  v4 = *(_DWORD *)(a1 + 16);
  if ( v2 )
  {
    if ( !AuditComputeEffectivePolicyBySid(v2, *(const GUID **)(a1 + 32), v4, &ppAuditPolicy) )
    {
      LastError = GetLastError();
      v7 = "AuditComputeEffectivePolicyBySid";
LABEL_4:
      WfpReportSysErrorAsWinError(v6, v7, LastError, 1);
      goto LABEL_14;
    }
  }
  else if ( !AuditQuerySystemPolicy(*(const GUID **)(a1 + 32), v4, &ppAuditPolicy) )
  {
    LastError = GetLastError();
    v7 = "AuditQuerySystemPolicy";
    goto LABEL_4;
  }
  v3 = *(_DWORD *)(a1 + 80);
  if ( *(_DWORD *)(a1 + 16) )
  {
    v8 = 0;
    v9 = 0;
    do
    {
      AuditingInformation = ppAuditPolicy[v9].AuditingInformation;
      v11 = 16 * v9;
      if ( (AuditingInformation & 1) != 0 )
        v3 |= *(_DWORD *)(*(_QWORD *)(a1 + 24) + v11 + 8);
      if ( (AuditingInformation & 2) != 0 )
        v3 |= *(_DWORD *)(*(_QWORD *)(a1 + 24) + v11 + 12);
      ++v8;
      ++v9;
    }
    while ( v8 < *(_DWORD *)(a1 + 16) );
  }
LABEL_14:
  if ( ppAuditPolicy )
    AuditFree(ppAuditPolicy);
  if ( v3 != *(_DWORD *)(a1 + 84) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 40))(*(_QWORD *)(a1 + 48), v3);
    *(_DWORD *)(a1 + 84) = v3;
  }
}

```

## disassembly

```asm
0x1800165c0  mov     [rsp+arg_8], rbx
0x1800165c5  push    rdi
0x1800165c6  sub     rsp, 30h
0x1800165ca  mov     rax, cs:__security_cookie
0x1800165d1  xor     rax, rsp
0x1800165d4  mov     [rsp+38h+var_10], rax
0x1800165d9  mov     rbx, rcx
0x1800165dc  mov     [rsp+38h+ppAuditPolicy], 0
0x1800165e5  mov     rcx, [rcx]; pSid
0x1800165e8  or      edi, 0FFFFFFFFh
0x1800165eb  mov     edx, [rbx+10h]; dwPolicyCount
0x1800165ee  test    rcx, rcx
0x1800165f1  jz      short loc_180016626
0x1800165f3  mov     r8d, edx; dwPolicyCount
0x1800165f6  lea     r9, [rsp+38h+ppAuditPolicy]; ppAuditPolicy
0x1800165fb  mov     rdx, [rbx+20h]; pSubCategoryGuids
0x1800165ff  call    cs:__imp_AuditComputeEffectivePolicyBySid
0x180016605  test    al, al
0x180016607  jnz     short loc_180016648
0x180016609  call    cs:__imp_GetLastError
0x18001660f  lea     rdx, aAuditcomputeef_0; "AuditComputeEffectivePolicyBySid"
0x180016616  mov     r9d, 1
0x18001661c  mov     r8d, eax
0x18001661f  call    WfpReportSysErrorAsWinError
0x180016624  jmp     short loc_180016693
0x180016626  mov     rcx, [rbx+20h]; pSubCategoryGuids
0x18001662a  lea     r8, [rsp+38h+ppAuditPolicy]; ppAuditPolicy
0x18001662f  call    cs:__imp_AuditQuerySystemPolicy
0x180016635  test    al, al
0x180016637  jnz     short loc_180016648
0x180016639  call    cs:__imp_GetLastError
0x18001663f  lea     rdx, aAuditquerysyst_0; "AuditQuerySystemPolicy"
0x180016646  jmp     short loc_180016616
0x180016648  cmp     dword ptr [rbx+10h], 0
0x18001664c  mov     edi, [rbx+50h]
0x18001664f  jbe     short loc_180016693
0x180016651  xor     r8d, r8d
0x180016654  xor     edx, edx
0x180016656  mov     rax, [rsp+38h+ppAuditPolicy]
0x18001665b  lea     rcx, [rdx+rdx*8]
0x18001665f  mov     r9d, [rax+rcx*4+10h]
0x180016664  mov     rcx, rdx
0x180016667  shl     rcx, 4
0x18001666b  test    r9b, 1
0x18001666f  jz      short loc_180016679
0x180016671  mov     rax, [rbx+18h]
0x180016675  or      edi, [rax+rcx+8]
0x180016679  test    r9b, 2
0x18001667d  jz      short loc_180016687
0x18001667f  mov     rax, [rbx+18h]
0x180016683  or      edi, [rax+rcx+0Ch]
0x180016687  inc     r8d
0x18001668a  inc     rdx
0x18001668d  cmp     r8d, [rbx+10h]
0x180016691  jb      short loc_180016656
0x180016693  mov     rcx, [rsp+38h+ppAuditPolicy]; Buffer
0x180016698  test    rcx, rcx
0x18001669b  jz      short loc_1800166A3
0x18001669d  call    cs:__imp_AuditFree
0x1800166a3  cmp     edi, [rbx+54h]
0x1800166a6  jz      short loc_1800166BA
0x1800166a8  mov     rcx, [rbx+30h]
0x1800166ac  mov     edx, edi
0x1800166ae  mov     rax, [rbx+28h]
0x1800166b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166b7  mov     [rbx+54h], edi
0x1800166ba  mov     rcx, [rsp+38h+var_10]
0x1800166bf  xor     rcx, rsp; StackCookie
0x1800166c2  call    __security_check_cookie
0x1800166c7  mov     rbx, [rsp+38h+arg_8]
0x1800166cc  add     rsp, 30h
0x1800166d0  pop     rdi
0x1800166d1  retn
```
