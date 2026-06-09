# FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0

- ea: `0x18002fb94`
- end: `0x18002fc34`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002fb04`

## callees

- `0x180007e38`
- `0x180011500`
- `0x1800120e0`
- `0x18002fb94`

## string_xrefs

- `0x18002fbcf`: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_CONFIG`
- `0x18002fbe3`: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_CONFIG`
- `0x18002fbfa`: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`
- `0x18002fc16`: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0(_DWORD *a1, struct _SID_AND_ATTRIBUTES *a2)
{
  _BYTE *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  if ( !a1 || !a2 )
  {
    v4 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0", 3223453724LL);
    if ( !v4 )
      return v4;
    goto LABEL_9;
  }
  LODWORD(a2->Sid) = *a1;
  v3 = a1 + 1;
  if ( a1 == (_DWORD *)-4LL || (a1 = (_DWORD *)&a2->Sid + 1, a2 == (struct _SID_AND_ATTRIBUTES *)-4LL) )
  {
    v5 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_IPSEC_AUTH_CONFIG", 3223453724LL);
    v4 = v5;
    if ( !v5 )
      return v4;
    WfpReportError(v5, "FwppDeepCopyFromVerIndependent_IPSEC_AUTH_CONFIG");
LABEL_9:
    FeFreeGroupsCallback(a2);
    WfpReportError(v4, "FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0");
    return v4;
  }
  v4 = 0;
  *(_BYTE *)a1 = *v3;
  return v4;
}

```

## disassembly

```asm
0x18002fb94  mov     [rsp+arg_0], rbx
0x18002fb99  push    rdi
0x18002fb9a  sub     rsp, 20h
0x18002fb9e  mov     rdi, rdx
0x18002fba1  test    rcx, rcx
0x18002fba4  jz      short loc_18002FBF4
0x18002fba6  test    rdx, rdx
0x18002fba9  jz      short loc_18002FBF4
0x18002fbab  mov     eax, [rcx]
0x18002fbad  mov     [rdx], eax
0x18002fbaf  lea     rax, [rcx+4]
0x18002fbb3  test    rax, rax
0x18002fbb6  jz      short loc_18002FBC9
0x18002fbb8  lea     rcx, [rdx+4]
0x18002fbbc  test    rcx, rcx
0x18002fbbf  jz      short loc_18002FBC9
0x18002fbc1  mov     al, [rax]
0x18002fbc3  xor     ebx, ebx
0x18002fbc5  mov     [rcx], al
0x18002fbc7  jmp     short loc_18002FC25
0x18002fbc9  mov     r8d, 0C022001Ch
0x18002fbcf  lea     rdx, aFwppdeepcopyfr_50; "FwppDeepCopyFromVerIndependent_IPSEC_AU"...
0x18002fbd6  call    WfpReportSysErrorAsNtStatus
0x18002fbdb  mov     rbx, rax
0x18002fbde  test    rax, rax
0x18002fbe1  jz      short loc_18002FC25
0x18002fbe3  lea     rdx, aFwppdeepcopyfr_50; "FwppDeepCopyFromVerIndependent_IPSEC_AU"...
0x18002fbea  mov     rcx, rax
0x18002fbed  call    WfpReportError
0x18002fbf2  jmp     short loc_18002FC0E
0x18002fbf4  mov     r8d, 0C022001Ch
0x18002fbfa  lea     rdx, aFwppdeepcopyfr_152; "FwppDeepCopyFromVerIndependent_IPSEC_AU"...
0x18002fc01  call    WfpReportSysErrorAsNtStatus
0x18002fc06  mov     rbx, rax
0x18002fc09  test    rax, rax
0x18002fc0c  jz      short loc_18002FC25
0x18002fc0e  mov     rcx, rdi; pSidAttrArray
0x18002fc11  call    FeFreeGroupsCallback
0x18002fc16  lea     rdx, aFwppdeepcopyfr_152; "FwppDeepCopyFromVerIndependent_IPSEC_AU"...
0x18002fc1d  mov     rcx, rbx
0x18002fc20  call    WfpReportError
0x18002fc25  mov     rax, rbx
0x18002fc28  mov     rbx, [rsp+28h+arg_0]
0x18002fc2d  add     rsp, 20h
0x18002fc31  pop     rdi
0x18002fc32  retn
```
