# CipReportPPLAuditFailure

- ea: `0x180064af0`
- end: `0x180064be1`
- name: `CipReportPPLAuditFailure`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e5fd0`

## callees

- `0x180064af0`
- `0x18006d284`
- `0x18006dd5c`
- `0x18008f038`
- `0x18008f2d0`
- `0x180090564`
- `0x1800a3d3c`

## import_xrefs

- `ntoskrnl!RtlFindUnicodeSubstring` at `0x180064b51`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x180064b51`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180064b8a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180064b8a`

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
0x180064af0  push    rbp
0x180064af2  push    rbx
0x180064af3  push    rsi
0x180064af4  push    rdi
0x180064af5  mov     rbp, rsp
0x180064af8  sub     rsp, 78h
0x180064afc  mov     rax, rdx
0x180064aff  mov     [rbp+var_38], 0
0x180064b07  xorps   xmm0, xmm0
0x180064b0a  mov     [rbp+var_30], 0
0x180064b12  mov     rbx, r8
0x180064b15  lea     rdx, [rbp+var_28]
0x180064b19  mov     rsi, rcx
0x180064b1c  lea     r8, [rbp+var_30]
0x180064b20  mov     rcx, rax
0x180064b23  mov     dil, r9b
0x180064b26  movups  xmmword ptr [rbp+var_18], xmm0
0x180064b2a  movups  xmmword ptr [rbp+var_28], xmm0
0x180064b2e  call    CipQueryProcessName
0x180064b33  lea     r8, [rbp+var_38]
0x180064b37  mov     rcx, rbx
0x180064b3a  lea     rdx, [rbp+var_18]
0x180064b3e  call    CipQueryFileName
0x180064b43  mov     r8b, 1
0x180064b46  lea     rdx, a68; "68"
0x180064b4d  lea     rcx, [rbp+var_28]
0x180064b51  call    cs:__imp_RtlFindUnicodeSubstring
0x180064b58  nop     dword ptr [rax+rax+00h]
0x180064b5d  test    rax, rax
0x180064b60  jz      short loc_180064B96
0x180064b62  mov     [rsp+78h+var_48], 0
0x180064b6a  lea     rcx, WNF_CI_LSAPPL_DLL_LOAD_FAILURE_AUDIT_MODE
0x180064b71  mov     dword ptr [rsp+78h+EventDescriptor], 0
0x180064b79  xor     r9d, r9d
0x180064b7c  xor     r8d, r8d
0x180064b7f  mov     qword ptr [rsp+78h+var_58], 0
0x180064b88  xor     edx, edx
0x180064b8a  call    cs:__imp_ZwUpdateWnfStateData
0x180064b91  nop     dword ptr [rax+rax+00h]
0x180064b96  mov     r9b, [rbp+arg_20]; int
0x180064b9a  lea     rax, CiPolicyFailureAudit
0x180064ba1  mov     [rsp+78h+EventDescriptor], rax; EventDescriptor
0x180064ba6  lea     rdx, [rbp+var_28]; int
0x180064baa  mov     eax, dword ptr [rbp+arg_28]
0x180064bad  lea     rcx, [rbp+var_18]; int
0x180064bb1  mov     r8b, dil; int
0x180064bb4  mov     dword ptr [rsp+78h+var_58], eax; char
0x180064bb8  call    CiLogPolicyEvent
0x180064bbd  mov     rcx, rsi
0x180064bc0  call    CiLogSignatureInformation
0x180064bc5  mov     rcx, [rbp+var_38]
0x180064bc9  call    CipReleaseFileName
0x180064bce  mov     rcx, [rbp+var_30]
0x180064bd2  call    CipReleaseProcessName
0x180064bd7  add     rsp, 78h
0x180064bdb  pop     rdi
0x180064bdc  pop     rsi
0x180064bdd  pop     rbx
0x180064bde  pop     rbp
0x180064bdf  retn
```
