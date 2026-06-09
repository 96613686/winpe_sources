# CfgAdtReportProviderOperation

- ea: `0x18006f30c`
- end: `0x18006f4d8`
- name: `CfgAdtReportProviderOperation`
- size: `460`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006bf70`
- `0x18006ce40`

## callees

- `0x18006f30c`
- `0x18006f4e0`
- `0x18006f628`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006f471`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006f471`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006f4a7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006f4a7`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006f38b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006f38b`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006f494`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006f494`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f3c4`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f3f1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f421`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f44f`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f3c4`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f3f1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f421`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f44f`

## string_xrefs

- `0x18006f465`: `Security`

## pseudocode

```c
__int64 CfgAdtReportProviderOperation(unsigned __int16 a1, void *a2, void *a3, int a4, ...)
{
  NTSTATUS appended; // ebx
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+48h] [rbp-B8h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+70h] [rbp-90h] BYREF
  va_list va; // [rsp+4E0h] [rbp+3E0h] BYREF

  va_start(va, a4);
  Data = a4;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  DestinationString = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5063);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, AuditParameters.ParameterCount, a2);
      if ( appended >= 0 )
      {
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, ++AuditParameters.ParameterCount, a3);
        if ( appended >= 0 )
        {
          appended = SeSetAuditParameter(
                       &AuditParameters,
                       SeAdtParmTypeMessage,
                       ++AuditParameters.ParameterCount,
                       &Data);
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
0x18006f30c  mov     [rsp-8+arg_0], rbx
0x18006f311  push    rbp
0x18006f312  push    rsi
0x18006f313  push    rdi
0x18006f314  lea     rbp, [rsp-3A0h]
0x18006f31c  sub     rsp, 4A0h
0x18006f323  mov     rax, cs:__security_cookie
0x18006f32a  xor     rax, rsp
0x18006f32d  mov     [rbp+3B0h+var_20], rax
0x18006f334  mov     rsi, r8
0x18006f337  mov     [rsp+4B0h+Data], r9d
0x18006f33c  mov     rdi, rdx
0x18006f33f  movzx   ebx, cx
0x18006f342  xor     edx, edx; Val
0x18006f344  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x18006f349  mov     r8d, 418h; Size
0x18006f34f  call    memset
0x18006f354  xorps   xmm1, xmm1
0x18006f357  lea     rcx, [rsp+4B0h+AuditParameters]
0x18006f35c  xorps   xmm0, xmm0
0x18006f35f  mov     r8d, 13C7h
0x18006f365  movzx   edx, bx
0x18006f368  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x18006f36d  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x18006f372  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x18006f377  call    CfgAdtpInitializeParameters
0x18006f37c  mov     ebx, eax
0x18006f37e  test    eax, eax
0x18006f380  js      loc_18006F4B3
0x18006f386  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006f38b  call    cs:__imp_SeCaptureSubjectContext
0x18006f392  nop     dword ptr [rax+rax+00h]
0x18006f397  lea     rdx, [rsp+4B0h+SubjectContext]
0x18006f39c  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006f3a1  call    CfgAdtpAppendSecuritySubjectInfo
0x18006f3a6  mov     ebx, eax
0x18006f3a8  test    eax, eax
0x18006f3aa  js      loc_18006F4A2
0x18006f3b0  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x18006f3b5  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006f3ba  mov     r9, rdi; Data
0x18006f3bd  mov     edi, 1
0x18006f3c2  mov     edx, edi; Type
0x18006f3c4  call    cs:__imp_SeSetAuditParameter
0x18006f3cb  nop     dword ptr [rax+rax+00h]
0x18006f3d0  mov     ebx, eax
0x18006f3d2  test    eax, eax
0x18006f3d4  js      loc_18006F4A2
0x18006f3da  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006f3df  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006f3e4  add     r8d, edi; Index
0x18006f3e7  mov     r9, rsi; Data
0x18006f3ea  mov     edx, edi; Type
0x18006f3ec  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006f3f1  call    cs:__imp_SeSetAuditParameter
0x18006f3f8  nop     dword ptr [rax+rax+00h]
0x18006f3fd  mov     ebx, eax
0x18006f3ff  test    eax, eax
0x18006f401  js      loc_18006F4A2
0x18006f407  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006f40c  lea     r9, [rsp+4B0h+Data]; Data
0x18006f411  add     r8d, edi; Index
0x18006f414  lea     edx, [rdi+14h]; Type
0x18006f417  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006f41c  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006f421  call    cs:__imp_SeSetAuditParameter
0x18006f428  nop     dword ptr [rax+rax+00h]
0x18006f42d  mov     ebx, eax
0x18006f42f  test    eax, eax
0x18006f431  js      short loc_18006F4A2
0x18006f433  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006f438  lea     r9, [rbp+3B0h+arg_20]; Data
0x18006f43f  add     r8d, edi; Index
0x18006f442  lea     edx, [rdi+9]; Type
0x18006f445  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006f44a  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006f44f  call    cs:__imp_SeSetAuditParameter
0x18006f456  nop     dword ptr [rax+rax+00h]
0x18006f45b  mov     ebx, eax
0x18006f45d  test    eax, eax
0x18006f45f  js      short loc_18006F4A2
0x18006f461  add     [rsp+4B0h+AuditParameters.ParameterCount], edi
0x18006f465  lea     rdx, aSecurity; "Security"
0x18006f46c  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x18006f471  call    cs:__imp_RtlInitUnicodeString
0x18006f478  nop     dword ptr [rax+rax+00h]
0x18006f47d  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006f482  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006f48a  xor     r8d, r8d; UserSid
0x18006f48d  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x18006f492  xor     ecx, ecx; Flags
0x18006f494  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006f49b  nop     dword ptr [rax+rax+00h]
0x18006f4a0  mov     ebx, eax
0x18006f4a2  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006f4a7  call    cs:__imp_SeReleaseSubjectContext
0x18006f4ae  nop     dword ptr [rax+rax+00h]
0x18006f4b3  mov     eax, ebx
0x18006f4b5  mov     rcx, [rbp+3B0h+var_20]
0x18006f4bc  xor     rcx, rsp; StackCookie
0x18006f4bf  call    __security_check_cookie
0x18006f4c4  mov     rbx, [rsp+4B0h+arg_0]
0x18006f4cc  add     rsp, 4A0h
0x18006f4d3  pop     rdi
0x18006f4d4  pop     rsi
0x18006f4d5  pop     rbp
0x18006f4d6  retn
```
