# CipReportPPLAuditFailure

- ea: `0x180064980`
- end: `0x180064a71`
- name: `CipReportPPLAuditFailure`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e5a50`

## callees

- `0x180064980`
- `0x18006cfa4`
- `0x18006da7c`
- `0x18009f2d8`
- `0x1800a00f8`
- `0x1800a0390`
- `0x1800a38a0`

## import_xrefs

- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800649e1`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800649e1`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180064a1a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180064a1a`

## pseudocode

```c
__int64 __fastcall CipReportPPLAuditFailure(__int64 a1, __int64 a2, __int64 a3, char a4, char a5, char a6)
{
  __int64 v9; // r8
  __int64 v11; // [rsp+40h] [rbp-38h] BYREF
  __int64 v12; // [rsp+48h] [rbp-30h] BYREF
  int v13[4]; // [rsp+50h] [rbp-28h] BYREF
  int v14[4]; // [rsp+60h] [rbp-18h] BYREF

  v11 = 0;
  v12 = 0;
  *(_OWORD *)v14 = 0;
  *(_OWORD *)v13 = 0;
  CipQueryProcessName(a2, v13, &v12);
  CipQueryFileName(a3, v14, &v11);
  LOBYTE(v9) = 1;
  if ( RtlFindUnicodeSubstring(v13, L"68", v9) )
    ZwUpdateWnfStateData(&WNF_CI_LSAPPL_DLL_LOAD_FAILURE_AUDIT_MODE, 0, 0);
  CiLogPolicyEvent((unsigned __int16 *)v14, (unsigned __int16 *)v13, a4, a5, a6, &CiPolicyFailureAudit);
  CiLogSignatureInformation(a1);
  CipReleaseFileName(v11);
  return CipReleaseProcessName(v12);
}

```

## disassembly

```asm
0x180064980  push    rbp
0x180064982  push    rbx
0x180064983  push    rsi
0x180064984  push    rdi
0x180064985  mov     rbp, rsp
0x180064988  sub     rsp, 78h
0x18006498c  mov     rax, rdx
0x18006498f  mov     [rbp+var_38], 0
0x180064997  xorps   xmm0, xmm0
0x18006499a  mov     [rbp+var_30], 0
0x1800649a2  mov     rbx, r8
0x1800649a5  lea     rdx, [rbp+var_28]
0x1800649a9  mov     rsi, rcx
0x1800649ac  lea     r8, [rbp+var_30]
0x1800649b0  mov     rcx, rax
0x1800649b3  mov     dil, r9b
0x1800649b6  movups  xmmword ptr [rbp+var_18], xmm0
0x1800649ba  movups  xmmword ptr [rbp+var_28], xmm0
0x1800649be  call    CipQueryProcessName
0x1800649c3  lea     r8, [rbp+var_38]
0x1800649c7  mov     rcx, rbx
0x1800649ca  lea     rdx, [rbp+var_18]
0x1800649ce  call    CipQueryFileName
0x1800649d3  mov     r8b, 1
0x1800649d6  lea     rdx, a68; "68"
0x1800649dd  lea     rcx, [rbp+var_28]
0x1800649e1  call    cs:__imp_RtlFindUnicodeSubstring
0x1800649e8  nop     dword ptr [rax+rax+00h]
0x1800649ed  test    rax, rax
0x1800649f0  jz      short loc_180064A26
0x1800649f2  mov     [rsp+78h+var_48], 0
0x1800649fa  lea     rcx, WNF_CI_LSAPPL_DLL_LOAD_FAILURE_AUDIT_MODE
0x180064a01  mov     dword ptr [rsp+78h+EventDescriptor], 0
0x180064a09  xor     r9d, r9d
0x180064a0c  xor     r8d, r8d
0x180064a0f  mov     qword ptr [rsp+78h+var_58], 0
0x180064a18  xor     edx, edx
0x180064a1a  call    cs:__imp_ZwUpdateWnfStateData
0x180064a21  nop     dword ptr [rax+rax+00h]
0x180064a26  mov     r9b, [rbp+arg_20]; int
0x180064a2a  lea     rax, CiPolicyFailureAudit
0x180064a31  mov     [rsp+78h+EventDescriptor], rax; EventDescriptor
0x180064a36  lea     rdx, [rbp+var_28]; int
0x180064a3a  mov     eax, dword ptr [rbp+arg_28]
0x180064a3d  lea     rcx, [rbp+var_18]; int
0x180064a41  mov     r8b, dil; int
0x180064a44  mov     dword ptr [rsp+78h+var_58], eax; char
0x180064a48  call    CiLogPolicyEvent
0x180064a4d  mov     rcx, rsi
0x180064a50  call    CiLogSignatureInformation
0x180064a55  mov     rcx, [rbp+var_38]
0x180064a59  call    CipReleaseFileName
0x180064a5e  mov     rcx, [rbp+var_30]
0x180064a62  call    CipReleaseProcessName
0x180064a67  add     rsp, 78h
0x180064a6b  pop     rdi
0x180064a6c  pop     rsi
0x180064a6d  pop     rbx
0x180064a6e  pop     rbp
0x180064a6f  retn
```
