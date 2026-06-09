# FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0

- ea: `0x180034430`
- end: `0x1800344d0`
- name: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800343a0`

## callees

- `0x180007e38`
- `0x180011500`
- `0x1800120e0`
- `0x180034430`

## string_xrefs

- `0x18003446b`: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_CONFIG`
- `0x18003447f`: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_CONFIG`
- `0x180034496`: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`
- `0x1800344b2`: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0(_DWORD *a1, struct _SID_AND_ATTRIBUTES *a2)
{
  _BYTE *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  if ( !a1 || !a2 )
  {
    v4 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0", 3223453724LL);
    if ( !v4 )
      return v4;
    goto LABEL_9;
  }
  LODWORD(a2->Sid) = *a1;
  v3 = a1 + 1;
  if ( a1 == (_DWORD *)-4LL || (a1 = (_DWORD *)&a2->Sid + 1, a2 == (struct _SID_AND_ATTRIBUTES *)-4LL) )
  {
    v5 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_IPSEC_CIPHER_CONFIG", 3223453724LL);
    v4 = v5;
    if ( !v5 )
      return v4;
    WfpReportError(v5, "FwppDeepCopyToVerIndependent_IPSEC_CIPHER_CONFIG");
LABEL_9:
    FeFreeGroupsCallback(a2);
    WfpReportError(v4, "FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0");
    return v4;
  }
  v4 = 0;
  *(_BYTE *)a1 = *v3;
  return v4;
}

```

## disassembly

```asm
0x180034430  mov     [rsp+arg_0], rbx
0x180034435  push    rdi
0x180034436  sub     rsp, 20h
0x18003443a  mov     rdi, rdx
0x18003443d  test    rcx, rcx
0x180034440  jz      short loc_180034490
0x180034442  test    rdx, rdx
0x180034445  jz      short loc_180034490
0x180034447  mov     eax, [rcx]
0x180034449  mov     [rdx], eax
0x18003444b  lea     rax, [rcx+4]
0x18003444f  test    rax, rax
0x180034452  jz      short loc_180034465
0x180034454  lea     rcx, [rdx+4]
0x180034458  test    rcx, rcx
0x18003445b  jz      short loc_180034465
0x18003445d  mov     al, [rax]
0x18003445f  xor     ebx, ebx
0x180034461  mov     [rcx], al
0x180034463  jmp     short loc_1800344C1
0x180034465  mov     r8d, 0C022001Ch
0x18003446b  lea     rdx, aFwppdeepcopyto_30; "FwppDeepCopyToVerIndependent_IPSEC_CIPH"...
0x180034472  call    WfpReportSysErrorAsNtStatus
0x180034477  mov     rbx, rax
0x18003447a  test    rax, rax
0x18003447d  jz      short loc_1800344C1
0x18003447f  lea     rdx, aFwppdeepcopyto_30; "FwppDeepCopyToVerIndependent_IPSEC_CIPH"...
0x180034486  mov     rcx, rax
0x180034489  call    WfpReportError
0x18003448e  jmp     short loc_1800344AA
0x180034490  mov     r8d, 0C022001Ch
0x180034496  lea     rdx, aFwppdeepcopyto_93; "FwppDeepCopyToVerIndependent_IPSEC_CIPH"...
0x18003449d  call    WfpReportSysErrorAsNtStatus
0x1800344a2  mov     rbx, rax
0x1800344a5  test    rax, rax
0x1800344a8  jz      short loc_1800344C1
0x1800344aa  mov     rcx, rdi; pSidAttrArray
0x1800344ad  call    FeFreeGroupsCallback
0x1800344b2  lea     rdx, aFwppdeepcopyto_93; "FwppDeepCopyToVerIndependent_IPSEC_CIPH"...
0x1800344b9  mov     rcx, rbx
0x1800344bc  call    WfpReportError
0x1800344c1  mov     rax, rbx
0x1800344c4  mov     rbx, [rsp+28h+arg_0]
0x1800344c9  add     rsp, 20h
0x1800344cd  pop     rdi
0x1800344ce  retn
```
