# FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0

- ea: `0x18002fccc`
- end: `0x18002fd6c`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002fc3c`

## callees

- `0x180007e38`
- `0x180011500`
- `0x1800120e0`
- `0x18002fccc`

## string_xrefs

- `0x18002fd07`: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_CONFIG`
- `0x18002fd1b`: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_CONFIG`
- `0x18002fd32`: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`
- `0x18002fd4e`: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0(
        _DWORD *a1,
        struct _SID_AND_ATTRIBUTES *a2)
{
  _BYTE *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  if ( !a1 || !a2 )
  {
    v4 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0", 3223453724LL);
    if ( !v4 )
      return v4;
    goto LABEL_9;
  }
  LODWORD(a2->Sid) = *a1;
  v3 = a1 + 1;
  if ( a1 == (_DWORD *)-4LL || (a1 = (_DWORD *)&a2->Sid + 1, a2 == (struct _SID_AND_ATTRIBUTES *)-4LL) )
  {
    v5 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_CONFIG", 3223453724LL);
    v4 = v5;
    if ( !v5 )
      return v4;
    WfpReportError(v5, "FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_CONFIG");
LABEL_9:
    FeFreeGroupsCallback(a2);
    WfpReportError(v4, "FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0");
    return v4;
  }
  v4 = 0;
  *(_BYTE *)a1 = *v3;
  return v4;
}

```

## disassembly

```asm
0x18002fccc  mov     [rsp+arg_0], rbx
0x18002fcd1  push    rdi
0x18002fcd2  sub     rsp, 20h
0x18002fcd6  mov     rdi, rdx
0x18002fcd9  test    rcx, rcx
0x18002fcdc  jz      short loc_18002FD2C
0x18002fcde  test    rdx, rdx
0x18002fce1  jz      short loc_18002FD2C
0x18002fce3  mov     eax, [rcx]
0x18002fce5  mov     [rdx], eax
0x18002fce7  lea     rax, [rcx+4]
0x18002fceb  test    rax, rax
0x18002fcee  jz      short loc_18002FD01
0x18002fcf0  lea     rcx, [rdx+4]
0x18002fcf4  test    rcx, rcx
0x18002fcf7  jz      short loc_18002FD01
0x18002fcf9  mov     al, [rax]
0x18002fcfb  xor     ebx, ebx
0x18002fcfd  mov     [rcx], al
0x18002fcff  jmp     short loc_18002FD5D
0x18002fd01  mov     r8d, 0C022001Ch
0x18002fd07  lea     rdx, aFwppdeepcopyfr_12; "FwppDeepCopyFromVerIndependent_IPSEC_CI"...
0x18002fd0e  call    WfpReportSysErrorAsNtStatus
0x18002fd13  mov     rbx, rax
0x18002fd16  test    rax, rax
0x18002fd19  jz      short loc_18002FD5D
0x18002fd1b  lea     rdx, aFwppdeepcopyfr_12; "FwppDeepCopyFromVerIndependent_IPSEC_CI"...
0x18002fd22  mov     rcx, rax
0x18002fd25  call    WfpReportError
0x18002fd2a  jmp     short loc_18002FD46
0x18002fd2c  mov     r8d, 0C022001Ch
0x18002fd32  lea     rdx, aFwppdeepcopyfr_173; "FwppDeepCopyFromVerIndependent_IPSEC_CI"...
0x18002fd39  call    WfpReportSysErrorAsNtStatus
0x18002fd3e  mov     rbx, rax
0x18002fd41  test    rax, rax
0x18002fd44  jz      short loc_18002FD5D
0x18002fd46  mov     rcx, rdi; pSidAttrArray
0x18002fd49  call    FeFreeGroupsCallback
0x18002fd4e  lea     rdx, aFwppdeepcopyfr_173; "FwppDeepCopyFromVerIndependent_IPSEC_CI"...
0x18002fd55  mov     rcx, rbx
0x18002fd58  call    WfpReportError
0x18002fd5d  mov     rax, rbx
0x18002fd60  mov     rbx, [rsp+28h+arg_0]
0x18002fd65  add     rsp, 20h
0x18002fd69  pop     rdi
0x18002fd6a  retn
```
