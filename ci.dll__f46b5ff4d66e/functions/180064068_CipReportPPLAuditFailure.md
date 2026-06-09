# CipReportPPLAuditFailure

- ea: `0x180064068`
- end: `0x180064159`
- name: `CipReportPPLAuditFailure`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e55e0`

## callees

- `0x180064068`
- `0x18006c1d0`
- `0x18006cca8`
- `0x18009dca8`
- `0x18009eac8`
- `0x18009ed60`
- `0x1800a2270`

## import_xrefs

- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800640c9`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800640c9`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180064102`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180064102`

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
0x180064068  push    rbp
0x18006406a  push    rbx
0x18006406b  push    rsi
0x18006406c  push    rdi
0x18006406d  mov     rbp, rsp
0x180064070  sub     rsp, 78h
0x180064074  mov     rax, rdx
0x180064077  mov     [rbp+var_38], 0
0x18006407f  xorps   xmm0, xmm0
0x180064082  mov     [rbp+var_30], 0
0x18006408a  mov     rbx, r8
0x18006408d  lea     rdx, [rbp+var_28]
0x180064091  mov     rsi, rcx
0x180064094  lea     r8, [rbp+var_30]
0x180064098  mov     rcx, rax
0x18006409b  mov     dil, r9b
0x18006409e  movups  xmmword ptr [rbp+var_18], xmm0
0x1800640a2  movups  xmmword ptr [rbp+var_28], xmm0
0x1800640a6  call    CipQueryProcessName
0x1800640ab  lea     r8, [rbp+var_38]
0x1800640af  mov     rcx, rbx
0x1800640b2  lea     rdx, [rbp+var_18]
0x1800640b6  call    CipQueryFileName
0x1800640bb  mov     r8b, 1
0x1800640be  lea     rdx, a68; "68"
0x1800640c5  lea     rcx, [rbp+var_28]
0x1800640c9  call    cs:__imp_RtlFindUnicodeSubstring
0x1800640d0  nop     dword ptr [rax+rax+00h]
0x1800640d5  test    rax, rax
0x1800640d8  jz      short loc_18006410E
0x1800640da  mov     [rsp+78h+var_48], 0
0x1800640e2  lea     rcx, WNF_CI_LSAPPL_DLL_LOAD_FAILURE_AUDIT_MODE
0x1800640e9  mov     dword ptr [rsp+78h+EventDescriptor], 0
0x1800640f1  xor     r9d, r9d
0x1800640f4  xor     r8d, r8d
0x1800640f7  mov     qword ptr [rsp+78h+var_58], 0
0x180064100  xor     edx, edx
0x180064102  call    cs:__imp_ZwUpdateWnfStateData
0x180064109  nop     dword ptr [rax+rax+00h]
0x18006410e  mov     r9b, [rbp+arg_20]; int
0x180064112  lea     rax, CiPolicyFailureAudit
0x180064119  mov     [rsp+78h+EventDescriptor], rax; EventDescriptor
0x18006411e  lea     rdx, [rbp+var_28]; int
0x180064122  mov     eax, dword ptr [rbp+arg_28]
0x180064125  lea     rcx, [rbp+var_18]; int
0x180064129  mov     r8b, dil; int
0x18006412c  mov     dword ptr [rsp+78h+var_58], eax; char
0x180064130  call    CiLogPolicyEvent
0x180064135  mov     rcx, rsi
0x180064138  call    CiLogSignatureInformation
0x18006413d  mov     rcx, [rbp+var_38]
0x180064141  call    CipReleaseFileName
0x180064146  mov     rcx, [rbp+var_30]
0x18006414a  call    CipReleaseProcessName
0x18006414f  add     rsp, 78h
0x180064153  pop     rdi
0x180064154  pop     rsi
0x180064155  pop     rbx
0x180064156  pop     rbp
0x180064157  retn
```
