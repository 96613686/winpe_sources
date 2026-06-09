# CfgAdtpAppendSecuritySubjectInfo

- ea: `0x18006eae0`
- end: `0x18006eb3e`
- name: `CfgAdtpAppendSecuritySubjectInfo`
- size: `94`
- prototype: `__int64 __fastcall(PSE_ADT_PARAMETER_ARRAY AuditParameters)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006d614`
- `0x18006d830`
- `0x18006da1c`
- `0x18006dcc0`
- `0x18006df68`
- `0x18006e2f0`
- `0x18006e624`
- `0x18006e90c`

## callees

- `0x18006eae0`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x18006eb03`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x18006eb03`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eb24`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eb24`

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
0x18006eae0  push    rbx
0x18006eae2  sub     rsp, 20h
0x18006eae6  mov     rbx, rcx
0x18006eae9  mov     qword ptr [rsp+28h+AuthenticationId.LowPart], 0
0x18006eaf2  mov     rcx, [rdx]
0x18006eaf5  test    rcx, rcx
0x18006eaf8  jnz     short loc_18006EAFE
0x18006eafa  mov     rcx, [rdx+10h]; Token
0x18006eafe  lea     rdx, [rsp+28h+AuthenticationId]; AuthenticationId
0x18006eb03  call    cs:__imp_SeQueryAuthenticationIdToken
0x18006eb0a  nop     dword ptr [rax+rax+00h]
0x18006eb0f  test    eax, eax
0x18006eb11  js      short loc_18006EB37
0x18006eb13  mov     r8d, [rbx+8]; Index
0x18006eb17  lea     r9, [rsp+28h+AuthenticationId]; Data
0x18006eb1c  mov     edx, 5; Type
0x18006eb21  mov     rcx, rbx; AuditParameters
0x18006eb24  call    cs:__imp_SeSetAuditParameter
0x18006eb2b  nop     dword ptr [rax+rax+00h]
0x18006eb30  test    eax, eax
0x18006eb32  js      short loc_18006EB37
0x18006eb34  inc     dword ptr [rbx+8]
0x18006eb37  add     rsp, 20h
0x18006eb3b  pop     rbx
0x18006eb3c  retn
```
