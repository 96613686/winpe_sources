# CfgAdtpAppendSecuritySubjectInfo

- ea: `0x18006f4e0`
- end: `0x18006f53e`
- name: `CfgAdtpAppendSecuritySubjectInfo`
- size: `94`
- prototype: `__int64 __fastcall(PSE_ADT_PARAMETER_ARRAY AuditParameters)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006e014`
- `0x18006e230`
- `0x18006e41c`
- `0x18006e6c0`
- `0x18006e968`
- `0x18006ecf0`
- `0x18006f024`
- `0x18006f30c`

## callees

- `0x18006f4e0`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x18006f503`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x18006f503`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f524`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f524`

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
0x18006f4e0  push    rbx
0x18006f4e2  sub     rsp, 20h
0x18006f4e6  mov     rbx, rcx
0x18006f4e9  mov     qword ptr [rsp+28h+AuthenticationId.LowPart], 0
0x18006f4f2  mov     rcx, [rdx]
0x18006f4f5  test    rcx, rcx
0x18006f4f8  jnz     short loc_18006F4FE
0x18006f4fa  mov     rcx, [rdx+10h]; Token
0x18006f4fe  lea     rdx, [rsp+28h+AuthenticationId]; AuthenticationId
0x18006f503  call    cs:__imp_SeQueryAuthenticationIdToken
0x18006f50a  nop     dword ptr [rax+rax+00h]
0x18006f50f  test    eax, eax
0x18006f511  js      short loc_18006F537
0x18006f513  mov     r8d, [rbx+8]; Index
0x18006f517  lea     r9, [rsp+28h+AuthenticationId]; Data
0x18006f51c  mov     edx, 5; Type
0x18006f521  mov     rcx, rbx; AuditParameters
0x18006f524  call    cs:__imp_SeSetAuditParameter
0x18006f52b  nop     dword ptr [rax+rax+00h]
0x18006f530  test    eax, eax
0x18006f532  js      short loc_18006F537
0x18006f534  inc     dword ptr [rbx+8]
0x18006f537  add     rsp, 20h
0x18006f53b  pop     rbx
0x18006f53c  retn
```
