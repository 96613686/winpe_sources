# CfgAdtReportContextOperation

- ea: `0x18006e230`
- end: `0x18006e415`
- name: `CfgAdtReportContextOperation`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006b19c`
- `0x18006b40c`

## callees

- `0x18006e230`
- `0x18006f4e0`
- `0x18006f628`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006e3ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e3ae`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e3e4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e3e4`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e2b2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e2b2`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e3d1`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e3d1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e2e9`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e32a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e35c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e38c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e2e9`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e32a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e35c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e38c`

## string_xrefs

- `0x18006e3a2`: `Security`

## pseudocode

```c
__int64 CfgAdtReportContextOperation(unsigned __int16 a1, int a2, __int64 *a3, int a4, ...)
{
  NTSTATUS appended; // ebx
  ULONG v7; // r8d
  __int64 *v8; // r9
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-B0h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+70h] [rbp-90h] BYREF
  va_list va; // [rsp+4E0h] [rbp+3E0h] BYREF

  va_start(va, a4);
  Data = a2;
  v11 = a4;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  DestinationString = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5064);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, AuditParameters.ParameterCount, &Data);
      if ( appended >= 0 )
      {
        v7 = ++AuditParameters.ParameterCount;
        if ( !a3 || (v8 = a3, !*(_WORD *)a3) )
          v8 = &qword_1800AA3B0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v7, v8);
        if ( appended >= 0 )
        {
          appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, ++AuditParameters.ParameterCount, &v11);
          if ( appended >= 0 )
          {
            appended = SeSetAuditParameter(
                         &AuditParameters,
                         SeAdtParmTypeHexUlong,
                         ++AuditParameters.ParameterCount,
                         va);
            if ( appended >= 0 )
            {
              ++AuditParameters.ParameterCount;
              RtlInitUnicodeString(&DestinationString, L"Security");
              appended = SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, &AuditParameters, 0x91u);
            }
          }
        }
      }
    }
    SeReleaseSubjectContext(&SubjectContext);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18006e230  mov     [rsp-8+arg_0], rbx
0x18006e235  push    rbp
0x18006e236  push    rsi
0x18006e237  push    rdi
0x18006e238  lea     rbp, [rsp-3A0h]
0x18006e240  sub     rsp, 4A0h
0x18006e247  mov     rax, cs:__security_cookie
0x18006e24e  xor     rax, rsp
0x18006e251  mov     [rbp+3B0h+var_20], rax
0x18006e258  mov     rdi, r8
0x18006e25b  mov     [rsp+4B0h+Data], edx
0x18006e25f  movzx   ebx, cx
0x18006e262  mov     [rsp+4B0h+var_478], r9d
0x18006e267  xor     edx, edx; Val
0x18006e269  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x18006e26e  mov     r8d, 418h; Size
0x18006e274  call    memset
0x18006e279  xorps   xmm1, xmm1
0x18006e27c  lea     rcx, [rsp+4B0h+AuditParameters]
0x18006e281  xorps   xmm0, xmm0
0x18006e284  mov     r8d, 13C8h
0x18006e28a  movzx   edx, bx
0x18006e28d  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x18006e292  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x18006e297  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x18006e29c  call    CfgAdtpInitializeParameters
0x18006e2a1  xor     esi, esi
0x18006e2a3  mov     ebx, eax
0x18006e2a5  test    eax, eax
0x18006e2a7  js      loc_18006E3F0
0x18006e2ad  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006e2b2  call    cs:__imp_SeCaptureSubjectContext
0x18006e2b9  nop     dword ptr [rax+rax+00h]
0x18006e2be  lea     rdx, [rsp+4B0h+SubjectContext]
0x18006e2c3  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e2c8  call    CfgAdtpAppendSecuritySubjectInfo
0x18006e2cd  mov     ebx, eax
0x18006e2cf  test    eax, eax
0x18006e2d1  js      loc_18006E3DF
0x18006e2d7  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x18006e2dc  lea     r9, [rsp+4B0h+Data]; Data
0x18006e2e1  lea     edx, [rsi+15h]; Type
0x18006e2e4  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e2e9  call    cs:__imp_SeSetAuditParameter
0x18006e2f0  nop     dword ptr [rax+rax+00h]
0x18006e2f5  mov     ebx, eax
0x18006e2f7  test    eax, eax
0x18006e2f9  js      loc_18006E3DF
0x18006e2ff  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e304  inc     r8d; Index
0x18006e307  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006e30c  test    rdi, rdi
0x18006e30f  jz      short loc_18006E319
0x18006e311  mov     r9, rdi
0x18006e314  cmp     [rdi], si
0x18006e317  jnz     short loc_18006E320
0x18006e319  lea     r9, qword_1800AA3B0; Data
0x18006e320  mov     edx, 1; Type
0x18006e325  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e32a  call    cs:__imp_SeSetAuditParameter
0x18006e331  nop     dword ptr [rax+rax+00h]
0x18006e336  mov     ebx, eax
0x18006e338  test    eax, eax
0x18006e33a  js      loc_18006E3DF
0x18006e340  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e345  lea     r9, [rsp+4B0h+var_478]; Data
0x18006e34a  inc     r8d; Index
0x18006e34d  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e352  mov     edx, 15h; Type
0x18006e357  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006e35c  call    cs:__imp_SeSetAuditParameter
0x18006e363  nop     dword ptr [rax+rax+00h]
0x18006e368  mov     ebx, eax
0x18006e36a  test    eax, eax
0x18006e36c  js      short loc_18006E3DF
0x18006e36e  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e373  lea     r9, [rbp+3B0h+arg_20]; Data
0x18006e37a  inc     r8d; Index
0x18006e37d  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e382  mov     edx, 0Ah; Type
0x18006e387  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006e38c  call    cs:__imp_SeSetAuditParameter
0x18006e393  nop     dword ptr [rax+rax+00h]
0x18006e398  mov     ebx, eax
0x18006e39a  test    eax, eax
0x18006e39c  js      short loc_18006E3DF
0x18006e39e  inc     [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e3a2  lea     rdx, aSecurity; "Security"
0x18006e3a9  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x18006e3ae  call    cs:__imp_RtlInitUnicodeString
0x18006e3b5  nop     dword ptr [rax+rax+00h]
0x18006e3ba  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e3bf  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006e3c7  xor     r8d, r8d; UserSid
0x18006e3ca  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x18006e3cf  xor     ecx, ecx; Flags
0x18006e3d1  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006e3d8  nop     dword ptr [rax+rax+00h]
0x18006e3dd  mov     ebx, eax
0x18006e3df  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006e3e4  call    cs:__imp_SeReleaseSubjectContext
0x18006e3eb  nop     dword ptr [rax+rax+00h]
0x18006e3f0  mov     eax, ebx
0x18006e3f2  mov     rcx, [rbp+3B0h+var_20]
0x18006e3f9  xor     rcx, rsp; StackCookie
0x18006e3fc  call    __security_check_cookie
0x18006e401  mov     rbx, [rsp+4B0h+arg_0]
0x18006e409  add     rsp, 4A0h
0x18006e410  pop     rdi
0x18006e411  pop     rsi
0x18006e412  pop     rbp
0x18006e413  retn
```
