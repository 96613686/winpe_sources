# CfgAdtpAppendSecuritySubjectInfo

- ea: `0x180078c80`
- end: `0x180078cde`
- name: `CfgAdtpAppendSecuritySubjectInfo`
- size: `94`
- prototype: `__int64 __fastcall(PSE_ADT_PARAMETER_ARRAY AuditParameters)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800777b4`
- `0x1800779d0`
- `0x180077bbc`
- `0x180077e60`
- `0x180078108`
- `0x180078490`
- `0x1800787c4`
- `0x180078aac`

## callees

- `0x180078c80`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x180078ca3`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x180078ca3`
- `ntoskrnl!SeSetAuditParameter` at `0x180078cc4`
- `ntoskrnl!SeSetAuditParameter` at `0x180078cc4`

## pseudocode

```c
NTSTATUS __fastcall CfgAdtpAppendSecuritySubjectInfo(PSE_ADT_PARAMETER_ARRAY AuditParameters, __int64 a2)
{
  void *v3; // rcx
  NTSTATUS result; // eax
  struct _LUID AuthenticationId; // [rsp+38h] [rbp+10h] BYREF

  AuthenticationId = 0;
  v3 = *(void **)a2;
  if ( !*(_QWORD *)a2 )
    v3 = *(void **)(a2 + 16);
  result = SeQueryAuthenticationIdToken(v3, &AuthenticationId);
  if ( result >= 0 )
  {
    result = SeSetAuditParameter(
               AuditParameters,
               SeAdtParmTypeLogonId,
               AuditParameters->ParameterCount,
               &AuthenticationId);
    if ( result >= 0 )
      ++AuditParameters->ParameterCount;
  }
  return result;
}

```

## disassembly

```asm
0x180078c80  push    rbx
0x180078c82  sub     rsp, 20h
0x180078c86  mov     rbx, rcx
0x180078c89  mov     qword ptr [rsp+28h+AuthenticationId.LowPart], 0
0x180078c92  mov     rcx, [rdx]
0x180078c95  test    rcx, rcx
0x180078c98  jnz     short loc_180078C9E
0x180078c9a  mov     rcx, [rdx+10h]; Token
0x180078c9e  lea     rdx, [rsp+28h+AuthenticationId]; AuthenticationId
0x180078ca3  call    cs:__imp_SeQueryAuthenticationIdToken
0x180078caa  nop     dword ptr [rax+rax+00h]
0x180078caf  test    eax, eax
0x180078cb1  js      short loc_180078CD7
0x180078cb3  mov     r8d, [rbx+8]; Index
0x180078cb7  lea     r9, [rsp+28h+AuthenticationId]; Data
0x180078cbc  mov     edx, 5; Type
0x180078cc1  mov     rcx, rbx; AuditParameters
0x180078cc4  call    cs:__imp_SeSetAuditParameter
0x180078ccb  nop     dword ptr [rax+rax+00h]
0x180078cd0  test    eax, eax
0x180078cd2  js      short loc_180078CD7
0x180078cd4  inc     dword ptr [rbx+8]
0x180078cd7  add     rsp, 20h
0x180078cdb  pop     rbx
0x180078cdc  retn
```
